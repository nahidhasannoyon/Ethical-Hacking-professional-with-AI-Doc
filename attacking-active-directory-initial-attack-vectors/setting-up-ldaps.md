# Setting Up LDAPS

what is LDAPS?&#x20;

why it is needed?

start windows server&#x20;

open server manager&#x20;

click manage on top bar then click "Add role and Features" then go to sever selection and choose "Server Roles" and check the "Active Directory Lightweight Directory Services" then add features others will be default and install it.&#x20;

a new wizard will pop up. set instance name (eg. ByteCapsule), random port number (eg. 5389, 1300) then check all in LDIF files others will be default. if success then a new section will be added in side bar named "AD LDS".

click on tools then ADSI Edit then Right click on ADSI Edit and click connect to.. and give a name (eg. Byte) and others will be default. verify by navigate by side bar and see the "CN=Users" where all users will be showen.&#x20;

