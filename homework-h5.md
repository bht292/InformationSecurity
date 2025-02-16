# h5 Uryyb, Greb!
## Appliec Crypographie Chapter 1

## PGP - Send Encrypted and Signed Message
The protocol PGP (pretty good privacy) is used to send encrypted messages in order to protect the exchanged data.
In order to set that up the following key steps are required

### PGP Encryption, Signing and Verification with GPG
GPG has to be installed along with useful tools like `micro` (a lightweight text editor) and `killall` from `psmisc`. After installation, a **GPG key pair** is generated using:
```bash
gpg --gen-key
```

### Exporting the Public Key
Once the key pair is generated, the **public key** needs to be exported so others can encrypt messages:

```bash
gpg --export --armor --output bob.pub
```

This creates a file `bob.pub`, which is shared with Alice.

### Simulating Alice’s Environment
To properly test encryption, a **separate environment** is created for Alice. A new directory is set up, and permissions are adjusted:

```bash
mkdir alice_home  
chmod 700 alice_home  
```

Inside this directory, Alice generates her own GPG key pair:

```bash
gpg --homedir alice_home --gen-key  
```

### Importing Public Keys
Alice imports Bob’s public key (`bob.pub`) to her keyring, allowing her to send encrypted messages:

```bash
gpg --homedir alice_home --import bob.pub  
```

To confirm the key's authenticity, its fingerprint is verified.

### Encrypting and Signing a Message
A message is written and saved as `message.txt`. To ensure security, it is **encrypted and signed** using Bob’s public key:

```bash
gpg --homedir alice_home --encrypt --sign --armor --output message.asc --recipient "Bob DEMO KEY" message.txt  
```
This produces an **ASCII-armored** encrypted file `message.asc`, which Alice sends to Bob.

### Decrypting and Verifying the Message
Upon receiving `message.asc`, Bob decrypts and verifies it using:

```bash
gpg --decrypt message.asc  
```

If the encryption and signature are valid, the original message is displayed on the screen with a confirmation that the signature is verified.

---

This process ensures that messages remain **securely encrypted and authenticated**. Once the setup is complete, encrypted and signed communication can continue securely between Alice and Bob.
