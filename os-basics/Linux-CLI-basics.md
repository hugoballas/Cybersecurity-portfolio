### CLI: command-line interface

#### commands:
* pwd (print working directory) - show the folder im in
* ls (list)
  * ls -l (lists the content of current directory)
  * ls -al (show hidden files) - start with "."
  * ls --help (list the possible options that the command accepts with a brief descrition and example)
  * man ls (view the manual pages for ls)
* cd < directory > (change directory) - ex: cd Documents
* cd .. (go back "1 level"/"folder")
* cat (read file)
* find ~ -name "filename"
* touch (create file)
* mkdir (create a folder)
* cp (copy a file/folder)
* mv (move file/folder)
* rm (remove file/folder)
* file (determine the type of a file)
* grep (searches inside for text)
  * example: grep "password123" password.txt
* whoami (username)
* echo (output some specific text that is provided)
  * example: echo TryHackMe; echo "hello world"
* uname -a (OS, kernel version and architecture).
* uname (OS name)
* df -h (check disk and storage)

#### example:
* Linux: The system is running the Linux kernel.
* tryhackme: The hostname (the computer’s name).
* < REDACTED >-aws: The kernel version installed on the machine.
* x86_64: The hardware platform (also 64-bit).
* GNU/Linux: The operating system type (Linux kernel + GNU tools).


#### AttackBox (Linux) Commands
* ssh username@192.168.1.10 (connect/log in to an account, use commands while remote) - need password (invisible, doesnt show typing the password)
* su - "user" (whenever i want to login from one user to another)
  * su user2 (new session drops us into previous user's home directory)
  * su -l user2 (new session has dropped us into the home directory of "user" automatically
* su - root (change to root account)
* /etc (commonplace location to store system files that are used by the OS)
* /var (main root folders; stores data that is frequently accessed or written by services or apps running on the system)
* /root (There isn't anything more to this folder other than just understanding that this is the home directory for the "root" user. But, it is worth a mention as the logical presumption is that this user would have their data in a directory such as "/home/root" by default)
* /tmp (volatile and is used to store data that is only needed to be accessed once or twice. Once the computer is restarted, the contents of this folder are cleared out)


#### Combine commands
* & (Runs the command, but does not wait for it to finish before you can do anything else. The command runs in the backgorund, and is helpful for commands that might take a while to complete, or ones that you want to keep running)
  * echo "Hi THM" &
* && (Runs both commands, but waits for the first command to finish first, before the next. Like a set of dominoes)
* ">" (Used to redirect output. We can take the output of a command and send it to a file. This operator will overwrite anything that exists in the file)
* ">>" (This redirector does the same thing, but instead of overwriting, it will just add the output to the bottom of the file)
  * example: echo hey > welcome; echo "test" > thm


### File permission 
* rwxrwxrwx (first 3 -> owner; next 3 -> group; last 3 -> other)
* r = read (4)
* w = write (2)
* x = execute (1)

#### Numeric value
* owner (group): rwx (permission) -> 4+2+1 (calculation) =7 (value)
* group: rwx -> 4+2+1=7
* other: rwx -> 4+2+1=7
* rwxrwxrwx = 777
  *examples:
    * rwxr-xr-x (symbolic) -> 755 (numeric) -> owner can do everything, other can read and execute)
    * rw-r--r-- -> 644 -> owner can read/write, other can only read
    * rwx------ -> 700 -> only the owner has access


### Terminal text editors

#### Nano commands
* nano filename (create or edit file)
* Ctrl = ^

#### Vim commands
* more advanced than nano
* Advantages:
  * Customisable - you can modify the keyboard shortcuts to be of your choosing
  * Syntax Highlighting - this is useful if you are writing or maintaining code, making it a popular choice for software developers
  * VIM works on all terminals where nano may not be installed
  * There are a lot of resources such as cheatsheets(opens in new tab), tutorials, and the sorts available to you use.

### Processes
#### commands
* ps (list of running processes, status code, session that is running it, usage time of the CPU it is using, name/command of the program that is being executed)
  * ps aux (processes run by other users and those that dont run from a session, i.e. system processes)
* top (gives you real-time statistics about the processes running on your system instead of a one-time view. These statistics will refresh every 10 seconds)
* kill "PID" (kill a command, kill a command and the associated PID)
  * SIGTERM - Kill the process, but allow it to do some cleanup tasks beforehand
  * SIGKILL - Kill the process - doesn't do any cleanup after the fact
  * SIGSTOP - Stop/suspend a process
* systemctl (this command allows us to interact with the systemd process/daemon)
  * format: systemctl [option] [service]
  * example: systemctl start apache2 / systemctl stop apache2
  * 5 options for systemctl:
    * start
    * stop
    * enable
    * disable
    * status
* echo "Hi THM" & (running in the background)
* fg (brings script/command back to focus/foreground)


### Automation
#### commands
* cron
* crontabs (processes that is started during boot, which is responsible for facilitating and managing cron jobs. Is simply a special file with formatting that is recognised by the cron process to execute each line step-by-step -> require 6 specific values)
  * MIN (minute to execute at)
  * HOUR (hour to execute at)
  * DOM (day of the month to execute at)
  * MON (monthe of the year to execute at)
  * DOW (day of the week to execute at)
  * CMD (atual command that will be executed)
 * i.e. backingup files such as "cmnatic"'s "Documents" every 12 hours -> 0 */12 * * * cp -R /home/cmnatic/Documents /var/backups/ (if we do not wish to provide a value for that specific field, i.e. we don't care what month, day, or year it is executed -- only that it is executed every 12 hours, we simply just place an asterisk)
 * crontab -e (edit crontab where i can select and editor, i.e. nano.


### Package Management
#### commands
* add-apt-repository (adding repositories)
* apt (part of the package management software: benefits of apt means that whenever we update our system -- the repository that contains the pieces of software that we add also gets checked for updates)
* dpkg (install software through the use of package installers)
  * i.e. adding text editor Sublime Text to an Ubuntu machine as a repository. GPG (Gnu Privacy Guard) keys will guarantee the integrity of what we download. They keys are essencially a safety check from the developers. If the keys do no match up to what the system trusts and what the developers used, then the software will not be downloaded)
     * wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add - (download GPG key and use apt-key to trust it)
     * A good practice is to have a separate file for every different community/3rd party repository that we add
     * /etc/apt/sources.list.d# touch sublime-text.list (create a file name named sublime-text.list in /etc/apt/sources.list.d)
     * use Nano to add & save the Sublime Text 3 repository into this newly created file
     * apt update (updating apt to recognise this new entry)
     * apt install sublime-text (after updating we can now install the software that we have trusted and added to apt)
 * add-apt-repository --remove ppa:PPA_Name/ppa (removing packages)
 * apt remove [software-name-here] (remove software)
    * i.e. apt remove sublime-text
 
