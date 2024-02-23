# Retos Bandit 
# Bandido Nivel 20 → Nivel 21 

# Objetivo 
Hay un binario setuid en el directorio de inicio que hace el siguiente: realiza una conexión con localhost en el puerto que especifique como argumento de línea de comandos. A continuación, lee una línea de texto de la conexión y la compara con la contraseña en el nivel anterior (Bandido20). Si la contraseña es correcta, transmitirá el contraseña para el siguiente nivel (bandit21).

**NOTA:** Intente conectarse a su propio demonio de red para ver si funciona como piensas
# Datos de acceso al nivel 
bandit20
ssh -l bandit20 bandit.labs.overthewire.org -p 2220
# Solución 

```
bandit20@bandit:~$ ls
suconnect
bandit20@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Oct  5 06:19 .
drwxr-xr-x 70 root     root      4096 Oct  5 06:20 ..
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
-rwsr-x---  1 bandit21 bandit20 15600 Oct  5 06:19 suconnect
bandit20@bandit:~$ ./suconnect
Usage: ./suconnect <portnumber>
This program will connect to the given port on localhost using TCP. If it receives the correct password from the other side, the next password is transmitted back.
bandit20@bandit:~$ nc -lnvp 2802 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[1] 3064901
bandit20@bandit:~$ Listening on 0.0.0.0 2802

bandit20@bandit:~$ jobs
[1]+  Running                 nc -lnvp 2802 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
bandit20@bandit:~$ ./suconnect
Usage: ./suconnect <portnumber>
This program will connect to the given port on localhost using TCP. If it receives the correct password from the other side, the next password is transmitted back.
bandit20@bandit:~$ ./suconnect 2802
Connection received on 127.0.0.1 37926
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
[1]+  Done                    nc -lnvp 2802 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$ jobs
bandit20@bandit:~$




```

![[Pasted image 20240221125921.png]]
# Notas 
Tmux es un multiplexor terminal. Te permite cambiar fácilmente entre varios programas en un terminal, desconéctelos (siguen ejecutándose en segundo plano) y Vuelva a conectarlos a un terminal diferente.
Comandos que se pueden utilizar para crear terminales, movimiento y el tamaño 
ctrl + b  ""          
ctrl +b   flechas   
ctrl +b   espacio 
ctrl +b % 