# sending files using nc

Receiving end:
~~~
$ nc -l -p 1234 > out.file
~~~

Sending end:
~~~
$ nc -w 3 [destination] 1234 < out.file
~~~

source: https://nakkaya.com/2009/04/15/using-netcat-for-file-transfers/

