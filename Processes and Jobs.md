# Module 8 : Processes and Jobs
When Linux starts up, it launches an init (short for initializer) process that, in turn, launches a bunch of other processes which launch more processes until, eventually, you are looking at your command line shell, which is also a process! The shell, of course, launches processes in response to the commands you enter. 

## i) Listing Processes
The `ps` command, short for "process snapshot" or "process status" lists the processes running in your terminal <br>
It displays 4 columns of the running processes including PID, TTY, TIME, CMD in the defuault `ps` without arguements <br>
each process has a numerical identifier (the Process ID, or PID), which is a number that uniquely identifies every running process in a Linux environment <br>
We also see the terminal on which the commands are running (TTY) <br>
total amount of cpu time that the process has eaten up so far (TIME) <br> <br>
There are 2 ways to specify arguements to `ps` : <br>
1. Standard Syntax : we can use `-e` to list "every" process and `-f` for a "full format" output, including arguments. These can be combined into a single argument `-ef` <br>
2. BSD Syntax : a to list processes for all users, `x` to list processes that aren't running in a terminal, and `u` for a "user-readable" output. These can be combined into a single argument `aux`. <br> <br>
Differences between `ps aux` and `ps -ef` <br>
`ps -ef` additionally outputs the Parent Process ID (PPID), while `ps aux` outputs the percentage of total system CPU and Memory that the process is utilizing <br> <br>
In this challenge, we list processes by `ps -ef` and run `/challenge/7377-run-30750` to get the flag :
>pwn.college{sHgW8UuN51anPFtjr3o-DUyYB9h.dhzM4QDLxQjN0czW}

## ii) killing processes
`kill` command is used to terminate processes in the terminal <br>
A process is found and to be killed using `ps -ef | grep dont_run` and `kill 73`, then run `/challenge/run` to get flag :
>pwn.college{spDFAWPJNRshrgmajPv4aFddEB_.dJDN4QDLxQjN0czW}

## iii) Interrupting Processes
used to get rid of the process that's clogging up your terminal <br>
Pessing `Ctrl + C` interrupts any process waiting for input on terminal, and this application cleanly exits <br>
In this challenge, we run `/challenge/run` and interrupt it by `Ctrl + C` to get flag :
>pwn.college{EDJaq9iUgmu4gGDPlES5tz84-vl.dNDN4QDLxQjN0czW}

## iv) Suspending Processes
You can suspend processes to the background with `Ctrl-Z`, which is a less drastic measure than interrupting a process by `Ctrl + C` <br>
In this challenge, we run `/challenge/run`, suspend it, run `/challenge/run` again to get the flag :
>pwn.college{ksb-vocGSzkvm10EmJml9XL7CTi.dVDN4QDLxQjN0czW}

## v) Resuming Processes
To resume processes, your shell provides the `fg` command, a builtin that takes the suspended process, resumes it, and puts it back in the foreground of your terminal. <br>
In this challenge, we run `/challenge/run`, suspend it, then again resume it invoking `fg` to get flag :
>pwn.college{MZ10wXL-jjCs_9ZMX7vUymc98hT.dZDN4QDLxQjN0czW}


## vi) Backgrounding Processes
You can also resume processes in the background with the `bg` command!
With the `ps -o` command, in the `STAT` column, we can which process is :
1. Running in Background `R` 
2. Running in foreground `R+`
3. Process is suspended `T`
4. Sleeping and suspended `Ss`
5. Sleeping but not suspended `S` <br> <br>
In this challenge, we run`/challenge/run`, suspend it, again run it in background `bg`, then again run `/challenge/run` to get flag :
>pwn.college{8Rdmv8_Pp0UVrGfdjjIo8rM5dsH.ddDN4QDLxQjN0czW}

## vii) Foregrounding Processes
you can foreground a backgrounded process with `fg` just like you foreground a suspended process <br>
In this challenge, we run `challenge/run`, then suspend it, then backgorund it using `bg`, then resume the process in the foreground using `fg` to get the flag :
>pwn.college{IxUj__UEQzWixDp306_2vM58Nzj.dhDN4QDLxQjN0czW}

## viii) Starting Backgrounded Processes
To background processes without suspending them, we have to append `&` to the command <br>
In this challenge, we have to start the given process in background. We do that by invoking `/challenge/run &` <br>
>pwn.college{0GqF7cY4t4uJLYhCa_hZng18kJX.dlDN4QDLxQjN0czW}

## ix) Process Exit Codes
You can access the exit code of the most recently-terminated command using the special `?` variable <br>
We prepend this with `$` to read it's value <br>
Generally, commands that succeed return `0`, and ones that don't return non zero values, typically `1` <br> <br>
In this challenge, we run `/challenge/get-code $?` to store the exit code to the variable `?`, then read the value stored in `?` invoking `echo $?`, thereafter invoking `/challenge/submit-code 167` where the exit code(167 here) is passed as an arguement <br>
>pwn.college{gXVEkBoIUSAbVrbN_7_yi1fQAmE.dljN4UDLxQjN0czW}
