# Bandit Level 10 -> Level 11

## Objetivo
The password for the next level is stored in the file data.txt, which contains base64 encoded data

### Datos de acceso
user: bandit10
password: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey 
address: bandit.labs.overthewire.org
port: 2220

### Teoria
Base64 utiliza un alfabeto de 64 caracteres: las letras de la A-Z (mayúsculas y minúsculas), los números 0-9, y los símbolos + y /. El carácter = se utiliza como relleno (padding) al final de la cadena si el mensaje original no tiene el tamaño necesario.
¿Cómo funciona matemáticamente?

Toma los datos binarios y los divide en grupos de 24 bits.

Esos 24 bits se dividen en 4 grupos de 6 bits cada uno.

Cada grupo de 6 bits corresponde a un valor decimal (0-63).

Ese valor se traduce al carácter correspondiente en la Tabla Base64.

### Solución
<pre>
ssh -p 2220 bandit10@bandit.labs.overthewire.org

bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ head data.txt 
VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJXbnBOVmozcVJyCg==
bandit10@bandit:~$ base64 --help
Usage: base64 [OPTION]... [FILE]
Base64 encode or decode FILE, or standard input, to standard output.

With no FILE, or when FILE is -, read standard input.

Mandatory arguments to long options are mandatory for short options too.
  -d, --decode          decode data
  -i, --ignore-garbage  when decoding, ignore non-alphabet characters
  -w, --wrap=COLS       wrap encoded lines after COLS character (default 76).
                          Use 0 to disable line wrapping
      --help        display this help and exit
      --version     output version information and exit

The data are encoded as described for the base64 alphabet in RFC 4648.
When decoding, the input may contain newlines in addition to the bytes of
the formal base64 alphabet.  Use --ignore-garbage to attempt to recover
from any other non-alphabet bytes in the encoded stream.

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Full documentation <https://www.gnu.org/software/coreutils/base64>
or available locally via: info '(coreutils) base64 invocation'
bandit10@bandit:~$ base64 -d data.txt 
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
bandit10@bandit:~$ 


<pre>


**Flag: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr**