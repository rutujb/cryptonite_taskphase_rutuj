# Module 4 : Digesting Documentation

# i) Learning From Documentation
In this challenge, to get the flag, I had to invoke the program `/challenge/challenge` with `--giveflag` as the arguement<br>
So, the statement is `/challenge/challenge --giveflag`<br>
Flag is : `pwn.college{QRHmvfwyMkLbuvS42V8YVmnSJnT.dRjM5QDLxQjN0czW}`

# ii) Learning Complex Usage
This submodule uses an arguement within an arguement <br>
when the file location `challenge/challenge` is passed an arguement `--printfile` with the arguement `/flag`, it prints the contents of `/flag` <br>
`/challenge/challenge --printfile /flag`
Flag is : `pwn.college{Yr7eDPMereemHV9unx7N5NNbx-u.dVjM5QDLxQjN0czW}`

# iii) Reading Manuals
The `man file_name` command reads the manual of the file mentioned in it's arguement(file_name) <br>
In this challenge, firstly, we've run `man challenge` to get instructions to generate flag. Thereafter, 
`/challenge/challenge --cheytx 863` to get flag <br>
Flag is : `pwn.college{863c8hU3eytx8YigXHx-kEVNgHp.dRTM4QDLxQjN0czW}`

# iv) Searching Manuals
You can scroll man pages with the arrow keys (and PgUp/PgDn) and search with `/` <br>
you can hit `n` to go to the next result and `N` to go to the previous result <br>
In this challenge, on seeing the manual of challenge, we get the arguement to be given and execute 
`/challenge/challenge --tsq` <br>
Flag is : `pwn.college{sSsYfe260a2A_uzHWFOpSPmUGMC.dVTM4QDLxQjN0czW}`

# v) Searching For Manuals
Digging deeper, `man -k <keyword>` command where -k literally translating to keyword searches the manual of the file with the given keyword and displays to the user <br>
In this challenge, we used `man -k /challenge` to find the hidden manpage and got manual of `man gujrgbtlvd` to see it's manual <br>
Then, executed ` /challenge/challenge --gujrgb 179` to obtain the flag ! <br>
Flag is : `pwn.college{gP1JuNjW7r9gbtMRlL1I10LvGI1.dZTM4QDLxQjN0czW}`

# vi) Helpful Programs
Some programs do not have an associated manpage, but tell you how to run with special arguements like `--help` or `-h` <br>
In this challenge, by invoking `/challenge/challenge --help` command, an instruction page is displayed <br>
On invoking `/challenge/challenge -p`, secret value is displayed `The secret value is: 164` <br>
Then, command `/challenge/challenge -g 164` to get flag <br> 
Flag is : `pwn.college{sD1qv6RGCeo-NzNUPSnrRSguqOr.ddjM4QDLxQjN0czW}`

# vii) Help for Builtins
Some commands, rather than being programs with man pages and help options, are built into the shell itself. These are called builtins. You can get a list of shell builtins by running the `builtin help` <br>
In this challenge, `help challenge` will display  builtin help page and the secret key which is `g1goSmUK`. Now, invoke `challenge --secret g1goSmUK` to get the flag <br>
Flag is : `pwn.college{g1goSmUKnkZ2sX8HbtJC8yu8Irr.dRTM5QDLxQjN0czW}`

