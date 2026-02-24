# Bandit Level 11 -> Level 12

## Objetivo
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions


### Datos de acceso
user: bandit11
password: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr 
address: bandit.labs.overthewire.org
port: 2220

### Teoria
ROT 13
ROT13 significa "Rotar 13 posiciones". Es un algoritmo que reemplaza cada letra del alfabeto por la letra que está 13 posiciones por delante.Como el alfabeto latino estándar tiene 26 letras, la magia del ROT13 es que es simétrico o recíproco: si aplicas ROT13 dos veces a la misma palabra, regresas al texto original 13 + 13 = 26.

Comando en Linux: En Bandit o cualquier terminal Linux, no necesitas instalar nada. Usamos el comando tr (translate):
<pre>
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
<pre>

### Solución
<pre>
ssh -p 2220 bandit11@bandit.labs.overthewire.org

bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt 
Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
bandit11@bandit:~$ 

<pre>


**Flag: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4**