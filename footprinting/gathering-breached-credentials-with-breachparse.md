---
description: Guide to Gathering Breached Credentials with BreachParse
---

# Gathering Breached Credentials with BreachParse

This guide outlines the steps to gather breached credentials using the BreachParse tool. BreachParse is a tool for parsing breached password datasets to analyze data logs or events associated with security breaches. It helps extract meaningful insights, such as identifying the source of a breach, how it occurred, and the affected components.

#### Prerequisites

* Install `qbittorrent` if it is not already installed on your system.
* Ensure you have sufficient disk space, as the breached password dataset requires over 40GB of space, and copying it will need up to 100GB.

#### Resources

* **BreachParse Repository Links:**
  * [Byte-Capsule-Ltd/breach-parse](https://github.com/Byte-Capsule-Ltd/breach-parse)
  * [hmaverickadams/breach-parse](https://github.com/hmaverickadams/breach-parse)
*   **BreachCompilation Magnet Link:**

    ```
    magnet:?xt=urn:btih:7ffbcd8cee06aba2ce6561688cf68ce2addca0a3&dn=BreachCompilation&tr=udp%3A%2F%2Ftracker.openbittorrent.com%3A80&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969&tr=udp%3A%2F%2Fglotorrents.pw%3A6969&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337
    ```

#### Steps to Use BreachParse

**Step 1: Download the Breached Password List**

1.  Install `qbittorrent`:

    ```bash
    sudo apt install qbittorrent
    ```
2. Open `qbittorrent` and add the provided magnet link to start the download.
   * Note: The file size is over 40GB, so ensure adequate storage space.

**Step 2: Move the Downloaded File to the Appropriate Directory**

1.  Navigate to the download location (e.g., `/home/kali/Downloads`):

    ```bash
    cd /home/kali/Downloads
    ```
2.  Move or copy the downloaded file to the `/opt` directory:

    ```bash
    sudo mv -f breach-parse /opt
    ```

    Alternatively, if you prefer copying (requires \~100GB of disk space):

    ```bash
    sudo cp -r breach-parse /opt
    ```

**Step 3: Set Up and Run BreachParse**

1.  Switch to the root user:

    ```bash
    sudo su
    ```
2.  Navigate to the BreachParse directory:

    ```bash
    cd /opt/breach-parse
    ```
3.  Grant execute permissions to the `breach-parse.sh` script:

    ```bash
    chmod +rwx breach-parse.sh
    ```
4.  Run the BreachParse script with the desired domain (e.g., `@tesla.com`) and output file name:

    ```bash
    ./breach-parse.sh @tesla.com tesla.txt
    ```

    * **Note:** This process may take some time to complete.

**Step 4: View the Extracted Files**

Once the script finishes, it will generate several files in the `/opt/breach-parse` directory:

* `BreachCompilation`
* `tesla-master.txt`
* `tesla-users.txt`
* `tesla-passwords.txt`

1.  To view the contents of a file, use the `cat` command. For example:

    ```bash
    cat tesla-master.txt
    ```
2.  To display the file with line numbers, use:

    ```bash
    cat -n tesla-master.txt
    ```

#### Conclusion

You have successfully set up and used BreachParse to extract breached credentials. Repeat the steps for other domains as needed.
