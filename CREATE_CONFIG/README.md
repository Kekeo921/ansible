# ***Topology for tests***

![topology_ansiblet1](https://user-images.githubusercontent.com/50756076/58367722-a2c46780-7ee2-11e9-83c0-2cfe1c9e01cd.jpg)

### ***Run generate_router_conf.yaml***
```
ansible-playbook generate_router_conf.yaml -k
```
<details>
<summary>Output</summary>
<pre>
PLAY [localhost] ********************************************************************************

TASK [Get login vars] ***************************************************************************
ok: [localhost]

TASK [Generate configuration files] *************************************************************
changed: [localhost] => (item={u'ntp1': u'10.0.0.1', u'lo_ip_add': u'2.0.1.1 255.255.255.0', u'ntp2': u'192.168.1.50', u'lo_number': 1, u'dns1': u'192.168.1.50', u'hostname': u'R1', u'lo_description': u'test R1'})
changed: [localhost] => (item={u'ntp1': u'10.0.0.1', u'lo_ip_add': u'2.0.2.1 255.255.255.0', u'ntp2': u'192.168.1.50', u'lo_number': 1, u'dns1': u'192.168.1.50', u'hostname': u'R2', u'lo_description': u'test R2'})
changed: [localhost] => (item={u'ntp1': u'10.0.0.1', u'lo_ip_add': u'2.0.3.1 255.255.255.0', u'ntp2': u'192.168.1.50', u'lo_number': 1, u'dns1': u'192.168.1.50', u'hostname': u'R3', u'lo_description': u'test R3'})

PLAY RECAP **************************************************************************************
localhost                  : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
</pre>
</details>

This is going to generate 3 configuration files: 
```
├── CONFIGS
│   ├── R1.txt
│   ├── R2.txt
│   └── R3.txt
```

<details>
<summary>R1.txt (configuration example)</summary>
<pre>
service timestamps debug datetime msec localtime show-timezone
service timestamps log datetime msec localtime show-timezone
service password-encryption
!
ip domain name test.com
ip name-server 192.168.1.50
ntp server 10.0.0.1
ntp server 192.168.1.50
!
ip ssh version 2
!
interface Loopback1
 description test R1
 ip address 2.0.1.1 255.255.255.0
!
no ip http server
no ip http secure-server
!
access-list 10 permit 10.0.0.0 0.255.255.255
access-list 10 permit 192.168.1.0 0.0.0.255
!
line vty 0 4
 access-class 10 in
 login local
 transport input ssh
line vty 5 15
 access-class 10 in
 login local
 transport input ssh
!

</pre>
</details>

### ***Run push_config.yaml***
```
ansible-playbook push_config.yaml --limit Edge20
```

This is going to push configuration to devices.

<details>
<summary>Output</summary>
<pre>
TASK [Get login vars] ***************************************************************************
ok: [R1]
ok: [R2]
ok: [R3]

TASK [Define login] *****************************************************************************
ok: [R1]
ok: [R2]
ok: [R3]

TASK [push config] ******************************************************************************
changed: [R1]
changed: [R2]
changed: [R3]

TASK [Save running-config] **********************************************************************
changed: [R1]
changed: [R2]
changed: [R3]

TASK [Compare startup to running-config] ********************************************************
ok: [R1]
ok: [R3]
ok: [R2]

PLAY RECAP **************************************************************************************
R1 : ok=5    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0                       
R2 : ok=5    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0                       
R3 : ok=5    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0                                         

</pre>
</details>
<details>
<summary>R1 running config</summary>
<pre>
Building configuration...

Current configuration : 2117 bytes
!
upgrade fpd auto
version 12.4
service timestamps debug datetime msec localtime show-timezone
service timestamps log datetime msec localtime show-timezone
service password-encryption
!
hostname R1
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
ip name-server 192.168.1.50
no ipv6 cef
ntp server 10.0.0.1
ntp server 192.168.1.50
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
memory-size iomem 32
username cisco privilege 15 secret 5 $1$jlv/$wuFQnbRy0H.IKbFKHMM2p0
username krzys privilege 15 secret 5 $1$UHmH$5WEHSDbEl48IoMjzqTm0f1
username ola privilege 15 secret 5 $1$JCIu$auos.crlcffhm4gn0MuuM1
username maciek privilege 15 secret 5 $1$JlBs$y2XBpwOXnjd1E9.4wgL3L1
username adam privilege 15 secret 5 $1$cmVU$ohKJ3fSwRxQC.s2c.ytmu0
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
interface Loopback1
 description test R1
 ip address 2.0.1.1 255.255.255.0
!
interface Ethernet0/0
 no ip address
 shutdown
 duplex auto
!
interface GigabitEthernet0/0
 ip address 10.0.0.2 255.255.255.0
 duplex full
 speed 1000
 media-type gbic
 negotiation auto
!
interface GigabitEthernet1/0
 ip address 20.0.0.1 255.255.255.252
 negotiation auto
!
interface GigabitEthernet2/0
 no ip address
 shutdown
 negotiation auto
!
ip forward-protocol nd
ip route 0.0.0.0 0.0.0.0 10.0.0.1
ip route 20.1.0.0 255.255.255.252 20.0.0.2
ip route 100.0.0.0 255.255.255.0 20.0.0.2
no ip http server
no ip http secure-server
!
!
!
access-list 10 permit 10.0.0.0 0.255.255.255
access-list 10 permit 192.168.1.0 0.0.0.255
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
 access-class 10 in
 login local
 transport input ssh
line vty 5 15
 access-class 10 in
 login local
 transport input ssh
!
end


</pre>
</details>
