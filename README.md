
# Ansible Role: Kernel Crash Dump

An ansible role which configures kdump.

## Role Variables

**dump_target**: Can be specified to write vmcore to a location that is not in
the root file system. If `type` is `raw` or a filesystem type, location points
to a partition (by device node name, label, or uuid). For example:

```yaml
dump_target:
  type: raw
  location: /dev/sda1
```

or for an `ext4` filesystem:

```yaml
dump_target:
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

**path**: The path to which vmcore will be written. If `dump_target` is not
null, path is relative to that dump target. Otherwise, it must be an absolute
path in the root file system.

**core_collector**: A command to copy the vmcore. If null, uses `makedumpfile`
with options depending on the `target_type`.

**system_action**:
  The action that is performed when dumping the core file fails. Can be
  `reboot`, `halt`, `poweroff`, or `shell`.

## License

MIT
