# ansible-role-cloudflared_proxydns
Ansible Role to install the cloudflared binary

## How to install
### requirements.yml
**Put the file in your roles directory**
```yaml
---
- src: https://gitlab.com/mohsenmirzaei91/ansible-role-cloudflared_proxydns.git
  scm: git
  version: main
  name: ansible-role-ansible-role-cloudflared_proxydns
```
### Download the role
```Shell
ansible-galaxy install -f -r ./roles/requirements.yml --roles-path=./roles
```

## Requirements

- Ansible >= 2.10 **(No tests has been realized before this version)**

## Role Variables

All variables which can be overridden are stored in [default/main.yml](default/main.yml) file as well as in table below.

| Name           | Default Value | Choices | Description                        |
| -------------- | ------------- | ------- | -----------------------------------|
| `cloudflared_version` | "2022.9.1" | [version](https://github.com//cloudflare/cloudflared/tags) | Choice of the cloudflared version. |
| `cloudflared_opts` | [] |  | The options that are passed at the start of cloudflared. |

## Example Playbook

```yaml
---
- hosts: all
  tasks:
    - name: Include ansible-role-cloudflared_proxydns
      include_role:
        name: ansible-role-cloudflared_proxydns
      vars:
        cloudflared_version: '2022.10.0'
        cloudflared_opts:
          - --upstream https://1.1.1.2/dns-query
          - --upstream https://1.0.0.2/dns-query
```
## License

