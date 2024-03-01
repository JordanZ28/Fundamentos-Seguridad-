
# Objetivo 


# Solución 
```
jordanza-picoctf@webshell:~$ 
jordanza-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/code.py
--2024-03-01 05:06:42--  https://artifacts.picoctf.net/c/3/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.43, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py                                                    100%[======================================================================================================================================>]   1.25K  --.-KB/s    in 0s      

2024-03-01 05:06:42 (37.2 MB/s) - 'code.py' saved [1278/1278]

jordanza-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/codebook.txt
--2024-03-01 05:07:03--  https://artifacts.picoctf.net/c/3/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.16, 3.160.22.43, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt                                               100%[======================================================================================================================================>]      27  --.-KB/s    in 0s      

2024-03-01 05:07:03 (1.50 MB/s) - 'codebook.txt' saved [27/27]

jordanza-picoctf@webshell:~$ ls
Addadshashanammu  Addadshashanammu.zip  Addadshashanammu.zip.1  README.txt  code.py  codebook.txt  flag  static  warm
jordanza-picoctf@webshell:~$ python3 code.py
picoCTF{c0d3b00k_455157_197a982c}
jordanza-picoctf@webshell:~$ 
```

# Notas 

Descargamos los dos documentos en la terminal al tenerlos corremos el code.py con el siguiente comando python3 code.py que nos dejara obtener la contraseña 
