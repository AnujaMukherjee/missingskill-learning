# Linux
## History of Linux
- Linux was invented in 1991  by Linus Torvalds. 
- Linux is a kernel it is the interaction between hardware and software
- Linux Licence is GNU(General public licence)/GPL

    -  Current version is 5 it is stable version

    - Long-Term Support (LTS) release is normally associated with an application or an operating system for which you will get security, maintenance and (sometimes) feature updates for a longer duration of time. ... But, you will get the necessary bug fixes and security fixes in the updates of a Long Term Support
- The history of Linux, is not less than a story. It began when UNIX was launched with a heafty price tag. Everybody wanted to use UNIX but the cost was too much to afford. Then as a revolt a person named Richard Stallman started the Free Software Foundation(FSF) with the mission of making a totally free UNIX like OS. He did end up with what we call GNU-OS but, the kernel he created (HURD) was not efficient enough. At the same time, somewhere, a person named Linus Torvalds was also making a UNIX like kernel. Linus Torvalds made Linux kernel. Both Richard and Linus met and, obviously HURD was replaced with Linux to get the GNU-Linux OS. Hence Richard Stallman and Linux Torvalds are called founding fathers of Linux.
## Popular Operating System:-
   
- GNU/linux
- DEBAIN

    - UBUNTU(80)

- REDHAT

    - FEDARA
    - CENTOS
    - MINT
## Other distro:-
 - Dos/windows
 - Unix
 - Apple/unix
 - Hp/unix
 -  FreeBSD
 -  NetBSD

<p> In linux everything is file /$/ boot -> it is the place where the kernel is stored. If the operating system is a human body then the kernel is the heart of that body. Operating system is a interface between user and software but Kernel is interface between hardware and software 
 
When we switch on the computer the first thing which opens is the kernel .

Linux is kernel and ubuntu ,redhat this are operating system <p>

---

## Linux commands :-

-  <b>ls -> Stands for list of files .
- cp -> copy file and directories
- mv -> move file or folder one place to another place.
- mkdir-> create directories.
- exit-> exit for terminal.
- pwd -> present Working directories.
- history -> How many commands used.
- who am i -> Current login user.
- who -> How Many users are logged in list of logged in users.
- cat -> Displays content  of the file on terminal.
    
    - cat filename -> displays 
    - cat > filename -> overrides 
    - cat >> filename -> appends 
- echo-> Print parametors.
- top -> All The system information  Devops are used this 
more frequently used this command.
- ps -> All the running Application .
- ssh ->Access the Remote  server.

- touch -> Create new file .
- more -> more gives us less data . paginate the file 
- less -> less gives  us more data . paginate the file
- rmdir [Remove Directory] -> rmdir commands only delete the empty folder if the folder consists of any file then this command will not work.
- rm[REMOVE] -> Remove commands can delete file
    - rm-rf[Remove]-> Remove commands can delete all the files and directory.
    - rm-rf a/b/c -> it will delete c
    - rm -rf a* -> delete any file or directory that start with a.
    - rm -rf *f -> delete any file or directory that ends with f.
    - rm -rf *imp* -> delete file and directory that has imp in the name .


- cd -> Change Directory.
- ping ->This is a network command to check the internet connectivity of my machine
- Ifconfig -> In windows we use ipconfig to get all the details about my internet connection like my IP, Subnet Mask, Default Gateway, DNS,
 - wget ->: command line browser 
 - which -> It shows us the path where our software is installed.
 - mkdir 2020/14 2021/01 ???p:
 this command will create two directories named
 inside 2020 folder, it willncreate a subfolder named "14", and inside 2021 folder, it will create a subfolder named ???01???.
- top :-> display all the running application and system utilization .
- tail :- display the content of conti nuously getting updated 
## Advance Linux commands:- 
 

- lS -l :- if we want to get file details then this command is used.
- lS-l-h:- if we want to get file details and also if we want human readability then we use this command.
 - ls-l--t:- if we want to create a file in descending order  then we use this command.
 - lS-l-r:-if we want to create a file in ascending order then we use this command 
- ls-a:- it will show us all the hidden files or to find all the hidden files we used.
- man -ls :- It will show all the files in detail.
 - Ls-l-f :- shows all content in long format but there is  a ???/??? at the end of every directory name which makes it easy to see which row is a file and which one is a directory.
 
 |cd|
|----|

- cd/ ->change directory to root directory.
- cd ~ -> change to home directory.
- cd ..  to move the present directory one step above from the current working directory.

- cd .. /.. -> two steps above from the present working directory 
- cd / root ->  goes to root path 
- cd - -> toggle to previous directory location 

 |cp|
|----|

- cp-> cp is same as mv  it will also help  us to copy one folder to other folder or one file to other file 

   - <p> cp-rf  Anuja Rima Titire Mousumi
Now the above command will copy the folders Anuja, Rima, Titire to Mousumi folder.This happened because of the
help of the ???rf flags. 
-   cp f1 f2 -> copies filefrom sre to dst (rename) 
- cp -rf f1 f3 ->  copies file / directory from src to dst .(rename)
 - cp -rf f1 ~/ -> copies file /  directory from current location to home directiry with same name .
 - cp -rf f1 ~/newf1 -> copies file / directory from current location to home directory with new f1 .

 |mv|
|----|
 move  the file or directory from one location to another location
- mv f1 f2  -> move the f1 src file to f2 dst.(rename)
- mv f1 f2/f3/final -> will move the f1 to inside f3 and rename it as final 
- mv a/b/c d/e/f -> will move the c to inside e and rename it as f .

        
---

##  Linux File System:-
<p> File in the Unix-like System are organized into a multi-level hierarchy structure know as a directory tree .At the very top of the file system in a directory is called ???root??? which is represented by a???/??? All other files are </p>

- <b> / :-</b> The slash / character alone denotes the root of the filesystem tree.
-  <b>/user:-</b> This is where we can find the installed application for the use.
    - <b>/bin:-</b> stands for ???binaries??? and contains certain fundamental utilities such as ls or cp,which are generally needed by all users.
    - <b>-/sbin:- </b>sbin will store the functions for the system admin only,others will not have the permission to use these functions.
- <b>/dev:-</b> this is where you can see all your devices list.This is kind of memory file .
- <b>/etc:-</b> System configuration are stored .
 - <b>/home:-</b> where we can store the personal files for each user.inside this there will be a folder for each user.
 - <b>/lib:</b> Contains system libraries,and some critical files such as kernel modules device drivers.
 - <b>/mmt:-</b> where the external devices get mounted.your Pen drive,and other devices.mnt is for manually mounted devices
- <b>/proc:-</b> This file includes pseudo files that contain information about system processes and the resources
 - <b>/root:-</b> This is the root users home  folder. You can store files here and you need the root permission to access it.

- <b>/temp:-</b> this folder will store the temporary files which are used by the sessions.
 - <b>/var:-</b> This contains the files or the folders which are expected to grow in size. Ex: log  files, crash reports,etc.
 - <b>/opt:-</b> This is the Optional folder. Which is used for manually installed software from vendors resides.






  
        
        

        















    

 


    
