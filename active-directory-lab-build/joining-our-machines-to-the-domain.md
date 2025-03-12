# Joining Our Machines to the Domain

## **Connecting Windows 10 to Windows Server 2019**

### **1. Start Windows Server 2019 and Check IP Address**

✅ **Step 1:** Start Windows Server 2019

* Log in to **Windows Server 2019**.
* Open **Command Prompt** → Type:

```bash
ipconfig
```

* Note down the **IPv4 Address** of the server (e.g., `192.168.1.10`).

***

### **2. Set Up Shared Folder on Windows 10**

✅ **Step 1:** Create a Shared Folder

1. Start **Windows 10 Enterprise**.
2. Create a new folder named **"Shared Folder"**.
3. Right-click the folder → **Properties** → Go to **Sharing** tab.
4. Click **Share** → Choose **Everyone** → Click **Share** → **Done**.

***

✅ **Step 2:** Turn on Network Discovery

* When prompted, select:\
  ✅ **"Yes, turn on network discovery and file sharing…"**

***

### **3. Configure Network Settings on Windows 10**

✅ **Step 1:** Set Server's IP as DNS

1. Right-click on the **Wi-Fi** or **Ethernet** icon in the taskbar.
2. Choose **"Open Network & Internet Settings."**
3. Select **"Change adapter options."**
4. Right-click on **Ethernet** → **Properties**.
5. Select **Internet Protocol Version 4 (TCP/IPv4)** → **Properties**.
6. Choose **"Use the following DNS server addresses:"**
   * **Preferred DNS server:** Enter the IP of the Windows Server 2019 (e.g., `192.168.1.10`).
   * **Alternate DNS server:** Leave blank or use `8.8.8.8`.
7. Click **OK** → **Close**.

***

### **4. Join Windows 10 to Domain**

✅ **Step 1:** Set Domain in System Settings

1. Open **File Explorer** → Right-click on **This PC** → **Properties**.
2. Click **"Change Settings"** under **Computer name, domain, and workgroup settings**.
3. In the **System Properties** window → Click **"Change."**
4. Select **"Domain"** → Enter the **Domain Name** (e.g., `brotherdev.com`).
5. When prompted, enter the **Administrator username** and **password** of the server.
6. Click **OK** → Restart the computer when prompted.

***

### **5. Verify Connection on Windows Server 2019**

✅ **Step 1:** Check Active Directory

1. Open **Server Manager** → **Tools** → **Active Directory Users and Computers**.
2. Expand your **Domain Name** (e.g., `brotherdev.com`).
3. Select **Computers** → Check if the **Windows 10 PC name** appears in the list.

***

### ✅ **Setup Complete!**

🎯 Windows 10 is now successfully connected to Windows Server 2019 through Active Directory! 🚀
