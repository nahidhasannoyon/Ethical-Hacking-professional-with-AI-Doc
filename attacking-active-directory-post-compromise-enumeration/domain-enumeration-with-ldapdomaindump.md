# Domain Enumeration with LDAPdomainDump

what is LDAP? what is LDAPdomainDump? why it is done and what can be gain form it?



LDAPDomainDump\
🔹 LDAPDomainDump একটি Python টুল যা LDAP (Lightweight Directory Access Protocol) থেকে তথ্য সংগ্রহ করে তা বিশ্লেষণযোগ্য ফরম্যাটে সংরক্ষণ করে।\
🔹 এটি সাধারণত BloodHound বা PingCastle-এর সাথে ব্যবহার করা হয়।\
🔹 AD এনভায়রনমেন্টের বিভিন্ন ইউজার, গ্রুপ, কম্পিউটার এবং GPO (Group Policy Objects) সম্পর্কিত তথ্য সংগ্রহ করতে সাহায্য করে।

👉 ব্যবহারের ধাপ:\
ldapdomaindump -u 'DOMAIN\USER' -p 'PASSWORD' -d domain.local\
📌 এটি চালানোর পর JSON, CSV, HTML ফরম্যাটে ডাটা এক্সপোর্ট করা যাবে।



{% embed url="https://www.hackingdna.com/2019/07/recon-ldap-information-using.html" %}



LDAPDOMAINDUMP installation & setup:

```
https://github.com/dirkjanm/ldapdomaindump  
```

```
git clone https://github.com/dirkjanm/ldapdomaindump.git
```

```
cd ldapdomaindump
```

```
ls
```

```
pip install -r requirements.txt --break-system-packages 
```

```
python3 ldapdomaindump -h
```

```
ldapdomaindump

sudo apt install python3-ldapdomaindump -y

sudo ldapdomaindump
```
