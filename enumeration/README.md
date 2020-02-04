# Scanning & Enumeration

## Host Discovery

```bash
netdiscover -i eth0
```

```bash
nmap -sN 192.168.1.0/24
```

## Port Discovery

```bash
nmap -sS $TARGET_IP -oA $OUPUT_FILE
nmap -Pn 192.168.0.10-12 -oA $OUPUT_FILE
```

```bash
unicornscan $TARGET_IP:a
```

## Service Identification

```text
nmap -sV 192.168.20.10-12 -oA $OUPUT_FILE
```

