# Chapter 7 - Cryptography and the PKI

---
## Domain 1.0: General Security Concepts

**1.4. Explain the importance of using appropriate cryptographic solutions.**

- Public key infrastructure (PKI) (Public key, Private key, Key escrow)
- Encryption (Level (Full-disk, Partition, File, Volume, Database, Record), Transport/communication, Asymmetric, Symmetric, Key exchange, Algorithms, Key length)
- Obfuscation (Steganography)
- Hashing
- Salting
- Digital signatures
- Key stretching
- Blockchain
- Open public ledger
- Certificates (Certificate authorities, Certificate revocation lists (CRLs), Online Certificate Status Protocol (OCSP), Self-signed, Third-party, Root of trust, Certificate signing request (CSR) generation, Wildcard)

## Domain 2.0: Threats, Vulnerabilities, and Mitigations

**2.3. Explain various types of vulnerabilities.**

- Cryptographic

**2.4. Given a scenario, analyze indicators of malicious activity.**

- Cryptographic attacks (Downgrade, Collision, Birthday)

---

# An Overview of Cryptography

## Historical Cryptography

- **Cipher**
	- Scramble or obfuscate characters
	- Nonmathematical
		- Substitution
		- Transposition

### Substitution Ciphers

- Change one character or symbol into another
- Caesar cipher
	- Shift of three to the right

### ROT13

- ROT13 or "rotate13"
- Another simple substitution cipher

### Polyalphabetic Substitution

- Using multiple substitution alphabets
- Vigenère cipher

### Transposition Ciphers

- A message is **broke into blocks of equal size** and each block is then scrambled
- Columnar transposition is a classic example

### The Enigma Machine

- Polyalphabetic substitution
- Changing the substitution for each character of the message

### Stenography 

- Embed secret message within another file

>[!TIP] Stenography is the practice of using cryptographic techniques to embed or conceal secret messages within another file. It can be used to hide images, text, audio, video, and many other forms of digital content.

# Goals of Cryptography

- Confidentiality, Integrity, Authentication, Non-repudiation

## Confidentiality

- Ensures data remains private

>[!TIP] Data in transit is also commonly called data *on the wire*, referring to the network cables that carry data communications.

- Data at rest
	- Storage media
- Data in transit
	- Common way with the TLS protocol
- Data in use
	- Active memory

- **Obfuscation**
	- Intentionally difficult for humans to understand how code works

### Protecting Data at Rest with Different Levels of Encryption
### Encrypting Data on Disk

- **Full-disk encryption (FDE)**
	- All data on hard drive
	- OS and system files
- **Partition encryption**
	- Allow more flexibility
- **File-level encryption**
	- Specific file
- **Volume encryption**
	- Between partition and file-level encryption

### Encrypting Database Data

- **Transparent Data Encryption (TDE)**
	- Entire database
- **Column-level Encryption (CLE)**
	- Specifics columns
- **Record-level Encryption**
	- More granular
	- Shared environments

>[!TIP] Be sure you know the differences between the various encryption levels; Full-disk, Partition, File, Volume, Database, and Record.

## Integrity

- Data is not altered
- Protect alteration
- Digital signatures

## Authentication

- Verifies the claimed identity
- Challenge-response protocol

## Non-repudiation

- Provide assurance to the recipient that the message was originated by the sender
- Offered only by **public key**, or **asymmetric** cryptosystems 

# Cryptographic Concepts

## Cryptographic Keys

- Cryptographic algorithms rely on keys
	- Large binary number
- **Key space**
	- Range of value that are valid
- **Key length**
	- Number of binary bits

- **Cryptographic keys** are sometimes referred to as **cryptovariables**
- **Cryptography**
	- The art of creating and implementing secret codes and ciphers
- **Cryptoanalysis**
	- The study of methods to defeat codes and ciphers
- **Cryptology**
	- Cryptography and Cryptoanalysis
- **Cryptosystems**
	- Implementation of a code or cipher in hardware and software

### The Kerckhoffs' Principle

- A concept that makes algorithms known and public, allowing everyone to examine and test them

## Ciphers

- The algorithms used to perform encryption and decryption
- **Cipher suite**
	- Sets of ciphers and key lenght supported by a system
- **Block ciphers**
	- Operate on "chunks", or block
	- Apply encryption to an entire message block at the same time
	- Transposition ciphers or Columnar transposition ciphers
- **Stream ciphers**
	- One character or bit of a message at a time

# Modern Cryptography

## Cryptographic Secrecy

- Old
	- Hide the details of the algorithm from outsider
- New
	- Don't rely on secrecy of algorithms
	- Rely on the secrecy of one or more cryptographic keys

- The length of cryptographic key is extremely important
- Data Encryption Standard (DES)
	- 56-bit key
	- No longer secure
- Modern cryptographic systems
	- At least 128-bit key

## Symmetric Key Algorithms

- **Shared Secret Key**
	- To encrypt and decrypt
- **Symmetric** Key Cryptography
	- **Secret** Key Cryptography
	- **Private** Key Cryptography
- **Key exchange is a major problem**
- Not implement Non-repudiation
	- No way to prove where a given message originated
- Not scalable
- Key must be regenerated often
	- Each time a participant leaves the group, all key known by that participant must be discarded
- **Very fast**

## Asymmetric Key Algorithms

- **Asymmetric** Key Algorithms
	- **Public** Key Algorithms
- Each user has 2 keys
	- Public key
	- Private key
- **Public key encrypts** a message
	- Only the **corresponding Private key** can decrypt it, an vice versa
- Scalable
- Support for **Digital Signature**
	- Hashing then encrypt with private key
		- To verify decrypt with paired public key
- The addition of new users requires the generation of only one public-private key pair
- User can be removed easy
- Key regeneration is required only when a user's private key is compromised
- Provide confidentiality, integrity, authentication, non-repudiation
- Key exchange is a simple process
- No preexisting communication link needs to exist
- Slow speed

>[!TIP] Exam objective 1.4 calls out Asymmetric, Symmetric, Key exchange, Algorithms, and Key length.

| Symmetric                                    | Asymmetric                                                     |
| -------------------------------------------- | -------------------------------------------------------------- |
| Single shared key                            | Key pair sets                                                  |
| Out-of-band exchange                         | In-band exchange                                               |
| Not scalable                                 | Scalable                                                       |
| Fast                                         | Slow                                                           |
| Bulk encryption                              | Small blocks of data, digital signatures, digital certificates |
| Confidentiality, integrity                   | Confidentiality, integrity, authentication, non-repudiation    |
## Hashing Algorithms

- Message digests are summaries of a message's content (like a file checksum) produced by a hashing algorithm
- **Collision**
	- Where a hash function produces the same value for two different methods
	- Leads to the deprecation

# Symmetric Cryptography

- Data Encryption Standard (DES)
- Triple DES (3DES)
- Advanced Encryption Standard (AES)

## Data Encryption Standaard

- **DES**
	- No longer secure
- **3DES**
	- Same DES algorithm
		- 3 different times with 3 different keys
	- Now considered insecure

## Advanced Encryption Standard

- Wireless network security, Transport Layer Security (TLS), file/disk encryption...
- **Strong**
- Key sizes 128-bit, 192-bit, 256-bit
- Block size 128-bit

## Symmetric Key Management

- Creation, distribution, storage, destruction, recovery, and escrow of secret keys

### Creation and Distribution of Symmetric Keys

- Key exchange is one of the major problems
- **Offline Distribution**
	- Physical exchange
- **Public Key Encryption**
	- To set up an initial communication
		- Then switch from Public Key encryption to Secret Key encryption
- **Diffie-Hellman**
	- Key exchange algorithm

### Storage and Destruction of Symmetric Keys

- Never store an encryption key on the same system where encrypted data resides
- Split knowledge
	- Providing two different individuals with half of the key
- When a user leaves
	- No longer permitted access to material protected with that key
	- All encrypted material must be re-encrypted with the new key
	- Main reason organizations turn to a Asymmetric algorithms

### Key Escrow and Recovery

- **Key escrow**
	- Having a third party store a protected copy of the key for use in an emergency
- Key recovery policies
	- Specifies the circumstances under which a key may be retrieved from escrow and used without a user's knowledge

# Asymmetric Cryptography

- **Public Key cryptosystems** rely on pairs of keys assigned to each user
	- Public key
	- Private key
- Public key can be freely shared
- **Higher degree** of computational complexity 
- **Longer key**

## RSA

- Standard
- Based on the complexity of factoring large prime numbers

## Key Length

- Most important security parameter
- Trade-off of resources vs security

## Elliptic Curve

- Elliptic Curve Cryptography (ECC)
- Difficult mathematic problem
	- Known as the elliptic curve discrete logarithm problem
- Harder to solve than the RSA and Dieffe-Hellman

# Hash Functions

- Generate a unique output value
	- This **value** is commonly referred to as the **message digest**
- Message digest synonyms
	- Hash, hash value, hash total, CRC, fingerprint, checksum, and digital ID
- Input of any length
- Output fixed length
- Relatively easy to compute
- One-way (extremely hard to reverse)
- Secure hash is collision free

>[!TIP] Hash is a one-way cryptographic function that takes an input and generates a unique and repeatable output from that input. No two inputs should ever generate the same hash, and a hash should not be reversible so that the original input can be derived from the hash.

## SHA

- **Secure Hash Algorithm**
- **SHA-1**
	- 160-bit message digest
	- Processes 512-bit blocks
- **SHA-2**
	- **SHA-256**
		- 256-bit message digest
		- 512-bit block size
	- **SHA-224**
		- 224-bit message digest
		- 512-bit block size
	- **SHA-512**
		- 512-bit message digest
		- 1024-bit block size
	- **SHA-384**
		- 384-bit message digest
		- 1024-bit block size
- **SHA-3**
	- Same variants and hash lengths of SHA-2
	- More secure algorithm

## MD5

- Processes 512-bit block
- Subject to **collisions**

# Digital Signatures

- Use **hashing algorithm and asymmetric cryptography**
- Integrity, Authentication and non-repudiation
- Rely on **Public Key** cryptography and **hashing** 
- Also used for authenticate code distribution

- **Generate** a **Message digest** of the original **plain-text** message using an **hashing algorithm**
- **Encrypt** the **Message digest** using **Private key**
	- This encrypted message digest is the **Digital signature**
- Append **Digital signature** with original **plein-text**

- **Decrypt** using the paired **Public key**
- Using the same **hashing algorithm** 
	- To create a **Message Digest** to compare from the original **plein-text** 
- Compare the two **Message digest**

- To provide privacy need to add encryption to entire message (plain-text with message digest)

## HMAC

- Hash-Based Message Authentication Code
- Partial **Digital Signature**
	- **Integrity** 
	- Not Non-repudiation
- Combined with **Message Digest generation**, by using a **shared Secret key**
	- Only who know the key can generate or verify the Digital Signature
	- Suitable when Symmetric Key cryptography is appropriate
- Halfway between unencrypted use of a Message Digest and computationally expensive Digital Signature based on Public Key
### Which Key Should I Use?

- To encrypt a message, use the recipient's Public key
- To decrypt a message sent to you, use your Private key
- Digitally sign a message you are sending, use your Private key
- Verify the signature on a message sent by someone else, use the sender's Public key

# Public Key Infrastructure

- Public Key Infrastructure (KPI) hierarchy of trust relationships
	- These trusts permit combining **Asymmetric cryptography** with **Symmetric cryptography** along with **Hashing** and **Digital certificates**
		- Giving hybrid cryptography

## Certificates

- **Digital certificates** provide assurance that we are communicating with entities who truly are who they claim to be
	- Endorsed copies of an individual's Public key
- When users verify that a certificate was signed by a trusted **Certificate Authority (CA)**, they know that the Public key is legitimate
- International **standard X.509**
	- Version of X.509
	- Serial number (from the certificate creator)
	- Signature algorithm identifier
	- Issuer name
	- Validity period
	- Subject's Common Name (CN) (e.g., certmike.com)
	- Optionally contain Subject Alternative Names (SANs)
	- Subject's Public Key (the meat of the certificate)
- Providing assurance for the Public keys of
	- Computers/machines
	- Individual users
	- Email addresses
	- Developers (code-signing certificates)
- A certificate may include a **wildcard**

## Certificate Authorities

- **Certificate Authorities (CAs)**
- The organizations offer notarization services for Digital certificates
	- You must prove your identity to the satisfaction of the CA
- Certificates are only good as the trust placed in the CA
- **Registration authorities (RAs)** assist CA with verifying users' identities
- CA must carefully **protect** their own **private key** to preserve their trust relationships
	- Use an **offline CA** to protect their **root certificate**
		- The top-level certificate for their entire PKI that serves as the **root of trust** for all certificates
		- The **offline CA** uses the root certificate to create **intermediate CA** that serve as the **online CA**
			- Used to issue certificates on a routine basis
- The use of a series of intermediate CAs is known as **Certificate chaining**
	- Root certificate (Offline CA) -> Intermediate Certificates (Online CA) -> End-user Certificates
- CA do not need to be third-party
	- **Self-signed certificates** for internal use

## Certificate Generation and Destruction

### Enrollment

- **Enrollment**
	- Prove your identity to the CA
	- Provide them with your public key in the form of a **Certificate Signing Request (CSR)**
	- CA creates an **X.509** digital certificate
		- Containing you **identity information** and a copy of your **Public key**
	- CA digitally signs the certificate using their Private key
	- Provides you with a copy of your signed digital certificate
- Different types of certificates
	- **Domain Validation (DV)**
	- **Extended Validation (EV)**
		- Higher level of assurance

### Verification

- **Verify** the certificate
	- Checking the CA's digital signature using the CA's Public key
	- Check that's not revoked using
		- Certificate Revocation List (CRL)
		- Online Certificate Status Protocol (OCSP)
	- At this point, you may assume that the Public key listed in the certificate is authentic, provided that it satisfies the following requirements
		- The digital signature of the CA is authentic
		- You trust the CA
		- The certificate is not listed on a CRL/OCSP
		- The certificate actually contains the **data you are trusting**

- **Certificate pinning**
	- Instruct browsers to attach a certificate to a subject
	- The browser associates that site with their public key
	- This allows users or administrators to notice and intervene if a certificate changes unexpectedly

### Revocation

- The certificate was compromised
- The certificate was erroneously issued
- The details of the certificate changed
- The security association changed

- The revocation request grace period 
	- Is the maximum response time within which a CA will perform any requested revocation
	- Defined in the Certificate Practice Statement (CPS)
		- CPS states the practices a CA employs when issuing or managing certificates

- To verify the authenticity of certificates and identify revoked certificates
	- **Certificate Revocation Lists (CRL)**
		- Latency
	- **Online Certificate Status Protocol (OCSP)**
		- Real-time
		- End-users request
		- Using remote server
	- **Certificate Stapling**
		- Extension to the OCSP
		- Web server use signed and timestamped response from the OCSP
		- Without contact remote server

## Certificate Formats

| **Standard**                        | **Format** | **File extension(s)** |                   |
| ----------------------------------- | ---------- | --------------------- | ----------------- |
| Distinguished Encoding Rules (DER)  | Binary     | .der, .crt, .cer      | Most common       |
| Privacy Enhanced Mail (PEM)         | Text       | .pem, .crt            |                   |
| Personal Information Exchange (PIX) | Binary     | .pfx, .p12            | Common on Windows |
| P7B                                 | Text       | .p7b                  |                   |

# Asymmetric Key Management

- Choose algorithm in the public domain
- Keys sufficient **entropy**
	- Truly random
- Keep Private key secret
- Retire keys when they've served a useful file
- Backup keys
- Hardware security modules (HSMs)
	- Devices store and manage encryption keys

# Cryptographic Attacks

## Brute Force

- Trying every possible key

## Frequency Analysis

- Looking at the **blocks** of an encrypted message to determine if any **common patterns** exist
- Work only on the historical ciphers

## Known Plain Text

- Known plain text and cipher text 
	- To crack the key

## Chosen Plain Text

- Ciphertexts corresponding to a set of plain text
	- Attempt to derive the key used

## Related Key Attack

- Like a chosen plain text
	- Except the attacker can obtain ciphertexts encrypted under two different keys

## Birthday Attack

- Birthday theorem
	- **Paradox** to find collisions
	- Needs fewer attempts then brute force

## Downgrade Attack

- Used against secure communications such as TLS
	- In an attempt to get the user or system to **shift to less secure cryptographic modes**

>[!TIP] Be sure to understand the differences between downgrade attacks as well as the concept of collisions and birthday attacks, as these are specifically mentioned in the exam objectives!

## Hashing, Salting, and Key Stretching

- **Rainbow table**
	- Reverse hashed password value by precomputing the hashes of common passwords
	- Looking for matches
- **Salting**
	- Add random value before hashing
	- To prevent Rainbow table
- **Key stretching**
	- Used to create encryption keys from password
		- Algorithms such **PBKDF2**
		- Use thousands of iterations of salting and hashing

>[!TIP] Hashing, salting, and key stretching are all specifically mentioned in the exam objectives.

## Exploiting Weak Keys

- Weak key generation

## Exploiting Human Error

- Email sent using an encryption scheme, someone may send it in clear (unencrypted)
	- If a cryptanalyst gets both messages, decoding will be simplified
- Weak or deprecated algorithms 

# Emerging Issues in Cryptography

## Tor and the Dark Web

- **The Onion Router**
	- Routing traffic across the Internet using encryption and a set of relay nodes
	- Rely on **Perfect forward secrecy**
		- Layers of encryption prevent nodes in the relay chain from reading information
- Anonymous browsing and hosting 

## Blockchain 

- **Distributed and immutable open public ledger**
	- Nobody can tamper or destroy 
- Major application is cryptocurrency
	- Allowing tracking without centralized authority
- Property ownership records, track supply chains

## Lightweight Cryptography

- Specialized hardware to implement lightweight cryptography with little power consumption
- Specialized encryption hardware for low latency
- High resiliency requirements
	- Sender retain a copy until the recipient confirms the receipt and decryption

## Homomorphic Encryption

- Enables privacy-preserving computations
- Encrypts individuals' data while allowing computations directly on encrypted data
- Produces result that, when decrypted, match computations performed on plain-text data

## Quantum Computing

- Defeat cryptographic algorithms that depend on factoring large prime numbers
- Develop stronger cryptographic algorithms

# Exam Essentials

- **Understand the goals of cryptography.**
	- Confidentiality
	- Integrity
	- Authentication 
	- Non-repudiation

- **Explain the differences between symmetric and asymmetric encryption.**
	- Symmetric
		- Same shared **Secret key**
		- Mechanism to exchange these shared secret key
			- Diffie-Hellman algorithm
	- Asymmetric
		- Pair of key
			- Public key
				- Freely shared
			- Private key
				- Kept secret
		- Decrypted with other key from the same pair

- **Explain how digital signatures provide non-repudiation.**
	- **Hash** function to generate **Message digest** 
		- Then **encrypting** using own **Private key**
	- Decrypting using sender Public key
	- Comparing with Message digest computed by themselves

- **Understand the purpose and use of digital certificates.**
	- Trusted mechanism for sharing Public keys
	- Obtained from **Certificate Authorities (CAs)**
		- Applying Digital signature
	- Recipient of the Digital certificate
		- Can rely on the Public key
			- If trust the issuing CA

- **Demonstrate familiarity with emerging issues in cryptography.**
	- TOR 
		- Perfect forward secrecy to allow anonymous communication
	- Blockchain
		- Immutable distributed public ledger
		- Through use of cryptography

#cybersecurity 