# Windows CLI
#### commands:
* cd
* cls (clears prompt screen)
* dir (show files on that directory)
* dir /a (show hidden files)
* cd "filename" (goes to specific file)
* dir /s "filename" (searches for the file on that directory)
* type "filename" (read file)
* whoami (username)
* hostname (machine name)
* systeminfo
* ipconfig
* set (check path from the command line)
* ver (OS version)
* ie: driverquery | more ("| more" it is to view page by page)

### Network troubleshooting
#### commands
* ipconfig
* ipconfig /all
* ping target_name (checking if the server can access a particular server on the internet)
* tracert (trace route - traces the network route traversed to reach the target)
    * ie: tracert example.com
* nslookup (looks up a host or domain and returns its IP address)
    * ie: nslookup example.com (will look up using the default name server)
    * ie: nslookup example.com 1.1.1.1 (will use the name server one.one.one.one)
* netstat (displays current network connections and listening ports)
* netstat -h (displays help page)
    * -a (displays all established connections and listening ports)
    * -b (shows the program associated with each listening port and established connection)
    * -o (reveals the process ID (PID) associated with the connection)
    * -n (uses a numerical form for addresses and port numbers)
* 



# Windows PowerShell
#### commands
