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
dig +short ns <<<domain>>> | xargs -n1 dig +short | xargs -n1 whois | grep OrgName | tr -s ' ' | cut -c10- | sort -u
```

##### Determine what version of BIND a DNS server is using (if applicable)
```bash
dig -t txt -c chaos VERSION.BIND @<<<nameserver>>>
```

##### Count number of lines recursively in directory
```bash
find . -name '*.php' | xargs wc -l
```


##### Get plain diff with subset files
```bash
diff -ibwB --unchanged-line-format= --old-line-format= --new-line-format='%L' --suppress-common-lines file1 file2 > file2
```
file3 will only contain the items that are in file2 but not in file1 assuming that file1 is a sorted subset of file2
