

## Step 1:

	use nmap to with -sV to identify open ports 
### command
	nmap -sV 10.10.175.60

![[key_1_photo1.png]]


## Step 2 :

	here we get two port are open which is port 80 and port 443 so now open a browser try to request the server with port 80 because its not required a ssl certificate or its unsecure connection


### command

	10.10.175.60:80

![[key_1_photo2.png]]




## Step 3

	use gobuster or durbuster to check a hidden directory(robots.txt)

### command

	gobuster dir -u 10.10.175.60:80/ -w /mnt/hgfs/share/common.txt 

![[key_1_photo3.png]]
![[Pasted image 20241227114544.png]]

## Step 4

	try to browse robots.txt in browser

![[key_1_photo4.png]]


## Step 5


	try to browse key-1-of-3.txt

![[key_1_photo5.png]]
