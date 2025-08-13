# 

| Encryption |
| :---: |

# Table of Contents {#table-of-contents}

[**Encryption	1**](#encryption)

[**Table of Contents	2**](#table-of-contents)

[**Executive Summary	3**](#executive-summary)

[**Strong Passwords	4**](#strong-passwords)

[**Password Expiration Policy	5**](#password-expiration-policy)

[**MFA (Multi-Factor Authentication)	6**](#mfa-\(multi-factor-authentication\))

[**Secure email with personal certificate	8**](#secure-email-with-personal-certificate)

[**VPN IPSec on Laptops	9**](#vpn-ipsec-on-laptops)

[**Encrypted hard drives/flash disks to protect portable/mobile devices	10**](#encrypted-hard-drives/flash-disks-to-protect-portable/mobile-devices)

[**Conclusion	11**](#conclusion)

# 

# 

# Executive Summary {#executive-summary}

Cyber Security is the practice of protecting devices, networks and programs from digital attacks. These attacks, known as cyberattacks, typically target sensitive data. They can access, alter or destroy that sensitive data or extort money by holding the data hostage, which is known as ransomware.\[1\]

As the attackers evolve with new methods, we as the defense for the company also need to update policies to keep our data secure. This report provides some methods to achieve the same. They are:

1. Strong Password: Weak passwords are some of the most vulnerable targets for hackers. Obtaining or guessing a weak password and login credentials can let attackers infiltrate systems, exfiltrate data and even escalate privileges to gain more power over the systems.  
2. Password expiration policy: Keeping the same password for a long period of time can increase the chances of that password being compromised. A password expiration policy that mandates updating passwords after a set period of time can help mitigate that risk.  
3. MFA (Multi Factor Authentication): MFA is an extra step required to login. It adds an extra layer of protection by not limiting the security to just a password. It can be implemented by a One Time Passcode delivered by SMS or authenticator applications.   
4. Secure email with personal certificate: Emails are the most preferred method of communication for most company work. Securing these emails by using personal certificates, also known as Secure/Multipurpose Internet Mail Extensions or S/MIME can help keep the conversations secure and confidential.  
5. VPN IPSec on the laptops: Data when transmitted over insecure networks can be intercepted by malicious agents. This is especially a problem when employees are working remotely. To combat this, it can be mandated to use a VPN IPSec connection to connect to company servers. This can make the communication private and secure.  
6. Encrypted hard drives/flash disks to protect portable/mobile devices: If there is any data that has to be moved through offline methods such as hard drives or flash disks, it is also vulnerable in case the devices are lost or stolen. To keep that data secure, encryption of that data will be mandatory. Encryption is the process of converting data to a ciphertext that can only be read if the receiving party has access to a key provided by the sender. Without this key, the data is gibberish to any other party.

Data is one of the most important assets of an organization. Protecting it is essential and the methods to do so are provided in this report.

# Strong Passwords {#strong-passwords}

Passwords are the most common way to authorize access to private data that is locked behind a login. Password cracking is a very common way for hackers to gain access to this data and passwords remain one of the most vulnerable targets for hackers.\[2\] Keeping these passwords strong can help in mitigating some of the risks associated with it.

Contrary to popular belief, just adding special characters does not have a significant effect on the efficacy of brute force attacks to compromise your passwords. The National Institute of Standards and Technology (NIST) provides some guidelines that can help with that.\[3\] These password guidelines say you should focus on length more and less on complexity when designing a password. Increasing the length of the password can significantly extend the time required to break it.\[2\] Just adding a single random character can add months, years or even centuries to the time required to brute force it.

Another good suggestion is to use a Password Manager. Password Managers have generators built into them that can generate long and strong passwords and passphrases for all the different logins a person needs.\[2\] The only password the person has to remember is the password for the manager. Password managers also seamlessly integrate into modern browsers which eliminates the need for a separate application.\[2\] They can also authenticate the user via the device’s own biometrics, such as fingerprint sensors on Macs and Androids and Face ID on iPhones. 

There will also be a system that will monitor what the new passwords are before they are created. The password field will have a strength meter which will provide a rating on how good a password is before it is set. We’ll also use a compromised passwords database to warn employees if the password they’re setting has been compromised before. This will provide more security by removing already leaked passwords from our employees’ accounts and will also prevent weak passwords like ‘123456’ from being used.

# Password Expiration Policy {#password-expiration-policy}

A password expiration policy can be implemented by an organization to enhance the protection of user accounts by requiring a periodical change to their passwords. The goal with this policy is to periodically change passwords and this can get rid of weak or compromised passwords.\[2\]

The most common range for expiration periods for the password range from 30 to 180 days\[2\], with Microsoft allowing a range from 14 to 730 days for their 365 enterprise accounts\[4\]. The user is notified a few days before it actually expires to give them ample time to create a new password. If it is not changed by the time the period expires, it can lead to a locking of the account or a mandatory change of password. 

The password system also keeps a history of previously used passwords which can help in preventing a reuse of an old password.\[2\] The complexity and length requirements from the previous section about “Strong Passwords” also applies to keep users from just setting a weak password. 

This system provides enhanced security as regularly changed passwords reduce the likelihood of unauthorized access, especially if a password has been compromised without the user’s knowledge due to phishing or social engineering attacks.\[5\] It also reduces risk of a long term exploit as a compromised password is only valid till the end of the expiration period.

In spite of all these advantages, there are some disadvantages to consider as well.\[2\] One of these is a frustration for the users of the frequent password changes. This can lead the users to make minor changes to their existing passwords like changing a single letter. It can also lead users to set weak passwords as they have to change it in the near future anyway. This is one of the reasons why NIST has recommended stopping this practice and only requiring a password change in the event of a suspected compromise.\[2\]\[3\] This can allow the users to set a long, complex password that will be much harder to break. 

Taking all of this into consideration, we have decided to implement the policy for now. It will be kept under observation and the results by the end of the year will determine if we’ll continue its use.

# MFA (Multi-Factor Authentication) {#mfa-(multi-factor-authentication)}

Multi Factor Authentication (MFA) requires two or more pieces of evidence to authenticate to a system. These can be a username and password and a token generated by a physical smart card or token generator.\[6\]  These tokens can be received by using an Authenticator application like Google Authenticator or Microsoft Authenticator or by sending the token to a verified means of communication like a phone number or an email.

The process of logging in when using MFA requires a step for each factor used to authenticate. The most common level is a 2-Factor Authentication(2FA) that requires 2 steps:

1. The first step is entering the correct username and password on the login page. If one of those is incorrect, the user is not allowed to move to the second step.  
2. The second step is to enter a token code, generally a 4 to 6 digit number, generated by an authenticator app. If the code entered by the user matches the code generated by the server, the user is logged in successfully.  
   

![Imgur](https://imgur.com/dL1S38w.png)
Google Authenticator app providing an authorization token

The token keeps updating every few seconds or minutes to make sure each code is unique and only valid for a short amount of time. If that code gets stolen or leaked, it makes it very difficult for attackers to gain unauthorized access.\[3\]

On modern devices, especially smartphones, there is also a robust way of using biometrics to enhance this security. Biometrics are ways to identify a person by distinguishing features of their body that are proven to be unique, like fingertips, facial scans or retinal scans. Almost every smartphone sold in the world today has at least one of these biometrics to help with unlocking the device only for the authorized user. 

![Imgur](https://imgur.com/JPFZeBS.png)
Google Authenticator App asking for biometric authorization before every login

We’ll be setting up this Authenticator token system by the end of this quarter. There are little to no downsides to this system of authorization. Our IT team will help everyone setup the Authenticator Apps on their devices and ensure the highest security is attained by mandating biometric sign in wherever possible.

# Secure email with personal certificate {#secure-email-with-personal-certificate}

Emails are the most common way of communication between the employees of any company. Keeping them secure is a significant step in keeping the company safe. This can be done by using digital signatures. They work the same as the signature of a person, it verifies the authenticity of a document.

The security capabilities provided by a digital certificate are:

* **Authentication**: Unsecured emails have no identifying features to verify if they’ve been sent by the actual sender. To counter this, a digital certificate provides a signature to validate the identity of the sender. This provides a verification that allows the receiver to know that the email was sent by the person or organization who claims to have sent the message.\[7\]  
* **Irrefutability:** Since the certificate is unique, the sender cannot later disown their signature. This can provide a protection similar to that of paper contracts. It would make anything written in them a legally binding document and you cannot go back on the same. This can be useful when dealing with suppliers and entities outside the organization.\[7\]  
* **Data Integrity:** A digital certificate can also provide the service of assuring the integrity of the data in the email. Any email sent with this certificate assures the receiver that the message has not been altered and anything written in it has come from the sender only. It provides a guarantee that the data has not been tampered with while in transit.\[7\]

When the email is sent using this certificate, it is encrypted using the sender’s public key and it is decrypted by using the intended recipient’s private key. This ensures that even if the email has reached the wrong party or has been intercepted, the contents of the email cannot be deciphered by the unauthorized party.\[8\]

All of this is provided by using a protocol known as Secure/Multipurpose Internet Mail Extensions (S/MIME) which is widely supported. To use this, the company will get in contact with a trusted certificate authority that can issue the digital certificate. When sending an email, the email can be signed by using this certificate and the certificate can act as a distinct digital stamp.\[8\]

This is a very good technology to use in business communications as it can protect sensitive information such as contracts, legal documents and financial documents. Information of this type is sent very regularly in our company environment and the possibility of it falling into the wrong hands can result in major losses.

# VPN IPSec on Laptops {#vpn-ipsec-on-laptops}

Normally, data transmitted over the internet is not secure, especially when using public networks. The data can be intercepted and deciphered by any attacker which can be harmful to the company’s Intellectual Property. To secure this connection, especially for employees who work remotely from any location, a Virtual Private Network (VPN) will be required to connect to the company servers.\[9\]

IPSec is a group of protocols used for securing connections. It works by setting up VPNs and encrypting Internet Protocol (IP) packets that contain the data to be transmitted. It also authenticates the source to make sure the device sending the packets is an authorized one. IPSec stands for Internet Protocol Security.

For our company’s network, we’ll be setting up the FortiGate VPN provided by industry standard creators of cyber security, Fortinet.\[10\] Our IT team will be setting up the connections for all the teams and they’ll set up the connection for any remote employee. Remote employees are required to present their devices by the end of this month to the IT Admin for this setup. From next month, the VPN will be required to connect to company servers.

The employees will have to set up their own username and password for logging in to the FortiClient application that will run the IPSec VPN connection. Once they have done that, the IT team will provide them with the remote gateway, which is the IP address for our company’s server’s VPN access.\[10\] It will also require a key which will be shared via a secure email to the employees. The key might vary for all the employees and sharing it may lead to suspension or other disciplinary action if it results in any loss for the company.

Security protocols like IPSec are important because networks are not encrypted by default. The normal networking protocols like TCP/IP are only concerned with establishing a connection and completing the delivery of the intended message to its recipient. Anyone in the middle can intercept and read these messages. IPSec adds a layer of protection by converting the message to a gibberish only the recipient can decipher by using the key provided to them. This ensures the message remains private and unaltered when it reaches its recipient.\[9\]

Like mentioned before, this will be mandatory for remote employees. Office employees don’t have to set up anything as the location network is under our IT Team’s management.

# Encrypted hard drives/flash disks to protect portable/mobile devices {#encrypted-hard-drives/flash-disks-to-protect-portable/mobile-devices}

Data stored on a portable hard drive or a flash disk is not protected in any way by default. If this device were to fall into the wrong hands, it could lead to big losses to the company as the data could expose future plans or financial data which could lead to reputational and financial damage. Therefore, it is imperative to protect this data.

To do this, we can use encryption. Encryption is a way to scramble data into an unreadable ciphertext that can only be deciphered by an authorized party. By doing this, even if the hardware device is lost, the data on it would be inaccessible or unreadable to any third party that finds it. \[11\]

To encrypt a portable storage device with company data, these are the steps that should be followed\[12\]:

1. Plug in the storage device to the USB port on a company Windows computer.  
2. Open File Explorer  
3. Right Click on the storage device and select **BitLocker** and turn it on. BitLocker is a Windows Service that can encrypt the data.  
4. Set a strong password to unlock the drive. It will be required when plugging back into any device. Follow the suggestions from the first section for a strong password.  
5. Select the whole drive as data you want to encrypt.  
6. Click “Start Encrypting”. It will notify you once complete. Do not remove drive in the middle of the operation

Any employee found with unencrypted sensitive data will face disciplinary action. If you have any problems handling this, the IT team is there to support.

The IT team will also be providing pre-encrypted drives for employees who do not have a Windows system, They can also be provided if you submit a request on the employee portal. Keep in mind the availability is low for these pre-encrypted drives till next year. 

# Conclusion {#conclusion}

Data is a really important asset. Whether it is employee data, customer data or financial data about the organization, leakage of that information outside the authorized circle can cause massive reputational and financial damage to the organization. It is therefore necessary to protect all the data in any form and while it is in transit as well. Encryption is a tool which can make this possible.

Encryption ensures only the authorized party can decipher the message. It also ensures the message is not tampered with. A lot of Personally Identifiable Information is also required to be encrypted by regulations such as HIPAA, PIPEDA and PCI-DSS. Providing a solution to all of this is possible by following the steps mentioned in this report.

# Citations

1. Cisco. (2024, April 26). *What is cybersecurity?*. Cisco. [What Is Cybersecurity? \- Cisco](https://www.cisco.com/c/en_ca/products/security/what-is-cybersecurity.html)   
2. Vicente, V. (2024, May). *NIST Password Guidelines 2024*. AuditBoard. [NIST Password Guidelines 2024 | AuditBoard](https://www.auditboard.com/blog/nist-password-guidelines/)  
3. National Institute of Standards and Technology (NIST). (2020). *Digital Identity Guidelines: Authentication and Lifecycle Management*. NIST Special Publication 800-63B. [NIST Special Publication 800-63B (Digital Identity Guidelines](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-63b.pdf))  
4. Microsoft. (2024, May 29). *Set the password expiration policy for your organization*. Microsoft. [Set the password expiration policy for your organization \- Microsoft 365 admin](https://learn.microsoft.com/en-us/microsoft-365/admin/manage/set-password-expiration-policy?view=o365-worldwide)  
5. James, D. (2023, December 8). *The Password Expiry Myth*. Spiceworks. [The Password Expiry Myth: Redefining Password Security \- Spiceworks](https://www.spiceworks.com/it-security/identity-access-management/guest-article/redefining-password-security-strategies/)  
6. MITRE. (2022, October 21). *Multi-factor Authentication*. MITRE ATT\&CK Mitigation M1032. [Multi-factor Authentication, Mitigation M1032 \- Enterprise | MITRE ATT\&CK®](https://attack.mitre.org/mitigations/M1032/)  
7. Microsoft. (2024, February 22). *S/MIME in Exchange Online.* Microsoft. [S/MIME for message signing and encryption in Exchange Online](https://learn.microsoft.com/en-us/exchange/security-and-compliance/smime-exo/smime-exo)  
8. Sectigo. (n.d.). *S/MIME Certificates.* Sectigo. [S/MIME Certificate \- Secure Email Encryption | Sectigo® Official](https://www.sectigo.com/ssl-certificates-tls/email-smime-certificate#:~:text=S%2FMIME%20Certificates&text=This%20allows%20the%20sender%20to,communications%20and%20ensure%20message%20integrity).  
9. Cloudflare. (n.d.). *What is IPSec?.* Cloudflare. [What is IPsec? | How IPsec VPNs work | Cloudflare](https://www.cloudflare.com/learning/network-layer/what-is-ipsec/)  
10. Fortinet. (n.d.). *Fortigate. Fortinet.* [FortiGate / FortiOS 7.6](https://docs.fortinet.com/product/fortigate/7.6)  
11. Cloudflare. (n.d.). *What is encryption?*. Cloudflare.  [What is encryption? | Cloudflare](https://www.cloudflare.com/learning/ssl/what-is-encryption/)  
12. Microsoft. (n.d.). *How to encrypt a flash drive?.* Microsoft. [How to encrypt a USB flash drive—and why you should – Microsoft 365](https://www.microsoft.com/en-us/microsoft-365-life-hacks/privacy-and-safety/how-and-why-to-encrypt-usb-flash-drive)
