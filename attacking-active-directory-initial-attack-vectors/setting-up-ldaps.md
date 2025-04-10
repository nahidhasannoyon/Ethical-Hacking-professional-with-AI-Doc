# Setting Up LDAPS

LDAP (Lightweight Directory Access Protocol) কী?\
LDAP (Lightweight Directory Access Protocol) হলো একটি ওপেন প্রোটোকল যা ডিরেক্টরি সার্ভিসে তথ্য সংরক্ষণ, অনুসন্ধান ও পরিচালনা করতে ব্যবহৃত হয়। এটি মূলত নেটওয়ার্কের মধ্যে ইউজার অথেনটিকেশন ও ডিরেক্টরি ম্যানেজমেন্ট সহজতর করার জন্য ব্যবহৃত হয়।

LDAP রিলে আক্রমণ কী?\
LDAP অথেনটিকেশনকে NTLM Relay Attack এর মাধ্যমে এক্সপ্লয়েট করা যায়। যদি LDAP সার্ভার LDAP Signing চালু না করে, তবে আক্রমণকারী NTLM অথেনটিকেশন রিলে করে LDAP অথেনটিকেশন পাস করতে পারে এবং অ্যাক্সেস নিতে পারে।

### **Setting Up Active Directory Lightweight Directory Services (AD LDS) on Windows Server**

Follow these steps to install and configure **AD LDS** on a Windows Server:

***

#### ✅ **Step 1: Start Windows Server and Open Server Manager**

1. Start the Windows Server.
2. Open **Server Manager** from the taskbar.

***

#### ✅ **Step 2: Add the AD LDS Role**

1. In **Server Manager**, click **"Manage"** on the top bar.
2. Select **"Add Roles and Features."**
3. Click **Next** until you reach the **Server Selection** window.
4. Under **Server Roles**, select **"Active Directory Lightweight Directory Services."**
5. A popup will appear → click **"Add Features."**
6. Keep the default settings and click **Next** until you reach the **Install** button.
7. Click **Install** and wait for the installation to finish.

***

#### ✅ **Step 3: Configure AD LDS**

1. After installation, a text link will appear that says:\
   &#xNAN;**"Run Active Directory Lightweight Directory Services setup wizard."**
2. Click on the link to launch the setup wizard.

***

#### ✅ **Step 4: Setup AD LDS Instance**

1. Set the **Instance Name** (e.g., `BrotherDev`).
2. Set a **random port number** (e.g., `5389`, `1300`).
3. On the **LDIF Files** section, check **all options** (Users, Configurations, etc.).
4. Complete the setup with the default settings and finish the wizard.

***

#### ✅ **Step 5: Open and Verify AD LDS Using ADSI Edit**

1. In **Server Manager**, click **"Tools"** (top-right).
2. Select **"ADSI Edit."**
3. In ADSI Edit:
   * Right-click **"ADSI Edit."**
   * Select **"Connect to…"**
   * Set a connection name (e.g., `BrotherDevConnection`).
   * Keep other settings at **default** and click **OK.**
4. Expand the left-side panel and navigate to:\
   **CN=Users**
5. ✅ If the list of users is shown, AD LDS is installed and working correctly!

***

#### 🚀 **AD LDS is now ready to use!** 😎

