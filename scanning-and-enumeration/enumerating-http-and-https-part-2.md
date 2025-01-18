# Enumerating HTTP and HTTPS Part 2

**Enumerating HTTP and HTTPS: Part 2**

#### Discovering IP Addresses

* Use **metasploitable** to find the IP addresses in your test environment.
* Once identified, open the target IP address in a browser to view its hosted content.

#### Scanning with Nmap

**Basic Port and Service Scan**

**Command:**

```bash
nmap -F -sV -T4 ip_address
```

**Purpose:**

* Performs a fast scan of common ports.
* Detects services and versions running on the target system.
* The `-T4` option speeds up the scan using a faster timing template.

**Enumerate HTTP Directories**

**Command:**

```bash
nmap -sV -p 80 --script http-enum ip_address
```

**Purpose:**

* Identifies directories and files hosted on the server.
* Useful for discovering hidden or unsecured resources.
* The `--script http-enum` uses Nmap’s scripting engine to perform directory enumeration on HTTP.

{% hint style="info" %}
Some time these file/folders contains some critical info. So it is good lock for them.&#x20;
{% endhint %}

#### Nikto: Web Server Scanner

**What is Nikto?** Nikto is an open-source web server scanner designed to identify security vulnerabilities and misconfigurations. It checks for:

* Outdated server versions.
* Dangerous files and directories.
* Server configuration issues.

**Command:**

```bash
nikto -h ip_address
```

**Why Use Nikto?**

* To quickly identify security weaknesses in web servers.
* To gain insights into server-specific risks.

#### DirBuster: Directory and File Brute-Forcing Tool

**What is DirBuster?** DirBuster is a GUI-based tool used for brute-forcing directories and file names on web servers. It is useful for uncovering hidden files and directories that might not be listed.

**Why Use DirBuster?**

* To find misconfigured or exposed resources.
* To identify potential entry points for exploitation.

**How to Use DirBuster:**

1. Launch DirBuster and enter the target IP address.
2. Select a wordlist to brute-force directory and file names.
3. Configure options like threads and extensions to fine-tune the scan.
4. Start the scan and review results for directories and files.

#### Summary

* Use **Nmap** to identify services, versions, and directories.
* Leverage **Nikto** for detecting vulnerabilities in web servers.
* Employ **DirBuster** to brute-force hidden files and directories. These tools, when combined, provide a comprehensive approach to HTTP/HTTPS enumeration.
