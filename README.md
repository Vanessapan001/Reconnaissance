
# Reconnaissance

### 01. Gaining Initial Access 

We have several passive reconnaissance tools, such as Google dorking and Shodan, to gather information about our target.

   - That information can be used to gain initial access into our target.
     - For example, perhaps through Google dorking you find an employee name and that person's job title, direct reports, and email address. You could use that information to craft a deceptive email to try and obtain the employee's credentials for their private network.

MITRE defines **initial access** as follows:
   - *Initial access consists of techniques that use various entry vectors to gain their initial foothold within a network. Techniques used to gain a foothold include targeted spear phishing and exploiting weaknesses on public-facing web servers. Footholds gained through initial access may allow for continued access, like valid accounts and use of external remote services, or may be limited-use due to changing passwords.*
   - Initial Access is a MITRE tactic, **ID TA0001**: https://attack.mitre.org/tactics/TA0001/.

In this section, we will cover two methods of gaining initial access to a target machine or network: 

- **1.** **Phishing**: The most common method, in which the attacker crafts a fraudulent email that misleads the recipient into clicking on a link in the email. 
- **2.** **Remote services through valid accounts**: This method involves gaining access to the target by guessing credentials on a VPN login portal. These techniques are categorized by MITRE as Valid Accounts and External Remote Services. 

We will explore both of these methods, and then you will attempt to gain access to a target via a password guessing method. 
   - Phishing: https://attack.mitre.org/techniques/T1566/
   - Valid Accounts: https://attack.mitre.org/techniques/T1078/
   - External Remote Services: https://attack.mitre.org/techniques/T1133/

Note that initial access commonly becomes the longest tactic time-wise, due to the limited number of avenues at the pentesters' disposal.

-  In a full-view pentest or red-team engagement, initial access is often ceded or granted at the start of the assessment to avoid spending long amounts of time gaining initial access.

#### Phishing 

**Phishing** is the most common way an attacker gains access to the internal network. 
  - MITRE’s Phishing page: https://attack.mitre.org/techniques/T1566/.

The goal of phishing can vary.
- Sometimes a phishing email is sent only to obtain credentials.  
- Other times, the email contains a malicious link that will install malware or a backdoor on the victim's computer.

Phishing is more like a social engineering exercise than a technical abuse.
- Unlike other attacks, phishing leverages human error by crafting misleading and convincing fraudulent emails.  
- Therefore, there is no “patch” to prevent phishing. 
- An organization’s best defense against phishing is knowledge. Users should be required to complete “security awareness” training.  Upon completion, users will be able to identify phishing attempts.

Typos in the body of the email and the sender’s email address are common flags. 
- **Typosquatting** is a common tactic in which an attacker will register a fraudulent domain similar to a legitimate one. 
   - E.g.: Google.com vs. GoogIe.com (The second domain has a capital "i" instead of a lowercase "l").
- Subdomains are often registered to mimic real domain names.
   - E.g.: payments.google.com vs. paymentsgoogle.bogusdomain.com
   - Remember that domains can be spoofed if proper DNS protections are not in place.
- If an email asks you to do something that's not traditionally part of your job or that's possibly risky, it's always better to confirm the task in person or by another means of contact.

we can practice detecting the difference between authentic and phishing emails with the following online activity created by Google: [Google Phishing Quiz](https://phishingquiz.withgoogle.com/).

### 02.  Valid Accounts, External Remote Services, and Password Guessing 


Another way of gaining initial access is by finding a VPN configuration file belonging to the target and logging in to the VPN with stolen credentials. 

- This method leverages two techniques from MITRE:
  - [Valid Accounts](https://attack.mitre.org/techniques/T1078/) - The attacker uses real user accounts to gain access.
  - [Remote Services](https://attack.mitre.org/techniques/T1133/) - The attacker uses remote services such as VPN to try and gain access from outside of the target's network.

#### Summary

- **Initial Access** is a MITRE tactic covering methods for gaining access into a target's system.
- **Phishing** is the most commonly used initial access method. It leverages human error by crafting misleading and convincing fraudulent emails.
   - **Typosquatting** is a common tactic used with phishing in which an attacker will register a fraudulent domain similar to a legitimate one.
- **Remote Services through Valid Accounts** is another initial access method, where the attacker uses real user accounts to gain access through a remote service, such as VPN.
   - This method can be used in conjunction with **password guessing**, as users often have weak and commonly used passwords.



