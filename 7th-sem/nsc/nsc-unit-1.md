# UNIT 1: Introduction to Cryptography

**Course:** PEC-CSE-411G | **Author:** [Deepak Modi](https://deepakmodi.tech)

**Syllabus:**  
Plain text and cipher text, substitution techniques, transposition techniques, encryption and decryption, symmetric and asymmetric key cryptography.

---

## **PYQ Priority Analysis**

### **High Priority Topics** (15 marks questions)
1. **Substitution Techniques** - Asked 3 times (Feb-22: 10 marks, May-23: 10 marks, 2024: 15 marks)
2. **Symmetric vs Asymmetric Key Cryptography** - Asked 2 times (2024: 15 marks each)
3. **Encryption and Decryption** - Asked 2 times (May-23: 8 marks, 2024: 15 marks)
4. **Transposition Techniques** - Asked 2 times (Feb-22: 5 marks, Dec-22: 8 marks)

### **Medium Priority Topics** (Short answers: 2.5 marks)
1. **Plain text and Cipher text** - 2024
2. **Feistel Cipher** - Feb-22
3. **Avalanche effect** - Feb-22
4. **Product cipher** - Dec-22
5. **Homophonic Substitution Cipher** - Dec-22
6. **Cryptanalysis** - May-23
7. **Rail-Fence Technique** - May-23

### **Important Algorithms**
- **Diffie-Hellman Key Exchange** - May-23 (7 marks)
- **Fermat and Euler's theorem** - Feb-22 (7 marks)

---

## **1. Basic Concepts**

> PYQ: Define plain-text and cipher-text. How are they related in encryption? (2024, 2.5 marks)

### 1.1 Plain Text and Cipher Text

**Plain Text** is the original readable message or data that needs to be protected. It is the input to an encryption algorithm and can be understood by anyone who reads it. Plain text can be text files, emails, passwords, or any form of data that needs to be kept confidential.

**Cipher Text** is the scrambled, unreadable output produced after applying an encryption algorithm to plain text. It appears as random gibberish to anyone who does not have the decryption key. The purpose of converting plain text to cipher text is to ensure that even if the data is intercepted during transmission, it cannot be understood without the proper decryption mechanism.

**Relationship in Encryption:**
```
Plain Text ──[Encryption Algorithm + Key]──> Cipher Text
Cipher Text ──[Decryption Algorithm + Key]──> Plain Text
```

### 1.2 Cryptography

**Cryptography** is the science and art of keeping information secure by transforming it into an unreadable format. It involves techniques for secure communication in the presence of adversaries, ensuring confidentiality, integrity, authentication, and non-repudiation. The word cryptography comes from Greek words "kryptos" (hidden) and "graphein" (writing), literally meaning "hidden writing."

### 1.3 Cryptanalysis

> PYQ: Cryptanalysis (May-23, 2.5 marks)

**Cryptanalysis** is the science of breaking cryptographic systems and recovering the plain text or key without having authorized access. It involves analyzing encryption algorithms to find weaknesses that can be exploited. Cryptanalysis techniques include brute force attacks, frequency analysis, known-plaintext attacks, chosen-plaintext attacks, and differential cryptanalysis.

**Types of Cryptanalytic Attacks:**
- **Ciphertext-only attack**: Attacker has only cipher text
- **Known-plaintext attack**: Attacker has some plaintext-ciphertext pairs
- **Chosen-plaintext attack**: Attacker can choose plaintexts and get corresponding ciphertexts
- **Chosen-ciphertext attack**: Attacker can choose ciphertexts and get corresponding plaintexts

---

## **2. Encryption and Decryption**

> PYQ: Encryption and Decryption with examples. (May-23, 8 marks)      
> PYQ: Describe the process of symmetric key cryptography and explain the role of encryption and decryption keys in the process. (2024, 15 marks)

### 2.1 What is Encryption?

**Encryption** is the process of converting plain text into cipher text using an encryption algorithm and a key. The purpose is to protect sensitive information from unauthorized access during storage or transmission. Only authorized parties with the correct decryption key can convert the cipher text back to its original form.

**Encryption Process:**
```
┌─────────────┐     ┌──────────────────┐     ┌─────────────┐
│  Plain Text │────>│   Encryption     │────>│ Cipher Text │
│   (Input)   │     │   Algorithm      │     │  (Output)   │
└─────────────┘     └────────┬─────────┘     └─────────────┘
                             │
                        ┌────▼────┐
                        │   Key   │
                        └─────────┘
```

### 2.2 What is Decryption?

**Decryption** is the reverse process of encryption, where cipher text is converted back to plain text using a decryption algorithm and the appropriate key. Only authorized users who possess the correct key can decrypt the cipher text and access the original information.

**Decryption Process:**
```
┌─────────────┐     ┌──────────────────┐     ┌─────────────┐
│ Cipher Text │────>│   Decryption     │────>│  Plain Text │
│   (Input)   │     │   Algorithm      │     │  (Output)   │
└─────────────┘     └────────┬─────────┘     └─────────────┘
                             │
                        ┌────▼────┐
                        │   Key   │
                        └─────────┘
```

### 2.3 Example: Caesar Cipher

**Encryption Example:**
- Plain Text: "HELLO"
- Key: Shift by 3
- Encryption: Each letter shifted 3 positions forward
  - H → K, E → H, L → O, L → O, O → R
- Cipher Text: "KHOOR"

**Decryption Example:**
- Cipher Text: "KHOOR"
- Key: Shift by 3
- Decryption: Each letter shifted 3 positions backward
  - K → H, H → E, O → L, O → L, R → O
- Plain Text: "HELLO"

---

## **3. Symmetric Key Cryptography**

> PYQ: Describe the process of symmetric key cryptography and explain the role of encryption and decryption keys in the process. (2024, 15 marks)      
> PYQ: Problem of key distribution in symmetric cryptography. (Dec-22, 7 marks)

### 3.1 What is Symmetric Key Cryptography?

**Symmetric Key Cryptography** is an encryption method where the same key is used for both encryption and decryption. Both the sender and receiver must possess the same secret key and keep it confidential. This approach is also called secret-key cryptography or private-key cryptography. It is faster and more efficient than asymmetric cryptography, making it suitable for encrypting large amounts of data.

**Process:**
```
Sender Side:                          Receiver Side:
┌─────────────┐                      ┌─────────────┐
│  Plain Text │                      │ Cipher Text │
└──────┬──────┘                      └──────┬──────┘
       │                                    │
       │  ┌──────────────┐                 │
       └─>│  Encryption  │                 │
          │  (Same Key)  │                 │
          └──────┬───────┘                 │
                 │                         │
          ┌──────▼───────┐                 │
          │ Cipher Text  │─────────────────┘
          └──────────────┘                 │
                                           │
                                    ┌──────▼───────┐
                                    │  Decryption  │
                                    │  (Same Key)  │
                                    └──────┬───────┘
                                           │
                                    ┌──────▼──────┐
                                    │  Plain Text │
                                    └─────────────┘
```

### 3.2 Role of Keys in Symmetric Cryptography

**Encryption Key Role:**
- Transforms plain text into cipher text
- Must be kept secret from unauthorized users
- Determines the specific transformation applied
- Same key used by sender

**Decryption Key Role:**
- Transforms cipher text back to plain text
- Identical to the encryption key
- Must be securely shared between sender and receiver
- Same key used by receiver

### 3.3 Key Distribution Problem

**The Challenge:**

The main problem in symmetric cryptography is securely distributing the secret key to both parties. If the key is intercepted during transmission, the entire system becomes vulnerable.

**Problems:**
- How to securely share the key initially?
- Risk of interception during key transmission
- Need for secure channel before secure communication
- Key management becomes complex with multiple users
- For n users, need n(n-1)/2 keys for pairwise communication

**Solutions:**
- Key Distribution Centers (KDC)
- Diffie-Hellman Key Exchange
- Using asymmetric cryptography for key exchange
- Physical key exchange through trusted courier
- Pre-shared keys during secure setup

### 3.4 Advantages and Disadvantages

**Advantages:**
- Fast encryption and decryption
- Efficient for large data volumes
- Simple implementation
- Less computational overhead
- Suitable for real-time applications

**Disadvantages:**
- Key distribution problem
- Not scalable for large networks
- No non-repudiation
- Key management complexity
- Requires secure channel for key exchange

---

## **4. Asymmetric Key Cryptography**

> PYQ: Discuss the challenges and benefits of asymmetric key cryptography over symmetric key cryptography. Provide real-world examples to illustrate their usage. (2024, 15 marks)      
> PYQ: Role of session key in public key schemes (Feb-22, 2.5 marks)

### 4.1 What is Asymmetric Key Cryptography?

**Asymmetric Key Cryptography** is an encryption method that uses two different but mathematically related keys - a public key for encryption and a private key for decryption. The public key can be freely distributed to anyone, while the private key must be kept secret by the owner. This approach is also called public-key cryptography and solves the key distribution problem of symmetric cryptography.

**Process:**
```
Sender Side:                          Receiver Side:
┌─────────────┐                      ┌─────────────┐
│  Plain Text │                      │ Cipher Text │
└──────┬──────┘                      └──────┬──────┘
       │                                    │
       │  ┌──────────────┐                 │
       └─>│  Encryption  │                 │
          │ (Public Key) │                 │
          └──────┬───────┘                 │
                 │                         │
          ┌──────▼───────┐                 │
          │ Cipher Text  │─────────────────┘
          └──────────────┘                 │
                                           │
                                    ┌──────▼───────┐
                                    │  Decryption  │
                                    │ (Private Key)│
                                    └──────┬───────┘
                                           │
                                    ┌──────▼──────┐
                                    │  Plain Text │
                                    └─────────────┘
```

### 4.2 Challenges of Asymmetric Cryptography

**Technical Challenges:**
- **Computational Overhead**: Much slower than symmetric encryption (100-1000 times)
- **Key Size**: Requires larger key sizes (2048-4096 bits) for equivalent security
- **Resource Intensive**: High CPU and memory requirements
- **Not Suitable for Large Data**: Inefficient for encrypting large files

**Management Challenges:**
- **Certificate Management**: Need for Certificate Authorities (CA)
- **Key Revocation**: Handling compromised keys
- **Trust Issues**: Verifying public key authenticity
- **Implementation Complexity**: More complex algorithms

### 4.3 Benefits of Asymmetric Cryptography

**Over Symmetric Cryptography:**
- **No Key Distribution Problem**: Public key can be shared openly
- **Scalability**: For n users, only need 2n keys (not n(n-1)/2)
- **Digital Signatures**: Provides authentication and non-repudiation
- **Key Management**: Easier to manage in large networks
- **No Pre-shared Secret**: No need for secure initial key exchange

**Security Benefits:**
- Private key never transmitted
- Provides confidentiality, authentication, and non-repudiation
- Enables secure communication with unknown parties
- Foundation for PKI (Public Key Infrastructure)

### 4.4 Real-World Examples

**Asymmetric Cryptography:**
- **SSL/TLS (HTTPS)**: Secure web browsing uses RSA for key exchange
- **Email Encryption**: PGP/GPG for secure email communication
- **Digital Signatures**: PDF signing, code signing, document authentication
- **SSH**: Secure remote server access
- **Cryptocurrency**: Bitcoin uses elliptic curve cryptography
- **VPN**: Initial authentication and key exchange

**Symmetric Cryptography:**
- **File Encryption**: BitLocker, VeraCrypt for disk encryption
- **Database Encryption**: AES for encrypting stored data
- **Video Streaming**: Netflix, YouTube use AES for content protection
- **Mobile Communication**: 4G/5G networks use AES
- **Banking**: ATM transactions use DES/3DES

### 4.5 Hybrid Approach

**Best of Both Worlds:**

Most real-world systems use both:
1. **Asymmetric** for secure key exchange and authentication
2. **Symmetric** for actual data encryption (faster)

**Example: HTTPS Connection:**
```
Step 1: RSA (Asymmetric) → Exchange session key
Step 2: AES (Symmetric) → Encrypt actual data using session key
```

### 4.6 Role of Session Key

> PYQ: Role of session key in public key schemes (Feb-22, 2.5 marks)

**Session Key** is a temporary symmetric key used for encrypting data during a single communication session. In public key schemes, asymmetric cryptography is used to securely exchange the session key, and then symmetric cryptography (using the session key) encrypts the actual data.

**Why Use Session Keys?**
- Combines security of asymmetric with speed of symmetric encryption
- Reduces computational overhead
- Limits damage if key is compromised (temporary key)
- New key for each session enhances security

---

## **5. Substitution Techniques**

> PYQ: Four substitution techniques – merits/demerits. (Feb-22, 10 marks)      
> PYQ: Substitution techniques with examples. (May-23, 10 marks)      
> PYQ: What is the difference between substitution and transposition techniques in cryptography? (2024, 2.5 marks)

### 5.1 What are Substitution Techniques?

**Substitution Technique** is a method of encryption where each element of the plain text (such as a letter, bit, or group of bits) is replaced with another element from a fixed system. The order of the elements remains the same, but their identity changes. This is one of the oldest and most fundamental encryption methods.

### 5.2 Caesar Cipher (Shift Cipher)

**Description:**

The simplest substitution cipher where each letter is replaced by a letter a fixed number of positions down the alphabet.

**Algorithm:**
```
Encryption: C = (P + K) mod 26
Decryption: P = (C - K) mod 26

Where:
C = Cipher text letter position
P = Plain text letter position
K = Key (shift value)
```

**Example (K=3):**
```
Plain Text:  A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
Cipher Text: D E F G H I J K L M N O P Q R S T U V W X Y Z A B C

Plain Text:  HELLO
Cipher Text: KHOOR
```

**Merits:**
- Extremely simple to implement
- Easy to understand
- Fast encryption/decryption
- No complex computations required

**Demerits:**
- Only 25 possible keys (very weak)
- Vulnerable to brute force attack
- Easily broken by frequency analysis
- Not secure for modern use

### 5.3 Monoalphabetic Cipher

**Description:**

A substitution cipher where each letter of the alphabet is mapped to another letter using a fixed substitution table. Unlike Caesar cipher, the mapping is random rather than a simple shift.

**Example:**
```
Plain Text:  A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
Cipher Text: Q W E R T Y U I O P A S D F G H J K L Z X C V B N M

Plain Text:  HELLO
Cipher Text: ITSSG
```

**Key Space:** 26! ≈ 4 × 10²⁶ possible keys

**Merits:**
- Large key space (26! combinations)
- More secure than Caesar cipher
- Simple implementation
- One-to-one mapping

**Demerits:**
- Vulnerable to frequency analysis
- Letter patterns preserved
- Statistical properties of language remain
- Can be broken with sufficient cipher text

### 5.4 Polyalphabetic Cipher (Vigenère Cipher)

> PYQ: Polyalphabetic Substitution Cipher. (Dec-22, 5 marks)

**Description:**

A substitution cipher that uses multiple substitution alphabets. Different letters in the plain text may be encrypted differently depending on their position. This makes frequency analysis much harder.

**Algorithm:**
```
Encryption: Cᵢ = (Pᵢ + Kᵢ) mod 26
Decryption: Pᵢ = (Cᵢ - Kᵢ) mod 26

Where:
Kᵢ = K[i mod key_length]
```

**Example:**
```
Plain Text: HELLO WORLD
Key:        KEYKE YKEYK (repeated)

H + K = R
E + E = I
L + Y = J
L + K = V
O + E = S
...

Cipher Text: RIJVS AMBPN
```

**Vigenère Table:**
```
    A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
A | A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
B | B C D E F G H I J K L M N O P Q R S T U V W X Y Z A
C | C D E F G H I J K L M N O P Q R S T U V W X Y Z A B
... (each row shifted by one)
```

**Merits:**
- Resistant to frequency analysis
- Multiple substitution alphabets
- Stronger than monoalphabetic ciphers
- Variable key length increases security

**Demerits:**
- Vulnerable to Kasiski examination
- Can be broken if key length is known
- Repeating key pattern is a weakness
- Not secure against modern cryptanalysis

### 5.5 Homophonic Substitution Cipher

> PYQ: Homophonic Substitution Cipher (Dec-22, 2.5 marks)

**Description:**

A substitution cipher where a single plain text letter can map to multiple cipher text symbols. This technique flattens the frequency distribution, making frequency analysis much more difficult.

**Example:**
```
Plain Text Letter: E (13% frequency in English)
Cipher Text Symbols: 05, 27, 33, 48, 52, 61, 73, 84, 90, 95, 98, 102, 117

Plain Text Letter: T (9% frequency)
Cipher Text Symbols: 12, 28, 44, 56, 67, 78, 89, 101, 110

Plain Text: MEET
Cipher Text: 95 05 27 12 (one possible encryption)
```

**Merits:**
- Defeats simple frequency analysis
- Flattens frequency distribution
- More secure than monoalphabetic
- Multiple representations for common letters

**Demerits:**
- Requires larger cipher text (more symbols)
- Complex key management
- Still vulnerable to advanced cryptanalysis
- Digram and trigram analysis can break it

### 5.6 Comparison Table

| Technique | Key Space | Security | Frequency Analysis | Complexity |
|-----------|-----------|----------|-------------------|------------|
| Caesar | 25 | Very Weak | Vulnerable | Very Low |
| Monoalphabetic | 26! | Weak | Vulnerable | Low |
| Polyalphabetic | 26^m | Moderate | Resistant | Medium |
| Homophonic | Large | Moderate | Resistant | Medium |

---

## **6. Transposition Techniques**

> PYQ: Transposition techniques. (Feb-22, 5 marks)      
> PYQ: Transposition techniques with examples. (Dec-22, 8 marks)      
> PYQ: What is the difference between substitution and transposition techniques in cryptography? (2024, 2.5 marks)

### 6.1 What are Transposition Techniques?

**Transposition Technique** is a method of encryption where the positions of the plain text characters are rearranged according to a specific system. Unlike substitution, the characters themselves remain unchanged, but their order is scrambled. This technique is also called permutation cipher.

**Key Difference from Substitution:**
- **Substitution**: Changes the identity of characters (A → D)
- **Transposition**: Changes the position of characters (HELLO → LOHEL)

### 6.2 Rail Fence Cipher

> PYQ: Rail-Fence Technique (May-23, 2.5 marks)

**Description:**

The plain text is written in a zigzag pattern across multiple rails (rows), and the cipher text is read row by row.

**Example (3 Rails):**
```
Plain Text: HELLO WORLD

Writing Pattern:
Rail 1: H . . . O . . . L .
Rail 2: . E . L . W . R . D
Rail 3: . . L . . . O . . .

Cipher Text: HOLELWRDLO
```

**Example (2 Rails):**
```
Plain Text: CRYPTOGRAPHY

Rail 1: C . Y . T . G . A . H .
Rail 2: . R . P . O . R . P . Y

Cipher Text: CYTGAHPRPOPY
```

**Algorithm:**
1. Write plain text in zigzag pattern across n rails
2. Read cipher text row by row from top to bottom

**Decryption:**
1. Calculate positions for each rail
2. Fill rails with cipher text characters
3. Read in zigzag pattern to get plain text

**Merits:**
- Simple to implement
- Fast encryption
- No complex calculations
- Easy to understand

**Demerits:**
- Weak security
- Pattern can be detected
- Small key space (number of rails)
- Vulnerable to brute force

### 6.3 Columnar Transposition

**Description:**

Plain text is written row by row in a grid, and cipher text is read column by column in an order determined by a key.

**Example:**
```
Key: 4 3 1 2 5
Plain Text: HELLO WORLD CRYPTOGRAPHY

Grid:
  4 3 1 2 5
  ---------
  H E L L O
  W O R L D
  C R Y P T
  O G R A P
  H Y . . .

Reading order: Column 1, 2, 3, 4, 5

Column 1: LYRRR
Column 2: LLPA.
Column 3: EORGY
Column 4: HWCOH
Column 5: ODTP.

Cipher Text: LYRRRLLPAEORGYHWCOHODTP
```

**Algorithm:**
1. Arrange plain text in rows of fixed length
2. Determine column order using key
3. Read columns in key order to get cipher text

**Merits:**
- More secure than rail fence
- Variable key increases security
- Can use multiple rounds
- Preserves letter frequency (harder to detect)

**Demerits:**
- Vulnerable to known-plaintext attack
- Pattern analysis can reveal structure
- Requires padding for incomplete rows
- Not secure against modern attacks

### 6.4 Double Transposition

**Description:**

Applies columnar transposition twice with different keys for enhanced security.

**Process:**
```
Plain Text → [Transposition with Key1] → Intermediate Text
Intermediate Text → [Transposition with Key2] → Cipher Text
```

**Example:**
```
Plain Text: HELLO
Key1: 3 1 2
Key2: 2 3 1

First Transposition:
  3 1 2
  -----
  H E L
  L O .

Read: EO HLL → EOHLL

Second Transposition:
  2 3 1
  -----
  E O H
  L L .

Read: HHL LEO → HHLLEO

Cipher Text: HHLLEO
```

**Merits:**
- Much stronger than single transposition
- Two keys increase complexity
- Difficult to break without both keys
- Used in historical military communications

**Demerits:**
- Slower than single transposition
- Requires two keys
- Still vulnerable to advanced cryptanalysis
- Not suitable for modern security needs

### 6.5 Comparison: Substitution vs Transposition

> PYQ: What is the difference between substitution and transposition techniques in cryptography? (2024, 2.5 marks)

| Aspect | Substitution | Transposition |
|--------|-------------|---------------|
| **Operation** | Replaces characters | Rearranges positions |
| **Character Identity** | Changed | Unchanged |
| **Character Position** | Unchanged | Changed |
| **Frequency Analysis** | Vulnerable (except polyalphabetic) | Not applicable |
| **Examples** | Caesar, Vigenère | Rail Fence, Columnar |
| **Security** | Depends on key space | Depends on permutation |
| **Pattern** | Letter patterns broken | Letter patterns preserved |

---

## **7. Block Cipher Design Principles**

> PYQ: Design principles of block cipher. (Feb-22, 8 marks)

### 7.1 What is a Block Cipher?

**Block Cipher** is a symmetric encryption method that processes fixed-size blocks of data (typically 64 or 128 bits) at a time. It transforms each block of plain text into a block of cipher text using a secret key. Modern encryption standards like DES and AES are block ciphers.

### 7.2 Feistel Cipher Structure

> PYQ: Feistel Cipher (Feb-22, 2.5 marks)

**Feistel Cipher** is a symmetric structure used in many block cipher designs where encryption and decryption processes are almost identical. The plain text block is divided into two halves, and multiple rounds of processing are applied using subkeys derived from the main key.

**Structure:**
```
┌─────────────────────────────────────┐
│         Input Block (64-bit)        │
└────────────┬────────────────────────┘
             │
      ┌──────┴──────┐
      │             │
   Left (L₀)    Right (R₀)
      │             │
      │      ┌──────┴──────┐
      │      │  Function F │
      │      │   (Key K₁)  │
      │      └──────┬──────┘
      │             │
      └─────⊕───────┘
            │
         (L₁, R₁)
            │
      (Multiple Rounds)
            │
      ┌─────┴─────┐
      │           │
    Left       Right
      │           │
      └─────┬─────┘
            │
┌───────────▼─────────────────────────┐
│         Output Block (64-bit)       │
└─────────────────────────────────────┘
```

**Round Function:**
```
Lᵢ = Rᵢ₋₁
Rᵢ = Lᵢ₋₁ ⊕ F(Rᵢ₋₁, Kᵢ)

Where:
⊕ = XOR operation
F = Round function
Kᵢ = Round key
```

**Advantages:**
- Encryption and decryption are similar (same structure)
- Easy to implement
- Reversible regardless of F function
- Used in DES, Blowfish, Twofish

### 7.3 Design Principles

**1. Confusion:**

Makes the relationship between cipher text and key as complex as possible. An attacker should not be able to predict how changes in the key affect the cipher text.

**Implementation:**
- Substitution operations (S-boxes)
- Complex non-linear transformations
- Each bit of cipher text depends on multiple key bits

**2. Diffusion:**

Spreads the influence of one plain text bit over many cipher text bits. A small change in plain text should cause significant changes in cipher text.

**Implementation:**
- Permutation operations (P-boxes)
- Transposition
- Each plain text bit affects multiple cipher text bits

### 7.4 Avalanche Effect

> PYQ: Avalanche effect (Feb-22, 2.5 marks)

**Avalanche Effect** is a desirable property of cryptographic algorithms where a small change in the input (plain text or key) produces a significant change in the output (cipher text). Ideally, changing one bit in the input should change approximately 50% of the output bits.

**Example:**
```
Plain Text 1: 10110101 10110101
Key:          11001100 11001100
Cipher Text:  01101110 10011001

Plain Text 2: 10110100 10110101 (1 bit changed)
Key:          11001100 11001100
Cipher Text:  11010001 01100110 (8 bits changed)
```

**Importance:**
- Prevents pattern detection
- Makes cryptanalysis difficult
- Small input changes hide relationships
- Essential for strong encryption

### 7.5 Product Cipher

> PYQ: Product cipher (Dec-22, 2.5 marks)

**Product Cipher** is a cipher that combines two or more simple ciphers in sequence to achieve higher security. It typically combines substitution and transposition operations to achieve both confusion and diffusion.

**Types:**
- **Substitution-Permutation Network (SPN)**: Alternates substitution and permutation
- **Feistel Network**: Uses repeated rounds of function application

**Example:**
```
Plain Text → [Substitution] → [Transposition] → [Substitution] → Cipher Text
```

**Advantages:**
- Stronger than individual ciphers
- Achieves both confusion and diffusion
- Foundation of modern block ciphers
- Multiple rounds increase security

### 7.6 Key Design Principles Summary

- **Block Size**: Larger blocks increase security but reduce efficiency (64, 128, 256 bits)
- **Key Size**: Longer keys increase security (128, 192, 256 bits)
- **Number of Rounds**: More rounds increase security but reduce speed (16 for DES, 10-14 for AES)
- **Subkey Generation**: Complex key schedule prevents related-key attacks
- **Round Function**: Should be non-linear and provide confusion
- **Efficiency**: Balance between security and performance

---

## **8. Mathematical Foundations**

> PYQ: Fermat and Euler's theorem. (Feb-22, 7 marks)

### 8.1 Fermat's Little Theorem

**Statement:**

If p is a prime number and a is any integer not divisible by p, then:

**aᵖ⁻¹ ≡ 1 (mod p)**

Or equivalently: **aᵖ ≡ a (mod p)**

**Example:**
```
Let p = 7, a = 3

3⁷⁻¹ = 3⁶ = 729
729 mod 7 = 1

Therefore: 3⁶ ≡ 1 (mod 7) ✓
```

**Applications:**
- Primality testing
- RSA algorithm
- Modular exponentiation
- Cryptographic key generation

### 8.2 Euler's Theorem

**Euler's Totient Function φ(n):**

The count of positive integers less than n that are relatively prime to n (gcd = 1).

**Examples:**
```
φ(9) = 6    (1, 2, 4, 5, 7, 8 are coprime to 9)
φ(10) = 4   (1, 3, 7, 9 are coprime to 10)
φ(p) = p-1  (if p is prime)
φ(p×q) = (p-1)(q-1)  (if p, q are prime)
```

**Euler's Theorem Statement:**

If a and n are relatively prime (gcd(a,n) = 1), then:

**aᶲ⁽ⁿ⁾ ≡ 1 (mod n)**

**Example:**
```
Let n = 10, a = 3
φ(10) = 4

3⁴ = 81
81 mod 10 = 1

Therefore: 3⁴ ≡ 1 (mod 10) ✓
```

**Relationship:**
- Fermat's theorem is a special case of Euler's theorem (when n is prime)
- Both are fundamental to RSA algorithm
- Used in modular arithmetic for cryptography

### 8.3 Application in RSA

**RSA Key Generation:**
```
1. Choose two primes: p, q
2. Calculate n = p × q
3. Calculate φ(n) = (p-1)(q-1)
4. Choose e such that gcd(e, φ(n)) = 1
5. Calculate d such that d×e ≡ 1 (mod φ(n))

Public Key: (e, n)
Private Key: (d, n)
```

**Why Euler's Theorem Works in RSA:**
```
Encryption: C = Mᵉ mod n
Decryption: M = Cᵈ mod n

Proof: Cᵈ = (Mᵉ)ᵈ = Mᵉᵈ mod n

Since e×d ≡ 1 (mod φ(n))
Therefore: e×d = 1 + k×φ(n)

Mᵉᵈ = M^(1+k×φ(n)) = M × (Mᶲ⁽ⁿ⁾)ᵏ

By Euler's theorem: Mᶲ⁽ⁿ⁾ ≡ 1 (mod n)

Therefore: M × 1ᵏ = M (Original message recovered!)
```

---

## **9. Key Exchange Algorithm**

> PYQ: Diffie–Hellman Key Exchange Algorithm. (May-23, 7 marks)

### 9.1 Diffie-Hellman Key Exchange

**Diffie-Hellman Key Exchange** is a method for two parties to securely establish a shared secret key over an insecure channel without having met before. The security is based on the difficulty of computing discrete logarithms. This algorithm solves the key distribution problem in symmetric cryptography.

### 9.2 Algorithm Steps

**Public Parameters:**
- **p**: A large prime number
- **g**: A primitive root modulo p (generator)

Both p and g are publicly known.

**Process:**

```
Alice Side:                          Bob Side:
1. Choose private key: a            1. Choose private key: b
   (random number)                     (random number)

2. Calculate public key:            2. Calculate public key:
   A = gᵃ mod p                        B = gᵇ mod p

3. Send A to Bob ──────────────────> Receive A

4. Receive B <────────────────────── Send B to Alice

5. Calculate shared secret:         5. Calculate shared secret:
   S = Bᵃ mod p                        S = Aᵇ mod p

Both have same secret: S = gᵃᵇ mod p
```

### 9.3 Example

**Given:**
```
p = 23 (prime)
g = 5 (primitive root)
```

**Alice's Side:**
```
Private key: a = 6
Public key: A = 5⁶ mod 23 = 15625 mod 23 = 8
Send A = 8 to Bob
```

**Bob's Side:**
```
Private key: b = 15
Public key: B = 5¹⁵ mod 23 = 30517578125 mod 23 = 19
Send B = 19 to Alice
```

**Shared Secret Calculation:**

**Alice computes:**
```
S = Bᵃ mod p = 19⁶ mod 23 = 47045881 mod 23 = 2
```

**Bob computes:**
```
S = Aᵇ mod p = 8¹⁵ mod 23 = 35184372088832 mod 23 = 2
```

**Shared Secret: S = 2** ✓

### 9.4 Security

**Why It's Secure:**
- Attacker can see: p, g, A, B
- Attacker needs to find: a or b
- This requires solving discrete logarithm problem: gᵃ = A (mod p)
- Computationally infeasible for large p (2048+ bits)

**Vulnerabilities:**
- **Man-in-the-Middle Attack**: No authentication of parties
- **Small Subgroup Attack**: If g is not properly chosen
- **Weak Random Numbers**: If a or b are predictable

**Solutions:**
- Use authenticated Diffie-Hellman
- Digital signatures for authentication
- Strong random number generators
- Proper parameter selection

---

## **Expected Exam Questions**

### **15 Marks Questions:**

1. **Explain substitution techniques in detail. Discuss Caesar cipher, monoalphabetic cipher, polyalphabetic cipher, and homophonic cipher with examples, merits, and demerits.**

2. **Describe the process of symmetric key cryptography and explain the role of encryption and decryption keys. What are the challenges in key distribution?**

3. **Discuss the challenges and benefits of asymmetric key cryptography over symmetric key cryptography. Provide real-world examples and explain the hybrid approach.**

4. **Explain transposition techniques with examples. Discuss rail fence cipher, columnar transposition, and double transposition. Compare substitution and transposition techniques.**

5. **Explain the Diffie-Hellman key exchange algorithm with a numerical example. Discuss its security and vulnerabilities.**

### **7-8 Marks Questions:**

1. **Explain the design principles of block cipher. Discuss confusion, diffusion, and avalanche effect.**

2. **Describe Feistel cipher structure with a diagram. Explain its advantages.**

3. **Explain Fermat's Little Theorem and Euler's Theorem with examples. How are they used in RSA?**

4. **Discuss the key distribution problem in symmetric cryptography and its solutions.**

5. **Explain polyalphabetic substitution cipher (Vigenère cipher) with an example.**

### **2.5 Marks Questions:**

1. **Define plain text and cipher text. How are they related in encryption?**

2. **What is the difference between substitution and transposition techniques?**

3. **Explain Feistel cipher.**

4. **What is avalanche effect?**

5. **Define product cipher.**

6. **Explain homophonic substitution cipher.**

7. **What is cryptanalysis?**

8. **Describe rail fence technique.**

9. **What is the role of session key in public key schemes?**

---

## **Quick Revision Points**

### **Key Concepts:**
- Plain text → original message; Cipher text → encrypted message
- Encryption uses key to convert plain text to cipher text
- Decryption reverses the process
- Symmetric: same key for encryption/decryption
- Asymmetric: public key for encryption, private key for decryption

### **Substitution Techniques:**
- **Caesar**: Shift by fixed positions (25 keys)
- **Monoalphabetic**: Random mapping (26! keys)
- **Polyalphabetic**: Multiple alphabets (Vigenère)
- **Homophonic**: Multiple symbols per letter

### **Transposition Techniques:**
- **Rail Fence**: Zigzag pattern writing
- **Columnar**: Write in rows, read in column order
- **Double**: Apply transposition twice

### **Block Cipher Principles:**
- **Confusion**: Complex key-ciphertext relationship (S-boxes)
- **Diffusion**: Spread plaintext influence (P-boxes)
- **Avalanche**: 1-bit change → 50% output change
- **Product Cipher**: Combine substitution + transposition

### **Mathematical Foundations:**
- **Fermat**: aᵖ⁻¹ ≡ 1 (mod p) for prime p
- **Euler**: aᶲ⁽ⁿ⁾ ≡ 1 (mod n) for coprime a,n
- **φ(n)**: Count of numbers coprime to n
- Used in RSA algorithm

### **Diffie-Hellman:**
- Public: p (prime), g (generator)
- Private: a (Alice), b (Bob)
- Exchange: A = gᵃ mod p, B = gᵇ mod p
- Shared secret: S = gᵃᵇ mod p

---

*These notes were compiled by [Deepak Modi](https://deepakmodi.tech)*  
*Last updated: December 2024*

