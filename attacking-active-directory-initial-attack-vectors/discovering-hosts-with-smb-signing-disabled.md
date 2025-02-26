# Discovering Hosts with SMB Signing Disabled

First check for all the ip address that are available. as we are doing it locally so just enter netdiscover will show the list of all active devices.&#x20;

Check if SMB signing is enabled or not.&#x20;

nmap --script=smb2-secyruty-mode.use -p445 TARGET\_IP





