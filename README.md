# ansible-regexp

Example playbook playgound testing some Ansible regular expression filters per [Ansible's docs](https://docs.ansible.com/ansible/latest/user_guide/playbooks_filters.html?highlight=regex%20match#regular-expression-filters). This documentation is now very good, but at the time I wrote this test repo, it had many confusing errors.


Run: 

```zsh
√ ansible-regexp-examples % ansible-playbook -i ./ansible_hosts ./playbook.yml
```

# Context 

Ansible evidently clones its own python executable. We installed Ansible with Homebrew.

```zsh
√ ansible-regexp-examples % ansible --version
ansible 2.9.2
  config file = None
  configured module search path = ['/Users/iain/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/local/Cellar/ansible/2.9.2/libexec/lib/python3.7/site-packages/ansible
  executable location = /usr/local/bin/ansible
  python version = 3.7.5 (default, Nov 30 2019, 08:09:42) [Clang 11.0.0 (clang-1100.0.33.12)]
```

And for the *remote* server's (`localhost`'s) python3 - per `ansible_python_interpreter=/usr/bin/python3` in `ansible_hosts` - it uses macOS Catalina's default installed python3:

```zsh
√ ansible-regexp-examples % python3 --version 
Python 3.7.3
√ ansible-regexp-examples % which python3 # `localhost`'s python3
/usr/bin/python3
```

