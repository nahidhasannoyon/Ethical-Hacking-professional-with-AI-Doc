# SMB Relay Attack Defenses

SMB Relay attacks exploit the way SMB (Server Message Block) handles authentication, allowing an attacker to intercept and relay credentials to gain unauthorized access. Here are some key defenses to mitigate SMB Relay attacks:

#### **1. Disable SMBv1**

* SMBv1 is outdated and vulnerable to various attacks, including SMB Relay.
*   **How to disable SMBv1 on Windows:**

    ```
    Set-SmbServerConfiguration -EnableSMB1Protocol $false
    ```
* Alternatively, disable it via **Windows Features** or Group Policy.

#### **2. Enforce SMB Signing**

* SMB signing ensures message integrity, preventing attackers from modifying and relaying traffic.
* **How to enable SMB signing (Windows Group Policy):**
  * Open `gpedit.msc`
  * Navigate to:\
    `Computer Configuration > Windows Settings > Security Settings > Local Policies > Security Options`
  * Enable **Microsoft network client: Digitally sign communications (always)**
  * Enable **Microsoft network server: Digitally sign communications (always)**

#### **3. Use NTLMv2 or Kerberos Authentication**

* NTLMv1 is weak and susceptible to relay attacks.
*   Force the use of **NTLMv2 or Kerberos** authentication:

    ```
    Set-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Control\Lsa" -Name "LmCompatibilityLevel" -Value 5
    ```
* This ensures only NTLMv2 or Kerberos authentication is used.

#### **4. Disable LM and NTLM (If Possible)**

* Completely disable LM and NTLM authentication if all systems support Kerberos.
* This can be done via Group Policy:
  * `Network security: LAN Manager authentication level = Send NTLMv2 response only. Refuse LM & NTLM`

#### **5. Implement SMB Client Restrictions**

* Restrict outgoing SMB connections to prevent credential relaying.
* **Windows Defender Firewall Rules:**
  * Block outgoing traffic on **TCP ports 139 and 445** unless required.

#### **6. Enforce LDAP Signing and Channel Binding**

* LDAP relay attacks can be chained with SMB relay attacks.
* Configure **LDAP signing** and **LDAP channel binding** via Group Policy.

#### **7. Use Privileged Access Workstations (PAW)**

* Administrators should use separate devices for privileged access to prevent relay attacks.

#### **8. Implement Multi-Factor Authentication (MFA)**

* Even if credentials are relayed, MFA can prevent unauthorized access.

#### **9. Regularly Patch and Update Systems**

* Keep Windows, domain controllers, and SMB-related components up to date.

#### **10. Monitor and Detect SMB Relay Attacks**

* Use SIEM solutions to detect unusual SMB authentication attempts.
* Monitor event logs:
  * **Event ID 4624** (Successful Logon)
  * **Event ID 4648** (A logon was attempted using explicit credentials)

By implementing these measures, you can significantly reduce the risk of SMB Relay attacks. Let me know if you need further details! 🚀
