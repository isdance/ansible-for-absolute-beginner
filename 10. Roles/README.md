Roles means do a set of tasks to make a box become certain role, like a db server or web server.
![Roles](./docs/images/roles-01.png)

There is not many reusability for playbooks
![Roles](./docs/images/roles-02.png)

However, you can package it, so it can be used by 1 server, or 100 servers
![Roles](./docs/images/roles-03.png)

Meanwhile, roles define a set of best practices for organizing your code:
![Roles](./docs/images/roles-04.png)

Also, roles can be shared with communities. [ansible galaxy](https://galaxy.ansible.com/) is one of those

To use roles you defined, there are 2 ways:

1. use folder structure:

When Ansible runs, it looks for the `mysql` role under the `roles` directory

![Roles](./docs/images/roles-05.png)

2. There is a common directory designated for roles on your system, `/etc/ansible/roles`

This default location can be changed from `/etc/ansible/ansible.cfg`

```
roles_path = /etc/ansible/roles
```

You can use ansible-galaxy cli to install roles

```
ansible-galaxy install geerlingguy.mysql
```

It will be downloaded, and extracted into your /etc/ansible/roles folder

![Roles](./docs/images/roles-06.png)

Benefits:

- Easy to reuse and share
  ![Roles](./docs/images/roles-07.png)
