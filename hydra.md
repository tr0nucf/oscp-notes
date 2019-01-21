# hydra

http post cracking \(login forms\):

~~~
hydra -l  -P   http-post-form “/login.php:username=^USER^&password=^PASS^:Login failed text”
~~~




