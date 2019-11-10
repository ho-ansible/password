# Ansible role: user
+ **Generate** random password for regular user
+ Store password in **hostvars**
+ Create **regular** user and set password
+ **Disable** password login to `root`
+ Add **ssh** pubkeys for login to regular user

## Requirements
Only tested on Debian stable, for now.

## Role Variables
+ `user_name` (default: `{{ ansible_user }}`): username of regular user
+ `user_pw` (auto-generated): stores plaintext password
+ `pw_dir` (default: `{{ inventory_dir }}/host_vars`):
  plaintext passwords will be stored in subdirectories under this path,
  `{{ inventory_hostname }}/pw.yml`, in a key named `user_pw`

## Dependencies
None

## Example Playbook

```
- hosts: all
  roles:
    - { role: ho-ansible.user }
```

## License
MIT

## Author Information
Sean Ho, https://github.com/ho-ansible/
