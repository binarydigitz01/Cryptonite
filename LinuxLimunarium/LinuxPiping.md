# Redirecting Output

```bash
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your
flag:
pwn.college{Irjvr1woPPQtPU5WMQuUkiDTXCl.dRjN1QDL1YDN1czW}
```

# Redirecting more Output

```bash
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{8RbWYMwV8vdLVZZKbk70QYhOJvs.dVjN1QDL1YDN1czW}
```

The script communicates to us via stderr.

# Appending output
```bash
hacker@piping~appending-output:~$ /challenge/run >> the-flag
hacker@piping~appending-output:~$ cat the-flag
pwn.college{cyerJudB4OHT_-7iEV247awLCaC.ddDM5QDL1YDN1czW}
```

# Redirecting errors
## IMPORTANT_NOTES:
FD 0 -> stdin
FD 1 -> stdout
FD 2 -> stderr

```bash
hacker@piping~redirecting-errors:~$ /challenge/run 1> myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{wzmK5lzW3Q8CIhXSNbiZY4G_IS-.ddjN1QDL1YDN1czW}
```

# Redirecting input
```bash
hacker@piping~redirecting-input:~$ echo COLLEGE >PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{Ad6YLVOWJgtROFi2USeJpl1VyXA.dBzN1QDL1YDN1czW}
```

# Grepping stored results
```bash
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
hacker@piping~grepping-stored-results:~$ grep pwn.college /tmp/data.txt
pwn.college{47-5r20TLlsypT1XzehmFevXP2I.dhTM4QDL1YDN1czW}
```

# Pipe operator
```bash
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
pwn.college{4KIT9HrB2SElketdlcQ3EoIWo9N.dlTM4QDL1YDN1czW}
```

# Grepping errors
```bash
hacker@piping~grepping-errors:~$ /challenge/run 2>& 1 | grep pwn.college
pwn.college{I5VyNaMgBUi5de6Bb4bQgxs61hU.dVDM5QDL1YDN1czW}
```

The >& symbol redirects 1 file descriptor to another.
# Tee command
```bash
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee flag__ | /challenge/college
Processing...
The input to 'college' does not contain the correct secret code! This code
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ cat flag__
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "YcRM3-Mh"
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret YcRM3-Mh | /challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{YcRM3-Mh5ItxL-UKyu2mZn2kCzr.dFjM5QDL1YDN1czW}
```

# Named pipes
```bash
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >(/challenge/the) >(/challenge/planet)
This secret data must directly and simultaneously make it to /challenge/the and
/challenge/planet. Don't try to copy-paste it; it changes too fast.
237862503400025263
Congratulations, you have duplicated data into the input of two programs! Here
is your flag:
pwn.college{U-kTJ0-e-T_NA2Ftc0j0HMNB5w5.dBDO0UDL1YDN1czW}
```

You can use >({command_name}) to use named pipes, having stdin connected to a file.

# split piping stderr and stdout
```bash
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2> >(/challenge/the) 1> >(/challenge/planet)
Congratulations, you have learned a redirection technique that even experts
struggle with! Here is your flag:
pwn.college{0JK_lA3DgYKG6KCjAnJAHmxDeix.dFDNwYDL1YDN1czW}
```
