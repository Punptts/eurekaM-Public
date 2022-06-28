uplinks:: [[Web3 MOC]]
tags:: #type/statement❖ #status/develop🔧

# A deeper look into HD Wallets
---
## Jot down...
### Blockchain wallets
**General info**
- Kept private key - not coin/money
- Owner of private key = owner of coin
- It is hardware and software device kept private key
- Its function - Manage and kept private key saftly
- Digital signature = use private key to sign -> transfer coin
**Type of wallets**
- By key location (About security)
	- Sofetware wallet
	- offline wallet
- By key generation
	- Nondeterministic wallet
	- Deterministic wallet
	- HD wallets
### The need for multiple keys
- Unlike bank acc... In blockchain, it is normal to have a hundred of keys and addresses. ***And why need multiple wallets?***
	- **Privacy**
		- Pseudonymous - unequal - Anonymous
		- Address reuse -> able to track back, harm privacy for yourself and also the seller.
	- **Security**
		- Key rotation - rotate to create more secure transaction
		- Risk Diversification
		- Access Control - some key able to use for something, diversify.
	- **Bitcoin** - a new key pair should be used for each transaction! to keep them from being linked to a common owner.
	- Gen key same as other even at the same time? -> based on math, its almost impossible... 
### Cryptographic Primitives & Math (like a lego to build crypto system)
- Modular Arithmetic
	- Computer don't do well with large number
	- Any calculation that result in a number larger than the max value = modulus gets wrapped.
	- Mod = 0-6 (estimate)
### Cryptographic hash function
- hash funciton = one-way function
	- input = (variable length) -> output = (fix-length value)
	- If we know output -> cannot calculate input
	- If we know input ->may not have the same output
	- SHA 256 = input variable length -> output 256
### Elliptic Curve (EC)
- Main property
	- Horizontal symmetric, whatever in x = y
	- any non-vertical = intersect atmost 3 dot
### Elliptic Curve Arithmetic
- Point addition
	- 2 point on elliptic curve - add them
	- Define "add" between point by draw a connect line.
	- Flip = get an integer
- Point Scalar (scalar = 123456)
	- Operation of adding a point along the curve
### Blockchain Keys and Addresses
- **Private key** = random positive integer (d) = eg. d=2022
- -- Point scalar multificatioon --
- **Public key** = dG (G = point on EC) 
	- A point on elliptical curve
	- The result of the point scalar multiplication of the privare key and based point G / eg. dG=2022G = add G to itself 2022 times
- -- Hash & Encode --
- **Address** = H(dG) = hash value of public key, human readable form
-
- Note - Cannot revert back to get private key
- Note - G value -> based point (public can see in google) / each blockchain have different G value.
- Note - G value -> not randomly selected, its already calculated
### ECC Composite Property (การรวม)
- There are 2 ways to gen public key C
	- 1. Private key A,B = Private key C -> gen public key C
	- 2. Public key A + B = Public key C
- C -> can calculate from  A and B also = Like A+B = C
- Can gen public key C without gen private key C ...?
- Advantage of gen **public key C** from more than 1 way
- ![[ECC Composite.png]]

## HD Wallets
### Non-deterministic wallet
General info
- First generation of Blockchain wallets
- Each private key is randomly and independently generate
- number of keys -> proportional -> to number of transactions
- // 1 key = 1 transaction - not necessary to reuse but first ui is force to create 1 key / transaction.
Problems
- High transaction = high cost // 1 key = 1 transaction 
	- Backup need to be done repeatedly
	- Backup storage size is proportional to transaction count
- Dose not support multiple device / share wallet
Early workarounds
- create a pool key inadvance to reduce backup interval

### Deterministic Wallet - have to remmber private key
- Wallet that derives private key through a key derivation function (KDF) from a seed (a large random secret value)
- All future key and addresses are determined in advance
- Mnumonic = 12 or 24 words (when create metamask wallet) this standard is known as BIP39
- Bakcup once - just the seed = backup everything in out wallet.
- 1 seed -> can create more than 1 address and private key (like metamask)

### Type-1 Deterministic Wallet - have to remember seed
- KDF = private key = H(i||seed||type) - 3 input
	- i = id (public and fix)
	- seed = seed
	- type = srting (for differentiate) public and fix
- Concept - 1 seed -> many keys
- Generate private key = ทำยังไงก็ได้ gen 0110 -> 256
Problem
- Know seed = all private key gone
- Wallet sharing still limited
	- only 2 option -> 1 share or 2 not share
	- Not much choice of access control
- Public key generate -> relies on private key

### Type-2: BIP32 HD Wallet
- BIP32 is the key generation standard for modern wallets / Metamask - wallets in nowsday use this concept.
- Originally -> Gregory Maxwell
- 2 kinds of Key Derivation
	- Nomal / soft / non-hardened
	- Hardened / Hard
- Concept of Chain code
	- Extended Private key = private key + chain code
	- Extended Public Key = publickey + chain code
	- Both use the same chain code

### BIP32 Normal Key Derivation
- Parent pub key able to generate Child
- ![[BIP-32 Normal Key Derivation.png]]

### BIP32 Normal Key Derivation
- Cannot use parent pub key to generate child

### Use case of Hierarchical Tree
Can be use to represent organizational structure
- Access control
- Easy back up key

### BIP32 Public Key Generatiion
- In order to gen pub key - no need to gen priv key first.
- So can generate pub key and use without priv key
- Use case
	- Read/receive only wallets
	- B2B transaction

### Problem with BIP32
- Can calculate parent priv key from child priv key

## CPK-based Wallets
- Algoritm for identity base and key management.
- Able to use in crypto system that have composite property. (ELiptic curve have this property so = able to use)
- Concept: Add on ( priv sequence / pub sequence )
- Concept - prive key add on together
- priv sequence (p)  (modular multiplication) with selector sequence (k) by multiple them eg. pk1, pk2,pk3 ... pk(n)
- Privacy depend on the length of the sequence, long = difficult to revert
- Index = help create many private or public key by using (id)
- The most imp in CPK is to use index to calculate keys
- About Access control - avoid write not leak

Key takeaway
- ![[HD wallets key takeaway.png]]

---
## References
- x
---
###### Note template
*I am the note template.*
	This reminds me of...
	It's kind of like...
	what is it...
	why does it matter...
	where did it come from...
	Freely write, say stuff, link things
Extracted from: [[2022-05-04-Wed]]