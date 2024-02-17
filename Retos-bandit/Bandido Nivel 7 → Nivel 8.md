# Retos Bandit 
# Bandido Nivel 7 → Nivel 8

# Objetivo 
La contraseña para el siguiente nivel se almacena en el archivo **data.txt** junto a la palabra **millonésimo**

# Datos de acceso al nivel 
bandit7
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
# Solución 
```
bandit7@bandit:~$ ls -la
total 4108
drwxr-xr-x  2 root    root       4096 Oct  5 06:19 .
drwxr-xr-x 70 root    root       4096 Oct  5 06:20 ..
-rw-r--r--  1 root    root        220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root    root       3771 Jan  6  2022 .bashrc
-rw-r-----  1 bandit8 bandit7 4184396 Oct  5 06:19 data.txt
-rw-r--r--  1 root    root        807 Jan  6  2022 .profile
bandit7@bandit:~$ grep  millionth data.txt
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit7@bandit:~$
```

# Notas 
WC -l Cuenta las líneas de un archivo de texto 
head muestra las primeras 10 líneas
tail muestra las ultimas 10 líneas 
grep filtra lineas en base a un patrón 
