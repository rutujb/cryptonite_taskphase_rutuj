# Module 11 : Chaning Commands
Aside from piping, this modules encloses some more methods to chain commands. <br>

## i) Chaining with semicolons
We can write multiple commands in the same line by seperating them with a `;` (semicolon) <br>
In this challenge, we run two commands `/challenge/pwn;/challenge/college` in a single line to get the flag :
>pwn.college{kvicWsLTRL0isGCEdQ81mlQOPQj.dVTN4QDLxQjN0czW}

## ii) Your First Shell Script
We can put a set of commands in one file, called a shell script, like `pwn.sh` (by convention, shell scripts end with `.sh`) <br>
We can execute that set of commands(in shell script) together by passing the shell script as an arguement to `bash` <br>
In this challenge, we create `touch x.sh` and edit by `nano x.sh`, then write `/challenge/pwn;/challenge/college` to it and bash out this file by `bash x.sh` to get the flag :
>pwn.college{4KieZIyAJYCXP3hM1Z1Zz9Ej3yZ.dFzN4QDLxQjN0czW}

## iii) Redirecting Script Output
In this challenge, we pipe the output of `x.sh` to `/challenge/solve` invoking `bash x.sh | /challenge/solve` to geth the flag :
>pwn.college{sPLmWJFMs_s0aMceEHMartH8s5z.dhTM5QDLxQjN0czW}

## iv) Executable Shell Scripts
We wrote `/challenge/solve` into the shell, made it executable invoking `chmod a=rwx ./x.sh`, then ran `./x.sh` to get the flag : <br>
>pwn.college{oP4VTpCsreQhv0URjGzbSv8tAUR.dRzNyUDLxQjN0czW}

