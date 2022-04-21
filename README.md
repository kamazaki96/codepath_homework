# Project 9 - Pentesting Live Targets

Time spent: **5** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:

* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each color is vulnerable to only 2 of the 6 possible exploits. First discover which color has the specific vulnerability, then write a short description of how to exploit it, and finally demonstrate it using screenshots compiled into a GIF.

## Blue

Vulnerability #1: SQL Injection

Description: The Blue target website is vulnverable to SQL Injection attack. An attacker is easily able to inject a SQL command in to the website and can do many things with the databse, like viewing sensitive information, or in this case putting the database to sleep. This can result in denial of service(DoS). 

<img src="sqli.gif">


## Green

Vulnerability #1: User Enumeration

Description: The Green target website is vulnerable to User Enumeration. An attacker can try to insert different username and password, and the system will respond back with an error that is very specific, telling the attacker what he is doing wrongly. On an incorrect username, the system respond back with normal font, but with a right username, it responds back with bold text. 

<img src="UserEnumeration.gif">


## Red

Vulnerability #1: Insecure Direct Object Refrences (IDOR)

Description: The Red Target website is vulnerable to IDOR attacks. The target website stores its employee information in the database and had assigned a very simple counter ID to each of its employee, which is not a good idea since its make URL manipulation exteremly easy. A person dont need a ton of technical knowledge in order to conduct this type of attack. Through URL manipulation, people might be able to see information, that wasnt intended to be seen. 

<img src="IDOR.gif">



