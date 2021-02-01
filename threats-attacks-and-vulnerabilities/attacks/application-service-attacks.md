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

### Zero-Days

Zero-Days are vulnerabilities that do not have a patch yet. The name alludes to the number of days the software/hardware developer has had to address it. 

### Buffer Overflow

A Buffer Overflow is when an attacker provides more data than what a program was expecting. For example, imagine a program that creates a buffer in memory 10 characters in size. Said buffer is designed to save the letters of your first name. If you provide a name that's 11 characters long, the program will crash. This is a Buffer Overflow. Buffer Overflows are often used for Privilege Escalation. 

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

