# Module 7 : Shell variables
# i) Printing Variables
The `cat` command can be used to print variables also <br>
Prepending a `$` before the arguement for `cat` indicates that `cat` is supposed to read a varibale <br>
In this challenge, `cat $FLAG` reads the contents of `FLAG` to get the flag which is :
> pwn.college{AWrIM5RYoQOY7o540RnIGqXw-XI.ddTN1QDLxQjN0czW}

# ii) Setting Variables
As in any other programming language, variables can be defined by the user in the command line <br>
`XYU=43` assgins the value `43` to variable `XYU` <br>
Note : No space can be given during varibale declaration, i.e. `XYU  = 43` would not work <br>
We assign COLLEGE to PWN by `PWN=COLLEGE` to get the flag which is :
>pwn.college{UpqDxplbRcd8DmobyI6bXy2mg2L.dlTN1QDLxQjN0czW}

# iii) Multi-word Variables
When the shell sees a space, it ends the variable assignment and interprets the next word <br>
Thus, to assign a value which has spaces, we need to put it in quotes <br>
for example `VAR="1337 SAUCE"` is used instead of `VAR=1337 SAUCE` <br>
In this challenge, we invoked `PWN="COLLEGE YEAH"` to get flag : 
>pwn.college{UWdb0kfaBE1567ssfVS_9Ci1zmf.dBjN1QDLxQjN0czW}

# iv) Exporting Variables
By default, variables that you set in a shell session are local to that shell process. That is, other commands you run won't inherit them. To explicitly export your variables, use the `export` command which exports the variable in arguement and it can be used in another shell process. <br>
Example, `export VAR=1337` and `export VAR` both work <br>
In this challenge, we invoke `export PWN=COLLEGE` and `COLLEGE=PWN` to get the flag :
>pwn.college{giXdhp7x3F846elAEtNXrU7hOh2.dJjN1QDLxQjN0czW}


# v) Printing Exported Variables
`env` command can be used to print out every exported variable in the shell <br>
We invoked `env $FLAG` to read contents of flag instead of `echo` <br>
>pwn.college{I1Ik7_Jp_B0-HDbENO4Yy7TsGmI.dhTN1QDLxQjN0czW}

# vi) Storing Command Output
to store the output of some command into a variable, we use Command Substitution <br>
Example, `FLAG=$(cat /flag)`, `FLAG` variable stores output of `cat /flag` <br>
We invoke  `PWN=$(/challenge/run)` to get the flag :
>pwn.college{4Cwey2zYFd7yGfJBeLRGbJUFKj-.dVzN0UDLxQjN0czW}

# vii) Reading Input
`read` bulletin reads input from the user <br>
We invoked `read PWN` and enetered `COLLEGE` as input to store COLLEGE in PWN to get the flag <br> 
>pwn.college{8W4qA9M310RecPFjeehbZ_D0IxV.dhzN1QDLxQjN0czW}

# viii) Reading Files
We invoked ` read PWN < /challenge/read_me` which redirects `/challenge/read_me` into the standard input of `PWN` 
to get flag : 
>pwn.college{gmzzMv0Vzb3XTYCO_Elew-ElOPT.dBjM4QDLxQjN0czW}
