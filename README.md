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
- `opencast_repository_identifiers:`
  - List of RPM repository identifiers.
  - This variable is not actually used in this role but can be used by other roles to temporarily activate the repository.
    For example, you can have it deactivated by default and then activate it in the install task.
  - Other tasks rely on this being present.
  - This holds the identifier for the stable repositories by default (`[opencast-noarch, opencast-x86_64]`).
- `opencast_repository_identifiers_testing:`
  - List of testing RPM repository identifiers.
  - This holds the identifier for the testing repositories by default (`[opencast-testing-noarch, opencast-testing-x86_64]`).


Example Playbook
----------------

Example of how to configure and use the role:

```yaml
- hosts: servers
  become: true
  roles:
    - role: elan.opencast_repository
      opencast_version_major: 9
```
