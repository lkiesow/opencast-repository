Ansible: Opencast Repository Role
=================================

This Ansible role enables the package repository for RHEL, CentOS, Debian or Ubuntu.


Role Variables
--------------

- `opencast.version.major`
  - The version of Opencast for which the repository should be installed.
- `repository.enabled.release`
  - If the release repository shall be enabled (default: `false`)
- `repository.enabled.testing`
  - If the testing repository shall be enabled (default: `false`)


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: servers
  become: true
  roles:
    - role: lkiesow.opencast_repository
      opencast:
        version:
          major: 9
```
