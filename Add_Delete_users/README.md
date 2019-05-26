
# ***Topology for add/delete users***

![topology_ansiblet1](https://user-images.githubusercontent.com/50756076/58367722-a2c46780-7ee2-11e9-83c0-2cfe1c9e01cd.jpg)

## Add users

### ***Run add_users_v1.yaml (run as user cisco and ask for password)***
```
ansible-playbook add_users_v1.yaml -u cisco -k
```
<details>
<summary>Output</summary>
<pre>

PLAY [Routers] *******************************************************************************************************************

TASK [Add users cli] *************************************************************************************************************
changed: [R10]
changed: [R4]
changed: [R1]
changed: [R7]
changed: [R2]
changed: [R3]
changed: [R8]
changed: [R5]
changed: [R9]
changed: [R6]

TASK [Show users] ****************************************************************************************************************
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

TASK [debug] *********************************************************************************************************************
ok: [R7] => {
    "user.stdout_lines": [
        [
            "username cisco privilege 15 secret 5 $1$JhMs$md2lzXu6XVeRCpqf7Fkxj0",
            "username krzys privilege 15 secret 5 $1$xPEr$L0/2HtroxrIx/pKhRbfQe1",
            "username maciek privilege 15 secret 5 $1$4J4C$WHvkmpho/OFJ3eejotrUE1",
            "username adam privilege 15 secret 5 $1$4kcA$9Nj/hsXSrvrRLWu47KLLQ0",
            "username ola privilege 15 secret 5 $1$C4dh$jxEbth2oaH.1NYdFf6jSl."
        ]
    ]
}
ok: [R2] => {
    "user.stdout_lines": [
        [
            "username cisco privilege 15 secret 5 $1$OM/E$VswczdJwbqvFfLcthiGaA0",
            "username krzys privilege 15 secret 5 $1$dhWR$4sIbkz011mAEcZ95KY5yY1",
            "username maciek privilege 15 secret 5 $1$F3at$LFjRc5GkhkN5yuYwiTNWA0",
            "username adam privilege 15 secret 5 $1$jGX.$H6ULOfv5PeDHvJSv1DSfZ0",
            "username ola privilege 15 secret 5 $1$CO5v$.2cfE63OjszLvUUrRSyVh."
        ]
    ]
}
ok: [R10] => {
    "user.stdout_lines": [
        [
            "username cisco privilege 15 secret 5 $1$eZ7H$Q.5UxpjUWNDKZde3mdhO/0",
            "username krzys privilege 15 secret 5 $1$EGF2$IqRapRvy1LA8kqalPSfBG/",
            "username maciek privilege 15 secret 5 $1$YEVV$5QKwo/MdKxDU2csvdp4.f.",
            "username adam privilege 15 secret 5 $1$pTnX$4Fr5UJIr8.Pby5mlJAusu0",
            "username ola privilege 15 secret 5 $1$A/P7$8vOH2txw/ZzOMB8E2/67q0"
        ]
    ]
}
ok: [R1] => {
    "user.stdout_lines": [
        [
            "username cisco privilege 15 secret 5 $1$jlv/$wuFQnbRy0H.IKbFKHMM2p0",
            "username krzys privilege 15 secret 5 $1$vHcT$mU6WY7HNauJUW5jeXkZXl1",
            "username maciek privilege 15 secret 5 $1$w/Xj$ZcO0jcYm09UDNxTHwWHSO.",
            "username adam privilege 15 secret 5 $1$91x8$Lwe5HG3kLn3qQtHorRtuX/",
            "username ola privilege 15 secret 5 $1$WP7r$h8hKRJxik41ECYNidIh/4."
        ]
    ]
}
ok: [R4] => {
    "user.stdout_lines": [
        [
            "username cisco privilege 15 secret 5 $1$DHza$H4oU0u./egj/KzgYJvr0f0",
            "username krzys privilege 15 secret 5 $1$JzHh$rTN1PWn77rvbMhe4o/hy60",
            "username maciek privilege 15 secret 5 $1$FGtj$wVh3GTqAFK0BuH5q7oTmu/",
            "username adam privilege 15 secret 5 $1$2G90$hfdh96.pkVgOuxG6cW95R1",
            "username ola privilege 15 secret 5 $1$9kH5$0r4ibC2YM6cKH4XCAAOOZ1"
        ]
    ]
}
ok: [R8] => {
    "user.stdout_lines": [
        [
            "username cisco privilege 15 secret 5 $1$yO1.$MgFUekXeDqii/gEaBn2CY.",
            "username krzys privilege 15 secret 5 $1$/3/9$1XFGPp9vKd3MfASGexNGw1",
            "username maciek privilege 15 secret 5 $1$HmUQ$AQJhqwQdh9ymMZpbQGH4E.",
            "username adam privilege 15 secret 5 $1$5n8g$e.Nu3HOqchn2k3FgdSCLS/",
            "username ola privilege 15 secret 5 $1$/OiD$/4cLoSsjluAKJ7kX2xD0S/"
        ]
    ]
}
ok: [R3] => {
    "user.stdout_lines": [
        [
            "username cisco privilege 15 secret 5 $1$HDq2$f29x7e9ll.pyz9hjX2Z780",
            "username krzys privilege 15 secret 5 $1$EAdo$BtUCQYkiB6rlzAzifdQ0Z0",
            "username maciek privilege 15 secret 5 $1$dKQq$AULAqYHwC/Jjmqe9K/W8o0",
            "username adam privilege 15 secret 5 $1$XXit$PqZtPEk1C7/z7Tb4yp.RS.",
            "username ola privilege 15 secret 5 $1$me7w$DkN1qNlWIl.7qtqzYrzXH/"
        ]
    ]
}
ok: [R9] => {
    "user.stdout_lines": [
        [
            "username cisco privilege 15 secret 5 $1$0bV9$xDMQTI4dExOAGGqgzXQlH1",
            "username krzys privilege 15 secret 5 $1$drGJ$MvMU0DBJ.q/g2YnLw/NZp/",
            "username maciek privilege 15 secret 5 $1$Lk9d$/rMwpOl67/PG5ftKXWi8B0",
            "username adam privilege 15 secret 5 $1$YPAR$CfGnkTUjCxHnEKLKNgR1B/",
            "username ola privilege 15 secret 5 $1$pERu$qTcXsylA95fgbwFPdnSn7."
        ]
    ]
}
ok: [R6] => {
    "user.stdout_lines": [
        [
            "username cisco privilege 15 secret 5 $1$THAT$mLkSL8YaedYLY9to53PCf/",
            "username krzys privilege 15 secret 5 $1$0AEa$QQgDlO9mHm3TjHXWUVah.1",
            "username maciek privilege 15 secret 5 $1$w8uw$E5auK4sjWoqsyqPkWmNn2/",
            "username adam privilege 15 secret 5 $1$HumZ$I0oFDe2mVWqrHOcHKRIYl1",
            "username ola privilege 15 secret 5 $1$.PmB$GoqzDm1Glw9B5hVgUk8He0"
        ]
    ]
}
ok: [R5] => {
    "user.stdout_lines": [
        [
            "username cisco privilege 15 secret 5 $1$/Flb$0INw3P4/rIsWgp1feJnJo/",
            "username krzys privilege 15 secret 5 $1$BEq8$rRCf2TahEv7Va1lzBcbEE1",
            "username maciek privilege 15 secret 5 $1$yrA.$8ORI7kyLX5SmReir3MYhT1",
            "username adam privilege 15 secret 5 $1$nnTH$lV8MizjLY3lJn.44l5bIV1",
            "username ola privilege 15 secret 5 $1$Q865$PdlEqmPtGvB8TKnfhkjj/1"
        ]
    ]
}

TASK [Save running-config] *******************************************************************************************************
changed: [R10]
changed: [R4]
changed: [R1]
changed: [R2]
changed: [R7]
changed: [R3]
changed: [R5]
changed: [R8]
changed: [R6]
changed: [R9]

TASK [Compare startup to running-config] *****************************************************************************************
ok: [R10]
ok: [R4]
ok: [R1]
ok: [R7]
ok: [R2]
ok: [R8]
ok: [R3]
ok: [R9]
ok: [R5]
ok: [R6]

PLAY RECAP ***********************************************************************************************************************
R1                         : ok=5    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R10                        : ok=5    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R2                         : ok=5    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R3                         : ok=5    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R4                         : ok=5    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R5                         : ok=5    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R6                         : ok=5    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R7                         : ok=5    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R8                         : ok=5    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
R9                         : ok=5    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

</pre>
</details>
