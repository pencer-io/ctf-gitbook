# Gobuster



Install:

```
apt-get install gobuster
```

Mode:

```
gobuster dns -d <target domain> -w <wordlist>
gobuster dir -u <target url> -w <wordlist>
gobuster vhost -u <target url> -w <wordlist>
```

File type:

```
gobuster dir -u <target url> -w <wordlist> -x .php
```

Ignore certificate errors:

```
gobuster dir -u <target url> -w <wordlist> -k
```

Specify cookie:

```
gobuster dir -u <target url> -w <wordlist> -c 'session=123456'
```
