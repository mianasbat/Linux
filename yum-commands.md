# Common yum commands

1. To get help on yum
   ```
   yum help
   ```
1. To list available packages
   ```
   yum list available
   ```
1. To list installed packages
   ```
   yum list installed
   ```
1. To list installed and available packages
   ```
   yum list all
   ```
1. To list information about a package
   ```
   yum info vsftpd
   ```
1. To list dependancies of a package
   ```
   yum deplist vsftpd
   ```
1. To show what package provide the file/app
   ```
   yum provides "top"
   ```
1. To search name and desciption of a package
   ```
   yum search samba
   ```
1. To get information of available update, e.g for security.
   ```
   yum updateinfo security
   ```
1. To check available group list
   ```
   yum grouplist
   ```
1. To list contents of a packagegroup
   ```
   yum groupinfo "Web Server"
   ```
1. To display enabled software repos
   ```
   yum repolist
   ```
1. To display info of specific repo
   ```
   yum repoinfo rhel-7-server-rpms
   ```
1. To display packages of particular repository
   ```
   yum repo-pkgs my-rpms list
   ```
1. To install all packages from my-rpms list
   ```
   yum repo-pkgs my-rpms install
   ```
1. To remove all packages from my-rpms list
   ```
   yum repo-pkgs my-rpms remove
   ```
1. To download yum repository data to cache
   ```
   yum makecache
   ```
1. To check for issues in yum
   ```
   yum check
   ```
1. To list all yum installs, updates and erase
   ```
   yum history list
   ```
1. To show details of yum transaction 3
   ```
   yum history info 3
   ```
1. To undo an action from yum history
   ```
   yum history undo 3
   ```
1. To redo the undone from yum history
   ```
   yum history redo 3
   ```
1. To clear out cached package data
   ```
   yum clean packages
   ```
1. To clean out all packages and metadata
   ```
   yum clean all
   ```
1. To install a package
   ```
   yum install vsftpd
   ```
1. To update all packages
   ```
   yum update
   ```
1. To update only httpd packages
   ```
   yum update httpd
   ```
1. To apply security related package updates
   ```
   yum update --security
   ```
1. To update one or all packages to a particular update
   ```
   yum update-to 
   ```
1. To update packages taking obsolete into account
   ```
   yum upgrade
   ```
1. To install a package from local drive
   ```
   yum localinstall abc-1-1.i686.rpm
   ```
1. To install a package from ftp site
   ```
   yum localinstall http://myrepo/abc-1-1.i686.rpm
   ```
1. To downgrade a package to an earlier version
   ```
   yum downgrade package-name
   ```
1. To reinstall the current version of software
   ```
   yum reinstall package-name
   ```
1. To remove one package and install another
   ```
   yum swap ftp lftp
   ```
1. To remove a package
   ```
   yum remove vsftpd
   or
   yum erase vsftpd
   ```
1. To remove a package and related unneeded packages
   ```
   yum autoremove httpd
   ```
1. To install a group of related packages
   ```
   yum groupinstall "web server"
   ```

Reference: 
1. https://access.redhat.com/sites/default/files/attachments/rh_yum_cheatsheet_1214_jcs_print-1.pdf

