# Bandit Level 1 -> Level 2

## Objetivo
The password for the next level is stored in a file called - located in the home directory

### Datos de acceso
user: bandit1
password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If 
address: bandit.labs.overthewire.org
port: 2220

### Solución
<pre>
ssh -p 2220 bandit1@bandit.labs.overthewire.org

bandit1@bandit:~$ ls
-
bandit1@bandit:~$ ls -la
total 24
-rw-r-----   1 bandit2 bandit1   33 Oct 14 09:26 -
drwxr-xr-x   2 root    root    4096 Oct 14 09:26 .
drwxr-xr-x 150 root    root    4096 Oct 14 09:29 ..
-rw-r--r--   1 root    root     220 Mar 31  2024 .bash_logout
-rw-r--r--   1 root    root    3851 Oct 14 09:19 .bashrc
-rw-r--r--   1 root    root     807 Mar 31  2024 .profile
bandit1@bandit:~$ cat ./-
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
bandit1@bandit:~$ 
<pre>

**Flag: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx**