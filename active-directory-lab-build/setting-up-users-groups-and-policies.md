# Setting Up Users, Groups, and Policies

Log in to windows Server 2019 and open Server Manager

Click Tools and choose Active Directory Users and Computers&#x20;

now right click on domain name (eg EHP.com) and create new Organizational Unit and set name Groups. now select all the groups in the Users folder and move them to Groups folder.&#x20;

Now add new User in the Users folder with strong password and all work is done here.&#x20;



again open Server Manager and go to File and Storage Services in the sidebar. then Shares and click TASKS and choose New Share and give Share Name (eg. employee) with default setting click Create.&#x20;



Now open Group Policy Management with Run as Administrator form search bar.&#x20;

then click Domains and right click on domain name (eg. EHP.com) and choose Create a GPO in this domain and Link  in here... Named "Disable Windows Defender".&#x20;

set yes to Enforced for Disable windows Defender. Now right click and chose edit.&#x20;

then go to "computer configuration" >> Administrative Templates Policy definitions... >>> Windows Component >> Windows Defender Antivirus.

Click on it and enable the Turn off Windows Defender Antivirus and also in the Real-time protection the Turn off real-time protection.&#x20;
