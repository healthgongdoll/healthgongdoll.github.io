---
layout: post
title:  "HackTheBox"
date:   2022-04-03 20:39:36 +0530
categories: Hacking
---

### **Linux Fundamentals** <br/>

If you are on the same Virtual Private Network (VPN) as the target, you can directly access it as any user would. If the target is a web server, running a public web page, you can navigate to its IP address to see what the page contains. If the target is storage server, you can connect to it using the same IP address to explore the files and folders stored on it, provided that you have the necessary credentials <br/>
   - Every server uses **ports** in order to serve data to other clients. We need to involve scanning these open ports to see the purpose of the target on the network and what potential vulnerabilities might appear from the services running on it <br/>
      - **nmap** = In order to quickly scan for ports <br/>
      - nmap stands for Network Mapper, and it will send requests to the target's port in hopes of receiving a reply, thus determining if the said port is open or not. </br>
      - After finding the open ports on the target, we can manually access each of them using different tools to find out if we have acccess to their contents or not. Different service will use different tools or scripts to be accessed. </br>
      - Some ports are used by default by certain services. Others might be non-standard, which is why we will be using the service detection flag **-sV** to determine the name and description of the identified services </br>
   - **ping {target_IP}** <br/>
      -  After our VPN connection is successfully established we can ping target IP address to see if our packets reach their destination.<br/>

<br/>
<br/>

![Image Alt MemoryLayout](/assets/hb1.jpg) <br/>
<br/>

**Telnet** <br/>
- Telnet is an old service used for remote management of other hosts on the network system. Since the target is running this service, it can receive telnet connection requests from other hosts in the network </br>
- Telent provides the security by using login/password (We can use bruteforce, other things)

<br/>
<br/>


