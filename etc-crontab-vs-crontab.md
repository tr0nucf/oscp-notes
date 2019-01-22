# /etc/crontab vs crontab

# /etc/crontab

~~~
$ cat /etc/crontab
~~~

- Contains everything in one place
- Only root can edit
- Able to view which user is running what cron
- /etc/crontab is public, and readable by anyone

# crontab

Switches
~~~
-l = list
-e = edit
~~~

- Users are allowed to create their own cron jobs
- Only root can edit crontab for user
- Cron job is private unlike /etc/crontab

Cron is stored in:

~~~
/var/spool/cron/crontab/{user}
~~~

