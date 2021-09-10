---
layout: post
title:  "Cryptography Introduction"
date:   2021-09-09 19:00:36 +0530
categories: Cryptography
---

### **Cryptology** <br/>


**Cryptology: an Overview** <br/>
	- Cyptography + Cryptoanalysis
<br/>
<br/>
**CIA traid in Cryptography** <br/>
It is a designed to guide polices for **information security** <br/>
	1. **Confidentiality (비밀리)** <br/>
	Only Authorized individuals / Systems can view sensitive or classified information (Cyptography is one of the tool to helps to obtain confidentiality) <br/>
	<br/>
	2. **Integrity (진실성)** <br/>
		- Of content: Contents are not tampered with (Important that when you send the data, data must not be tampered) <br/>
		- Of sender: the sender is who he claims to be (Verifiy the integrity of the sender) <br/>
		- Of Time of Sending: is recent (Things that are not suppose to be reusable)<br/>
		- Of Act of Sending: non-repudiation (Sender can not walk back)<br/>
		<br/>
	3. **Availability** 
	Making sure the resources are available to its authorized parties <br/>
<br/>
**The Generic Model** <br/>
![Image Alt MemoryLayout](/assets/crypto.png) <br/>
**Problem Statement:** <br/>
1. Alice and Bob would like to communicate via an unsecure channel(eg. WLAN or the Internet) <br/>
2. A malicious party (Eve) has channel access but should not be able to understand the communication <br/>
<br/>
**The Solution to the Problem** <br/>
Encryption using a symmetric cipher <br/>
![Image Alt MemoryLayout](/assets/crypto1.png) <br/>
<br/>
**Question:** Let's say we have encryption algorithm and keep it extremely secure, so only Alice and Bob knows the algorithm. Is it good? <br/> 
**Answer:** Using a single algorithm is extremely difficult task, If it gets leaked Alice wouldn't even know Bob or Eve. <br/>
<br/>
![Image Alt MemoryLayout](/assets/crypto2.png) <br/>
Encryption Algorithm published online but only thing we need to be secret is the **KEY** <br/>
Even if the people know the Encryption Algorithm, If they do not have a **KEY** they can not access <br/>
Anther benefit is that Even if we lose the **KEY** we can generate new private **KEY** not changing the Encryption Algorithm <br/>
<br/>
**Symmetric Cryptography** <br/>
	- Encryption and decryption are **inverse operations** if the same key K is used on both sides: <br/>
		**Encryption equation y = encryptkeyfunction(x)** <br/>
		**Decryption equation x = decryptkeyfunction(y)** <br/>
		**decrypt(y) = decrypt(encrypt(x)) = x** <br/>
	- Key must be transmitted via a **secure channel between A and B**: The problem of secure communication is reduced to secure tranmission and storage of the key K <br/>
<br/>
**Cryptanalysis**<br/>
- There is no mathmatical proof of security for any partical cipher: only way is to try to braek it <br/>
- **Kerkhoff's Principle:** A cryptosystem should be secure even if the attacker knows all details about the system, with the exception of the secret key. <br/>
<br/>
**Brute Force Attack**<br/>
- Trial and Error <br/>
- Trying every key in the key space! <br/>
- Lends itself naturally to parallel computing <br/>
- Requires an approximate definition of sucess <br/>
- Currentl technologies 1 key/microsecond/core: 1second = 1,000,000 microsecond, Cluster can reach 1M/key/microsecond  <br/>
![Image Alt MemoryLayout](/assets/crypto3.png) <br/>
<br/>
**Other form of attacks**<br/>
- **Attack Models: **<br/>
1. Known/ Chosen Ciphertext (KCA/CCA)
2. Known/ Chosen Plaintext (KPA/CPA)
<br/>
- **Methodologies** <br/>
1. Residual Patterns <br/>
2. Algorithmic/Implementation Vulnerability <br/>
3. Timing, Linear, and Differential Techniques  <br/>
4. Dictionary, Rainbow Table <br/>
5. Birthday <br/>
6. Meet-in-the-Middle, Man-in-the-Middle <br/>
