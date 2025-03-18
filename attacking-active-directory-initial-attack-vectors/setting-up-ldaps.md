# Setting Up LDAPS

LDAP (Lightweight Directory Access Protocol) কী?\
LDAP (Lightweight Directory Access Protocol) হলো একটি ওপেন প্রোটোকল যা ডিরেক্টরি সার্ভিসে তথ্য সংরক্ষণ, অনুসন্ধান ও পরিচালনা করতে ব্যবহৃত হয়। এটি মূলত নেটওয়ার্কের মধ্যে ইউজার অথেনটিকেশন ও ডিরেক্টরি ম্যানেজমেন্ট সহজতর করার জন্য ব্যবহৃত হয়।

LDAP রিলে আক্রমণ কী?\
LDAP অথেনটিকেশনকে NTLM Relay Attack এর মাধ্যমে এক্সপ্লয়েট করা যায়। যদি LDAP সার্ভার LDAP Signing চালু না করে, তবে আক্রমণকারী NTLM অথেনটিকেশন রিলে করে LDAP অথেনটিকেশন পাস করতে পারে এবং অ্যাক্সেস নিতে পারে।

start windows server&#x20;

open server manager&#x20;

click manage on top bar then click "Add role and Features" then go to sever selection and choose "Server Roles" and check the "Active Directory Lightweight Directory Services" then add features others will be default and install it.&#x20;

a new wizard will pop up. set instance name (eg. ByteCapsule), random port number (eg. 5389, 1300) then check all in LDIF files others will be default. if success then a new section will be added in side bar named "AD LDS".

click on tools then ADSI Edit then Right click on ADSI Edit and click connect to.. and give a name (eg. Byte) and others will be default. verify by navigate by side bar and see the "CN=Users" where all users will be showen.&#x20;

