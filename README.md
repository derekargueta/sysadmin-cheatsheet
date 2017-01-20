# sysadmin-cheatsheet
personal notes on cool commands I find around the web


List all incoming ICMP echo requests (i.e. see real-time _incoming_ pings)

```bash
sudo tcpdump -i ethX icmp and icmp[icmptype]=icmp-echo
```
