# Domain Enumeration with PlumHound

what is PlumHound? why use it and what can be gain form it?&#x20;



{% @github-files/github-code-block url="https://github.com/PlumHound/PlumHound" %}

Clone this project in /opt folder.

run "pip3 install -r [requirements.txt](https://github.com/PlumHound/PlumHound/blob/master/requirements.txt)" in terminal

now start bloodHound then work with PlumHound.





PlumHound\
🔹 PlumHound হল BloodHound-এর জন্য একটি প্রি-অ্যানালাইসিস টুল, যা রিয়েল টাইমে নিরাপত্তা দুর্বলতা বিশ্লেষণ করতে ব্যবহৃত হয়।\
🔹 এটি অডিট রিপোর্ট তৈরি করে, যা ব্লু টিম (Blue Team) সদস্যদের জন্য সহায়ক।\
🔹 মূলত PowerShell এবং JSON ফরম্যাটে তথ্য উপস্থাপন করে।

👉 ব্যবহারের ধাপ:\
pip install plumbhound\
plumbhound --input data.json --output report.json\
📌 এটি BloodHound-এর তথ্য ব্যবহার করে বিস্তারিত রিপোর্ট তৈরি করে।
