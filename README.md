Ansible: Opencast Repository Role
=================================

![molecule](https://github.com/elan-ev/opencast_repository/actions/workflows/molecule.yml/badge.svg)

This Ansible role enables the package repository for RHEL, CentOS, Debian or Ubuntu.


Role Variables
--------------

- `opencast_version_major`
  - The version of Opencast for which the repository should be installed (_required_).
- `opencast_repository_enabled_release`
  - If the release repository shall be enabled (default: `false`)
- `opencast_repository_enabled_testing`
  - If the testing repository shall be enabled (default: `false`)
- `opencast_repository_enable_epel`
  - Opencast uses some dependencies from EPEL RPM repository.
    Here you can enable (value: `true`) or disable (value: `false`) installation of the
    `epel-release` package (default: `true`). On RedHat installation with Satellite this
    property can be handy. On Debian based systems this property do nothing.
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

Development
-----------

For development and testing you can use [molecule](https://molecule.readthedocs.io/en/latest/).
With podman as driver you can install it like this – preferably in a virtual environment (if you use docker, substitute `podman` with `docker`):

```bash
pip install -r .dev_requirements.txt
```

Then you can *create* the test instances, apply the ansible config (*converge*) and *destroy* the test instances with these commands:

```bash
molecule create
molecule converge
molecule destroy
```

If you want to inspect a running test instance use `molecule login --host <instance_name>`, where you replace `<instance_name>` with the desired value.

To test the role run `molecule test`.

License
-------

[BSD-3-Clause](LICENSE)

Author Information
------------------

[ELAN e.V](https://elan-ev.de/)
