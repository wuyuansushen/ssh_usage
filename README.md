# sshkey usage
A tutorial about how to add ssh key in server and how to use it connect to the server in client

1.Generate a pair of keys

 `ssh-keygen`
 
 Then,It will prompt you to write some information
 1.where this pair of keys will be saved
 2.Enter passphrase--empty for no passphrase.If you have written this,you need to fill in the password everytime when you connect to the server(Although you have the private key)
 
 At this,you have 2 files(`id_rsa.pub` and `id_rsa`) in `~/.ssh/` diretory
 
 >:warning: Set permission `0600` to file `~/.ssh/authorized_keys`
 
 2.Upload the public key to the server
 
  __You should know:In client,Its name is ssh;In Server,Its name is sshd!!!!!__
 
 You need to upload the `id_rsa.pub` and rename it to 'authorized_keys'
 That is means the content in `id_rsa.pub` should be in `~/.ssh/authorized_keys` at last.

# multi-authorized_keys

 0.You could add __many__ public keys in a server.

 1.The file `~/.ssh/authorized_keys` could include many keys.

***method:everyline include the content of a public key,That is OK!(Warning:This method is not useful for private key file,such as `id_rsa`.You should use `ssh/scp -i [file_name]` to assign private key to connect when you have two or more private keys!)***

# Port setting difference between ***ssh*** and ***scp***

ssh: use `-p` to assign port

scp: use `-P` to assign port

# Use in Termux(Android for Linux emulator)

Permissions of the private key must be 400,either the `ssh` will ignore it for safe when you use `ssh` to servers 

# Use *~/.ssh/config* to simplify your connection operation

## Template:
```
	Host <shortAlias>
		HostName < IP | FQDN >
		Port <portNumber>
		User <loginUser>
```
