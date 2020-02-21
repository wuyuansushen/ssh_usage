# sshkey_add_Server
A tutorial about how to add ssh key in server and how to use it connect to the server in client

1.Generate a pair of keys

 `ssh-keygen`
 
 Then,It will prompt you to write some information
 1.where this pair of keys will be saved
 2.Enter passphrase--empty for no passphrase.If you have written this,you need to fill in the password everytime when you connect to the server(Although you have the private key)
 
 At this,you have 2 files(`id_rsa.pub` and `id_rsa`) in `~/.ssh/` diretory
 
 
 2.Upload the public key to the server
 
  __You should know:In client,Its name is ssh;In Server,Its name is sshd!!!!!__
 
 You need to upload the `id_rsa.pub` and rename it to 'authorized_keys'
 That is means the content in `id_rsa.pub` should be in `~/.ssh/authorized_keys` at last.

# multi-authorized_keys

 0.You could add __many__ public keys in a server.

 1.The file `~/.ssh/authorized_keys` could include many keys.

***method:everyline include the content of a public key,That is OK!***

# Port setting difference between ***ssh*** and ***scp***

ssh: use `-p` to assign port

scp: use `-P` to assign port
