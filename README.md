[![Build Status](https://travis-ci.org/wluisaraujo/iac-ansible-common-server.svg?branch=master)](https://travis-ci.org/wluisaraujo/iac-ansible-common-server)

[![Ansible Galaxy](https://img.shields.io/badge/Ansible%20Galaxy-Common%20Server-blue.svg)](https://galaxy.ansible.com/wluisaraujo/iac-ansible-common-server)

------------

Description
------------

* Ajusta configurações de sistemas Linux, seguindo boas práticas ;)
  - [config2base-CentOS.yml](../tasks/config2base-CentOS.yml)
  - config2base-Debian.yml
  - config2base-Ubuntu.yml
  - config2clamav.yml
  - config2environment.yml
  - config2epel.yml
  - config2files.yml
  - config2guestagent.yml
  - config2pamrules.yml
  - config2rsyslog.yml
  - config2snmp.yml
  - config2sudo.yml
  - config2time.yml
  - config2users.yml
  - package-base-CentOS.yml
  - package-base-Debian.yml
  - package-base-RedHat.yml
  - package-base-Ubuntu.yml
  - unconfig2users.yml

Variaveis
------------

[defaults/main.yml](defaults/main.yml)

```yaml
   vars:
     - MEUDOMINIO: define o dominio do ambiente
     - PROXYSERVER: define o servidor de proxy
     - PROXYPORT: define a porta do proxy
```     
     

Requirements
------------

*

Dependencies
------------

*

Example Playbook
----------------

```yaml
---
- hosts: servers
  roles:
    - { role: iac-ansible-common-server, MEUDOMINIO: EXEMPLO.NET }
...    
```

Dev Features
----------------

Option | Quem sabe um dia
--- | ---
`tuned` | Configurar tuned
`httpd` | Alterar o arquivo httpd.conf para conter: ServerTokens Prod
`httpd` | Alterar o arquivo httpd.conf para conter: ServerSignature Off
`sshd` | Alterar o arquivo sshd_config para conter: PermitRootLogin no
`postfix` | Alterar o arquivo main.cf para conter: disable_vrfy_command = yes
`pam` | Alterar o arquivo /etc/login.defs para conter: PASS_MAX_DAYS 30
`pam` | Alterar o arquivo /etc/login.defs para conter: PASS_WARN_AGE 3
`pam` | Alterar o arquivo /etc/login.defs para conter: PASS_MIN_LEN 8
`pam` | Alterar o arquivo /etc/pam.d/su para conter: "auth       required     /lib/security/pam_wheel.so group=wheel use_uid"
`init` | Alterar o arquivo /etc/inittab para não conter a linha: ca:12345:ctrlaltdel:/sbin/shutdown -t1 -a -r now; Em versões mais recentes, Alterar o arquivo /etc/init/control-alt-delete.conf para não conter a linha: start on control-alt-delete

----------------
[![Licence](https://img.shields.io/badge/License-GPL%20v3-red.svg)](https://www.gnu.org/licenses/gpl-3.0.pt-br.html)
