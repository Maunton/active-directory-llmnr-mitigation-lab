## Project Walk-through

### Network Diagram
<p align="center">
  <img src="images/01-network-diagram.png" height="80%" width="80%" alt="Network diagram"/>
</p>

## LLMNR Poisoning with Responder

This phase demonstrates how LLMNR poisoning can be used to capture NTLM authentication material from a victim system in a controlled lab environment.

### Responder Command
```bash
sudo responder -I eth0 -dPv
```
## Attack Demonstration

### 1. Responder Capture
This screenshot shows Responder actively listening for LLMNR/NBT-NS traffic and preparing to capture authentication attempts from the victim system.

<p align="center">
  <img src="images/02-responder-capture.png" height="80%" width="80%" alt="Responder capture"/>
</p>

### 2. Victim Authentication
This step shows the victim attempting to authenticate, which triggers the poisoned name resolution workflow in the lab.

<p align="center">
  <img src="images/03-victim-authentication.png" height="80%" width="80%" alt="Victim authentication"/>
</p>

### 3. Captured Hash
Here, the victim's NTLM hash is captured by the attacker system using Responder.

<p align="center">
  <img src="images/04-captured-hash.png" height="80%" width="80%" alt="Captured hash"/>
</p>

### 4. Hashcat Result
This screenshot demonstrates the captured hash being cracked with Hashcat to reveal the underlying password.

<p align="center">
  <img src="images/05-hashcat-result.png" height="80%" width="80%" alt="Hashcat result"/>
</p>

## Mitigation and Hardening

### 5. Group Policy Mitigation
This image shows the Group Policy setting used to disable multicast name resolution and reduce the risk of LLMNR poisoning.

<p align="center">
  <img src="images/06-group-policy-mitigation.png" height="80%" width="80%" alt="Group Policy mitigation"/>
</p>

### 6. NetBIOS Hardening
This step disables NetBIOS over TCP/IP to further reduce legacy name resolution exposure within the environment.

<p align="center">
  <img src="images/07-netbios-hardening.png" height="80%" width="80%" alt="NetBIOS hardening"/>
</p>

### 7. Post-Mitigation Validation
This final screenshot confirms that the mitigation steps were applied and the attack path was reduced or blocked.

<p align="center">
  <img src="images/08-post-mitigation-validation.png" height="80%" width="80%" alt="Post-mitigation validation"/>
</p>
