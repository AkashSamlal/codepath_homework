# Project 8 - Pentesting Live Targets

Time spent: **7** hours spent in total

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

Vulnerability #1: Session Hijacking/Fixation

Description:
Open with two browsers, one with Chrome and another w/ Firefox
Login w/ (Username: pperson) on Chrome, and go to "public/hacktools/change_session_id.php" and extract the session ID
Go to the Firefox browser and go to "public/hacktools/change_session_id.php", and paste the session ID from Chrome to Firefox
Refresh the page and you are login without entering user credentials 

![SessionHijackingBlue](https://user-images.githubusercontent.com/43329669/98874340-12684280-2448-11eb-9e3a-81ab9ad08f53.gif)

Vulnerability #2: SQL Injection (SQLi)

Description:
After "id=" enter " ' or 1=1 " 
The database would failed to sanitize the results 

![SqliBlue](https://user-images.githubusercontent.com/43329669/98874365-201dc800-2448-11eb-86d8-e177424a24dd.gif)

## Green

Vulnerability #1: Cross-Site Scripting (XSS)

Description:
Login w/ (Username: pperson) and click on "Contact" on the header
Fill in the data fields, and for the "Feedback" type in: 
<script>alert('FF7RemakeGOTY!');</script> and hit submit button 
And lastly, go back to the feedback and you will see the alert

![XSSGreen](https://user-images.githubusercontent.com/43329669/98874389-2e6be400-2448-11eb-832d-f1bfad6dad91.gif)

Vulnerability #2: Username Enumeration

Description:
Login w/ random usernames and you will receive an error that login was unsuccessful, 
however it was written in paragraph text, while if you use the test login: jmonroe99 the error will be in bold

![UserEnumerationGreen](https://user-images.githubusercontent.com/43329669/98874412-362b8880-2448-11eb-984f-0b89705a4cca.gif)

## Red

Vulnerability #1: Cross-Site Request Forgery (CSRF)

Description:
Go to Salespeople list and edit a salesperson, 
Inspect the webpage, and in the forum, change the value to a "not_a_csrf_token" 
Change the name of the person, and update the user, check back to the salesperson list and changes are saved. 

![CSRF_Red](https://user-images.githubusercontent.com/43329669/98874274-ed73cf80-2447-11eb-908c-7876bfe3bb7b.gif)

Vulnerability #2: Insecure Direct Object Reference (IDOR)

Description:
In the URL you can change the id, however users value 10, 11 are not accessible since they are fired from the company
and they don't appear in the list, however you can still access them by manipulating the URL 

![IDORed](https://user-images.githubusercontent.com/43329669/98874327-08464400-2448-11eb-8cf6-a1d299ab8fcf.gif)

## Notes
Complete the assignment in seven hours 
