#Proposal: An evaluation framework for password recovery method

Passwords are still dominating user authentication schemes. However, passwords are long being critized to be vulnerable to various attacks. Nowadays people are guided to select passwords that meet many restrictions such as at least be 8 characters long, composing of different types of characters, avoiding using personal information, etc. Besides, users are suggested to use a different password for each of their accounts and change the password regularly. These instructions put heavy burden on users. Consequently, users are never more prone to forget their passwords. Thereby, password recovery becomes important. However, there are many password recovery schemes and no previous work has been done to evaluate these scehems systematically. 

This project __aims to create a framework to evaluate three aspects of existing password recovery mechanisms__ -- usability, security, and deployability (just like what J Bonneau did to evaluate authentication methods). Under each aspect there are sub-categories. For example, when measuring the usability, memory-effortless, nothing-to-carry, physical-effortless, etc coule be evaluated.

__Besides, we do a measurement study to uncover the recovery method in the wild__ by examing the real world enterprise websites (Alexa top 500). Meanwhile we present interesting quantatitive results.

Expected results could be:
* E-mail or cell phone recovery are the most popular recovery methods, thus producing single point of failures.
* The security question scheme (which is proven to be insecure) is still popular.
* Websites may use multiple ways to recover the passwords.

###Update after 9/3 meeting
__Outline__:
1. A large-scale study on how password recovery mechanisms are implemented in present websites.
2. Study how the email addresses are important to users (it is like a password manager, single point of failure).
3. A user study to show the importance of email is underestimated
4. Discuss alternative methods

###A sample table for what will be recorded in a website

==functionality==

| Website        | Allow login? | Allow Recovery?|
| ------------- |:-------------:|:---:|
| www.google.com | y|y|
(Record`login page`)

==login name==

| Username      | Assigned ID | Email Address| Single Sign On |
| ------------- |:-------------:|:---:|:---:|
|y|n|y|y
(Record `page` that shows such info)

==pwd recovery==

|Email| Cell Phone | Security Question |Others?| combined?|
|:---:|:---:|:---:|:---:|:---:|
|link, code, password?| link, code, password?| provided?|specify| email+cell

(Record `recovery page` of each method)



