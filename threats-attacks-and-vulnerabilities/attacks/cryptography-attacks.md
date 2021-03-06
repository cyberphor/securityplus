---
description: Compare and contrast types of attacks.
---

# Password Guessing

I wrote this section to talk about Password Guessing. Although, the more I wrote, the more I felt like it was necessary to provide a quick review of important concepts one grasp before going further. 

## More Buzzwords

I've read a lot of cybersecurity books throughout my career and I like feel the best way to remember the following buzzwords is to categorize them as either a process or principle. For example, Identification, Authentication, and Hashing are processes, they are things you do \(the journey\). Confidentiality, Integrity, Availability, and Non-repudiation are principles, they are things you achieve \(the destination\). 

### Identification & Authentication

Identification is when you claim to be someone or something. Authentication is when you prove it. 

### Hashing

Hashing is feeding data into an algorithm to get a value that represents it. This value can be used to provide authentication, integrity, and non-repudiation. Think of hashing like paying for groceries and getting a receipt. Your groceries are data while your receipt is the hash. 

### Integrity

Integrity is achieved and maintained when something remains the same. For example, you might save a grocery list to always remember to buy coffee and root beer. The integrity of your grocery shopping is confirmed \(achieved\) whenever the receipt doesn't change. If the receipt does change, either you forgot to grab the coffee or the root beer or someone added something to your cart.  

### Non-repudiation

Non-repudiation is achieved when someone unable to deny they did something. For example, a security camera provides Non-repudiation because it proves someone did something.  

## Password Guessing

There's no such thing as password _cracking_. Either the attacker correctly guesses your password or they're able to uncover it using tactics like Social Engineering. Password guessing includes Brute Force, Dictionary, and Hybrid attacks. Each method represents how much the attacker is willing to invest in performing reconnaissance beforehand. Regardless, their success largely depends on if their guessing efforts are online or offline.

## Online vs Offline Guessing

I've read a lot of cybersecurity books throughout my career and I like feel the best way to remember the following buzzwords is to categorize them as either a process or principle. For example, Identification, Authentication, and Hashing are processes, or things you do \(the journey\). Confidentiality, Integrity, Availability, and Non-repudiation are principles, or are things you achieve \(the destination\). 

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
If you hashed a single password using multiple algorithms and then assigned one color to each result, it would look like a rainbow.
{% endhint %}

## Hybrid Attacks

Attackers can increase their chance for success by using different word permutations and focusing their attention on words relating to their target. This technique is called a Hybrid attack. For example, imagine someone who likes football and was born in 1984. An attacker might then try football1984, f00tball1984, f00tb@ll1984, etc. In theory this should still take less time than outright guessing individual letters.

{% hint style="warning" %}
Most people prefer to include context in their passwords. This is makes it easier for both them and their would be attacker. As a cybersecurity professional, your intent should always be to strike a balance between security and usability. If you require super complex and long passwords, users will be tempted to write them down on a sticky note. Instead enlighten them with techniques like passphrases.
{% endhint %}

{% hint style="success" %}
Passphrases are sentence-long passwords like "iLoveCyberSecurity!AndItLovesMeT00!"
{% endhint %}

## Other Attacks

### Hash Collisions

Hash Collisions are when different strings of data generate the same hash value. The MD5 hashing algorithm is known to be vulnerable to Hash Collisions. Avoid using it for anything that requires what is called "collision-resistance." For instance, anti-virus programs use hash values to recognize malicious software files. An attacker could bypass an anti-virus program if they're able to find a hash collision and get their malware to look benign instead of something known to be malicious. 

In your career, you may still see people who work in Digital Forensics & Incident Response use MD5 and other hashing algorithms vulnerable to hash collisions. This is that balance between usability and security I was talking about. MD5 has been around forever and gets the job done \(not to mention it's available in tool-form on almost every computer\). 

#### The Birthday Paradox

The Birthday Paradox is the idea that with enough people in one room, two of them are bound to have the same birthday. It's been said attackers can use this statistic to improve their success in finding Hash Collisions. 

### Known Plain-Text

Known Plain-Text attacks are when the attacker has both the plain-text and the cipher-text version of your password. The significance of this is the attacker can now begin deducing other passwords. To explain, imagine if I knew what your password was. I would count the length and identify the character classes. I would then also feed your plain-text password into my password guessing tools until I found a match to the cipher-text version of your password. This would help me learn which hashing algorithm is in use. If I am able to what password policy and hashing algorithm your organization uses, I can target anyone's account. 

### Known Cipher-Text

Known Cipher-Text is when the attacker only knows the cipher-text version of your password. For the attacker, this is difficult to work with if they specifically need the plain-text version. Scenarios were this might be true is if they learned the cipher-text version of your Instagram account, but they want to access your Snapchat. Regardless, having a bit of cipher-text is better than having nothing. They can still use this information to perform Replay attacks. 

### Downgrade Attacks

Downgrade attacks are when someone is able to get an authentication or encryption technology to fallback to a more vulnerable version. A well-known example is in found in web browsing. A browser will need to negotiate with their intended web server which encryption protocol they both support. If an attacker is able to convince the web server to use a vulnerable version they will be able to conduct surveillance and/or access sensitive information. 

### Weak Implementations

Weak Implementations of password security describe either a hashing algorithm or technology configuration \(such as conditions that allow Downgrade attacks to happen\). An example of a weak hashing algorithm is found on computers using the LAN Manager \(LM\) hashing algorithm. LM is incredibly vulnerable. It restricts passwords to 14 characters, changes the character class of all provided letters to upper-case, and splits the result into two separate hashes. Instead of guessing a 14 character-long password, the attacker only needs to guess seven characters at a time. To explain, consider the number of possible combinations of a 14 character password versus a seven character one. The attacker would have to try all special characters, A-Z, and 0-9 in each position. In short, they will come to a conclusion for a seven character password twice well before deducing a 14 character password.  

