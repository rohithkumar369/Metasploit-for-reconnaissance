# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:


## OUTPUT:
![Screenshot (148)](https://github.com/user-attachments/assets/c0d0ee4b-675e-4f9c-a6a4-3577c66dc945)
# Invoke msfconsole:
## OUTPUT:
![Screenshot (149)](https://github.com/user-attachments/assets/3375c5ab-cac0-42f3-b04c-71a9e267e844)
# Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
## Output:
![Screenshot (150)](https://github.com/user-attachments/assets/c3c6c92d-a9d1-4e6c-b66d-4c895783280f)

Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000).
msf >  nmap -sT 192.168.1810/24 -p1-1000
## OUTPUT:
![image](https://github.com/user-attachments/assets/1b712a43-d042-43bc-a6aa-52eeb61804e2)

step4:
use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows.
msf > db_nmap 192.168.181.0/24
## OUTPUT:
![image](https://github.com/user-attachments/assets/b39087fa-b1f4-4a32-98ff-e8c616a4532b)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules.
cd /usr/share /metasploit-framework/modules/auxiliary
kali > ls -l
## OUTPUT:
![image](https://github.com/user-attachments/assets/1a1a52a2-3cba-4028-a9c6-019db849799e)

Search is a powerful command in Metasploit that you can use to find what you want to locate. 
msf >search name:Microsoft type:exploit
![image](https://github.com/user-attachments/assets/030853d5-db05-4f14-bfe6-a019a7a2bc3a)
##OUTPUT
The info command provides information regarding a module or platform,
![image](https://github.com/user-attachments/assets/8eacda45-7653-488e-a22a-89d993c9c2b6)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows:
systemctl start postgresql
msfdb init
##MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port.
db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![Screenshot (156)](https://github.com/user-attachments/assets/6129f958-b710-4b85-86ca-9c2320e020ed)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database.
search type:auxiliary mysql
![Screenshot (157)](https://github.com/user-attachments/assets/5cc7909a-248e-4c9d-8ec4-038db1525040)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details.
use 11
Or:
use auxiliary/scanner/mysql/mysql_version
![Screenshot (158)](https://github.com/user-attachments/assets/57ba5d4c-c895-4636-a5e2-5979192f3247)

Use the set rhosts command to set the parameter and run the module, as follows:



## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
