# Ansible Role: wiredobjects.ntp

Ansible role for managing ntp daemon

## Requirements

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

## Role Variables

The listed ariables are defined as defaults (see `defaults/main.yml`) or fixed variables (see `vars/main.yml`)
with the predefined values.
### Variables for tasks/package

    ntp_package_name: "ntp"

The package name to install.

    ntp_package_state: "present"

The package install state. Defaults to present for idempotency, so no upgrades by default.

### Variables for tasks/config

    ntp_config_dir: "{{ path_sysconfdir }}/ntp"

The service configuration directory. Defaults to /etc/ntp on most Linux systems.

    ntp_config_file: "{{ ntp_config_dir  }}/ntp.conf"

The service main configuration file.

    ntp_config_validate: "no"

Do configuration validation after config file changes.
You need to customize the validation cmd `tasks/config.yml`

### Variables for tasks/firewall

    ntp_firewall_enabled: "yes"

Add firewall rules for the service.

### Variables for tasks/service and handlers/main

    ntp_service_name: "ntp"

The service name used for enable/disable/start/stop.

    ntp_service_enabled: "yes"

The service activation state (enable/disable).

    ntp_service_state: "started"

The service run state (started/stopped).

## Dependencies

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: wiredobjects.ntp
           x: 42

## License

Apache Software License 2.0

## Author Information

For authors/contributors please check AUTHORS.md.

## References

This ansible role was generated using [Cookiecutter](https://cookiecutter.readthedocs.io/en/latest/)
and the [wiredobjects Cookiecutter Ansible role template](https://github.com/wiredobjects/cookiecutter-ansible-role), a customized version of ansible-galaxy standard template.

* [Cookiecutter](https://cookiecutter.readthedocs.io/en/latest/)
* [wiredobjects/cookiecutter-ansible-role](https://github.com/wiredobjects/cookiecutter-ansible-role)
* [Ansible Documentation](https://docs.ansible.com/)
* [Ansible Documentation - Best Practices](https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html)
