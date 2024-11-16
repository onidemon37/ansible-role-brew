Role Name
=========

This role installs Homebrew on Debian, Ubuntu, and Arch Linux systems.

Requirements
------------

- Ansible 2.11 or higher
- Supported platforms:
  - Debian 11, 12
  - Ubuntu 20.04, 22.04, 24.04
  - Arch Linux

Role Variables
--------------

| Variable       | Default                    | Description               |
|----------------|----------------------------|---------------------------|
| `homebrew_path` | `/home/linuxbrew/.linuxbrew` | Path to Homebrew installation |

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: all
  roles:
    - role: ansible-role-brew
```

Testing
-------

This setup ensures your role supports Debian, Ubuntu, and Arch Linux, and it can be tested locally using Molecule. Let me know if you encounter any issues!

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
