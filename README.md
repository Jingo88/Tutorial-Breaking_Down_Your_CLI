# Useful Commands for your Command Line

I'm consolidating some/all of the commands I use when working in the CLI. I'll try to keep this somewhat organized in sections so feel free to browse through the table of contents. I'm working on organization and formatting, if it seems too messy for you to look at come back at a later time. Or do your own research!

##### I. Navigating Directories In The CLI
##### II. What is YUM And How To Install Things
##### III.


* ps aux | grep name
* find / -name searchingfor
* tar cvfz backupOfMiddleware.tgz Middleware/
* To restore the Middleware if deployment installations go wrong
* rm –rf the middleware folder
* tar xvf backupFileName –C target directory### Zipping and Unzipping
* zip filename.zip targetdirectory/*
* zip filename.zip file1 file2 file3
* unzip filename.zip
* unzip filename.zip -d target/directory/path
* zip filename.zip file1 file2 file3
* sudo yum install unzip

### YUM Installs
You may be asking yourself "What is YUM?" That's a good question. You should google it. But incase you are too lazy I'll give you a short breakdown. 

YUM = Yellowdog Updater, Modified. It is a package manager for Linux operating systems. (Think of how you can npm install things when running node). YUM can install, delete, and update packages. Some examples are 

* yum install unzip
* yum install xclock
* yum update xauth### Backing up a directory
### Environmental Variables and Shortcuts
* env | sort
* export variable_name=what is this variable
* export HOME_PATH=/home/blah/asdf/boom
* cd $HOME_PATH
* ### Command Line Navigation
### Making Users
* mkuser
* password### Giving access and ownership

* chown
* chmod### Log file navigation