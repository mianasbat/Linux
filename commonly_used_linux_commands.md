# Linux Commands

1. To print working directory.
    ```
    pwd
    ```
1. To change directory
    ```
    cd 
    # To go to root directory
    cd /
    # To go to user's home directory
    cd
    # To got to user's home directory
    cd ~
    # To go to parent directory
    cd ..
    # To go to previous directory
    cd -
    ```
1. To list contents of the direcotry
   ```
   ls
   # To show contents long form
   ls -l
   # To show hidden contents of the directory
   ls -a
   # To seperate directories, files and binaries
   ls -F
   # To show human readable size of items
   ls -lh
   # To show item sorted by time, oldest at the bottom.
   ls -lt ~/Desktop
   # To show item sorted by time, newest at the bottom.
   ls -ltr ~/Desktop
   # To show all the text files
   ls *.txt
   ```
1. To make a directory
   ```
   mkdir
   # To make a directory test
   mkdir test
   # To make multiple directories in one go
   mkdir -p /test/subtest/subsubtest/subsubsubtest
   ```
1. To remove an empty directory
   ```
   rmdir

   # To remove empty test directory
   rmdir test
   # To remove directory with contents and verbose
   rm -rv /test
   ```
1. To spit text
   ```
   echo 

   # To print hello world
   echo "hello world"
   ```
1. To show contents of a text file
   ```
   cat
   # To show the contents of text file sampletext.txt
   cat sampletext.txt
   # To print the line numbers on each line
   cat -n sampletext.txt
   ```
1. To show the contents of text file in reverse.
   ```
   tac
   # To show the contents of text file sampletext.txt in reverse
   tac sampletext.txt
   ```
1. To copy files/folders
   ```
   cp 
   # To copy the file
   cp existingsampletext.txt newplace.txt 
   # To copy directories and files
   cp -r dir1 dir2
   # To copy and check status
   cp -rv dir1 dir2
   ```
1. To rename a file or directory
   ```
   mv 
   # To rename a file
   mv file1.txt file2.txt
   # To rename a directory
   mv dir1 dir2
   ```
1. To remove a file or directory
   ```
   rm
   # To remove a file
   rm sampletext.txt
   # To remove a directory
   rm -r dir1
   # To remove a directory by force
   rm -rf dir1
   # To securely delete a file. Overwrite contents before delete
   rm -P sampletext.txt
   ```
1. To see the manual of a command
   ```
   man
   # To see the manual of ls command
   man ls
   ```
1. To see the first ten lines of a file
   ```
   head
   # To view the first 10 lines
   head sampletext.txt
   # To view the first 12 lines
   head -12 sampletext.txt
   ```
1. To see the last ten lines of a file
   ```
   tail 
   # To view the last 10 lines
   tail sampletext.txt
   # To view the last 15 lines
   tail -15 sampletext.txt
   ```
1. To see the contents of a file
   ```
   less or more
   # To see one screen of output at a time
   less sampletext.txt
   # To enable horizontal scrolling 
   less -S sampletext.txt
   # To see one screen a zip file
   zless sampletext.txt.gz 
   ```
1. To find the location of application binary
   ```
   which
   # To see where is ls binary located
   which less
   # To see where is python binary located
   which python
   ```
1. To change permission of the file
   ```
   chmod
   # Make executable for you only
   chmod u+x myfile
   # Add read write execute permissions for the group
   chmod g+rxw myfile
   # Remove write execute permissions for the group
   # and for everyone else (excluding you, the user)
   chmod go-wx myfile
   # Remove all permissions for you, the group,
	# and the rest of the world
   chmod a-rwx myfile
   # Revoke all permissions (---------)
   chmod 000 myfile
   # Grant all permissions (rwxrwxrwx)
   chmod 777 myfile
   # Reserve write access for the user,
   # but grant all other permissions (rwxr-xr-x)
   chmod 755 myfile          
   ```
1. To change owner of the file
   ```
   chown
   # To change the owner of the file to ec2-user
   chown ec2-user myfile
   # To change the owner and group of a file
   chown someuser:somegroup myfile
   ```
1. To check the commands history
   ```
   history

   # To see the history commands
   history
   # To clear the history
   history -c; history -w
   # To rerun a command from the history
   !command_number
   # To rerun the last executed command
   !!
   ```
1. To clear the screen
   ```
   clear
   # To clear the screen/terminal
   clear
   ```
1. To logout or exit an environment.
   ```
   logout or exit
   ```
1. To run a command as a super user
   ```
   sudo
   # To create a directory in root /
   sudo mkdir /bkup
   # To become super user for some time
      sudo -i
      #check who are you now
      whoami
      # To become your own user
      exit
      # Now check again who are you
      whoami
   ```
1. To switch the user
   ```
   su
   # To become another user (john) for whome you know the password
   su john
   ```
1. To count the words, lines and characters of a file
   ```
   wc
   # To count the number of lines in a file
   wc -l sampletext.txt
   # To count the number of words in a file
   wc -w sampletext.txt
   # To count the number of characters in a file
   wc -c sampletext.txt
   # To count lines, words and characters
   wc -clw sampletext.txt
   
   ```
1. To sort files.  
   ```
   sort
   # To sort a file
   sort sampletext.txt
   # To sort numberically
   sort -n samplenumbers.txt
   # To sort uniquely
   sort -u sampletext.txt
   ```
1. To connect to a remote computer securely. It uses port 22.
   ```
   ssh
   # To connect to a remote computer
   ssh username@remote_computer.ucl.ac.uk
   # To enable X11 window system
   ssh -Y username@remote_computer.ucl.ac.uk
   # This command should not be empty
   echo $DISPLAY
   # Run xclock on remote computer and see it on your own monitor
   xclock
   # To run a command on remote computer without loggin in
   ssh -Y username@remote_computer.ucl.ac.uk "ls -ali"
   ```
1. To generate a public and private key for secure communication.
   ```
   ssh-keygen
   # The keys are usually created in ~/.ssh
   # Create .ssh directory if it doesnt exist
   mkdir -p ~/.ssh
   # Get into .ssh directory
   cd ~/.ssh
   # Now run the command to generate the keys `localkey` (private key) and `localkey.pub` (public key)   
   ssh-key-gen -t rsa -b 4096 -f localkey
   ```
1. To copy your public key to remote computer for keyless entry next time
   ```
   ssh-copy-id
   # To send public key to remote_computer
   ssh-copy-id -i username@remote_computer.ucl.ac.uk
   ```
1. If you have ssh connection to remote computer, you can use scp to transfer to/from remote computer.
   ```
   scp
   # To transfer data from remote computer to your computer. Run this command on local computer
   scp username@host:/some/path/on/remote/machine /some/path/on/my/machine
   # To transfer data to remote computer from your computer. Run this command on local computer
   scp /some/path/on/my/machine username@host:/some/path/on/remote/machine
   ```
1. If you have ssh connection to remote computer, you can use rsync to transfer to/from remote computer.
   ```
   rsync
   # To copy files from a remote computer to local computer
   rsync -chavP username@host:/some/path/on/remote/machine /some/path/on/my/machine/
   # To copy files from a local computer to remote computer
   rsync -chavP /some/path/on/my/machine username@host:/some/path/on/remote/machine/
   # It can also be used to sync two directories on your local machine
   rsync directory1 directory2
   ```
1. To list the contents of directory visually
   ```
   tree 
   # To list current directory contents
   tree .
   # To list /etc/ directory contents
   tree /etc
   # To add colour in output
   tree -C /etc
   # To show only directories
   tree -d /etc/
   ```
1. To export a variable and source to make the effect immidiately. 
   ```
   source, export
   # To export a variable with value 54
   export myvariable=54
   echo $myvariable
   # To make the changes effect take place immidiately.
   source ~/.bash_profile
   ```
1. To create link of file in another location
   ```
   ln
   # To create a soft link of file in current directory
   ln -s /path/to/target/file mylinkfile

   # To create a hard link
   ln /path/to/target/file mylinkfile
   ```
1. To take for specific time in seconds
   ```
   sleep
   # To pause for 5 second
   sleep 5
   ```
1. To check the size of directory or file
   ```
   du
   # To check the size of dir1
   du dir1
   # To read the sizes human friendly
   du -sh dir1
   # To check the sizes of everything in a directory
   du -sh *
   ```
1. To check the disk space and details
   ```
   df
   # To check how much space is used and left
   df
   # To make the sizes human readable
   df -h
   ```
1. To keep the connection active on ssh
   ```
   nohup
   # To keep a job running even if you close the window
   nohup python
   ```
1. To count the time of execution of a script/process
   ```
   time
   # To count how long a command took
   time sleep 5
   # To count how much copying took
   time cp apple.mov /home/username/
   ```
1. To get one or more columns from the delimited file
   ```
   cut
   # To get column 2 from the file, delimeter is space 
   cut -f2 -d" " sampletext.txt

   ```
1. For text manipulating
   ```
   awk
   # To print column 1 
   awk '{ print $1}' sampletext.txt
   ```
1. For text manipulating
   ```
   sed
   # To ignore first line of the column and show remaining.
   cat sampletext.txt | sed '1d'
   ```
1. To get current date and time
   ```
   date
   # To get only date time
   date
   # To get only the date part 
   date "+%y%m%d"
   ```
1. To get the calendar
   ```
   cal
   # To get the month calendar
   cal
   # To get for year
   cal -y
   # To get specific month
   cal 12 2021
   ```
1. To compress and uncompress a file
   ```
   tar
   # To compress a directory
   tar -cvf dir.tar dir
   # To compress and zip a directory
   tar -zcvf dir.tar.gz dir
   # To uncompress a directory
   tar -xvf dir.tar
   # To uncompress a zip and tar directory
   tar -zxvf dir.tar.gz
   ```
1. To find uniq lines in a file
   ```
   uniq
   # To find unique lines in a file
   uniq samplenumbers.txt
   ```
1. To get various system information.
   ```
   uname
   # To get operating system
   uname
   # To get all information
   uname -a
   ```
1. alias can map one word to another, usually used for shortcuts
   ```
   alias, unalias
   # To set shortcut for copy recursively
   alias cp="cp -R"
   # To set shortcut for mkdir
   alias mkdir="mkdir -p"
   # To get rid of an alias
   unalias cp
   ```
1. To find for files and directories in the computer
   ```
   find
   # To find makedev in /sbin
   find /sbin -name makedev
   # To find cases insensitive in the above command
   find /sbin -iname makedev
   # To find any files ending with v
   find /bin -name *v
   # To find files that are older than 10 days and newer than 15 days
   find . -mtime +10 -mtime -13
   # find and run ls command on it
   find . -name s* ls
   # find files that are 1MB or greater
   find . -size +1M G K
   # find everything in current directly and execute file on it
   find . -exec file{}\; 
   # To suppress warning in search
   find / -type file -name sampletext.txt 2>/dev/null
   ```
1. To create an empty file
   ```
   touch
   # To create a file sampletext.txt
   touch sampletext.txt
   ```
1. It is used to show differences between two files.
   ```
   diff 
   # To show differnce between two files
   diff file1.txt file2.txt
   ```
1. This command is used to show commonalities in files.
   ```
   comm
   # To show common between two files
   comm file1.txt file2.txt
   ```
1. To keep multiple sessions in ssh connection
   ```
   screen
   # To keep the process running in the background
   screen
      # Now to run a process
      ping google.com
      # Now to move it to background
      Ctrl + a
      d
      # Now close the window if you like and ssh again and type the command to connect to that command again
      screen -dr
   ```
1. How to split window into multiple
   ```
   tmux
   # To use tmux, you need to install it first
   yum install tmux -y
   # To start the session type command
   tmux
   # To split the screen into two vertically
   ctrl+b %
   # To split the screen horizontally
   ctrl+b "
   # To switch between windows.
   # Remember windows are numbers from left to right and top to bottom.
   press window number + o
   To finish 


   ```
1. To find your username
   ```
   whoami
   ```
1. To see what groups a user belong to
   ```
   groups
   # To see which groups the logged in user belong to
   groups
   ```
1. To see the logged in users on that computer.
   ```
   who, w
   # Just run the command to see who are logged in 
   who
   # Just run the command to see who are logged in 
   w
   ```
1. To find the host name of the computer
   ```
   hostname
   # To check the hostname of computer, run command
   hostname
   ```
1. To see information about the user.
   ```
   finger
   # To see information about the current user
   finger $(whoami)
   ```
1. To schedule any process.
   ```
   crontab
   # To run a process every week at 12 midnight
      # First start the crontab program
      crontab -i
      # Now add the line for the job to run
      0 0 * * * cp -R /home /backup
      # For setting schedule time visit the website
      [https://crontab.guru/](https://crontab.guru/)
   ```
1. To see the related commands
   ```
   apropos
   # To see related commands to grep
   apropos grep
   ```
1. To mount a file system
   ```
   mount
   # To mount a usb
   mount /dev/sda2 /mnt
   ```
1. To continously observe the situation
   ```
   watch
   # To watch the directory size when copying e.g.
   watch du -sh
   ```
1. To check the status of remote computer
   ```
   ping
   # To ping yahoo.com
   ping www.yahoo.com
   ```
1. To find the DNS name or IP address
   ```
   dig
   # To find the ip address of yahoo.com
   dig www.yahoo.com
   ```
1. To check the network card details and IP address
   ```
   ifconfig
   # To check the ip addresses of the system
   ifconfig | grep inet
   ```
1. To download file and check the code of webpage from commandline
   ```
   curl
   # To check the source code of a webpage 
   curl https://mianasbat.github.io/web/
   # To get header information
   curl -i https://mianasbat.github.io/web/
   # To download a file using curl
   curl -o file.jpg https://url-of-the-resource
   ```


## References:
1. [Ref 1](https://www.oliverelliott.org/article/computing/ref_unix/)
1. 


