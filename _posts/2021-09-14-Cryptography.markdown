---
layout: post
title:  "Classical Cryptography"
date:   2021-09-14 15:25:36 +0530
categories: Cryptography
---

### **Overview of Cipher** <br/>


![Image Alt MemoryLayout](/assets/cipherdiagram.png) <br/>
<br/>

### Transposition Ciphers <br/>
<br/>

**Rail and Fence** <br/>
<br/>
Transposition Ciphers = Plaintext's letters are **rearranged** <br/>
    - Cipher text is considered a **permutation** of the plain text <br/>
    - If there is a plaintext "Jay Chung", Choose to remove spaces and rearrange: **"gnuhcyaj"**  <br/>
<br/>
The Rail Fence Cipher
    - Plaintext "WE ARE DISCOVERED FLEE AT ONCE" <br/>
    - Encryption key = **#of rails (In this case: #3 (lines))** <br/>

![Image Alt MemoryLayout](/assets/railcipher.png) <br/>

Ciphertext: **WECRLTEERDSOEEFEAOCAIVDEN** <br/>
Explaination: 'W' goes to the first line at index 0 dot, 'E' goes to second line index 1 dot, 'A' goes to third line index 2 dot, 'R' goes to second line (Go up again) at index 3 dot... <br/> 
The Key can be found easily using **Brute Force** <br/>
<br/>

**Scytale Cipher** <br/>
<br/>
Sctyale dates back to 7 B.C. <br/>
Encryption/ Decryption: A Cylinder with a strip of parchment wound around it <br/>
**Key = Diameter of scytale's rod**<br/>
Hypothessis: used for **Message authentication**<br/>
Also **Brute Force** of the rod size <br/>

**Columnar Transposition Cipher** <br/>
<br/>
The message is written out in rows of a fixed length <br/>
    - Read out column by column <br/>
    - The columns are chosen in some scrambled order <br/>

**KEY = length of the rows (i.e # of the columns) AND order of the columns used in the read out (6 3 2 4 1 5)** <br/>
![Image Alt MemoryLayout](/assets/columnarcipher.png) <br/>
(Empty Padding filled with other letters to make harder to decrypt) <br/>
Plain text: **WE ARE DISCOVERED FLEE AT ONCE" <br/>
Cipher text: **EVLNEACDTKESEAQROFOJDEECUWIREE** <br/>
<br/>

Number of columns can be guessed by **Trail and Error** <br/>
    - Double Transposition: apply columnar transposition twice to make it harder to guess. 
<br/>
<br/>

### Modular Arithmetic  <br/>

**Modular Arithmetic** is most important for **asymmetric cryptography** <br/>
    - can also describe some symmetric and classic ciphers elegantly using it  <br/>

Generally, cryptosystems are founded on **set of numbers:** Discrete (Set of positive integers,..), Finite <br/>
 
Example: Watch, Clock: System that starts from 1 to 12 <br/>

8:30 + 23 hours = 7:30 (NOT 31:30) <br/>
<br/>

![Image Alt MemoryLayout](/assets/modulusoperation.png) <br/>
<br/>
The remainder is **not unique**: a = q(몫) * m + r  where 0 <= r <= m-1 (read "a" divided by "m") <br/>
Example: a = 12 and m = 9 <br/>
12 = 1 * 9 + 3 (valid) <br/>
12 = -1 * 9 + 21 (valid) <br/>
<br/>

**Modular Division** <br/>
We prefer to multiply by the inverse b/a === bxa^(-1) <br/>
The inverse of a number is defined as **aa^-1 = 1 mod m** <br/>
a = 2, a^-1 = 2, m = 9 ... then 2 * 2^-1 = 1 mod 9  (...,0,1,2,3,...,8) <br/>
but what's 2^-1 ? (2 * 2^-1) = (2*5) = 1 mod 9 <br/>
Therefore, 2^-1 = 5 mod 9 <br/>
Exist because gcd(2,9) = 1 <br/> 
<br/>

**How about 6^-1 = ? mod 9 ?** <br/>
- gcd(6,9) = 3, therefore, no inverse exist for 6, 3 is the number that can divide both of them and it's greater than 1 <br/>
<br/>

### Subsitution Ciphers <br/>

**Subsitution Cipher** <br/>
<br/>

**Main idea** : repalce the plaintext letter by another fixed letter<br/>
![Image Alt MemoryLayout](/assets/subsitution.png) <br/>
Whenever you have "A" you can replace with your "K" <br/>
Whenever you have "B" you can replace with your "E" <br/>
Whenever you have "C" you can replace with your "D" <br/>
<br/>
"ABBA" -> "KEEK"<br/>

What is the all possibilities? **26!** Why? <br/>
When you choose "A" -> 26 possibilities "B" -> 25 possibilities, "C" -> 24 ... = 26 * 25 * 24 * 23 * 22 ... * 2 * 1 <br/>
**Is it still Safe? without Brute Force Attack?:**  <mark style='background-color: #fff5b1'>Beacuse of the language frequency, map the frequency of the letter and figure it out! </mark>  <br/>
<br/>

**Frequency Analysis** <br/>
It turns some letters are more frequent than others in the English language <br/>
    - Also, this from of transformation preserve frequency of plaintext letters <br/>
    - Pair, Tri letters can also be measure such as "The", "And", and etc.. <br/>
<br/>
Consider the following ciphertext generated using a subsitution cipher <br/>
    - "iq ifcc vqqr fb rdq vfllcq na rdq cfjwhwz hr bnnb hcc hwwhbsqvqbre hwq vhlq" <br/>
We replace the most common letter with "e" and get the following: <br/>
    - "i**E** ifcc v**E****E**r fb rd**E** vfllc**E** na rd**E** cfjwhwz hr bnnb hcc hwwhbs**E**v**E**bre hw**E** vhl**E**" <br/>
By further guesses based on frequency of remaining ciphertext letters we can obtain the plain text <br/>
    - "WE WILL MEET IN THE MIDDLE OF THE LIBRARY AT NOON ALL ARRANGEMENTS ARE MADE <br/>
    <br/>
In practice, you can consider frequency of the letter pairs and not just inidivual letters (unigram) <br/>
    - For example, "th" is a common bi-gram in the English language <br/>
    - "EE" is one of the same letter common bigram <br/>
    - "THE" and "ING" are some of the most common tri-garm <br/>
<br/>

**Frequency Vectors**<br/>
<br/>
Form an array with the English language's letters frequency ratio<br/>
    - double[] eng_freq={0.0812,0.0149,...,0.0007} <br/>
    - Find the which key is the match: How do you know your decryption is correct? <br/>
Form an array with the plaintext's letters frequency ration <br/>
    - double[] plaintext_freq = { 0.812,0.149,...}; <br/>
Are the two vectors close? <br/>
    - One is eng_freq , one is plaintext_freq and two are close chances are correct. (Euclidian distance, Manhathan distance) <br/>
<br/>
Can use **Cosine Similarity** <br/>
![Image Alt MemoryLayout](/assets/cosine.png) <br/>
1 means exactly same, 0 means orthogonal <br/>
<br/>
**Caesar Cipher**<br/>
<br/>
Also known as Shift Cipher <br/>
Take letter that follows after **k position** in alphabet <br/>
![Image Alt MemoryLayout](/assets/caesar.png) <br/>
Example, k = 7 <br/>
    - Plaintext: "Attack" <br/>
    - Ciphertext: "haahfr" <br/>
    - **letters "wrap around" at the end of the alphabet, which can be mathematically be expressed as reduction modulo 26, e.g, 19 + 7 = 26 = 0 mod 26 ** <br/>
<br/>
<br/>
**Steps for Caesar Cipher** <br/>
1. Read the plaintext file into array of bytes pt <br/> 
2. Clean pt keeping only letters and upper case them <br/>
3. Shift: ct[i] = [(pt[i])-'A')+ key] % 26 + 'A'<br/>
4. write the ciphertext array to a file. <br/>