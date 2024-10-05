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

# vi) touching files

