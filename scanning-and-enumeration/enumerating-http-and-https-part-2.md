# Enumerating HTTP and HTTPS Part 2

use _ip address_ in metasploitable to get ip address list&#x20;

open ip\_address in browser

nmap -F -sV -T4 ip\_address



see all directories using&#x20;

nmap -sV -p 80 --script http-enum ip\_address



what is nikto and why use it&#x20;

nikto -h ip\_address



what is dirbuster, why and how use it?&#x20;
