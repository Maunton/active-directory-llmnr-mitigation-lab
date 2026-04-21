<h1>LLMNR Poisoning and Mitigation</h1>



<h2>Description</h2>
Link-Local Multicast Name Resolution (LLMNR) is a protocol used in the Domain Name System (DNS) to resolve the NetBIOS names of neighboring computers. It operates in a local network environment and is primarily intended as a fallback mechanism when the standard DNS resolution fails.

However, LLMNR has vulnerabilities that can be exploited by malicious actors for various attacks, one of which is LLMNR poisoning. LLMNR poisoning occurs when an attacker intercepts LLMNR queries and responds with spoofed information, redirecting legitimate traffic to malicious destinations. This can lead to various security risks, including man-in-the-middle attacks, credential theft, and unauthorized access to sensitive information.
  
By understanding the vulnerabilities associated with LLMNR and implementing appropriate mitigation strategies, organizations can enhance the security posture of their networks and protect against potential attacks targeting this protocol.





<br />


<h2>Tools and Commands Used</h2>

- <b>Responder</b>
- <b>Hashcat</b>

<h2>Environments Used </h2>

- <b>VirtualBox VM</b>
- <b>Kali Linux</b>
- <b>Windows 10</b>
- <b>Windows Server 22</b>
- <b>Ubuntu Server 22.04</b>

<h2>Project walk-through:</h2>

<p align="center">
Network Diagram: <br/>
<img src="https://01-network-diagram.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
  
<h2>LLMNR Poisoning using Responder in Kali Linux to acquire a hash value from the victim:</h2>

## Usage:
    sudo responder -I eth0 -dPv
<br />    
<br />
<p align="center">
LLMNR Poisoning using Responder: <br/>
<img src="https://02-responder-capture.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
Victim signs in with credentials: <br/>
<img src="https://03-victim-authentication.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
Responder receives hash value from victim: <br/>
<img src="https://04-captured-hash.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<p align="center">
Using hashcat in Kali Linux, we decrypt the hash: <br/>
<br />
<br />  

## Usage:
    hashcat -m 5600 hash.txt ~/Desktop/ad-project/passwords.txt

<p align="center">
<img src="https://05-hashcat-result.png" height="80%" width="80%" alt="Project walk-through"/>
<br />  
<br />
The users password is then revealed: <br/>
<img src="https://06-group-policy-mitigation.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
  
<h2>LLMNR Poisoning Mitigation Techniques:</h2>  

<p align="center">
Disable Multicast Name Resolution(MNR) in Group Policy Editor: <br/>
<img src="https://07-netbios-hardening.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
Disable 'NetBIOS over TCP\IP' in Network Connections: <br/>
<img src="https://08-post-mitigation-validation.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />  
</p>


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
