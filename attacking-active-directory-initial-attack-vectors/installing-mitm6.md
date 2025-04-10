# Installing mitm6

### **What is MITM (Man-in-the-Middle) Attack?**

A **Man-in-the-Middle (MITM)** attack is a type of cyberattack where an attacker secretly intercepts and potentially alters the communication between two parties without their knowledge. The attacker positions themselves between the client and the server, making both parties believe they are communicating directly with each other — while in reality, the attacker is relaying and manipulating the messages.

***

#### **✅ How MITM Works:**

1. **Interception:**
   * The attacker inserts themselves between two communicating parties (e.g., client and server).
   * This can be done through various methods like ARP spoofing, DNS poisoning, or NDP spoofing (in IPv6).
2. **Data Capture and Modification:**
   * The attacker captures sensitive data such as login credentials, session cookies, financial data, etc.
   * They can also modify the data before forwarding it to the intended recipient.
3. **Relay or Injection:**
   * The attacker can inject malicious payloads into the communication stream.
   * The attacker can also impersonate one of the parties to escalate privileges or maintain persistent access.

***

#### **🛡️ Common MITM Attack Techniques:**

| Technique               | Description                                                                 | Target Protocol |
| ----------------------- | --------------------------------------------------------------------------- | --------------- |
| **ARP Spoofing**        | Sends fake ARP responses to redirect traffic through the attacker's machine | IPv4            |
| **DNS Spoofing**        | Manipulates DNS responses to redirect traffic to a malicious server         | DNS             |
| **NDP Spoofing**        | Similar to ARP spoofing, but for IPv6 networks                              | IPv6            |
| **SSL Stripping**       | Downgrades HTTPS connections to HTTP, exposing data in plaintext            | HTTPS           |
| **Wi-Fi Eavesdropping** | Attacker sets up a rogue Wi-Fi hotspot to intercept traffic                 | Wi-Fi           |
| **Session Hijacking**   | Steals session cookies to impersonate a user                                | HTTP            |

***

#### **🎯 Example Scenario:**

1. A user logs into a banking website over HTTPS.
2. The attacker intercepts the connection and downgrades it to HTTP (SSL stripping).
3. The attacker captures the user’s login credentials and redirects them to the original site.
4. The user is unaware that the session has been compromised.

***

### **What is mitm6?**

**mitm6** is an advanced MITM tool specifically designed to exploit misconfigurations in IPv6 networks, especially in Windows Active Directory environments. It allows attackers to perform NTLM relay attacks by abusing IPv6 auto-configuration and forcing network devices to authenticate with the attacker's machine.

***

#### **✅ How mitm6 Works:**

1. **IPv6 Auto-Configuration Abuse:**
   * When a Windows machine connects to a network, it will automatically configure itself for IPv6 using SLAAC (Stateless Address Autoconfiguration).
   * mitm6 pretends to be a legitimate IPv6 router by sending out rogue Router Advertisement (RA) messages.
   * The target machine will prefer the attacker's IPv6 network over the existing IPv4 connection.
2. **Forcing Authentication:**
   * mitm6 sets itself as the default gateway and DNS server.
   * The target machine will attempt to authenticate to the attacker's DNS server using NTLM.
3. **NTLM Relay Attack:**
   * The attacker can relay NTLM authentication to other network services (like SMB or LDAP).
   * This allows the attacker to gain unauthorized access to Windows servers and escalate privileges.

***

#### **🛡️ Example mitm6 Attack Scenario:**

1. Attacker runs mitm6 to broadcast fake IPv6 Router Advertisement.
2. Windows machine configures itself using mitm6 as the default gateway.
3. The machine sends an authentication request using NTLM to the attacker-controlled DNS server.
4. The attacker captures the NTLM hash and relays it to an SMB server using **ntlmrelayx**.
5. The attacker gains access to the SMB server and executes commands with the victim’s privileges.

***

#### **⚠️ Why mitm6 is Effective:**

✔️ Windows systems automatically prefer IPv6 over IPv4.\
✔️ IPv6 auto-configuration is enabled by default in Windows.\
✔️ NTLM is often enabled in Active Directory environments.\
✔️ SMB signing is frequently misconfigured or disabled.

***

### **🛡️ How to Defend Against mitm6 and MITM Attacks:**

✔️ **Disable IPv6** if it's not needed.\
✔️ **Enable SMB Signing** to prevent SMB relay attacks.\
✔️ **Enforce LDAP Signing and Channel Binding** to prevent NTLM relay over LDAP.\
✔️ **Use Kerberos instead of NTLM** for authentication.\
✔️ **Disable WPAD (Web Proxy Auto-Discovery)** to prevent rogue proxy settings.\
✔️ **Monitor Router Advertisements** and IPv6 traffic for anomalies.\
✔️ **Enforce MFA (Multi-Factor Authentication)** to prevent credential compromise.



#### **Installing mitm6 on Linux**

Follow these steps to install **mitm6** on your attacker machine:

***

#### ✅ **Step 1: Update the Package List**

First, update your system's package list to ensure all repositories are up to date:

```bash
sudo apt update
```

***

#### ✅ **Step 2: Install mitm6**

Install mitm6 directly from the package manager:

```bash
sudo apt install mitm6
```

***

#### ✅ **Step 3: Verify the Installation**

After installation, verify that mitm6 was installed correctly:

```bash
mitm6 --help
```

If you see the help menu, mitm6 is installed successfully.
