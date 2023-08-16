# Nutanix Role to configure Pulse on either Prism Element or Prism Central

This Ansible role accept/reject the Prism EULA after the initial deployment of either a Nutanix cluster or Prism Central.


## Role Variables

| Variable                                          | Required | Default | Choices                   | Comments                                                                                               |
|---------------------------------------------------|----------|---------|---------------------------|--------------------------------------------------------------------------------------------------------|
| nutanix_prism_eula_host                           | yes      |         |                           | The IP address or FQDN for the Prism (Element or Central) where you want to accept the EULA.           |
| nutanix_prism_eula_username                       | no       | "admin" |                           | A valid username with appropriate rights to access the Nutanix API where you want to accept the EULA.  |
| nutanix_prism_eula_password                       | yes      |         |                           | A valid password for the supplied username where you want to accept the EULA.                          |
| nutanix_prism_eula_port                           | no       | 9440    |                           | The Prism TCP port where you want to accept the EULA.                                                  |
| validate_certs                                    | no       | no      | yes / no                  | Whether to check if Prism UI certificates are valid.                                                   |
| nutanix_debug                                     | no       | False   | True / False              | Whether to output variable contents for debugging purposes.                                            |
| nutanix_prism_eula_accept                         | no       | False   | True / False              | If ELUA is set to True the full_name, company and role variables are mandatory.                        |
| nutanix_prism_eula_full_name                      | no       |         |                           |                                                                                                        |
| nutanix_prism_eula_company_name                   | no       |         |                           |                                                                                                        |
| nutanix_prism_eula_job_title                      | no       |         |                           |                                                                                                        |


## Dependencies

None


## Example Playbook

```
- hosts: localhost
  gather_facts: false
  roles:
  - role: grdavies.role_nutanix_prism_eula
  vars:
    nutanix_prism_eula_host: 10.38.185.37
    nutanix_prism_eula_username: admin
    nutanix_prism_eula_password: nx2Tech165!
    nutanix_prism_eula_eula_accept: True
    nutanix_prism_eula_full_name: Ross Davies
    nutanix_prism_eula_company_name: Nutanix
    nutanix_prism_eula_job_title: SE
```


## License

See LICENSE.md

## Author Information

Ross Davies
