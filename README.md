# sysadmin-cheatsheet
personal notes on cool commands I find around the web


##### List all incoming ICMP echo requests
(i.e. see real-time _incoming_ pings)

```bash
sudo tcpdump -i ethX icmp and icmp[icmptype]=icmp-echo
```
where ethx is the device you want to listen to. Such as `en0`.

##### List all listening ports
```bash
lsof -Pni4 | grep LISTEN
```

##### Find out what DNS provider someone is using
```bash
dig NS <<<domain>>>
whois $(dig +short A <<<nameserver>>>) | fgrep Org
```
