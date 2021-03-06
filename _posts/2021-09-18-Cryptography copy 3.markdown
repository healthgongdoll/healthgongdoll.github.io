---
layout: post
title:  "Symmetric Cryptography"
date:   2021-09-21 22:24:36 +0530
categories: Cryptography
---

### **Stream Ciphers** <br/>


Stream Ciphers <br/>
- OPT, WEB, PRNG <br/>
<br/>

BLOCK Ciphers <br/>
- Modes, DES, AES <br/>

**Stream Cipher** <br/>
<br/>
A stream cipher encrypts bits individually (one bit at a time) <br/>
- Simple and fast - common in embedded devices (GSM Phones) <br/>
- Quality of Service (Must be fast) <br/>



![Image Alt MemoryLayout](/assets/stream.png) <br/>
- xi = Plain Text (Sequence of xi) <br/>
- si = Key (Sequence of seceret keyi) <br/>
- yi = Cipher Text (Sequence of yi) <br/>
- **Encryption and Decryption are the same function** <br/>
- A simple additions modulo 2 (i.e. XOR) - also known as Vernam Cipher <br/>
- PlainText xi, Ciphertext yi, and key stream si, are individual bits z = {0,1} <br/>
- Given a plaintext we can shift that text by the constant and then compute the modulos of the length of your alphabet. This time your alphabet is {0,1} (mod2)<br/>
<br/>

**Proof** <br/>
<br/>
Xi = Yi + Si mod 2 <br/>
Xi = (Xi + Si) + Si mod 2 <br/>
Xi = 2Si + Xi mod 2 // 2 is divisible by 2 <br/>
Xi = Xi mod 2 <br/>
Xi = Xi <br/>
<br/>

**Why Modulo 2 Addition** <br/>
- Modulo 2 addition is same as **XOR gate** => easy and extremely fast to implement in hardwares <br/>
- A perfectly random key stream si, each ciphertext output bit has a 50% chance to be 0 or 1 <br/>
- Encrypt = Decryption => Inverting XOR is as simple as applying XOR operation again <br/> 
- We know that xi could be 0 or 1 , si could be 0 or 1  <br/> 
![Image Alt MemoryLayout](/assets/stream1.png) <br/>
- If you know your plain text xi = 0 but you dont know the si , yi could be 0 or 1 <br/>
- If you know your plain text xi = 1 but you dont know the si , yi could be 0 or 1 <br/>
- essentially eventhough it is very simple, if key stream is perfectly random output bit has a 50% chance <br/>
<br/>

**Example** <br/>
<br/>

Plaintext = (ASCII) 'A' <br/>
Key Stream = (Binary) 0101101 <br/>
<br/>
1. Plaintext's bit representation: x7, ..., x1 = 1000001 <br/>
2. XOR it with key stream:        s7, ... , s1 = 0101101 <br/>
3. Ciphertext will be =           y7, ... , y1 = 1101100 = 'i' <br/>
<br/>

**How secure is a stream cipher** <br/>
<br/>

- Depends entirely on the key stream si <br/>
- Should be random: Pr(si = 0) = Pr(si=1) = 0.5 <br/>
- Must be reproducible by sender and recevier <br/>
- Receiving 0 or 1 in your key stream, should be 50% if I give you the n bit of the key stream and n is very large num (like 100) you should not able to guess always have 50/50 chance <br/>
<br/>

We have a module called **KEY STREAM GENERATOR** <br/>
<br/>
- Synchronous Stream Cipher <br/>
   - Key Stream depends only on the key <br/>
   - Provides confusion (each bit of ciphertext should not depend on several part of the key) (no diffusion: if you change single bit in plaintext it should change multiple bit in cipher text ) <br/>
<br/>
- Asynchronous Stream Cipher <br/>
   - Key Stream depends on the key and also ciphertext (dotted feedback!) <br/>
   - Provides confusion and diffusion <br/> 
<br/>

**Random Number Generator** <br/>
<br/>
Three Main Categories <br/>
<br/>

1. True Random Number Generator (TRNG) <br/>
   - Based on physical random process: coin flipping, radioactive decay, mouse movement <br/>
   - Given a sequence of n output, can not predict n+1 with certainty <br/>
   - Not reproducable 
<br/>

2. Pseudorandom Number Generator (PRNG) <br/>
   - Generates the sequence from an initial seed value <br/> 
   - typically, the output stream has good statistical properties (uniformity) <br/>
![Image Alt MemoryLayout](/assets/stream2.png) <br/>
   - Most PRNGs have bad cryptographic properties <br/>

3. Cryptographically Secure Random Number Generator (SRNG) <br/>
   - Special PRNG when output is unpredictable, i.e, given n consecutive bits of output s_i <br/>
<br/>

**Random Number Generators** <br/>
<br/>
Example: a simple PRNG: Linear Congruential Generator (LCG) <br/>

![Image Alt MemoryLayout](/assets/stream3.png) <br/>

- S0 is the seed (fixed number) <br/>
- Next number is always depend on previous number **Key is (A,B)** <br/>
- If adversary knows A and B, they can generate the same random sequence <br/>
- If I were to generate sequence of random bits using this and give n of those bits and give it to adversary, can he/she guess? <br/>
<br/>

**Cryptanalyzing LCG** <br/>
<br/>

- Unknowns: key = (A,B) and s0 <br/>
- Attacker knows s1, s2, s3 <br/>
- Can they find what s4 is? <br/> 
- Assume that attacker knows 3 plaintext x1, x2, and x3 (e.g. protocol headers) <br/>
- Can observe y1, y2, and y3 by having access to the channel <br/>
- So the attacker can compute s1,s2,s3 from the known information (XOR) <br/>
<br/>
He has to solve following two equations to find out A and B (Beacuse it is a linear) <br/>

![Image Alt MemoryLayout](/assets/stream4.png) <br/>
<br/>

**One-Time Pad (OTP)**<br/>
<br/>

![Image Alt MemoryLayout](/assets/stream5.png) <br/>

Unconditionally secure cryptosystem **if key used only once**<br/>
- Cannot be solved given infinite computational power <br/>

- Every equation is linear equation with two unknown <br/>
   - True iff keys are independent truly random <br/>

- Disadvantages: for almost all application the OTP is impractical since the key must be as long as the message! (1TB database/message must accompanied by 1TB secret key for encryption!) <br/>
