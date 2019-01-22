# john

johntheripper

if you get errors... remember use jumbojohn (https://github.com/magnumripper/JohnTheRipper)


# Cracking Linux Passwords

if we have the shadow file and the passwd file we can use john's unshadow to combine them into one file:

~~~
$ unshadow passwd shadow > crackme
~~~

`john skips usernames without hashes, so you can leave them`

~~~
$ john --wordlist=/usr/share/wordlists/rockyou.txt crackme
~~~

john cracks the passwords simultaneously

# Cracking Encrypte SSH Keys

Example of Encrypted SSH Key:
![ssh key][/home/to/image]

Use SSH2John to convert the RSA key to john format:

~~~
$ /opt/JohnTheRipper/run/ssh2john.py id_rsa > crackme
~~~

~~~
$ /opt/JohnTheRipper/run/john --wordlist=/usr/share/wordlists/rockyou.txt --format=SSH crackme
~~~

