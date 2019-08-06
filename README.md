# Ansible Role: Jumpserver

An Ansible Role that installs [Jumpserver](http://www.jumpserver.org/) on Linux.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
mariadb_root_password: ''
jumpserver_db_name: jumpserver
jumpserver_db_user: jumpserver
jumpserver_db_password: jumpserver

secret_key: 'zmJi58sPzJPVYNBi9ojZqsETVskYguAHRcKYvuIQYJJdvPBggL'
bootstrap_token: 'wCZotF5vTKsTT1rC'

docker_registry_mirror: https://registry.docker-cn.com
jms_koko_image: jumpserver/jms_koko:1.5.2
jms_guacamole_image: jumpserver/jms_guacamole:1.5.2

luna_version: 1.5.2
```

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  vars:
    mariadb_root_password: "Q1w2e3r4"
    jumpserver_db_password: "jumpserver"
    secret_key: "uQguZIl3tmBVsyUA2uRnV7VsIlECvsss0pIUY4COxoH2nEsSwR"
    bootstrap_token: "an2wB0TEqMgB8EMn"
  roles:
    - jumpserver
```

## License

MIT / BSD

## 生成随机SECRET_KEY

```
$ cat /dev/urandom | tr -dc A-Za-z0-9 | head -c 50
```

MacOS:
```
$ cat /dev/urandom | LC_CTYPE=C tr -dc A-Za-z0-9 | head -c 50
```

## 生成随机BOOTSTRAP_TOKEN

```
$ cat /dev/urandom | tr -dc A-Za-z0-9 | head -c 16
```

MacOS:
```
$ cat /dev/urandom | LC_CTYPE=C tr -dc A-Za-z0-9 | head -c 16
```

## Jumpserver访问方式

请打开浏览器访问公网80端口，用户名: admin 密码: admin