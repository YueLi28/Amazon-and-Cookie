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
|485|shopify.com| US | em | sms(2)/app(2)/code(for2)| em(c)| no |
|484|ancestry.com| US | em/un | FB | em(c) | no | 
|483| tabelog.com| Japan | em | FB/TT/G+ | em(c) | no | cannot read japanese
|482 | souq.com | Egypt | em/un | FB | em(c) | no
|481 | webssearches.com | brazil | no |
|480 | nyaa.se | Japan | un/em/ui | no | em(c) | no |
|479 | liputan6.com | Indonesia | em | FB | em(c) | no| 
|478 |techcrunch.com| US | no | FB/TT/LI / no | no |
| 477 | asos.com | US | em | FB/TT/G+ | em(c) | no
| 476 | wow.com | US | no
|1| Google.com | US | un/em | sms(2) | em(c) | sms()/oldpass| using old password can still reset password
|2 | Facebook.com | US | em/ce | sms(2)/app(2)/paper(2)| em | google | 
|3| Youtube.com | US | same as Google
|4 | Baidu.com | China | em\cell | sms(2)/app(2)/em(2)/QQ/weibo | em/cell | sq | I am not sure since it requires cellphone binding
|5 | Yahoo.com | US | un | OTP/sms(2) | sms | em | sms |
|6 | Amazon | US | em | cell | em | cell | 
|7 | Wikipedia | US | un | no | em | no |
|8 | QQ.com | China | em/cell | app | cell | cell/app/sq | need further verify (I do not have Chinese cell phone)
|9 | twitter.com |US | em/un/cell | app(2)/sms(2)/sms(can opt out)/app(can opt out) | em/sms | personalinfo(optional) | 
|10 | Google.co.in |India | same as google
| 11 | Taobao.com | China | cell(must)/email(optional)/un |no| cell | sq/appeal | no
| 12 | Live.com | US | un=em/cell | sms(2)/em(2)/app(2) | em/cell | app/code | need combine 2 ways to reset password if 2-step verification is used
| 13 | sina.com.cn |China | em/cell | QQ | cell | appeal | no
| 14 | yahoo.co.jp | Japan | same as Yahoo.com
| 15 | Linkedin.com | US | em | sms(2) | em | no | no
| 16 | weibo.com | China | same as sina
| 17 | Ebay.com | US | em | no | em | cell | no
| 18 | Google.co.jp | Japan | same as Google
| 19 | Yandex.ru | Russia | Cannot input russian captcha.. | VK/FB/TT/G/Mail.ru/Classmate/App |
| 20 | VK.com | Russia | cell | em/FB/URL/sms(2)/app(2)/paper(2) | cell | no
| 21 | Hao123 | China | same as Baidu |extra login: QQ/Renren/Weibo
| 22 | blogspot.com | same as Google
| 23 | t.co | US | Same as twitter | t.co is the referrer source for twitter. 
| 24 | bing.com | US | Same as Microsoft 
| 25 | Google.de | Germany| Same as Google
| 26 | instagram.com | US| em | no | em | no | can only signup in its app
| 27 | aliexpress.com | Russia | em | FB | em | no 
| 28 | msn.com | US | same as microsoft
| 29 | Amazon.co.jp | Japan | same as Amazon | May need further verification. Cannot read Japanese
| 30 | Google.co.uk | UK | same as google
| 31 | reddit.com | US | un | no | em | no | email is optional, in such case, no password reset 
| 32 | www.ask.com |  no sign in
| 33 | Google.com.br | Brazil | Same as Google
|34 | Pinterest.com | US | em | FB/TT/G+ | em | no | 
| 35 | Onclickads.net |  Indonesia | Ads serving refferrer, no sign in
| 36 | Google.fr | France | same as google
| 37 | microsoft.com | US | same as live.com
| 38 | Wordpress.com |US | em/un | sms(2)/app(2)/paper(2) | em | sms | no
| 39 | TMall.com | China | same as Taobao.com
| 40 | Paypal.com | US | em | cell(2)/sq(2) | em/cell | 
| 41 | Mail.ru | Russia | did not sign up due to language..
| 42 | sohu.com | China | cell | I do not have a chinese cell
| 43 | Tumblr.com | US | em | sms(2)/app(2) | em | app(2)/sms | no
| 44 | Imgur.com | US | un/em | FB/TT/G+/YH | em | no | no
| 45 | Google.ru | Russia | Same as Google
| 46 | Xvideos.com | Japan | em | no | em | no | no
| 47 | imdb.com | US | em | Amazon/FB/GG | em | no
| 48 | apple.com | US | em | no | em/sq+bd | key+sms | sq is used to change password, 2-step verification is not required to sign in, but changing or recovering password|
| 49 | FC.com | Japan | em | em(2) | em(plain) | bd+sq | the 2-step verification is not controlled by user, be popped out when abnormal activity is detected
| 50 | Google.it | italy | same as Google
| 51 | Google.es | spain | same as Google
| 52 | Googleadservices.com | Germany | Google ads referrer
| 53 | netflix.com | US | em | FB | em | cell/(creditcardinfotorecoveremail) | no
| 54 | Amazon.de | Germany | same as Amazon
| 55 | 360.cn | China | I have no cell phone number
| 56 | stackoverflow.com | US | em |G+/FB/YH/LiveJournal/Wordpress/Blogger/Verisign/AOL   | em | no | no
| 57 | Tianya.cn | China | I have no cell phone number
| 58 | Craigslist.org | US |em | no | em | no | no
| 59 | Alibaba.com | China | Same as Taobao
| 60 | ok.ru | Russia | un/em | em | em | cell | If use un to register, no recovery
| 61 | Google.com.mx | Mexico | same as Google
| 62 | Google.ca | Canada | Same as Google
| 63 | Pornhub.com | US | un/em | no | em | no | no
| 64 | Google.com.hk | China | Same as Google
| 65 | diply.com | Canada | no |FB/TT| no | no | no
| 66 | Naver.com |South Korea | cannot read korean
| 67 | Amazon.co.uk | UK | same as Amazon
| 68 | GMW.cn | China | un/em | no | em | no| no
| 69 | Rakuten.co.jp | Japan | em | no | em | no | no
| 70 | 
| 71 | go.com | US | em | no | sq/em | no | no
| 72 | blogger.com | India | same as Google
| 73 | kat.cr | India | em | no | em | no
| 74 | adcash.com | ID/em | no | em | no | not sure, needs a company to sign in
| 75 | outbrain.com | US | un/em | no | em | no | no
| 76 | cnn.com | US | em |  no | em | no | for cnn ireport


hybrid


