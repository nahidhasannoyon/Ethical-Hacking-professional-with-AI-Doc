# Enumerating SMB

What is SMB?

* **SMB (Server Message Block):** A protocol used for sharing files, printers, and other network resources.

#### What Can We Discover Using SMB?

* Shared files and directories.
* Usernames and groups.
* Misconfigurations and vulnerabilities.

#### Steps for Enumerating SMB

**Setting Up the Vulnerable Machine**

1. Open **Metasploitable** and configure it as a vulnerable machine.
2.  Open a terminal or application menu and launch **Metasploit** by typing:

    ```bash
    msfconsole
    ```

**Searching for SMB Modules**

1.  In the Metasploit console, search for SMB-related modules:

    ```bash
    search smb
    ```
2. Look for the module `auxiliary/scanner/smb/smb_ms17_010` in the results.
3. Note the module number (e.g., `42`).

**Using the Module**

1.  Use the module by entering its number:

    ```bash
    use 42
    ```
2.  View detailed information about the module:

    ```bash
    info
    ```
3.  Set the target's IP address to check for vulnerabilities:

    ```bash
    set RHOSTS IP_ADDRESS
    ```
4.  Run the module:

    ```bash
    run
    ```

    * If the target is vulnerable, it will display relevant information.

#### Understanding smbclient

* **smbclient:** A command-line tool used to interact with SMB shares.
* **Capabilities:**
  * Enumerate SMB shares.
  * Access shared resources.
  * Upload and download files.

**Checking smbclient Options**

1.  To view available options and usage:

    ```bash
    smbclient --help
    ```

**Enumerating SMB Shares**

1.  List available shares on a target:

    ```bash
    smbclient -L \\IP_ADDRESS\
    ```

    * Replace `IP_ADDRESS` with the target’s IP.
    * The backslashes `\` are required to escape the SMB path.
2.  Connect to a specific share:

    ```bash
    smbclient \\IP_ADDRESS\SHARENAME
    ```

    * Replace `SHARENAME` with the name of the share.

**Checking Access**

1. When prompted for a password, try pressing `Enter` to check for access without credentials.
   * If successful, this indicates a misconfigured or unsecured share.

#### Summary

* SMB allows for file and resource sharing, but misconfigurations can expose sensitive data.
* Tools like **Metasploit** and **smbclient** help identify vulnerabilities and enumerate shares effectively.
* Properly securing SMB shares is essential to prevent unauthorized access and potential exploitation.

