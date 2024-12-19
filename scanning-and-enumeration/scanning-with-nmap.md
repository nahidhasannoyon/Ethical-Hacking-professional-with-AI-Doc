# Scanning with Nmap

what is nmap

nmap works with both ip and domain&#x20;

how to get ip address of a server from domain name - nslookup.com



{% embed url="https://sourceforge.net/projects/metasploitable/" %}

Metasploitable is an intentionally vulnerable Linux virtual machine. This VM can be used to conduct security training, test security tools, and practice common penetration testing techniques.



use _ip address_ in metasploitable to get ip address list&#x20;

use _netdiscover -r ip\_address_ to know more info&#x20;

## Some commands

_nmap IP\_ADDRESS --traceroute_

_nmap IP\_ADDRESS -P_

_nmap IP\_ADDRESS -F_

_nmap IP\_ADDRESS -p-_

_nmap IP\_ADDRESS -F -sV_

_nmap IP\_ADDRESS -A_

_<mark style="color:orange;">nmap --script vuln IP\_ADDRESS</mark>_ <mark style="color:orange;background-color:red;">Important</mark>

_nmap -oN FILE\_NAME IP\_ADDRESS_



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

