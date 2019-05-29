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
ok: [R7]
ok: [R4]
ok: [R2]
ok: [R8]
ok: [R3]
ok: [R5]
ok: [R9]
ok: [R6]

TASK [check hosts backup directory] ******************************************************************************************************
changed: [R7]
changed: [R1]
changed: [R4]
changed: [R2]
changed: [R10]
changed: [R3]
changed: [R9]
changed: [R8]
changed: [R5]
changed: [R6]

TASK [create timestamp] ******************************************************************************************************************
changed: [R1]
changed: [R7]
changed: [R4]
changed: [R2]
changed: [R10]
changed: [R8]
changed: [R5]
changed: [R9]
changed: [R6]
changed: [R3]

TASK [copy] ******************************************************************************************************************************
changed: [R4]
changed: [R1]
changed: [R7]
changed: [R2]
changed: [R10]
changed: [R3]
changed: [R8]
changed: [R6]
changed: [R5]
changed: [R9]

PLAY RECAP *******************************************************************************************************************************
R1                         : ok=4    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
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


<details>
<summary>Backup file</summary>

<pre>
Building configuration...

Current configuration : 1525 bytes
!
upgrade fpd auto
version 12.4
service timestamps debug datetime msec
service timestamps log datetime msec
no service password-encryption
!
hostname R10
!
boot-start-marker
boot-end-marker
!
logging message-counter syslog
!
no aaa new-model
ip source-route
no ip icmp rate-limit unreachable
ip cef
!
!
!
!
no ip domain lookup
ip domain name test.com
no ipv6 cef
!
multilink bundle-name authenticated
!
!
!
!
!
!
!
!
!
!
!
!
!
!
!
!
memory-size iomem 0
username cisco privilege 15 secret 5 $1$eZ7H$Q.5UxpjUWNDKZde3mdhO/0
archive
 log config
  hidekeys
!
!
!
!
!
ip tcp synwait-time 5
ip ssh version 2
!
!
!
!
interface Ethernet0/0
 no ip address
 shutdown
 duplex auto
!
interface GigabitEthernet0/0
 ip address 10.0.0.1 255.255.255.0
 duplex full
 speed 1000
 media-type gbic
 negotiation auto
!
interface GigabitEthernet1/0
 no ip address
 shutdown
 negotiation auto
!
interface GigabitEthernet2/0
 ip address 192.168.1.100 255.255.255.0
 negotiation auto
!
ip forward-protocol nd
ip route 20.0.0.0 255.254.0.0 10.0.0.2
ip route 30.0.0.0 255.254.0.0 10.0.0.3
ip route 40.0.0.0 255.254.0.0 10.0.0.4
no ip http server
no ip http secure-server
!
!
!
no cdp log mismatch duplex
!
!
!
!
!
!
control-plane
!
!
!
mgcp fax t38 ecm
!
!
!
!
gatekeeper
 shutdown
!
!
line con 0
 exec-timeout 0 0
 privilege level 15
 logging synchronous
 stopbits 1
line aux 0
 exec-timeout 0 0
 privilege level 15
 logging synchronous
 stopbits 1
line vty 0 4
 login local
 transport input ssh
line vty 5 15
 login local
 transport input ssh
!
</pre>
</details>
