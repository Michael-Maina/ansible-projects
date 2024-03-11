# Ansible Roles for Server Configuration

This Ansible project contains roles for configuring different types of servers, including base setup, database server, load balancer, and web server. Each role automates the setup process for the corresponding server type.

## Roles

### Base

The base role is responsible for the initial setup of all servers. It performs the following tasks:

- Updates all servers to ensure they have the latest packages and security patches.
- Creates a new user on all servers and sets up SSH key-based authentication.
- Copies a public SSH key and custom sudoers file for secure access and permissions management.

### Database Server

The db_server role installs and configures MySQL database server on the designated hosts. It ensures the database server is set up correctly and ready to use by the application.

### Load Balancer

The load_balancer role installs and configures HAProxy load balancer on the designated hosts. It sets up load balancing rules to distribute incoming traffic across multiple backend servers, ensuring high availability and scalability.

### Web Server

The web_server role installs and configures Nginx web server on the designated hosts. It sets up virtual hosts and SSL certificates if required, making the servers ready to serve web content.
