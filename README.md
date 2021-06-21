Ansible: Opencast Repository Role
=================================

This Ansible role enables the package repository for RHEL, CentOS, Debian or Ubuntu.


Role Variables
--------------

- `opencast_version_major`
  - The version of Opencast for which the repository should be installed.
- `opencast_repository_enabled_release`
  - If the release repository shall be enabled (default: `false`)
- `opencast_repository_enabled_testing`
  - If the testing repository shall be enabled (default: `false`)


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: servers
  become: true
  roles:
    - role: lkiesow.opencast_repository
      opencast_version_major: 9
```
