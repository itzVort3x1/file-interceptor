# File-interceptor

This will allow you inject code or even fake download file for the user.
Since this stores packets in the queue. You will need these command to forward traffic.
1. `iptables -I INPUT -j NFQUEUE --queue-num 0`
2. `iptables -I OUTPUT -j NFQUEUE --queue-num 0`

To remove these queing tables use: `iptables --flush`

In MITM to maintan connectivity for the client run: `echo 1 > /proc/sys/net/ipv4/ip_forward`. 

This will ensure there is no drop of internet connectivity for the client.
