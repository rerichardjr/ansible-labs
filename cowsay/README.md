# Ansible playbook for cowsay

Test for cowsay before running the playbook using the command module

```t
ansible@ansible-ctl:~/cowsay$ ansible servers -a "cowsay It Worked" -u ansible
192.168.1.20 | FAILED | rc=2 >>
[Errno 2] No such file or directory: b'cowsay'
```

Run Ansible playbook

```t
ansible@ansible-ctl:~/cowsay$ ansible-playbook playbook.yml -u ansible

PLAY [servers] **********************************************************************************************************************************************************

TASK [Gathering Facts] **************************************************************************************************************************************************
ok: [192.168.1.20]

TASK [Install cowsay] ***************************************************************************************************************************************************
changed: [192.168.1.20]

PLAY RECAP **************************************************************************************************************************************************************
192.168.1.20               : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

Test cowsay again using the command module

```t
ansible@ansible-ctl:~/cowsay$ ansible servers -a "cowsay It Worked" -u ansible
192.168.1.20 | CHANGED | rc=0 >>
 ___________
< It Worked >
 -----------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```
