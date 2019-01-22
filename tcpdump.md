# tcpdump

Listen to Source IP:
~~~
$ tcpdump src {IP}
~~~

Show traffic for protocol:
~~~
$ tcpdump icmp


ping in this example
~~~

Use AND (&&), OR (||), EXCEPT(!) to group filters:

~~~
$ tcpdump -i ppp0 src {IP} and icmp

Listen on interface ppp0, for certain source ip for icmp traffic
~~~

