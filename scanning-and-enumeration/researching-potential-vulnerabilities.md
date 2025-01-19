---
description: Identifying Exploitable Services and Versions
---

# Researching Potential Vulnerabilities

#### Overview

When scanning a target machine or IP, various services and their versions will often be identified. Examples include:

* **IPC Service Samba 3.0.20**
* **SSH Service Version: SSH-2.0-OpenSSH\_4.7p1**

By researching these services and their specific versions, you can determine if any vulnerabilities exist that can be exploited.

#### Exploit Database

* **Exploit-DB (**[**https://www.exploit-db.com/**](https://www.exploit-db.com/)**):** A popular repository for publicly available exploits and proof-of-concept code.
* Use it to search for vulnerabilities related to identified services and versions.

#### Searching for Exploits Locally

For faster results, you can search for exploits locally using the `searchsploit` tool:

**Initial Setup**

1.  Switch to the root user:

    ```bash
    sudo su
    ```
2.  Update `searchsploit` to ensure you have the latest exploit database:

    ```bash
    searchsploit -u
    ```

    * Note: The first update or updates after a long time may take a while, as it may download up to 2 GB of data.

**Searching for Exploits**

1.  Use `searchsploit` to find exploits for a specific service and version:

    ```bash
    searchsploit 'SERVICE VERSION'
    ```

    Example:

    ```bash
    searchsploit Samba 3.0.20
    ```
2. Review the results for relevant exploits.

#### Summary

* Use tools like `searchsploit` and websites like **Exploit-DB** to identify vulnerabilities in detected services and versions.
* Keeping the exploit database updated ensures access to the latest vulnerabilities.
* Local searches using `searchsploit` can save time when working in restricted or offline environments.

