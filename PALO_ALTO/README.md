
## Folders
***1. panos_op***
Show commands

### ***Run show_int.yaml***
```
ansible-playbook show_int.yaml
```

Shows list of all interfaces in the default JSON format

<details>
<summary>Output</summary>
<pre>
PLAY [PaloAlto] *******************************************************************************************

TASK [PaloAltoNetworks.paloaltonetworks : Install pan-python required library] ****************************
ok: [PA1]

TASK [PaloAltoNetworks.paloaltonetworks : Install pandevice required library] *****************************
ok: [PA1]

TASK [PaloAltoNetworks.paloaltonetworks : Install xmltodict required library] *****************************
ok: [PA1]

TASK [Get login vars] *************************************************************************************
ok: [PA1]

TASK [Define login] ***************************************************************************************
ok: [PA1]

TASK [show list of all interfaces] ************************************************************************
changed: [PA1]

TASK [debug] **********************************************************************************************
ok: [PA1] => {
    "showint.stdout": {
        "response": {
            "@status": "success",
            "result": {
                "hw": {
                    "entry": [
                        {
                            "duplex": "full",
                            "id": "16",
                            "mac": "ba:db:ee:fb:ad:10",
                            "mode": "(autoneg)",
                            "name": "ethernet1/1",
                            "speed": "10000",
                            "st": "10000/full/up",
                            "state": "up",
                            "type": "0"
                        },
                        {
                            "duplex": "full",
                            "id": "17",
                            "mac": "ba:db:ee:fb:ad:11",
                            "mode": "(autoneg)",
                            "name": "ethernet1/2",
                            "speed": "10000",
                            "st": "10000/full/up",
                            "state": "up",
                            "type": "0"
                        },
                        {
                            "duplex": "full",
                            "id": "18",
                            "mac": "ba:db:ee:fb:ad:12",
                            "mode": "(autoneg)",
                            "name": "ethernet1/3",
                            "speed": "10000",
                            "st": "10000/full/up",
                            "state": "up",
                            "type": "0"
                        }
                    ]
                },
                "ifnet": {
                    "entry": [
                        {
                            "addr": null,
                            "addr6": null,
                            "dyn-addr": null,
                            "fwd": "N/A",
                            "id": "16",
                            "ip": "N/A",
                            "name": "ethernet1/1",
                            "tag": "0",
                            "vsys": "1",
                            "zone": null
                        },
                        {
                            "addr": null,
                            "addr6": null,
                            "dyn-addr": null,
                            "fwd": "N/A",
                            "id": "17",
                            "ip": "N/A",
                            "name": "ethernet1/2",
                            "tag": "0",
                            "vsys": "1",
                            "zone": null
                        },
                        {
                            "addr": null,
                            "addr6": null,
                            "dyn-addr": null,
                            "fwd": "N/A",
                            "id": "18",
                            "ip": "N/A",
                            "name": "ethernet1/3",
                            "tag": "0",
                            "vsys": "1",
                            "zone": null
                        }
                    ]
                }
            }
        }
    }
}

PLAY RECAP ************************************************************************************************
PA1                        : ok=7    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

</pre>
</details>

### ***Run mgmt_conf.yaml***

```
ansible-playbook mgmt_conf.yaml
```
Push management config.

<details>
<summary>Output</summary>
<pre>
PLAY [PaloAlto] *********************************************************************************

TASK [PaloAltoNetworks.paloaltonetworks : Install pan-python required library] ******************
ok: [PA1]

TASK [PaloAltoNetworks.paloaltonetworks : Install pandevice required library] *******************
ok: [PA1]

TASK [PaloAltoNetworks.paloaltonetworks : Install xmltodict required library] *******************
ok: [PA1]

TASK [Define login] *****************************************************************************
ok: [PA1]

TASK [set dns, ntp, and panorama but don't commit] **********************************************
changed: [PA1]

PLAY RECAP **************************************************************************************
PA1                        : ok=5    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

</pre>
</details>

***PA GUI***
![p1](https://user-images.githubusercontent.com/50756076/59163215-3c546180-8afe-11e9-8de8-5ab0ad58144f.jpg)

### ***Run int_conf.yaml***

```
ansible-playbook int_conf.yaml
```
Create management profile, zones, and interfaces.

<details>
<summary>Output</summary>
<pre>
PLAY [PaloAlto] *********************************************************************************

TASK [PaloAltoNetworks.paloaltonetworks : Install pan-python required library] ******************
ok: [PA1]

TASK [PaloAltoNetworks.paloaltonetworks : Install pandevice required library] *******************
ok: [PA1]

TASK [PaloAltoNetworks.paloaltonetworks : Install xmltodict required library] *******************
ok: [PA1]

TASK [Define login] *****************************************************************************
ok: [PA1]

TASK [Create management profile] ****************************************************************
changed: [PA1]

TASK [create zone] ******************************************************************************
changed: [PA1] => (item={u'zone': u'DMZ'})
changed: [PA1] => (item={u'zone': u'INSIDE'})
changed: [PA1] => (item={u'zone': u'OUTSIDE'})

TASK [Create interfaces] ************************************************************************
changed: [PA1] => (item={u'management_profile': u'PING', u'state': u'present', u'mode': u'Layer3', u'zone_name': u'OUTSIDE', u'ip': [u'193.254.247.58/24'], u'vr_name': u'default', u'if_name': u'ethernet1/1'})
changed: [PA1] => (item={u'management_profile': u'PING', u'state': u'present', u'mode': u'Layer3', u'zone_name': u'INSIDE', u'ip': [u'10.0.0.1/24'], u'vr_name': u'default', u'if_name': u'ethernet1/2'})
changed: [PA1] => (item={u'management_profile': u'PING', u'state': u'present', u'mode': u'Layer3', u'zone_name': u'DMZ', u'ip': [u'10.100.0.1/24'], u'vr_name': u'default', u'if_name': u'ethernet1/3'})

PLAY RECAP **************************************************************************************
PA1                        : ok=7    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

</pre>
</details>

***PA GUI***
![pa2](https://user-images.githubusercontent.com/50756076/59163393-dfa67600-8b00-11e9-8369-f4bd4cf30210.jpg)
