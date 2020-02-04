# Port Redirection and Tunneling

## SSH Tunneling

### Local Port Forwarding

```text
ssh -L <local-port-to-listen>:<remote-host>:<remote-port> remote-host
```

### Remote Port Forwarding

```text
ssh -R <remote-port-to-listen>:<local-host>:<local-port> remote-host
```

### Dynamic Port Forwarding

```text
ssh -D <local-port-to-listen> <remote-host>
```

This command creates a SOCKS proxy listening at &lt;local-port&gt;. It is required to configure the browser to point to the SOCKS proxy at &lt;local-port&gt; to redirect all traffics to &lt;remote-host&gt;.

## Proxychains

Change proxy value to desired proxy server.

{% code title="/etc/proxychains.conf" %}
```text
# add proxy here ...
# meanwile
# defaults set to "tor"
socks4 	127.0.0.1 9050
```
{% endcode %}

#### Usage

```bash
proxychains nmap -Pn -sT -sV -p 445,446 $TARGET_IP
```

#### Metasploit Usage

1. Add route to a destined subnet through a session
2. Run socks4a server to listen traffics from proxychains

```bash
msf > route add 172.16.85.0 255.255.255.0 2
msf > use auxiliary/server/socks4a
```

## References

* [https://chamibuddhika.wordpress.com/2012/03/21/ssh-tunnelling-explained/](https://chamibuddhika.wordpress.com/2012/03/21/ssh-tunnelling-explained/)

