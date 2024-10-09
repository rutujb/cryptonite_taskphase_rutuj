# Module 6 : Practicing Piping
Standard Input is the channel through which the process takes input.  - `stdin`<br>
Standard Output is the channel through which processes output normal data - `stdout` <br>
Standard Error is the channel through which processes output error details - `stderr` 

# i) Redirecting output
In, `"SOURCE" > "DESTINATION"`, the output of the source file is redirected to the destination file using `>` operator <br>
In this challenge, command given is `echo PWN > COLLEGE` to redirect output of `echo PWN` (which is "PWN") to `COLLEGE` <br>
Flag is : `pwn.college{cEaz3YrbcqJimsn_gxVyASsw_pM.dRjN1QDLxQjN0czW}`

# ii) Redirecting more output
The `>` operator can redirect output  of any file to another file <br>
In this challenge, we invoked `/challenge/run > myflag` to redirect output of `/challenge/flag` to `myflag` <br>
Then, read the later file `myflag`, invoking `cat myflag` to get the flag <br>
Flag is : `pwn.college{8MyJ2hFd5IhY0H2fVO_fkBJdyx_.dVjN1QDLxQjN0czW}`

# iii) Appending output
using `>` command, we can write multiple lines to the same destination file, as it overwrites the contents each time <br>
Although, with `>>` (append) command, we can write multiple lines to the same file as it appends contents to the file <br>
Using `/challenge/run >> /home/hacker/the-flag`, we redirected and appended second half of the flag to `/home/hacker/the-flag` <br>
To get the flag, we read contents of `cat /home/hacker/the-flag` <br>
Flag is : `pwn.college{oJbdQzKKwA_q6pOZqfX76-eTk5-.ddDM5QDLxQjN0czW}`

# iv) Redirecting errors
A File Descriptor (FD) number describes the communication channel in Linux. These are some standard ones : <br>
FD 0: Standard Input <br>
FD 1: Standard Output<br>
FD 2: Standard Error<br>
In this challenge, we redirect output of `/challenge/run` to `.myflag` and errors to `instructions` by invoking `/challenge/run > myflag 2> instructions` and get flag by reading `cat myflag` <br>
Flag is : ` pwn.college{waBQenuUpchBpeFrdOJSrL_8DzW.ddjN1QDLxQjN0czW}`

# v) Redirecting input
In this challenge, we learn about redirecting inputs by using `<` <br>
First, we copy contents of `echo COLLEGE` (which is 'COLLEGE') to the file `PWN` <br>
Then, redirect input of `PWN` to `/challenge/run` and get the flag <br>
`echo COLLEGE > PWN`
`/challenge/run < PWN`
Flag is : `pwn.college{IH2Q_vx0WQHEbjetTR-2lTDGWPR.dBzN1QDLxQjN0czW}`

# vi) Grepping stored results
In this challenge, we redirect output of `/challenge/run > /tmp/data.txt`, then read `cat /tmp/data.txt` which displays thousands of lines. Further to find the flag we execute `grep pwn /tmp/data.txt` <br> 
Flag is : `pwn.college{wKpqLYzTQDSMkgqXKoU6SIA7IxX.dhTM4QDLxQjN0czW}`

# vii) Grepping live output

Flag is : ``

# viii) Grepping errors

Flag is : ``

# ix) Duplicating piped data with tee

Flag is : ``

# x) Writing to multiple programs

Flag is : ``

# xi) Split piping stderr and stdout

Flag is : ``
