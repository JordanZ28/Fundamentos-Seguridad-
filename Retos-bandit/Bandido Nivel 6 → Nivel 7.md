# Retos Bandit 
# Bandido Nivel 6 → Nivel 7

# Objetivo 
La contraseña para el siguiente nivel se almacena **en algún lugar de la carpeta server** y tiene todas las propiedades siguientes:

- Propiedad del usuario Bandit7
- Propiedad del grupo Bandit6
- 33 bytes de tamaño

# Datos de acceso al nivel 
bandit6
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
# Solución 
```
bandit6@bandit:~$ ls
bandit6@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Oct  5 06:19 .
drwxr-xr-x 70 root root 4096 Oct  5 06:20 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit6@bandit:~$ find  / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
bandit6@bandit:~$
```

# Notas 
find 
-user nos permite especificar el usuario 
-group permite especificar el grup 
si agregamos al final de un comando el 2>/dev/null envía la salida de error al dispositivo null o que no aparezca los errores en la pantallas 

