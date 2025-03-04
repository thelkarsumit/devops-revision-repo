The questions are divided into categories like Basic Commands, File Permissions, Networking, System Monitoring, Scripting, Package Management, Security, and OS Hardening.

### Basic Commands
1. **What command is used to list files in a directory?**
   - `ls`
   
2. **How can you display the current working directory?**
   - `pwd`
   
3. **What command shows the contents of a file?**
   - `cat filename`
   
4. **How do you create a new directory?**
   - `mkdir directory_name`
   
5. **How do you remove a file?**
   - `rm filename`
   
6. **How do you copy a file from one directory to another?**
   - `cp source_file destination_directory`
   
7. **How do you move or rename a file?**
   - `mv old_name new_name`
   
8. **How do you search for a specific file in the system?**
   - `find /path -name filename`
   
9. **How do you check the size of a file or directory?**
   - `du -sh /path/to/directory`
   
10. **What command is used to change the file permissions?**
    - `chmod permissions filename`

### File Permissions
11. **What does the `chmod 755` command do?**
    - Grants read, write, and execute permissions to the owner and read/execute permissions to group and others.
    
12. **How do you give read, write, and execute permissions to the owner only?**
    - `chmod 700 filename`
    
13. **How can you view the file permissions of a file?**
    - `ls -l filename`
    
14. **How do you change the owner of a file?**
    - `chown username filename`
    
15. **How can you change the group ownership of a file?**
    - `chgrp groupname filename`
    
16. **What does the `umask` command do?**
    - It sets the default file creation permissions.
    
17. **How do you set the `sticky bit` on a directory?**
    - `chmod +t directory_name`
    
18. **What is the command to check the disk usage of the file system?**
    - `df -h`
    
19. **What command will give you the access control list (ACL) for a file?**
    - `getfacl filename`
    
20. **How do you modify the ACL of a file?**
    - `setfacl -m u:username:rwx filename`

### Networking
21. **What command shows the IP address of the system?**
    - `ifconfig` or `ip a`
    
22. **How do you check if a port is open on the local machine?**
    - `netstat -tuln` or `ss -tuln`
    
23. **How do you ping a remote host?**
    - `ping hostname_or_ip`
    
24. **What is the command to view active network connections?**
    - `netstat -an`
    
25. **How do you get the default gateway IP address?**
    - `ip route show`
    
26. **What command is used to display the routing table?**
    - `route -n` or `ip route`
    
27. **How do you disable a network interface?**
    - `ifconfig eth0 down` or `ip link set eth0 down`
    
28. **How do you restart the network service in Linux?**
    - `systemctl restart network` or `service networking restart`
    
29. **How do you view the DNS settings on a Linux machine?**
    - `cat /etc/resolv.conf`
    
30. **What is the command to check DNS resolution?**
    - `nslookup domain_name`

### System Monitoring
31. **What command can be used to view CPU usage?**
    - `top` or `htop`
    
32. **How can you check memory usage on a Linux system?**
    - `free -h` or `top`
    
33. **What is the command to view the system uptime?**
    - `uptime`
    
34. **How do you check disk usage for all mounted filesystems?**
    - `df -h`
    
35. **What is the command to view running processes?**
    - `ps aux`
    
36. **How do you sort processes by memory usage?**
    - `top -o %MEM`
    
37. **How do you monitor disk I/O usage?**
    - `iotop` (may need to be installed)
    
38. **How do you check the number of open files?**
    - `lsof`
    
39. **What command is used to view the system log files?**
    - `journalctl` or `tail -f /var/log/syslog`
    
40. **How do you monitor network activity in real time?**
    - `netstat -tuln` or `iftop`

### Scripting
41. **How do you create a simple bash script?**
    - Use a text editor to create a file with `.sh` extension and include `#!/bin/bash` at the top.
    
42. **How do you execute a bash script?**
    - `./script_name.sh`
    
43. **How do you pass arguments to a bash script?**
    - `./script_name.sh arg1 arg2`
    
44. **What is the command to print output in a bash script?**
    - `echo "message"`
    
45. **How do you store the output of a command in a variable?**
    - `variable=$(command)`
    
46. **How do you loop through a list of items in a bash script?**
    - `for item in list; do ... done`
    
47. **How do you test if a file exists in a bash script?**
    - `if [ -f filename ]; then ... fi`
    
48. **What does `#!/bin/bash` at the start of a script mean?**
    - It specifies the shell to be used to interpret the script.
    
49. **How do you make a script executable?**
    - `chmod +x script_name.sh`
    
50. **How do you create an infinite loop in a bash script?**
    - `while true; do ... done`

### Package Management
51. **What command is used to install a package on Debian-based systems?**
    - `sudo apt install package_name`
    
52. **How do you update all installed packages on an Ubuntu system?**
    - `sudo apt update && sudo apt upgrade`
    
53. **What is the command to remove a package in Debian-based systems?**
    - `sudo apt remove package_name`
    
54. **How do you search for a package in Debian-based systems?**
    - `apt search package_name`
    
55. **How do you install a package on Red Hat-based systems?**
    - `sudo yum install package_name`
    
56. **What command is used to list all installed packages in Red Hat-based systems?**
    - `rpm -qa`
    
57. **How do you upgrade a single package on an Ubuntu system?**
    - `sudo apt install --only-upgrade package_name`
    
58. **How do you view the list of available updates on Red Hat-based systems?**
    - `sudo yum check-update`
    
59. **What command is used to install software packages using Snap?**
    - `sudo snap install package_name`
    
60. **How do you remove an application installed via Snap?**
    - `sudo snap remove package_name`

### Security
61. **What command shows the current user on the system?**
    - `whoami`
    
62. **How do you change the password for a user?**
    - `passwd username`
    
63. **What command is used to add a user to a Linux system?**
    - `sudo useradd username`
    
64. **How do you lock a user account in Linux?**
    - `sudo usermod -L username`
    
65. **How do you check the firewall status in Linux?**
    - `sudo ufw status`
    
66. **What command is used to configure a firewall on Linux?**
    - `sudo ufw allow service_name`
    
67. **How do you set the expiration date for a user account?**
    - `sudo usermod -e YYYY-MM-DD username`
    
68. **What command is used to show active security policies in Linux?**
    - `semanage`
    
69. **How do you enable SELinux in enforcing mode?**
    - `sudo setenforce 1`
    
70. **How do you disable a specific service at boot time?**
    - `sudo systemctl disable service_name`

### OS Hardening
71. **How do you disable a service on Linux?**
    - `sudo systemctl stop service_name`
    
72. **What command is used to disable unused system ports?**
    - `ufw deny port_number`
    
73. **How do you ensure that SSH uses only key-based authentication?**
    - Edit `/etc/ssh/sshd_config` and set `PasswordAuthentication no`
    
74. **How do you prevent users from executing certain commands?**
    - `chmod o-x command_name`
    
75. **What is the command to update the system and apply security patches?**
    - `sudo apt update && sudo apt upgrade`
    
76. **How do you disable root login via SSH?**
    - `sudo nano /etc/ssh/sshd_config`

 and set `PermitRootLogin no`
    
77. **How do you enable automatic security updates on Debian-based systems?**
    - `sudo apt install unattended-upgrades`
    
78. **How can you configure Linux to log failed login attempts?**
    - Edit `/etc/ssh/sshd_config` and set `LogLevel VERBOSE`
    
79. **How do you install a firewall on Linux?**
    - `sudo apt install ufw` (Ubuntu/Debian)
    
80. **What command is used to list all running processes?**
    - `ps aux`
    
81. **How can you configure Linux to automatically run security updates?**
    - `sudo dpkg-reconfigure -plow unattended-upgrades`
    
82. **What is the default SSH port in Linux?**
    - Port 22
    
83. **How do you check the SSH configuration?**
    - `sshd -t`
    
84. **How do you set up IP filtering rules in iptables?**
    - `sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT`
    
85. **How do you secure shared memory?**
    - `sudo mount -o remount,noexec,nosuid,nodev /dev/shm`
    
86. **How do you disable the USB storage driver for hardening?**
    - `sudo modprobe -r usb_storage`
    
87. **How do you enforce password complexity in Linux?**
    - Edit `/etc/login.defs` and set `PASS_MIN_LEN` and `PASS_COMPLEXITY`
    
88. **How do you set up auditing on a Linux system?**
    - `sudo apt install auditd`
    
89. **How do you remove all inactive user accounts?**
    - `sudo userdel -r username`
    
90. **How do you enable system auditing for login attempts?**
    - Edit `/etc/ssh/sshd_config` and set `AuditLogLevel VERBOSE`

---
