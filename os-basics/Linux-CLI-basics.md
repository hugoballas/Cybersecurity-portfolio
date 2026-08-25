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
