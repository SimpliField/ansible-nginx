Nginx
=========

Ansible role to setup nginx

Requirements
------------

Need ansible 2+

Role Variables
--------------

```yaml
nginx_service_name: "nginx"
nginx_conf_dir: "/etc/nginx"
nginx_log_dir: "/var/log/nginx"
nginx_configs: {}
nginx_sites_disabled: {}
nginx_sites:
  status:
  - listen 127.0.0.1:80
  - server_name status
  - location /nginx_status {
      stub_status on;
      access_log off;
      allow 127.0.0.1;
      deny all;
    }
  default:
  - listen 80 default_server
  - server_name _
  - root "/usr/share/nginx/html"
  - index index.html
keep_only_specified: false
```

Dependencies
------------

There is no dependency

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
   - { role: SimpliField.nginx }
```

License
-------

BSD
