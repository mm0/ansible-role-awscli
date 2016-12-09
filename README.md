Ansible Role: AWS CLI
=====================

[![Build Status](https://travis-ci.org/mm0/ansible-role-awscli.svg?branch=master)](https://travis-ci.org/mm0/ansible-role-awscli)


An Ansible role that installs latest awscli on Mac and Ubuntu and configures boto credentials file


Requirements
---------------

- Sudo access


Role Variables
---------------

Available variables are listed below, there are no defaults:

```yml
  aws_access_key_id: 
  aws_secret_access_key:
  region:
  dest: /path/to/credentials
  owner: 
  group: 
  mode: 
  credential_setup: false
```

Fills in AWS credentials file (usually located at ~/.aws/credentials) when credential_setup is set to true.

Dependencies
---------------

None 

Example Playbook
---------------

    - hosts: webservers
      vars:
				users:
					ubuntu:
						state: present
						groups:  sudo,ubuntu
						sudo: "ALL=(ALL) NOPASSWD: ALL"
      roles:
			- { role: awscli,
					aws_access_key_id: "id"
					aws_secret_access_key: "key",
					region: "us-west-1",
					dest: "/home/myuser/.boto",
					owner: "myuser",
					group: "myuser",
					mode: "0600",
					credential_setup: true
				}

License
---------------

BSD-2

Author Information
------------------

[Matt Margolin](mailto:matt.margolin@gmail.com)

[mm0](https://github.com/mm0) on github
