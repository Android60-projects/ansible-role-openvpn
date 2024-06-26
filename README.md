# OpenVPN Server Ansible

[![Molecule test](https://github.com/Android60-projects/ansible-role-openvpn/actions/workflows/molecule.yml/badge.svg?branch=main)](https://github.com/Android60-projects/ansible-role-openvpn/actions/workflows/molecule.yml)

This directory contains playbooks used for installing and configuring OpenVPN server. OpenVPN-UI install is optional.

## Tags:
```
- ovpn-genkeys
- ovpn-config
- ovpn-ui-config
- nginx-config
```

## General options
```
openvpn_port: "1194"
openvpn_proto: "udp"
openvpn_easyrsa_path: "/opt/EasyRSA"
openvpn_configuration_directory: "/etc/openvpn/"
easyrsa_version: "3.0.9"
ovpn_admin_path: "/opt/ovpn-admin"
nginx_global_auth_username: "your-username"
nginx_global_auth_password: "your-password"
firewalld_default_interface_zone: "public"
ovpn_ui_install: true
nginx_whitelist:
    - 10.8.0.0/24
```
