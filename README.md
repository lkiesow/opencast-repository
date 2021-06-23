Ansible: Opencast Repository Role
=================================

This Ansible role enables the package repository for RHEL, CentOS, Debian or Ubuntu.


Role Variables
--------------

- `opencast_version_major`
  - The version of Opencast for which the repository should be installed (_required_).
- `opencast_repository_enabled_release`
  - If the release repository shall be enabled (default: `false`)
- `opencast_repository_enabled_testing`
  - If the testing repository shall be enabled (default: `false`)


Example Playbook
----------------

Example of how to configure and use the role:

```yaml
- hosts: servers
  become: true
  roles:
    - role: lkiesow.opencast_repository
      opencast_version_major: 9
```
