
## What is Ettercap 

	etter cap is basically a kali linux builtin tool which is used to perform man in the middle attack with ettercap we can perform so many attack but in this note i am discuss only ARP poisning
	the omly prerequisits for the tool is you have a updated kali with ettercap tool


	when you open the ettercap you will see this below screen on your terminal

![[Pasted image 20250108172903.png]]

	now you have to selcet your primary interface and for this you can find in your terminal with exceuting command ifconfig

![[Pasted image 20250108173255.png]]


	now you ready to go to save this just click the right button which is held in top right corner and you will see the home screen of ettercap


![[Pasted image 20250108173540.png]]

	now we can start the actual attack lets hack

### Step 1

	scan all the host in your network to do this follow below steps
		1.you will see virtical three dots on the top right corner click it
		2. you will see drop down menu 
		3. select host 
		4. select scan for hosts

![[Pasted image 20250108174057.png]]

	you not see any diffrence right! too see all scaned host on top right corner click host and click host list and it will show all nodes

![[Pasted image 20250108174251.png]]


### Step 2

	now we have to select a targets for mitm attack you need minimum two vicitm hosts ok one is probely a your network router and other is your targets machines

	when you select the targets you will see

![[Pasted image 20250108174729.png]]

### Step 3

	now you have to open the wireshark 

![[Pasted image 20250108174915.png]]

### Step 4

	on top right corner you will find a mitm menu open it and click arp poisiniing it will poisioned arp packets on the network

![[Pasted image 20250108175309.png]]

### step 5

	now you find play button on ettercap on top left corner click to start the attck
	you can see the traffic on wire shark 

![[Pasted image 20250108180021.png]]

