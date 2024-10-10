# Cat
```bash
hacker@commands~cat-not-the-pet-but-the-command:~$ ls
Desktop  a  flag
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{YoP6OTPS8SqFFGKGBUhXuFWXvUf.dFzN1QDL1YDN1czW}
```
# Catting Absolute Paths
```bash
Connected!
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{IaOHsy5B2teWU5Ajdv1aPO9fQSH.dlTM5QDL1YDN1czW}
```

# More Catting Practice
```bash
hacker@commands~more-catting-practice:~$ PWD=/lib/terminfo/d/
hacker@commands~more-catting-practice:/lib/terminfo/d/$ ls
Desktop  a
hacker@commands~more-catting-practice:/lib/terminfo/d/$ cat a
pwn.college{4XDRHoq93anQadozDjuwuBw6_QK.dNzM4QDL1YDN1czW}
```

In this challenge, instead of using cd, I directly set the environment variable PWD to the desired directory, this works very similar to cd.

# Grep
```bash
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ ls
Desktop  a
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college a
pwn.college{4XDRHoq93anQadozDjuwuBw6_QK.dNzM4QDL1YDN1czW}

```

# Listing Files
```bash
hacker@commands~listing-files:~$ ls /challenge/
6624-renamed-run-21572  DESCRIPTION.md
hacker@commands~listing-files:~$ /challenge/6624-renamed-run-21572
Yahaha, you found me! Here is your flag: pwn.college{s-yijJ9GHysWESBGVX2Z4q4LKqO.dhjM4QDL1YDN1czW}

```

# Touching files
```bash
hacker@commands~touching-files:~$ vim /tmp/pwn
hacker@commands~touching-files:~$ vim /tmp/college
hacker@commands~touching-files:~$ /challenge/run
Success! Here is your flag:
pwn.college{kZ_mk-rMdpJ6qOrGP9hHpL68Fvr.dBzM4QDL1YDN1czW}
```
In this challenge, they told us to use touch, but i used vim, just cuz :p
# Removing files
```bash
hacker@commands~removing-files:~$ mv delete_me did_not
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{Qxf0Q41Z_c_xYixGOI9M648i5FI.dZTOwUDL1YDN1czW}
```

The intended solution was to use rm delete_me, but I renamed the file, which the /challenge/check can't determine.
# hidden files
```bash
hacker@commands~hidden-files:~$ ls -a /
.           .flag-85562818721517  challenge  home   lib64   mnt  proc  sbin  tmp
..          bin                   dev        lib    libx32  nix  root  srv   usr
.dockerenv  boot                  etc        lib32  media   opt  run   sys   var
hacker@commands~hidden-files:~$ cat /.flag-85562818721517
pwn.college{syYn7wJZl7gN0mayBig0JBZjkIm.dBTN4QDL1YDN1czW}
hacker@commands~hidden-files:~$
```
# An Epic Filesystem Quest
```bash
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls -lah
total 92K
drwxr-xr-x    1 root root 4.0K Oct  8 21:45 .
drwxr-xr-x    1 root root 4.0K Oct  8 21:45 ..
-rwxr-xr-x    1 root root    0 Oct  8 21:45 .dockerenv
-rw-r--r--    1 root root  211 Oct  8 21:45 EVIDENCE
lrwxrwxrwx    1 root root    7 May 30 02:03 bin -> usr/bin
drwxr-xr-x    1 root root 4.0K Apr 15  2020 boot
drwxr-xr-x    1 root root 4.0K Oct  8 21:45 challenge
drwxr-xr-x    6 root root  380 Oct  8 21:45 dev
drwxr-xr-x    1 root root 4.0K Oct  8 21:45 etc
-r--------    1 root root   58 Oct  8 21:45 flag
drwxr-xr-x    1 root root 4.0K Oct  4 23:03 home
lrwxrwxrwx    1 root root    7 May 30 02:03 lib -> usr/lib
lrwxrwxrwx    1 root root    9 May 30 02:03 lib32 -> usr/lib32
lrwxrwxrwx    1 root root    9 May 30 02:03 lib64 -> usr/lib64
lrwxrwxrwx    1 root root   10 May 30 02:03 libx32 -> usr/libx32
drwxr-xr-x    1 root root 4.0K May 30 02:03 media
drwxr-xr-x    1 root root 4.0K May 30 02:03 mnt
drwxr-xr-x    4 root root 4.0K Sep  6 16:53 nix
drwxr-xr-x    1 root root 4.0K Sep  6 16:42 opt
dr-xr-xr-x 3093 root root    0 Oct  8 21:45 proc
drwx------    1 root root 4.0K Sep  6 16:43 root
drwxr-xr-x    1 root root 4.0K Oct  8 21:45 run
lrwxrwxrwx    1 root root    8 May 30 02:03 sbin -> usr/sbin
drwxr-xr-x    1 root root 4.0K May 30 02:03 srv
dr-xr-xr-x   13 root root    0 Sep 15 22:45 sys
drwxrwxrwt    1 root root 4.0K Oct  8 21:49 tmp
drwxr-xr-x    1 root root 4.0K Sep  6 16:25 usr
drwxr-xr-x    1 root root 4.0K May 30 02:07 var
hacker@commands~an-epic-filesystem-quest:/$ cat flag
cat: flag: Permission denied
hacker@commands~an-epic-filesystem-quest:/$ cat EVIDENCE
Lucky listing!
The next clue is in: /opt/aflplusplus/qemu_mode/qemuafl/hw/avr

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/$ ls -lah /opt/aflplusplus/qemu_mode/qemuafl/hw/avr
total 60K
drwxr-xr-x 1 root root 4.0K Oct  8 21:45 .
drwxr-xr-x 1 root root 4.0K Sep  6 16:45 ..
-rw-r--r-- 1 root root  131 Oct  8 21:45 .WHISPER
-rw-r--r-- 1 root root  155 Sep  6 16:45 Kconfig
-rw-r--r-- 1 root root 4.6K Sep  6 16:45 arduino.c
-rw-r--r-- 1 root root  16K Sep  6 16:45 atmega.c
-rw-r--r-- 1 root root 1.3K Sep  6 16:45 atmega.h
-rw-r--r-- 1 root root 3.9K Sep  6 16:45 boot.c
-rw-r--r-- 1 root root  897 Sep  6 16:45 boot.h
-rw-r--r-- 1 root root  215 Sep  6 16:45 meson.build
hacker@commands~an-epic-filesystem-quest:/$ cd /opt/aflplusplus/qemu_mode/qemuafl/hw/avr
hacker@commands~an-epic-filesystem-quest:/opt/aflplusplus/qemu_mode/qemuafl/hw/avr$ cat .WHISPER
Tubular find!
The next clue is in: /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Gyre-Pagella/Monospace/Regular
hacker@commands~an-epic-filesystem-quest:/opt/aflplusplus/qemu_mode/qemuafl/hw/avr$ cd /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Gyre-Pagella/Monospace/Regular
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Gyre-Pagella/Monospace/Regular$ ls -lah
total 20K
drwxr-xr-x 1 root root 4.0K Oct  8 21:45 .
drwxr-xr-x 1 root root 4.0K Sep 15 08:45 ..
-rw-r--r-- 1 root root 3.3K Apr  4  2018 Main.js
-rw-r--r-- 1 root root   96 Oct  8 21:45 TEASER
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Gyre-Pagella/Monospace/Regular$ cat TEASER
Tubular find!
The next clue is in: /opt/busybox/busybox-1.33.2/include/config/feature/mdev/load
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Gyre-Pagella/Monospace/Regular$ ls /opt/busybox/busybox-1.33.2/include/config/feature/mdev/load
GIST  firmware.h
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Gyre-Pagella/Monospace/Regular$ cat /opt/busybox/busybox-1.33.2/include/config/feature/mdev/load/GIST
Yahaha, you found me!
The next clue is in: /usr/lib/python3/dist-packages/future/moves/test/__pycache__

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Gyre-Pagella/Monospace/Regular$ cd /opt/busybox/busybox-1.33.2/include/config/feature/mdev/load
hacker@commands~an-epic-filesystem-quest:/opt/busybox/busybox-1.33.2/include/config/feature/mdev/load$ cd /usr/lib/python3/dist-packages/future/moves/test/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/future/moves/test/__pycache__$ ls
SECRET  __init__.cpython-38.pyc  support.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/future/moves/test/__pycache__$ cat SECRET
Lucky listing!
The next clue is in: /opt/radare2/shlr/zip/zlib

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/future/moves/test/__pycache__$ cd /opt/radare2/shlr/zip/zlib
hacker@commands~an-epic-filesystem-quest:/opt/radare2/shlr/zip/zlib$ ls
ChangeLog   compress.d  deflate.h  gzlib.o    infback.d   inflate.d   trees.c    zlib.h
HINT        compress.o  deflate.o  gzread.c   infback.o   inflate.h   trees.d    zutil.c
Makefile    crc32.c     gzclose.c  gzread.d   inffast.c   inflate.o   trees.h    zutil.d
README      crc32.d     gzclose.d  gzread.o   inffast.d   inftrees.c  trees.o    zutil.h
adler32.c   crc32.h     gzclose.o  gzwrite.c  inffast.h   inftrees.d  uncompr.c  zutil.o
adler32.d   crc32.o     gzguts.h   gzwrite.d  inffast.o   inftrees.h  uncompr.d
adler32.o   deflate.c   gzlib.c    gzwrite.o  inffixed.h  inftrees.o  uncompr.o
compress.c  deflate.d   gzlib.d    infback.c  inflate.c   libr_z.a    zconf.h
hacker@commands~an-epic-filesystem-quest:/opt/radare2/shlr/zip/zlib$ cat HINT
Great sleuthing!
The next clue is in: /opt/busybox/busybox-1.33.2/include/config/feature/install

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/opt/radare2/shlr/zip/zlib$ cd /opt/busybox/busybox-1.33.2/include/config/feature/install
hacker@commands~an-epic-filesystem-quest:/opt/busybox/busybox-1.33.2/include/config/feature/install$ ls -lah
total 20K
drwxr-xr-x 1 root   root   4.0K Oct  8 21:45 .
drwxr-xr-x 1 root   root   4.0K Sep  6 16:26 ..
-rw-r--r-- 1 hacker hacker  111 Oct  8 21:45 MESSAGE
drwxr-xr-x 2 root   root   4.0K Sep  6 16:26 long
hacker@commands~an-epic-filesystem-quest:/opt/busybox/busybox-1.33.2/include/config/feature/install$ cat MESSAGE
Lucky listing!
The next clue is in: /usr/local/lib/python3.8/dist-packages/angr/state_plugins/heap/__pycache__
hacker@commands~an-epic-filesystem-quest:/opt/busybox/busybox-1.33.2/include/config/feature/install$ cd /usr/local/lib/python3.8/dist-packages/angr/state_plugins/heap/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/angr/state_plugins/heap/__pycache__$ ls
MEMO                      heap_brk.cpython-38.pyc       heap_ptmalloc.cpython-38.pyc
__init__.cpython-38.pyc   heap_freelist.cpython-38.pyc  utils.cpython-38.pyc
heap_base.cpython-38.pyc  heap_libc.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/angr/state_plugins/heap/__pycache__$ cat MEMO
Great sleuthing!
The next clue is in: /opt/gef/tests/binaries

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/angr/state_plugins/heap/__pycache__$ cat /opt/gef/tests/binaries
cat: /opt/gef/tests/binaries: Is a directory
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/angr/state_plugins/heap/__pycache__$ cd /opt/gef/tests/binaries
ssh-entrypoint: INSIGHT-TRAPPED: Permission denied
hacker@commands~an-epic-filesystem-quest:/opt/gef/tests/binaries$ ls
ssh-entrypoint: INSIGHT-TRAPPED: Permission denied
INSIGHT-TRAPPED       class.cpp               heap-multiple-heaps.c  nested2.c
Makefile              collision.c             heap-non-main.c        pattern.c
bss.c                 default.c               heap-tcache.c          pcustom.c
canary.c              format-string-helper.c  heap.c                 utils.h
checksec-no-canary.c  heap-analysis.c         memwatch.c
checksec-no-nx.c      heap-bins.c             mmap-known-address.c
checksec-no-pie.c     heap-fastbins.c         nested.c
ssh-entrypoint: INSIGHT-TRAPPED: Permission denied
hacker@commands~an-epic-filesystem-quest:/opt/gef/tests/binaries$ cat INSIGHT-TRAPPED
ssh-entrypoint: INSIGHT-TRAPPED: Permission denied
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{I3eQW2EY7owVtPPPmknKZrquPVv.dljM4QDL1YDN1czW}

```
# Making directories
```bash
hacker@commands~making-directories:~$ cd /
hacker@commands~making-directories:/$ ls
bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@commands~making-directories:/$ mkdir -p /tmp/pwn
hacker@commands~making-directories:/$ cd tmp/pwn/
hacker@commands~making-directories:/tmp/pwn$ ls
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{o20biGLnSvf7kU_iH8TjskEvqq3.dFzM4QDL1YDN1czW}

```

# Find Command

```bash
$ find / -name "flag" > poss
$ cat poss
/usr/local/share/xml/entities/flag
/usr/local/share/radare2/5.9.5/flag
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/opt/radare2/libr/flag
/nix/store/pmvk2bk4p550w182rjfm529kfqddnvh3-python3.11-pwntools-4.12.0/lib/python3.11/site-packages/pwnlib/flag
/nix/store/1yagn5s8sf7kcs2hkccgf8d0wxlrv5sz-radare2-5.9.0/share/radare2/5.9.0/flag
$ cat /usr/local/share/xml/entities/flag
pwn.college{Q1Ucid5F9neD-ssCYyjSIqtbnOT.dJzM4QDL1YDN1czW}
```

# Linking

```bash
hacker@commands~linking-files:~$ ln -s /flag ~/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{4J5K_Ly5h4nFuHl99oP-_rWMBJ5.dlTM1UDL1YDN1czW}
```
