---
description: Compare and contrast types of attacks.
---

# Password Guessing

There's no such thing as password _cracking_. Either the attacker correctly guesses your password or they're able to uncover it using tactics like Social Engineering. Password guessing includes Brute Force, Dictionary, and Hybrid attacks. Each method represents how much the attacker is willing to invest in performing reconnaissance beforehand. Regardless, their success largely depends on if their guessing efforts are online or offline.

## Online vs Offline Guessing

Online password guessing is noisy and risky for the attacker. If the right cybersecurity controls are in place, the victim will get tipped off relatively quickly. Example controls are having a password lockout policy and multi-factor authentication. Offline guessing is only possible if the attacker is able to access and exfiltrate the database that contains username and passwords.

In a Microsoft Windows environment, this database is either the `SAM` file or the `NTDS.dit` file. The `SAM` \(Security Account Manager\) file is used to authenticate local user accounts like those on a stand-alone computer. `NTDS.dit` is used to authenticate domain-based or Active Directory user accounts. Both `SAM` and `NTDS.dit` files store the NTLM \(New Technology Local Area Network Manager\) hash version of the passwords they're given.

On a Linux computer the attacker must exfiltrate both the `passwd` and `shadow` files from the `/etc/` directory. `/etc/passwd` contains user information like their display name, username, home directory, and login shell. `/etc/shadow` contains the hash version of their password. Tools like John the Ripper and hashcat need both of these files to correctly Brute Force a user's password.

## Brute Force Attacks

Brute Forcing a user's password is when the attacker tries every possible combination as a guess until they're successful. The attacker can start with no information about the password or supply known characteristics like hash type, character classes, or length to her tool. As mentioned above, a password from a Microsoft Windows environment likely to be in a NTLM format while a password from a Linux computer might be MD5, SHA1, or SHA256. Upper-case, lower-case, letters, numbers, and symbols are all character classes. Length is self-explanatory, but it's important to understand why it's important.

It would not take very long to guess a password that has one character from every class. Yet, it would take much longer to guess a password that is 15 characters in length. This is because you \(or a computer\) would have to try every single character from each class in every position of the 15 character password \(and even then your success as an attacker is only possible because you know the length\).

## Dictionary Attacks

Dictionary attacks are successful when people user passwords commonly found in a dictionary. The process involves the attacker developing or downloading a list of words and then using the list as a look-up table to guess the victim's password. 

### Rainbow Tables

Like Brute Force attacks, Dictionary attacks can also be a slow password guessing technique. To speed up the process of selecting a plain-text password from a list, hashing it, and then trying it as a guess attackers will often use Rainbow Tables. Rainbow Tables are made ahead of time and include plain-text passwords along with their hash. By computing a password's hash ahead of time, the attacker greatly reduces the time required to guess. In practice, an attacker will create or acquire a Rainbow Table once and then maintain/use it on every mission from that point forward. 

{% hint style="info" %}
If you hashed a single password using multiple algorithms and then assigned one color to each result, it would like a rainbow. 
{% endhint %}

## Hybrid Attacks

Attackers can increase their chance for success by using different word permutations and focusing their attention on words relating to their target. This technique is consider a Hybrid attack. For example, imagine someone who likes football and was born in 1984. An attacker might then try football1984, f00tball1984, f00tb@ll1984, etc. In theory this should still take less time than outright guessing individual letters.

{% hint style="warning" %}
Most people prefer to include context in their passwords. This is makes it easier for both them and their would be attacker. As a cybersecurity professional, your intent should always be to strike a balance between security and usability. If you enforce super complex and long passwords, users will be tempted to write them down on a sticky note. Instead enlighten them with techniques like passphrases.
{% endhint %}

{% hint style="success" %}
Passphrases are sentence-long passwords like "iLoveCyberSecurity!AndItLovesMeT00!"
{% endhint %}

Collisions

The Birthday Paradox

Known Text

Known Plain-Text

Known Cipher-Text

Replay

Weak Implementations

Downgrade Attacks

