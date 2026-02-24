# Bandit Level 14 -> Level 15

## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

### Datos de acceso
user: bandit14
password: MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS 
address: bandit.labs.overthewire.org
port: 2220

### Teoria
Localhost is a hostname and its IP address is ‘127.0.0.1’. It is used to access network services on the same device that is running these services.

nc or netcat is a command that allows to read and write data over a network connection. It can be used for TCP and UDP connections. To connect to a service (as client) on a network the command syntax is the following: nc <host> <port>. To create a server that listens to incoming packets, the command looks like this: nc -l <port>.


### Solución
<pre>
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220

bandit14@bandit:~$ ls
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
bandit14@bandit:~$ nc localhost 30000
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
Correct!
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

<pre>


**Flag: 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo**