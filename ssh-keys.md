# SSH Keys

How to add your public SSH key to another host:

Create SSH key \(on your host\):

```text
$ ssh-keygen

Keys will be saved to
/home/yourusername/.ssh/id_rsa <- private key
/home/yourusername/.ssh/id_rsa.pub <- public key
```

1. Copy the contents of the public key \(id\_rsa.pub\)
2. Save the contents on the victim machine in the authorized\_keys file \(if it does not exist, create it\) authorized\_keys location:

   ```text
        /home/user/.ssh/authorized_keys

        root's authorized_keys location
        /root/.ssh/authorized_keys
   ```

Once the key is saved in the authorized\_keys, you will not need a password to sign in

Use your private key \(generated with the public key using ssh-keygen\) to sign in:

Make sure to update the correct key-permissions first:

```text
$ chmod 600 id_rsa
```

```text
$ ssh -i id_rsa user@host
```

\(The user is in whosever authorized\_keys you used to save the key\)

