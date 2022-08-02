# SSH Port Forwarding

Also known as tunnelling. Can use it to access services on a box that we can do from a command line. Like the box has a webserver running and we need a web browser so we tunnel from Kali to the box. Then we can use our local Kali web browser to view content on the box.

For example:

```
ssh -L 10000:localhost:10000 agent47@10.10.42.137
```

Here we are sending any traffic going to port 10000 on Kali through the SSH tunnel to port 10000 on the box at IP 10.10.42.137.&#x20;
