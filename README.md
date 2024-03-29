Acmesh
======

Installation for acmesh


Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

| Name                                    | Default Value                    | Description                    |
|-----------------------------------------|----------------------------------|--------------------------------|
| `acmesh__show_ansible_management`       | `false`                          | Enable to show hint in ansible managed files. |
| `acmesh__account_email`                 | ''                               | Specify the e-mail address for letsencrypt registration and notifications. |
| `acmesh__http_proxy`                    | ''                               | Set http proxy, if needed. |
| `acmesh__package_version`               | `*OS default*`                   | Version/Branch for acmesh to install. |
| `acmesh__validation_method`             | standalone                       | Specify certificate validation method. (standalone/dns) |
| `acmesh__enable_auto_issue`             | `true`                           | Enable to automatically issue new certificate for hostname. |
| `acmesh__issue_certificates`            | `see below`                      | List of certificates, if automatically issue `acmesh__enable_auto_issue` is enabled. |
| `acmesh__use_staging`                   | `false`                          | Enable to use letsencrypt staging API. |
| `acmesh__default_acme_server`           | ''                               | Set default acme server or do not set to use acme.sh default. For Letsencrypt set: https://acme-v02.api.letsencrypt.org/directory
| `acmesh__dns_provider`                  | ''                               | Set DNS provider API. See `Supported DNS provider` below. |
| `acmesh__dns_cloudflare_email`          | ''                               | Set e-mail address for Cloudflare DNS API authentication. |
| `acmesh__dns_cloudflare_key`            | ''                               | Set key for Cloudflare DNS API authentication. |
| `acmesh__enable_haproxy_deploy_hook`    | `false`                          | Enable to use haproxy deploy hook. |
| `acmesh__haproxy_deploy_hook_pem_path`  | /etc/haproxy/ssl                 | Set default Pem Path for Haproxy. |
| `acmesh__haproxy_deploy_reload_command` | /usr/sbin/service haproxy reload | Set reload command for Haproxy.

### acmesh__issue_certificates Parameter

| Name                  | Default Value       | Description                    |
|-----------------------|---------------------|--------------------------------|
| `name`                | ''                  | Set common name for certificate. |
| `alternative_names`   | []                  | List of alternative names. |
| `server`              | `omit`              | Set ca server for certificate. (optional) |

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
