# File Globbing using *
```bash
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ ./run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{UCuJMKYT7TsYzhFr3umyeMMh2WX.dFjM4QDL1YDN1czW}
hacker@globbing~matching-with-:/challenge$
```

\* Does not replace leading . and /

# File Globbing using ?
? works exactly like \*, but only acts like a wildcard for *1* character.
```bash
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ ./run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{QTg80QyOe7SIoqJ4VJsnAYIVgwB.dJjM4QDL1YDN1czW}
```

# File globbing with []

[] is a limited form of ?, you have to specify which characters it can substitute.
Acts just like in regex.

```bash
hacker@globbing~matching-with-:/challenge$ ./run file_[absh]
Error: please run with a working directory of /challenge/files!
hacker@globbing~matching-with-:/challenge$ cd files
hacker@globbing~matching-with-:/challenge/files$ ../run file_[absh]
You got it! Here is your flag!
pwn.college{cz60qHcW5R5btS0jlpHj6FRJwdn.dNjM4QDL1YDN1czW}
```

# File globbing with [] 2

```bash
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[absh]
You got it! Here is your flag!
pwn.college{gav0B-NRD7u3jCUnQ-PmRuB0-Ku.dRjM4QDL1YDN1czW}
```

# Mixing Globs
```bash
hacker@globbing~mixing-globs:/challenge/files$ ../run [cep]*
You got it! Here is your flag!
pwn.college{QjCKGTWnZDq4AJi_x1wuOqlTiww.dVjM4QDL1YDN1czW}
```

# Exclusionary globbing
```bash
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files/
hacker@globbing~exclusionary-globbing:/challenge/files$ ../run [^pwn]*
You got it! Here is your flag!
pwn.college{ocF417MiOrlZf8gYrZ7G-Luw1V4.dZjM4QDL1YDN1czW}
```

! and ^ are negation characters, however ! works differently if its not the first character.
