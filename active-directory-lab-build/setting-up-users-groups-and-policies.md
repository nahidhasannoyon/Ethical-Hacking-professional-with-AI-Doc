# Setting Up Users, Groups, and Policies

#### **1. Active Directory Configuration**

#### ✅ **Step 1:** Open Active Directory Users and Computers

1. **Log in** to **Windows Server 2019**.
2.  Open **Server Manager** → Click **Tools** → Select **Active Directory Users and Computers**.

    <figure><img src="../.gitbook/assets/Screenshot 2025-03-05 174032.png" alt=""><figcaption></figcaption></figure>

***

#### ✅ **Step 2:** Create a New Organizational Unit (OU)

1. Right-click on the **domain name** (e.g., `brotherdev.com`).
2.  Select **New** → **Organizational Unit**.

    <figure><img src="../.gitbook/assets/Screenshot 2025-03-05 174130.png" alt=""><figcaption></figcaption></figure>
3. Set the **OU name** as **Groups** → Click **OK**.

***

#### ✅ **Step 3:** Move Existing Groups to New OU

1. Expand the **Users** folder.
2. Select all the existing groups.
3.  Right-click → **Move** → Choose **Groups** → Click **OK**.

    <figure><img src="../.gitbook/assets/Screenshot 2025-03-05 174251.png" alt=""><figcaption></figcaption></figure>

***

#### ✅ **Step 4:** Add a New User

1.  Right-click on the **Users** folder → **New** → **User**.

    <figure><img src="../.gitbook/assets/Screenshot 2025-03-05 174337.png" alt=""><figcaption></figcaption></figure>
2.  Fill in the details:

    * **First name**, **Last name**, **User logon name**.

    <figure><img src="../.gitbook/assets/Screenshot 2025-03-05 174441.png" alt=""><figcaption></figcaption></figure>
3. Set a **strong password** and select:
   * ✅ **User must change password at next logon** → Uncheck.
   * ✅ **Password never expires** → Check.
4. Click **Next** → **Finish**.

***

### **2. Create a File Share**

#### ✅ **Step 1:** Open File and Storage Services

1. Open **Server Manager** → **File and Storage Services** (left sidebar).
2.  Go to **Shares** → **TASKS** → **New Share**.

    <figure><img src="../.gitbook/assets/Screenshot 2025-03-05 174939.png" alt=""><figcaption></figcaption></figure>

***

#### ✅ **Step 2:** Configure Share Settings

1. Choose **SMB Share - Quick**.
2. Set **Share Name** → e.g., `Employee`.
3. Leave default settings → Click **Next**.
4.  Click **Create** → **Close** when finished.

    <figure><img src="../.gitbook/assets/Screenshot 2025-03-05 174939 (1).png" alt=""><figcaption></figcaption></figure>

***

### **3. Create and Apply Group Policy**

#### ✅ **Step 1:** Open Group Policy Management

1. Open **Search** → Type `Group Policy Management` → Right-click → **Run as Administrator**.

***

#### ✅ **Step 2:** Create a New GPO

1. Expand **Domains** → Right-click on your **Domain Name** (e.g., `brotherdev.com`).
2.  Select **Create a GPO in this domain, and Link it here…**

    <figure><img src="../.gitbook/assets/Screenshot 2025-03-05 175136.png" alt=""><figcaption></figcaption></figure>
3. Name it **"Disable Windows Defender"** → Click **OK**.

***

#### ✅ **Step 3:** Edit the GPO

1. Right-click on **"Disable Windows Defender"** → Select **Edit**.
2. Go to:
   * **Computer Configuration** → **Administrative Templates** → **Windows Components** → **Windows Defender Antivirus**.
3.  Double-click **"Turn off Windows Defender Antivirus"** → Set to **Enabled** → **Apply**.

    <figure><img src="../.gitbook/assets/Screenshot 2025-03-05 175618.png" alt=""><figcaption></figcaption></figure>
4. Go to **Real-time Protection**:
   *   Double-click **"Turn off real-time protection"** → Set to **Enabled** → **Apply**.

       <figure><img src="../.gitbook/assets/Screenshot 2025-03-05 175706.png" alt=""><figcaption></figcaption></figure>

***

#### ✅ **Step 4:** Enforce the GPO

1.  Right-click on **"Disable Windows Defender"** → Select **Enforced** → **Yes**.

    <figure><img src="../.gitbook/assets/Screenshot 2025-03-05 175357.png" alt=""><figcaption></figcaption></figure>

***

### ✅ **Setup Complete!**

🎯 Your Active Directory setup, file sharing, and Group Policy configuration are now complete!&#x20;
