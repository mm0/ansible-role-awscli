# README.md

# Ansible Role: Bash v1.0

An Ansible role that installs latest awscli on Mac and Ubuntu and configures boto credentials file


![travis-ci](https://travis-ci.org/mm0/ansible-role-awscli.svg?branch=master)

## Requirements

Sudo access

## Role Variables

Available variables are listed below, there are no defaults:

      aws_access_key_id: 
      aws_secret_access_key:
      region:
      dest: /path/to/credentials
      owner: 
      group: 
      mode: 
    credential_setup: false

Fill in the aws fields and credentials file location (usually ~/.aws/credentials) and set credential_setup to true if you'd like to add a key

## Dependencies

None 

## Example Playbook

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

## License

MIT

Author Information
------------------

[Matt Margolin](mailto:matt.margolin@gmail.com)

mm0 on github
