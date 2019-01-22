# linux interesting commands

find file owned by group
~~~
$ find / -group {group name}
~~~

find file owned by user
~~~
$ find / -user {user}
~~~

find world writeable files
~~~
$ find / -type f -perm -0222
~~~

find files modified in the last 24 hours
~~~
$ find / -mtime -1 -print -type f
~~~

List packages [Ubuntu/Debian]
~~~
$ dpkg -l
~~~

List packages [Redhat]
~~~
$ rpm -qa
~~~

