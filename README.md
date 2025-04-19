## Ansible Role: Baseline Settings for Debian Hosts

This Ansible role configures TLS (sChannel) settings on a Windows-based host using the [IIS Crypto CLI](https://www.nartac.com/Products/IISCrypto) utility.

## Actions Performed

The role performs the following actions:

1. Downloads requisite files.
2. Runs IIS Crypto CLI, configuring TLS settings.
3. Deletes IIS Crypto CLI and associated templates.
4. Enables TLS 1.2 for .NET.

## Setup Instructions

### Clone Repository

Clone the project into the roles directory of your Ansible Controller.

```bash
git clone https://github.com/twobyteblog/ansible_tls.git
```

### Generate Template

1. Download [IIS Crypto GUI](https://www.nartac.com/Products/IISCrypto/Download) onto a Windows host.
2. Configure TLS settings as required.
3. Create a template of your configuration, and copy it into ```files/IISCrypto```.

### Playbook

Create a playbook which runs this role.

```
- hosts: all
  roles:
    - role: ansible_tls
```