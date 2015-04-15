# Breaking Down Your Command Line Interface

I'm consolidating some/all of the commands I use when working in the CLI. I'll try to keep this somewhat organized in sections so feel free to browse through the table of contents. I'm working on organization and formatting, if it seems too messy for you to look at come back at a later time. Or do your own research!

##### I. Navigating Your CLI
##### II. Secure Copy Files
##### III. What is YUM And How To Install Things
##### IV. Zipping and Unzipping
##### V. Backing Up Your Data

### Navigating Your CLI
Before doing anything inside your Command Line Interface you should know how to navigate between folders in your terminal. Move between folders, copy paste, remove, and the like. Here are some of the more common commands I use commandes:	

* ls - This will list all of the files and folders in your current directory
* ll - This will list all the files and folders in your current directory as well as the groups and users that own those files
* pwd - print working directory. typing this command will give your the directory you are currently in along with all the folders above your current view 
* cd (target)- change directory. Your main command to moving between folders
* cd - you can also just type cd by itself and it will lead you to your home directory
* .. - will bring you up one folder

```
Examples:

cd opt/apps/middleware
(you are now in the middleware folder)

cd ..
(you are now in the apps folder)

cd 
(you are now in your home folder)
```
* cp - copy. Use this command to "copy" or "rename" a file/folder 
* mv - move. Use this command to move a file/folder
* mkdir (new folder name)- make directory. Makes a new folder
* touch (new file name)- Makes a new file

```
Examples: 

cd opt/apps/middleware
(remember this? Now you're back in the middleware folder)

mkdir bottomwear
ls
(using ls you should see a new folder called "bottomwear")

cd bottomwear
touch pants.html
ls
(using ls you should see an html file called "pants.html")

cp pants.html ../..
(now your pants.html is copied two folders up in "apps")

mv pants.html bottoms.html
(your pants.html stayed in the bottomwear folder but is not named "bottoms.html")

```

* rm (filename)- remove. Deletes a file
* rmdir (folder name)- remove directory. Deletes an EMPTY directory
* rm -rf (file/folder name)- remove force - Deletes anything listed even if it is not empty. DO NOT TYPE "rm -rf" BY ITSELF. YOU WILL DELETE EVERYTHING AND HAVE AN AWFUL TIME.
* find (where to look) (type to look for) (what to look for) - Finding a file or folder

```
Example:
find / -name server.js
(this will return all the "pwd"s of any location with a file name "server.js")
```

### Secure Copy FilesYou've seen the "cp" command up top, but what if you want to send something up to a server without going through a third party. An example would be sending a JSON file containing API keys up to your Digital Ocean box without going through Github. Why? Because you DO NOT want your API keys up there viewable by others. 
```
scp [options] (source where the file is) (target destination)

(The "options" is optional, for instance if you want to use a pem file key your command may look similar to the example below)

scp -i Desktop/pemkey opt/apps/Middleware 127.0.0.1:/tmp
(secure copy / use identity file / pemkey file / source directory / target directory)

(You can also copy whole folders, but you will need an option to make sure the process runs and copies all the files in the folder)

scp -i Desktop/pemkey opt/apps/Middleware -r 127.0.0.1:/tmp
(The only difference here is the "-r" which means to recursively copy all the files)```### Zipping and Unzipping
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

* ps aux | grep name
* find / -name searchingfor
* tar cvfz backupOfMiddleware.tgz Middleware/
* To restore the Middleware if deployment installations go wrong
* rm –rf the middleware folder
* tar xvf backupFileName –C target directory### Environmental Variables and Shortcuts
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