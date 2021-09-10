---
layout: post
title:  "Network Introduction"
date:   2021-09-09 17:00:36 +0530
categories: Network
---

### **Data Communication** <br/>


 Data communication is the **exchange of data between two devices** via some **Transmission Media.** Four Characteristics are: <br/>
	- **Delivery:** send data to correct destination <br/>
	- **Accuracy:** Analog Data, Digital Data (Microphone, Keyboards) <br/>
	- **Timeliness:** Data to be on time (Time sensitive: Electronic Gaming, Zoom, Web Surfing, Time insensitive) <br/>
	- **Jitter:** Variation in the packet arrival time <br/>
	(One packet is comming 30s, 40s, 50s,... It is the **Variation time of those delays** (Not the Delays)) <br/>
Without these 4 characteristics of Communication data is useless <br/>
<br/>
**Components**<br/>
A data communications system has **five components**: <br/>
1. Message <br/>
2. Sender <br/>
3. Receiver <br/>
4. Transmission Medium <br/>
5. Protocol <br/>

![Image Alt MemoryLayout](/assets/network1.png) <br/>
<br/>
**Message** <br/>
Information today comes with different form of text, numbers, images and videos.<br/>
	- **Text** is represented as a **bit pattern using UNICODE** (Translate character to Unicode bit Pattern 32bit per Character) <br/>
	- **Numbers** are represented in **binary** <br/>
	- **Images** are represented as bit patterns using either **RGB or CMY**<br/>
	- **Audio** refers to the **recording or broadcating** of sound or music, represented as analog or digital signals <br/>
	- **Videos** can be **continous images** or a **combination of images** <br/>  
<br/>
**Data Flow**<br/>
Communication between two devices can be **simplex**, **half-duplex**, and **Full duplex** <br/>
![Image Alt MemoryLayout](/assets/network2.png) <br/>

**Simplex**: One-Direction communication that only one of the two connected devices can send or recieve <br/>
Example: Keyboard, Monitor <br/>
**Half-Duplex**: each station can send or receive, but not at the same time <br/>
Example: Woki Toki<br/>
**Full-Duplex**: both station can send or receive at the same time <br/>
Example: Phone<br/>
<br/>
**Networks**<br/>
**Networks** is the **interconnection of a set of devices** capable of communication (Computers, Laptop) <br/>
**Device** can be **host** (Desktop,Laptop,Workstation,Phone)<br/>
**Device** can also be a **connecting device** such as (Router, Switch, Modem) <br/>
<br/>
**Network Criteria**
Network must be able to meet certain number of criteria:<br/>
1. Performance measured in many ways: <br/>
Transit time (amount of time required for message to travel from device to another)<br/>
Response time (elapsed time between an inquiry and a response)<br/>
2. Network Reliability is measured by: <br/>
Frequency of failure, the time it takes a link to recover from a failure, and network's robustness in a catastrophe <br/>
3. Network Security <br/>
protecting data from damage and development, and implementing policies and procedures for recovery from breaches and data loses<br/>
<br/>
**Types of Connection**<br/>
![Image Alt MemoryLayout](/assets/network3.png) <br/>

<br/>
**Physical Topology**<br/>
The physical topology is that the way in which a network is laid out physically <br/>
Four Basics Topologies: **Mesh**, **Star**, **Bus**, **Ring** <br/>
![Image Alt MemoryLayout](/assets/network4.png) <br/>
Mesh: N*(N-1)/2 , Star: N, Bus: N+1, Ring: N<br/>
<br/>
**Network Types** <br/>
Two types: **LANs** and **WANs** <br/>
<br/>
**Local Area Network**: privately owned and connecets some hosts in a single office, building or campus. <br/>
<br/>
**Wide Area Network**: Also conenction of devices capable of communication. A WAN has wider geographical span, spanning a town, a state, a country, even World. <br/>



	
