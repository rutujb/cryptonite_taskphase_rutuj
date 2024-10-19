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
Password of each user is stored in `/etc/shadow` file <br>
Username and password of a file is seperated by `:` and `*` or `!` symbol means that password login for the account is disabled, and a blank field indicates that the account is not password protected. <br>
A long string in the place of password is the result of one way encrypting (hashing) <br>
In this challenge, we learn to crack the password of a user by the famous John the Ripper method. <br>
We invoke `john /challenge/shadow-leak` to get the password and login to the account by `su zardus` and enter the password obtained which is `aardvark` and run `/challenge/run` to get the flag :
>pwn.college{w1wm0Rd57JQAqdP-qmb_3hp8wOn.ddTN0UDLxQjN0czW}

## iv) Using Sudo
We will learn about `sudo` (superuser do) now <br>
`sudo` basically runs any command given to it's arguement as the `root` user <br>
The `sudo` method does not authenticate with passwords, instead it checks with policies in `/etc/sudoers` <br>
In this challenge, we invoke `sudo cat /flag` to get the flag :
>pwn.college{0I8-5rM3pfcLGGuYe38UON7mBWJ.dhTN0UDLxQjN0czW}
