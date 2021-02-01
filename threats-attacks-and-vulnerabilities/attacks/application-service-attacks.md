---
description: Compare and contrast types of attacks.
---

# Attacking Services & Applications

Attacks against services/applications seek to disrupt or manipulate client-server communications. They occur between systems, within systems, and against the web. As a security professional, you must be able to recognize them and reduce their impact. 

## Between Systems

### Generic Attacks

#### Denial of Service

#### Distributed Denial-of-Service

#### Man-in-the-Middle

#### Amplification

### Protocol-based Attacks

![Spoofing is when attackers disguise themselves as someone trustworthy.](../../.gitbook/assets/spoofing.png)

#### MAC Spoofing

#### ARP Poisoning

#### IP Spoofing

#### DNS Poisoning

## Within Systems

### Pass-the-Hash

Pass-the-Hash is when an attacker uses the hash of a victim's password instead of the actual credential to login. By doing so, the attacker eliminates the need to guess the plain-text version. An attacker will be able to learn a victim's password hash if it unencrypted and stored or sent across the network.  

### Privilege Escalation

Privilege Escalation is when an attacker uses low-level access to a system to gain high-level access. One way of doing this is by invoking programs that run with administrator privileges and hijacking them in memory. 

### Buffer Overflow

Attackers use Buffer Overflows

### Zero-Day

### Manipulating Drivers

#### Shimming

#### Refactoring

## Against the Web

### Cross-Site Scripting

### Cross-Site Request Forgery

### Injection

### Man-in-the-Browser

### Hijacking

#### Domain Hijacking

#### Click-jacking

#### Session Hijacking

#### URL Hijacking

#### Typo-squatting

