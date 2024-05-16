# Ansible playbook for cowsay

Test for cowsay before running an ad hoc command

```t
ansible@ansible-ctl:~/cowsay$ ansible -i inventory servers -a "cowsay It Worked"
192.168.50.5 | FAILED | rc=2 >>
[Errno 2] No such file or directory: b'cowsay'
```

Run Ansible playbook

```t
ansible@ansible-ctl:~/cowsay$ ansible-playbook -i inventory playbook.yml

PLAY [servers] **********************************************************************************************************************************************************

TASK [Gathering Facts] **************************************************************************************************************************************************
ok: [192.168.50.5]

TASK [Install cowsay] ***************************************************************************************************************************************************
changed: [192.168.50.5]

PLAY RECAP **************************************************************************************************************************************************************
192.168.50.5               : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

Test cowsay again using an ad hoc command

```t
ansible@ansible-ctl:~/cowsay$ ansible -i inventory servers -a "cowsay It Worked"
192.168.50.5 | CHANGED | rc=0 >>
 ___________
< It Worked >
 -----------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```
