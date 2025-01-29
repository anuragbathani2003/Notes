
# level 0

**Username** : bandit0
**Password**: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

![[Pasted image 20241218121411.png]]

## level 1

**Username** : bandit1
**Password**: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx

![[Pasted image 20241218121631.png]]


## level 2

**Username** : bandit2
**Password**:  MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

![[Pasted image 20241218122437.png]]

## level 3

**Username** : bandit3
**Password**: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

![[Pasted image 20241218123057.png]]

## level 4

**Username** : bandit4
**Password**: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

![[Pasted image 20241218123822.png]]

## level 5

**Username** : bandit5
**Password**: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
![[Pasted image 20241218135633.png]]
![[Pasted image 20241218135711.png]]
![[Pasted image 20241218135734.png]]
![[Pasted image 20241218135803.png]]
![[Pasted image 20241218132450.png]]


## level 6


**Username** : bandit6
**Password**: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

![[Pasted image 20241218135537.png]]

![[Pasted image 20241218135414.png]]

## level 7

**Username** : bandit7
**Password**: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc


![[Pasted image 20241218140413.png]]

## level 8


**Username** : bandit8
**Password**: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

![[Pasted image 20241218141933.png]]

![[Pasted image 20241218142007.png]]

![[Pasted image 20241218142034.png]]

## level 9

**Username** : bandit9
**Password**: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

![[Pasted image 20241218153818.png]]

![[Pasted image 20241218153859.png]]

## level 10

**Username** : bandit10
**Password**: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr


![[Pasted image 20241218155623.png]]


## level 11

**Username** : bandit11
**Password**: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

![[Pasted image 20241218161948.png]]


## level 12

**Username** : bandit12
**Password**: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

![[Pasted image 20241218172539.png]]

![[Pasted image 20241218172604.png]]

![[Pasted image 20241218172619.png]]

![[Pasted image 20241218172636.png]]

![[Pasted image 20241218172651.png]]
![[Pasted image 20241218172706.png]]


## level 13

**Username** : bandit13
**Password**: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

![[Pasted image 20241218181906.png]]

![[Pasted image 20241218181927.png]]


## level 14

**Username** : bandit14
**Password**: MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS

![[Pasted image 20241218183136.png]]
![[Pasted image 20250106113741.png]]
## level 15

Username :bandit15
Password: 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

![[Pasted image 20250106114859.png]]
![[Pasted image 20250106114929.png]]
![[Pasted image 20250106115009.png]]
## Level 16

Username :bandit16
Password: kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
![[Pasted image 20250106123623.png]]
![[Pasted image 20250106123645.png]]
![[Pasted image 20250106123709.png]]
![[Pasted image 20250106123726.png]]


## Level 17

Username :bandit17
Password: EReVavePLFHtFlFsjn3hyzMlvSuSAcRD

![[Pasted image 20250106125816.png]]


## Level 18

Username :bandit18
Password: x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO(temp)

![[Pasted image 20250107104256.png]]



## Level 19

username : bandit19
password:  cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8

![[Pasted image 20250107112908.png]]

## Level 20

username : bandit20
password: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO

![[Pasted image 20250107114510.png]]

![[Pasted image 20250107114532.png]]


## Level 21

username: bandit21
password: EeoULMCra2q0dSkYj561DX7s1CpBuOBt


![[Pasted image 20250107121228.png]]

## Level 22

username: bandit22
password:tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q

![[Pasted image 20250107125547.png]]

## Level 23

username : bandit23
pasword :0Zf11ioIjMVN551jX3CmStKLYqjk54Ga


![[Pasted image 20250107154526.png]]


## Level 24

username: bandit24
password: gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8

	import socket

	BANDIT24_PASSWORD = "gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8"
	HOST = "localhost"  # Change to the target IP if remote
	PORT = 30002
	
	def brute_force():
	    with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
	        s.connect((HOST, PORT))
	
	        for pincode in range(10000):  # 0000 to 9999
	            formatted_pincode = f"{pincode:04}"  # Always 4 digits
	            message = f"{BANDIT24_PASSWORD} {formatted_pincode}\n"
	            s.sendall(message.encode())
	
	            response = s.recv(1024).decode()
	            print(f"Trying {formatted_pincode}: {response}")
	
	            if "Correct" in response:  # Adjust based on expected success message
	                print(f"Found correct pincode: {formatted_pincode}")
	                break
	
	if __name__ == "__main__":
	    brute_force()


![[Pasted image 20250107171013.png]]


![[Pasted image 20250107171211.png]]

## Level 25

username : bandit25
password :iCi86ttT4KSNe1armKiwbQNmB3YJP3q4

![[Pasted image 20250107175604.png]]

## Level 26

username: bandit26
password:s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ

![[Pasted image 20250107175604.png]]
## Level 27

username; bandit27
password: upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB

![[Pasted image 20250107181143.png]]

![[Pasted image 20250107181204.png]]

## level 28

username: bandit28
password: Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN

![[Pasted image 20250107182630.png]]

![[Pasted image 20250107182704.png]]

![[Pasted image 20250107182738.png]]

![[Pasted image 20250107182825.png]]

## level 29

username : bandit29
password : 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7

![[Pasted image 20250107184054.png]]

![[Pasted image 20250107184123.png]]

![[Pasted image 20250107184153.png]]

![[Pasted image 20250107184228.png]]

## level 30

username : bandit30
password: qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL

![[Pasted image 20250107185800.png]]

![[Pasted image 20250107185819.png]]


![[Pasted image 20250107185840.png]]


## Level 31

username : bandit31
password: fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy

![[Pasted image 20250108111854.png]]

![[Pasted image 20250108111922.png]]

![[Pasted image 20250108111955.png]]


![[Pasted image 20250108112029.png]]

![[Pasted image 20250108112044.png]]


## Level 32

username: bandit32
password: 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K


![[Pasted image 20250108115202.png]]


## Level 33


username : bandit33
password: tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0



