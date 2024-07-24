
# Ansible Role: Kernel Crash Dump

[![ansible-lint.yml](https://github.com/linux-system-roles/kdump/actions/workflows/ansible-lint.yml/badge.svg)](https://github.com/linux-system-roles/kdump/actions/workflows/ansible-lint.yml) [![ansible-test.yml](https://github.com/linux-system-roles/kdump/actions/workflows/ansible-test.yml/badge.svg)](https://github.com/linux-system-roles/kdump/actions/workflows/ansible-test.yml) [![markdownlint.yml](https://github.com/linux-system-roles/kdump/actions/workflows/markdownlint.yml/badge.svg)](https://github.com/linux-system-roles/kdump/actions/workflows/markdownlint.yml) [![tft.yml](https://github.com/linux-system-roles/kdump/actions/workflows/tft.yml/badge.svg)](https://github.com/linux-system-roles/kdump/actions/workflows/tft.yml) [![woke.yml](https://github.com/linux-system-roles/kdump/actions/workflows/woke.yml/badge.svg)](https://github.com/linux-system-roles/kdump/actions/workflows/woke.yml)

An ansible role which configures kdump.

## Warning

The role replaces the kdump configuration of the managed
host. Previous settings will be lost, even if they are not specified
in the role variables. Currently, this includes replacing at least the
following configuration file:

* `/etc/kdump.conf`

## Requirements

See below

### Collection requirements

The role requires external collections only for management of `rpm-ostree`
nodes. Please run the following command to install them if you need to manage
`rpm-ostree` nodes:

```bash
ansible-galaxy collection install -vv -r meta/collection-requirements.yml
```

## Role Variables

**kdump_target**: Can be specified to write vmcore to a location that is not in
the root file system. If `type` is `raw` or a filesystem type, location points
to a partition (by device node name, label, or uuid). For example:

```yaml
kdump_target:
  type: raw
  location: /dev/sda1
```

or for an `ext4` filesystem:

```yaml
kdump_target:
  type: ext4
  location: "12e3e25f-534e-4007-a40c-e7e080a933ad"
```

If `type` is `ssh`, location points to a server:
example:

```yaml
  type: ssh
  location: user@example.com
```

Similarly for `nfs`, `location` points to an nfs server:

```yaml
  type: nfs
  location: nfs.example.com
```

Only the `ssh` type is considered stable, support for the other types
is experimental.

**kdump_path**: The path to which vmcore will be written. If `kdump_target` is not
null, path is relative to that dump target. Otherwise, it must be an absolute
path in the root file system.

**kdump_core_collector**: A command to copy the vmcore. If null, uses `makedumpfile`
with options depending on the `kdump_target.type`.

**kdump_system_action**:
  The action that is performed when dumping the core file fails. Can be
  `reboot`, `halt`, `poweroff`, or `shell`.

**kdump_auto_reset_crashkernel**:
  Whether to reset kernel crashkernel to new default value or not when kexec-tools
  updates the default crashkernel value and existing kernels using the old default
  kernel crashkernel value.

**kdump_dracut_args**:
  Pass extra dracut options when rebuilding kdump initrd.

**kdump_reboot_ok**: If you run the role on a managed node that does not have
memory reserved for crash kernel, i.e. the file `/sys/kernel/kexec_crash_size`
contains `0`, it might be required to reboot the managed node to configure kdump.

By default, the role does not reboot the managed node. If a managed node
requires reboot, the role sets the `kdump_reboot_required` fact and fails, so
that the user can reboot the managed node when needed. If you want the role to
reboot the system if required, set this variable to `true`. You do not need to
re-execute the role after boot.

Default: `false`

## Ansible Facts Returned by the Role

**kdump_reboot_required**: The role sets this fact if the managed node requires
reboot to complete kdump configuration. Re-execute the role after boot to ensure
that kdump is working.

## rpm-ostree

See README-ostree.md

## License

MIT
