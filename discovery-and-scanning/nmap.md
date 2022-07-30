# NMAP

Use nmap for initial scans:

```bash
ports=$(nmap -p- --min-rate=1000 -T4 10.10.10.24 | grep ^[0-9] | cut -d '/' -f 1 | tr '\n' ',' | sed s/,$//)

nmap -p$ports -v -sC -sV -oA haircut 10.10.10.24
```
