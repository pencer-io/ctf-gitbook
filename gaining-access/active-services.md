# Active Services

Look for active using systemctl and list-units:

```
jennifer@admirertoo:~$ systemctl list-units --type=service
UNIT                               LOAD   ACTIVE SUB     DESCRIPTION                                                       
apache2.service                    loaded active running The Apache HTTP Server                                            
apache2@opencats.service           loaded active running The Apache HTTP Server                                            
apparmor.service                   loaded active exited  Load AppArmor profiles                                            
console-setup.service              loaded active exited  Set console font and keymap                                       
cron.service                       loaded active running Regular background program processing daemon                      
dbus.service                       loaded active running D-Bus System Message Bus                                          
fail2ban.service                   loaded active running Fail2Ban Service                                                  
getty@tty1.service                 loaded active running Getty on tty1                                                     
hbase.service                      loaded active running HBase                                                             
ifup@eth0.service                  loaded active exited  ifup for eth0
```
