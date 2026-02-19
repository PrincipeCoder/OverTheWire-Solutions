# Bandit Level 3 -> Level 4

## Objetivo
The password for the next level is stored in a hidden file in the inhere directory.

### Datos de acceso
user: bandit3
password: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx 
address: bandit.labs.overthewire.org
port: 2220

### Solución
<pre>
ssh -p 2220 bandit3@bandit.labs.overthewire.org

bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd ./inhere/
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -a
.  ..  ...Hiding-From-You
bandit3@bandit:~/inhere$ file ./...Hiding-From-You 
./...Hiding-From-You: ASCII text
bandit3@bandit:~/inhere$ cat ./...Hiding-From-You 
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
bandit3@bandit:~/inhere$ 
<pre>

**Flag: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ**