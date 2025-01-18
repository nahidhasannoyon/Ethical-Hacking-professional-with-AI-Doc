# Scripting with Bash

## Only ping once

ping \<ip address> -c 1

## Save info in a file and use Grep to find something

ping \<ip address> -c 1 > ip.txt

cat ip.txt | grep "WORD/s YOU ARE LOOKING FOR"

cat ip.txt | grep "WORD/s YOU ARE LOOKING FOR" | cut -d " " -f 4

cat ip.txt | grep "WORD/s YOU ARE LOOKING FOR" | cut -d " " -f 4 | tr -d ":"

<figure><img src="../.gitbook/assets/Screenshot from 2024-11-29 01-10-30.png" alt=""><figcaption></figcaption></figure>



