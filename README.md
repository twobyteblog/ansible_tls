## Ansible Role: Baseline Settings for Debian Hosts

This Ansible role configures TLS (sChannel) settings on a Windows-based host using the [IISCrypto](https://www.nartac.com/Products/IISCrypto) Utility.

## Actions Performed

The role performs the following actions:

1. Downloads requisite files.
2. Runs IISCrypto, configuring TLS settings.
3. Deletes downloaded files.
4. Enables TLS 1.2 for .NET.

## Setup Instructions

### Clone Repository

Clone the project into the roles directory of your Ansible Controller.

```bash
git clone https://github.com/twobyteblog/ansible_baseline.git
```

### Generate Template

1. Download IISCryptoGUI onto a host.
2. Configure TLS settings as required.
3. Save template, and copy it into the ```files/IISCrypto``` directory.

### Playbook

Create a playbook which runs this role.

```
- hosts: all
  roles:
    - role: ansible_tls
```