# Cyber-Security Internship
### Comapny: Shadowfox
### Duration: 1 Month (01/07/2025 - 01/08/2025)

## Tasks
### Level-1
1) Find all the ports that are open on the website
http://testphp.vulnweb.com/
```bash 
nmap -Pn -sV http://testphp.vulnweb.com/
```
2) Brute force the website http://testphp.vulnweb.com/ and find the
directories that are present in the website.
```bash 
gobuster dir -u http://testphp.vulnweb.com/ -w /usr/share/wordlists/dirb/comman.txt
```
3) Make a login in the website http://testphp.vulnweb.com/ and intercept
the network traffic using wireshark and find the credentials that were
transferred through the network.
``` bash
sudo wireshark
```
- Start capturing in wlp3s0
- Login with username & password
- Stop capturing
- Use filter - http
- Go to POST /userinfo.php
- Hypertext Transfer Protocol -> Exposed Credentials
