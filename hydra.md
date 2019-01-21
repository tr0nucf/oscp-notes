# hydra

http POST-form cracking \(login forms\):

```text
hydra -l USERNAME -P /path/to/wordlist http-post-form “/login.php:username=^USER^&password=^PASS^:Login failed text”
```

http basic auth:

```text
hydra -l USERNAME -P /path/to/wordlist -f 127.0.0.1 http-get /pathtoauth
```

useful flags:

```text
-f = stop cracking after password is found
-I = skip restoring from previous session
-R = restore from previous session
```

