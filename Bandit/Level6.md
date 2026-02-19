# Bandit Level 5 -> Level 6

## Objetivo
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

human-readable
1033 bytes in size
not executable

### Datos de acceso
user: bandit5
password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw 
address: bandit.labs.overthewire.org
port: 2220
### Teoria
El comando find permite filtrar archivos basándose en sus atributos (metadatos) sin necesidad de abrirlos. 

El comando find sigue esta estructura: find [ruta] [expresión] [acción].

1. Búsqueda por Propiedades del Archivo
-name "patrón": Busca por nombre exacto. Usa -iname para ignorar mayúsculas/minúsculas.
-type [letra]: Filtra por tipo de objeto.
    f: Archivo regular.
    d: Directorio.
    l: Enlace simbólico.
-size [+/-]n[cwbkMG]: Busca por tamaño.
    100c: Exactamente 100 bytes.
    +10M: Más de 10 Megabytes.
    -1k: Menos de 1 Kilobyte.
2. Búsqueda por Tiempo (Forense)
    -mtime [+/-]n: Modificado hace $n$ días.
    -atime [+/-]n: Accedido hace $n$ días.
    -mmin [+/-]n: Modificado hace $n$ minutos (útil para ver qué cambió un atacante hace poco).
3. Búsqueda por Permisos y Dueños
-user [nombre]: Archivos que pertenecen a un usuario específico.
-group [nombre]: Archivos que pertenecen a un grupo
-perm [modo]: Busca permisos específicos (ej. -perm 777 o -perm /u=s para SUID).

### Solución
<pre>
ssh -p 2220 bandit5@bandit.labs.overthewire.org

bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere/
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere02  maybehere04  maybehere06  maybehere08  maybehere10  maybehere12  maybehere14  maybehere16  maybehere18
maybehere01  maybehere03  maybehere05  maybehere07  maybehere09  maybehere11  maybehere13  maybehere15  maybehere17  maybehere19
bandit5@bandit:~/inhere$ ls -la
total 88
drwxr-x--- 22 root bandit5 4096 Oct 14 09:26 .
drwxr-xr-x  3 root root    4096 Oct 14 09:26 ..
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere00
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere01
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere02
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere03
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere04
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere05
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere06
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere07
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere08
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere09
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere10
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere11
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere12
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere13
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere14
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere15
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere16
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere17
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere18
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere19
bandit5@bandit:~/inhere$ find . -type f -size 1033c ! -executable
./maybehere07/.file2
bandit5@bandit:~/inhere$ find . -type f -size 1033c ! -executable | cat
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
bandit5@bandit:~/inhere$ 
<pre>

**Flag: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG**