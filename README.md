------------------------------------
VI command
--------------------------

yy    		copy line
p  or P  	paste

dd 	or cc		delete line

R or r 	or X  or x 	replace a chacter

o 				insert new line 
A     curson EOL
k    cusor up
j		cursor down
h		move curson left 
l 		move cursor right

shift+zz  or esc :qw		save and exit
esc :q			exist without save

esc /stringtofind

set command also
--------------------------------------------------------------------------------------------------------

/dev

"Dev" is short for "devices." This directory contains mostly special files that represent the physical hardware on the system. When you see "dev" think "devices."

/bin

"Bin" is short for "binaries" which is just a fancy word for executable files. Files in here can be run from a shell. When you see "bin" think "binaries."

/etc

"Etc" is kind of a strange one. It used to literally mean "et cetera," and was where everything that didn't belong everywhere else went. Now it has a new meaning, and contains low-level system utilities and low-level configuration files. When you see "etc" remember that it's the weird one with low-level configurations.

/boot

"Boot" contains files used during boot. Yeah.

/lib

"Lib" contains shared libraries used by executable files. When you see "lib" just think "Libraries."

/home

"Home" is where a user's files are stored, be it documents, settings, desktop, downloads, etc. When you see "home" just remember that home is where the heart is, given that heart = documents, settings, and important things.

/media

"Media" is commonly used by the system as a place to mount attachable storage (Flash drives, CDs, DVDs, etc). When you see "media" think of attachable media.

/mnt

"Mnt" is a directory used for mounting file systems, especially block devices stored within a filesystem. When you see "mnt" think "Mount."

/opt

"Opt" is a special place for application-installers to install their software when they don't want to use other places. The purpose of this directory isn't quite clear to me. Although I've seen several applications use it, most just install in other directories. I'm not sure what "opt" stands for, but I always think "Optional Software."

/proc

"Proc" is a special directory not made for mere mortals to understand. It represents currently running processes in memory as files, and understanding what's actually contained in here is beyond what I know. When you see "proc" think "Processes."

/root

"Root" is a directory used to store the root user's home directory. Very mysterious. You will rarely need to interact with this directory. Just remember that "root" stores root's documents and settings.

/sbin

"SBin" is just like "bin" except used for special executables for the system. When you see "sbin" think of "System Binaries."

/tmp

"Tmp" is for temporary storage for applications such as web browsers. When you see "tmp" think or "Temporary."

/usr

"Usr" is a directory used for user-installed software. Instead of installing libraries to "/bin" and "/lib," package managers will usually install to "/usr/bin" and "/usr/lib" instead. When you see "usr" think "User installed software."

Note that some distributions are now making "/usr/bin" and "/usr/lib" synonymous to the equivalent "/bin" and "/lib" directories to eliminate confusion and simplify the way software is installed on the system.

/var

"Var" is for "variable" files, or files which can rapidly change on the system while processes are running. When you see "var" think "Variable files."
-----------------------------------------------------------------------------------------------------------

Mounting is a process by which the operating system makes files and directories on a storage device (such as hard drive, CD-ROM, or network share) available for users to access via the computer's file system.[1]

In general, the process of mounting comprises operating system acquiring access to the storage medium; recognizing, reading, processing file system structure and metadata on it; before registering them to the virtual file system (VFS) component.

Good software design has high cohesion and low coupling.Cohesion refers to what the class (or module) can do.
As for coupling, it refers to how related or dependent two classes/modules are toward each other. 
Cohesion (Co-hesion) : Co which means together, hesion which means to stick. The System of sticking together of particles of different substances.Low coupling often correlates with high cohesion, and vice versa.
What is the difference between replication, partitioning, clustering, and sharding?
Replication: The strategy of duplicating data across more than one node. There are many varieties, simplest being Master-Slave(s) or Leader-Follower and can either be synchronous or asynchronous.
From a database perspective, clustering is when you have a group of machines (nodes) hosting the same database schema on the same database software with some form of data exchange between these machines. From outside of the cluster, these machines are seen as a single unit containing a union of the data that is spread across the nodes in the cluster. When your application accesses a cluster, the request is ultimately routed to a single node in the cluster for read or write operation.Replication is a form of clustering where all nodes in the cluster have the same/identical schema and data. This is useful in the following scenarios:

To have high availability of data. Even if a node goes down, the data is still available from other nodes in the cluster.
Separate nodes for write and read. Data is replicated from the write cluster to all read clusters. This ensures that under high transaction volumes, the read operations are not getting delayed by write operations and vice-versa.
Multiple nodes for read operations and for write operations. This ensures that the read and the write operations are load balanced across multiple nodes resulting in higher scalability and data throughput.
Sharding and Partitioning are essentially the same cluster topology. All nodes in the cluster have identical schema, however the data is divided across nodes such that each node has only a subset of the data. No two nodes will have the same data. Sharding has its use in the following scenarios:

Each database node has an upper limit to the amount of data it can store. This limited is usually due to hardware configuration. For example, a node that has a 4TB hard disk attached, can store up to a maximum of 4TB of data. If the total volume of data exceeds this limit, it has to be sharded.
Suppose your dataset has 500 million records (rows) for a given table. In a replicated setup, when you fire a query against this table, it is executed in a single node for all 500 million records. In a sharded setup, the query would be split-up across shards and executed. This would be faster since a. the amount of records to query in each shard would be much lesser than 500 million and b. the queries across shards will be executed in parallel.
Of course, sharding is a much more complex setup than clustering. Apart from database platform support it would also require effort in schema design for identifying/introducing a shard key that would be used to split/join data across the shards. The shard key must be chosen such that data is distributed equally across all shards, which may not be easy to determine under certain scenarios.

Also note that in the interest of high availability, it is a common practice to have each shard replicated across more than one node, thereby adding another level of complexity to the cluster topology.

----------------------------------------------------------------------------------------------

rm file(s) or directory(s)     rm filename1 filename2 filename3


cp -r source destination
35. cp <file1> <file2> : Used to copy files
36. cp -i <file1> <file2> : Enters interactive mode; CLI asks before overwriting files
37. cp -n <file1> <file2> : Does not overwrite the file
38. cp -u <file1> <file2> : Updates the destination file only when source file is different from destination file
39. cp –R <dir1> <dir2> : Used to copy directories
40. cp –v <file1> <file2> : verbose; prints informative messages


mv [option(s)] source destination     option are -i,-r,-b,-S
mv old_file new_file    rename
41. mv <file1> <file2> : Used to move and rename files
42. mv -i <file1> <file2> : Interactive mode; CLI asks before overwriting files
43. mv –u <file1> <file2> : updates the destination file only only when source file is different from destination file
44. mv -v <file1> <file2> : Verbose; prints source and destination files

How to see content of file in Unix(without able to edit)?
cat -b filename

cd ~username

cd -    goto last directory

rmdir dirname1 dirname2 dirname3

mkdir -p /tmp/amrood/test
mkdir directory(s)

chmod u-x testfile
chmod o+wx,u-x,g = rx testfile
chmod 755 testfile

chown nameofuser or uid filename

chgrp groupname or gid filename

passwd   to change password

grep [optons]pattern file(s) 

ls -l | grep "Aug" | sort +4n | more

ls -a : Lists all the hidden contents in the specified directory
ls *.<format> : Lists only the contents in the directory of a particular format


The simplest way to start a background process is to add an ampersand (&) at the end of the command.
$ls ch*.doc &

ps -f
65. ps -ux : Used to display the longlist of all the running processes
66. ps -aux : Used to display all the processes which run by all the users
67. ps -U <username> : Used to display the processes run by certain user

kill -9 pid
kill <pid>/kill –KILL <pid>/kill -9 <pid> : Used to kill the process

fg - bring a background job to the foreground

which <command> : Used to identify the location of executables

69. whatis <command> : Provides very brief description of command


ping hostname or ip-address

scp copies files between hosts on a network
scp -r -i file.pem user@192.10.10.10:/home/backup /home/user/Desktop/

--- To go in your home directory  $cd ~    Here ~ indicates the home directory
To go in your last directory  $cd -
$pwd

Assume we create a test.sh script. Note all the scripts would have the .sh extension. Before you add anything else to your script, you need to alert the system that a shell script is being started. This is done using the shebang construct. For example −

#!/bin/sh
This tells the system that the commands that follow are to be executed by the Bourne shell. It's called a shebang because the # symbol is called a hash, and the ! symbol is called a bang.

To create a script containing these commands, you put the shebang line first and then add the commands −

#!/bin/bash
pwd
ls


------------------------
In addition, we would need to remember several partigular sets of commands, such as:

apt-get (or yum or dnf or pacman ): handle packages
npm: to handle nodejs packages
composer: to handle php packages
pip: to handle python packages
gem: to handle ruby pakages
git and/or hg: to handle version control
docker: to handle docker resources
ssh: to work with remote server


--------------
man (manual page, e.g., man rm)

cd (change directory)

ls [-lrtdF] -> The most basic command used to list files and directories
ls (list contents of directory, see man ls for more options, e.g., ls -1, just print file names)

mv [-if] rename or move files or dir
mv (move/rename file or directory)


cp (to copy files)
clear (clears terminal window)

rm [-ifr]  remove files or dir
rm (remove file or directory)

echo (print something to stdout)
60. echo “string” : used to display the string
61. echo $<variable name> : Used to display the value assigned to variable

cat (print an entire file to stdout)

tail (see man tail for options, see the last 10 lines of a file by default), which is also useful for leaving a file-handle open and seeing as the file is modified, e.g., tail -f some_file <-- now you can watch as the file is modified

54. less (inspect a file page by page or line by line)
less <file> : Used to view the file on terminal (especially for big files)
( up/down arrow is used to go through the file line by line & tab is used to view The file page by page &
“g” is used to go to the beginning of the file & “G” is Used to go to the end of the file & /<string> is
used to search for the string in File from top to bottom & ?<string> is used to search from down to top) q to return

find (see man find, finds files and/or directories using a variety of methods, most commonly by name, e.g. find . -name "somepattern*.someext" -type f <-- finds files with that name pattern in the current directory and all accessible subdirectories)
93. find <path> -name <file> : Used to find the location of the file in a particular path

grep (see man grep, finds files that contain a string, also see man egrep for finding files that contain a regular expression)
24. grep <string> file : Returns results for matching string
25. grep -i <string> file : Returns results for case insensitive string
26. grep -n <string> file : Returns the matching string along with their line number
27. grep -v <string> file : Returns the result of lines not matching the string
28. grep -c <string> file : Returns the number of lines which matches the string

awk (cut a file by column, e.g., cat some_file | awk -F',' '{print $2}' <-- print the second column of a file delimited by commas)

sed (edit a file inline or output to stdout, e.g., sed -i "s/foo/bar/g" some_file <-- inline replace foo for bar anywhere in the file multiple times per line if necessary)

sort (see man sort for sorting options)

uniq (get a unique listing of elements, e.g., cat some_file | awk -F',' '{print $2}' | sort | uniq)

history (see recent bash history, also see ~/.bash_history)
15. How to see History of commands executed
history Using only "history" will give you all the commands executed in current session.
If you want to see specific type of command,use grep along with history as below :
history | grep mk

view (read-only vim)

ln (to create links to files)

chmod (change permissions, see Linux and Unix chmod command help and examples)

chown (change user and group ownership)

chgrp (change just group ownership)

top (for monitoring processes)
62. top : Used to display all the processes running in your system (“s” flag is used to change the refreshing time & “i” is used to display only the Running processes & “k” is used to kill the processes(by pid))

ps (see man ps, lists running processes)

kill (see man kill, asks a program to exit, tells you if a program is running, or can force kill a program)

pwd (to view the present working directory)

locate (to locate files)

scp (to copy files to a remote server)

rsync (to sync remote servers)

rpm (for managing packages in Red Hat Enterprise Linux)

gzip [-d]  compress/decompress ascii files

gunzip  similar to gzip -d

id [-a]  information about current user and its groups

df [-h]  disk free space
81. df : Used to get the full summary of available and used disk space usage of the file system on linux system
82. df -h : same as df ;but displays in human readable way

date [-su]  current date

du [-s]  disk used
83. du : Used to display the amount of space used by certain folder/directory
84. du -h : Same as du;but in human readable format
85. du -sh : Same as du ; but in a simple format as a summary

tar [-cxfv]  archiving multiple files and folder

top  list top 10 processes consuming memory

diff  display difference between two files

comm : compare files

touch 'filename.ext' : update file access time or create new file

wget (or curl) : download file to disk

1. Editing your ~/.bash_profile and/or ~/.bash_rc to ensure certain variables are set

2. clear : Used to clear the terminal

3. cd <path> : Used to change the current working directory

4. cd : Changes the directory to the home directory

5. cd ~ : Changes the directory to the home directory

6. cd / : Changes the directory to the root directory

7. cd .. : Changes the directory to it’s parent directory

8. cd ‘folder name’ : Used to change the directory when there is a space in the directory name

57. sudo : Executes only that command with root/super user privileges

58. su <username> : Used to switch to a different user

59. su/sudo -s : Used to switch to root user

70. sudo useradd <username> -m : Used to add a new user along with new home directory(-m)

71. sudo passwd <username> : Used to set a password for the user

72. sudo userdel <username> : Used to delete the user

73. sudo userdel -r <username> : Used to delete the user and user home directory

74. sudo rm –r /home/<usrname>/	: Used to delete the home directory of the user

75. groups : Used to show the groups in which the current user is connected to

76. cat /etc/group/ : Used to show all the groups in the system

77. sudo groupadd <groupname> : Used to add a group

78. sudo groupdel <groupname> : Used to delete a group

79. sudo gpasswd -a <username> <groupname> : Used to add the user to a particular group

80. sudo gpasswd -d <username> <groupname> : Used to remove the user from a particular group

86. free -h : Gives information about total used and available space of physical memory and swap memory with buffers used by kernel (‘-k’ flag for kilobytes, ‘- m’ flag for megabytes, ‘-g’ flag for gigabytes)

87. watch <command> : Used to run the command repeatedly at regular intervals

88. watch -n <time(s)> <command> : Same as watch and to set the time interval

94. wc <file> : Used to display the number of lines, words and characters the file has

95. wc -l <file> : Used to display the number of lines only(‘-w’ flag for no.of words and ‘-c’ flag for no.of characters)

100. sudo date -s “01 jan 2050 12:00:00” : Used to set the date and time in system

ifconfig : to check ip address

19. How to copy File from one host to another in Unix?
When you are sending files from current machine to remote machine
scp <current machine path to file,which we want to send to remote machine> user@remote machine:/remote path
Example : scp /var/log/was/abc.txt GA99@test.com:/var/log/remoteDirectory
When you want to retrieve file(s) from remote machine
scp user@remote machine:/remote path to file <current machine path where we want to download the file>
Example : scp user@remote machine:/var/log/remoteDirectory/abc.txt /var/log/was

22. How to find all the files with certain content in Unix?
find . –name <type of files to be searched> | xargs grep <content to be matched>
Example : find . -name "*.txt" | xargs grep "Hi"

21. How to execute previously executed command i nUnix ?
!<Previous Command>
This is really handy when your command includes lots of parameters and options.You need not type all those parameters and options again with this shorthand.
Example : Say I executed following command: ls -lrt | grep abc
Now I want to execute this command again,I just have to type following to execute above command again :
!ls

23. How to find file(s) which have been modified since last day,today or more than 1 day
23.1)Find all files in current directory and sub directories which has been modified exactly 1 day back.
find . -mtime 1
23.2) Find all files in current directory and sub directories which has been modified more than 1 day before
find . -mtime +1
23.3) Find all files in current directory and sub directories which has been modified less than 1 day before.
find . -mtime -1

11. How to see List of all background process? Jobs
5. How to find a File/Directory with name starting with particular character in Unix?
ls -ltr | grep <character>*
Example : Find file/directory starting with name "ab"
ls -lrt | grep ab*

6. How to give/change permissions of File or Directory.?
File permissions in numeric format and their meaning :
0 – no permissions
 1 – execute only
 2 – write only
 3 – write and execute
 4 – read only
 5 – read and execute
 6 – read and write
 7 – read, write and execute
By default,when we create a File in Unix ,it is created with permission 666(read/write).
By default,when we create a Directory in Unix,it is created with permission 777(read/write/execute).
Along with numeric notation,Unix permissions can also be represented by following characters:
Reference Class Description
u user the owner of the file
g group users who are members of the file's group
o others users who are not the owner of the file or members of the group
a all all three of the above, is the same as ugo
r read read a file or list a directory's contents
w write write to a file or directory
x execute execute a file
6.1. How to make File read only in Unix
 chmod <permission> <fileName>
 Example : chmod 400 abc.txt
6.2. How to give File Read/Write Permissions in Unix
chmod <Permission> <FileName>
Example : chmod 777 abc.txt
7. How to find list of all the links in a directory in Unix?
ls -lrt | grep "^l"

^  This signifies start of each line
l  Each symbolic link has "1'' in the beginning of line like below :
lrwxrwxrwx 1 gg99a weblog 3 Dec 9 22:20 latest -> 1.3
So this command prints all lines from result of ls -lrt,which starts with "l" and all symolic link's lines start with "l",hence the result.

::::::::::::::::::::Hands on Example:::::::::::::::::::
I’ll describe a common scenario of the following task - you are sitting at a Linux computer and you need to add a little RESTful service to a remote server. How do you do it?

First you need to connect to the remote server with ssh with this command:

ssh user@host

where user is your username on the remote server and “host” is it’s hostname or IP address.

At this point it’s worth noting that it’s useful to add the hosts that you’r working on to /etc/hosts so that you can connect to them using names that are meaningful to you.

So the first command in our journey is ssh. To see more options of using ssh run:

man ssh

Which makes man the second basic command on our list, a very important one.

Now you’re at a remote host and you want to install Node.js (it’s just an example - it could be Ruby, Python, Perl, Lua, Go or any other language). So you make a new directory with mkdir:

mkdir node-src

You then enter that directory with cd:

cd node-src

Then you download the Node source with either wget or curl:

wget https://nodejs.org/dist/v4.4.6/n...

curl -O https://nodejs.org/dist/v4.4.6/node-v4.4.6.tar.gz

To see if we have it there we can use the ls command with options a (to list all files), l (for a long listing) and p (to show slashes at the end of directories) like this:

ls -alp

Now you extract the archive with tar:

tar xzvf node-v4.4.6.tar.gz

You go into the extracted directory with cd again:

cd node-v4.4.6

Now you configure the source tree for installation:

./configure --prefix=/opt/node-v4.4.6

Note the “./” (dot slash) at the beginning - it means to run a script in the current directory. The configure script has more options that you can read about using the --help switch:

./configure --help

Now you are ready to build and test the source using make and make test but we also want to make sure that we start testing only if the building succeeds and then print OK if everything went well or ERROR if there was some error, for which we will use the echo command and two useful shell operators: && and || (two ampersands and two vertical bars)

make && make test && echo OK || echo ERROR

Now it’s time to make a coffee. :) It will take a while to complete.

If we see “OK” then we can install Node into our destination using make install but to install it where we want it we need administrator priviledges.

We can see what user we are logged in as using the whoami command:

whoami

If it is not “root” then we need to obtain administrative priviledges using the sudo command prepended to make install:

sudo make install

If we were already “root” then we wouldn’t need sudo.

At this point we can run Node using:

/opt/node-v4.4.6/bin/node

But we want to have it in:

/opt/node/bin/node

So we need to make a symbolic link using the ln command:

sudo ln -svf /opt/node-v4.4.6 /opt/node

And now we have /opt/node pointing to /opt/node-v4.4.6 as we wanted.

Still we don’t want to have to write the full path every time, we want to be able to run just:

node

For that we need to modify the PATH environment variable using the = operator:

PATH=”/opt/node/bin:$PATH”

using the string interpolation with dollar sign to append the old contents of PATH at the end.

To make the new PATH available to subprocesses we use the export command:

export PATH

Or both operations in one line:

export PATH=”/opt/node/bin:$PATH”

To have it always available when we log in in the future, we need to add that line to .bachrc or .profile in our home directory. To do that we need to run a text editor called vi that is available everywhere so we need to know its basic usage even if we prefer some other editor:

vi ~/.bashrc

The ~ (tilde) is our home directory, the same as the HOME environment variable. We could also use this as well:

vi $HOME/.bashrc

Now we go to a line after which we want to add our new PATH (e.g. the last line) and we press the letter “o” which is a vi command to insert a line after the one where the cursor is:

We write:

export PATH=”/opt/node/bin:$PATH”

And then we press Escape to go out of the insert mode into the command mode of vi again.

Then we press ZZ (two uppercase Z letters) or :wq and Enter to save the file and exit.

To make sure that we have the new PATH in .bashrc we can use grep:

grep PATH ~/.bashrc

To run our new .bashrc file we use the source command which has a shortcut of a single dot:

. ~/.bashrc

(note the space between the dot and tilde)

Now we can see if the PATH is correct using echo:

echo $PATH

If it contains /opt/node/bin we can test if the system can find the node binary somewhere in the PATH using the which command:

which node

We should see:

/opt/node/bin/node

If everything is fine we should be able to run:

node -v

To see the node version. We can write a onliner to see if everything works:

node -e 'console.log("Hello!");'

Writing oneliners is very useful. Those are commands but those are your commands. You can write them using perl, python, ruby or other languages that you may prefer.

Now that we have the node installed and working we can remove the source directory using rm with the following flags:

rm -rvf ~/node-src/node-v4.4.6

Now we can move the original tarball to some other place for backup using mv:

mv ~/node-src/*.tar.gz ~

The * means to move all files ending with “.tar.gz” into our home directory (tilde).

Now the ~/node-src directory should be empty so we can remove it with rmdir:

rmdir ~/node-src

Summary:

So we have used: ssh, ls, cd, mkdir, rmdir, mv, rm, make, vi, grep, whoami and few other commands just in such a simple task. Other command that will be needed are cp for copying files, cut, sed, awk for manipulating text streams etc. but here I wanted not to post a random list of commands but to show a real life example. I hope it will be useful to demonstrate the feel of a typical flow of working in the Linux command line.































