# HTTP/HTTPS 80/443/\*

## HTTP

### Nikto

Scan for web application vulnerability

```bash
nikto -h $TARGET_URL
```

### Gobuster

Brute force directories and files in websites.

```bash
gobuster -w /usr/share/seclists/Discovery/Web_Content/common.txt -u $TARGET_URL
```

## HTTPS

### sslscan

Check for OpenSSL HeartBleed

```bash
sslscan $TARGET_URL
```

## Web Applications

### PHP

Important information in `phpinfo()`

* DOCUMENT\_ROOT

### Wordpress

```bash
wpscan --url $TARGET_URL
```

