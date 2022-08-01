# TCPDump

Sometimes it's useful to check connectivity back to us from within a box.

Start tcpdump listening on Kali:

```
tcpdump -i tun0
```

Ping Kali tun0 IP, method to do this will vary depending on box:

```
22:33:43.401625 IP kali.39206 > 10.10.10.8.http: Flags [.], ack 1744, win 276, options [nop,nop,TS val 2785576152 ecr 720506], length 0
22:33:43.402242 IP kali.39206 > 10.10.10.8.http: Flags [F.], seq 406, ack 1744, win 276, options [nop,nop,TS val 2785576153 ecr 720506], length 0
22:33:43.440371 IP 10.10.10.8.http > kali.39206: Flags [.], ack 407, win 257, options [nop,nop,TS val 720511 ecr 2785576153], length 0
```
