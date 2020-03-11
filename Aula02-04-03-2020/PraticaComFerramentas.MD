# NMAP

Dominio http://testhtml5.vulnweb.com

apt-get install nmap -y


> Disable host discovery. Port scan only.
> Attempts to determine the version of the service running on port

> nmap -Pn -sV testhtml5.vulnweb.com


```


Not shown: 965 filtered ports, 26 closed ports
PORT     STATE SERVICE  VERSION
21/tcp   open  ftp      ProFTPD 1.3.3e
22/tcp   open  ssh      OpenSSH 5.3p1 Debian 3ubuntu7.1 (Ubuntu Linux; protocol 2.0)
80/tcp   open  http     nginx 1.4.1
110/tcp  open  pop3     Courier pop3d
143/tcp  open  imap     Plesk Courier imapd
465/tcp  open  ssl/smtp Postfix smtpd
993/tcp  open  ssl/imap Plesk Courier imapd
995/tcp  open  ssl/pop3 Courier pop3d
8443/tcp open  http     lighttpd
Service Info: Hosts: localhost.localdomain,  rs202995.rs.hosteurope.de; OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 304.66 seconds

Disable host discovery. Port scan only.
Scan with default NSE scripts. Considered useful for discovery and safe
Attempts to determine the version of the service running on port
```

> nmap -Pn -sC -sV testhtml5.vulnweb.com

```
Starting Nmap 7.60 ( https://nmap.org ) at 2020-03-09 20:54 UTC
Stats: 0:00:01 elapsed; 0 hosts completed (1 up), 1 undergoing SYN Stealth Scan
SYN Stealth Scan Timing: About 0.50% done
Stats: 0:00:54 elapsed; 0 hosts completed (1 up), 1 undergoing SYN Stealth Scan
SYN Stealth Scan Timing: About 70.27% done; ETC: 20:55 (0:00:22 remaining)
Nmap scan report for testhtml5.vulnweb.com (176.28.50.165)
Host is up (3.0s latency).
rDNS record for 176.28.50.165: rs202995.rs.hosteurope.de
Not shown: 882 filtered ports, 111 closed ports
PORT    STATE SERVICE  VERSION
21/tcp  open  ftp      ProFTPD 1.3.3e
22/tcp  open  ssh      OpenSSH 5.3p1 Debian 3ubuntu7.1 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   1024 2d:4e:a6:d9:33:4a:f5:cf:fe:7a:e2:55:66:0a:41:ae (DSA)
|_  2048 a1:7d:bd:2c:5d:9f:02:26:da:52:91:c0:2d:20:2f:3c (RSA)
80/tcp  open  http     nginx 1.4.1
|_http-server-header: nginx/1.4.1
|_http-title: SecurityTweets - HTML5 test website for Acunetix Web Vulnerabi...
110/tcp open  pop3     Courier pop3d
|_pop3-capabilities: STLS USER LOGIN-DELAY(10) SASL(LOGIN CRAM-MD5 PLAIN) IMPLEMENTATION(Courier Mail Server) UIDL APOP PIPELINING TOP
| ssl-cert: Subject: commonName=Parallels Panel/organizationName=Parallels/stateOrProvinceName=Virginia/countryName=US
| Not valid before: 2012-11-09T10:32:06
|_Not valid after:  2013-11-09T10:32:06
|_ssl-date: 2020-03-09T20:56:29+00:00; -6m21s from scanner time.
143/tcp open  imap     Plesk Courier imapd
|_imap-capabilities: IMAP4rev1 ACL IDLE SORT OK THREAD=REFERENCES AUTH=PLAIN QUOTA STARTTLSA0001 CHILDREN completed ACL2=UNION CAPABILITY UIDPLUS AUTH=CRAM-MD5 THREAD=ORDEREDSUBJECT NAMESPACE
| ssl-cert: Subject: commonName=Parallels Panel/organizationName=Parallels/stateOrProvinceName=Virginia/countryName=US
| Not valid before: 2012-11-09T10:32:06
|_Not valid after:  2013-11-09T10:32:06
|_ssl-date: 2020-03-09T20:56:30+00:00; -6m21s from scanner time.
993/tcp open  ssl/imap Plesk Courier imapd
|_imap-capabilities: AUTH=PLAIN IMAP4rev1 AUTH=CRAM-MD5 UIDPLUS IDLE CAPABILITY THREAD=ORDEREDSUBJECT CHILDREN completed ACL2=UNIONA0001 ACL OK QUOTA SORT THREAD=REFERENCES NAMESPACE
| ssl-cert: Subject: commonName=Parallels Panel/organizationName=Parallels/stateOrProvinceName=Virginia/countryName=US
| Not valid before: 2012-11-09T10:32:06
|_Not valid after:  2013-11-09T10:32:06
|_ssl-date: 2020-03-09T20:56:28+00:00; -6m21s from scanner time.
| sslv2: 
|   SSLv2 supported
|   ciphers: 
|     SSL2_RC2_128_CBC_WITH_MD5
|     SSL2_RC4_128_EXPORT40_WITH_MD5
|     SSL2_RC4_128_WITH_MD5
|     SSL2_DES_192_EDE3_CBC_WITH_MD5
|     SSL2_RC2_128_CBC_EXPORT40_WITH_MD5
|_    SSL2_DES_64_CBC_WITH_MD5
995/tcp open  ssl/pop3 Courier pop3d
|_pop3-capabilities: PIPELINING UIDL USER LOGIN-DELAY(10) TOP SASL(LOGIN CRAM-MD5 PLAIN) IMPLEMENTATION(Courier Mail Server) APOP
| ssl-cert: Subject: commonName=Parallels Panel/organizationName=Parallels/stateOrProvinceName=Virginia/countryName=US
| Not valid before: 2012-11-09T10:32:06
|_Not valid after:  2013-11-09T10:32:06
|_ssl-date: 2020-03-09T20:56:29+00:00; -6m21s from scanner time.
| sslv2: 
|   SSLv2 supported
|   ciphers: 
|     SSL2_RC2_128_CBC_WITH_MD5
|     SSL2_RC4_128_EXPORT40_WITH_MD5
|     SSL2_RC4_128_WITH_MD5
|     SSL2_DES_192_EDE3_CBC_WITH_MD5
|     SSL2_RC2_128_CBC_EXPORT40_WITH_MD5
|_    SSL2_DES_64_CBC_WITH_MD5
Service Info: Host: localhost.localdomain; OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

Host script results:
|_clock-skew: mean: -6m22s, deviation: 0s, median: -6m22s

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 517.77 seconds
```


> Disable host discovery. Port scan only.
> Scan with default NSE scripts. Considered useful for discovery and safe


> nmap -Pn -sC testhtml5.vulnweb.com
```
Nmap scan report for testhtml5.vulnweb.com (176.28.50.165)
Host is up (2.9s latency).
rDNS record for 176.28.50.165: rs202995.rs.hosteurope.de
Not shown: 986 filtered ports
PORT     STATE  SERVICE
21/tcp   open   ftp
22/tcp   open   ssh
| ssh-hostkey: 
|   1024 2d:4e:a6:d9:33:4a:f5:cf:fe:7a:e2:55:66:0a:41:ae (DSA)
|_  2048 a1:7d:bd:2c:5d:9f:02:26:da:52:91:c0:2d:20:2f:3c (RSA)
80/tcp   open   http
|_http-title: SecurityTweets - HTML5 test website for Acunetix Web Vulnerabi...
110/tcp  open   pop3
|_pop3-capabilities: APOP PIPELINING IMPLEMENTATION(Courier Mail Server) TOP USER UIDL STLS SASL(LOGIN CRAM-MD5 PLAIN) LOGIN-DELAY(10)
| ssl-cert: Subject: commonName=Parallels Panel/organizationName=Parallels/stateOrProvinceName=Virginia/countryName=US
| Not valid before: 2012-11-09T10:32:06
|_Not valid after:  2013-11-09T10:32:06
|_ssl-date: 2020-03-09T20:50:20+00:00; -6m21s from scanner time.
143/tcp  open   imap
|_imap-capabilities: UIDPLUS NAMESPACE STARTTLSA0001 IMAP4rev1 CHILDREN OK THREAD=REFERENCES ACL2=UNION SORT completed ACL AUTH=CRAM-MD5 CAPABILITY AUTH=PLAIN QUOTA IDLE THREAD=ORDEREDSUBJECT
| ssl-cert: Subject: commonName=Parallels Panel/organizationName=Parallels/stateOrProvinceName=Virginia/countryName=US
| Not valid before: 2012-11-09T10:32:06
|_Not valid after:  2013-11-09T10:32:06
|_ssl-date: 2020-03-09T20:50:20+00:00; -6m21s from scanner time.
990/tcp  closed ftps
993/tcp  open   imaps
|_imap-capabilities: completed UIDPLUS THREAD=REFERENCES AUTH=PLAIN OK ACL2=UNIONA0001 ACL SORT IDLE IMAP4rev1 AUTH=CRAM-MD5 CAPABILITY NAMESPACE QUOTA THREAD=ORDEREDSUBJECT CHILDREN
| ssl-cert: Subject: commonName=Parallels Panel/organizationName=Parallels/stateOrProvinceName=Virginia/countryName=US
| Not valid before: 2012-11-09T10:32:06
|_Not valid after:  2013-11-09T10:32:06
|_ssl-date: 2020-03-09T20:50:18+00:00; -6m21s from scanner time.
| sslv2: 
|   SSLv2 supported
|   ciphers: 
|     SSL2_DES_192_EDE3_CBC_WITH_MD5
|     SSL2_RC2_128_CBC_WITH_MD5
|     SSL2_DES_64_CBC_WITH_MD5
|     SSL2_RC4_128_EXPORT40_WITH_MD5
|     SSL2_RC2_128_CBC_EXPORT40_WITH_MD5
|_    SSL2_RC4_128_WITH_MD5
995/tcp  open   pop3s
|_pop3-capabilities: UIDL APOP PIPELINING SASL(LOGIN CRAM-MD5 PLAIN) IMPLEMENTATION(Courier Mail Server) TOP LOGIN-DELAY(10) USER
| ssl-cert: Subject: commonName=Parallels Panel/organizationName=Parallels/stateOrProvinceName=Virginia/countryName=US
| Not valid before: 2012-11-09T10:32:06
|_Not valid after:  2013-11-09T10:32:06
|_ssl-date: 2020-03-09T20:50:18+00:00; -6m21s from scanner time.
| sslv2: 
|   SSLv2 supported
|   ciphers: 
|     SSL2_DES_192_EDE3_CBC_WITH_MD5
|     SSL2_RC2_128_CBC_WITH_MD5
|     SSL2_DES_64_CBC_WITH_MD5
|     SSL2_RC4_128_EXPORT40_WITH_MD5
|     SSL2_RC2_128_CBC_EXPORT40_WITH_MD5
|_    SSL2_RC4_128_WITH_MD5
1000/tcp closed cadlock
3001/tcp closed nessus
3007/tcp closed lotusmtap
5061/tcp closed sip-tls
5190/tcp closed aol
5910/tcp closed cm

Host script results:
|_clock-skew: mean: -6m22s, deviation: 0s, median: -6m22s

Nmap done: 1 IP address (1 host up) scanned in 150.88 seconds
```


> TCP SYN port scan (Default)
> Disable host discovery. Port scan only.
> Scan with default NSE scripts. Considered useful for discovery and safe

> nmap -Pn -sC -sS --top-ports 10 testhtml5.vulnweb.com 
```
Starting Nmap 7.60 ( https://nmap.org ) at 2020-03-09 20:31 UTC
Nmap scan report for testhtml5.vulnweb.com (176.28.50.165)
Host is up (0.24s latency).
rDNS record for 176.28.50.165: rs202995.rs.hosteurope.de

PORT     STATE    SERVICE
21/tcp   open     ftp
22/tcp   open     ssh
| ssh-hostkey: 
|   1024 2d:4e:a6:d9:33:4a:f5:cf:fe:7a:e2:55:66:0a:41:ae (DSA)
|_  2048 a1:7d:bd:2c:5d:9f:02:26:da:52:91:c0:2d:20:2f:3c (RSA)
23/tcp   filtered telnet
25/tcp   filtered smtp
80/tcp   open     http
|_http-title: SecurityTweets - HTML5 test website for Acunetix Web Vulnerabi...
110/tcp  open     pop3
|_pop3-capabilities: UIDL LOGIN-DELAY(10) SASL(LOGIN CRAM-MD5 PLAIN) IMPLEMENTATION(Courier Mail Server) TOP PIPELINING STLS APOP USER
| ssl-cert: Subject: commonName=Parallels Panel/organizationName=Parallels/stateOrProvinceName=Virginia/countryName=US
| Not valid before: 2012-11-09T10:32:06
|_Not valid after:  2013-11-09T10:32:06
|_ssl-date: 2020-03-09T20:24:54+00:00; -6m21s from scanner time.
139/tcp  filtered netbios-ssn
443/tcp  filtered https
445/tcp  filtered microsoft-ds
3389/tcp filtered ms-wbt-server

Host script results:
|_clock-skew: mean: -6m21s, deviation: 0s, median: -6m21s

Nmap done: 1 IP address (1 host up) scanned in 10.74 seconds
```