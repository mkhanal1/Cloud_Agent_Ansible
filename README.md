# Cloud_Agent_Ansible
Deploy Qualys Cloud Agent (CA) on Linux instances using Ansible-Playbook.

## License
_**THIS SCRIPT IS PROVIDED TO YOU "AS IS."  TO THE EXTENT PERMITTED BY LAW, QUALYS HEREBY DISCLAIMS ALL WARRANTIES AND LIABILITY FOR THE PROVISION OR USE OF THIS SCRIPT.  IN NO EVENT SHALL THESE SCRIPTS BE DEEMED TO BE CLOUD SERVICES AS PROVIDED BY QUALYS**_

## Description
The playbook InstallQCA.yml can be used to deploy QCA across the assets included in your "host" file. Additionally, you can use the tags to deploy QCA on your instances.

The required input parameters are:

* private-key = private-key to access the instances (Ansible works via SSH)
* ssh_user = username to login into the instance
* URL = the URL where the file is hosted For example: Webserver, S3, Blob Storage, Cloud Storage
* ActivationID = An ID that provides a way to group agents and bind them to your account 
* CustomerID = An ID to identify your account

## Usage 
ansible-playbook -i hosts qca-install.yml --private-key=Mikesh.pem --extra-vars "ssh_user=ec2-user  URL=https://s3.amazonaws.com/REPLACE_ME_BUCKET/REPLACE_ME_FILE ActivationID=xxxx-xxxx CustomerID=xxxx-xxxx"

## Important links
* [Dynamic Amazon EC2 Inventory Management for Ansible](https://aws.amazon.com/blogs/apn/getting-started-with-ansible-and-dynamic-amazon-ec2-inventory-management/)
* [Running Ansible Playbooks using EC2 Systems Manager](https://aws.amazon.com/blogs/mt/running-ansible-playbooks-using-ec2-systems-manager-run-command-and-state-manager/)
* [Ansible for managing AWS:](https://docs.ansible.com/ansible/latest/scenario_guides/guide_aws.html)
