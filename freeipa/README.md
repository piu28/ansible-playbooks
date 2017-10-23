# Ansible Playbooks for FreeIPA Servers/Clients

This playbook configures FreeIPA Server and Client. 

## FreeIPA Server

Variables:

main.yml in defaults directory is used to specify the variables. We are specifying the following variables in the yml file:

```
freeipa_server_version: 4.3.1
freeipa_server_dns_version: 4.3.1
server_alias: ipa
server_hostname: ipa.powerupcloud.com
domain: powerupcloud.com
realm: POWERUPCLOUD.COM
principal_user: admin
principal_user_password: puc123
directory_manager_password: puc123
```
Update the variables as required before executing the playbook.

Execute the playbook using the below command:

```
ansible-playbook freeipa-server/ipa-server.yml --extra-vars 'host=localhost'
```

## FreeIPA Client

Variables:

The variables are defined in the defaults directory:

```
freeipa_client_version: 4.3.1
server_alias: ipa
server_hostname: ipa.powerupcloud.com
domain: powerupcloud.com
realm: POWERUPCLOUD.COM
principal_user: admin
principal_user_password: puc123
directory_manager_password: puc123
```
Give the proper values as given while configuring the IPA Server.

Execute the playbook using the command:

```
ansible-playbook ipa-client/ipa-client.yml --extra-vars 'host=<ansiblehost> client_hostname=<clienthostname>'
```
