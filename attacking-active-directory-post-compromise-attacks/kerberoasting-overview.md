# Kerberoasting Overview

#### Kerberos Key কী? Kerberos Key হলো Kerberos অথেনটিকেশন প্রোটোকলে ব্যবহৃত ক্রিপ্টোগ্রাফিক কী, যা সুরক্ষিত অথেনটিকেশন ও নিরাপদ টিকিটিং সিস্টেম নিশ্চিত করতে ব্যবহৃত হয়। এই কী-এর মাধ্যমে ব্যবহারকারী ও সার্ভারের মধ্যে এনক্রিপ্টেড অথেনটিকেশন ও তথ্য আদান-প্রদান করা হয়। Kerberos অথেনটিকেশন প্রোটোকলটি শক্তিশালী হলেও, কিছু দুর্বলতা থাকলে আক্রমণকারীরা একে কাজে লাগিয়ে অবৈধভাবে অ্যাক্সেস নিতে পারে।

#### **Kerberoasting Attack কী?**&#x20;

Kerberoasting হলো Windows Active Directory এর উপর একটা জনপ্রিয় আক্রমণ (attack)। এই আক্রমণের মাধ্যমে, অ্যাটাকার (হ্যাকার) Service Account গুলোর Kerberos Ticket সংগ্রহ করে, পরে সেই টিকিট অফলাইনে ক্র্যাক করে পাসওয়ার্ড বের করার চেষ্টা করে।&#x20;

#### **কিভাবে কাজ করে?**&#x20;

_১. তথ্য সংগ্রহ_ (Enumeration) অ্যাটাকার প্রথমে AD (Active Directory) থেকে কোন কোন সার্ভিস অ্যাকাউন্ট আছে, তা বের করে। সার্ভিস অ্যাকাউন্টগুলো সাধারণত উচ্চ অনুমতি (privilege) নিয়ে কাজ করে, তাই এগুলো হ্যাক করলে অনেক সুবিধা পাওয়া যায়।&#x20;

_২. Ticket Request_ অ্যাটাকার Kerberos এর মাধ্যমে টার্গেট সার্ভিসের জন্য TGS (Ticket Granting Service) টিকিট রিকোয়েস্ট করে। AD সার্ভার এই টিকিট ইস্যু করে, যা সার্ভিস অ্যাকাউন্টের পাসওয়ার্ড হ্যাশ দিয়ে সাইন করা থাকে।&#x20;

_৩. Ticket সংগ্রহ ও ক্র্যাকিং_ অ্যাটাকার এই TGS টিকিট সংগ্রহ করে অফলাইনে নিয়ে গিয়ে Hash Cracking Tools দিয়ে পাসওয়ার্ড বের করার চেষ্টা করে। সাধারণত Hashcat বা John the Ripper ব্যবহার করা হয়।&#x20;

<img src="https://web.telegram.org/k/assets/img/emoji/1f3af.png" alt="🎯" data-size="line"> **কেন এটা বিপজ্জনক?**&#x20;

Service Account গুলোর পাসওয়ার্ড সাধারণত দীর্ঘদিন ধরে অপরিবর্তিত থাকে। অনেক সময় এই অ্যাকাউন্টগুলো Domain Admin বা অন্যান্য গুরুত্বপূর্ণ অনুমতি পায়। একবার পাসওয়ার্ড পেয়ে গেলে পুরো নেটওয়ার্কের ওপর নিয়ন্ত্রণ নেওয়া সহজ হয়।&#x20;

#### <img src="https://web.telegram.org/k/assets/img/emoji/1f510.png" alt="🔐" data-size="line"> _**প্রতিরোধের উপায়**_

<img src="https://web.telegram.org/k/assets/img/emoji/2705.png" alt="✅" data-size="line"> Service Account এর পাসওয়ার্ড নিয়মিত পরিবর্তন করুন।&#x20;

<img src="https://web.telegram.org/k/assets/img/emoji/2705.png" alt="✅" data-size="line"> শক্তিশালী পাসওয়ার্ড ব্যবহার করুন।&#x20;

<img src="https://web.telegram.org/k/assets/img/emoji/2705.png" alt="✅" data-size="line"> Managed Service Accounts (MSA) ব্যবহার করার চেষ্টা করুন।&#x20;

<img src="https://web.telegram.org/k/assets/img/emoji/2705.png" alt="✅" data-size="line"> AD Monitoring ও Event Log মনিটরিং করুন (ID 4769)।&#x20;

<img src="https://web.telegram.org/k/assets/img/emoji/2705.png" alt="✅" data-size="line"> Privileged Service Accounts কে খুবই সীমিত করুন।&#x20;

_**সংক্ষেপে -**_ Kerberoasting হলো এমন একটি টেকনিক, যেখানে অ্যাটাকার Kerberos Service Tickets নিয়ে অফলাইনে ক্র্যাক করে সার্ভিস অ্যাকাউন্টের পাসওয়ার্ড বের করে ফেলে।

{% embed url="https://www.crowdstrike.com/en-us/cybersecurity-101/cyberattacks/kerberoasting/" %}
