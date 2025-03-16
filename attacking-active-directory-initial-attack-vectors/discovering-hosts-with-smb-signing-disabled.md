# Discovering Hosts with SMB Signing Disabled

### **Discovering Hosts with SMB Signing Disabled**

#### **🔹 Step 1: Discover Active IP Addresses**

Since the process is being done locally, use the `netdiscover` command to list all active devices on the network:

```bash
netdiscover
```

✅ This will scan the local network and show all the available IP addresses of connected devices.

***

#### **🔹 Step 2: Check if SMB Signing is Enabled or Not**

Use **Nmap** to check the SMB signing status on a target IP:

```bash
nmap -Pn --script=smb2-security-mode -p445 TARGET_IP
```

👉 **Explanation:**

* `-Pn` → Treat all hosts as online (skip host discovery).
* `--script=smb2-security-mode` → Runs the SMB security mode check script.
* `-p445` → Specifies the SMB port (445).
* `TARGET_IP` → Replace this with the actual IP address of the target machine.

✅ **If SMB signing is disabled**, it will be shown in the output, indicating that the system is vulnerable to SMB relay attacks.\
✅ **If SMB signing is enabled**, the system is more secure against SMB relay attacks.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

