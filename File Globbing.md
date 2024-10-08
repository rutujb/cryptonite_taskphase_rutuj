# Module 5 : File Globbing

# i) Matching with *
`*` is a wildcard that can replace any set of characters  except `/` or leading `.` in a file location<br>
In this challenge, we invoked `cd /ch*` which expands to `cd /challenge`, then executed `/challenge/run` to get the flag  <br>
Flag is : `pwn.college{oRxjn9EF5zJ0F84O2-kNQm_Cbse.dFjM4QDLxQjN0czW}`

# ii) Matching with ?
`?` is a single character wildcard, i.e. it can replace only 1 character in a file location <br>
In this challenge, we change directory using `cd /?ha??enge` which expands to `cd /challenge`, then invoke `/challenge/run` to get the flag <br>
Flag is : `pwn.college{wwxNdeTghYJSShKzd-bOyGUIwUI.dJjM4QDLxQjN0czW}`

# iii) Matching with []
`[]` is a wildcard for some subset of potential characters, specified within the brackets <br>
example : `[abc]` can substitute any of the letters 'a', 'b', and 'c' <br>
In this challenge, `/challenge/run file_[absh]` looks for all 4 files namely, file_b, file_a, file_s, and file_h <br>
Flag is : `pwn.college{ck5LdcHaz_zcPIPQV1cgwWjbHUl.dNjM4QDLxQjN0czW}`

# iv) Matching paths with []
`/challenge/run /challenge/files/file_[bash]` executes `/challenge/run` in the directory specified as arguement with wildcar [absh] <br>
Flag is : `pwn.college{4wGSBmCjUAu9W85G2zj6NbkS6tC.dRjM4QDLxQjN0czW}`

# v) Mixing globs
write a single, short (6 characters or less) glob that will match the files "challenging", "educational", and "pwning"! <br>
`/challenge/run [cep]*` gives flag <br>
Flag is : `pwn.college{4GNxBZqSKhE8xxiYyYdAWygBPdZ.dVjM4QDLxQjN0czW}
`

# vi) Exclusionary globbing
If the first character in the brackets is a ! or (in newer versions of bash) a ^, the glob inverts, and that bracket instance matches characters that aren't listed. <br>
`/challenge/files$ /challenge/run [!pwn]*` enlists file that do not start with p, w , or n <br>
Flag is : `pwn.college{su16uPjHzo0Ac6TiwJ8_ytkJDgp.dZjM4QDLxQjN0czW}`
