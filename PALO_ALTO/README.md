
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
