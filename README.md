# VPN Server role
Installing and configuring PGBouncer Exporter.

## Variables
The role supports the following variables:
| Variable name                   | Default value                     | Mandatory | Description                                               |
|---------------------------------|-----------------------------------|-----------|-----------------------------------------------------------|
| email                           | your_email@example.com            | yes       | Email address to create SSL cert                          |
| vpn_port                        | 2053                              | yes       | Your VPN port                                             |
| domain_name                     | example.com                       | yes       | Your server's domain name                                 |  
| users:                          | - name: rostom                    | no        | Users to create on the server and their ssh public key    |
|  - name: rostom                 |   ssh_key: "ssh-rsa AA ..."       |           |                                                           |
|    ssh_key: "ssh-rsa AA ..."    |                                   |           |                                                           |
|  - name: rostom                 |                                   |           |                                                           |
|    ssh_key: "ssh-rsa AA ..."    |                                   |           |                                                           |

Full list of supported variables see in the [defaults](defaults/main.yml) role variable.

## Example Playbook
```yaml
---

- name: Обновление системы, установка и настройка Nginx, создание пользователей
  hosts: webservers
  become: yes
  vars:
    vpn_port: 2053
    domain_name: example.com
    email: admin@example.com
    users:
      - name: user1
        ssh_key: "ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEA... user1@example.com"
      - name: user2
        ssh_key: "ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQE... user2@example.com"

```
