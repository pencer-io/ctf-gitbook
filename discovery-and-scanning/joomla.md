# Joomla

Scan Joomla sites with joomscan to look for vulnerabilities:

```bash
root@kali:/home/kali/thm/bugle# joomscan -u http://10.10.96.177
    ____  _____  _____  __  __  ___   ___    __    _  _
   (_  _)(  _  )(  _  )(  \/  )/ __) / __)  /__\  ( \( )
  .-_)(   )(_)(  )(_)(  )    ( \__ \( (__  /(__)\  )  (
  \____) (_____)(_____)(_/\/\_)(___/ \___)(__)(__)(_)\_)
                        (1337.today)

    --=[OWASP JoomScan
    +---++---==[Version : 0.0.7
    +---++---==[Update Date : [2018/09/23]
    +---++---==[Authors : Mohammad Reza Espargham , Ali Razmjoo
    --=[Code name : Self Challenge
    @OWASP_JoomScan , @rezesp , @Ali_Razmjo0 , @OWASP

Processing http://10.10.96.177 ...
[+] FireWall Detector
[++] Firewall not detected
[+] Detecting Joomla Version
[++] Joomla 3.7.0
[+] Core Joomla Vulnerability
[++] Target Joomla core is not vulnerable
[+] Checking Directory Listing
[++] directory has directory listing :
http://10.10.96.177/administrator/components
http://10.10.96.177/administrator/modules
http://10.10.96.177/administrator/templates
http://10.10.96.177/images/banners

[+] Checking apache info/status files
[++] Readable info/status files are not found
[+] admin finder
[++] Admin page : http://10.10.96.177/administrator/
```
