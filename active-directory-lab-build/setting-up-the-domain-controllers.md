# Setting Up the Domain Controllers

windows server 2019 setup steps:

First in the virtualbox >> tools >> Tools >> network manager >> create and enable the vboxnet0.&#x20;

now create new windows server 2019 with atleast 60 GB disk with the iso or VHD which is available.&#x20;

set the adapter 1 to Bridged Adapter.

do the set up and set strong password.&#x20;

on lock screen press Crtl + Alt + delete&#x20;



First change the computer name to a more remmberable name.&#x20;



Domain Controller Setup steps:&#x20;

now open the server manager then click manage then add Roles and Features.&#x20;

Click next till Server Roles and in it click Active Directory Domain Service and add the feature and also do the same for Remote Access and Remote Desktop Service, DHCP Server, DNS Server.&#x20;

Add all features of Rol Services of both Remote Access and Remote Desktop Services.&#x20;

lastly click install and then restart the server.&#x20;



Now in Server Manager click on the Flag icon which may have some warnings too.&#x20;

in one the the warning there will be "Promote this server to a domain controller" click on it and then choose Add a new forest and give any domain in Root domain name (eg EHP.com) and then set password and then click install.

then the pc might prompt for sign out. do it.&#x20;

in the same flag icon check for "Complete DHCP setup" and commit the default things.&#x20;

