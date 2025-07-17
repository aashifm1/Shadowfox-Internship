# Level-3 Task
## Information Gathering
Use Wappalyzer to identigy the Technology

It contains,
- Web servers ( Ngnix 1.19.0 )
- Operating System ( Ubuntu )
- Programming languages ( PHP, Adobe Flash )
- Reverse proxies ( Ngnix 1.19.0 )

## Attacks Performed
#### 1. XSS (Cross-Site-Scripting)
Trying some xss scripts to see if it actually works.
``` bash
<script>alert(1)</script>
```
The script works. It is a High / Critical Bug

#### 2. IDOR ( Insecure Direct Object Reference )
Classic idor found at where id=1 changed to id=2 gives another use info.

Vulnerable endpoint: http://testphp.vulnweb.com/artists.php
- artists.php?artist=1 ( Username: r4w8173 )
- artists.php?artist=3 ( Username: lyzae )

#### 3. LFI ( Local File Inclusion ) 
Vulnerable endpoint:
``` bash
showimage.php?file=php://filter/convert.base64-encode/resource=showimage.php
```
Response: 200 ok
#### 4. SSRF ( Server-side request forgery )
Vulnerable endpoint:
``` bash
showimage.php?file=http://127.0.0.1:22
```
Response: 200 ok
