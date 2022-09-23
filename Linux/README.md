# Linux commands
-`history`: Linux store any command you type in an archive file. History is the command to use to display this list. You can also clear all the history.
`history -c` Or clear one specific entry. `history -d 12`
- `ls` : The most frequently used command in Linux to list directories
- `pwd` - Print working directory command in Linux
- `cd` - Linux command to navigate through directories
- `mkdir` - Command used to create directories in Linux
- `mv` - Move or rename files in Linux
- `cp` - Similar usage as mv but for copying files in Linux
- `rm` - Delete files or directories
- `touch` - Create blank/empty files
- `ln` - Create symbolic links (shortcuts) to other files
- `cat` - Display file contents on the terminal
- `clear` - Clear the terminal display
- `echo` - Print any text that follows the command
- `less` - Linux command to display paged outputs in the terminal
- `man` - Access manual pages for all Linux commands
- `uname` - Linux command to get basic information about the OS
- `whoami` - Get the active username
- `tar` - Command to extract and compress files in Linux
- `grep` - Search for a string within an output
- `head` - Return the specified number of lines from the top
- `tail` - Return the specified number of lines from the bottom
- `diff` - Find the difference between two files
- `cmp` - Allows you to check if two files are identical
- `comm` - Combines the functionality of diff and cmp
- `sort` - Linux command to sort the content of a file while outputting
- `export` - Export environment variables in Linux
- `zip` - Zip files in Linux
- `unzip` - Unzip files in Linux
- `ssh` - Secure Shell command in Linux
- `service` - Linux command to start and stop services
- `ps` - Display active processes
- `kill` and `killall` - Kill active processes by process ID or name
- `df` - Display disk filesystem information
- `mount` - Mount file systems in Linux
- `chmod` - Command to change file permissions
- `chown` - Command for granting ownership of files or folders
- `ifconfig` - Display network interfaces and IP addresses
- `traceroute` - Trace all the network hops to reach the destination
- `wget` - Direct download files from the internet
- `ufw` - Firewall command
- `iptables` - Base firewall for all other firewall utilities to interface with
-  apt, pacman, yum, rpm - Package managers depending on the distro
- `sudo` - Command to escalate privileges in Linux
- `cal` - View a command-line calendar
- `alias` - Create custom shortcuts for your regularly used commands
- `dd` - Majorly used for creating bootable USB sticks
- `whereis` - Locate the binary, source, and manual pages for a command
- `whatis` - Find what a command is used for
- `top` - View active processes live with their system usage
- `useradd` and `usermod` - Add new user or change existing users data
- `passwd` - Create or update passwords for existing users
- `sudo killall openvpn`: Close OpenVpn
- Check if xterm package exists: `dpkg -l | grep xterm`,If xterm package does not exist , install it `sudo apt install xterm`
- Set lxterminal as x-terminal-emulator by running the following command `sudo update-alternatives --config x-terminal-emulator`

### Bash Scripting
- `touch hello_world.sh` :Create a file named hello_world.sh
- `which bash` : Find the path to bash shell
- Setup of a Bash Script
```
#! usr/bin/bash
echo "Hello World"
```
- `chmod u+x hello_world.sh` Make the Bash script executable, chmod modifies the existing rights of a file for a particular user. We are adding +x to user u.
- You can run the script in the following ways:
```
./hello_world.sh
or
bash hello_world.sh
```
## Raspberry Pi 
- `sudo raspi-config`: Configure Raspberry Pi
- `/usr/bin/dm-tool lock` : Lock screen
- `cat /home/pi/README.txt` `cat <file>` : Displays all the content of the specified file.
- `more /var/log/syslog` `more <file>` : Displays the content of the specified file, page per page (enter or space to continue, q to quit).
- `tail /var/log/syslog` `tail <file>` : Tail allows you to display the end of a file, it’s useful to check new entries in a log file.
- `tail -n20 /var/log/syslog` :You can specify the number of lines to display with -n.
- `tail -f /var/log/syslog` : Option -f to displays new lines in real-time.
- `head /home/pi/file.txt` `head -n20 /home/pi/file.txt` `head <file>` : It’s the same as tail but to display the beginning of a file.
- `grep dhcp /var/log/syslog` `grep <string>` : Grep is a powerful tool to search string in a text. You can use it to search something in a file or to filter the output of another command or script.
`cat /var/log/syslog | grep dhcp
`/home/pi/myscript.sh | grep error
`ls -latr | grep php`
- Lot of options to use with grep, like regular expressions or options to display lines before (-B), after (-A) or around (-C) the search string. You can also use -v to display everything except the input string.
`grep 'dhcp|dns' /var/log/syslog`
`grep -A2 -B4 'Fatal error' /var/log/apache/error.log`
`grep -v 'Notice' /var/log/apache/error.log`
- `w` : Show who is logged on and what they are doing
- `tree` : Analyze current location in the file tree. It will show you the entire lower tree.
- `ifconfig` or `ip a`: Displays your current network configuration, mainly your IP address if connected.
- `sudo ifup eth0` `ifup <interface>` : Enables the specified interface.
`sudo ifdown wlan0` `ifdown <interface>` : Disables the specified interface. Can be useful to disable Wi-Fi if you are already connected by cable for example.
- `sudo rpi-update` : Only use this if you know what you do. This command will update everything on your Raspberry Pi (firmware, packages, …) and can potentially break something.
- `sudo apt install phpmyadmin` `sudo apt install vim htop` `apt install <package>` :  Installs the specified package(s).
- `sudo apt remove vim` `apt remove <package>` : Removes a previously selected package.
- `sudo apt search myadmin` `sudo apt search php` `apt search <search>` : Searches for a package name in the packages list (repository).
- `dpkg -l` `dpkg -l | grep myadmin` `dpkg -l` : Lists all installed packages on your system. You can use grep to find a specific package.
- `sudo reboot` : This command will restart the Raspberry Pi immediately.
- `shutdown -h now` : This is to stop the Raspberry Pi immediately. You can replace “now” by a specific time (shutdown -h 12:05). Don’t use the power switch to stop your Raspberry, you should do it properly by using this command.
- `ps aux` : This command displays all running process on your Raspberry Pi.
The basic command is this one to display everything:
- `ps -u pi` : You can also display process started by a specific user:
- `kill 12345` `kill <pid>`: The kill command allows you to terminate a process. You’ll need the process ID to do this.
- `kill -9 12345` :Sometime you may need to use the -9 option to force all related commands to stop. For example, if you run 20 commands in a script and kill it, it’ll continue to the next line, not exit the program, except if you use the -9 option.
-`killall php`: Killall to stop all occurrences of a program.
- `htop` : This tool is an alternative to top. It’s more user-friendly than top, with colors and dynamic load bars.
- `df` `df -h`: Displays the partition list, with the disk space used and available for each one.
- `vcgencmd measure_temp` : You may not remember it, but this command displays the current CPU temperature.
`raspi-gpio` :  This command allows you to manage the GPIO pins of the Raspberry Pi. You can either set or get a value.
```
raspi-gpio get
raspi-gpio get 20
raspi-gpio set 20 a5
raspi-gpio set 20 op pn dh
```
- `crontab -l crontab -e` : Cron is a tool to schedule tasks on a Raspberry Pi. Crontab is the file where you enter lines for each task to run. `-l` option to display lines. `-e` option to edit lines. You can use sudo before to schedule tasks to run with root privileges.
- `screen -s <name> screen -r <name>`: This tool allows you to let something run in the background even if you close your session. `-s` option to start a new screen with the following name. `-r` option to resume a running screen with this name. You can forget the name if you want, an ID will be generated, use screen `-r` to find it and screen `-r <ID>` to resume it.
With only one screen running, screen `-r` will resume it directly.
- `lsof` :  lsof stands for “List open files”. This command displays all files open on your Raspberry Pi. This can be useful to know why you can’t edit a file, or which file lock the unmount process.
- `watch`: If you are waiting for something, in a file or directory, the watch command can help you to monitor what happens. This will execute the same command every two seconds. You can also change the refresh rate with the `-n` option. `watch -n10 date`
```
watch date 
watch ls -latr 
watch cat output.txt
```
- `netstat`: Netstat is a powerful tool to monitor what your Raspberry Pi is doing with the network. For example, you can see every port open and every traffic flow. But netstat is a complex tool that i can’t explain in detail in a few lines. Basic usages to display all listening connections you can use:
`netstat -l` `-p` option will add the process id (PID).
`netstat -lp` `-c` option allows you to refresh data continuously.
`netstat -lpc`
-`dmesg` :  This command is useful to understand your Raspberry Pi boot problems. It will show you every event that happened in the start sequence.
Here you could see errors with drivers or services and understand why something doesn’t work the way you want. You will get a column with the time elapsed since the beginning of the boot and a text explaining what happened.
There are also normal messages when everything is fine



