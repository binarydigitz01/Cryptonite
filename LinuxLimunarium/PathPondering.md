# Path Pondering
## The Root
$ /pwn
 pwn.college{gkXqCGIiK5ozFYQSPWNEgikkeAR.dhzN5QDL1YDN1czW}

## Program And Absolute Paths
$ /challenge/run
$ pwn.college{4NJiLXdVp4pa4-R04MJ352EHYrK.dVDN1QDL1YDN1czW}

## Postion Thyself
$ hacker@paths~position-thy-self:~$ /challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:~$ cd /
hacker@paths~position-thy-self:/$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{gD4goUg4AYj3LG1Sg4XKa7s2ZwU.dZDN1QDL1YDN1czW}

## Position elsewhere
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /tmp directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /tmp
hacker@paths~position-elsewhere:/tmp$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{oVHKqVV3_ypiQi0QPU1_aOQY6jM.ddDN1QDL1YDN1czW}

## Position yet elsewhere

hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /usr/share/doc/fontconfig directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /usr/share/doc/fontconfig
hacker@paths~position-yet-elsewhere:/usr/share/doc/fontconfig$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{QwBvauv6chY3NU1Co1_H3Jhl14R.dhDN1QDL1YDN1czW}


## Implicit relative paths from /

hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{k-hy4XWTVlsar061qaJEFpKbxtS.dlDN1QDL1YDN1czW}

This was a fun script, I was amused when I read the question, as it differentiated between relative path
and absolute path. I thought the only way to differentiate between those was to see if the first letter
started with or without a '/'. This was indeed the case, when I read the script.

## explicit relative paths from /

hacker@paths~explicit-relative-paths-from-:~$ ../../challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{gBpzyMz_7UCGqMswRXLcAAigasq.dBTN1QDL1YDN1czW}

## implicit relative path

hacker@paths~implicit-relative-path:~$ cd /challenge/
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{kM7zgWxrjL54uS_PQ3x6YaTbJ5a.dFTN1QDL1YDN1czW}

## Home Sweet Home

hacker@paths~home-sweet-home:~$ /challenge/run ~/a
Writing the file to /home/hacker/a!
... and reading it back to you:
pwn.college{4XDRHoq93anQadozDjuwuBw6_QK.dNzM4QDL1YDN1czW}
