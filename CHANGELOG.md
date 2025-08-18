Changelog
=========

[1.4.13] - 2025-08-18
--------------------

### Other Changes

- test: run handlers after each role invocation to ensure role works (#245)

[1.4.12] - 2025-08-08
--------------------

### Other Changes

- test: default wrapper should use local connection if local (#243)

[1.4.11] - 2025-07-02
--------------------

### Other Changes

- ci: Check spelling with codespell (#229)
- ci: Add test plan that runs CI tests and customize it for each role (#230)
- ci: In test plans, prefix all relate variables with SR_ (#231)
- ci: Fix bug with ARTIFACTS_URL after prefixing with SR_ (#232)
- ci: several changes related to new qemu test, ansible-lint, python versions, ubuntu versions (#233)
- ci: use tox-lsr 3.6.0; improve qemu test logging (#234)
- ci: skip storage scsi, nvme tests in github qemu ci (#235)
- ci: bump sclorg/testing-farm-as-github-action from 3 to 4 (#236)
- ci: bump tox-lsr to 3.8.0; rename qemu/kvm tests (#237)
- ci: Add Fedora 42; use tox-lsr 3.9.0; use lsr-report-errors for qemu tests (#238)
- ci: Add support for bootc end-to-end validation tests (#239)
- ci: Use ansible 2.19 for fedora 42 testing; support python 3.13 (#240)
- refactor: support ansible 2.19 (#241)

[1.4.10] - 2025-02-04
--------------------

### Other Changes

- ci: ansible-plugin-scan is disabled for now (#223)
- ci: bump ansible-lint to v25; provide collection requirements for ansible-lint (#226)
- test: fix ssh wrapper test (#227)

[1.4.9] - 2025-01-09
--------------------

### Other Changes

- ci: Use Fedora 41, drop Fedora 39 (#220)
- ci: Use Fedora 41, drop Fedora 39 - part two (#221)

[1.4.8] - 2024-10-30
--------------------

### Other Changes

- ci: Add tft plan and workflow (#208)
- ci: Update fmf plan to add a separate job to prepare managed nodes (#210)
- ci: bump sclorg/testing-farm-as-github-action from 2 to 3 (#211)
- ci: Add workflow for ci_test bad, use remote fmf plan (#212)
- ci: Fix missing slash in ARTIFACTS_URL (#213)
- ci: Add tags to TF workflow, allow more [citest bad] formats (#214)
- ci: ansible-test action now requires ansible-core version (#215)
- ci: add YAML header to github action workflow files (#216)
- refactor: Use vars/RedHat_N.yml symlink for CentOS, Rocky, Alma wherever possible (#218)

[1.4.7] - 2024-07-02
--------------------

### Bug Fixes

- fix: el10 kdump role should depend on kdump-utils (#204)
- fix: add support for EL10 (#206)

### Other Changes

- ci: ansible-lint action now requires absolute directory (#205)

[1.4.6] - 2024-06-11
--------------------

### Other Changes

- ci: use tox-lsr 3.3.0 which uses ansible-test 2.17 (#199)
- ci: tox-lsr 3.4.0 - fix py27 tests; move other checks to py310 (#201)
- ci: Add supported_ansible_also to .ansible-lint (#202)

[1.4.5] - 2024-04-04
--------------------

### Other Changes

- ci: fix python unit test - copy pytest config to tests/unit (#195)
- ci: bump ansible/ansible-lint from 6 to 24 (#196)
- ci: bump mathieudutour/github-tag-action from 6.1 to 6.2 (#197)

[1.4.4] - 2024-01-16
--------------------

### Other Changes

- ci: support ansible-lint and ansible-test 2.16 (#192)
- ci: Use supported ansible-lint action; run ansible-lint against the collection (#193)

[1.4.3] - 2023-12-08
--------------------

### Other Changes

- ci: bump actions/github-script from 6 to 7 (#189)
- refactor: get_ostree_data.sh use env shebang - remove from .sanity* (#190)

[1.4.2] - 2023-11-30
--------------------

### Other Changes

- test: clean up kdump_path (#187)

[1.4.1] - 2023-11-29
--------------------

### Other Changes

- refactor: improve support for ostree systems (#185)

[1.4.0] - 2023-11-06
--------------------

### New Features

- feat: support for ostree systems (#182)

### Other Changes

- build(deps): bump actions/checkout from 3 to 4 (#173)
- ci: ensure dependabot git commit message conforms to commitlint (#176)
- ci: use dump_packages.py callback to get packages used by role (#178)
- ci: tox-lsr version 3.1.1 (#180)

[1.3.8] - 2023-09-12
--------------------

### Bug Fixes

- fix: retry read of kexec_crash_size (#169)

### Other Changes

- test: delete kdump user last, retry until success (#171)

[1.3.7] - 2023-09-07
--------------------

### Other Changes

- docs: Make badges consistent, run markdownlint on all .md files (#167)

  - Consistently generate badges for GH workflows in README RHELPLAN-146921
  - Run markdownlint on all .md files
  - Add custom-woke-action if not used already
  - Rename woke action to Woke for a pretty badge
  
  Signed-off-by: Sergei Petrosian <spetrosi@redhat.com>

- ci: Remove badges from README.md prior to converting to HTML (#168)

  - Remove thematic break after badges
  - Remove badges from README.md prior to converting to HTML
  
  Signed-off-by: Sergei Petrosian <spetrosi@redhat.com>

[1.3.6] - 2023-08-17
--------------------

### Bug Fixes

- fix: ensure .ssh directory exists for kdump_ssh_user on kdump_ssh_server (#164)
- fix: Ensure authorized_keys management works with multiple hosts (#165)

[1.3.5] - 2023-08-16
--------------------

### Bug Fixes

- fix: do not fail if authorized_keys not found (#161)
- fix: Write new authorized_keys if needed is not idempotent (#162)

### Other Changes

- ci: Add markdownlint, test_converting_readme, and build_docs workflows (#160)

[1.3.4] - 2023-08-02
--------------------

### Other Changes

- test: call handlers to refresh kdump before calling role again (#158)

[1.3.3] - 2023-07-30
--------------------

### Bug Fixes

- fix: use failure_action instead of default on EL9 and later (#155)

### Other Changes

- test: add test for failure_action (#156)

[1.3.2] - 2023-07-19
--------------------

### Bug Fixes

- fix: facts being gathered unnecessarily (#152)

### Other Changes

- ci: Rename commitlint to PR title Lint, echo PR titles from env var (#150)
- ci: ansible-lint - ignore var-naming[no-role-prefix] (#151)

[1.3.1] - 2023-06-20
--------------------

### Other Changes

- ci: Add pull request template and run commitlint on PR title only (#147)
- test: add test for crashkernel, dracut settings (#148)

[1.3.0] - 2023-05-26
--------------------

### New Features

- feat: Add support for auto_reset_crashkernel and dracut_args

### Bug Fixes

- fix: do not use /etc/sysconfig/kdump
- fix: use grubby to update crashkernel=auto if needed

### Other Changes

- docs: Consistent contributing.md for all roles - allow role specific contributing.md section

[1.2.9] - 2023-04-27
--------------------

### Other Changes

- test: check generated files for ansible_managed, fingerprint
- ci: Add commitlint GitHub action to ensure conventional commits with feedback

[1.2.8] - 2023-04-13
--------------------

### Other Changes

- ansible-lint - use changed_when even for conditional execution (#138)

[1.2.7] - 2023-04-06
--------------------

### Bug Fixes

- Use ansible_os_family in template (#133)

### Other Changes

- Remove unused test script "semaphore" (#131)
- Add README-ansible.md to refer Ansible intro page on linux-system-roles.github.io (#134)
- Fingerprint RHEL System Role managed config files (#136)

[1.2.6] - 2023-01-16
--------------------

### New Features

- none

### Bug Fixes

- none

### Other Changes

- ansible-lint 6.x fixes
- Add check for non-inclusive language
- CHANGELOG.md - cleanup non-inclusive words.

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
- update to tox-lsr 2.4.0 - add support for ansible-test with docker
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
