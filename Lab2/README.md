# Lab 2 - Installing a Database & its Dependencies

## Exercise 1

Use the `ansible.builtin.yum` module to install the mariadb server and its dependencies. This will require you to install the packages:
* mariadb-server
* python3-PyMySQL

Use the [ansible.builtin.yum](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_module.html) documentation to see the modules usage.

Edit the following code snippet in `databse.yml`:

```yaml
- name: Install mariadb-server & python3-PyMySQL
    ansible.builtin.yum:
        # your solution
```

## Exercise 2

Use the `ansible.builtin.service` module to start and enable the mariadb database. 

Use the [ansible.builtin.service](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/service_module.html) documentation to see the modules usage.

Edit the following code snippet in `database.yml`:

```yaml
- name: Start and enable the mariadb service
    ansible.builtin.service:
      # Your solution
```

## Exercise 3

Use the `community.mysql.mysql_user` to change the root password. Mariadb server installs with default login_user of root and no password. To secure this user as part of an idempotent playbook, you must create at least two tasks: 1) change the root user’s password, without providing any login_user/login_password details, 2) drop a ~/.my.cnf file containing the new root credentials. Subsequent runs of the playbook will then succeed by reading the new credentials from the file.

This collection may need to be manually installed. It can be done with:

```bash
ansible-galaxy collection install community.mysql
```

Use the [community.mysql.mysql_user](https://docs.ansible.com/ansible/latest/collections/community/mysql/mysql_user_module.html#ansible-collections-community-mysql-mysql-user-module) documentation to see the modules usage.

Edit the following code snippet in `database.yml`:

```yaml
- name: Set Mysql root password
    community.mysql.mysql_user:
    login_user: root
    login_password: password
    name: root
    check_implicit_admin: true
    password: password
    host:

```

## Run Your code!

Once you have completed each exercise, run the playbook using the `ansible-playbook database.yml` command. 

If the playbook runs successfully, try using the `mysql` command on the db server to connect to the database. (e.g: mysql -h mydb.host -u username -p).

## Possible Errors 1
Is you get an error saying "Could not resolve module/ action 'community.mysql.mysl_user'" it means we do not have the collection installed. To install the correct collection run:

```bash
ansible-galaxy collection install community.mysql
```

Once it's installed, try running the playbook again.

## Possible Errors 2
If you get an error saying "Can't connect to MYSQL server on localhost" then let me know and we can skip this task for now.