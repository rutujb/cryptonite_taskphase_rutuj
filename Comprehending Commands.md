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
The command `grep` takes 2 inputs, firstly the SEARCH_STRING and secondly the location of file like `grep SEARCH_STRING FILE_LOCATION`<br>
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
Flag is : `pwn.college{sPvh9agZAobajCier3n0IH6bUyE.dljM4QDLxQjN0czW}`

# xi) making directories
Learnt to make directories using the `mkdir` command <br>
Made directory `mkdir /tmp/pwn` and created file `touch /tmp/pwn/college`, then executed `/challenge/run` to get flag<br>
Flag is : `pwn.college{ksookdeJ9gD5bg9wEMWF58QIORF.dFzM4QDLxQjN0czW}`

# xii) Finding files
Flag is :  ``
