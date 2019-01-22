# tcpdump

Listen to Source IP:

```text
$ tcpdump src {IP}
```

Show traffic for protocol:

```text
$ tcpdump icmp
```

\(showing traffic that contains ping\)

Use AND \(&&\), OR \(\|\|\), EXCEPT\(!\) to group filters:

```text
$ tcpdump -i ppp0 src {IP} and icmp
```

\(Listen on interface ppp0 for source IP for ICMP traffic

