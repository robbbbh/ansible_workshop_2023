# Lab 3 - Installing and enable a Webserver Using a Jinja2 Template

Once you have completed each exercise, run the playbook using the `ansible-playbook webserver.yml` command.

## Exercise 1

Use the `ansible.builtin.yum` module to install the httpd package. This will require you to install the package:
* httpd

Use the [ansible.builtin.yum](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_module.html) documentation to see the modules usage.

Edit the following code snippet in `webserver.yml`:

```yaml
- name: Install httpd
    ansible.builtin.yum:
        # your solution
```

## Exercise 2

Use the `ansible.builtin.service` module to start and enable the httpd server. 

Use the [ansible.builtin.service](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/service_module.html) documentation to see the modules usage.

Edit the following code snippet in `webserver.yml`:

```yaml
- name: Start and enable the httpd service
    ansible.builtin.service:
      # Your solution
```

## Exercise 3

Use the `ansible.builtin.template` to populate the html server. We must set the file permissions to "0755" and the file destination as `/var/www/html/index.html`

Use the [ansible.builtin.template](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/template_module.html) documentation to see the modules usage.

Edit the following code snippet in `webserver.yml`:

```yaml
- name: Populate html webserver
    ansible.builtin.template:
    # Your solution
```

## Exercise 4

Use the `ansible.builtin.service` module to restart the `httpd` service

Use the [ansible.builtin.service](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/service_module.html) documentation to see the modules usage.

Edit the following code snippet in `webserver.yml`:

```yaml
- name: Restart the httpd service
    ansible.builtin.service:
      # Your solution
```

## Run Your code!

Once you have completed each exercise, run the playbook using the `ansible-playbook webserver.yml` command. If the playbook runs successfully, try using the `curl` command to test if your website is up and running. (e.g: curl my.webserver.com).