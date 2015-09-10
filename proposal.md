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

###Human Subject Experiment (<a href = "https://cups.cs.cmu.edu/soups/2010/howtosoups.pdf"> human subject experiment[https://cups.cs.cmu.edu/soups/2010/howtosoups.pdf] </a>.)


###A sample table for what will be recorded in a website

==functionality==

| Website        | Allow login? | Allow Recovery?|
| ------------- |:-------------:|:---:|
| www.yahoo.com | y|y|
(Record`login page`)

==login name==

| Username      | Assigned ID | Email Address| Single Sign On |
| ------------- |:-------------:|:---:|:---:|
|y|n|y|n
(Record `page` that shows such info)

==pwd recovery==

|Email| Cell Phone | Security Question |Others?| combined?|extra?|
|:---:|:---:|:---:|:---:|:---:|:---:|
|link, code, password?| link, code, password?| provided? sensitive or private?|specify| email+cell | email|

|Email| Cell Phone | Security Question |Others?| combined?|
|:---:|:---:|:---:|:---:|:---:|
|n| code| n | customer service | n

(Record `recovery page` of each method)

How does present system implement password recovery

* Default recovery method: The ones that are mentioned in account registration
* Extra recovery method: The ones that can be added after registration (while not mentioned in registration).
* Email vs Cellphone vs Security Questions


Yun, born in Taibei, live in San Francisco 94101
__eyny.com__

==functionality==

|rk| Website        | region| login |extra login| recovery | extra recovery| Memo|
|:---:| ------------- |:----:|:---------:|:---:|:---:|:---:|:---:|:---:|
|500| www.eyny.com | Taiwan | un | sq(2) | em(c) | no | 台北
|499| www.myway.com | US | un | no | em(n)/ht | no | 台北
|498| www.kinogo.co | Russia | cannot register | cannot read russian 
|497|realtor.com | US | em | FB | em(c) | no
|496|freegameszonetab.com | India | no |||||
|495|slack.com | US| em | sms(2)/app(2) | em(c) | em+sms | malfunctioned?|
|494|www.wunderground.com/| US | em/un | no | em(c) | no | email can be changed
|493|people.com| US | em | no | em(c) | no | needs credit card to sign-up
|492|albawabhnews.com| egypt | no
|491|shopclues.com| India | em |FB/G+| em(c) |no | sent the pwd in registration email|
|490|scribd.com| India | em/un | FB | em(c) | no |
|489|free.fr| France | ||||No login for non-subscriber
|488|naukri.com | India | em | no | em (c)| no | 
|487|gmarket.co.kr| South Korea | un | no | em(c) | ahyipin | Seems like a korean tool
|486|gamefaqs.com| US | em/un | no | em(c) | no |
|485|shopify.com| US | em | sms(2)/app(2)/code| em(c)| no |
|484|ancestry.com| US | em/un | FB | em(c) | no | 
|483| tabelog.com| Japan | em | FB/TT/G+ | em(c) | no | cannot read japanese
|482 | souq.com | Egypt | em/un | FB | em(c) | no
|481 | webssearches.com | brazil | no |
|480 | nyaa.se | Japan | un/em/ui | no | em(c) | no |
|479 | liputan6.com | Indonesia | em | FB | em(c) | no| 
|478 |techcrunch.com| US | no | FB/TT/LI / no | no |
| 477 | asos.com | US | em | FB/TT/G+ | em | no
| 476 | wow.com | US | no










