# Red Team: Summary of Operations

## Table of Contents
- Exposed Services
- Critical Vulnerabilities
- Exploitation

### Exposed Services


Nmap scan results for each machine reveal the below services and OS details:
nmap -Sn 192.168.1.110


This scan identifies the services below as potential points of entry:
- Target 1
  -ssh
  -http
  -rcpbind
  -netbios
  -microsoft-ds



The following vulnerabilities were identified on each target:
- Target 1
  - guessed ssh password michael:michael
  - found plaintext password for MySQL Database in wp-config.php
  -found password hashes in MySQL for Michael and Steven
     -cracked password for Steven with John the ripper: pink84


### Exploitation
_TODO: Fill out the details below. Include screenshots where possible._

The Red Team was able to penetrate `Target 1` and retrieve the following confidential data:
- Target 1
  -All the flag screenshots are in my project folder
