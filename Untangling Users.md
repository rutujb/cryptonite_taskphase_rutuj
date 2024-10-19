# Module 9 : Untangling Users
The full list of users on a Linux system is specified in the `/etc/passwd` file <br>
Each line of `/etc/passwd` contains seperated by `:`'s, --> username, password, default numerical group ID, long form user details,home directory,and the default shell. <br>

## i) Become root with su
In linux, to become the root user, we have two utilities --> `su`(switch user command) and `sudo` <br>
![image](https://github.com/user-attachments/assets/a1297fe4-c434-427b-ac52-5d1404356422) <br>
As the file has the SUID bit set, it can run as `root` and can start a shell. <br>
Before allowing the user root privileges, the `su` command takes the `root` password which obsoletes the use of `su` in modern day <br>
There are better methods (like `sudo`) in linux to allow administrative access to the user <br>
In this challenge, we invoke `su` and enter the password `hack-the-planet`, then read `/flag` to get the flag : 
>pwn.college{EqB11MouJ1j2ION1YgR67rLOWjl.dVTN0UDLxQjN0czW}

## ii) Other users with su
With no arguements passed to `su`, it starts the `root` shell by default. However, we can give a username as an arguement <br>
In this challenge, we invoke `su zardus` to access the user `zardus` and run `/challenge/run` to get the flag :
>pwn.college{E4YC9imsxu8Usp42m-48k5hJNXm.dZTN0UDLxQjN0czW}

## iii) Cracking passwords
