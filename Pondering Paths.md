# Module 2 : Pondering Paths
This module encloses an introduction to the tree directory structure of the computer as well as concept of relative and absolute paths.
# i) The Root
Learnt to invoke a program called `pwn` using it's absolute path which is the path from the base of the tree structure<br>
Statement to invoke the program is : `/pwn `<br>
Flag is : `pwn.college{QTZtSpAYG1lT_kshux4m7mEuTRQ.dhzN5QDLxQjN0czW}`

# ii) Program and absolute paths
Learnt to change directories by using `/`<br>
Command used : `/challenge/run`<br>
Flag is : `pwn.college{QTZtSpAYG1lT_kshux4m7mEuTRQ.dhzN5QDLxQjN0czW}`

# iii) Position they self
Learnt to use the `cd` command to change directories in linux subsystem<br>
Also, learnt to execute a program from a directory different than the current working directory<br>
Changed the directory to `cd /proc/67` and then executed `/challenge/run`<br>
The flag is : `pwn.college{wAIoaUHyNNBCY4By5MwSQiLbe7b.dZDN1QDLxQjN0czW}`

# iv) Position elsewhere
This challenge required me to execute the program from the directory `/`<br>
After changing directory, I executed `/challenge/run`<br>
Flag is : `pwn.college{oZABdehwpi9p51fpryHmG3QMeM3.ddDN1QDLxQjN0czW}`

# v) Position yet elsewhere
Changed the directory to `cd /proc/67` using absolute path and then executed `/challenge/run`<br>
Flag is : `pwn.college{Y_UIWAjbsNRqiG4q4YoHNfTExFy.dhDN1QDLxQjN0czW}`

# vi) implicit relative paths, from /
Learnt about relative paths which are paths associated with respect to the current working directory<br>
Relative paths do not start with `/` but absolute paths begin with `/`<br>
Using relative path, it searches for the required path in the cwd only thus may be more efficient by narrowing down searching
area<br>
I found the cwd by the command `pwd` and the output was `/home/hacker`<br>
i went 2 steps back by using command `cd ..` twice and then executed `challenge/run`<br>
Flag is : `pwn.college{8koIO2yqjLJ7ImlmdqxCatInnmw.dlDN1QDLxQjN0czW}`

# vii)  explicit relative paths, from /
I found the cwd by the command `pwd` and the output was `/home/hacker`<br>
i went 2 steps back by using command `cd ..` twice and then executed `./challenge/run`<br>
Essentially, the motive of the module was to tell me that adding a dot does not make any difference<br>
Flag is : `pwn.college{YHDdCYN9e2ZT_b6XOOTmTyFzWrl.dBTN1QDLxQjN0czW}`

# ix) implicit relative path
There is a safety measure in linux to avoid accidental execution of programs<br>
If i go into directory `cd /challenge` and enter `run` it will not execute the program and i have to mention 
the relative path of the program explicity to execute it as `./run`<br>
Flag is : `pwn.college{0dybqXsyMRyhv1vwP5WCYQrp532.dFTN1QDLxQjN0czW}`

# x) home sweet home
Learnt that `~` is a shorthand operator to the home directory, i.e. `/home/hacker`<br>
However, `~/~` expands to `/home/hacker/~` as only the leading `~` expands to `home/hacker`<br>
In the challenge, I ran `/challenge/run ~/x` which writes the flag in `/challenge/run/x`<br>
Writing the file to /home/hacker/x!
... and reading it back to you:
Flag is : `pwn.college{g4pqlffiMqoatOctjuUkizHRCoF.dNzM4QDLxQjN0czW}`

