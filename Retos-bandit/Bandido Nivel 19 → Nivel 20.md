# Retos Bandit 
# Bandido Nivel 19 → Nivel 20

# Objetivo 
Para obtener acceso al siguiente nivel, debe usar el binario setuid en el directorio de inicio. Ejecútalo sin argumentos para saber cómo para usarlo. La contraseña para este nivel se puede encontrar en el place (/etc/bandit_pass), después de haber utilizado el binario setuid.

# Datos de acceso al nivel 
bandit19
ssh -l bandit19 bandit.labs.overthewire.org -p 2220
# Solución 
```
bandit19@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Oct  5 06:19 .
drwxr-xr-x 70 root     root      4096 Oct  5 06:20 ..
-rwsr-x---  1 bandit20 bandit19 14876 Oct  5 06:19 bandit20-do
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit19@bandit:~$
```

# Notas 
Aqui el archivo bandit20-do tiene permisos del sistema donde se tiene privilegios 
