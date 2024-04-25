### Ansible

Ansible is an open-source automation tool used for
* Configuration management
* Application deployment
* Cloud provisioning and orchestration(But not recommended)

#### What is configuration?

Before deploying the application we need to make the server ready. For example
* Installing packages
* Installing Programming languages
* Installing build tools.
* Installing Application Runtime.
* Creation of users, folders, etc.
* Setting permissions.
* Creation of systemctl services.

As a DevOps engineer we need to do this effectively. Basically CRUD over the server.

Creation of configuration --> should be fast and accurate</br>
Update the configuration --> any changes in configuration should be rolled out asap.</br>
Delete the configuration --> delete the configuration if not required.</br>
Read the configuration --> it is easy to read the configuration of server through ansible playbooks.</br>

#### Disadvantages of shell

* Does your shell script can work with all distributions? because command may change based on distribution.
* Suppose on big billion day we have 1000 servers. How can we configure servers?
* Is shell scripting effective for error handling?
* Is shell scripting easy to understand and read?
* How to manage sensitive information in shell scripts?
* How to integrate shell script with external systems like AWS, Azure, etc.

### Ansible Features
* Platform independent
* Scalable
* Idempotence
* Error Handling
* Readable and maintainable
* Vault
* Rich modules
* Agent less

### Pull vs Push configuration

![alt text](images/pullvspush.jpg)

![alt text](images/push.jpg)

**PULL:**
1. Nodes should connect to the servers through agent software.
2. Nodes should download the configuration periodically, say every 30min.
3. Even there is no change in configuration, agents connect to servers that creates unnecessary traffic and data consumption.

**PUSH:**
1. Unlike pull there is no need of agent installation.
2. Whenever there is a change in configuration, server can push to the nodes directly.
3. Ansible uses SSH authentication to connect to the servers.