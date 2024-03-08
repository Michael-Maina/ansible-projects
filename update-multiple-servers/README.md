# Update Servers Playbook

This playbook automates the process of updating packages on multiple servers using Ansible. It also demonstrates how to securely manage user passwords using Ansible Vault.

## Approach to Securing User Passwords

In this playbook, we use Ansible Vault to securely manage user passwords. Ansible Vault allows us to encrypt sensitive data such as passwords, ensuring they are safely stored and transmitted.

### Steps Taken:

1. **Define Passwords and Users in Variables:**

   We define two dictionaries in the `all.yaml` file:
   
   ```yaml
   passwords:
     atreides: *****
     harkonnen: *****
     leto: *****
   
   users:
     atreides: paul
     harkonnen: raban
     leto: leto
   ```
    The passwords dictionary stores the passwords for each server, and the users dictionary maps each server to its corresponding user.

2. **Set Ansible Variables:**

    We set the ansible_become_pass and ansible_user variables in the playbook based on the inventory hostname:
    ```yaml
    ansible_become_pass: "{{ passwords[inventory_hostname] }}"
    ansible_user: "{{ users[inventory_hostname] }}"
    ```

3. **Encrypt Passwords with Ansible Vault:**

    We encrypt the all.yaml file containing sensitive data using Ansible Vault:
    ```bash
    ansible-vault encrypt group_vars/all.yaml
    ```

4. **Usage:**

    When running the playbook, provide the vault password using the --ask-vault-pass option:
    ```bash
    ansible-playbook playbooks/update_servers.yml
    ```

    The `ansible.cfg` file defines the inventory file and the vault password file. The vault password file is an executable Python script that is run by Ansible to retrieve the password which is defined as an environment variable.

    ```bash
    export VAULT_PASSWORD="your_vault_password"
    ```

    This approach avoids the risk of accidentally pushing your vault password to version control repositories, ensuring better security. However, you only need to set the vault password environment variable once per terminal session, reducing the inconvenience of entering it every time you run Ansible.
