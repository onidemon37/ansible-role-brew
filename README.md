Role Name: Homebrew Installation
=========

This Ansible role installs Homebrew on Debian, Ubuntu, and Arch Linux systems. It handles the installation of dependencies, checks if Homebrew is already installed, and ensures that Homebrew is available for use.

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
| `brew_packages` | `""`                         | Packages to be installed by brew |
| `homebrew_install_command` Override the default Homebrew installation command if needed.

Dependencies
------------

This role does not have any mandatory dependencies but may rely on the presence of `sudo` on certain systems like `Arch Linux`. If sudo is not installed, the role will automatically install it.

Dependencies required for Homebrew (like `build-essential`, `curl`, and `git`) will be installed if not present.

Platform Specifics
------------------

*Debian/Ubuntu* : For Ubuntu and Debian-based systems, the installation path for Homebrew is `/home/linuxbrew/.linuxbrew`.

The role checks if Homebrew is installed using the which brew command. If it's not found, the role will download and install Homebrew using the official installation script.

*Arch Linux* : The role ensures sudo is installed on Arch Linux as it is required for some installation steps.

Homebrew installation is handled similarly to Debian/Ubuntu using the official script. On Arch Linux, the path to Homebrew is also `/home/linuxbrew/.linuxbrew`.

Example Playbook
----------------

To use this role, include it in your playbook with the desired hosts and configuration.

```yaml
- hosts: all
  roles:
    - role: ansible-role-brew
```

Testing with Molecule
---------------------

This role is tested using Molecule to ensure compatibility with the supported platforms (Debian, Ubuntu, Arch Linux). Molecule will spin up Docker containers for each platform, execute the role, and validate the results.

To test this role locally with Molecule:

- Clone the repository and navigate to the role directory.
- Run molecule test to start testing across the platforms.

``` shell
molecule test
```

This setup ensures your role supports Debian, Ubuntu, and Arch Linux, and it can be tested locally using Molecule. Let me know if you encounter any issues!

License
-------

BSD

Author Information
------------------

Author: [Edino Tavares Moniz]
Email: [edinomoniz@gmail.com]
GitHub: [https://github.com/onidemon37/onidemon37/tree/main]
