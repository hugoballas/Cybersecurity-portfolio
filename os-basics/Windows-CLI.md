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


### File and Disk Managment
#### commands
* chkdsk (checks the file system and disk volumes for errors and bad sectors)
* driverquery (displays a list of installed device drivers)
* sfc /scannow (scans system files for corruption and repairs them if possible)
* dir /a (displays hidden and system files)
* dir /s (displays files in the current directory and all subdirectories)
* tree (visually represent the child directories and subdirectories)
* cd targer_directory (change directory)
* cd  .. (go up one level)
* mkdir directory_name (create a directory)
* rmdir directory_name (remove directory)
* type example (view text files)
* more example (view text files but for longer texts files. displays a single page at a time)
* copy (copy files from one location to another)
      * ie: copy test.txt test2.txt
* move (move files)
* del or erase (delete file)
* copy *.md C"\Markdown (using * when refering to multiple files. will copy all files with the extension .md to the directory C"\Markdown)


### Task and Process Management
#### commands
* tasklist (list of running processes)
* tasklist /? (help page)
* tasklist /fi (displays a set of tasks that match a given criteria specified by the filter)
      * ie: tasklist /FI "imagename eq sshd.exe" (/FI is used to set the filter *image name equals* sshd.exe)
* taskkill /PID target_pid (terminate any task when we know the PID)





# Windows PowerShell
#### commands
