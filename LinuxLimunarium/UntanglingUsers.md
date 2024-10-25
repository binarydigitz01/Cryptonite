# su
```bash
hacker@users~becoming-root-with-su:~$ su
Password:
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{oNqkrJwRIeCBTNKlz_GzXi8qzxy.dVTN0UDL1YDN1czW}
```
# su with other user
```bash
hacker@users~other-users-with-su:~$ su zardus
Password:
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{oeP9Ep-P-AwIv6sVyDqbwhY24Br.dZTN0UDL1YDN1czW}
```
# Using John The Ripper
```bash
$ john /challenge/shadow-leak
aardvark (zardus)
$ su zardus
$ /challenge/run
```
# Using sudo
```bash
$ sudo cat /flag
```
