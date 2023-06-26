# Ansible config for my MacOS environment setup

This repository contains the ansible configuration required to provision my development setup in a MacOS-powered computer.

## Usage

1. In a fresh MacOS environment, run `xcode-select --install` to install the developer tools. We'll need this to have git installed.
2. MacOS comes with Python by default. Using Python 3, [install ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#pipx-install).
3. Clone this repository to the target environment and navigate to the cloned folder.
4. Run: `ansible-playbook --ask-vault-pass main.yml -e "laptop_type=<replace_this>"`. The laptop_type defines different roles to be executed.

## Vaulted files
Some confidential files (e.g. SSH keys) are encrypted with Ansible Vault AES256 encryption. Ansible will decrypt the files during the playbook execution, hence you need to provide the vault passphrase.

## Troubleshooting

### Ansible commands not found

When you install ansible with Python pip it won't put the binaries in the path. You'll need to check which Python verison you're running and then do:
```bash
export PATH="/Users/<your-user>/Library/Python/3.xx/bin:$PATH"
```

