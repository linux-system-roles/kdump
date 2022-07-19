Changelog
=========

[1.2.5] - 2022-07-19
--------------------

### New Features

- none

### Bug Fixes

- none

### Other Changes

- make min_ansible_version a string in meta/main.yml (#104)

The Ansible developers say that `min_ansible_version` in meta/main.yml
must be a `string` value like `"2.9"`, not a `float` value like `2.9`.

- Add CHANGELOG.md (#105)

[1.2.4] - 2022-05-06
--------------------

### New Features

- none

### Bug Fixes

- none

### Other Changes

- bump tox-lsr version to 2.11.0; remove py37; add py310

[1.2.3] - 2022-04-13
--------------------

### New features

- support gather\_facts: false; support setup-snapshot.yml

### Bug Fixes

- none

### Other Changes

- bump tox-lsr version to 2.10.1

[1.2.2] - 2022-02-08
--------------------

### New features

- use kdumpctl reset-crashkernel on rhel9

### Bug Fixes

- none

### Other Changes

- bump tox-lsr version to 2.9.1

[1.2.1] - 2022-01-10
--------------------

### New Features

- none

### Bug Fixes

- none

### Other Changes

- bump tox-lsr version to 2.8.3
- change recursive role symlink to individual role dir symlinks

[1.2.0] - 2021-12-03
--------------------

### New features

- Add reboot required

### Bug Fixes

- none

### Other Changes

- update tox-lsr version to 2.8.0

[1.1.2] - 2021-11-08
--------------------

### New Features

- none

### Bug Fixes

- none

### Other Changes

- update tox-lsr version to 2.7.1
- support python 39, ansible-core 2.12, ansible-plugin-scan

[1.1.1] - 2021-09-22
--------------------

### New Features

- none

### Bug Fixes

- Use {{ ansible\_managed | comment }} to fix multi-line ansible\_managed
- remove authorized\_key; use ansible builtins

### Other Changes

- use apt-get install -y
- use tox-lsr version 2.5.1

[1.1.0] - 2021-08-10
--------------------

### New features

- Drop support for Ansible 2.8 by bumping the Ansible version to 2.9

### Bug Fixes

- none

### Other Changes

- none

[1.0.5] - 2021-06-09
--------------------

### New features

- use localhost if no SSH\_CONNECTION env. var.

### Bug Fixes

- none

### Other Changes

- none

[1.0.4] - 2021-05-05
--------------------

### New features

- Add `KDUMP_BOOTDIR="/boot"`to `/etc/sysconfig/kdump` for RedHat oses \<7
- Copy the dump target's public host key to the managed node known\_hosts.

### Bug fixes

- Cleaning up ansible-lint errors
- fixing ansible-test errors
- Avoid bare variable in when and the resulting warning.

### Other Changes

- Remove python-26 environment from tox testing
- update to tox-lsr 2.4.0 - add support for ansible-test sanity with docker
- Add tags to tests
- CI: Add support for RHEL-9

[1.0.3] - 2021-02-11
--------------------

### New Features

- Add centos8

### Bug Fixes

- Get rid of the extra final newline in string
- Fix centos6 repos; use standard centos images

### Other Changes

- use tox-lsr 2.2.0
- use molecule v3, drop v2 - use tox-lsr 2.1.2
- remove ansible 2.7 support from molecule
- use tox for ansible-lint instead of molecule
- use new tox-lsr plugin
- disable yamllint line-length checks
- disable line-length
- add shellcheck,collection
- use github actions instead of travis

[1.0.2] - 2020-10-14
--------------------

### New Features

- none

### Bug Fixes

- none

### Other Changes

- lock ansible-lint version at 4.3.5; suppress role name lint warning
- sync collections related changes from template to kdump role
- collections prep - use FQRN
- Synchronize files from linux-system-roles/template

[1.0.1] - 2020-08-05
--------------------

### New Features

- Rename 'dump\_target.kind' to 'type' in conf template.

### Bug Fixes

- Fix lint errors, fix checkmode

### Other Changes

- Synchronize files from linux-system-roles/template
- use molecule v2
- Run tests in wrappers
- Configure Molecule and Travis CI

[1.0.0] - 2018-08-21
--------------------

### Initial Release
