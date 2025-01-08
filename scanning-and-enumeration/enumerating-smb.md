# Enumerating SMB

what is smb --> server mail block.&#x20;

what can we find form it

Steps&#x20;

1. first open metasploitable and do need configuration as vulnerable machine
2. write _msfconsole_ in terminal or search in apps and open metasploit&#x20;
3. run command "search smb" in opened console
4. look out for  "auxiliary/scanner/smb/smb\_ms17\_010" and it's number infront of it. (might be 42)
5. write "use 42" in console then might write "info" to see what can it do.&#x20;
6. check if the target have vulnerability or not
   1. Enter "set RHOSTS IP\_ADDRESS" then "run" if it have vulnerability then it will show.

What is smbclient and what does it can do?&#x20;

write "smbclient --help" to check info

Steps to check list of clients&#x20;

1. write "smbclient -L \\\\\\\IP\_ADDRESS\\\\" to check what are connected
   1. why is \ used in the command
2. write "smbclient \\\\\\\IP\_ADDRESS\\\ SHARENAME" to connect to that SHARENAME client.
3. check if without password (just by pressing enter) can access the client.

