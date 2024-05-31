# Ansible Commands and Their Usage

## Basic Commands

### Ansible Version
```sh
ansible --version
```
Show the Ansible version information.

Ansible Help
sh
Copy code
ansible --help
Show help for Ansible commands.

Ad-hoc Commands
Ping Hosts
sh
Copy code
ansible all -m ping
Ping all hosts to check connectivity.

Execute a Command on Hosts
sh
Copy code
ansible all -m shell -a "uptime"
Run a shell command (e.g., uptime) on all hosts.

Copy a File to Hosts
sh
Copy code
ansible all -m copy -a "src=/path/to/source dest=/path/to/destination"
Copy a file from the control machine to all hosts.

Install a Package on Hosts
sh
Copy code
ansible all -m apt -a "name=package_name state=present"
Install a package (e.g., package_name) on all hosts using the apt module.

Reboot Hosts
sh
Copy code
ansible all -m reboot
Reboot all hosts.

Playbook Management
Run a Playbook
sh
Copy code
ansible-playbook playbook.yml
Execute an Ansible playbook (e.g., playbook.yml).

Check Playbook Syntax
sh
Copy code
ansible-playbook playbook.yml --syntax-check
Check the syntax of an Ansible playbook.

List Playbook Tasks
sh
Copy code
ansible-playbook playbook.yml --list-tasks
List all tasks that will be executed in an Ansible playbook.

Run Playbook in Check Mode
sh
Copy code
ansible-playbook playbook.yml --check
Run a playbook in check mode to simulate changes.

Limit Playbook to Specific Hosts
sh
Copy code
ansible-playbook playbook.yml --limit "host_pattern"
Run a playbook on specific hosts matching the given pattern.

Run Playbook with Tags
sh
Copy code
ansible-playbook playbook.yml --tags "tag_name"
Run only the tasks in a playbook that are tagged with a specific tag.

Skip Tags in a Playbook
sh
Copy code
ansible-playbook playbook.yml --skip-tags "tag_name"
Skip tasks tagged with a specific tag in a playbook.

Inventory Management
List Hosts in Inventory
sh
Copy code
ansible-inventory --list -i inventory_file
List all hosts and groups in an inventory file.

Graph Inventory
sh
Copy code
ansible-inventory --graph -i inventory_file
Generate a graph of the inventory file.

Validate Inventory
sh
Copy code
ansible-inventory --validate -i inventory_file
Validate the inventory file for correctness.

Role Management
Create a New Role
sh
Copy code
ansible-galaxy init role_name
Create a new Ansible role with the specified name.

Install a Role from Ansible Galaxy
sh
Copy code
ansible-galaxy install username.role_name
Install a role from Ansible Galaxy.

Remove a Role
sh
Copy code
ansible-galaxy remove username.role_name
Remove a role that was installed from Ansible Galaxy.

Vault Management
Create a New Encrypted File
sh
Copy code
ansible-vault create file.yml
Create a new file and encrypt it with Ansible Vault.

Edit an Encrypted File
sh
Copy code
ansible-vault edit file.yml
Edit an existing encrypted file.

View an Encrypted File
sh
Copy code
ansible-vault view file.yml
View the contents of an encrypted file.

Re-key an Encrypted File
sh
Copy code
ansible-vault rekey file.yml
Change the password of an encrypted file.

Encrypt a Plaintext File
sh
Copy code
ansible-vault encrypt file.yml
Encrypt an existing plaintext file.

Decrypt an Encrypted File
sh
Copy code
ansible-vault decrypt file.yml
Decrypt an encrypted file and convert it to plaintext.

Configuration Management
View Current Configuration
sh
Copy code
ansible-config view
Display the current configuration settings.

List All Configuration Options
sh
Copy code
ansible-config list
List all available configuration options.

Dump Configuration to a File
sh
Copy code
ansible-config dump --only-changed
Dump the current configuration (only changed settings) to a file.

Copy code
Render all ansible basic command and usage in markdown format text
ChatGPT
markdown
Copy code
# Ansible Commands and Their Usage

## Basic Commands

### Ansible Version
```sh
ansible --version
Show the Ansible version information.

Ansible Help
sh
Copy code
ansible --help
Show help for Ansible commands.

Ping Hosts
sh
Copy code
ansible all -m ping
Ping all hosts to check connectivity.

Execute a Command on Hosts
sh
Copy code
ansible all -m shell -a "uptime"
Run a shell command (e.g., uptime) on all hosts.

Copy a File to Hosts
sh
Copy code
ansible all -m copy -a "src=/path/to/source dest=/path/to/destination"
Copy a file from the control machine to all hosts.

Install a Package on Hosts
sh
Copy code
ansible all -m apt -a "name=package_name state=present"
Install a package (e.g., package_name) on all hosts using the apt module.

Reboot Hosts
sh
Copy code
ansible all -m reboot
Reboot all hosts.

Run a Playbook
sh
Copy code
ansible-playbook playbook.yml
Execute an Ansible playbook (e.g., playbook.yml).

Check Playbook Syntax
sh
Copy code
ansible-playbook playbook.yml --syntax-check
Check the syntax of an Ansible playbook.

List Playbook Tasks
sh
Copy code
ansible-playbook playbook.yml --list-tasks
List all tasks that will be executed in an Ansible playbook.

Run Playbook in Check Mode
sh
Copy code
ansible-playbook playbook.yml --check
Run a playbook in check mode to simulate changes.

Limit Playbook to Specific Hosts
sh
Copy code
ansible-playbook playbook.yml --limit "host_pattern"
Run a playbook on specific hosts matching the given pattern.

Run Playbook with Tags
sh
Copy code
ansible-playbook playbook.yml --tags "tag_name"
Run only the tasks in a playbook that are tagged with a specific tag.

Skip Tags in a Playbook
sh
Copy code
ansible-playbook playbook.yml --skip-tags "tag_name"
Skip tasks tagged with a specific tag in a playbook.

List Hosts in Inventory
sh
Copy code
ansible-inventory --list -i inventory_file
List all hosts and groups in an inventory file.

Graph Inventory
sh
Copy code
ansible-inventory --graph -i inventory_file
Generate a graph of the inventory file.

Validate Inventory
sh
Copy code
ansible-inventory --validate -i inventory_file
Validate the inventory file for correctness.

Create a New Role
sh
Copy code
ansible-galaxy init role_name
Create a new Ansible role with the specified name.

Install a Role from Ansible Galaxy
sh
Copy code
ansible-galaxy install username.role_name
Install a role from Ansible Galaxy.

Remove a Role
sh
Copy code
ansible-galaxy remove username.role_name
Remove a role that was installed from Ansible Galaxy.

Create a New Encrypted File
sh
Copy code
ansible-vault create file.yml
Create a new file and encrypt it with Ansible Vault.

Edit an Encrypted File
sh
Copy code
ansible-vault edit file.yml
Edit an existing encrypted file.

View an Encrypted File
sh
Copy code
ansible-vault view file.yml
View the contents of an encrypted file.

Re-key an Encrypted File
sh
Copy code
ansible-vault rekey file.yml
Change the password of an encrypted file.

Encrypt a Plaintext File
sh
Copy code
ansible-vault encrypt file.yml
Encrypt an existing plaintext file.

Decrypt an Encrypted File
sh
Copy code
ansible-vault decrypt file.yml
Decrypt an encrypted file and convert it to plaintext.

View Current Configuration
sh
Copy code
ansible-config view
Display the current configuration settings.

List All Configuration Options
sh
Copy code
ansible-config list
List all available configuration options.

Dump Configuration to a File
sh
Copy code
ansible-config dump --only-changed
Dump the current configuration (only changed settings) to a file.