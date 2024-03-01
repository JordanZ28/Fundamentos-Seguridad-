
# Objetivo 
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/10/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/10/level1.flag.txt.enc) in the same directory too.

# Solución 
```
jordanza-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/10/level1.py
--2024-03-01 17:59:02--  https://artifacts.picoctf.net/c/10/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.43, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: 'level1.py'

level1.py                                                  100%[======================================================================================================================================>]     876  --.-KB/s    in 0s      

2024-03-01 17:59:02 (241 MB/s) - 'level1.py' saved [876/876]

jordanza-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/10/level1.flag.txt.enc
--2024-03-01 17:59:30--  https://artifacts.picoctf.net/c/10/level1.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.43, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: 'level1.flag.txt.enc'

level1.flag.txt.enc                                        100%[======================================================================================================================================>]      30  --.-KB/s    in 0s      

2024-03-01 17:59:30 (1.45 MB/s) - 'level1.flag.txt.enc' saved [30/30]

jordanza-picoctf@webshell:~$ ls
Addadshashanammu  Addadshashanammu.zip  Addadshashanammu.zip.1  README.txt  code.py  codebook.txt  convertme.py  file  fixme1.py  fixme2.py  flag  level1.flag.txt.enc  level1.py  static  strings  warm
jordanza-picoctf@webshell:~$ nano level1.py
jordanza-picoctf@webshell:~$ nano level1.flag.txt.enc 
jordanza-picoctf@webshell:~$ nano level1.py
jordanza-picoctf@webshell:~$ python level1.py 
Please enter correct password for flag: 691d
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_56891419}


```


# Notas 
Se descargan dos archivos  se inspeccionan para poder obtener la contraseña que nos pide el codigo paython para poder obtener la bandera 


