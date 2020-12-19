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
   # To show human readable size of items
   ls -lh
   # To show item sorted by time, oldest at the bottom.
   ls -lt ~/Desktop
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
   # To remove directory with contents
   rm -r /test
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
   # To show the contents of text file apple.txt
   cat apple.txt
   # To print the line numbers on each line
   cat -n apple.txt
   # to view the contents of zip file
   zcat file.txt.gz
   ```
1. To show the contents of text file in reverse.
   ```
   tac
   # To show the contents of text file apple.txt in reverse
   tac apple.txt
   ```
1. To copy files/folders
   ```
   cp 
   # To copy the file
   cp existingfile.txt newplace.txt 
   # To copy directories and files
   cp -R dir1 dir2
   # To copy and check status
   cp -Rv dir1 dir2
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
   rm file.txt
   # To remove a directory
   rm -r dir1
   # To remove a directory by force
   rm -rf dir1
   # To securely delete a file. Overwrite contents before delete
   rm -P file.txt
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
   head file.txt
   # To view the first 12 lines
   head -12 file.txt
   ```
1. To see the last ten lines of a file
   ```
   tail 
   # To view the last 10 lines
   tail file.txt
   # To view the last 15 lines
   tail -15 file.txt
   ```
1. To see the contents of a file
   ```
   less or more
   # To see one screen of output at a time
   less apple.txt
   # To enable horizontal scrolling 
   less -S apple.txt
   # To see one screen a zip file
   zless apple.txt.gz 
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
   history -c
   ```
1. To clear the screen
   ```
   clear
   # To clear the screen/terminal
   clear
   ```
1. 
   ```
   logout or exit
   ```
1. 
   ```
   sudo
   ```
1. 
   ```
   su
   ```
1. To count the words of a file
   ```
   wc
   ```
1. To sort a list 
   ```
   sort
   ```
1.  
   ```
   ssh
   ```
1. 
   ```
   ssh-keygen
   ```
1. 
   ```
   scp
   ```
1. 
   ```
   rsync
   ```
1. 
   ```
   source, export
   ```
1. To create link or shortcut
   ```
   ln
   ```
1. To make the computer sleep
   ```
   sleep
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




## References:
1. https://www.oliverelliott.org/article/computing/ref_unix/


