# ansible-aws

## Variables
Variables are defined in `roles/ec2/vars/main.yml` - make sure to set them before running.

```yml
count: 1
key_name: ansible
instance_type: t2.nano
image: ami-60b6c60a
vpc_subnet_id:
group: ['default']
region: us-east-1
assign_public_ip: yes
```

### Note: AWS credentials
AWS credentials have been intentionally excluded from the variables. You should define these in you local Boto config at `~/.boto`.

```
[Credentials]
aws_access_key_id: key
aws_secret_access_key: key
```

### SSH key
Your SSH private key should be stored properly, ideally as `~/.ssh/ansible.pem`, which the included ansible.cfg assumes.

## Usage
Run ansible-playbook using the included site.yml

```shell
ansible-playbook site.yml
```

### Dependencies
* Boto
