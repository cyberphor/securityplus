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

![](../../.gitbook/assets/014-hacker.png)

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

![PTH is when an attacker authenticates with a hash instead of a password.](../../.gitbook/assets/012-hash.png)

### Privilege Escalation

Privilege Escalation is when an attacker uses low-level access to a system to gain high-level access. One way of doing this is by invoking programs that run with administrator privileges and hijacking them in memory. 

### Zero-Days

Zero-Days are vulnerabilities that do not have a patch yet. The name alludes to the number of days the software/hardware developer has had to address it. 

### Buffer Overflow

A Buffer Overflow is when an attacker provides more data than what a program was expecting. For example, imagine a program that creates a buffer in memory 10 characters in size. Said buffer is designed to save the letters of your first name. If you provide a name that's 11 characters long, the program will crash. This is a Buffer Overflow. Buffer Overflows are often used for Privilege Escalation. 

### Shimming

Shimming is when attackers use drivers to exploit software compatibility issues. The word "shim" means to fill a gap, put something in-between, or level something off-balance. Loading additional drivers is often the fix when a program is unable to run. One method of mitigating shimming attacks is ensure your drivers are digitally-signed by a vendor you trust. 

### Refactoring

Attackers will routinely refactor the malware they develop to evade detection. Factoring is a technique used to represent a complex solution to a problem in small parts. Take a car as a metaphor. Cars solve the problem of getting from one place to another. Refactoring a car may involve moving the front wheels to the back and vice versa. In the end, the car still gets you to your destination albeit it's a different design. The same goes for malware. An attacker may redesign their malware to make it unrecognizable to anti-virus programs. 

## Against the Web

![](../../.gitbook/assets/016-www.png)

### Cross-Site Scripting

Cross-Site Scripting \(XSS\) is when an attacker stages and launches an attack from a website that accepts input. The attack is not against the server hosting the website, it is against anyone who visits the website. These kind of attacks are described as _client-side attacks_ as opposed to _server-side attacks_. Prime candidates for XSS attacks are social media platforms like blogs and message boards. These attacks work because of the way web browsers render HTML \(Hypertext Markup Language\) files and JavaScript code. 

Websites with static information are written in HTML and consist of elements like `<h1>` and `</h1>`  tags. Think of static information like restaurant menus, phone numbers, and the names of business owners. If someone wanted to display dynamic content, they would add JavaScript to their HTML code. Dynamic content might be weather notifications, online puzzles, etc. HTML organizes JavaScript code using `<script>` and `</script>` tags. Although, the browser doesn't care what kind of data is served. It will render anything it recognizes. 

Other conditions that allow XSS attacks to happen are when websites fail to validate input \(block special characters like those found in `</script>` tags\). I mentioned blogs before, let's use those as an example. Blog owners may wish to accept input so readers can comment and provide feedback. Yet, what if instead of sharing praise an attacker typed malicious code written in a language like JavaScript? Anyone visiting the blog would then fall prey to the perpetrator's XSS attack. As a security professional, you must be cognizant of possible avenues of approach an attacker may take, especially public-facing ones like the web. 

### Cross-Site Request Forgery

-

### Injection

-

### Man-in-the-Browser

Malicious web browser add-ons.

### Domain Hijacking

Taking a domain name from the original registrant. This can happen via Social Engineering or complacency. For example, if you fail to monitor when your domain name registration ends, someone could purchase it and hold it for ransom \(how much are you willing to pay for your reputation online?\). 

### Click-Jacking

Getting a user to click on something that appears benign but is actually malicious. For example, a button on a website might say "Click here for free beer!" Unbeknownst to the user, the button is a link to a malicious server. 

### Session Hijacking

-

### URL Hijacking

URL Hijacking is when an attacker registers a domain name of a topic that is expected to garner a lot of attention. For example, say there's a rumor that Angelina Jolie will run for president in 2024. Someone might go buy `www.angelina4president2024.com` expecting to get a return-on-investment in the future. 

### Typo-Squatting

-

