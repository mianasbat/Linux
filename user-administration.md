# User Administration in Linux

1. To view user information
   ```
   id
   # To view user id , username, group id and other groups for user tom
   id tom
   ```
1. To view the groups of user
   ```
   groups
   # To view primary and secondary groups of user tom
   groups tom
   ```
1. To view users on the system
   ```
   /etc/passwd
   # To view users
   cat /etc/passwd
   ```
1. To view users and encrypted passwords of users
   ```
   /etc/shadow
   # To view info in shadow file
   cat /etc/shadow
   ```
1. To view all the groups
   ```
   /etc/groups
   # To see all throups and ids
   cat /etc/group
   ```
1. To create a user
   ```
   useradd
   # To create a user tom with home directory /home/tom
   useradd -d /home/tom tom
   ```
1. To modify a user
   ```
   usermod
   # To modify a user home directory
   usermod -d /home/tommy tom
   # To check the changes
   cat /etc/passwd | grep tom
   # To give tom root permissions
   usermod -aG wheel tom
   # To check the changes
   id tom
   ```
1. To change the password of a user
   ```
   passwd
   # For assigning or changing tom password
   passwd tom
   # To confirm new password
   cat /etc/shadow | grep tom
   ```
1. To check password expiry information
   ```
   chage
   # To find details of tom username
   chage -l tom
   # To set the expiry days
   chage -M 30 tom
   # To check the change
   chage -l tom
   # To expire the account on specific date
   chage -E 2021-11-30
   # To check the change
   chage -l tom

   ```
1. To create a groups
   ```
   groupadd 
   # To create two groups
   group add test
   group add test2
   # To make test primary and test2 secondary group of tom
   usermod -g test -aG test2 tom
   # To check the changes
   groups tom
   id tom
   ```
1. To change the name of the group
   ```
   groupmod
   # To change group test to test0
   groupmod -n test0 test
   # To check the changes
   id tom
   ```
1. How to add user to sudoers groups
   ```
   /etc/sudoers

   # To add users to the sudoers group
   visudo
   # Now go down and add the line `#includedir /etc/sudoers.d` section
   tom  ALL=(ALL)   NOPASSWD: ALL
   # Now run a command as sudo
   sudo systemctl status httpd 
   ```
   
