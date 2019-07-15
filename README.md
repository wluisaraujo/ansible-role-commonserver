[![Ansible Galaxy](https://img.shields.io/badge/Ansible%20Galaxy-Common%20Server-blue.svg)](https://galaxy.ansible.com/wluisaraujo/commonserver) [![Build Status](https://travis-ci.org/wluisaraujo/ansible-role-commonserver.svg?branch=master)](https://travis-ci.org/wluisaraujo/ansible-role-commonserver)

------------

Description
------------

* Ajusta configurações de sistemas Linux, seguindo boas práticas ;)

Tasks | Description
--- | ---
[config2base-CentOS.yml](../tasks/config2base-CentOS.yml) | Configuracao para CentOS
[config2base-Debian.yml](../tasks/config2base-Debian.yml) | Configuracao para Debian
[config2base-Ubuntu.yml](../tasks/config2base-Ubuntu.yml) | Configuracao para Ubuntu
[config2clamav.yml](../tasks/config2clamav.yml) | Configuracao Clamav AntiVirus
[config2environment.yml](../tasks/config2environment.yml) | Configuracao de variaveis Linux
[config2epel.yml](../tasks/config2epel.yml) | Configuracao do repositorio EPEL
[config2files.yml](../tasks/config2files.yml) | Configuracao de arquivos
[config2guestagent.yml](../tasks/config2guestagent.yml) | Configuracao de Guest Agent (2VM)
[config2pamrules.yml](../tasks/config2pamrules.yml) | Configuracaos de PAM
[config2rsyslog.yml](../tasks/config2rsyslog.yml) | Configuracao Log
[config2snmp.yml](../tasks/config2snmp.yml) | Configuracao protocolo SNMP
[config2sudo.yml](../tasks/config2sudo.yml) | Configuracoes de SUDO
[config2time.yml](../tasks/config2time.yml) | Configuracoes sincronismo de Data e Hora
[config2users.yml](../tasks/config2users.yml) | Configuracoes de Usuarios locais
[package-base-CentOS.yml](../tasks/package-base-CentOS.yml) | Instalação de pacotes para CentOS
[package-base-Debian.yml](../tasks/package-base-Debian.yml) | Instalação de pacotes para Debian
[package-base-RedHat.yml](../tasks/package-base-RedHat.yml) | Instalação de pacotes para RedHat
[package-base-Ubuntu.yml](../tasks/package-base-Ubuntu.yml) | Instalação de pacotes para Ubuntu
[unconfig2users.yml](../tasks/unconfig2users.yml) | Remoção de Usuários 

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

Installation
------------

```console
vagrant@localhost:~$ ansible-galaxy install wluisaraujo.commonserver
```

Dependencies
------------

*

Example Playbook
----------------

```yaml
---
- hosts: servers
  roles:
    - { role: commonserver, MEUDOMINIO: EXEMPLO.NET }
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
