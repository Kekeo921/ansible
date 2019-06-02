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

This will generate 3 configuration files: 
```
├── CONFIGS
│   ├── R1.txt
│   ├── R2.txt
│   └── R3.txt
```

