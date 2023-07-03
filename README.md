## Ansible Playbook for Automated AWS Infrastructure Provisioning and Termination

This repository contains an Ansible playbook designed to automate the provisioning and termination of AWS infrastructure. The playbook streamlines the process of setting up EC2 instances, security groups, and other necessary configurations for hosting web applications on AWS.

### Features:
- Automates the creation of EC2 instances with the specified configuration.
- Sets up security groups to manage incoming traffic to the instances.
- Deploys a web server environment suitable for hosting web applications.
- Provides tags for easy identification and categorization of AWS resources.

### Prerequisites:
- Ansible installed on your local machine.
- AWS credentials (access key and secret key) with the necessary permissions to create and manage EC2 instances, security groups, and key pairs.
- A valid key pair (PEM file) for secure access to EC2 instances.

### Usage:
1. Clone this repository to your local machine.
2. Create a `keys.yml` file and provide your AWS access key and secret key in the following format:
   ```yaml
   access_key: YOUR_ACCESS_KEY
   secret_key: YOUR_SECRET_KEY
   ```
3. Adjust the playbook variables in `ansible1.yml` to suit your specific project and environment requirements.
4. Run the Ansible playbook with the desired tags for infrastructure creation or destruction:
   - For infrastructure creation: `ansible-playbook ansible1.yml --tags "infra"`
   - For infrastructure termination: `ansible-playbook ansible1.yml --tags "destroy"`

### Important Note:
**Please use this playbook with caution!** The `destroy` play will terminate all AWS resources (instances, security groups, and key pairs) matching the specified tags. Make sure to double-check the tags and configurations to avoid accidental deletion of important resources.
