# SSH Keys

How to add your public SSH key to another host:

Create SSH key (on your host):
~~~
$ ssh-keygen

Keys will be saved to
/home/yourusername/.ssh/id_rsa <- private key
/home/yourusername/.ssh/id_rsa.pub <- public key

~~~

2. Copy the contents of the public key (id_rsa.pub)

3. Save the contents on the victim machine in the authorized_keys file (if it does not exist, create it)
	authorized_keys location:
		~~~
		/home/user/.ssh/authorized_keys
		~~~
	root's authorized_keys location
		~~~
		/root/.ssh/authorized_keys
		~~~

Once the key is saved in the authorized_keys, you will not need a password to sign in


Use your private key (generated with the public key using ssh-keygen) to sign in:

Make sure to update the correct key-permissions first:

~~~
$ chmod 600 id_rsa
~~~

~~~
$ ssh -i id_rsa user@host
~~~

(The user is in whosever authorized_keys you used to save the key)


