# Enumerating HTTP and HTTPS Part 1

HTTP methods

{% embed url="https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods" fullWidth="false" %}

What does these scripts do?&#x20;

ls -al /usr/share/nmap/scripts/ | grep -e "http-"



nmap -Pn -sV -P 80 -T4 --script http-methods -script-args http-methods.test=all DOMAIN
