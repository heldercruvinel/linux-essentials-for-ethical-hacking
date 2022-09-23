Daemons are services that run when the system starts, process running that we dont starts then, Background Processes. When to list the processes, deamons show a "d" letter at the end: sshd, ntpd, etc.

Processes are Instances of a runnig program

To list all process runningo on system -> ps -aux

Systemd <- master daemon <- commands all deamons, it is a service manager, initialization system "init"

Boot system -> Kernel -> Systemd -> mounting file system, starting all services

systemd is the first process to run, that call all others processes 

Show all processes tree -> pstree

systemd units = deamons

To control the deamons -> systemctl (System controller)

To list all unit system runnig -> systemctl list-unit

To list all unit system running with details -> systemctl list-unit -t service

ps command, combined with grep command -> pgrep

to list processes and hardware consume -> htop

To stop and kill a processes -> kill

To list jobs running -> jobs

To stop a job -> Ctrl + z

To run a job in background -> bg [number of job listed with jobs command]

To put a job in foreaground -> fg [number of job listed with jobs command]

To run a command directly in background -> [command] & (Finish the command with &)

To list all possibles signals to use with commando kill the default is 15 -> kill -l
