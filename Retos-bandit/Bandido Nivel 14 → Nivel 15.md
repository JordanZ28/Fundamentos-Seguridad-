# Retos Bandit 
# Bandido Nivel 14 → Nivel 15

# Objetivo 
La contraseña para el siguiente nivel se puede recuperar enviando el archivo contraseña del nivel actual al **puerto 30000 en localhost**.

# Datos de acceso al nivel 
bandit14
ssh -l bandit14 bandit.labs.overthewire.org -p 2220
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
# Solución 
```
bandit14@bandit:~$ nc localhost 4040
hola quien eres
chapito sanchez
ok
10
^C
bandit14@bandit:~$ nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

```

# Notas 
nc localhost y numero de puerto podemos entrar en una conexión como un canal de chateo donde podemos enviar mensajes o documentación  

# Referencias 