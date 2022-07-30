# SNMP

SNMP uses UDP so can be missed by a normal nmap scan of TCP only, use -sU to check:

```bash
root@kali:~/htb/sneaky# nmap -sU 10.10.10.20
Starting Nmap 7.80 ( https://nmap.org ) at 2020-05-28 16:10 BST
Nmap scan report for 10.10.10.20
Host is up (0.023s latency).
Not shown: 999 closed ports
PORT    STATE SERVICE
161/udp open  snmp
```

If SNMP is open the use [snmpwalk](https://linux.die.net/man/1/snmpwalk):

```bash
root@kali:~/htb/sneaky# snmpwalk -c public -v2c 10.10.10.20
iso.3.6.1.2.1.4.34.1.8.2.16.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.1 = Timeticks: (0) 0:00:00.00
iso.3.6.1.2.1.4.34.1.8.2.16.222.173.190.239.0.0.0.0.2.80.86.255.254.185.18.18 = Timeticks: (3002) 0:00:30.02
iso.3.6.1.2.1.4.34.1.8.2.16.254.128.0.0.0.0.0.0.2.80.86.255.254.185.18.18 = Timeticks: (0) 0:00:00.00
```

Can see easier by filtering on just the IP-MIB 1.3.6.1.2.1.4.34.1.3:

```bash
root@kali:~/htb/sneaky# snmpwalk -c public -v2c 10.10.10.20 1.3.6.1.2.1.4.34.1.3
iso.3.6.1.2.1.4.34.1.3.1.4.10.10.10.20 = INTEGER: 2
iso.3.6.1.2.1.4.34.1.3.1.4.10.10.10.255 = INTEGER: 2
iso.3.6.1.2.1.4.34.1.3.1.4.127.0.0.1 = INTEGER: 1
```

More on IPv6/MIBS here: [https://pencer.io/ctf/ctf-htb-sneaky/#gaining-access](https://pencer.io/ctf/ctf-htb-sneaky/#gaining-access)
