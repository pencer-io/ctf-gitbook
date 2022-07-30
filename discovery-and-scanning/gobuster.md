# Gobuster



Install:

```bash
apt-get install gobuster
```

Mode:

```bash
gobuster dns -d <target domain> -w <wordlist>
gobuster dir -u <target url> -w <wordlist>
gobuster vhost -u <target url> -w <wordlist>
```

Examples:

```
gobuster -t 100 dir -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -u http://10.10.10.20
```

File type:

```bash
gobuster dir -u <target url> -w <wordlist> -x .php
```

Ignore certificate errors:

```bash
gobuster dir -u <target url> -w <wordlist> -k
```

Specify cookie:

```bash
gobuster dir -u <target url> -w <wordlist> -c 'session=123456'
```
