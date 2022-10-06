---
title: Creating SSH keys
date: 2022-10-06 13:00:00 -500
categories: [network,ssh]
tags: [network,ssh,authenticate]
---

There a multiple protocols to use when authenticating to Github:

* HTTPS
* SSH
* Github CLI

### Here we will use SSH protocol


[openSSH](https://www.ssh.com/academy/ssh/agent) is a implementation of the ssh protocol and runs on most linux systems, for windows users, [Putty](https://www.putty.org/) is most likely your best option. 

SSH is used for secure communications between two computers

#### Brief overview

> Secure Shell or SSH uses one Private and one Public key(key value pair). The public key can be distributed freely whilst the private key should be kept secure on your computer. When estableshing a connection using SSH both keys are being used. First of all the client(your computer, with your private key) creates a "sessionkey" and encrypts it with the private key. The sessionkey can only be decrypted with the pair's public key. Since the server should have your public key, the server should be able to decrypt the sessionkey, this way the server can be sure that you actually are you(or at least that someone with the private key is trying to connect to the server).

### Create your SSH keys
In the terminal of your linux machine, you first need to create a key-value-pair, this is simply done using the ssh-keygen command:

```bash
ssh-keygen
```
* You dont have to specify a file to where the key should be saved, just hit enter.
* When prompted for a passphrase(optional), enter your usual unsecure password, this is just an extra secure layer.

If you want to know how to create keys with different algorithm, checkout the [ssh docs](https://www.ssh.com/academy/ssh/keygen).


You're keys should be stored in the users home directory, in a hidden folder called ".ssh".

### Adding the private key to the ssh-agent
the ssh-agent is a small program that keep tabs on your keys and passphrases so you dont have to enter the passphrase each time you are connection over ssh to another computer.

```bash
ssh-add ~/.ssh/<name of you identification key/private key>
```
Enter you passphrase when prompted.

### Spread the public key
Now you should be all set. You can now copy your public key:

```bash
cat ~/.ssh/<yourkey.pub>
```

And add it the server you want to connect to.