<h2>Project Walk-through</h2>

<p align="center">
Network Diagram: <br/>
<img src="images/01-network-diagram.png" height="80%" width="80%" alt="Network diagram"/>
<br />
<br />

<h2>LLMNR Poisoning using Responder in Kali Linux to acquire a hash value from the victim:</h2>

## Usage:
    sudo responder -I eth0 -dPv

<br />
<br />

<p align="center">
LLMNR Poisoning using Responder: <br/>
<img src="images/02-responder-capture.png" height="80%" width="80%" alt="Responder capture"/>
<br />
<br />

Victim signs in with credentials: <br/>
<img src="images/03-victim-authentication.png" height="80%" width="80%" alt="Victim authentication"/>
<br />
<br />

Responder receives hash value from victim: <br/>
<img src="images/04-captured-hash.png" height="80%" width="80%" alt="Captured hash"/>
<br />
<br />

Using Hashcat in Kali Linux, we crack the hash: <br/>
<img src="images/05-hashcat-result.png" height="80%" width="80%" alt="Hashcat result"/>
<br />
<br />

<h2>LLMNR Poisoning Mitigation Techniques:</h2>

Disable Multicast Name Resolution in Group Policy Editor: <br/>
<img src="images/06-group-policy-mitigation.png" height="80%" width="80%" alt="Group Policy mitigation"/>
<br />
<br />

Disable NetBIOS over TCP/IP in Network Connections: <br/>
<img src="images/07-netbios-hardening.png" height="80%" width="80%" alt="NetBIOS hardening"/>
<br />
<br />

Post-mitigation validation: <br/>
<img src="images/08-post-mitigation-validation.png" height="80%" width="80%" alt="Post-mitigation validation"/>
<br />
<br />
</p>
