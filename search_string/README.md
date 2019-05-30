# ***Topology for string-searching***

![topology_ansiblet1](https://user-images.githubusercontent.com/50756076/58367722-a2c46780-7ee2-11e9-83c0-2cfe1c9e01cd.jpg)
### ***Run string_search.yaml (using vars)***
```
ansible-playbook string_search.yaml
```
<details>
<summary>Output</summary>
<pre>

PLAY [Routers] **********************************************************************************

TASK [Get conf vars] ****************************************************************************
ok: [R10]
ok: [R1]
ok: [R4]
ok: [R7]
ok: [R2]
ok: [R3]
ok: [R8]
ok: [R9]
ok: [R5]
ok: [R6]

TASK [Get login vars] ***************************************************************************
ok: [R10]
ok: [R1]
ok: [R4]
ok: [R7]
ok: [R2]
ok: [R3]
ok: [R8]
ok: [R9]
ok: [R5]
ok: [R6]

TASK [Define login] *****************************************************************************
ok: [R10]
ok: [R1]
ok: [R7]
ok: [R4]
ok: [R2]
ok: [R3]
ok: [R8]
ok: [R9]
ok: [R5]
ok: [R6]

TASK [Show ip interface brief] ******************************************************************
ok: [R10]
ok: [R4]
ok: [R7]
ok: [R1]
ok: [R2]
ok: [R3]
ok: [R8]
ok: [R5]
ok: [R9]
ok: [R6]

TASK [check line; ip address 20.0.0.1 255.255.255.252 (skipp if exists)] ************************
ok: [R10] => {
    "msg": "ip address 20.0.0.1 255.255.255.252 is missing"
}
skipping: [R1]
ok: [R4] => {
    "msg": "ip address 20.0.0.1 255.255.255.252 is missing"
}
ok: [R7] => {
    "msg": "ip address 20.0.0.1 255.255.255.252 is missing"
}
ok: [R2] => {
    "msg": "ip address 20.0.0.1 255.255.255.252 is missing"
}
ok: [R3] => {
    "msg": "ip address 20.0.0.1 255.255.255.252 is missing"
}
ok: [R9] => {
    "msg": "ip address 20.0.0.1 255.255.255.252 is missing"
}
ok: [R8] => {
    "msg": "ip address 20.0.0.1 255.255.255.252 is missing"
}
ok: [R5] => {
    "msg": "ip address 20.0.0.1 255.255.255.252 is missing"
}
ok: [R6] => {
    "msg": "ip address 20.0.0.1 255.255.255.252 is missing"
}

TASK [check line; ntp server 10.100.100.100 (skipp if exists))] *********************************
ok: [R10] => {
    "msg": "line:ntp server 10.100.100.100 is missing"
}
ok: [R1] => {
    "msg": "line:ntp server 10.100.100.100 is missing"
}
ok: [R4] => {
    "msg": "line:ntp server 10.100.100.100 is missing"
}
skipping: [R7]
ok: [R2] => {
    "msg": "line:ntp server 10.100.100.100 is missing"
}
ok: [R3] => {
    "msg": "line:ntp server 10.100.100.100 is missing"
}
ok: [R8] => {
    "msg": "line:ntp server 10.100.100.100 is missing"
}
ok: [R9] => {
    "msg": "line:ntp server 10.100.100.100 is missing"
}
ok: [R5] => {
    "msg": "line:ntp server 10.100.100.100 is missing"
}
ok: [R6] => {
    "msg": "line:ntp server 10.100.100.100 is missing"
}

TASK [check line; ip route 20.0.0.0 255.254.0.0 10.0.0.2 (skipp if exists))] ********************
skipping: [R10]
ok: [R1] => {
    "msg": "line:ip route 20.0.0.0 255.254.0.0 10.0.0.2 is missing"
}
ok: [R4] => {
    "msg": "line:ip route 20.0.0.0 255.254.0.0 10.0.0.2 is missing"
}
ok: [R7] => {
    "msg": "line:ip route 20.0.0.0 255.254.0.0 10.0.0.2 is missing"
}
ok: [R2] => {
    "msg": "line:ip route 20.0.0.0 255.254.0.0 10.0.0.2 is missing"
}
ok: [R3] => {
    "msg": "line:ip route 20.0.0.0 255.254.0.0 10.0.0.2 is missing"
}
ok: [R8] => {
    "msg": "line:ip route 20.0.0.0 255.254.0.0 10.0.0.2 is missing"
}
ok: [R9] => {
    "msg": "line:ip route 20.0.0.0 255.254.0.0 10.0.0.2 is missing"
}
ok: [R5] => {
    "msg": "line:ip route 20.0.0.0 255.254.0.0 10.0.0.2 is missing"
}
ok: [R6] => {
    "msg": "line:ip route 20.0.0.0 255.254.0.0 10.0.0.2 is missing"
}

TASK [check line; ip domain name test.com (skipp if exists))] ***********************************
skipping: [R1]
skipping: [R4]
skipping: [R10]
skipping: [R7]
skipping: [R2]
skipping: [R3]
skipping: [R8]
skipping: [R9]
skipping: [R6]
skipping: [R5]

PLAY RECAP **************************************************************************************
R1                         : ok=6    changed=0    unreachable=0    failed=0    skipped=2    rescued=0    ignored=0
R10                        : ok=6    changed=0    unreachable=0    failed=0    skipped=2    rescued=0    ignored=0
R2                         : ok=7    changed=0    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0
R3                         : ok=7    changed=0    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0
R4                         : ok=7    changed=0    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0
R5                         : ok=7    changed=0    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0
R6                         : ok=7    changed=0    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0
R7                         : ok=6    changed=0    unreachable=0    failed=0    skipped=2    rescued=0    ignored=0
R8                         : ok=7    changed=0    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0
R9                         : ok=7    changed=0    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0

</pre>
</details>
