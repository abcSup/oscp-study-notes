# FTP 21

## NSE Script

Check if anonymous login is enabled

```text
nmap -p21 --script=ftp-anon $TARGET_IP
```

Scan for vulnerabilities

```text
nmap -p21 --script=ftp-libopie,ftp-proftpd-backdoor,ftp-vsftpd-backdoor,ftp-vuln-cve2010-4221 $TARGET_IP
```



