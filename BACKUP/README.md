# ***Topology for tests***

![topology_ansiblet1](https://user-images.githubusercontent.com/50756076/58367722-a2c46780-7ee2-11e9-83c0-2cfe1c9e01cd.jpg)

### ***Run backup.yaml (run as user cisco and ask for password)***
Backup to txt file.
```
ansible-playbook backup.yaml -u cisco -k
```
<details>
<summary>Output</summary>
<pre>
PLAY [Routers] ***************************************************************************************************************************

TASK [show run] **************************************************************************************************************************
ok: [R10]
ok: [R1]
ok: [R4]
ok: [R7]
ok: [R2]
ok: [R3]
ok: [R9]
ok: [R8]
ok: [R5]
ok: [R6]

TASK [check hosts backup directory] ******************************************************************************************************
changed: [R7]
changed: [R10]
changed: [R4]
ok: [R1]
changed: [R2]
changed: [R3]
changed: [R9]
changed: [R5]
changed: [R8]
changed: [R6]

TASK [create timestamp] ******************************************************************************************************************
changed: [R2]
changed: [R7]
changed: [R4]
changed: [R10]
changed: [R1]
changed: [R3]
changed: [R8]
changed: [R5]
changed: [R9]
changed: [R6]

TASK [copy] ******************************************************************************************************************************
ok: [R1]
changed: [R10]
changed: [R2]
changed: [R4]
changed: [R7]
changed: [R3]
changed: [R6]
changed: [R9]
changed: [R5]
changed: [R8]

PLAY RECAP *******************************************************************************************************************************
R1                         : ok=4    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R10                        : ok=4    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R2                         : ok=4    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R3                         : ok=4    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R4                         : ok=4    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R5                         : ok=4    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R6                         : ok=4    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R7                         : ok=4    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R8                         : ok=4    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R9                         : ok=4    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0


</pre>
</details>

<details>
<summary>Tree</summary>

<pre>
├── BACKUP
│   ├── R1
│   │   └── R1_running-config_29052019.txt
│   ├── R10
│   │   └── R10_running-config_29052019.txt
│   ├── R2
│   │   └── R2_running-config_29052019.txt
│   ├── R3
│   │   └── R3_running-config_29052019.txt
│   ├── R4
│   │   └── R4_running-config_29052019.txt
│   ├── R5
│   │   └── R5_running-config_29052019.txt
│   ├── R6
│   │   └── R6_running-config_29052019.txt
│   ├── R7
│   │   └── R7_running-config_29052019.txt
│   ├── R8
│   │   └── R8_running-config_29052019.txt
│   └── R9
│       └── R9_running-config_29052019.txt
</pre>
</details>
