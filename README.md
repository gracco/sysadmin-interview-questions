Linux System Administrator/DevOps Interview Questions
====================================================

A collection of Linux sysadmin/devops interview questions. Feel free to contribute via pull requests, issues or email messages.


## <a name='toc'>Table of Contents</a>

  1. [Contributors](#contributors)
  1. [General Questions](#general)
  1. [Simple Linux Questions](#simple)
  1. [Medium Linux Questions](#medium)
  1. [Hard Linux Questions](#hard)
  1. [Expert Linux Questions](#expert)
  1. [Networking Questions](#network)
  1. [MySQL Questions](#mysql)
  1. [DevOps Questions](#devop)
  1. [Fun Questions](#fun)
  1. [SRE Questions](#sre)
  1. [Kubernetes Questions](#kubernetes)
  1. [Demo Time](#demo)
  1. [Other Great References](#references)


####[[⬆]](#toc) <a name='contributors'>Contributors:</a>

* [moregeek](https://github.com/moregeek)
* [typhonius](https://github.com/typhonius)
* [schumar](https://github.com/schumar)
* [negesti](https://github.com/negesti)
* peter
* [andreashappe](https://github.com/andreashappe)
* [quatrix](https://github.com/quatrix)
* [biyanisuraj](https://github.com/biyanisuraj)
* [pedroguima](https://github.com/pedroguima)
* Ben


####[[⬆]](#toc) <a name='general'>General Questions:</a>

* What did you learn yesterday/this week?
   - I was reading about differences types of encryption, and their usage, when use an asymmetric key or a symmetric key and what are the limits and applications of GCP when need to encrypt backups for example. 

* Talk about your preferred development/administration environment. (OS, Editor, Browsers, Tools etc.)
  - SO - Linux
    editor - vscode
    Browser- chromium/firefox 
    tools - terraform, vim, git, zsh, oh-my-zsh, python, ansible, terminator, packer, meld, helm, kubectl, aws tools, kubetail, eksctl
    distro - Arch Linux
    environment - i3wm + lxde

* Tell me about the last major Linux project you finished.
  - My major project in life was an e-commerce creation/migration project using opensource tools like centos, java, springcloud, mongodb, centos, rabbitmq, cassandra, kafka+zookeeper, Azure, percona-mysql, NetflixOSS (as API gateway), nodejs, took 2 years to complete, I joined since the very beginning.

* Tell me about the biggest mistake you've made in [some recent time period] and how you would do it differently today. What did you learn from this experience?
  - I hired someone that it's a very good engineer but it's awful into social skills. This new person broke completely the team synergy and at the end the team itself. I learned that friendly > technical skills

* Why we must choose you?
  - I have a lot of experience, with different types of environments, I worked with all three main cloud providers, different size of companies. I have a huge experience scaling services, learning new technologies, automating simple tasks, a cool mind to troubleshoot and solve problems in critical environments. I have been working as tech lead, and product owner for SRE team.

* What function does DNS play on a network?
  - It's on the core for any environment, responsible to translate IP addresses into names, DNS can also provides a load balancer layer using geolocation, service discovery using SRV entry and a lot of others features.

* What is HTTP?
  - HTTP (hypertext transport protocol) it's a protocol that defines how messages are formated and transmitted via web, and what actions webservers and browsers should take in response of various commands.

* What is an HTTP proxy and how does it work?
  - An HTTP proxy it's a service that forwards HTTP connections, for example a user A want's to access a server www.b.com, but for security reasons the user cannot have direct access on internet, so the user's browser will ask for the HTTP proxy to access the website, the webserver from www.b.com will receive a HTTP message from the proxy and will answer as usual, but in the http HEADER from the message will be changed by the HTTP proxy server who will add or change some headers like User-Agent, X-Forwarded-For, used a lot by companies that need to control their users Internet access.

* Describe briefly how HTTPS works.
  - HTTPS uses the same HTTP protocol but creates a security layer(tunnel) using SSL/TLS, on top of it, this prevents anyone modify or inspect what's happening inside this tunnel and ensure the client it's communicating with the right server. The SSL handshake is established and after that all HTTP responses are send by.  

* What is SMTP? Give the basic scenario of how a mail message is delivered via SMTP.
  - SMTP ( Simple Mail transport protocol) works in the application layer, and uses a process called "store and forward", working close to a  MTA (Mail Tranfer Agent), this MTA service sends via SMTP a package with the messages, when this message arrives at the destination, the client will use POP3/IMAP to download it.


* What is RAID? What is RAID0, RAID1, RAID5, RAID10?
  RAID (Redundant Array of Independent Disks) it' s a data storage virtualization technology that combines multiple physical disks in one logical volume.
  - RAID0 - Striping, the data is striped between 2 or more disks, improving speed but compromising availability.
  - RAID1 - Mirroring, the data is mirrored between 2 or more disks, improving availability (the server could lose N - 1 disks) but compromises the speed (replication time).
  - RAID5 -  Blocks striped but uses distributed parity, RAID5 uses minimum 3 disks, that stripe data between them, but replicates blocks too, it's a good RAID for databases, in this cenario read operations are good, but write can be slow.
  - RAID10 - It's a implementation using RAID0 + RAID1, uses 4 disks, striping data between 2 of then and mirroring this data in another 2 disks.

* What is a level 0 backup? What is an incremental backup?
  - Level0 backup it's a full backup (all blocks), an after a level 0 backup, we can initializes an incremental backup rotine ( only the difference between the blocks)

* Describe the general file system hierarchy of a Linux system.
  - /  - root folder
  - /etc - configuration files provided by the package manager
  - /bin - binaries files
  - /sbin - system  binaries files (important binaries for the OS)
  - /boot - Static files for boot processes ( boot loader)
  - /dev - Device files
  - /lib - Essential shared libraries and kernel modules
  - /usr - Secundary hierarchy
  - /mnt - Mounting point for temporary filesystem
  - /media - Mounting point for removable media
  - /opt - Add-on application software packages
  - /srv - Data service provided by this system
  - /tmp - Temporary files
  - /var - Variable data
  - /root - Root user folder
  - /home - Home users folders


####[[⬆]](#toc) <a name='simple'>Simple Linux Questions:</a>

* What is the name and the UID of the administrator user?
  - root, 0

* How to list all files, including hidden ones, in a directory?
  - ls -a or find .

* What is the Unix/Linux command to remove a directory and its contents?
  - rm -R

* Which command will show you free/used memory? Does free memory exist on Linux?
  - free
  - Sure exists, but the Linux kernel creates file caches in ram, so when we see the output from free command, sometimes can show us that we are without memory but this memory is cached by the SO.

* How to search for the string "my konfi is the best" in files of a directory recursively?
  - grep -Rin "my konfi is the best" /folder

* How to connect to a remote server or what is SSH?
  - ssh user@server - simple way
  - SSH (secure shell) it's a cryptographic network protocol, used for remote login to computer systems by users.

* How to get all environment variables and how can you use them?
  - env, set or printenv, will show every variable that login session, we can use setting as variables ex.: TEST=something or using export the variable will be global (can be used by all system users)

* I get "command not found" when I run ```ifconfig -a```. What can be wrong?
  - your PATH variable doesn't have the full path for the ifconfig command.

* What happens if I type TAB-TAB?
  -  It depends which program the user is trying to complete

* What command will show the available disk space on the Unix/Linux system?
  - df -h

* What commands do you know that can be used to check DNS records?
  - dig +trace
  - nslookup
  - whois

* What Unix/Linux commands will alter a files ownership, files permissions?
  - chmod, chown, chattr

* What does ```chmod +x FILENAME```do?
  - Add a execute permission to a file for all users

* What does the permission 0750 on a file mean?
  - Add a permission to the owner of the file write, execute and read, the group of the owner execute and read, and others do nothing

* What does the permission 0750 on a directory mean?
  - Add a permission to the owner of the folder, create, get access and list the directory files,for the group of the owner only enter and list the directory, and nothing for others.
  - +r - User can list the files
  - +w - User can create a file inside the directory
  - +x - User can get into the folder

* How to add a new system user without login permissions?
  - useradd username -s /bin/false

* How to add/remove a group from a user?
  - usermod -a -G groupname username #to add a user in a new group
  - usermod -G [all groups that you want the user into] username #You don't remove the user from a group, you add the user in all groups that this user is suppose to be.
  - newgrp <GroupName> - Updates shell session with new group permissions

* What is a bash alias?
  - It's a shortcut for some bash command

* How do you set the mail address of the root/a user?
  - creating a file called .forward in the user folder
  - editing the file /etc/aliases

* What does CTRL-c do?
  - send a SIGINT to the terminal (it's a polite kill)

* What is in /etc/services?
  - A mapping for services and ports, when a service call a function getportbyname() usually this function goes in this file to check.
  - Example the command netstat or ss without the -n parameter

* How to redirect STDOUT and STDERR in bash? (> /dev/null 2>&1)
  - 1> redirect the STDOUT
  - 1>> redirect the STDOUT in append mode
  - 2> redirect the STDERR
  - 2>> redirect the STDERR in append mode
  - &> redirect both STDERR and STDOUT
  - &>> redirect both STDERR and STDOUT in append mode
  - 2>&1 redirect STDERR to STDOUT

* What is the difference between UNIX and Linux.
  - Linux it's a UNIX "clone" using the same POSIX(Portable Operating System Interface) standards, but UNIX it's a brand, has different copyrights and tools.

* What is the difference between Telnet and SSH?
  - SSH it's encripted and telnet isn't.
  - Telnet can ommit authentication
  - SSH adds overhead to the bandwidth

* Explain the three load averages and what do they indicate. What command can be used to view the load averages?
  - The three load averages indicate the processor usage a estimate in 1 minute, a estimate in 5 minutes and a 15 minutes.
  - top or uptime

* Can you name a lower-case letter that is not a valid option for GNU ```ls```?
  - z

####[[⬆]](#toc) <a name='medium'>Medium Linux Questions:</a>

* What do the following commands do and how would you use them?
 * ```tee```
  - copies the STDOUT to a file, but continues to show the STDOUT.

 * ```awk```
  - awk it's a programming language designed for text processing.

 * ```tr```
   - tr or translate, it's a command to substitute characters.

 * ```cut```
   - cut is a command for text processing, and extracts portion of a text

 * ```tac```
  - tac it's a reverse cat, pritting the file bottom to up.

 * ```curl```
  - curl or cURL is a tool to transfer data from or to a server, using one of the supported protocols. cURL can be called a CLI browser, you can use to authenticate, change the HEADER, and do a lot of stuffs with it.

 * ```wget```
  - wget is a tool for retrieving files using HTTP, HTTPS or FTP.

 * ```watch```
  - Watch it's a tool that runs a specified command repeatedly and displays the result on standard output.

 * ```head```
   - It's a command who shows the beginning of a file, the default it's 10 lines

 * ```tail```
   - It's a command who shows the end of a file, the default it's 10 lines

* What does an ```&``` after a command do?
  - Makes the command run in a background sub shell.

* What does ```& disown``` after a command do?
  - disown control jobs that are running in the system.

* What is a packet filter and how does it work?
  - Packet filter it's the process of passing or blocking packets at a network interface based on source and destination address, port or protocols. The packet filter examines, the header of every packet who passed through and based in the rules, ACCEPT, DROP or REJECT the packet, it's well know as firewall.

* What is Virtual Memory?
  - Virtual memory it's the amount of memory available for the system, physical memory + swap memory (hard disk memory).

* What is swap and what is it used for?
  - Swap it's a disk partition used by the Linux when the physical memory is full, if the system needs more memory resources some inactive pages are copied to swap, it was a common way to increase the computer/server memory using the disk.

* What is an A record, an NS record, a PTR record, a CNAME record, an MX record?
  - A record stands for address, indicates a IP address for a domain
  - NS stands for Name Server record indicates which DNS server is authoritative for that domain ( Where the actual DNS entries are)
  - CNAME stands for canonical name and servers to make one domain to another domain name.
  - MX stands for mail exchange, it's a list of mail exchange servers used by the domain.

* Are there any other RRs and what are they used for?
  - Yes.
  - PRT record stands for pointer record  and maps a IPV4 address to a CNAME
  - SOA record stands for State of Authority and is easily one of the most important DNS records because stores information like when the domain was last updated.
  - SRV record stands for Service Record, is a record that specifies hostname and port number for a specific service, it can be used for service discovery.
  - TXT record stands for Text Information, used by various purposes, as domain ownership for example.

* What is a Split-Horizon DNS?
  - It's the hability of the DNS answer a different answer to a query based on the source of the query. A common use it's when the DNS server for internal and external queries.
   We can use views to configure this.

* What is the sticky bit?
  - It's a permission bit that is set on a file or a directory  that lets only the owner of the file/directory or the root user to delete or rename the file.

* What does the immutable bit do to a file?
  - It makes the file immutable, any user can change the state of the file or create hard links.

* What is the difference between hardlinks and symlinks? What happens when you remove the source to a symlink/hardlink?
  - All files in the linux filesystem are a link to a inode, a hard link is a new link to the same inode (if you remove or rename the old or the new link, the file will be intact, but any change in the data on the inode is reflected in all files that refer to that inode), the file system will only delete the inode if you don't have any link for this inode. Because of that a hardlink only works in files that are in the same file system.

  - A softlink, it's a link that points the link from the inode, so it's a link from a link if the first link change the name or be deleted, the soft link will break, but you can use between differents filesystems.

* What is an inode and what fields are stored in an inode?
  - Each object in the filesystem is represented by a inode that stores all the information about the file, like file type, permissions, owner, group, file size, file access, change and modification time (never birth time), file deletion time, number of links, extended attributes. Each inode has a unique number and you can see all this information using ``` stat filename ``` 

* How to force/trigger a file system check on next reboot?
  - Create a file named forcefsck in the root folder

* What is SNMP and what is it used for?
  - SNMP stands for simple network monitoring protocol, it's a protocol to monitor devices, works in the application layer, has 3 versions now, they are not compatible between each other, and V3 introduced encryption. Messages are transported via UDP.

* What is a runlevel and how to get the current runlevel? 
  - Runlevel it's a preset operational system state, to get the current runlevel uses the command runlevel, or `who -r`

* What is SSH port forwarding?
  - SSH Port forwarding it's a way to create a tunnel between your machine in a destination using ssh.

* What is the difference between local and remote port forwarding?
  - Local port forwading creates a tunnel between a local server and a local client, a remote port uses a local server but with internet ip address to connect a internal service that doesn't have access in the internet.

* What are the steps to add a user to a system without using useradd/adduser?
  - Edit `/etc/passwd` with the new username, configure the home, and shell
  - Edit `/etc/groups` add this new username to some groups
  - Create the user home folder and set the right permissions
  - Reset the user password with passwd username

* What is MAJOR and MINOR numbers of special files?
  - The MAJOR number will set to the kernel with kind of device it is, and MINOR number will set a special characteristics of the device, example if a machine have 2 disks, the MAJOR number will be the same for both, but the MINOR doesn't.

* Describe the mknod command and when you'd use it.
  - mknod command creates a new device in `/dev` but actually udev creates automatically each device, if something very terrible happen we can recreate some devices using mknod to fix or make some backup.

* Describe a scenario when you get a "filesystem is full" error, but 'df' shows there is free space.
  - When a filesystem it's out of inodes. `df -i` will show.

* Describe a scenario when deleting a file, but 'df' not showing the space being freed.
  - when a processing it's using that file. We can use `lsof` to check it.

* Describe how 'ps' works.
  - the ps command read files from /proc which the content of this files are generated by the kernel.

* What happens to a child process that dies and has no parent process to wait for it and what’s bad about this?
  - creates a zombie process, one zombie process it's not a big problem, but each process uses a little size of ram, and uses a PID that's a finite number of it.

* Explain briefly each one of the process states.
  - Created or new state, in this moment the process wait the admission to the ready state, by the scheduler
  - Ready or waiting the process has been loaded into main memory  and is awaiting execution on a CPU
  - Running the process moves into running state when it's chosen for execution.
  - Blocked it's when the process cannot carry without an external change in the state or event, example when a process needs a user input.
  - Terminated it's a state after completing the execution or being explicitly killed, but the process remain as zombie until the parent  process call the wait system call to read its exit status, and finally ending the process lifetime.

* How to know which process listens on a specific port?
  - `lsof -i :$PORT` or `netstat -lp | grep $port` or `ss -lp | grep $port`

* What is a zombie process and what could be the cause of it?
  - Each process when ended enter in zombie state, waiting for the parent process call a wait call and read the exit status, if this wait call never be called, this process will end up as a zombie, and we will need to call a SIGCHLD to the parent process to kill all child process.

* You run a bash script and you want to see its output on your terminal and save it to a file at the same time. How could you do it?
 - Use the tee command
 - `script | tee file`

* Explain what echo "1" > /proc/sys/net/ipv4/ip_forward does.
 - Disable ipv4 ip_forward function from the kernel, as well the routing function

* Describe briefly the steps you need to take in order to create and install a valid certificate for the site https://foo.example.com.
  - Create a key file
  - Uses this key file to create a csr file
  - Send this csr file to a ssl certificate provider
  - Get the crt from the certificate provider with the CA chain and configure into the webserver
  or
  - Uses certbot for your specific case.

* Can you have several HTTPS virtual hosts sharing the same IP?
  - Yes using virtualhosts, but the client needs to support http/1.1, to use name-based virtual host configuration.

* What is a wildcard certificate?
  - It's a certificate that can be used by differents hostnames from a single domain.

* Which Linux file types do you know?
  - Regular file
  - Directory file
  - Special files
    - Block file
    - character file
    - named pipe file
    - symbolic link file
    - socket file

* What is the difference between a process and a thread? And parent and child processes after a fork system call?
  - A fork it's identical process as the parent but with new PID, it has a own memory share, and runs independently from the parent. A thread it's a lightweight process and usually it's just a CPU state with the process containing the remainings. A threads require less overhead then forking or spawning a new process, because doesn't have a new system virtual memory space and environment.
  - Both child and parent process have different PIDs, neither process access the variables of each other, the child process ctime, uptime, stime, cutime and cstime subrotines are set to 0.

* What is the difference between exec and fork?
  - A fork in a simple way, it's a process copy only changing the pid and resource limits, a exec it's a call that basically replaces the entire current process with a new program. It loads the program into the current process space and runs it from the entry point. Example, when we call the find command, our bash forks itself, and in this new fork context, uses exec call to execute the find program.  

* What is "nohup" used for?
  - It's used to create process that are independent from user login, starting a process with nohup it's telling the process to ignore SIGHUP calls, that the signal sent by the kernel when the parent shell is closed.

* What is the difference between these two commands?
 * ```myvar=hello```
 * ```export myvar=hello```
 - The first one create the variable only in the user context, the second in a global context, so this variable can be used by all users.

* How many NTP servers would you configure in your local ntp.conf?
  - 4 it's minimum recommended by RedHat

* What does the column 'reach' mean in ```ntpq -p``` output?
  - It's a octal number, that show the last 8 transactions with the ntp server, this number is a FIFO log, so if same packet doesn't arrive (it's UDP), this number can be different based in the order of the checks.

* You need to upgrade kernel at 100-1000 servers, how you would do this?
  - I would use ansible, but before I will test in some controled group to see if something bad can happen.

* How can you get Host, Channel, ID, LUN of SCSI disk?
  - `cat /proc/scsi/scsi`

* How can you limit process memory usage?
  - Calling the program with limit command, or set the ulimit in the console, or in the /etc/security/limits.d, or in the systemd init script.

* What is bash quick substitution/caret replace(^x^y)?
  - `sed -e 's/^x/^y/g'`

* Do you know of any alternative shells? If so, have you used any?
  - I use zsh, it's 100% bash compatible

* What is a tarpipe (or, how would you go about copying everything, including hardlinks and special files, from one server to another)?
  - It's a way to copy a directory to a server from another preserving permissions and the files, usually I don't copy files from a server to another, I use automation to do the job to recreate the server for me, but if I really need to copy, we could use a tarpipe, or dd.

####[[⬆]](#toc) <a name='hard'>Hard Linux Questions:</a>

* What is a tunnel and how you can bypass a http proxy?
  - We can create a ssh tunnel with ssh -R and redirect the http proxy to our server who has access to the internet.

* What is the difference between IDS and IPS?
  - IDS detect the problem inspecting the packet header and payload and creates a log.
  - IPS detect the problem inspecting the packet header and payload and drops the packet if finds something problematic, based in some pre defined rules.

* What shortcuts do you use on a regular basis?
  - `ai package` - `sudo aptitude install package`
  - `ll` - `ls -lha`
  - `gitcm` - `git commit -m`
  - `gl` - `git pull`
  - `gp` - `git push`
  - `..` - `cd ..`
  - `...` - `cd ../..`
  - `....` - `cd ../../../`

* What is the Linux Standard Base?
  - It's a joint project projected by several Linux distributions under the organizational structure of the Linux Foundation to standardize the sofware system structure, including filesystem hierarchy.

* What is an atomic operation?
  - Atomic operations are program operations that run completly independently from any other process.

* Your freshly configured HTTP server is not running after a restart, what can you do?
  - I would try to see the logs and check what's the problem.

* What kind of keys are in ~/.ssh/authorized_keys and what it is this file used for?
  - Public keys, they are used to authenticate users in the server.

* I've added my public ssh key into authorized_keys but I'm still getting a password prompt, what can be wrong?
  - The permission for authorized_keys file, and .ssh folder, as the path from authorized_keys file needs to be /home/user/.ssh/authorized_keys and right spelled, or your private key has the wrong permission.

* Did you ever create RPM's, DEB's or solaris pkg's?
  - yes using fpm, and using dpkg or rpm.

* What does ```:(){ :|:& };:``` do on your system?
  - creates a forkbomb

* How do you catch a Linux signal on a script?
  - using the command `trap` inside the script

* Can you catch a SIGKILL?
  - No, by security proposes

* What's happening when the Linux kernel is starting the OOM killer and how does it choose which process to kill first?
  - OOM will kill the process that will freed more memory and the least important for the SO.

* Describe the linux boot process with as much detail as possible, starting from when the system is powered on and ending when you get a prompt.
  - BIOS
    - BIOS performs startup based in the hardware, and calls the bootloader.
  - bootloader
    - The bootloader (GRUB2) present options to the user select, and loads the kernel into memory and supplies it with some parameters.
  - kernel
    - The kernel will decompress itself and will setup essential hardware and memory paging, and calls start_kernel() function, and it will perform the majority of system setups like device and driver initialization, scheduler, idle process and then starts separately in the user space the init process (pid 1).
  - init
    -The init it's scripts executed by shell (sysV, runit) or configuration files that are executed by binaries (upstart, systemd), init has specific levels, that are passed as variable at the call, with consists of specifics set of daemons. These will provide various non-operating system services and structures and form the user environment.
  - User enviroment
    - The typical desktop environment begins with a daemon that calls everything needed.
  To shudown, it's the inverse, the kernel kills every process, and shut itself down.

* What's a chroot jail?
  - Chroot jail it's a way to isolate a process and its children from the rest of the system. The idea is that you create a directory tree where you copy or link in all the system files needed for a process to run, usually we use bind to mount some folder inside a chroot.

* When trying to umount a directory it says it's busy, how to find out which PID holds the directory?
  - lsof directory

* What's LD_PRELOAD and when it's used?
  - LD_PRELOAD it's a variable that can be used to load some library before the default C library, can be used to test a new version for a library, or for development proposes.

* You ran a binary and nothing happened. How would you debug this?
  - strace binary, and see what's happening.

* What are cgroups? Can you specify a scenario where you could use them?
  - Cgroups are a Linux kernel feature that allow us limit the resource use for a group of process(CPU, memory, disk I/O). A scenario to use could be to test a software in a physical machine that has a big hardware, and make this software run a minimum configuration, a very common sofware that uses cgroups it's docker.


####[[⬆]](#toc) <a name='expert'>Expert Linux Questions:</a>

* A running process gets ```EAGAIN: Resource temporarily unavailable``` on reading a socket. How can you close this bad socket/file descriptor without killing the process?
  - using gdb, attach the gdb in the process and close the file descriptor or socket that is with problem, and detach.


####[[⬆]](#toc) <a name='network'>Networking Questions:</a>

* What is localhost and why would ```ping localhost``` fail?
  - Localhost it's the internal interface in Linux, that some programs can use to talk to each other inside the server. The ping will fail if the lo interface is down, or if we don't resolve localhost in our /etc/hosts file or some firewall rule it's enabled dropping ICMP packets.

* What is the similarity between "ping" & "traceroute" ? How is traceroute able to find the hops.
  - Both use ICMP (Internet control message protocol) packets to archive their proposes, but traceroute sends the packets gradually increasing the TTL value, starting with TTL 1. The first router  receives the packet, decrements the TTL value and drops the packet because the TTL has zero. The router sends an ICMP Time Exceeded message back to the source.


* What is the command used to show all open ports and/or socket connections on a machine?
  - `lsof -i`
  - `netstat -a`
  - `ss -a`

* Is 300.168.0.123 a valid IPv4 address?
  - no

* Which IP ranges/subnets are "private" or "non-routable" (RFC 1918)?
  - 10.0.0.0/8
  - 192.168.0.0/16
  - 172.16.0.0/16

* What is a VLAN?
  - It's a virtual lan created to separate networks inside a switch, making the broadcast domain shorter, and for security proposes. Works in the network layer (OSI Layer 2)

* What is ARP and what is it used for?
  - It's a layer 2 protocol that maps IP address to MAC address.

* What is the difference between TCP and UDP?
  - TCP it's more reliable but slower, because we are sure that our packets will arrive, and UDP it's faster but unreliable because doesn't have confirmation for each package.

* What is the purpose of a default gateway?
  - The default gateway it's the way to get in other networks.

* What is command used to show the routing table on a Linux box?
 - route
 - netstat -r
 - ip route list
 - ip r

* A TCP connection on a network can be uniquely defined by 4 things. What are those things?
 - remote-ip-address
 - remote-port
 - source-ip-address
 - source-port

* When a client running a web browser connects to a web server, what is the source port and what is the destination port of the connection?
  - source port it's dynamic based on net.ipv4.ip_local_port_range defined between 32768 - 61000, destination port 80 or 443.

* How do you add an IPv6 address to a specific interface?
  - using ip -6 addr command, or using ifconfig ip inet6, or editing the SO file for network interfaces.

* You have added an IPv4 and IPv6 address to interface eth0. A ping to the v4 address is working but a ping to the v6 address gives yout the response ```sendmsg: operation not permitted```. What could be wrong?
  - can be a firewall rule

* What is SNAT and when should it be used?
  - SNAT stands for Source Network Address Translation - changes the source address in IP header of a packet. The typical usage is to change the private address/port to a public address/port for packets leaving the network.

* Explain how could you ssh login into a Linux system that DROPs all new incoming packets using a SSH tunnel.
  - We could login using some DRAC interface if the machine it's physical, or we can use the libvirt, or vmware console if virtual, or aws console.

* How do you stop a DDoS attack?
  - You try to block the source address of the attack, or we use some CDN.

* How can you see content of an ip packet?
  - capturing the packet with tcpdump, and opening with wireshark.


####[[⬆]](#toc) <a name='devop'>DevOps Questions:</a>

* Can you describe your workflow when you create a script?
  - First I think about the problem, then create some concept to solve a small part of the problem, than I interate on top of if, adding more layers of complexity, at the end I test, and run some lint, create a pull request and submit to the team evaluate the solution proposed.

* What is GIT?
  - It's a SCM (source code management), it's a software that controls source code, and helps developers to work together and to share code.

* What is a dynamically/statically linked file?
  - dynamically uses the dynamic path for the file example ../../file
  - statically uses the static path for the file example /usr/local/bin/file

* What does "./configure && make && make install" do?
  - Compiles a source code, creates a binary file and copy to a pre defined path

* What is puppet/chef/ansible used for?
  - Automatize infrastructure, you create a code and run this code against an infrastructure

* What is Nagios/Zenoss/NewRelic used for?
  - Monitoring infrastructure and services.

* What is the difference between Containers and VMs?
  - VMs have all the OS stack, devices and so, containers uses the cgroup implementation from the kernel, and have a smaller footprint because of that.

* How do you create a new postgres user?
  - `createuser command`

* What is a virtual IP address? What is a cluster?
  - Virtual IP address, it's IP address defined in a virtual interface, a cluster it's 2 or more machines working together to delivery a service.

* How do you print all strings of printable characters present in a file?
  - using the command strings

* How do you find shared library dependencies?
  - `ldd /fullpath/command`
  - `readelf -d /fullpath/command`

* What is Automake and Autoconf?
  - They are programming tools to automate parts of the compilation process.

* ./configure shows an error that libfoobar is missing on your system, how could you fix this, what could be wrong?
  - Installing the dev or devel version of the lib, that will contain the source code to be compiled 

* What are the advantages/disadvantages of script vs compiled program?
  - Scripts are easy to correct and see how works, compiled are much faster

* What's the relationship between continuous delivery and DevOps?
  - Continous delivery it's one subject inside the DevOps methodology, this subject explain and show us how to delivery sofware or services fast, without human intervention.

* What are the important aspects of a system of continuous integration and deployment?
  - testing, automatize the process, decrease human error, automate quality of code, check of vulnerabilities, lint to have a more reliable and trustful process/delivery

####[[⬆]](#toc) <a name='fun'>Fun Questions:</a>

* A careless sysadmin executes the following command: ```chmod 444 /bin/chmod ``` - what do you do to fix this?
  - find the library that controls the chmod command, with ldd, after that call the  /lib64/ld-linux-x86-64.so.2 /bin/chmod +x /bin/chmod

* I've lost my root password, what can I do?
  - you can use another administrator account to access and reset, or you can reset the server passing in the grub2 init=/bin/bash and reset the password.

* I've rebooted a remote server but after 10 minutes I'm still not able to ssh into it, what can be wrong?
  - network issues, or some fsck it's running, or some service locked the startup.

* If you were stuck on a desert island with only 5 command-line utilities, which would you choose?
  - cd, vim, cat, awk, find

* You come across a random computer and it appears to be a command console for the universe. What is the first thing you type?
  - lshw

* Tell me about a creative way that you've used SSH?
  - a for loop to send via ssh a command to 50 vms.
  - to connect in an internal deployed gitlab service, using a IPSec VPN connected in a bastion host.

* You have deleted by error a running script, what could you do to restore it?
  - I could copy the file descriptor from the /proc/PID/fd/number_of_file_descriptor into a new file.

* What will happen on 19 January 2038?
  - The standard time libray from C was developed using 4-byte to storage time and 4-byte integer its, a 2 trillion number, that in seconds, translates to January 2038, in that time some mainframes could have some issue, openbsd is already patched.

####[[⬆]](#toc) <a name='SRE'>SRE Questions:</a>
* Can you explain what SLA means?

* What's the “five nines” (“nine fives”, “two and a half nines”) uptime?

* What would be the good SLI for an API service? How would you use an SLI to meet the SLO?

* What are the SRE Signals?

* True or false, you should always aim to make your service as reliable as it can possibly be?

* Explain the differences between GKE ingress and Nginx Ingress

* As an SRE, what is your choice?


####[[⬆]](#toc) <a name='kubernetes'>Kubernetes and Docker Questions:</a>

* Describe a simple approach to efficient manage container resources K8S cluster
  - In the pod or deployment specification you can set `limits` for that container or `requests`
  - Seting a request for Containers in a pod, the scheduler it will use this information to decide which node to run that container, the container can if needed use more resource than what it was set in the request.
  - Setting a limit it will limit the container to use maximum that amount of memory or CPU cycles, this is enforced by the kubelet the container. If only limits is set the kube scheduler it will set the request that matches the limit.
  - When a process tries to use more than the allowed amount of memory the system kernel terminates the process with a OOM Error ( out of memory ) 
  - Configure a HPA

* What are the layers in Docker and why are they useful?
  - Docker layer it's a file generated from running some command during a docker build, and be accessed in the docker host `/var/lib/docker/aufs/diff`, they can be used as cache.
    - `docker history [image name]` shows all layers 
  - Because of the usage of AUFS ( Advanced multi-layered unification filesystem ) when docker mounts those layers a diff is applied and layers are reused.

* What features of the Linux kernel enable Docker to work?
  - CGroups
  - Namespaces

* What is the difference between the COPY and ADD commands in a Dockerfile?
  - ADD and COPY have the same usage but ADD supports tar and remote url handling, so you can download files or untar directly in the image.

* Describe the lifecycle of a Pod? What is the phase of a Pod?
  - Pods are considered ephemeral rather ahtn durable entities, and are created, assigned an unique ID and scheduled to a node, do not self-heal by themselves, if the node goes down, a new pod with new ID is rescheduled.
  - Pods have status and a `PodStatus` field which has `phase` field and it can be:
    - Pending: The Pod has been accepted by Kubernetes Cluster, but one or more containers has not been set up. This includes the time that a Pod spends waiting download container images.
    - Running: The Pod has been bound to a node, and all of the containers have been created.
    - Suceeded: All containers in the Pod have terminated in success, and will not be restarted.
    - Failed: All containers in the Pod have terminated, and at least one conetainer has terminated in failure. That is. the container either exited with non-zero status or was terminated by the system.
    - Unknown: For some readon the state of the Pod could not be obtained. This phase typically occurs dut to an error in communicating with the node where the Pod should be running.

* What are three types of handlers to perform a diagnostic by Kubernetes engine?
  - A probe is a diagnostic performed by the kubelet on a Container, to diagnost the kubelet calls a handler implemented by the container.
  - ExecAction: Executes a specified command inside the container. The diagnostic is considered successful if the command exits with a status code of 0.
  - TCPSocketAction: Performs a TCP check agains the Pod's IP address on a specific port. The diagnostic is considered successful if the command the port is open.
  - HTTPGetAction: Performs an HTTP GET request against the Pod's IP address on a specified port and path. The Diagnostic is considered succesful if the response has a status code greater or equal to 200 and less than 400.

* When should you use a liveness, readiness and startup probe?
  - The kubelet use liveness probes to know when to restart a container, one example is a deadlock. Readiness probe is used when the kubelet needs to know if the container is ready to accept traffic, and this signal is used to control which Pods are used as backend Services. When is not ready is removed from Service load balancer. The startup probe is used by kubelet to know when a container application has started, if is configured, it disables liveness and readiness checks until succeeds. This can be used to adopt liveness checks on slow starting containers, avoiding them getting killed by the kubelet before they are up and running.

* What are Init Containers?  How do they differ from regular containers? Why are they useful?
  - Init containers are used by Pods to run before the app container start. They differ from app containers, as they always need to run to completion, so they don't have probes, and each init container must complete successfully before the next one starts, if not the kubelet it will apply the `restartPolicy` defined in the Pod, until the init container is succesful. They are useful because they can be used by a blocker or delay of dependencies, to start Pods in parallel, they can run utilities that would make the app container less secure.

* postStart & preStop events?
  - Kubernetes has component lifecycle hooks and they are exposed at the container level:
    - `PostStart` is executed immediately after a container is created.
    - `PreStop` is called immediately before a container is terminated due to an API request or management event, such as probes.

* Why use a Statefulset?
  - Stateful sets different than deployments, have a unique network identifiers, and DNS names inside of the kubernetes network, stable storage, and pod name label,
deployment and scaling guarantees like deploy and termination order.

####[[⬆]](#toc) <a name='Service Mesh'>Service Mesh Questions:</a>

####[[⬆]](#toc) <a name='demo'>Demo Time:</a>

* Unpack test.tar.gz without man pages or google.
  - tar xf test.tar.gz

* Remove all ".pyc" files from testdir recursively?
  - find testdir -name '.pyc' -delete

* Search for "my konfu is the best" in all .py files.
  - grep 'string' .py

* Replace the occurrence of "my konfu is the best" with "I'm a linux jedi master" in all *.txt files.
  - find . -name '*.txt' | xargs sed -i 's/test/teste/g'

* Test if port 443 on a machine with IP address X.X.X.X is reachable.
  - telnet x.x.x.x 443

* Get http://myinternal.webserver.local/test.html via telnet.
  - wget

* How to send an email without a mail client, just on the command line?
  - using telnet

* Write a ```get_prim``` method in python/perl/bash/pseudo.
* Find all files which have been accessed within the last 30 days.
  - find . -atime +30

* Explain the following command ```(date ; ps -ef | awk '{print $1}' | sort | uniq | wc -l ) >> Activity.log```
 - date; ps -ef  will get the actual date and all process that the user who runs the command can access
 - awk '{ print $1}' will filter the first collunm before space
 - sort  will sort, first numbers than characters
 - uniq will merge equal entries
 - wc -l will count the amount of lines and print the number
 - >> Activity.log will save this command appending in the file Activity.log

* Write a script to list all the differences between two directories.

* In a log file with contents as ```<TIME> : [MESSAGE] : [ERROR_NO] - Human readable text``` display summary/count of specific error numbers that occurred every hour or a specific hour.

 - cat log.log | grep $HOUR | uniq -c


####[[⬆]](#toc) <a name='references'>Other Great References:</a>

Some questions are 'borrowed' from other great references like:

* https://github.com/darcyclarke/Front-end-Developer-Interview-Questions
* https://github.com/kylejohnson/linux-sysadmin-interview-questions/blob/master/test.md
* http://slideshare.net/kavyasri790693/linux-admin-interview-questions
