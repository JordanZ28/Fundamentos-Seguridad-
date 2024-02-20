# Retos Bandit 
# Bandido Nivel 11 → Nivel 12

# Objetivo
La contraseña para el siguiente nivel se almacena en el archivo **data.txt**, donde todas las letras minúsculas (a-z) y mayúsculas (A-Z) han sido Girado en 13 posiciones
# Datos de acceso al nivel 
bandit11
ssh -l bandit11 bandit.labs.overthewire.org -p 2220
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
# Solución 
```
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M]
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
bandit11@bandit:~$
```
# Notas 
Rot 13 es un cifrado simple de sustitución de letras que reemplaza una letra
# Referencias 
[ROT13 - Wikipedia, la enciclopedia libre](https://en.wikipedia.org/wiki/ROT13)
