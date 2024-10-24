# Linux Reference

## Help
`man {command}` - man page file of {command}\
`whatis {command}` - return short description of {command}\
`apropos {keyword}` - search the man page files for {keyword}

## File Commands
`ls` - directory listing\
`ls -la` - formatted detailed long listing with date, size, permissions, and hidden files\
`cd` - change directory to home\
`cd {dir}` - change directory to {dir}\
`pwd` - show current/present working directory\
`mkdir {dir}` - create a directory {dir}\
`rm {file}` - delete {file}\
`rm -r {dir}` - delete directory {dir}\
`rm -f {file}` - force remove {file}\
`rm -rf {dir}` - force remove directory {dir}\
`cp {file1} {file2}` - copy {file1} to {file2}\
`cp -r {dir1} {dir2}` - copy {dir1} to {dir2}; create {dir2} if it does not exist\
`mv {file1} {file2}` -  move or rename {file1} to {file2}; if {file2} is an existing directory, moves {file1} into directory {file2}\
`ln -s {file} {link}` - create symbolic link {link} to {file}\
`touch {file}` - create or update {file}\
`cat > {file}` - create {file} and places standard input into {file}\
`more {file}` - output the contents of {file}\
`head {file}` - output the first 10 lines of {file}\
`head -n {#} {file}` - output the first {#} lines of {file}\
`tail {file}` - output the last 10 lines of {file}\
`tail -n {#} {file}` - output the last {#} lines of {file}

## Process Management
`exec bash` - replace the current shell process with a new instance of bash. for other shells, you can use `exec $SHELL`.\
`ps` - display currently active processes\
`top` - display all running processes\
`jobs` - display status of jobs and job_id\
`kill {pid}` - kill process with id {pid}\
`pkill {proc}` - kill process with name {proc}\
`killall {proc}` - kill all processes with names beginning with {proc}\
`bg` - lists stopped or background jobs; resume a stopped job in the background\
`fg` - brings the most recent job to foreground\
`fg {job_id}` - brings job {job_id} to the foreground

## File Permissions
`chmod {octal} {file}` - change the permissions of file to octal, which can be found separately for user (owner), group, and others (world) by adding:

`4` - read (`r`)\
`2` - write (`w`)\
`1` - execute (`x`)

Symbolic Classes:

`u` - user (owner)\
`g` - group\
`o` - others (world)\
`a` - all

Examples:\
`chmod 777 {file}` - read, write, execute for all\
`chmod 754 {file}` - rwx for user, rx for group, r for others\
`chmod u+r,g+x {file}` - add read to user, add execute to group\
`chmod u+a,g-x {file}` - add all permissions to user, remove execute from group\
`chmod a-x {file}` - remove execute from all\
`chmod g=u {file}` - copies user permissions to group

## SSH
`ssh {user}@{host}` - connect to {host} as {user}\
`ssh -p {port} {user}@{host}` - connect to host on port {port} as user\
`ssh-copy-id {user}@{host}` - add your key to host for user to enable a keyed or passwordless login

## Searching
`grep {pattern} {files}` - search for {pattern} in {files}\
`grep -r {pattern} {dir}` - search recursively for {pattern} in {dir}\
`{command} | grep {pattern}` - search for {pattern} in the output of {command}\
`locate {file}` - find all instances of {file}

## System Info
`date` - show the current date and time\
`cal` - show this month's calendar\
`uptime` - show current time, uptime, number of users logged in, system load.\
`w` - display who is online\
`whoami` - who you are logged in as\
`finger {user}` - display information about {user}\
`uname -r` - show kernel version\
`uname -a` - show kernel information\
`cat /proc/cpuinfo` - CPU information\
`cat /proc/meminfo` - RAM information\
`free -h` - memory utilization in readable form\
`df` - show disk usage\
`du` - show directory space usage\
`whereis {app}` - show possible locations of {app}\
`which {app}` -  show which {app} will be run by default

## Compression
`tar cvf {file.tar} {files}` - create a tar named {file.tar} containing {files}. (cvf = create, verbose, file).\
`tar tvf {file.tar}` - list all files in {file.tar}. (tvf = table of contents, verbose, file).\
`tar xvf {file.tar}` - extract the files from {file.tar}. (xvf = extract, verbose, file).

`gzip {file}.tar` - compress a tar gzip -> {file}.tar.gz\
`gunzip {file}.tar.gz` - extract a tar with gzip\
`bzip2 {file}.tar` - compress a tar with bzip2 -> {file}.tar.bz2\
`bunzip {file}.tar.bz2` - extract a tar with bzip2

In One Command:

`tar cvzf {file.tar.gz} {files}` - create a tar compressed with gzip. (cvzf = create, verbose, gzip, file).\
`tar xvzf {file.tar.gz}` - extract a tar with gzip. (xvzf = extract, verbose, gzip, file).

`tar cvjf {file.tar.bz2} {files}` - create a tar compressed with bzip2. (cvjf = create, verbose, bzip2, file).\
`tar xvjf {file.tar.bz2}` - extract a tar with bzip2. (xvjf = extract, verbose, bzip2, file).

## Network
`ping {host}` - ping {host} and output results\
`whois {domain}` - get whois information for {domain}\
`whois -h {whois server} {domain}` - get whois information for {domain}\
`host -a {domain}` - get DNS information for {domain}\
`dig {domain} ANY` - get DNS information for {domain}\
`dig -x {host}` - reverse lookup {host}\
`wget {file}` - download {file}\
`wget -c {file}` - continue a stopped download

## Shortcuts
`Ctrl+C` - halts the current command\
`Ctrl+Z` - stops the current command, resume with `fg` in the foreground or `bg` in the background\
`Ctrl+D` - log out of current session, similar to `exit`\
`Ctrl+W` - erases one word in the current line\
`Ctrl+U` - erases the entire line\
`Ctrl+R` - type to bring up a recent command\
`!!` - repeats the last command\
`exit` - log out of current session

## Package Management

### Debian / Ubuntu
`apt update` - update list of available packages\
`apt upgrade` - upgrade the system by installing/upgrading packages\
`apt install {pkg}` - install {pkg}\
`apt remove {pkg}` - uninstall {pkg}\
`apt autoremove` - remove obsolete packages\
`apt search` - search in package descriptions\
`apt show` - show package details\
`dpkg -i pkg.deb` - install file pkg.deb (try to use apt install instead)\
`apt-get install -f` - fix broken dependencies (try to use apt install instead, which automatically installs dependencies)\
`/etc/apt/sources.list` (file) - APT repository list

### RHEL / Fedora / CentOS
`dnf check-update` - check for updates\
`dnf upgrade` - upgrades all packages installed\
`dnf install {pkg}` - install {pkg}\
`dnf remove {pkg}` - uninstall {pkg}\
`dnf reinstall {pkg}` - removes and reinstalls {pkg}\
`dnf search {search-pattern}` - search list of package names and descriptions\
`dnf provides {pkg}` - list all dependencies\
`dnf info {pkg}` - show package details\
`dnf repolist` - DNF repository list\
`/etc/yum.repos.d/` (file) - DNF respository list

#### RHEL / Fedora / CentOS Kernel Management
`rpm -q kernel` - check installed kernels\
`dnf install yum-utils` - install yum-utils\
`package-cleanup --oldkernels --count=2` - package-cleanup set count as how many old kernels you want left\
`installonly_limit=2` (option) - edit /etc/yum.conf or /etc/dnf/dnf.conf and set option

### SUSE / openSUSE
`zypper refresh` - or zypper ref. refresh repositories\
`zypper patch` - upgrades all packages installed\
`zypper patch-check` - check packages that need to be upgraded\
`zypper dist-upgrade` - for TUMBLEWEED. upgrades all packages by upgrading the entire distribution\
`zypper update` - or zypper up. for LEAP. updates all installed packages (if a repository contains only new packages, but does not provide patches)\
`zypper list-updates` - list of all new installable packages\
`zypper install {pkg}` - install {pkg}\
`zypper remove {pkg}` - uninstall {pkg}\
`zypper rm {pkg} --clean-deps` - clean up dependencies of removed packages\
`zypper ar {repository location} {name of repository}` - add repository
