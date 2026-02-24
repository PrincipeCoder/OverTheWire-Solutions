# Bandit Level 9 -> Level 10

## Objetivo
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

### Datos de acceso
user: bandit9
password: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM 
address: bandit.labs.overthewire.org
port: 2220

### Teoria
El comando strings escanea archivos binarios y extrae las secuencias de caracteres imprimibles (texto legible) que tengan una longitud mínima (por defecto 4 caracteres).

### Solución
<pre>
ssh -p 2220 bandit9@bandit.labs.overthewire.org

bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ strings data.txt | grep "=="
========== the
========== password
f\Z'========== is
========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
bandit9@bandit:~$ 
<pre>

**Flag: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey**
