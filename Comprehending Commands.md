# Module 3 : Comprehending Commands

# i) cat command
the command `cat` in linux reads the contents of the file in it's arguement passed to it <br>
For example, `cat myfile ` read the contents of myfile <br>
I read the contents of the file `flag` using the command `cat flag`<br>
Flag is : `pwn.college{wYZ7j0TXC9PdK8uak7OtmoDWB1C.dFzN1QDLxQjN0czW}`

# ii) catting absolute paths
This part teaches me that I can give file location as an arguement to the `cat` command <br>
I executed `cat /flag` which gave me the flag<br>
FLag is : `pwn.college{Ycq0Epb-st69ibCs7HTlEOuDN0t.dlTM5QDLxQjN0czW}`

# iii) more catting practice
I chased cat with absolute path, a continuation of the previous subpart<br>
I passed the command `cat /usr/lib/terminfo/flag`<br>
Flag is : `pwn.college{oUzoeATtCetpN2Li0WLQXXjmJis.dBjM5QDLxQjN0czW}`

# iv) grepping for a needle in a haystack
This is the command used to search for a substring in a bigger string or a text file<br>
The command `grep` takes 2 inputs, firstly the SEARCH_STRING and secondly the location of file like <br> `grep SEARCH_STRING FILE_LOCATION`<br>
I passed `grep pwn.college /challenge/data.txt` to the terminal to get the flag<br>
Flag is : `pwn.college{s61HFayKQ63q3E1IQ5Lj2VT2G5O.ddTM4QDLxQjN0czW}`

# v) listing files
The listing command `ls` lists the files in the current working directory<br>
`ls /challenge` listed the files under the directory  `challenge` and it was `31382-renamed-run-6370`<br>
I ran that file using `/challenge/31382-renamed-run-6370` and got the flag !<br>
Flag is : `pwn.college{UY7yXSQgql2_7MEmJkmrr9z4uus.dhjM4QDLxQjN0czW}`

# vi) touching files
`touch` is a command that creates a blank file in the present working direectory<br>
`touch /tmp/college` and ` touch /tmp/pwn` creates 2 new blank files <br>
Then, execute `/challenge/run` to get the flag<br>
Flag is : `pwn.college{AR2ZOg2HE0Z5rwJ1UkNHqSxN4zW.dBzM4QDLxQjN0czW}`

# vii) removing files 
Learnt to remove or delete files using the `rm` command<br>
Initially, created a blank file using `touch delete_me`, then deleted it `rm delete_me`, and executed `/challenge/check` to get flag<br>
Flag is : `pwn.college{EmapV9W26FhSQxB4LHJVFRci8eI.dZTOwUDLxQjN0czW}`

# ix) hidden Files 
Some system files that begin with `.` do not show up when `ls` command is passed to the terminal<br>
To display these files, `ls -a` command must be given<br>
To find dot prepended files in `/` is changed directory by `cd /` ,then found the file `.flag-47541698019408` and read it by `cat .flag-47541698019408` <br>
Flag is : `pwn.college{Qf9kGD7A31Y3IkK17o8Mjan0x-d.dBTN4QDLxQjN0czW}`

# x) An Epic Filesystem Quest
This challenge was a revision everything learnt uptil now. It encouraged the usage of `cd`, `ls`, and `ls -a` commands <br>
Flag is : `pwn.college{sPvh9agZAobajCier3n0IH6bUyE.dljM4QDLxQjN0czW}`

# xi) making directories
Learnt to make directories using the `mkdir` command <br>
Made directory `mkdir /tmp/pwn` and created file `touch /tmp/pwn/college`, then executed `/challenge/run` to get flag<br>
Flag is : `pwn.college{ksookdeJ9gD5bg9wEMWF58QIORF.dFzM4QDLxQjN0czW}`

# xii) Finding files
Find command is used to find files within the system<br>
It takes 2 optional arguements, firstly the file location, and secondly the name of file<br>
With the syntax `find /file_location -name file_name`<br>
In this challenge, the flag was hidden in a random directory and i was expected to find it using `find` command<br>
Flag is :  `pwn.college{8qkdqBRbiiOM7lJB0Kg9vNR6fbQ.dJzM4QDLxQjN0czW}`

# xiii) linking files 
`file FILE_NAME` command takes the FILE_NAME as the arguement and displays the type of file <br>
Learnt about hard and soft(sybolic) links which are created with `ln -s` command <br>
A hard link are multiple adress link to the contents of the same file<br>
In most cases, both situations result in accessing the original data, but the mechanisms are different.<br>
The challenge is to get the flag with a symbolic link to `/flag` from `/home/hacker/not-the-flag` <br>
These were steps I followed to obtain the flag : <br>
`rm /home/hacker/not-the-flag`<br>
`ln -s /flag /home/hacker/not-the-flag`<br>
`/challenge/catflag`<br>
<br>
Flag is : `pwn.college{wXvvk2TacwrB47kbq-FC3MBaZ7D.dlTM1UDLxQjN0czW}`

