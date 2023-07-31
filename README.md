# temple

deployment code

# Terraform

## Infrastructure

* AWS EC2 instances x2 running nginx in separate target groups attached to an Application Load Balancer. EC2 instances are deployed initially in separate AZs in the same region.

* A droplet on Digital Ocean running nginx.

# Interface

* Describe currecnt infrastructure

```
cd terraform
tf show
```

# Ansible

## Inventory

* `ansible/inventory/aws_ec2.yml.sample` is a sample dynamic AWS inventory module for Ansible. Installation instructions: https://devopscube.com/setup-ansible-aws-dynamic-inventory/

## Playbooks

* letsencrypt: Check SSL certificate validity

```
ansible-playbook letsencrypt.yml -i inventory --tags test --ask-become-pass
```

* letsencrypt: Renew SSL certificate

```
ansible-playbook letsencrypt.yml -i inventory --tags enroll --ask-become-pass
```

* deploy-web: Deploy website

```
ansible-playbook deploy-web.yml -i inventory --tags all
```

* deploy-web: Restart nginx

```
ansible-playbook deploy-web.yml -i inventory --tags restartweb
```
