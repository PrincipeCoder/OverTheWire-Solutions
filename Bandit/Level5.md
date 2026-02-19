# Bandit Level 3 -> Level 4

## Objetivo
The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.


### Datos de acceso
user: bandit4
password: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ 
address: bandit.labs.overthewire.org
port: 2220

### Teoría
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file00

Tipo de archivo y Permisos (-rw-r-----):
* Primer carácter: Indica el tipo. - es un archivo regular, d un directorio, l un enlace simbólico
* Tríadas de permisos: Se dividen en Dueño (User), Grupo (Group) y Otros (Others).
    * rw-: El dueño (bandit5) tiene lectura ($r$) y escritura ($w$).
    * r--: El grupo (bandit4) solo tiene lectura ($r$).
    * ---: Otros no tienen ningún permiso.
* Enlaces duros (1): El número de enlaces físicos que apuntan al inodo del archivo.
* Propietario (bandit5): El usuario que posee el archivo.
* Grupo (bandit4): El grupo asociado al archivo. Los usuarios en este grupo heredan los permisos de la segunda tríada.
* Tamaño (33): El tamaño del archivo en bytes.
* Timestamp (Oct 14 09:26): Fecha y hora de la última modificación.
* Nombre del archivo (-file00): El identificador del archivo. Ojo: El guion inicial en el nombre tiene implicaciones técnicas en la terminal.


### Solución
<pre>
ssh -p 2220 bandit4@bandit.labs.overthewire.org

bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere/
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ ls -l 
total 40
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file00
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file01
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file02
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file03
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file04
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file05
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file06
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file07
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file08
-rw-r----- 1 bandit5 bandit4 33 Oct 14 09:26 -file09
bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: OpenPGP Public Key
./-file02: OpenPGP Public Key
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ 
bandit4@bandit:~/inhere$ cat ./-file07
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
bandit4@bandit:~/inhere$ 
<pre>

**Flag: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw**
