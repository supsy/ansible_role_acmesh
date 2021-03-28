Acmesh
======

Installation for acmesh


Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

| Name                               | Default Value       | Description                    |
|------------------------------------|---------------------|--------------------------------|
| `acmesh__show_ansible_management` | `false`              | Enable to show hint in ansible managed files. |
| `acmesh__account_email`           | ''                   | Specify the e-mail address for letsencrypt registration and notifications. |
| `acmesh__http_proxy`              | `false`              | Set http proxy, if needed. |
| `acmesh__package_version`         | `*OS default*`       | Version/Branch for acmesh to install. |
| `acmesh__enable_dns_cloudflare`   | `false`              | Enable DNS API for Cloudflare. |
| `acmesh__dns_cloudflare_email`    | `false`              | Set e-mail address for Cloudflare DNS API authentication. |
| `acmesh__dns_cloudflare_key`      | `false`              | Set key for Cloudflare DNS API authentication. |


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

MIT / BSD


Author Information
------------------

This role was created by Noles
