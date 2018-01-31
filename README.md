# Ansible Role: Create a Subdomain using PLESK API
Creates and configures a new subdomain in [Plesk](https://docs.plesk.com/en-US/onyx/customer-guide/websites-and-domains/domains-and-dns/adding-subdomains.65180/).

## Requirements
No special requirements:
  * a server running plesk
  * this role requires admin access for plesk
  
## Role Variables
Required variables are listed below and can be set with values (see `vars/main.yml`):
```yaml
host_url: <your-strato-server-id>.stratoserver.net
host_port: 8443

domain_name: "mydomain.com"
subdomain_name: "my-new-instance"

plesk_admin_user: "admin"
plesk_admin_pw: "secure-admin-pw"
```
This example will create my-new-instance.mydomain.com.

Available variables are listed below, along with default values (see `defaults/main.yml`):
```yaml
enable_asp: "false"
enable_ssi: "false"
enable_php: "true"
php_handler_id: "plesk-php56-fastcgi"
enable_fastcgi: "false"
enable_ssl: "false"
```

## Dependencies
None.

## Example Playbook
```yaml
- hosts: strato-server
  become: yes
  vars_files:
    - vars/main.yml
  roles:
    - { role: ansible.role.create-subdomain-using-plesk-api }
```
Inside `vars/main.yml`:
```yaml
host_url: <your-strato-server-id>.stratoserver.net
host_port: 8443

domain_name: "mydomain.com"
subdomain_name: "my-new-instance"

plesk_admin_user: "admin"
plesk_admin_pw: "secure-admin-pw"
```

## Authors
This role was created in 2018 by Sergej Kukshausen and Susann Sgorzaly.

