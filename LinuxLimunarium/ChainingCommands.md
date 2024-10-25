# Chaining with ;
```bash
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn;/challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{wQy2Zvv7jkjZyoprJTdidCFjKus.dVTN4QDL1YDN1czW}
```

# shell script

Script:
```bash
/challenge/pwn
/challenge/college
```

```bash
hacker@chaining~your-first-shell-script:~$ vi x.sh
hacker@chaining~your-first-shell-script:~$ ./x.sh
ssh-entrypoint: ./x.sh: Permission denied
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{wKPHCbrO6I_81HXfQQgUyR-tElE.dFzN4QDL1YDN1czW}
```

# Redirecting
```bash
hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{YsPXyOXMyLmco7krDRDPffsE9y0.dhTM5QDL1YDN1czW}
```

# Executable scripts
Script x.sh:
```bash
/challenge/solve
```

Solution
```bash
hacker@chaining~executable-shell-scripts:~$ vi x.sh
hacker@chaining~executable-shell-scripts:~$ chmod u+x x.sh
hacker@chaining~executable-shell-scripts:~$ ./x.sh
Congratulations on your shell script execution! Your flag:
pwn.college{w6LpHLWeolohGV8RRufG1jiFPcV.dRzNyUDL1YDN1czW}

```
