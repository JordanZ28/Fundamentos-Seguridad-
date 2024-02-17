# Retos Bandit 
# Bandido Nivel 4 → Nivel 5

# Objetivo 
La contraseña para el siguiente nivel se almacena en el único archivo legible por humanos en el directorio **inhere**. Consejo: si tu terminal está desordenado arriba, pruebe el comando "reiniciar".

# Datos de acceso al nivel 
bandit4
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

# Solucion
```
bandit4@bandit:~/inhere$
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ file ./-file00
./-file00: data
bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ cat ./-file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
bandit4@bandit:~/inhere$
```
# Notas 
- * sirve como un comodin que a la hora de usarlo con un cat nos muestra el contenido de todos los archivos 
   file nos ayuda para saber el tipo de archivo 
   

