# Ansible role: password
+ Prevent root from having any password login
+ Generate and store a random password for regular user

## Requirements
Only tested on Debian stable, for now.

## Role Variables
+ `sudo_user` (default: `{{ ansible_user }}`): username of regular user
+ `pw_store` (default: `{{ inventory_dir }}/host_vars`):
  plaintext passwords will be stored in subdirectories under this path,
  `{{ inventory_hostname }}/pw.yml`, in a key named `sudo_pw`

## Dependencies
+ role: ho-ansible.sudo

## Example Playbook

```
- hosts: all
  roles:
    - { role: ho-ansible.password }
```

## License
MIT

## Author Information
Sean Ho, https://github.com/ho-ansible/
