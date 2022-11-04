# pabalca-ansible

Deploy webapps to https://pabalca.com

| Webapp    | Url                           | Github                                      |
|-----------|-------------------------------|---------------------------------------------|
| Dashboard | https://pabalca.com           | https://github.com/pabalca/dashboard        |
| Artwork   | https://art.pabalca.com       | https://github.com/pabalca/artwork          |
| Chat      | https://chat.pabalca.com      | https://github.com/pabalca/chat             |
| Passwords | https://password.pabalca.com  | https://github.com/pabalca/password_manager |
| Invoices  | https://invoice.pabalca.com   | https://github.com/pabalca/invoices         |

## webapp role
In order to deploy a new webapp, just create a simple role that is based from the <webapp> role.

Example: roles/chat/meta/main.yml
```
dependencies:
  - role: webapp
    vars:
      script_name: chat
      script_dns: chat.pabalca.com
      script_url: git@github.com:pabalca/chat.git
```

## Run it
```
ansible-playbook -i inventory/ site.yml -t webapps -kK
```
