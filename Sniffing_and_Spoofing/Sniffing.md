Packet sniffing allows a person to observe and access the entire network’s traffic from a given point. It monitors any bit of information entering or leaving the network.

### Types of sniffing
- Passive: sniffing on hub-based networks.
- Active: sniffing on switch-based networks. (More common)

### Protocols
-  HTTP
- FTP
- SMTP
- POP
- Telnet
- IMAP
- NNTP

---
## Active Sniffing
ARP traffic is actively injected to a LAN to sniff.
- **MAC flooding**: flooding the CAM table with fake MAC-IP pairs to fill it
- **DNS poisoning**: tricks a DNS server
- **ARP poisoning**: Overloads a switch
- **DHCP attack**: DHCP starvation and Rogue DHCP 
- **Switch port stealing**: floods the switch with with forged ARP packets with the target MAC as source
- **Spoofing attack**: MAC spoofing, VLAN hopping, STP attacks

### MAC flooding with macof
1. Open Wireshark
2. Select network interface and open terminal

```
macof -i [INTERFACE] -d [TARGET IP] -n [NUMBER OF PACKETS TO SEND]
```
this will start flooding the CAM table

3. in Wireshark we can see IP packets from random IPs, it's also possible to gather information in detail for each packet

### DHCP Starvation Attack using Yersinia
1. Open Wireshark
2. Select network interface and open terminal

```
yersinia -I
```
this will open yersinia in interactive mode
3. Press F2 to select DHCP mode.
4. Press **x** to list available attack options.
5. Press **1** to start DHCP starvation attack, press **q** to stop attack
6. In Wireshark we can see the captured DHCP packets

### ARP poisoning with arpspoof
1. Open Wireshark
2. Select network interface and open terminal
```
arpspoof -i [INTERFACE] -t [AP/GATEWAY IP] [TARGET IP]
```
this will send spoofed packets telling the AP that TARGET IP has our MAC address.
3. Repeat this operation inverting AP IP and TARGET IP
4. arpspoof tool can be used to obtain ARP cache; then the MAC address is replaced with that of the attacker. This way, any traffic from the victim to gateway is redirected to the attacker.

### MITM Attack using Cain & Abel
Cain & Abel is a password recovery tool that allows the recovery of passwords by sniffing the network and cracking encrypted passwords. The ARP poisoning feature of the Cain & Abel tool involves sending free spoofed ARPs to the network’s host victims. This spoofed ARP can make it easier to attack a middleman.

### MAC spoofing using TMAC and SMAC
1. Technitium MAC Address Changer is uselful to change the MAC address.
2. In SMAC tool we can choose a MAC address to spoof.

### MAC spoofing in Linux using macchanger
1. Close the connection on desired interface:
```
# ifconfig [INTERFACE] down
```
2. Set a random vendor MAC:
```
# macchanger -a [INTERFACE]
```
3. Set a completely random MAC:
```
# macchanger -r [INTERFACE]
```
4. Re-open connection:
```
# ifconfig [INTERFACE] up
```

---
