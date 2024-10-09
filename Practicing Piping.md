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
The `|` operator essentially allows you to filter data step-by-step by passing the output of one command directly into another without running 2 lines of command <br>
Invoking `/challenge/run | grep pwn` executes `/challenge/run` and searches(greps) for `pwn` in `/challenge/run` <br>
Flag is : `pwn.college{YP4FEYEYl45paVRofCQi-U27l0W.dlTM4QDLxQjN0czW}`

# viii) Grepping errors
`>&` command redirects a file descriptor to another file descriptor <br>
foe example, `2>&1` redirects FD 2 (stderr) to FD 1 (stdoout) <br>
In this challenge, we redirect output of errors of  `/challenge/run` to its output an search (grep) for `pwn` in it to get the flag <br> 
`/challenge/run 2>&1 | grep pwn` <br>
Flag is : `pwn.college{4UjII6w1uG29BWtxnkR2DX5orJY.dVDM5QDLxQjN0czW}`

# ix) Duplicating piped data with tee
`tee` command, named after a "T-splitter" from plumbing pipes, duplicates data flowing through your pipes to any number of files provided on the command line <br>
In this challenge, we 
Flag is : `pwn.college{o11Jp6KOqFiSAQv4ExHRl0gr9tS.dFjM5QDLxQjN0czW}`

# x) Writing to multiple programs
Process substitution is a feature that allows the output of a command to be used as if it were a file.<br>
In this challenge, we take output of `/challenge/hack` and pass it as input to the files `/challenge/the` and `/challenge/planet` files using Process Substitution as these fikes do not accept any input by default <br>
Invoking the command, `/challenge/hack | tee >( /challenge/the ) >( /challenge/planet )` <br>
Flag is : `pwn.college{YPQforHg7NYSYORFJJLqUkGH-HO.dBDO0UDLxQjN0czW}`

# xi) Split piping stderr and stdout
In this challenge, we connect the standard output of `/challenge/hack` to `/challenge/input` and <br>
all the standard errors of `/challenge/hack` to `/challenge/the` using process substitution <br>
` /challenge/hack > >( /challenge/planet ) 2> >( /challenge/the )`
Flag is : `pwn.college{wqPD6rO2xiOJWO5G9xpjTZ4vVyl.dFDNwYDLxQjN0czW}`
