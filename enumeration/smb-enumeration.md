# SMB 139/443

## enum4linux

A wrapper that enumerates all kind of information using `smbclient`, `rpclient`, `net` and `nmblookup`.

```bash
enum4linux $TARGET_IP
```

## NSE Script

Scan for SMB vulnerabilities.

```bash
nmap -p139,445 --script=smb-vuln-* $TARGET_IP --open
```

## smbver.sh Script

Check SMB version because sometimes `enum4linux` does not show it.

{% code title="smbver.sh" %}
```text
#!/bin/sh
#Author: rewardone
#Description:
# Requires root or enough permissions to use tcpdump
# Will listen for the first 7 packets of a null login
# and grab the SMB Version
#Notes:
# Will sometimes not capture or will print multiple
# lines. May need to run a second time for success.
if [ -z $1 ]; then echo "Usage: ./smbver.sh RHOST {RPORT}" && exit; else rhost=$1; fi
if [ ! -z $2 ]; then rport=$2; else rport=139; fi
tcpdump -s0 -n -i tap0 src $rhost and port $rport -A -c 7 2>/dev/null | grep -i "samba\|s.a.m" | tr -d '.' | grep -oP 'UnixSamba.*[0-9a-z]' | tr -d '\n' & echo -n "$rhost: " &
echo "exit" | smbclient -L $rhost 1>/dev/null 2>/dev/null
sleep 0.5 && echo ""
```
{% endcode %}

## References

* [https://0xdf.gitlab.io/2018/12/02/pwk-notes-smb-enumeration-checklist-update1.html](https://0xdf.gitlab.io/2018/12/02/pwk-notes-smb-enumeration-checklist-update1.html)



