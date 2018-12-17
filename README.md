# deploy_qualys_Ansible
Deploy Qualys Cloud Agent in Linux instances using Ansible-Playbook

The playbook InstallQCA.yml can be used to deploy QCA across the assests included in your "host" file.

Input parameters which are required are:
private-key = private-key to access the instances ( ansible works via SSH)
ssh_user = username to login into the instance
URL = the URL where the file is hosted eg: Webserver, S3, Blob Storage, Cloud Storage
ActivationID = An ID that provides a way to group agents and bind them to your account 
CustomerID = An ID to identify your account

# Examples:  
ansible-playbook -i hosts qca-install.yml --private-key=Mikesh.pem --extra-vars "ssh_user=ec2-user  URL=https://s3.amazonaws.com/REPLACE_ME_BUCKET/REPLACE_ME_FILE ActivationID=xxxx-xxxx CustomerID=xxxx-xxxx"

# Important links:
1. Dynamic Amazon EC2 Inventory Management for Ansible: https://aws.amazon.com/blogs/apn/getting-started-with-ansible-and-dynamic-amazon-ec2-inventory-management/
2. Running Ansible Playbooks using EC2 Systems Manager: https://aws.amazon.com/blogs/mt/running-ansible-playbooks-using-ec2-systems-manager-run-command-and-state-manager/
3. Ansible for managing AWS: https://docs.ansible.com/ansible/latest/scenario_guides/guide_aws.html
