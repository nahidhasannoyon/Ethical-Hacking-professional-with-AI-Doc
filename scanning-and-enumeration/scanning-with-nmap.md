# Scanning with Nmap

**Scanning with Nmap**

#### What is Nmap?

Nmap (Network Mapper) is a powerful open-source tool for network scanning and reconnaissance. It is used to discover hosts, services, open ports, and vulnerabilities in a network. Nmap works with both IP addresses and domain names, making it versatile for various scenarios.

#### How to Get an IP Address from a Domain Name

Use `nslookup` to find the IP address of a server from its domain name:

```bash
nslookup domain_name
```

Replace `domain_name` with the target domain (e.g., `example.com`).

#### Discover IP Addresses in a Network

* Use `metasploitable` to find IP addresses in a test environment.
*   Run `netdiscover` to scan a range of IP addresses:

    ```bash
    netdiscover -r ip_address_range
    ```

    Replace `ip_address_range` with the desired subnet (e.g., `192.168.1.0/24`).

#### Nmap Commands and Their Purpose

**1. Perform a Traceroute**

**Purpose:** Trace the path packets take to reach the target.

```bash
nmap IP_ADDRESS --traceroute
```

**2. Perform a Ping Scan**

**Purpose:** Check if the target is online and reachable.

```bash
nmap IP_ADDRESS -P
```

**3. Fast Scan**

**Purpose:** Quickly scan the most common 100 ports.

```bash
nmap IP_ADDRESS -F
```

**4. Scan All Ports**

**Purpose:** Identify services running on all 65,535 ports.

```bash
nmap IP_ADDRESS -p-
```

**5. Service Version Detection**

**Purpose:** Detect service versions on open ports.

```bash
nmap IP_ADDRESS -F -sV
```

**6. Aggressive Scan**

**Purpose:** Perform a detailed scan, including OS detection, version detection, script scanning, and traceroute.

```bash
nmap IP_ADDRESS -A
```

**7. Vulnerability Scan**

**Purpose:** Check the target for known vulnerabilities using Nmap scripts.

```bash
nmap --script vuln IP_ADDRESS
```

**8. Save Scan Results to a File**

**Purpose:** Export scan results to a file for later analysis.

```bash
nmap -oN FILE_NAME IP_ADDRESS
```

Replace `FILE_NAME` with the desired output filename.

#### Summary

Nmap is an essential tool for network analysis, enabling detailed scanning of hosts and networks. By combining commands such as traceroute, version detection, and vulnerability scripts, users can uncover valuable insights for security assessments and troubleshooting.



## Test Scanning on vulnerable mechine.&#x20;

{% embed url="https://sourceforge.net/projects/metasploitable/" %}

Metasploitable is an intentionally vulnerable Linux virtual machine. This VM can be used to conduct security training, test security tools, and practice common penetration testing techniques.

use _ip address_ in metasploitable to get ip address list&#x20;

use _netdiscover -r ip\_address_ to know more info&#x20;



## Resources ( Which were Discussed in the Class )

{% embed url="https://nmap.org/book/man-port-scanning-techniques.html" %}

## **Mastering Nmap: Essential Commands for Network Scanning and Recon for Hacking**

1. **Scan a Single IP**\
   `nmap 192.168.1.1`
   * Performs a simple scan on the specified IP address.
2. **Scan Multiple IPs**\
   `nmap 192.168.1.1 192.168.1.2 192.168.1.3`
   * Scans the given list of IP addresses.
3. **Scan a Range of IPs**\
   `nmap 192.168.1.1-100`
   * Scans IPs from 192.168.1.1 to 192.168.1.100.
4. **Detect Services and Versions**\
   `nmap -sV 192.168.1.1`
   * Detects open ports and services along with their versions.
5. **Aggressive Scan with OS Detection**\
   `nmap -A 192.168.1.1`
   * Performs a detailed scan with OS detection, version detection, script scanning, and traceroute.
6. **Scan Specific Ports**\
   `nmap -p 22,80,443 192.168.1.1`
   * Scans only the specified ports.
7. **Scan All 65,535 Ports**\
   `nmap -p- 192.168.1.1`
   * Performs a full port scan.
8. **Use Default Scripts**\
   `nmap -sC 192.168.1.1`
   * Runs default scripts to gather additional information.
9. **Run Specific NSE Script**\
   `nmap --script http-title 192.168.1.1`
   * Runs the `http-title` script to extract the title of a web page.
10. **Run Multiple Scripts**\
    `nmap --script http-title,http-headers 192.168.1.1`
    * Runs both the `http-title` and `http-headers` scripts.
11. **Use a Decoy to Hide Your IP**\
    `nmap -D RND:10 192.168.1.1`
    * Generates 10 random decoy IPs to obfuscate the scan source.
12. **Scan with Random Port Order**\
    `nmap -r 192.168.1.1`
    * Randomizes the order of scanned ports.
13. **Save Output in Multiple Formats**\
    `nmap -oA scan_results 192.168.1.1`
    * Saves the output in `.nmap`, `.xml`, and `.gnmap` formats.
14. **Save Output in a Plain Text File**\
    `nmap -oN results.txt 192.168.1.1`
    * Saves results in a human-readable text file.
15. **Scan an Entire Subnet**\
    `nmap 192.168.1.0/24`
    * Scans all devices in the 192.168.1.x subnet.
16. **List All Live Hosts (No Port Scan)**\
    `nmap -sn 192.168.1.0/24`
    * Performs a ping scan to list live hosts without scanning ports.

## Scanning Network Example

{% embed url="https://medium.com/@zisansakibhaque/network-scanning-101-c47c655f2d98" %}
