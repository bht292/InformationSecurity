# h5 Uryyb, Greb!
## Applied Crypographie Chapter 1

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

## a) Install OpenSSH server, connect to it using 'ssh' client.
I have already installed SSH for the bandit over the wire tasks. But the command would be:
```bash
sudo apt update && sudo apt install -y openssh-server
```
![Shell](screenshots/homework-05-a1.png)


## b) Automate SSH connection using public keys.
![Shell](screenshots/homework-05-b1.png)

![Shell](screenshots/homework-05-b2.png)

## c) Pretty Good indeed. 
Encrypt and decrypt a message with 'gnupg', using PGP public key cryptography. (Note that here you learn each step; for end users, you can often automate and make it look simple)
### Installation of GnuPG
![Shell](screenshots/homework-05-c1.png)
### Generation of Keypair pgp
![Shell](screenshots/homework-05-c2.png)
![Shell](screenshots/homework-05-c3.png)
![Shell](screenshots/homework-05-c4.png)

### Export and Import Siumlation of public key
![Shell](screenshots/homework-05-c5.png)

### Message encryption
![Shell](screenshots/homework-05-c6.png)

### Message decryption
![Shell](screenshots/homework-05-c7.png)

## d) Password manager, open and cloudless. 
Choose a password manager that 1) works without cloud 2) is free, open source sofware. 

### Install it
![Shell](screenshots/homework-05-d1.png)

### Demonstrate its use. 
Passwords can be stored in a password database securely. You dont have to remember them and can copy paste the passwords into the websites.
![Shell](screenshots/homework-05-d2.png)
![Shell](screenshots/homework-05-d3.png)
![Shell](screenshots/homework-05-d4.png)
![Shell](screenshots/homework-05-d5.png)

### Explain why a password manager is needed i.e. what kind of attacks or threats it protects against.
A password manager is essential for keeping your accounts secure. Without one, people tend to use weak passwords or reuse the same ones across multiple sites, making them easy targets for hackers. One major risk is password reuse attacks—if a hacker gets one password from a breached website, they can try it on other accounts. A password manager prevents this by storing a unique password for every account. Another threat is phishing, where fake websites trick users into entering their login details. 

Furthermore, it helps by autofilling only on real sites, so you don’t accidentally enter your credentials on a scam page. Keyloggers, which record everything typed on a keyboard, can steal passwords. Since a password manager auto-fills login details, it helps protect against keylogging attacks. Using long and complex passwords is one of the best defenses against brute force attacks, where hackers try millions of combinations to guess a password. A password manager generates and remembers strong passwords for you. It also solves the issue of forgotten passwords—instead of writing them down or resetting them constantly, you just remember one master password, and the manager securely stores the rest. 

In short, a password manager makes security easy and automatic. It protects against hacks, phishing, keyloggers, and weak passwords—so you stay safe online with minimal effort.

## o) Voluntary bonus:
Find out frequency distribution of letters for a language that you know (other than English). 
What are the six most common letters? (This subtask y does not require tests with a computer if the question can be answered without them)

The following table shows the approximate frequency of letters in the Spanish language:

| Rank | Letter | Frequency (%) |
|------|--------|--------------|
| 1    | **E**  | 13.72%       |
| 2    | **A**  | 11.72%       |
| 3    | **O**  | 8.44%        |
| 4    | **S**  | 7.20%        |
| 5    | **N**  | 6.83%        |
| 6    | **R**  | 6.41%        |

These percentages are from an analysis of a Spanish text comprising **2,129,690 characters** across various literary genres.

## References
PGP Knowlegde: https://terokarvinen.com/2023/pgp-encrypt-sign-verify/
o) voluntary bonus: https://www.sttmedia.com/characterfrequency-spanish
