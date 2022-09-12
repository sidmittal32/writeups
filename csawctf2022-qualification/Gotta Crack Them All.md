# Gotta Crack Them All
## Category
Cryptography
## Problem Description
As an intern in the security department, you want to show the admin what a major security issue there is by having all passwords being from a wordlist (even if it is one the admin created) as well as potential issues with stream ciphers. Here's the list of encrypted passwords (including the admin's), the encryption algorithm and your password. Can you crack them all and get the admin's password? Here is the web service that the admin made to encrypt a password: nc crypto.chal.csaw.io 5002<br>
NOTE: The flag is just the admin's password.
## Approach
I got my very own password in **leaked_password.txt**, Encrypting it at **nc crypto.chal.csaw.io 5002** I got the cyphertext ``b'kz\xc6\xb9\xd9Du\xcb\x8a\x9e\xe0\x9d\xbeo\xee\x03\xcf\xddd'``.<br>
According the [XOR cipher](https://en.wikipedia.org/wiki/XOR_cipher): plaintext ⊕ ciphertext = key.

```python
ciphertext = b'kz\xc6\xb9\xd9Du\xcb\x8a\x9e\xe0\x9d\xbeo\xee\x03\xcf\xddd'

def encrypt(plain):
	return b''.join((ord(x) ^ y).to_bytes(1,'big') for (x,y) in zip(plain,ciphertext))

encrypt("Cacturne-Grass-Dark")
```

I got the key: ``b'(\x1b\xa5\xcd\xac6\x1b\xae\xa7\xd9\x92\xfc\xcd\x1c\xc3G\xae\xaf\x0f'``.

Using the key on the file **encrypted_passwords.txt**.

```python
ciphertext = b'(\x1b\xa5\xcd\xac6\x1b\xae\xa7\xd9\x92\xfc\xcd\x1c\xc3G\xae\xaf\x0f'

def encrypt(plain):
	return b''.join((ord(x) ^ y).to_bytes(1,'big') for (x,y) in zip(plain,ciphertext))

file = open('/home/siddharth/Downloads/encrypted_passwords.txt','r', encoding='latin-1') 
plain = file.readlines()
i = 0
for x in plain:
	print(encrypt(plain[i]))
	i += 1
```

And voila!
## Flag
flag{1n53cu2357234mc1ph3}
