# Retos Bandit 
# Bandido Nivel 0 → Nivel 1

# Objetivo 
La contraseña para el siguiente nivel se almacena en un archivo llamado **Léame** ubicado en el directorio de inicio. Utilice esta contraseña para iniciar sesión en bandit1 usando SSH. Cada vez que encuentres una contraseña para un nivel, usa SSH (en el puerto 2220) para iniciar sesión en ese nivel y continuar el juego.
# Datos de acceso al nivel 
Dirección :**bandit.labs.overthewire.org**
Usuario: bandit0
Contraseña:bandit1 
Puerto: 2220
# Solución 
ls 
cat readme
Contraseña :NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

``
```
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
bandit0@bandit:~$
```
# Notas 
ls Sirve para en listar  archivos 
cat Sive para mostrar el contenido de un archivo 