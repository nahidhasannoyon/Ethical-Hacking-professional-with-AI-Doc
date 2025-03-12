# Setting Up the Domain Controllers

## **Windows Server 2019 Setup Guide**

### **1. Setup in VirtualBox:**

#### ✅ **Step 1:** Configure Network in VirtualBox

1. Open **VirtualBox**.
2. Go to **Tools → Tools → Network Manager**.
3. Create and enable **vboxnet0**.

***

#### ✅ **Step 2:** Create a New Virtual Machine

1. Create a new Virtual Machine for **Windows Server 2019**.
2. Set the following specifications:
   * **Minimum Disk:** 60 GB
   * **ISO/VHD:** Use a valid Windows Server 2019 ISO or VHD.
3. Set **Adapter 1** to **Bridged Adapter** for network connection.

***

#### ✅ **Step 3:** Complete Installation

1. Proceed with the setup.
2. Set a **strong password** for the administrator account.
3. On the lock screen, press **Ctrl + Alt + Delete** to log in.

***

#### ✅ **Step 4:** Rename Computer

1. Open **Settings** → **System** → **About** → **Rename this PC**.
2. Set a memorable name (e.g., **DC-Server**).
3. Restart the server if prompted.

***

### **2. Domain Controller Setup:**

#### ✅ **Step 5:** Add Roles and Features



1. Open **Server Manager**.
2. Click **Manage** → **Add Roles and Features**.
3. Click **Next** until you reach **Server Roles**.
4.  Select the following roles:

    * ✅ **Active Directory Domain Services**
    * ✅ **Remote Access**
    * ✅ **Remote Desktop Services**
    * ✅ **DHCP Server**
    * ✅ **DNS Server**

    <figure><img src="../.gitbook/assets/Screenshot 2025-03-05 144808.png" alt=""><figcaption></figcaption></figure>
5.  Then Select all the **Role Services** in **Remote Desktop Services** and **Remote Access.**

    <figure><img src="../.gitbook/assets/Screenshot 2025-03-05 145119 (1).png" alt=""><figcaption></figcaption></figure>

    <figure><img src="../.gitbook/assets/Screenshot 2025-03-05 145156.png" alt=""><figcaption></figcaption></figure>
6. Click **Install** and wait for the process to complete.
7. Restart the server after installation.

***

#### ✅ **Step 6:** Promote to Domain Controller

1.  In **Server Manager**, click on the **Flag Icon** (may show warnings).

    <figure><img src="../.gitbook/assets/Screenshot 2025-03-05 150824.png" alt=""><figcaption></figcaption></figure>
2. Find the warning **"Promote this server to a domain controller."**
3. Click on it and select **"Add a new forest."**
4. Enter the **Root Domain Name** (e.g., `brotherdev.com`).
5. Set a **password** for the Directory Services Restore Mode (DSRM).
6. Click **Install**.
7. The system may prompt for **sign out** — confirm and sign out.

***

#### ✅ **Step 7:** Complete DHCP Setup

1.  In **Server Manager**, go to the **Flag Icon** (if warnings remain).

    <figure><img src="../.gitbook/assets/Screenshot 2025-03-05 152550 (1).png" alt=""><figcaption></figcaption></figure>
2. Find **"Complete DHCP setup."**
3.  Accept the default settings and **commit**.

    <figure><img src="../.gitbook/assets/Screenshot 2025-03-05 152621 (1).png" alt=""><figcaption></figcaption></figure>

***

### **✅ Setup Complete!**

🎯 Your Windows Server 2019 is now set up as a **Domain Controller** with essential services like **DHCP** and **DNS**!
