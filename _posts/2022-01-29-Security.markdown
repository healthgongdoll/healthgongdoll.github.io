---
layout: post
title:  "Software Threats"
date:   2022-01-29 20:39:36 +0530
categories: Databse
---

### **Worms** <br/>

Malware actively seeks out more machines to infect and then each infected machines serves as an automated launching pad for attacks on other machines <br/>
   - Worms exploit(악용하다) software vulnerabilities(취약점) in client or server programs to gain access to a new system <br/>
      - **Worm** = power of virus + convenience of interent <br/>
   - **Virus vs. Worm** <br/>
      - Viruses need a carrier medium (document or program to 'attach' itself to) and then require user action to propagate <br/>
      - Worm do not always need a carrier (can sometimes 'move' on their own), are typically spread through the interent, and Never rely on user action to replicate <br/>
      -  Virus attaches itself to a piece of an existing software or file if you will and a worm, effectively, its a standalone running on itself, kind of an amount of our application. it uses different technique to spread it self through the internet, it does not require any actions <br/>

<br/>
<br/>

**Classification of Worms by replication strategy** <br/>
<br/>

1. **Electronic mail or instant messaging:** worms emails a copy of itself to other system, or sends itself as an attachment via an instant message service<br/>
2. **File Sharing:** worm copies itself on removable media such as USB drives; it, then, executes when the drive is connected to another system <br/>
3. **Remote execution capacbility:** worm exploits a flaw in a remote execution facility (program)<br/>
4. **Remote File access:** worm uses a remote file access or transfer service to another system to copy itself <br/>
5. **Remote Login Capability:** worm logs onto a remote system as a user and then uses commands to copy itself from one system to another <br/>
6. **Random:** each compromised host probes random addresses in IP address space - fast process but <br/>
   - UnKnown Resutls (many machines may not be vulnerable)<br/>
   - Same machine may be probed n-x<br/>

7. **Hit List:** The attacker complies a long list of potentially vulnerable machines, each infected machine uses a part of this list - time consuming <br/>
8. **Topological:** Worm uses information contained on the infected machine to find more hosts to scan <br/>
   - Eg. Worms infecting / exploiting P2P applications <br/>

9. **Local Subnet:** Worm uses the subnet address to find other vulnerable machine on the same network <br/>



<br/>
<br/>

**State of Worm Technology**<br/>
<br/>

- **Multiplatform** - target a variety of platforms <br/>
- **Multi-exploit** - penetrate system in a variety of ways (through emails, browsers, file sharing,...)<br/>
- **Ultra-fast spreading** - Uses various techniques to identify as many vulnerable machines in a short period of time <br/>
- **Polymorphic** <br/>
- **Metamorphic** <br/>
- **Multi 'transport vehicle'** - can carry a variety of payloads <br/>
- **Zero day exploit** - try to exploit new/unknown vulnerabilities (exploit is a vulnerability of software that is not known to the general population). These exploits are help worm to spread through network <br/>


<br/>
<br/>


**Zero-Day Attack (Software Attack)**<br/>
<br/>

Attack that exploits a previously unknown vulnerability in a computer application or OS (patch not available)<br/>
![Image Alt MemoryLayout](/assets/s.jpg.png) <br/>
<br/>
 
 - From the time that a feature is introduced into a software<br/>
 - **Window of exposure:** that is the time that vulnerabilities in the system and an exploits some echnique or a code or a piece of a script that could misuse that vulnerability can effectively perform the malicious act in this time window. Because the patch is not released <br/>
 - Zero day is the time that vulnerability is discovered until it disclosed to the public (you can not take an action about things that you do not know.) By the time it gets disclosed to the public, Now the manufacturer or the software producer they have the time to fix the vulnerability <br/>
<br/>
<br/>

**Vulnerability vs Exploits**<br/>
<br/>

**Vulnerability** is the weakness of your software <br/>
**Exploit** is tool that takes weakness and exploits<br/>
<br/>
<br/>

**Trojan Horse (Require action of User)**<br/>
<br/>

- Malware that looks legitimate and is advertised as performing one activity but actually does something else; **IT DOES NOT SELF-REPLICATE** <br/>
- EX: AOL4Free - advertised free access to AOL Internet Service: Would delete hard drive <br/>
- **Common Types of Trojans:** <br/>
   - **Remote access** - designed to give an attacker control over a victim's system <br/>
   - **Data sending** - desgined to capture and redirect data (key strokes, passwords... to an attacker) <br/>
   - **Destructive** - designed to destroy data or kill the system <br/>
   - **Denial of Service** - designed to conduct a DoS attack on a predefined IP address <br/>
   - **FTP** - designed to set up the infected system to serve as an FTP server for illegal software, pirated movies and music, etc. <br/>

**Examples:** <br/>
- Trojan for "Legitimate Purpose" <br/>
   - In 2002, FBI Identified a pair of Russian hacker who had stolen thousand of credit numbers to make purchases on eBay and defraud PayPal. In order to obtain the necessary evidence. FBI created a Trojan which was then successfully implanted on the hacker's computer <br/>
- **Common techniques of Trojan Detection:** <br/>
   - **On the infected computer** - RUN netstat and look up for unusual ports and connection <br/>
   - **From the infected network** - scan the network with nmap and look for system with unusual open ports. <br/>
<br/>
<br/>


