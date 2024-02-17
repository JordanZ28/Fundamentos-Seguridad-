# Retos Bandit 
# Bandido Nivel 2 → Nivel 3

# Objetivo 
La contraseña para el siguiente nivel se almacena en un archivo llamado **espacios en este nombre de archivo ubicado en** el directorio de inicio

# Datos de acceso al nivel 
bandit2
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi


# Solucion 
```
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat spaces in this filename
cat: spaces: No such file or directory
cat: in: No such file or directory
cat: this: No such file or directory
cat: filename: No such file or directory
bandit2@bandit:~$ cat spaces\in\this\filename
cat: spacesinthisfilename: No such file or directory
bandit2@bandit:~$ cat spaces\ in\ this\ filename
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$ cat "spaces in this filename"
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$
```

# Notas 