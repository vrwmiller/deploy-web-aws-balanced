# temple

hostileadmin deployment code

# Terraform

## Infrastructure

Two AWS EC2 instances running nginx in separate target groups attached to an Application Load Balancer. EC2 instances are deployed initially in separate AZs in the same region.

A droplet on Digital Ocean running nginx.

# Ansible

## Inventory

* `ansible/inventory/aws_ec2.yml.sample` is a sample dynamic AWS inventory module for Ansible. Installation instructions: https://devopscube.com/setup-ansible-aws-dynamic-inventory/

## Playbooks

* Check SSL certificate validity

```
ansible-playbook letsencrypt.yml -i inventory --tags test --ask-become-pass
```

* Renew SSL certificate

```
ansible-playbook letsencrypt.yml -i inventory --tags enroll --ask-become-pass
```
