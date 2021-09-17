---
layout: post
title:  "Analog and Digital Communication"
date:   2021-09-15 20:20:36 +0530
categories: Network
---

### **Analog vs Digital Communication** <br/>


**Anaglog Vs. Digital** <br/>

**Analog:** Once the **noise is added to the signal**, it becomes part of the signal. At maximum, we can do **filtering and amplifications** which amplifies the noise. We need higher <br/>
**signal-to-noise ratio (SNR)** to reconstruct the signal <br/>
<br/>

**Digital:** Once the signals are known to the reciever, we send symbols, in simple case its 1 or 0. The reciever has to recognize the binary signal. Digital signals are much easier to detect <br/>
<br/>

**Reconstruction (analog) vs Recognition (digital)**<br/>
<br/>

**Transmitter (Send Analog Signal) and Reciever (Reconstruct Analog Signal)**, they are the basic element of the communication system, when we send the signal to the channel, channel contains <br/> 
The noise and disruption of the signal and it is **hard to Reciever to reconstruct the signal**. It is not obvious and what was the amplification of the signal. <br/> 

Therefore in analog, **you can not send many signals in one channel**. However, digital communication we convert the signals to the **0 and 1s (bits)** <br/>
Digital communcation **transforms the analog signals into digital form**. 1 and 0s can be represented in certian voltage (+5, -5).  <br/>
This is much easier in Reciever Side. Reciever knows the **Codebook** and just **recognize the signal** <br/> 


![Image Alt MemoryLayout](/assets/network5.png) <br/>

 <br/>

 **Digital Communication System (TX)** <br/>
<br/>
    1. **Transducer**: take your voice signal and convert them into two electric signals (Physical World signal: Microphone)<br/>
    2. **Transmitter**: **Sample the signal** (Observe the signal at certain specific time **(Continous Time Continous Value Singal -> Discrete Time Continous Value Signal)**), <br/>
     **Quantization** (Make the certain level: ex) let's approaximate 1.2 to the 1, 2.9 to the 3 , and so on.), **Encoding** (how many bits to allocate for levels? 1(+) and 0(-)) <br/>
     <br/>
     Calculation: If you have 4 levels, how many bits need? 2^2 = 00, 01, 10, 11 (2bits). How many bits we need for 32 level ?  2^5 = 5 bits / per sample <br/>
     **Data rate** (bits/sec)= 2 sample/sec * 5 bits/sample = 10 bits/sec   EX) What if we have 33 level? must use 2^6 bits (but waste of bits) <br/>
    3. **Channels**: Wired, Wireless, Storage
    4. **Reciever(RX)**: Demodulation (Reverse of the modulartion, Take physical electric wave form and convert them into 1 and 0), Demultiplexing, Detection (Detect the signal) <br/>
    5. **Output Transducer**
    <br/>
    ![Image Alt MemoryLayout](/assets/network6.png) <br/>
<br/>

**Types of Communications** <br/>
<br/>
Direct-link Communications (One physical link, no intermediate devices) <br/>
Network Communications (Multiple physical link, multiple intermediate(Router, Switches) devices) <br/>
<br/>

**What is a Communication Network** <br/>
<br/>
Definition: set of equipment and channels that provide a service: enables transfer of information between users located at various geographical point <br/>
    - Equipment = hardware + software: computers, switches, routers, modems, servers, etc. <br/>
    - Channels = copper wires, coaxial cables, optical fiber, air <br/>
    - Different -ntworks/services differ in what form of data is transferred how <br/>
Different type of Communication networks: Telephone networks (wired or wireless) vs Computer networks (internet) <br/>
<br/>

**Telephone Networks** <br/>
<br/>
Discovered by Bell <br/>
Voice signals can be transmitted over wires, led to invention of telephone <br/>
Microphone converts voice into analogous electrical signal <br/>
Loudspeaker converts electrical signal back into sound <br/>
<br/>
**Dedicated Telephone networks**<br/>
    - in early days of telephony <br/>
    - dedicated lines between each pair of users (MESH topology) <br/>
    - need N(N-1)/2 lines for N users <br/>
    - very costly <br/>
<br/>
**Circuit switch telephone networks** <br/>
    - patch cord panels + human operators [1878]<br/>
    - **only N lines to central operator for N user** <br/>
    - Operator connects users on demand, establishes switch circuits to connect two lines <br/>
    - this tranfser mode of a network that involves setting up a **dedicated end-to-end connection** is called **circuit switching** <br/>
    - By 1890s the patch panel switches were replaced by **automated switches** that could take signal that contained the destination telephone number <br/>
        and automatically establish a cirtuit to the destination telephone <br/>
<br/>

**Problem of the dedicated connection** <br/>
<br/>
One source to destination is connected somehow, but there is a still problem there: <br/>
1. Delay is always there <br/>
2. number of subscribers <br/>
3. If the source becomes silence, all the data is bursty (a lot of packets then there is some silence). **Source utilization efficiency really goes down** <br/>
<br/>

**Digital telephone system**<br/>
<br/>

1. evolution began with the invention of the transistor (in 1948) and the integrated circuits(in 1960s) <br/>
2. converts analog voice into digital signal (a binary sequence) => better transmission <br/>
3. converts analog switch into digital switch => fast switching <br/>
<br/>

**Public switched telephone network**(PSTN) <br/>
1. current wired telephone network  <br/>
2. computer control for setting up a connection in a switch <br/>
3. a hierarchical network structure  <br/>
<br/>

**Hierarchical Network Structure of PSTN** <br/>
<br/>
![Image Alt MemoryLayout](/assets/network7.png) <br/>
- Toll is required (international call) <br/>
- (AREACODE) - (ExchangeCode) - (Unquie ID) 647-xxx-xxxx <br/>
- CO: same neighborhood, call go to the local central office and connect directly <br/>
- Tandem Office: another part of town, call go to central office and routed to tandem office and routed to the central office and routed to opponent  <br/>
- Toll Office: another city or state, tandem office connect to toll office and call would be switched from there <br/>
- International gateway: if you are in a different country from your recipient, call would be routed to international gateway to connect <br/>
<br/>

**When a resident uses a dial up or DSL service to connect to the Internet, what is the role of the telephone company? **<br/>
    - Do nothing except for circuit switching <br/>
<br/>
**PSTN vs ISDN** <br/>
<br/>
ISDN(Integrated Service Digital Network) was developed for the digital transmission of data and voice over ordinary phone lines. <br/>
ISDN provides better voice quality than PSTN <br/>
The ISDN provides 128 Kbps <br/>
ISDN integrates both speech and data in the same line, which is not available with ordinary telephone wires <br/>
Users can make faster calls with ISDN than with PSTN <br/>
<br/>
**PSTN vs VOIP** <br/>
<br/>
VOIP = IP telephny, broadband telephony or Internet telephony, means voice commincation is transmitted over the internet or private wide ware network (WAN) service <br/>
VOIP eliminates the need for circuit-switched-networks for phone calls <br/>
VOIP uses codecs to turn audio into data packets, transmits them across the network and turns the packets back into audio on the receiving end of them <br/>
VOIP has advantages over PSTN, including lower network infrastructure costs, scalability and advanced features, such as unified communications and app integrations <br/>
VOIP can lose the pixels or voice loss <br/>
<br/>
**Mobile Telephone Networks** <br/>
<br/>

![Image Alt MemoryLayout](/assets/network8.png) <br/>
- MS: Mobile handset <br/>
- BTS: Mobile phone -> BTS (Base transceiver station): A cell is formed by the coverage area of a Base Transceiver Station which serves the MS in its coverage area <br/>
- BSC: BaseStation controller contorls the BTS<br/>
- BSS: BSC + BTS (Subsystem), combine traffical mobile station <br/>
- MSC: Combined traffic of the mobile station in their respective cells is routed through a switch<br/>
- GMSC: PSTN connected to that <br/>

