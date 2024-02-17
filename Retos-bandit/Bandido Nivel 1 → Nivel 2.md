# Retos Bandit 
# Bandido Nivel 1 → Nivel 2

# Objetivo 
La contraseña para el siguiente nivel se almacena en un archivo llamado **-** ubicado en el directorio de inicio
# Datos de acceso al nivel 
bandit1
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

# Solucion 
ssh -l bandit1 bandit.labs.overthewire.org -p 2220
```
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$
```
# Notas  
Si nos encontramos un Archivo que comience con un -  tendremos que poner un ./ para poder abrir el archivo 


