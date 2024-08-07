# Ansible-Role: acr-ansible-ca-certs

AIT-CyberRange: Certificate Authority management


## Requirements

- Debian or Ubuntu 

## Role Variables

```yaml
ca_certs: []
ca_certs_strings: |
  {% for ca_cert in ca_certs %}
  {{ lookup('file', ca_cert) }}
  {% endfor %}

```

## Example Playbook

```yaml
- hosts: localhost
  roles:
    - acr-ansible-ca-certs
      vars:
        ca_certs:
          - /path/to/cert.crt
```

## License

GPL-3.0

## Author

- Lenhard Reuter