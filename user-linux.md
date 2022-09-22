To run commands with [S]uper [U]ser [DO] permissions -> sudo "command"

To [S]witch [U]ser -> su "username" or empty to sudo user

To add a user to sudo -> visudo

Add a user -> adduser "username" 

Delete a user -> userdel

To modify a user account -> usermod

The /etc/passwd file is a text file with one entry per line, representing a user account: -> cat /etc/passwd

passwd file structure:

mark:x:1001:1001:mark,,,:/home/mark:/bin/bash
[--] - [--] [--] [-----] [--------] [--------]
|    |   |    |     |         |        |
|    |   |    |     |         |        +-> 7. Login shell
|    |   |    |     |         +----------> 6. Home directory
|    |   |    |     +--------------------> 5. GECOS
|    |   |    +--------------------------> 4. GID
|    |   +-------------------------------> 3. UID
|    +-----------------------------------> 2. Password
+----------------------------------------> 1. Username

1 - Username. The string you type when you log into the system. Each username must be a unique string on the machine. The maximum length of the username is restricted to 32 characters.

2 - Password. In older Linux systems, the user’s encrypted password was stored in the /etc/passwd file. On most modern systems, this field is set to x, and the user password is stored in the /etc/shadow file.

3 - UID. The user identifier is a number assigned to each user. It is used by the operating system to refer to a user.

4 - GID. The user’s group identifier number, referring to the user’s primary group. When a user creates a file , the file’s group is set to this group. Typically, the name of the group is the same as the name of the user. User’s secondary groups are listed in the /etc/groups file.

5 - GECOS or the full name of the user. This field contains a list of comma-separated values with the following information:
User’s full name or the application name.
Room number.
Work phone number.
Home phone number.
Other contact information.

6 - Home directory. The absolute path to the user’s home directory. It contains the user’s files and configurations. By default, the user home directories are named after the name of the user and created under the /home directory.

7 - Login shell. The absolute path to the user’s login shell. This is the shell that is started when the user logs into the system. On most Linux distributions, the default login shell is Bash.

All groups be in -> /etc/group

To add a new group -> groupadd "group name" 

To all group that you are member -> groups

Command to administer groups -> gpasswd
