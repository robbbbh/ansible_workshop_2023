# Lab 1 - Introduction to the Basics

## Exercise 1
Review the `inventory` and `ansible.cfg` files.

Print the contents of the ansible.cfg.
```bash
cat ./ansible.cfg
```

Print the content of the ivnentory file.
```bash
cat ./inventory
```
## Exercise 2

Install Ansible and Verify the Installation

Install Ansible with the `yum` command. Ensure you run this command with root privileges.
```bash
sudo yum install ansible
```

Verify the Installation by checking the ansible version.
```bash
ansible --version
```

## Exercise 3
Run an Ansible ad-hoc command to print the contents of the server message of the day (motd).

```bash
ansible web -a "cat /etc/motd"
```

Run an Ansible ad-hoc command to restart the httpd service.

```bash
ansible web -m service -a "name=httpd state=restarted"
```

## Exercise 4 
View the motd.yml playbook. Can you figure out What the playbook does?

```bash
cat ./motd.yml
```

Run the playbook using the `ansible-playbook` command and observe the output. To see a more verbose output, append `-v` as an argument to the command.

```bash
ansible-playbook motd.yml
```
