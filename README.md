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

Getting information from System Manager's Manual from commands -> man + "command"

Getting help about command's options -> "command" + --help

Getting help to find commando by context that you want to do -> apropos + "Part of text about you want todo, like 'usb' ou 'network'"