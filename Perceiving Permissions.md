# Perceiving Permissions
You can check out a permissions of a file or directory using `ls -l` <br>
![image](https://github.com/user-attachments/assets/b759830e-4930-41ef-ae93-eb4317f7dfc3) <br>
The first character of each line represents the file type, `d` indicates a directory and `-` incdicates a normal file. <br>
The following 9 characters are the actual access permissions of the file, split into 3 parts about which we will learn in this module <br>
There are 2 columns showing that the user owns the file (`hacker` in this case) and the group owns the file (group is also `hacker` in this case ) <br>

## i) Changing File Ownership
we can change the ownership of files using the `chown` (change owner) command with the syntax <br>
`chown [username] [file]` <br>
However, `chown` can only be invoked by the root user <br>
In this challenge, we changed permissions of the `/flag` file from the `root` to the `hacker` invoking `chown hacker /flag`, then getting flag by `cat /flag` 
> pwn.college{gDtQeBG7hR-qyCt1ucssceW2oC6.dFTM2QDLxQjN0czW}

## ii) Groups and Files
You can check what groups you are a part of with the `id` command <br>



## iii) Fun with Groups Names
## iv) Changing Permissions
## v) Executable Files
## vi) Permission Tweaking Practice
## vii) Permissions Setting Practice
## viii) The SUID Bit
