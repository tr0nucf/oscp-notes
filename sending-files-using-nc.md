# sending files using nc

Receiving end:

```text
$ nc -l -p 1234 > out.file
```

Sending end:

```text
$ nc -w 3 [destination] 1234 < out.file
```

source: [https://nakkaya.com/2009/04/15/using-netcat-for-file-transfers/](https://nakkaya.com/2009/04/15/using-netcat-for-file-transfers/)

