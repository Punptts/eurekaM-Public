uplinks:: [[Web3 MOC]]
tags:: #type/thing❖ #status/develop🔧 #on/web3

# Cryptography
---
## Jot down...
### What is Cryptography?
- Cryptography is a study of secure communications technique that allow only sender and intended receiver to see the message.
- It is an act of transforming the ordinary text into Ciphertext (encryption) and again transforming it back to an ordinary text (decryption).

![[Basic Cryptography.png]]

### Symmetric Cryptography (Key encryption)
- Symmetric Cryptography is also known as secret key cryptography (a two-way process). This technique is a use of a single shared secret to share encrypted data between parties.
- *Use case:* Symmetric cryptography is useful for protecting data between parties and is also frequently used to store confidential data.
- *How's to:* the data encrypted using secret key, then send the encrypted message (Ciphertext) and secret key to the receiver and then they can use the secret key to decode the ciphertext.
- *Problem:* If the message is stealed by the third party, they have all resources to open the message. (Not secure)

And to solve the problem of Symmetric, the Asymmetric appear.

### Asymmetric Cryptography (Key Encryption)
- Asymmetric Cryptography is also known as public-key cryptography. This technique is a use of pairs keys. Each pairs consist of public key and private key. To encrypt message needs public key, and to get access to those message (decrypt) needs prive key.
- *Use case* : Asymmetric Cryptography is used in key exchange, email security, Web security, and other [encryption systems](https://www.sciencedirect.com/topics/computer-science/encryption-system "Learn more about encryption systems from ScienceDirect's AI-generated Topic Pages") that require key exchange over the public network.
- *How's to:* Unlike the normal [[#Symmetric Key Cryptography]]. It is encrypt and decrypt the data using seperate key. One key, the Public Key, is used for encryption and the other, the Private Key, is for decryption.
- *Problem:* The problem is that we cannot differentiate people who hold the public keys if it belong to more than one person. When people try to encrypt the message, they all use the same (copy) public key.

%%// How the two keys generated?%%

### Classical Cryptography (Technique)
In the olden days, there are two type of Classical Cryptography techniques that are use to encrypt the message,
1. [[Transposition Cryptography]]
2. [[Substitude Cryptography]]

Eventhough there are a lot of use cases that happend dusing the olden days but still there are many disadvantage behind such as,
- Require each paties to meet up in order to exchange the keys.
- The process is not secure enough, it is able to crack by human.

When the computer hit the world, there are a new version of cryptography which is known as [[Modern Cryptography]]. A Modern Cryptography development was based on the standard of Classical cryptography but in more secure and effective in keeping the data. The key: Modern Cyptography is actually a mixed of tranposition + substitution x (n time).

---
## References
- [Symmetric Cryptography](https://www.sciencedirect.com/topics/computer-science/symmetric-cryptography)
- [Classical Cryptography and Quantum Cryptography](https://www.geeksforgeeks.org/classical-cryptography-and-quantum-cryptography/)