# OASIS CTF 2024
This was my first experience of a Capture The Flag event which taught me many new things.<br>
All the flags are in the format `OASIS{  }` unless mentioned otherwise <br>
Following is a write up of the 10 latest challenges of the OASIS CTF 2024 

# 6) String me to Sleep
Flag is in plaintext in the middle of the file. Used grep to find it. <br>
`OASIS{y0u_fou7d_m3}`

# 7) This or that ?
A simple XOR cipher is given in the question with the cipher text and key mentioned which has to be decoded to get the flag <br>
`Ciphertext - 036363127c7c60001a117c6463170b`

`key - ARTEMIS_WHISPER`

decoding it, you get  `B17W153_MY573RY`

Further putting in it flag format `OASIS{B17W153_MY573RY}`

# 8) Jekylle and Hide!
The key is hidden in 2 different parts. <br>
To obtain the flag, we need to inspect each part of the library `https://oasis-challs-8-chi.vercel.app/` <br>
Part 1 is in `book.js` and part 2 is in `script.js` <br>
The obtained flag is : `OASIS{th15_15_part1_@nd_h3r3_go35_1h3_n3xt!!}`

# 9) Keynough is enough
An inscription `KHAAH{W1C3J7_C1O3F3G3}` is given to us, we have to decipher it <br>
To crack the code, consider a method that involves a repeating pattern  --> this indicates it is a vigenere cipher with the key `WHISPER`  <br>
Thus, the flag  obtained is : `OASIS{S1L3N7_V1G3N3R3}`

# 10) BasiKellY
A ciphertext is given in the description `J5AVGSKTPNWDA53LGN4V65BQGBPXGMDGORPXG4BQNMZW4XZTNB6Q====` <br>
This is encoded in base32. Use any online tool to decipher it to get the flag. <br>
Flag is : `OASIS{l0wk3y_t00_s0ft_sp0k3n_3h}`

# 11) Key-Key do you love me?
The key is in the form of the discord bot on the server. Talk to it in order to get the flag <br>
Asked it to convert instructions to python using chat GPT and got the flag <br>
Flag is : `OASIS{thE_kEyPeR_oF_sECReTS_iS_kInDa_wEiRD_nGL}`

# 12) Knock Knock
Given is an obscured QR code. The player has to unobscure it using increased contrast, etc. to get the flag from the QR. <br>
Flag is : `OASIS{qu3u3r_r3c0v3r3r}`

# 13) Microsoft Strong Edge
Given is a .pptx file. Extracting it, we find a file in the media/ directory. The file is an image with the flag encrypted with substitution cipher. <br>
The encrypted contents are `BNFVF{e0g4g0e_0s_cc75}` <br>
Using substitution cipher, decoding it, gives the flag which is : `OASIS{r0t4t0r_0f_pp75}` 

# 14) Maze Runner
An image was given in the challenge of a labyrnith, used google lens to decipher what the given monument is. <br>
Flag is the surname of Ideator behind the creation of the labyrinth and the name of the place where the object exists. <br>
When you dig deeper you get the Surname of the Ideator - `Borges` and place is `Fontanello`--> we get this after trying several permutations <br>
The flag  is : `OASIS{Borges_Fontanellato}`

# 15) Not Noice
Open the given .wav file in Audacity or any audio file visualizer and change the view to Spectogram to get the flag <br>
Flag is : `OASIS{5P3CT0GR4M_15_TH3_C00L35T}`

# 16) Nom-Nom
A pacman game is given which is not working originally for the user <br>
We have to make it work by inspecting the website and changing it's javascript code to allow the user to play. <br>
Go to Inspector-->cookies and change cookie value to true and refresh <br>
Flag is : `OASIS{p@cman_l!k3d_y0ur_c00k!3_<3}`







 
