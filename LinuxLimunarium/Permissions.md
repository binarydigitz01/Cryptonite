# Changing file ownership
```bash
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{UU-ElijnAC3VE01FnrV2R6OA6ek.dFTM2QDL1YDN1czW}
```
# Changing file group
```bash
hacker@permissions~groups-and-files:~$ chgrp hacker /flag
hacker@permissions~groups-and-files:~$ cat /flag
pwn.college{sVypjfMxSS3Aph8KvbOrdz0maf1.dFzNyUDL1YDN1czW}
```

# Fun with group names
```bash
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp9949) groups=1000(grp9949)
hacker@permissions~fun-with-groups-names:~$ chgrp grp9949 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{cSl4wS8sec9QBTvVdguP3RY7evx.dJzNyUDL1YDN1czW}
```

# Permissions
NOTE:

    u+r, as above, adds read access to the user's permissions
    g+wx adds write and execute access to the group's permissions
    o-w removes write access for other users
    a-rwx removes all permissions for the user, group, and world

```bash
hacker@permissions~changing-permissions:~$ ls -l /flag
-r-------- 1 root root 58 Oct 25 00:49 /flag
hacker@permissions~changing-permissions:~$ chmod o+r /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{MVCe1--TksydCz5eBAQegEN1YPn.dNzNyUDL1YDN1czW}
```
# Executable Files
```bash
hacker@permissions~executable-files:~$ ls -l /challenge/run
-r--r--r-- 1 hacker hacker 32 Jul  4 06:37 /challenge/run
hacker@permissions~executable-files:~$ chmod u+x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
pwn.college{Awo97A1o0bnxlU-3WEVBoa37qmH.dJTM2QDL1YDN1czW}
```

# Permission Practice
```bash
$ chmod a+rw /challenge/pwn
$ chmod o+x /challenge/pwn
$ chmod go-rwx /challenge/pwn
$ chmod o+w /challenge/pwn
$ chmod a-rwx /challenge/pwn
$ chmod uo+r /challenge/pwn
$ chmod u-w /challenge/pwn
$ chmod g+rwx /challenge/pwn
$ chmod a+r /flag
$ cat /flag
pwn.college{AQrfWmYvcBmCKl4mmFyKoe6xPZE.dBTM2QDL1YDN1czW}
```

# Permission setting practice
```bash
$ chmod a+rwx /challenge/pwn
$ chmod u=r,o-x /challenge/pwn
$ chmod u+w,go=r /challenge/pwn
$ chmod u=rx,g=r,o=wx /challenge/pwn
$ chmod u=rx,g=wx,o=rw /challenge/pwn
$ chmod go=r,u=- /challenge/pwn
$ chmod u=w,g=x,o=rw /challenge/pwn
$ chmod u=rwx,g=r,o=x /challenge/pwn
hacker@permissions~permissions-setting-practice:~$ chmod a+r /flag
hacker@permissions~permissions-setting-practice:~$ cat /flag
pwn.college{kcvZzS4g8LcBKSdE5ga0Xu7YXgU.dNTM5QDL1YDN1czW}
```
# SUID
```bash
hacker@permissions~the-suid-bit:~$ ls -l /challenge/getroot
-rwxr-xr-x 1 root root 155 Jul 12 10:30 /challenge/getroot
hacker@permissions~the-suid-bit:~$ chmod a+s /challenge/getroot
hacker@permissions~the-suid-bit:~$ /challenge/getroot
SUCCESS! You have set the suid bit on this program, and it is running as root!
Here is your shell...
root@permissions~the-suid-bit:~# cat /flag
pwn.college{QgLQN6g_vpIrAdCkj0Nlo3LsUn7.dNTM2QDL1YDN1czW}
```

# John The Ripper
```bash
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
aardvark         (zardus)
1g 0:00:00:24 100% 2/3 0.04006g/s 233.2p/s 233.2c/s 233.2C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ su zardus
Password:
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{4oYYwY0TEP6iNxLWGFgi20RBDkc.ddTN0UDL1YDN1czW}
```
# sudo
```bash
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{w4qCeSAjhDqfaNAJPUcXZfkWgo1.dhTN0UDL1YDN1czW}
```
