---
description: Compare and contrast types of attacks.
---

# Wireless Communications

In this section, I cover wireless communication and how attackers use this medium to achieve their objectives. 

## Amplification

![](../../.gitbook/assets/mobile-unit%20%281%29.png)

To remain undetected, attackers will try to stay as far away from their target as possible. In the real-world, this would look like someone using binoculars. In cyberspace, this is someone beefing-up their hacking rig to include a high-powered antenna that can reach greater distances than the one that came with their laptop or cellphone.

## Replay Attacks

Replay attacks are when the attacker sniffs the network, steals credentials, and uses them to gain access. Since the credentials are being presented again "as is" they are being _replayed_. Another closely-related concept is Pass-the-Hash \(PTH\). I cover PTH attacks in the section called, "Services & Applications."

## Interference

Interference is when a transmitter and receiver are unable to wirelessly communicate with each other. When Interference is intentional, it is considered Jamming. 

### Jamming

Attackers are often successful in Jamming wireless communications when they're able to get their equipment to transmit a high-powered signal on the same frequency as their target. If the attacker's signal is able to cancel out their victim's, they have effectively achieved a Denial-of-Service \(DoS\) attack. Another form of Jamming is using Disassociation. 

### Disassociation

![](../../.gitbook/assets/wifi-signal.png)

By design, Disassociation is an option for wireless devices when they no longer wish to communicate with an Access Point \(AP\). Attackers know this and will often seek to \(1\) find out their target's wireless MAC address, \(2\) spoof it, and \(3\) send Disassociation requests to the AP on the victim's behalf. As a cybersecurity professional, enforcing stronger authentication is one technique for mitigating this attack. If this speaks to you, consider implementing the IEEE 802.11w standard across your organization. It includes frame protections not inherent to previous iterations of IEEE 802.11. 

## Rogue APs

Attackers use Rogue APs in order to wirelessly extend the already-existing, wired network. The benefit of doing so allows them to bypass various network access controls and enter the network without being in close-proximity. Your organization should have a policy that prohibits personnel from connecting networking equipment without proper authorization. 

### Evil Twins

An Evil Twin is also a Rogue AP albeit they go one step further by spoofing a known-good AP. In addition to performing logical network scans to detect Rogue APs, ensure to physically inspect equipment on a routine basis.  

## WPS Attacks

WPS, or Wi-Fi Protected Setup, is an alternative method of authenticating to an AP for the first time. Normally, you would specify the network, provide a password, and from that point forward your computer and AP would use the password to exchange/encrypt wireless communication. Yet, what about the non-technical folks who just cannot be bothered to remember their Wi-Fi password? This is the gap WPS was designed to fill. WPS is a service on the AP that will prompt the user for a PIN and then give their computer the Wi-Fi password. WPS attacks are when the attacker brute forces the PIN. 

## PAN Attacks

Most of the attacks above pertain to Wireless Local Area Networks \(WLANs\). As a cybersecurity professional, you must also be aware of what an attacker might do when they "close the distance" between themselves and their target. 

### Bluetooth

Bluetooth was designed to facilitate Personal Area Networks \(PANs\). 

#### Bluejacking

Sending unsolicited messages.

#### Bluesnarfing

Stealing data. 

### RFID

Radio Frequency Identification

### NFC

Near-Field Communication

