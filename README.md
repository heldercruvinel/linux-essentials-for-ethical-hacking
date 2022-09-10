# Linux Essentials For Ethical Hacking
Commands, examples and references about using linux for ethical hacking

## General information
When terminal information end with "/$" you are logged with normal user

When terminal information end with "/#" you are logged with root user

## The Linux File System
### ** Everything in Linux is file: Networks settings, devices e etc.
The root file system -> /

Directory with binary commands like, ls, cat, vim, etc. -> /bin (Standsfor Binaries)

Directory with "Super" binary commands used to administrate the system -> /sbin (Standsfor Super Binaries)

Directory with system resources -> /usr (Standsfor Unix System Resources)

Carbon copy of /bin -> /usr/bin

Carbon copy of /sbin -> /usr/bin

Library with libs shared between commands -> /usr/lib

Boot file system -> /boot

Root directory that contains files to which the system writes data during the course of its operation -> /var

Temporary files -> /tmp

Library with libs shared between system -> /lib

Users diretories -> /home

Root user diretory -> /root

Devices diretories -> /dev

A central location for all your configuration files, like a nerve centre of Linux machine -> /etc

Linux mount automaticaly devices -> /media

You can mount manually -> /mnt


## Keyboard shortcuts to manipulate the terminal Screen
Open terminal on Ubuntu: Ctrl + Alt + T

To moviments the terminal: Super + Arrow Keys

To increase the terminal font size: Ctrl + Shift and +

To decrease the terminal font size: Ctrl and -

To empty the terminal screen: Ctrl + L

After your command locked the screen, for go back to terminal: Ctrl + C

To stop the commando: Ctrl + Z

When writing a command, to auto complete de command: Tab

To close the terminal: Ctrl + Shift + W


## Linux Usefull Commands
List all directores and files from you are -> ls

Show the full path when you are -> pwd

Open a diretory -> cd

Show all content into a file -> cat (the cat command standsfor concatenate)

Copy a file -> cp (The cp command standsfor copy)

Add a user -> adduser

## Getting Helping in Terminal
Show de full path of a command -> which + "command"

Show your logged user -> whoami

Show id of my logged user -> id

Show pc name on network -> hostname

Show linux name -> uname (standsfor Unix Name)

Show network informations -> ifconfig

Show, manipulate routting, network devices e etc -> ip

Print network connections, routing tables, interface statistics, masquerade connections, and multicast memberships -> netstat

Print network connections, routing tables, interface statistics, masquerade connections, and multicast memberships -> ss

Check de process status -> ps (Standsfor Process Status)

Who is logged into you system -> who

Show all envriment variables -> env

Lists information about all available or the specified block  devices -> lsblk

Utility for displaying information about USB buses in the system and the devices  connected to them -> lsusb

Information about files opened by processes -> lsof

List PCI devices -> lspci

Getting information from System Manager's Manual from commands -> man + "command"

Getting help about command's options -> "command" + --help

Getting help to find commando by context that you want to do -> apropos + "Part of text about you want todo, like 'usb' ou 'network'"

## Getting connection

Getting connection with ssh -> ssh [username]@[IP address]

## User Management

|Command    |Description    |
|-----------|---------------|
|sudo |	Execute command as a different user.|
|su |	The su utility requests appropriate user credentials via PAM and switches to that user ID (the default user is the superuser).| A shell is then executed.|
|useradd |	Creates a new user or update default new user information.|
|userdel |	Deletes a user account and related files.|
|usermod |	Modifies a user account.|
|addgroup |	Adds a group to the system.|
|delgroup |	Removes a group from the system.|
|passwd	| Changes user password.|

## Package Management

|Command    |Description    |
|-----------|---------------|
|dpkg|	The dpkg is a tool to install, build, remove, and manage Debian packages. The primary and more user-friendly front-end for dpkg is aptitude.|
|apt|	Apt provides a high-level command-line interface for the package management system.|
|aptitude|	Aptitude is an alternative to apt and is a high-level interface to the package manager.|
|snap|	Install, configure, refresh, and remove snap packages.| Snaps enable the secure distribution of the latest apps and utilities for the cloud, servers, desktops, and the internet of things.|
|gem|	Gem is the front-end to RubyGems, the standard package manager for Ruby.|
|pip|	Pip is a Python package installer recommended for installing Python packages that are not available in the Debian archive.| It can work with version control repositories (currently only Git, Mercurial, and Bazaar repositories), logs output extensively, and prevents partial installs by downloading all requirements before starting installation.|
|git|	Git is a fast, scalable, distributed revision control system with an unusually rich command set that provides both high-level operations and full access to internals.|

Resources do comando apt ficam na pasta /etc/apt/sources.list.d

## Service and Process Management

In general, there are two types of services: internal, the relevant services that are required at system startup, which for example, perform hardware-related tasks, and services that are installed by the user, which usually include all server services. Such services run in the background without any user interaction. These are also called daemons and are identified by the letter 'd' at the end of the program name, for example, sshd or systemd.

Most Linux distributions have now switched to systemd. This daemon is an Init process started first and thus has the process ID (PID) 1. This daemon monitors and takes care of the orderly starting and stopping of other services. All processes have an assigned PID that can be viewed under /proc/ with the corresponding number. Such a process can have a parent process ID (PPID), known as the child process.

Besides systemctl we can also use update-rc.d to manage SysV init script links. Let us have a look at some examples. We will use the OpenSSH server in these examples. If we do not have this installed, please install it before proceeding to this section.

### Systemctl

After installing OpenSSH on our VM, we can start the service with the following command.

- systemctl start ssh

After we have started the service, we can now check if it runs without errors.

- systemctl status ssh

To add OpenSSH to the SysV script to tell the system to run this service after startup, we can link it with the following command:

- systemctl enable ssh

Once we reboot the system, the OpenSSH server will automatically run. We can check this with a tool called ps.

- ps -aux | grep ssh

We can also use systemctl to list all services.

- systemctl list-units --type=service

It is quite possible that the services do not start due to an error. To see the problem, we can use the tool journalctl to view the logs.

- journalctl -u ssh.service --no-pager

## Kill a Process

A process can be in the following states:

- Running
- Waiting (waiting for an event or system resource)
- Stopped
- Zombie (stopped but still has an entry in the process table).

Processes can be controlled using kill, pkill, pgrep, and killall. To interact with a process, we must send a signal to it. We can view all signals with the following command:

- kill -l

The most commonly used are:

|Signal |Description    |
|-------|---------------|
|1|	SIGHUP - This is sent to a process when the terminal that controls it is closed.|
|2|	SIGINT - Sent when a user presses [Ctrl] + C in the controlling terminal to interrupt a process.|
|3|	SIGQUIT - Sent when a user presses [Ctrl] + D to quit.|
|9|	SIGKILL - Immediately kill a process with no clean-up operations.|
|15|	SIGTERM - Program termination.|
|19|	SIGSTOP - Stop the program.| It cannot be handled anymore.|
|20|	SIGTSTP - Sent when a user presses [Ctrl] + Z to request for a service to suspend. The user can handle it afterward.|

For example, if a program were to freeze, we could force to kill it with the following command:

- kill 9 "PID" 

## Background a Process

Sometimes it will be necessary to put the scan or process we just started in the background to continue using the current session to interact with the system or start other processes. As we have already seen, we can do this with the shortcut [Ctrl + Z]. As mentioned above, we send the SIGTSTP signal to the kernel, which suspends the process.

- ping -c 10 www.hackthebox.eu [Ctrl + Z]
- vim tmpfile [Ctrl + Z]

Now all background processes can be displayed with the following command.

- jobs

The [Ctrl + Z] shortcut suspends the processes, and they will not be executed further. To keep it running in the background, we have to enter the command bg to put the process in the background.

- bg

Another option is to automatically set the process with an AND sign (&) at the end of the command.

- ping -c 10 www.hackthebox.eu &

Once the process finishes, we will see the results.

## Foreground a Process

After that, we can use the jobs command to list all background processes. Backgrounded processes do not require user interaction, and we can use the same shell session without waiting until the process finishes first. Once the scan or process finishes its work, we will get notified by the terminal that the process is finished.

- jobs
- fg [Number of job]

## Execute Multiple Commands

There are three possibilities to run several commands, one after the other. These are separated by:

- Semicolon (;)
- Double ampersand characters (&&)
- Pipes (|)

The difference between them lies in the previous processes' treatment and depends on whether the previous process was completed successfully or with errors. The semicolon (;) is a command separator and executes the commands by ignoring previous commands' results and errors.

- echo '1'; echo '2'; echo '3'

For example, if we execute the same command but replace it in second place, the command ls with a file that does not exist, we get an error, and the third command will be executed nevertheless.

- echo '1'; ls MISSING_FILE; echo '3'

However, it looks different if we use the double AND characters (&&) to run the commands one after the other. If there is an error in one of the commands, the following ones will not be executed anymore, and the whole process will be stopped.

- echo '1' && ls MISSING_FILE && echo '3'

Pipes (|) depend not only on the correct and error-free operation of the previous processes but also on the previous processes' results. We will deal with the pipes later in the File Descriptors and Redirections section.


***** PAREI EM Working with Web Services ****
https://academy.hackthebox.com/module/18/section/74