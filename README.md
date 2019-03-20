![Packer - Ansible - AWS AMI](aws_ansible_pacer.png)

# Packer / Ansible / AWS AMI

Utilize Packer and Ansible to automate the creation of Centos 7 AWS AMI images (base, hardening, Jenkins, Kubespray).

---

## Packer

Generate new keypair for AWS if one does not already exists

    $ ssh-keygen -t rsa -C "packer_base_id_rsa" -f ./../ssh-keys/packer_base_id_rsa

Import into AWS using this command or manually import from AWS EC2 console

    $ aws ec2 import-key-pair --key-name "packer_base_id_rsa" --region us-east-1 --public-key-material "$(cat ./../ssh-keys/packer_base_id_rsa.pub)"

`NOTE`: Make sure to change the aws profile as well as `--region` and `--key-name` accordingly.

Validate the syntax and configuration of a template

  $ packer validate my-packer-template.json

Takes a template and runs all the builds within it in order to generate a set of artifacts.

  $ packer build template.json

## Ansible

Dry run and debug

  $ ansible-playbook my-ansible-playbook.yml --check

Run the playbook

  $ ansible-playbook my-ansible-playbook.yml

## Resources

* [Packer Commands (CLI)](https://www.packer.io/docs/commands/index.html)
* [Ansible Playbook](https://docs.ansible.com/ansible/latest/cli/ansible-playbook.html)
* [AMI Builder (EBS backed)](https://www.packer.io/docs/builders/amazon-ebs.html)
* [DevSec Hardening Framework: Security + DevOps](https://dev-sec.io/)
