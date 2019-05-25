# ***Topology for tests v1***

![topology_ansiblet1](https://user-images.githubusercontent.com/50756076/58367722-a2c46780-7ee2-11e9-83c0-2cfe1c9e01cd.jpg)

## Show commands

### ***Run test_v1.yaml (run as user cisco and ask for password)***
```
ansible-playbook test_v1.yaml -u cisco -k
```

***Output***
```
PLAY [Routers] **********************************************************************************

TASK [Show run] *********************************************************************************
ok: [R10]
ok: [R1]
ok: [R4]
ok: [R2]
ok: [R7]
ok: [R3]
ok: [R8]
ok: [R5]
ok: [R9]
ok: [R6]

TASK [debug] ************************************************************************************
ok: [R1] => {
    "ipbrief.stdout_lines": [
        [
            "Interface                  IP-Address      OK? Method Status                Protocol",
            "Ethernet0/0                unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet0/0         10.0.0.2        YES NVRAM  up                    up      ",
            "GigabitEthernet1/0         20.0.0.1        YES NVRAM  up                    up      ",
            "GigabitEthernet2/0         unassigned      YES NVRAM  administratively down down    ",
            "SSLVPN-VIF0                unassigned      NO  unset  up                    up"
        ]
    ]
}
ok: [R4] => {
    "ipbrief.stdout_lines": [
        [
            "Interface                  IP-Address      OK? Method Status                Protocol",
            "Ethernet0/0                unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet0/0         10.0.0.4        YES NVRAM  up                    up      ",
            "GigabitEthernet1/0         40.0.0.1        YES NVRAM  up                    up      ",
            "GigabitEthernet2/0         unassigned      YES NVRAM  administratively down down    ",
            "SSLVPN-VIF0                unassigned      NO  unset  up                    up"
        ]
    ]
}
ok: [R10] => {
    "ipbrief.stdout_lines": [
        [
            "Interface                  IP-Address      OK? Method Status                Protocol",
            "Ethernet0/0                unassigned      YES unset  administratively down down    ",
            "GigabitEthernet0/0         10.0.0.1        YES manual up                    up      ",
            "GigabitEthernet1/0         unassigned      YES unset  administratively down down    ",
            "GigabitEthernet2/0         192.168.1.100   YES manual up                    up      ",
            "SSLVPN-VIF0                unassigned      NO  unset  up                    up"
        ]
    ]
}
ok: [R7] => {
    "ipbrief.stdout_lines": [
        [
            "Interface                  IP-Address      OK? Method Status                Protocol",
            "Ethernet0/0                unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet0/0         10.0.0.3        YES NVRAM  up                    up      ",
            "GigabitEthernet1/0         30.0.0.1        YES manual up                    up      ",
            "GigabitEthernet2/0         unassigned      YES NVRAM  administratively down down    ",
            "SSLVPN-VIF0                unassigned      NO  unset  up                    up"
        ]
    ]
}
ok: [R2] => {
    "ipbrief.stdout_lines": [
        [
            "Interface                  IP-Address      OK? Method Status                Protocol",
            "Ethernet0/0                unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet0/0         unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet1/0         20.0.0.2        YES NVRAM  up                    up      ",
            "GigabitEthernet2/0         20.1.0.1        YES NVRAM  up                    up      ",
            "SSLVPN-VIF0                unassigned      NO  unset  up                    up"
        ]
    ]
}
ok: [R3] => {
    "ipbrief.stdout_lines": [
        [
            "Interface                  IP-Address      OK? Method Status                Protocol",
            "Ethernet0/0                unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet0/0         unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet1/0         unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet2/0         20.1.0.2        YES NVRAM  up                    up      ",
            "SSLVPN-VIF0                unassigned      NO  unset  up                    up"
        ]
    ]
}
ok: [R8] => {
    "ipbrief.stdout_lines": [
        [
            "Interface                  IP-Address      OK? Method Status                Protocol",
            "Ethernet0/0                unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet0/0         unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet1/0         30.0.0.2        YES NVRAM  up                    up      ",
            "GigabitEthernet2/0         30.1.0.1        YES NVRAM  up                    up      ",
            "SSLVPN-VIF0                unassigned      NO  unset  up                    up"
        ]
    ]
}
ok: [R9] => {
    "ipbrief.stdout_lines": [
        [
            "Interface                  IP-Address      OK? Method Status                Protocol",
            "Ethernet0/0                unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet0/0         unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet1/0         unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet2/0         30.1.0.2        YES NVRAM  up                    up      ",
            "SSLVPN-VIF0                unassigned      NO  unset  up                    up"
        ]
    ]
}
ok: [R5] => {
    "ipbrief.stdout_lines": [
        [
            "Interface                  IP-Address      OK? Method Status                Protocol",
            "Ethernet0/0                unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet0/0         unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet1/0         40.0.0.2        YES NVRAM  up                    up      ",
            "GigabitEthernet2/0         40.1.0.1        YES NVRAM  up                    up      ",
            "SSLVPN-VIF0                unassigned      NO  unset  up                    up"
        ]
    ]
}
ok: [R6] => {
    "ipbrief.stdout_lines": [
        [
            "Interface                  IP-Address      OK? Method Status                Protocol",
            "Ethernet0/0                unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet0/0         unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet1/0         unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet2/0         40.1.0.2        YES NVRAM  up                    up      ",
            "SSLVPN-VIF0                unassigned      NO  unset  up                    up"
        ]
    ]
}

PLAY RECAP **************************************************************************************
R1                         : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R10                        : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R2                         : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R3                         : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R4                         : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R5                         : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R6                         : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R7                         : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R8                         : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R9                         : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

```

### ***Run test_v1.yaml on limit to just one host(run as user cisco and ask for password)***
```
ansible-playbook --limit R1  test_v1.yaml -u cisco -k
```
***Output***
```
PLAY [Routers] **********************************************************************************

TASK [Show run] *********************************************************************************
ok: [R1]

TASK [debug] ************************************************************************************
ok: [R1] => {
    "ipbrief.stdout_lines": [
        [
            "Interface                  IP-Address      OK? Method Status                Protocol",
            "Ethernet0/0                unassigned      YES NVRAM  administratively down down    ",
            "GigabitEthernet0/0         10.0.0.2        YES NVRAM  up                    up      ",
            "GigabitEthernet1/0         20.0.0.1        YES NVRAM  up                    up      ",
            "GigabitEthernet2/0         unassigned      YES NVRAM  administratively down down    ",
            "SSLVPN-VIF0                unassigned      NO  unset  up                    up"
        ]
    ]
}

PLAY RECAP **************************************************************************************
R1                         : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

```
