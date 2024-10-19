# Module 12 : Pondering PATH
## i) The PATH Variable
We write into the `x.sh` file the following commands : `PATH=""` AND `/challenge/run` so that the shell can't find where to search for `rm` and it won't remove the flag.<br>
Then, we invoke `bash x.sh` to get the flag :
>pwn.college{wgeZPst96g_wbEpqTBQP3tF8HhU.dZzNwUDLxQjN0czW}

## ii) Setting PATH
We write `PATH="/challenge/more_commands/";/challenge/run` into the `x.sh` file and invoke `/challenge/run` with the arguement `win` to get the flag :
>pwn.college{k2twIBV1HscQWGCuSRtqlnXRe5f.dVzNyUDLxQjN0czW}

## iii) 
