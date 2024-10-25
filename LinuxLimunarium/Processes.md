# Listing processes
```bash
hacker@processes~listing-processes:~$ ps -ef | grep challenge
root          68       1  0 22:54 ?        00:00:00 /challenge/3002-run-1392
hacker       100      73  0 22:56 pts/0    00:00:00 grep --color=auto challenge
hacker@processes~listing-processes:~$ /challenge/3002-run-1392
Yahaha, you found me! Here is your flag:
pwn.college{Y3fPT1zA1ttfD_rv1Koszr3Jx8-.dhzM4QDL1YDN1czW}
```
# Killing processes
```bash
hacker@processes~killing-processes:~$ ps -ef | grep dont_run
hacker        73      71  0 22:58 ?        00:00:00 /challenge/dont_run
hacker        93      75  0 22:58 pts/0    00:00:00 grep --color=auto dont_run
hacker@processes~killing-processes:~$ kill 73
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{stzPds1d9F3twFbUfClCEPSv7aL.dJDN4QDL1YDN1czW}
```
# Interrupting processes
```bash
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember,
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{IOXYuNTgZb80tzQgQZ6tZncbuc5.dNDN4QDL1YDN1czW}
```
# Suspending processes
```bash
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root          82      65  0 23:01 pts/0    00:00:00 bash /challenge/run
root          84      82  0 23:01 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can
background me with Ctrl-Z or, if you're not ready to do that for whatever
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root          82      65  0 23:01 pts/0    00:00:00 bash /challenge/run
root          89      65  0 23:01 pts/0    00:00:00 bash /challenge/run
root          91      89  0 23:01 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{gHiuQ52j9lorWvTKg88-Pfe0wnY.dVDN4QDL1YDN1czW}
```
# Resuming Processes
```bash
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{UcuWnInRvFAfkPR-7Qdb47GOVaR.dZDN4QDL1YDN1czW}
Don't forget to press Enter to quit me!

Goodbye!
```
# Background process
```bash
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root          82 S+   bash /challenge/run
root          84 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the
background, and then launch a new version of me! You can background me with
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &



Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out.
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root          82 S    bash /challenge/run
root          92 S    sleep 6h
root          93 S+   bash /challenge/run
root          95 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{QPSLuy3PTa4TIDd-x8QxpB5LQli.ddDN4QDL1YDN1czW}
```
# Foregrounding processes
```bash
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the
background, and *then* foreground it without re-suspending it! You can
background me with Ctrl-Z (and resume me in the background with 'bg') or, if
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &



Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out. After that, resume me into the foreground with 'fg';
I'll wait.
hacker@processes~foregrounding-processes:~$ fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{MRFSKlvh3XO2Wjgt05OboGHs44Z.dhDN4QDL1YDN1czW}
```

# Starting suspended processes
```bash
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 82



Yay, you started me in the background! Because of that, this text will probably
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{ACC__6z97lZNy0MPxz9ybjKu0Qb.dlDN4QDL1YDN1czW}
[1]+  Done                    /challenge/run
```

# Error Codes
```bash
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
71
hacker@processes~process-exit-codes:~$ /challenge/
DESCRIPTION.md  get-code        submit-code
hacker@processes~process-exit-codes:~$ /challenge/submit-code 71
CORRECT! Here is your flag:
pwn.college{0D5_lHggiiqgkHADge9HcEjFyQq.dljN4UDL1YDN1czW}
```
