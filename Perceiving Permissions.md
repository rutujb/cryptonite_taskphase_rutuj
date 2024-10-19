# Module 9 : Perceiving Permissions
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
Modifying the existing mode, `chmod` allows you to tweak permissions with the mode format of WHO+/-WHAT, where WHO is user/group/other and WHAT is read/write/execute. <br> For example, `g+wx` command allows groups to write and execute, <br>
`a-rwxx` removes all permissions for the user, group and the world, `go-rw` removes read and write permissions for groups and other users. <br>
In this challenge, we invoke `chmod go+r /flag` to allow groups and other users to read the `/flag` file so we can <br>
`cat /flag` to get the flag : 
>pwn.college{MeIVZg03AjCK4mAGMurULYX-fl4.dNzNyUDLxQjN0czW}

## v) Executable Files
In this challenge, by invoking `chmod u+x /challenge/run`(user gets permission to execute) and running `/challenge/run` we get the flag :
>pwn.college{8K4xLj9QRGBzrjbWuKbQVBwneGM.dJTM2QDLxQjN0czW}

## vi) Permission Tweaking Practice
In this challenge we tweak permissions of files 8 times to get the flag by invoking : <br>
`chmod go+w /challenge/pwn` <br>
`chmod ug-r /challenge/pwn` <br>
`chmod ug-w /challenge/pwn` <br>
`chmod o-r /challenge/pwn` <br>
`chmod o-w /challenge/pwn` <br>
`chmod go+x /challenge/pwn` <br>
`chmod uo+r,u+x /challenge/pwn` <br>
`chmod uo-r /challenge/pwn` <br>
Now, to make the cat file readable, we invoke `chmod a+r /flag` and `cat /flag` to read the flag :
>pwn.college{QizhPehGrcgtWAcFFSvs8fhoP3h.dBTM2QDLxQjN0czW}

## vii) Permissions Setting Practice
The `chmod` command can also set permissions using `=` operator <br>
eg. `u=rw` sets read and write permission for the user and wipes execution permisssion <br>
If we want to set different permissions for user and groups and others, we can seperate them with `,` in `chmod`'s arguement <br> Also, we can zero out permissions like `o=-` will set user permission to nothing <br>
In this challenge we tweak permissions of files 8 times to get the flag by invoking : <br>
`chmod u=r--,g=rwx /challenge/pwn` <br>
`chmod u+wx,g-x,o=w /challenge/pwn` <br>
` chmod u-wx,g-w,o=rx /challenge/pwn` <br>
`chmod u=w,g+w,o=rw /challenge/pwn` <br>
`chmod u=-,g=w,o+x /challenge/pwn` <br>
`chmod u+wx,g+rx,o-rw /challenge/pwn` <br>
`chmod u=r,g=rx,o=r /challenge/pwn` <br>
`chmod a=x /challenge/pwn` <br>
Now, to make the cat file readable, we invoke `chmod a=r /flag` and `cat /flag` to read the flag :
>pwn.college{UH7mLP3BLwAVoL7XryR4ZNoQFsh.dNTM5QDLxQjN0czW}

## viii) The SUID Bit
The "Set User ID" (SUID) permissions bit allows the user to run a program as the owner of that program's file.<br>
![image](https://github.com/user-attachments/assets/c8120a1c-355b-4ae1-99c9-fd84e4415d3e) <br>
The `s` part in place of the executable bit means that the program is executable with SUID, i.e. regardless of which user runs the program, program will  execute as the owner user <br>
As the owner of a file, we can set a file's SUID by using `chmod` in the syntax `chmod u+s [program/file_name]` <br>
In this challenge, we invoke `chmod u+s /challenge/getroot` to set the SUID bit and get to the shell where we <br>
`cat /flag` :
>pwn.college{kIYrXFpj2RDnOhsLNiPtUkkGRTl.dNTM2QDLxQjN0czW}
