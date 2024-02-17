# Retos Bandit 
# Bandido Nivel 3 → Nivel 4

# Objetivo 

La contraseña para el siguiente nivel se almacena en un archivo oculto en el directorio **inhere**.
# Datos de acceso al nivel 
bandit3
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

# Solución 
```
bandit3@bandit:~$ cd
bandit3@bandit:~$ pwd
/home/bandit3
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -la
total 12
drwxr-xr-x 2 root    root    4096 Oct  5 06:19 .
drwxr-xr-x 3 root    root    4096 Oct  5 06:19 ..
-rw-r----- 1 bandit4 bandit3   33 Oct  5 06:19 .hidden
bandit3@bandit:~/inhere$ cat .hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
bandit3@bandit:~/inhere$
```
# Notas 
ls -la Muestra todos los archivos en formato largo también incluye los archivos ocultos 