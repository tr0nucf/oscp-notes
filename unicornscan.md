# unicornscan

unicornscan full tcp portscan:

```text
$ unicornscan -Iv -r 160 -mT IP:a

-Iv = Immediately display results as they are found (-v = verbose)
-r = Rate of packets to send per second
-mT = mode TCP
IP = host ip
a = all (Scan 65535 ports)
```

`for udp, change -mT to -mU`

in action: [https://ch4n3l.github.io/writeups/blacklight-writeup/](https://ch4n3l.github.io/writeups/blacklight-writeup/)

