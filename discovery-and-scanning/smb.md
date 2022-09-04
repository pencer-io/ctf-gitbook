# SMB

Use nmap to enumerate smb shares:

```
nmap -p 445 --script=smb-enum-shares.nse,smb-enum-users.nse 10.10.102.194
```

Use smbmap to look around inside shares:

```
smbmap -H 10.10.102.194
```

Use smbclient to look around and get files we have access to:



```
smbclient //10.10.102.194/anonymous

smb: \> ls
  .                                   D        0  Thu Nov 26 16:04:00 2020
  ..                                  D        0  Tue Sep 17 08:20:17 2019
  attention.txt                       N      163  Wed Sep 18 04:04:59 2019
  logs                                D        0  Wed Sep 18 05:42:16 2019

smb: \> get attention.txt
getting file \attention.txt of size 163 as attention.txt (1.3 KiloBytes/sec)
```
