# Ansible Learning Projects

This repository contains projects aimed at learning how to use Ansible for automating various tasks in IT infrastructure management, configuration management, and application deployment.

## About Ansible

Ansible is an open-source automation tool that simplifies IT orchestration, configuration management, and application deployment. It uses simple YAML-based playbooks to describe automation tasks and can manage multiple servers in a network simultaneously.

## Individual Project Structure

- **playbooks**: Contains Ansible playbooks used for automating tasks.
- **inventories**: Inventory files defining the hosts or servers Ansible manages.
- **group_vars**: Directory for storing group variables used in playbooks.
- **roles**: Reusable components that encapsulate playbooks, variables, and tasks for specific tasks or applications.
- **README.md**: Provides an overview of the project

## Projects

1. **Update Servers**: Automate the process of updating packages on multiple servers using Ansible playbooks.
   - Project: [Update multiple servers](./update-multiple-servers)
   - Description: This playbook updates packages on servers listed in the inventory.


## Getting Started

To get started with Ansible and the projects in this repository, follow these steps:

1. **Install Ansible**: Install Ansible on your local machine or a control node by following the instructions in the [Ansible Documentation](https://docs.ansible.com/ansible/latest/installation_guide/index.html).
   
2. **Clone the Repository**: Clone this repository to your local machine using the following command:
```bash
git clone https://github.com/Michael-Maina/ansible-projects.git
```

3. **Navigate to Project**: Navigate to the project directory you are interested in:
```bash
cd ansible-projects/project-name
```

4. **Run the Playbook**: Execute the playbook using the `ansible-playbook` command. For example:
```bash
ansible-playbook -i inventories/hosts playbook.yml
```

## Acknowledgements

- Thanks to the Ansible community for creating and maintaining Ansible.
- Inspiration for projects and ideas from various Ansible tutorials and documentation.