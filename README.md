# temple

# Ansible Inventory

* `ansible/inventory/aws_ec2.yml.sample` is a smaple dynamic inventory module for Ansible. Installation instrucitons: https://devopscube.com/setup-ansible-aws-dynamic-inventory/

# Playbooks

* Check hostileadmin SSL certificate validity

```
ansible-playbook letsencrypt.yml -i inventory --tags test --ask-become-pass
```

* Renew hostileadmin SSL certificate

```
ansible-playbook letsencrypt.yml -i inventory --tags enroll --ask-become-pass
```
