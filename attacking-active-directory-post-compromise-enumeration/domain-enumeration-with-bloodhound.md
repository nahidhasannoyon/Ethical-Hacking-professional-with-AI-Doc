# Domain Enumeration with Bloodhound

What is BloodHound? Why it is used? what can be gain from it?



BloodHound\
🔹 BloodHound হল একটি গ্রাফ বিশ্লেষণ টুল যা Active Directory এনভায়রনমেন্টে অ্যাটাক পাথ (Attack Path) চিহ্নিত করতে ব্যবহৃত হয়।\
🔹 এটি Neo4j ডাটাবেজ ব্যবহার করে তথ্য সংরক্ষণ ও বিশ্লেষণ করে।\
🔹 SharpHound নামক ইনজেকশন টুল ব্যবহার করে AD ডাটা সংগ্রহ করা হয়।

👉 ব্যবহারের ধাপ:\
✅ SharpHound দিয়ে ডাটা সংগ্রহ করুন:\
SharpHound.exe -c All\
✅ BloodHound-এ গ্রাফ বিশ্লেষণ করুন:\
Neo4j ডাটাবেজ চালিয়ে BloodHound GUI ওপেন করুন এবং ডাটা ইমপোর্ট করুন।

📌 ব্যবহার:\
Privilege Escalation Paths চিহ্নিত করা\
Domain Admin খুঁজে বের করা\
Kerberoasting অ্যাটাক এনালাইসিস



{% embed url="https://www.hackingarticles.in/active-directory-enumeration-bloodhound/" %}
