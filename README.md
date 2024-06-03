<h1>MITM with Ettercap</h1>

<h2>Description</h2>

<br />

<h2>Skills Obtained</h2>

- <b>Traffic Injection:</b> Ability to inject malicious payloads into intercepted traffic and Understanding of scripting and automation to facilitate traffic injection.
- <b>Network Analysis and Monitoring:</b> Ability to capture and analyze network traffic, Understanding of topologies, dataflow and network protocols (TCP/IP, ARP, DNS, etc.).
- <b>ARP Spoofing/Poisoning:</b>  ARP spoofing techniques to position yourself between the target devices and how ARP tables can be manipulated to redirect network traffic.
- <b>Packet Manipulation and DNS Spoofing:</b> Intercepting and modifying network packets in real-time, along with how DNS resolution works and how it can be exploited.
- <b>Credential Harvesting:</b> Techniques for capturing login credentials and sensitive data.
- <b>Session Hijacking:</b> Hijacking active sessions to gain unauthorized access to services and the Understanding of session management and cookies.
- <b>SSL/TLS Interception:</b> Intercepting and decrypting SSL/TLS traffic and knowledge of SSL strip techniques to downgrade HTTPS to HTTP.
- <b>Critical Thinking:</b> Anticipating and mitigating potential countermeasures and defenses and the ability to adapt tactics based on the target's environment and security environment.
- <b>End-User Training:</b> Ability to explain how the Pi-Hole works and its benefits to non-technical users.


<h2>Utilities Used</h2>

- <b>Ettercap</b> 
- <b>Wireshark</b>

<h2>Environments Used </h2>

- <b>Windows 11 VM</b> (the device to monitor)
- <b>Kali Linux</b> 

<h2>Project walk-through:</h2>

<p align="center">
Step 1: Open Ettercap after Updating repositories and libraries <br/><br/>
<img src="https://i.imgur.com/WRyi0yO.png" height="80%" width="80% alt="ettercap"/>
<img src="https://i.imgur.com/Mm9gX8M.png" height="80%" width="80%" alt="ettercap"/>
<br />
<br />
Step 2: Scanning for hosts connected to the network  <br/><br/>
<img src="https://i.imgur.com/wW1OSKq.png" height="80%" width="80%" alt="ettercap"/>
<br />
<br />
Step 3: Adding hosts to the targets - We'll add the victim to target 1 and the router to target 2 <br/><br/>
<img src="https://i.imgur.com/J25b4Pg.png" height="80%" width="80%" alt="ettercap"/><br/>
<img src="https://i.imgur.com/tQ0s7eE.png" height="80%" width="80%" alt="ettercap"/><br/>
  <img src="https://i.imgur.com/7nuSmAL.png" height="80%" width="80%" alt="ettercap"/>
<br />
<br />
Step 4: Open wireshark and analyze what’s happening on the network  <br/> by clicking on ARP poising, we can see that our interface has now became the gateway. (Via wireshark)<br/><br/>
<img src="https://i.imgur.com/WYKFhd4.png" height="80%" width="80%" alt="ettercap"/>
<img src="https://i.imgur.com/SujayvV.png" height="80%" width="80%" alt="ettercap"/>
<br />
<br />
It is visible that we can monitor the victim’s activities. (It can be seen that the victim was on youtube)  <br/><br/>
<img src="https://i.imgur.com/6pyrmox.png" height="80%" width="80%" alt="ettercap"/>
<br /><br/>
Step 5: If the victim visits an HTTP WEBSITE, We’ll be able to see their credentials because the text is not encrypted.  <br/>
1. navigate to http://testphp.vulnweb.com/login.php and login with any credentials  <br/><br/>
<img src="https://i.imgur.com/nTRLZwy.png" height="80%" width="80%" alt="ettercap"/><br/>
  <br/>
2. Go the to the hacker’s machine, check Ettercap   <br/><br/>
<img src="https://i.imgur.com/s5P4NOk.png" height="80%" width="80%" alt="ettercap"/><br/>
  <br/>
3. On Wireshark, filter “http” and find the packet   <br/><br/>
<img src="https://i.imgur.com/7qDdIMf.png" height="80%" width="80%" alt="ettercap"/><br/>
  <br/>
4. Or filter <b>http.request.method == "POST"</b> to get to it   <br/><br/>
<img src="https://i.imgur.com/7qDdIMf.png" height="80%" width="80%" alt="ettercap"/><br/>
  <br/>

  <h2 align=center>THANK YOU</h2>
