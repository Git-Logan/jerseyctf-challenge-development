# avenge-my-password - hard 

## Description
* Stark to Star-Lord - "Oh my, see Quill?! I told you your credentials can work for more than one thing, but things only go so far. Time will tell when to search another path to find a way in!" Automated directory brute force is unnecessary.
* ssh `<username>@<host>` | Password: `<password>`

## Hint
* No hints. 

## Solution Steps
* SSH into the virtual machine and notice you should access mySQL because of the description "my, see Quill": `mysql -h localhost -u quantumleaper -p` using the same credentials provided for SSH access. 
* You can see the user's database permissions using the command `SHOW GRANTS FOR 'quantumleaper'@'localhost';`
* Perform a command to see and use a database: `SHOW databases;` and `USE website;`
* Perform a command to show the website database tables and select the data from it: `SHOW tables;` and `SELECT * FROM login;`
* Look through the data and notice it is 500 userIDs and password MD5 hashes. Although, userID 401 has an unhashed password `Spring2023!!!`
* Knowing that this is a website virtual machine, exit mysql and navigate to /var/www/html. Perform an `ls -la`.
* There is a file `index.php`, but read permissions are restricted. There are a lot of hidden directories, one of the notable ones being `.username`. There is another hidden file within this directory called .usernames.txt, also with restricted read permissions.
* Knowing this is a website, we can access it in our web browser using the provided IP we SSH'd into - `http://159.203.191.48`
* We can access .usernames.txt via `http://159.203.191.48/.username/.usernames.txt`, which shows a list of 500 users. One of these matches up with the unhashed password from the mySQL database.
* Knowing that we have a 500 username list and one password, we can perform a password spraying attack.
* Utilize BurpSuite (free version works) to conduct a password spraying brute force attack.
* Configure the web browser to be connected to the Burp proxy by setting the HTTP proxy to 127.0.0.1:8080.
* With Intercept enabled in the Proxy tab, navigate to the site and submit any username with the discovered unhashed password `Spring2023!!!`. The POST request will be tracked, and switch over to the HTTP history in the Proxy tab.
* Right click the POST method for the 159.203.191.48 host, and click Send to Intruder.
* In Positions, click Clear on the right. Highlight the username that was inputted and click Add on the right.
* In Payloads, click Load and select the downloaded usernames.txt file. Click Start attack, and then click the Length filter twice so that it orders from greatest to least. In ~5-10 minutes of running the attack, the correct user `MarsString` will have a larger length than the rest because it logged-in and provided the flag in an alert. Navigate to the site and enter in the proper credentials to see the flag or simply read it in Burp.
* Flag: `jctf{w3_LoV3_M@RV3L_:)_GOOD_JOB!}`

## Knowledge and/or Tools Needed
* [MITRE ATT&CK® Technique T1552.001 - Unsecured Credentials: Credentials In Files](https://attack.mitre.org/techniques/T1552/001/) 
* [MITRE ATT&CK® Technique T1110.003 - Brute Force: Password Spraying](https://attack.mitre.org/techniques/T1110/003/) 
* [web/heres-my-password from JerseyCTF II](https://github.com/njitacm/jerseyctf-2022-challenges/tree/main/web/heres-my-password)
* [BurpSuite](https://portswigger.net/burp)
