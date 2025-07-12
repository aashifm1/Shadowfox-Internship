## Level-2 Task

### 1) A file is encrypted using Veracrypt (A disk encryption tool). The password to access the file is encrypted in a hash format and provided to you in the drive with the name encoded.txt. Decode the password and enter in the vera crypt to unlock the file and find the secret code in it. The veracrypt setup file will be provided to you. 

#### Finding the password to access encrypted file
- Unzip the wordlist file
``` bash
sudo gzip -d /usr/share/wordlists/rockyou.txt.gz
ls /usr/share/wordlists/rockyou.txt  # Verify if it's unzipped.
```
- Use Hastcat 
``` bash
hashcat -m 0 -a 0 encoded.txt /usr/share/wordlists/rockyou.txt
```
- Content of encoded.txt: 482c811da5d5b4bc6d497ffa98491e38  #md5
- Cracked password: password123

#### Installing veracrypt for Parrot OS
- Dowload from https://veracrypt.io/en/Downloads.html

- Install this version: veracrypt-1.26.24-setup.tar.bz2 (PGP Signature)
``` bash
tar -xvjf veracrypt-1.26.24-setup.tar.bz2  # Extract
./veracrypt-1.26.24-setup.tar.bz2 
```
- Run veracrypt-1.26.24-setup-gui-x64
- Accept the Terms & Conditions

#### Veracrypt Window
- Mount Secret.txt
- Use password: password123  # Use password found in encoded.txt
- Open file Shadowfox-Cybersecurity.txt
- Secret code :- never giveup  # Secret code found


### 2) An executable file of veracrypt will be provided to you. Find the address of the entry point of the executable using PE explorer tool and provide the value as the answer as a screenshot.

- PE Explorer is windows only software. So install alternative (i.e Detect-It-Easy)
- Install DIE from https://github.com/horsicq/DIE-engine/releases

``` bash
chmod +x Detect_It_Easy-3.10-x86_64.AppImage
./Detect_It_Easy-3.10-x86_64.AppImage
```
- Open DIE (Detect-it-easy)
- Select Veracrypt.exe file and scan
- Select advanced option at right  # It Shows Entry point
- Entry Point: 004237b0

### 3) Create a payload using Metasploit and make a reverse shell connection from a Windows 10 machine in your virtual machine setup.
### 4) Make a deauth attack in your own network and capture the handshake of the network connection between the device and the router and and crack the password for the wifi. To crack the password create a wordlist that can include the password of your network.
