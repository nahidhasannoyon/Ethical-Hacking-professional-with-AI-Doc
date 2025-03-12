# Password Cracking with Hashcat

### **Cracking NTLMv2 Hash Using Hashcat**

#### **Step 1: Open Terminal and Switch to Super User Mode**

1. To switch to super user (root) mode, enter the following command:

```bash
sudo su
```

➡️ **`sudo su`** – Switches to the root user, allowing you to execute commands with administrative privileges.

***

#### **Step 2: Check Hashcat Options and Syntax**

2. To display all available options and syntax for Hashcat, enter:

```bash
hashcat --help
```

➡️ This will display information about Hashcat's modes, attack types, and other configuration options.

***

#### **Step 3: Crack NTLMv2 Hash Using Hashcat**

3. To crack NTLMv2 hash using Hashcat, use the following command:

```bash
hashcat -m 5600 hash.txt rockyou.txt --force
```

**👉 Explanation:**

* `-m 5600` – Specifies the mode for NTLMv2 hash cracking.
* `hash.txt` – The file containing the captured NTLMv2 hash.
* `rockyou.txt` – The password wordlist file used for cracking.
* `--force` – Forces Hashcat to run, ignoring hardware-related warnings.

***

> 💡 **Notes:**\
> ✔️ Place both `hash.txt` and `rockyou.txt` files in the **home folder**.\
> ✔️ The `rockyou.txt` file is usually located in Kali Linux at:

```bash
/usr/share/wordlists/rockyou.txt.gz
```

✔️ If the file is compressed, unzip it using:

```bash
gzip -d /usr/share/wordlists/rockyou.txt.gz
```
