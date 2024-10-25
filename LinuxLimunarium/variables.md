# Printing variables
```bash
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{Ec9ULdqnQ8jjiHkc7EXAD7t2Lmf.ddTN1QDL1YDN1czW}
```
# Setting variables
```bash
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{MM6nunwg-htDLkLPRFwqWs2Y63L.dlTN1QDL1YDN1czW}
```

# Multi word variables
```bash
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{ITOLkjp0BJGGxPd6yh2dEVpFoJg.dBjN1QDL1YDN1czW}
```
# Exporting variables
```bash
hacker@variables~exporting-variables:~$ PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ export PWN
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great
job! Here is your flag:
pwn.college{0VUhzC7EZXuOCmJOnhyGqNM2UuS.dJjN1QDL1YDN1czW}
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
```
# env command
```bash
hacker@variables~printing-exported-variables:~$ env | grep pwn
FLAG=pwn.college{cp7lqvDI6B5jU8wS0vBIGyluQCz.dhTN1QDL1YDN1czW}
```

# Storing Command output
```bash
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out
and submit it!
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{MymeyhbjsCb_ckuZFAf57mcNluh.dVzN0UDL1YDN1czW}
```

# Reading input
```bash
hacker@variables~reading-input:~$ read -p "INPUT: " PWN
INPUT: COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{QeKXQ_Jd6ejC2QDKGxHI5k09G3n.dhzN1QDL1YDN1czW}
```

# Reading files
```bash
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{8WfqfH78ZoiqFZ6ucTiGmMclj0u.dBjM4QDL1YDN1czW}
```
