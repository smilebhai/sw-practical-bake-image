![Packer - Ansible - AWS AMI](aws_ansible_pacer.png)

# Packer / Ansible / AWS AMI

Utilize Packer and Ansible to automate the creation of Centos 7 AWS AMI images (base, hardening, Jenkins, Kubespray).

---

## Packer

```sh
Validate the syntax and configuration of a template
$ packer validate my-packer-template.json

Takes a template and runs all the builds within it in order to generate a set of artifacts.
$ packer build template.json
```

## Ansible

```sh
Dry run & debug
$ ansible-playbook my-ansible-playbook.yml --check

Run the playbook
$ ansible-playbook my-ansible-playbook.yml
```

## Resources

* [Packer Commands (CLI)](https://www.packer.io/docs/commands/index.html)
* [Ansible Playbook](https://docs.ansible.com/ansible/latest/cli/ansible-playbook.html)
* [AMI Builder (EBS backed)](https://www.packer.io/docs/builders/amazon-ebs.html)
* [DevSec Hardening Framework: Security + DevOps](https://dev-sec.io/)
