# Ansible Playbook for Deploying a Shell Script

This Ansible Playbook will be able to Deploy Shell Script on the Target host, and as well will configurate the crontab entry.
Just Replace the 'vars' values in the YAML file for your use case.

## Introduction

This Ansible playbook is designed to automate the deployment of a Shell script to one or more remote servers. It will copy the specified Bash script from the local machine to the target servers and then execute it. This playbook assumes you have Ansible installed on your local machine and have SSH access to the remote servers.

## Prerequisites

Before running this playbook, ensure the following:

1. Ansible is installed on your local machine.
2. You have SSH access to the remote servers with appropriate privileges.
3. The Shell script you want to deploy is available on your local machine.

## Instructions

1. Update the `inventory.ini` file with the names or IP addresses of the remote servers where you want to deploy the Shell script. You can specify a single host or a list of hosts.

2. Modify `deploy-with-ansible.sh` to the name of the Bash script you want to deploy. Ensure that the script is available at the `SCRIPT_SRC` specified in the playbook.

3. Set all the variable in the script as per your requirement.

## Running the Playbook

Execute the following command in the terminal:

```bash
ansible-playbook -i inventory.ini deploy_script.yml
```

Ansible will connect to the target servers, copy the Shell script, make it executable, and will create an Entry in the crontab.

## Notes

- Ensure that the remote servers have the necessary permissions to execute the script after copying.
- If your Bash script requires specific environment configurations or dependencies, ensure they are already set up on the target servers.
- Make sure to have backups or proper version control for critical scripts before running this playbook in a production environment.
## Disclaimer

This playbook is provided as-is, and the user assumes full responsibility for its usage. Ensure you understand the implications of running the Bash script on the target servers and verify its behavior before deploying in a production environment.
