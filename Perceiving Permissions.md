# Perceiving Permissions
You can check out a permissions of a file or directory using `ls -l` <br>
![image](https://github.com/user-attachments/assets/b759830e-4930-41ef-ae93-eb4317f7dfc3) <br>
The first character of each line represents the file type, `d` indicates a directory and `-` incdicates a normal file, `c` indicates a special file (called character device)  <br>
The following 9 characters are the actual access permissions of the file, split into 3 parts about which we will learn in this module <br>
There are 2 columns showing that the user owns the file (`hacker` in this case) and the group owns the file (group is also `hacker` in this case ) <br>

In the character set of 9 character denoting the permissions, the first three denote permission for the owning user, the next three for the owning group and the last three denote the permissions that all other users and groups have to the file.<br>
`r` --> user/group can read the file <br>
`w` --> user/group can write/edit/make changes to file <br>
`x` -->user/group can execute the file as a program (can enter the directory) <br>
`-` --> nothing <br>
For example, `rw-r--r--` decodes to :
r: the user that owns the file can read it
w: the user that owns the file can write to it
-: the user that owns the file cannot execute it
r: users in the group that owns the file can read it
-: users in the group that owns the file cannot write to it
-: users in the group that owns the file cannot execute it
r: all other users can read it
-: all other users cannot write to it
-: all other users cannot execute it



## i) Changing File Ownership
we can change the ownership of files using the `chown` (change owner) command with the syntax <br>
`chown [username] [file]` <br>
However, `chown` can only be invoked by the root user <br>
In this challenge, we changed permissions of the `/flag` file from the `root` to the `hacker` invoking `chown hacker /flag`, then getting flag by `cat /flag` 
> pwn.college{gDtQeBG7hR-qyCt1ucssceW2oC6.dFTM2QDLxQjN0czW}

## ii) Groups and Files
You can check what groups you are a part of with the `id` command <br>
group ownership can be changed with the`chgrp` command, but this typically requires root access with the syntax <br>
`chgrp <user> <file_location>` <br>
In this challenge, we changed group of `/flag` file invoking ` chgrp hacker /flag` to read it : 
>pwn.college{s_MaFh-wYWyGoUXrRhTbPFoXuti.dFzNyUDLxQjN0czW}

## iii) Fun with Groups Names
In this challenge, initially we find which group we are a part of with `id` command <br>
Thereafter, we invoke `chgrp grp2309 /flag` to get access to and read the flag file by `cat /flag` 
>pwn.college{cBQNQfBusmY3yKAJhiX2kw1Yizz.dJzNyUDLxQjN0czW}

## iv) Changing Permissions
File permissions can be changed by invoking `chmod` command with syntax `chmod [OPTIONS(user.group)] MODE FILE` <br>
The mode can be specified in two ways. One way is : <br>
Modifying the existing mode, `chmod` allows you to tweak permissions with the mode format of WHO+/-WHAT, where WHO is user/group/other and WHAT is read/write/execute


## v) Executable Files
## vi) Permission Tweaking Practice
## vii) Permissions Setting Practice
## viii) The SUID Bit
