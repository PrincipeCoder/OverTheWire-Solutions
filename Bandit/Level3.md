# Bandit Level 2 -> Level 3

## Objetivo
The password for the next level is stored in a file called --spaces in this filename-- located in the home directory

### Datos de acceso
user: bandit2
password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx 
address: bandit.labs.overthewire.org
port: 2220

### Solución
<pre>
ssh -p 2220 bandit2@bandit.labs.overthewire.org

bandit2@bandit:~$ ls
--spaces in this filename--
bandit2@bandit:~$ file ./--spaces\ in\ this\ filename-- 
./--spaces in this filename--: ASCII text
bandit2@bandit:~$ cat ./--spaces\ in\ this\ filename-- 
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
bandit2@bandit:~$ 
<pre>

**Flag: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx**