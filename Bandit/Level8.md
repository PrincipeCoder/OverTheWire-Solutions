# Bandit Level 7 -> Level 8

## Objetivo
The password for the next level is stored in the file data.txt next to the word millionth



### Datos de acceso
user: bandit7
password: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj 
address: bandit.labs.overthewire.org
port: 2220

### Solución
ssh -p 2220 bandit7@bandit.labs.overthewire.org

bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ head data.txt 
peroration's    a9aUjV0EDU4p4oiy1MECWUbZx67GqDIN
benefactress    J5Qj0V9NvcXtjf5i9pWCDcWwqLpXrF3j
Lubbock GjfK8Mo1FyG2NZs0KdBMaJlCLgTIAJA9
dispossession's dIOOFe0Cfv2NkSTwQl43yRAerDOWTvpH
libidos vTCZdLjTG02C1vbuJFxG2vqpvmIllv8Z
flailed 3uZIT1mgZe2G4HjnxlL8xQ9dx2sUsmVc
cyclone's       cpqxy7fYUJY5Ng5couwcih5GU285irTN
curt    dz9MYBvtkGaAsQmOs5r964zm0c3OAvQY
amphitheater's  RG06ahKLryAUEdZbFAIqDU2DvrKq9lYV
infrequent      prgVPbuC3H3BHxzhsybUplbyVRdljiKI
bandit7@bandit:~$ cat data.txt | grep millionth
millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
bandit7@bandit:~$ 


**Flag: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc**
