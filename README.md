# Simple script for mitigate DDoS.

+ Fast. 10Gb logfiles per seconds
+ Support netfilter (iptables) an Nginx access module
+ Support any flawor of GNU/Linux
+ Suitable for litle admins or operators.


# Usage

Fill main cycle with find credentials and add IP field in array `a[$1]++`

## Netfilter (iptables)
```
ddos_mitigate some.log | iptables-restore
```

### Or ever that (suitable for balancer):
```
ddos_mitigate some.log | ssh host sudo iptables-restore
```

## Nginx applicate:
```
ddos_mitigate -v ngx=1 some.log > /var/tmp/ddos_blacklist
```

### And add in nginx.conf:
```
include /var/tmp/ddos_blacklist;
```
