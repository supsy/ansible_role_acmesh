Acmesh
======

Installation for acmesh


Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

| Name                               | Default Value       | Description                    |
|------------------------------------|---------------------|--------------------------------|
| `acmesh__show_ansible_management`  | `false`              | Enable to show hint in ansible managed files. |
| `acmesh__account_email`            | ''                   | Specify the e-mail address for letsencrypt registration and notifications. |
| `acmesh__http_proxy`               | ''                   | Set http proxy, if needed. |
| `acmesh__package_version`          | `*OS default*`       | Version/Branch for acmesh to install. |
| `acmesh__validation_method`        | standalone           | Specify certificate validation method. (standalone/dns) |
| `acmesh__enable_auto_issue`        | `true`               | Enable to automatically issue new certificate for hostname. |
| `acmesh__issue_certificates`       | `see below`          | List of certificates, if automatically issue `acmesh__enable_auto_issue` is enabled. |
| `acmesh__use_staging`              | `false`              | Enable to use letsencrypt staging API. |
| `acmesh__dns_provider`             | ''                   | Set DNS provider API. See `Supported DNS provider` below. |
| `acmesh__dns_cloudflare_email`     | ''                   | Set e-mail address for Cloudflare DNS API authentication. |
| `acmesh__dns_cloudflare_key`       | ''                   | Set key for Cloudflare DNS API authentication. |

### acmesh__issue_certificates Parameter

| Name                  | Default Value       | Description                    |
|-----------------------|---------------------|--------------------------------|
| `name`                | ''                  | Set common name for certificate. |
| `alternative_names`   | []                  | List of alternative names. |

#### Default
  - name: "{{ ansible_fqdn }}"

### Supported DNS provider

| Value     | Description   |
|-----------|---------------|
| `dns_cf`  | Cloudflare    |


Dependencies
------------

None.


Example Playbook
----------------

    - hosts: acmesh
      vars_files:
        - vars/main.yml
      roles:
        - { role: acmesh }

License
-------

MIT


Author Information
------------------

This role was created by Noles
