* Powershell commands are known as cmdlets (command-lets)
* cmdlets follow a consistent verb-noun naming convention
* verb describes the action
* noun specifies the object on which action is performed
    * i.e: Get-Content (retrieves (gets) the content of a file and displays it in the console)
    * Set Location (changes (sets) the current working directory)


## Navigating and Working with Files
#### commands
* Get-Command (what commands one can use)
* get-command -commandtype "function" (display the available commands of type "funciton")
* get-help get-date -examples (will be shown a list of common ways in which the cosen cmdlet can be used)
* get-alias (lists all aliases available)
* find-module (search for modules in online repositories)
    * i.e: find-module -name "powershell*" (whenever we dont know the exact name of the module we can search for similar names by using *) - cmdlet -property "pattern*" (standard powershell syntax)
* install-module (download and install module)
    * i.e: install-module -name "NameOfTheModule"
* get-childitem (lists the files and directories in a localtion specified)
    * get-childitem -path
* set-location (navigate to a different directory)
    * set-location -path ".\documents"
* new-item (create and item: file or directory)
    * new-item -path ".\captain-cabin\captainwardrobe" -itemtype "directory"
* remove-item (remove both directories and files)
    * Remove-Item -Path ".\captain-cabin\captain-wardrobe\captain-boots.txt"
    * Remove-Item -Path ".\captain-cabin\captain-wardrobe"
* copy-item (copy files and directories)
    * Copy-Item -Path .\captain-cabin\captain-hat.txt -Destination .\captain-cabin\captain-hat2.txt
* move-item (move files and directories)
* get-content (read and display the contents of a file)



## Piping, Filtering and Sorting Data
* -eq (equal to) -> This operator can be used to exclude objects from the results based on specified criteria
* -ne (not equal) -> This operator will filter only objects which exceed a specified value. It is important to note that this is a strict comparison, meaning that objects that are equal to the specified value will be excluded from the results
* -gt (greater than) -> This is the non-strict version of the previous operator. A combination of -gt and -eq
* -ge (greater than or equal to)
* -lt (less than) -> Like its counterpart, "greater than", this is a strict operator. It will include only objects which are strictly below a certain value
* -le (less than or equal to) -> Just like its counterpart -ge, this is the non-strict version of the previous operator. A combination of -lt and -eq


#### commands
* | (allows the output of one command to be used as the input for another. creates a sequence of operations where the data flows from one command to the next)
    * Get-ChildItem | Sort-Object Length (Get-ChildItem retrieves the files (as objects), and the pipe (|) sends those file objects to Sort-Object, which then sorts them by their Length (size) property)
    * Get-ChildItem | Where-Object -Property "Extension" -eq ".txt" (filter objects based on specified conditions, returning only those that meet the criteria)
    * Get-ChildItem | Where-Object -Property "Name" -like "ship*" (objects filtered by selecting properties that match -like)
    * Get-ChildItem | Select-Object Name,Length (specific properties from objects or limit the number of objects returned)
* Get-ChildItem | Sort-Object Length -Descending | Select-Object -First 1 (sort and filter the output with the goal of displaying the largest file in a specific directory) - piping more than 2 cmdlets
* select-string (searches for text patterns within files)
    * Select-String -Path ".\captain-hat.txt" -Pattern "hat"


## System and Network Information
#### commands
* get-computerinfo (retrieves comprehensive system information)
* systeminfo (retrieves only a small set of system information)
* get-localuser (lists all local user accounts on the system)
* get-netipconfiguration (provvides detailed information about the network interfaces on the system)
* get-netipaddress (show details for all IP addresses configured on the system even inactive ones)
* get-process (detailed view of all currently running processes)
* get-service (information about the status of services on the machine)
* get-NetTCPConnection (displays current TCP connections, insights into both local and remote endpoints)
* get-filehash (generating file hashes, which is particularly valuable in incident response, threat hunting, and malware analysis, as it helps verify file integrity and detect potential tampering)
* get-item -path "C:\Users\captain\document\captain-cabin\ship-flag.txt" -stream * (view the Alternative Data Streams (ADS) attached to a file through Powershell) -> there can be streams attached to the file such us:
      * :$DATA (default data stream of every NTFS file. It contains the normal file contents and is not an ADS)
      * housinginfo (Alternate Data Stream (ADS) added to this file)



## Scpriting
#### commands
* invoke-command (ssential for executing commands on remote systems, enables efficient remote management and—combining it with scripting—automation of tasks across multiple machines. It can also be used to execute payloads or commands on target systems during an engagement by penetration testers—or attackers alike)
  * get-help invoke-command -examples
   * i.e: Invoke-Command -FilePath c:\scripts\test.ps1 -ComputerName Server01
   * Invoke-Command -ComputerName Server01 -Credential Domain01\User01 -ScriptBlock { Get-Culture }
      * i.e: invoke-command -computername "royalfortune" -scriptblock {get-service}





