# Evil-WinRM

Standard connection with user and password, also use SSL:

```
┌──(root💀kali)-[~/htb/timelapse]
└─# evil-winrm -i 10.10.11.152 -u user123 -p 'password123' -S
```

Connect using certificate and private key, no user or password needed, use SSL:

```
┌──(root💀kali)-[~/htb/timelapse]
└─# evil-winrm -i 10.10.11.152 -c ./pfx.crt -k ./priv.key -p -u -S 
```
