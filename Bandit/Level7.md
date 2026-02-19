# Bandit Level 6 -> Level 7

## Objetivo
The password for the next level is stored somewhere on the server and has all of the following properties:

owned by user bandit7
owned by group bandit6
33 bytes in size

### Datos de acceso
user: bandit6
password: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG 
address: bandit.labs.overthewire.org
port: 2220
### Teoria
En Linux, los programas tienen dos canales de salida principales:

Stdout (Standard Output - Descriptor 1): Donde sale el resultado exitoso del comando.

Stderr (Standard Error - Descriptor 2): Donde salen los mensajes de error (como el "Permission denied").

2: Representa el canal de errores (Stderr).

>: Es el operador de redirección.

/dev/null: Es el "agujero negro" de Linux. Todo lo que envíes ahí desaparece y no se muestra en la terminal.
### Solución
<pre>
ssh -p 2220 bandit6@bandit.labs.overthewire.org

bandit6@bandit:~$ find / -type f -size 33c -user bandit7 -group bandit6 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
bandit6@bandit:~$ 
<pre>


**Flag: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj**
