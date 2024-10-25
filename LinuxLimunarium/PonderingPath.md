# The Path Variable
```bash
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{IX8_uHhjeLiWG3gDdTMWmu3Szyj.dZzNwUDL1YDN1czW}
```
# Setting the path
```bash
hacker@path~setting-path:~$ PATH=$PATH:/challenge/
DESCRIPTION.md  more_commands/  run
hacker@path~setting-path:~$ PATH=$PATH:/challenge/more_commands/
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{wsKxo1Gckbkd9sRXkuXx-il6TAu.dVzNyUDL1YDN1czW}
```
# Adding Commands
```bash
hacker@path~adding-commands:~$ vim win
hacker@path~adding-commands:~$ ls -l win
-rw-r--r-- 1 hacker hacker 10 Oct 25 02:08 win
hacker@path~adding-commands:~$ PATH=$PATH:/home/hacker/
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
/challenge/run: line 4: /home/hacker/win: Permission denied
It looks like that did not work... Did you set PATH correctly?
hacker@path~adding-commands:~$ chmod o+x win
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
pwn.college{ApQCJ2n4SBqA6HDeXe1mnSxaNpM.dZzNyUDL1YDN1czW}

```

The win script:
```
cat /flag
```

# Shenanigans
Create a script named rm in home directory:
```
/usr/bin/cat /flag
```
We need to specify the full name as we remove the PATH.
```bash
hacker@path~hijacking-commands:~$ vim rm
hacker@path~hijacking-commands:~$ PATH="/home/hacker/"
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
pwn.college{sgt103OHvpqbmn7E4YXCjrkCHd2.ddzNyUDL1YDN1czW}
```
