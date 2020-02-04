# SMTP 25

## NSE Script

Enuemerate commands and users on the target system.

```bash
nmap -p25 --script=smtp-commands,smtp-enum-users, $TARGET_IP
```

Scan for SMTP vulnerabilites.

```bash
nmap -p25 --script=smtp-vuln-cve2010-4344,smtp-vuln-cve2011-1720,smtp-vuln-cve2011-1764 $TARGET_IP
```



