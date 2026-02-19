# Bandit Level 8 -> Level 9

## Objetivo
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once



### Datos de acceso
user: bandit8
password: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc 
address: bandit.labs.overthewire.org
port: 2220

### Teoría
sort: Ordena las líneas alfabéticamente. Esto agrupa todas las palabras repetidas (ej. pone todas las "password123" una tras otra).

uniq -u: La flag -u (unique) es la más importante aquí. A diferencia del uniq normal (que solo quita duplicados), el parámetro -u le dice al sistema: "Muéstrame únicamente las líneas que NO se repitieron nunca".

### Solución

ssh -p 2220 bandit8@bandit.labs.overthewire.org

bandit8@bandit:~$ cat data.txt | sort | uniq -u
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM                                                                                    
bandit8@bandit:~$  

**Flag: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM**

