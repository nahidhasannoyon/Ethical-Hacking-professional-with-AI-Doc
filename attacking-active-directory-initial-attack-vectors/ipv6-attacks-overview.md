# IPv6 Attacks Overview

### **What is IPv6?**

IPv6 (Internet Protocol version 6) is the latest version of the Internet Protocol (IP) designed to replace IPv4 due to the exhaustion of IPv4 addresses. IPv6 provides a significantly larger address space and improved network functionality.

#### **✅ Key Features of IPv6:**

* **128-bit address:** IPv6 addresses are 128 bits long, providing approximately 340 undecillion (3.4 × 10³⁸) unique addresses.
* **Hexadecimal notation:** IPv6 addresses are represented in hexadecimal, separated by colons (`:`).
* **Simplified header:** IPv6 headers are more streamlined than IPv4, improving packet processing efficiency.
* **No need for NAT (Network Address Translation):** The large address space eliminates the need for private-to-public IP address translation.
* **Built-in security:** IPv6 natively supports IPsec (Internet Protocol Security) for encryption and authentication.
* **Auto-configuration:** Devices can automatically configure themselves with an IPv6 address using Stateless Address Autoconfiguration (SLAAC).

***

### **What Are Some IPv6 Attacks?**

Since IPv6 is widely used in modern networks, attackers have adapted techniques to exploit its vulnerabilities. Common IPv6-based attacks include:

#### **1. MITM (Man-in-the-Middle) Attacks:**

* Attackers can intercept and manipulate IPv6 traffic by spoofing router advertisements or poisoning Neighbor Discovery Protocol (NDP).

#### **2. NDP Spoofing (Neighbor Discovery Protocol Spoofing):**

* Similar to ARP spoofing in IPv4, an attacker can respond to NDP requests with false information, redirecting traffic to the attacker's machine.

#### **3. SLAAC (Stateless Address Autoconfiguration) Attacks:**

* Attackers can set up a rogue router to send fake SLAAC responses, assigning malicious IPv6 addresses to devices.

#### **4. IPv6 Tunneling Attacks:**

* IPv6 packets can be tunneled over IPv4 using protocols like `6to4` or `Teredo`. Attackers can inject malicious traffic through these tunnels.

#### **5. DNS Attacks:**

* DNS queries over IPv6 (`AAAA` records) can be intercepted and manipulated by an attacker.
* DNS cache poisoning can also be executed through IPv6.

#### **6. DHCPv6 Attacks:**

* Attackers can set up rogue DHCPv6 servers to distribute malicious network configurations to clients.

#### **7. Flooding and DoS (Denial of Service):**

* Due to the large address space of IPv6, attackers can generate massive amounts of spoofed IPv6 traffic to overwhelm network infrastructure.

***

### **What is IPv6 Exploitation in AD (Active Directory)?**

Attackers often target IPv6 misconfigurations and vulnerabilities to gain access to Active Directory environments. The most common techniques include:

#### **1. MITM via NDP Spoofing:**

* An attacker can create a rogue IPv6 router and advertise themselves as the default gateway using Router Advertisement (RA) messages.
* This allows the attacker to intercept all AD authentication traffic, leading to credential theft or session hijacking.

#### **2. NTLM Relay Over IPv6:**

* Once the attacker positions themselves as the gateway using NDP spoofing, they can relay NTLM authentication attempts to other machines using IPv6.
* This enables the attacker to escalate privileges and gain control over the domain.

#### **3. IPv6 to IPv4 Downgrade Attacks:**

* If an AD network is misconfigured to allow both IPv4 and IPv6, an attacker can downgrade the authentication method to a weaker IPv4-based NTLMv1 or Kerberos version, making it easier to crack hashes.

#### **4. DHCPv6 Rogue Server Attack:**

* By setting up a malicious DHCPv6 server, an attacker can assign malicious DNS servers or IPv6 routes, redirecting AD traffic to the attacker’s machine.

#### **5. SMB Relay Over IPv6:**

* After setting up a MITM scenario over IPv6, an attacker can capture NTLMv2 hashes and relay them over SMB to authenticate and execute commands on domain controllers.

#### **6. Exploiting IPv6 Group Policy Misconfigurations:**

* Attackers can inject malicious IPv6 addresses into AD Group Policy Objects (GPO) to control routing or DNS settings, giving them the ability to manipulate network traffic or resolve malicious domains.

***

#### ✅ **Why IPv6 Exploitation is Effective in AD:**

* Most networks enable IPv6 by default even if it's not properly configured.
* IPv6 traffic is often not monitored as closely as IPv4.
* Windows systems automatically prefer IPv6 over IPv4 if both are available.
* NTLM and Kerberos authentication can be relayed over IPv6 if proper mitigations (like SMB signing) are not enabled.

***

#### 🔥 **Key Defense Strategies:**

✔️ Disable IPv6 if it's not in use.\
✔️ Enable SMB signing and LDAP signing.\
✔️ Monitor IPv6 traffic and log router advertisements.\
✔️ Use Kerberos instead of NTLM for authentication.\
✔️ Implement Group Policy to control IPv6 configurations and disable rogue router advertisements.



{% embed url="https://medium.com/@browninfosecguy/ipv6-exploitation-in-ad-environment-b22a7c3ec8af" %}

