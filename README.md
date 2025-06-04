CA
=========

This role installs and sets up components for Certificate Authority server. It uses the easy-rsa app to generate necessary files for OpenVPN server creation.

Requirements
------------

- python3 passlib (Install: `pip install passlib`)

Role Variables
--------------

### Main Configuration Variables

| Variable           | Required | Default               | Description                                                  |
|--------------------|----------|-----------------------|--------------------------------------------------------------|
| `rsa_country`      | yes      | `"RU"`                | Country name for certificates (2-letter code)                |
| `rsa_province`     | yes      | `"Moscow"`            | State/province name                                          |
| `rsa_city`         | yes      | `"Moscow City"`       | City name                                                    |
| `rsa_org`          | yes      | `"Example Inc"`       | Organization name                                            |
| `rsa_email`        | yes      | `"admin@example.com"` | Admin email                                                  |
| `rsa_ou`           | no       | `"IT"`                | Organizational Unit                                          |

### System Configuration

| Variable           | Required | Default               | Description                                                  |
|--------------------|----------|-----------------------|--------------------------------------------------------------|
| `ca_group`         | no       | `"ca-ops"`            | System group for CA operations                               |
| `ca_username`      | no       | `"ca-admin"`          | System user for CA operations                                |
| `ca_user_password` | yes      | -                     | Password for CA system user (should be encrypted with vault) |
| `ca_name`          | yes      | `"example"`           | Name for CA                                                  |
| `ca_dir`           | no       | `"/etc/CA"`           | Base directory for CA files                                  |

### Security settings

| Variable           | Required | Default               | Description                                                  |
|--------------------|----------|-----------------------|--------------------------------------------------------------|
| `ca_password`      | yes      | -                     | Password for CA private key encryption (use vault!)          |


Dependencies
------------

No dependencies required.

Example Playbook
----------------

## Installation 

Playbook example:

    - hosts: servers
      roles:
         - CA

## Uninstallation  

To remove the CA role, run:  
```bash  
ansible-playbook -i inventory uninstall.yml 
```

License
-------

BSD

Author Information
------------------

GitHub: https://github.com/Name1essGuy
Ansible-Galaxy: https://galaxy.ansible.com/ui/standalone/namespaces/22123/
