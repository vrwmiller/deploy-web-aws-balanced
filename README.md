# temple

# Terraform

## Infrastructure

Two EC2 instances running nginx in separate target groups attached to an application load balancer. EC2 instances are deployed in separate AZs in the same region.

# Ansible

## Inventory

* `ansible/inventory/aws_ec2.yml.sample` is a sample dynamic AWS inventory module for Ansible. Installation instructions: https://devopscube.com/setup-ansible-aws-dynamic-inventory/

## Playbooks

* Check hostileadmin SSL certificate validity

```
ansible-playbook letsencrypt.yml -i inventory --tags test --ask-become-pass
```

* Renew hostileadmin SSL certificate

```
ansible-playbook letsencrypt.yml -i inventory --tags enroll --ask-become-pass
```
