# Reconhecimento Externo

## NMAP
Ping Sweep For Network
```
    $ nmap -sn -PE <IP ADDRESS OR RANGE>
```

Scan and show open ports: 
```
    $ nmap --open <IP ADDRESS OR RANGE> 
```

Determine open services: 
```
    $ nmap -sV <IP ADDRESS>
```

 Scan two common TCP ports, HTTP and HTTPS: 
```
    $ nmap -p 80,443 <IP ADDRESS OR RANGE> 
```

Scan common UDP port, DNS: 
```
    $ nmap -sU -p 53 <IP ADDRESS OR RANGE> 
```

Scan UDP and TCP together, be verbose on a single host and include optional skip ping: 
```
    $ nmap -v -Pn -SU -ST -p U:53,111,137,T:2125,80,139,8080 <IP ADDRESS>
```

## Nessus
Basic Nessus scan: 
```
    $ nessus -q -x -T html <NESSUS SERVER IP ADDRESS> <NESSUS SERVER PORT 1241> <ADMIN ACCOUNT> <ADMIN PASSWORD> <FILE WITH TARGETS>,txt <RESULTS FILE NAME>.html 

    $ nessus [-vnh] [-c .refile] [-VJ [-T <format>] 
```
Batch-mode scan:
```
    $ nessus -q [-pPS] <HOST> <PORT> <USER NAME> <PASSWORD> <targets-file> <result-file>
```

Report conversion: 

```
    $ nessus -i in. [nsrlnbe] -o out. [xmllnsrlnbelhtmlltxt]
```

## Openvas

Step 1: Install the server, client and plugin packages:

```
    $ apt-get install openvas-server openvas-client openvas-plugins-base openvas-plugins-dfsg 
```

Step 2: Update the vulnerability database 
```
    $ openvas-nvt-sync 
```

Step 3: Add a user to run the client: 
```
    $ openvas-adduser 
```
Step 4: Login: sysadm 

Step 5: Authentication (pass/cert) [pass]: [HIT ENTER] 

Step 6: Login password: <PASSWORD> You will then be asked to add "User rules".

Step 7: Allow this user to scan authorized network by typing: 
```
accept <YOUR IP ADDRESS OR RANGE> 
default deny 
```

Step 8: type ctrl-D to exit, and then accept. 

Step 9: Start the server: 
```
    $ service openvas-server start 
```
Step 10: Set targets to scan: 
Create a text file with a list of hosts/networks to scan. 
```
    $ vi scanme.txt 12 
```
Step 11: Add one host, network per line: 
```
<IP ADDRESS OR RANGE> 
```
Step 12: Run scan: 
```
    $ openvas-client -q 127.0.0.1 9390 sysadm nsrc+ws scanme.txt openvas-output-.html -T txt -V -x 
```

Step 13: (Optional)run scan with HTML format: 
```
    $ openvas-client -q 127.0.0.1 9390 sysadm nsrc+ws scanme.txt openvas-output.txt -T html -V -x 
```