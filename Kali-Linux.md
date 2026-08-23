### Gobuster
* runs in the terminal
* automates the scanning for web pages

#### commands
* gobuster dir --url http://www.onlineshop.thm/ -w /usr/share/wordlists/dirbuster/directory-list.txt
  * gobuster -  command-line tool used to perform the discovery of web content
  * dir - Specifies the directory and file enumeration mode, which attempts to discover hidden directories and files on a web server
  * --url http://www.onlineshop.thm/ - Sets the target website that Gobuster will scan
  * -w /usr/share/wordlists/dirbuster/directory-list.txt - Specifies the wordlist Gobuster will use to guess directory and file names


### Hydra
* runs in the terminal
* password-testing tool
* automates login attempts against a target app using a wordlist
* technique known as a dictionary attack
* tool relies on a predefines list of possible passwords

#### commands
* hydra -l admin -P passlist.txt www.onlineshop.thm http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect" -V
  * hydra - The command-line tool used to perform the dictionary attack
  * -l admin Attempts to log in using the username admin
  * -P passlist.txt Specifies the password list to try
  * www.onlineshop.thm Sets the target website
  * http-post-form Indicates that this is an HTTP POST request form
  * "/login:username=^USER^&password=^PASS^:F=incorrect" Specifies how the login request is sent and how Hydra determines whether a login attempt has failed
  * -V Enables verbose output, which displays each username and password attempted
