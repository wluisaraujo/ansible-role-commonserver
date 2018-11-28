[![Build Status](https://travis-ci.org/wluisaraujo/iac-ansible-common-server.svg?branch=master)](https://travis-ci.org/wluisaraujo/iac-ansible-common-server)
=========

iac-ansible-common-server
=========

Ajusta configurações de sistemas Linux, seguindo boas práticas ;)

- base-centos.yml

- base-debian.yml

- base-redhat.yml

- clamav.yml

- config2sudo.yml

- epel.yml

- files.yml

- linux-environment.yml 

- pamlimits.yml 

- rsyslog.yml

- snmpd.yml 

- sysctl.yml 

- timezone.yml

Variaveis
------------

- MEUDOMINIO: define o dominio do ambiente  

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

Próximas Features
----------------
- Configurar tuned

- Alterar o arquivo httpd.conf para conter: ServerTokens Prod

- Alterar o arquivo httpd.conf para conter: ServerSignature Off

- Alterar o arquivo sshd_config para conter: PermitRootLogin no

- Alterar o arquivo main.cf para conter: disable_vrfy_command = yes

- Alterar o arquivo /etc/login.defs para conter: PASS_MAX_DAYS 30

- Alterar o arquivo /etc/login.defs para conter: PASS_WARN_AGE 3

- Alterar o arquivo /etc/login.defs para conter: PASS_MIN_LEN 8

- Alterar o arquivo /etc/pam.d/su para conter: "auth       required     /lib/security/pam_wheel.so group=wheel use_uid"

- Alterar o arquivo /etc/inittab para não conter a linha: ca:12345:ctrlaltdel:/sbin/shutdown -t1 -a -r now; Em versões mais recentes, alterar o arquivo /etc/init/control-alt-delete.conf para não conter a linha: start on control-alt-delete


		 
License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
