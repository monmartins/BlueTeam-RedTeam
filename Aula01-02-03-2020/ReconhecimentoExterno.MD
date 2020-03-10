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


## Openvas

Step 1: Install the server, client and plugin packages:

```
    $ apt-get update -y && apt-get install  \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common -y

    $ add-apt-repository ppa:mrazavi/openvas

    $ apt-get update -y && apt-get install libopenvas9-dev openvas9 sqlite3 -y

    $ apt install texlive-latex-extra --no-install-recommends -y    

    $ apt install texlive-fonts-recommended --no-install-recommends -y

```

Step 2: Update the vulnerability database 
```
    $ greenbone-nvt-sync
    $ greenbone-scapdata-sync
    $ greenbone-certdata-sync
```

Step 2: Add your host to config file: 
```
    $ echo 'ALLOW_HEADER_HOST=<ip or host>' >> /etc/default/openvas-gsa 
    $ echo 'LISTEN_ADDRESS=0.0.0.0' >> /etc/default/openvas-gsa 
```

Step 3: Restart the OpenVAS scanner.
```
systemctl restart openvas-scanner
```

Step 4: Restart the OpenVAS manager.
```
systemctl restart openvas-manager
```

Step 5: Restart the Greenbone security assistant.

```
systemctl restart openvas-gsa
```

Step 6: Then enable restarted services on system boot.

```
systemctl enable openvas-scanner

systemctl enable openvas-manager

systemctl enable openvas-gsa
```

Step 7: Check OpenVAS processes
```
    $ openvasmd --rebuild --progress
```




Links:


https://www.stationx.net/nmap-cheat-sheet/

https://hackertarget.com/nmap-cheatsheet-a-quick-reference-guide/

https://lzone.de/cheat-sheet/Security%20Auditing