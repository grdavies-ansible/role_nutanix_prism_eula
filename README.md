# Nutanix Role to configure Pulse on either Prism Element or Prism Central

This Ansible role accept/reject the Prism EULA after the initial deployment of either a Nutanix cluster or Prism Central.

## Input Variables

| Variable                                          | Required | Default | Choices                   | Comments                                                                                               |
|---------------------------------------------------|----------|---------|---------------------------|--------------------------------------------------------------------------------------------------------|
| role_nutanix_prism_eula_host                      | yes      |         |                           | The IP address or FQDN for the Prism (Element or Central) where you want to accept the EULA.           |
| role_nutanix_prism_eula_host_username             | no       | "admin" |                           | A valid username with appropriate rights to access the Nutanix API where you want to accept the EULA.  |
| role_nutanix_prism_eula_host_password             | yes      |         |                           | A valid password for the supplied username where you want to accept the EULA.                          |
| role_nutanix_prism_eula_host_port                 | no       | 9440    |                           | The Prism TCP port where you want to accept the EULA.                                                  |
| role_nutanix_prism_eula_host_validate_certs       | no       | false   | true / false              | Whether to check if Prism UI certificates are valid.                                                   |
| role_nutanix_prism_eula_debug                     | no       | false   | true / false              | Whether to output variable contents for debugging purposes.                                            |
| role_nutanix_prism_eula_accept                    | no       | false   | true / false              | If ELUA is set to True the full_name, company and role variables are mandatory.                        |
| role_nutanix_prism_eula_full_name                 | no       |         |                           |                                                                                                        |
| role_nutanix_prism_eula_company_name              | no       |         |                           |                                                                                                        |
| role_nutanix_prism_eula_job_title                 | no       |         |                           |                                                                                                        |

## Dependencies

- grdavies.role_nutanix_prism_api

## Example Playbook

```
- hosts: localhost
  gather_facts: false
  roles:
  - role: grdavies.role_nutanix_prism_eula
  vars:
    role_nutanix_prism_eula_host: 10.38.185.37
    role_nutanix_prism_eula_host_username: admin
    role_nutanix_prism_eula_host_password: nx2Tech165!
    role_nutanix_prism_eula_accept: True
    role_nutanix_prism_eula_full_name: Ross Davies
    role_nutanix_prism_eula_company_name: Nutanix
    role_nutanix_prism_eula_job_title: SE
```


## License

See LICENSE.md

## Author Information

Ross Davies
