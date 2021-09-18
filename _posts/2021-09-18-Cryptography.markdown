---
layout: post
title:  "Caesar Cipher"
date:   2021-09-18 11:24:36 +0530
categories: Cryptography
---

### **Obliterating Patterns** <br/>


To defat the cyptanalyst, we must **prevent Plaintex's patterns from appearing in Ciphertext** <br/>
    
   - Make Ciphertext as **random as possible**(create confusion) <br/> 
   - Compose two ciphers - **Affine** (Monoalphabetic) Observation: Any composition of different cipher is useless if both are monoalphabetic <br/>
   - Different mappings for same Plain Text Letter - **Vigenere** (Polyalphabetic) <br/>
   - Encrypt in Blocks - **Hill** (Polyalphabetic) <br/>
<br/>

**Affine cipher** <br/>
<br/>
Is a symmetric product (i.e. composition) cipher <br/>
<br/>

In **Caesar Cipher** : C = P + K mod 26 <br/>

![Image Alt MemoryLayout](/assets/affine.png) <br/>
In **Affine Cipher** we got two parameter Alpha and Beta <br/>
<br/>
Example: Plaintext = "CS" 2, 18 / Ciphertext = "LH" <br/>
Key = (Alpha,Beta) = (3,5) <br/>
C = 2 (3) + 5 mod 26 = 11<br/>
S = 18 (3) + 5 mod 26 = 7<br/>
<br/>

**Affine Cipher Search Space**<br/>
<br/>
How big is the search space? <br/>

- Alpha must be (1~25) (Why start from 1? becuase if its 0 your plain text will be 0 too) and Beta must be (0~26) <br/>
- Since the inverse of a is needed for inversion, we can only use values for a for which **gcd(a,26)=1** <br/>
- We are computing the inverse of the alpha, the inverse of alpha must exist in mod 26. However Not every number has a inverse of given modulous <br/>
- We  know that the greatest common divisor has to be equal to **1** for inverse to exist.  <br/>
- Therefore, there are only **12 values** for a that fulfill this condition <br/>
- **12 * 26 = 312 Key Space**
- Easy to brute-force <br/>
- Easy to Frequnecy Analyze the cipher text <br/>
- Because your increasing every multiply by **Constant Alpha**, Creating larger bars but preserved and shift that <br/>
<br/>

**Monoalphabetic** <br/>
<br/>

Monoalphabetic is a cipher in which for a given key, the cipher alphabet for each plain alphabet is **fixed** thorughout the encryption process <br/>
Always certain Alphabet is mapped to another Alphabet: A-> 'C' , B-> 'x' ... <br/>
<br/>

**Polyalphabetic** <br/>
<br/>

Polyalphabetic is a cipher in which for a given key, the cipher alphabet for each plain alphabet **Change** throughout the encryption process <br/>
<br/>

**Vigenere Cipher**  <br/>
- Invented by Blaise de Vigenere in 1523 <br/>
![Image Alt MemoryLayout](/assets/vigenere.png) <br/>

