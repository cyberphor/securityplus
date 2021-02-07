---
description: Compare and contrast types of attacks.
---

# Password Guessing

There's no such thing as password _cracking_. Either the attacker correctly guesses your password or they're able to uncover it through Social Engineering. Password guessing includes Brute Force, Dictionary, and Hybrid attacks. Each method represents how much the attacker is willing to invest in performing reconnaissance beforehand. Regardless, their success largely depends on if their guessing efforts are online or offline. 

## Online vs Offline Guessing

Online password guessing is noisy and risky for the attacker. If the right cybersecurity controls are in place, the victim will get tipped off relatively quickly. Example controls are having a password lockout policy and multi-factor authentication. Offline guessing is only possible if the attacker is able to access and exfiltrate the database that contains username and passwords. 

In a Microsoft Windows environment, this database is either the `SAM` file or the `NTDS.dit` file. The `SAM` \(Security Account Manager\) file is used to authenticate local user accounts like those on a stand-alone computer. `NTDS.dit` is used to authenticate domain-based or Active Directory user accounts. Both `SAM` and `NTDS.dit` files store the NTLM \(New Technology Local Area Network Manager\) hash version of the passwords they're given. 

On a Linux computer the attacker must exfiltrate both the `passwd` and `shadow` files from the `/etc/` directory. `/etc/passwd` contains user information like their display name, username, home directory, and login shell. `/etc/shadow` contains the hash version of their password. Tools like John the Ripper and hashcat need both of these files to correctly Brute Force a user's password. 

## Brute Force

## Dictionary

## Hybrid

Collisions

The Birthday Paradox

Known Text

Known Plain-Text

Known Cipher-Text

Replay

Weak Implementations

Downgrade Attacks

