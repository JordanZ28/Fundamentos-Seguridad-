
# Objetivo 
Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/27/fixme1.py)
# Solución 
```

jordanza-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/27/fixme1.py                                       
--2024-03-01 05:28:58--  https://artifacts.picoctf.net/c/27/fixme1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.16, 3.160.22.43, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 837 [application/octet-stream]
Saving to: 'fixme1.py'

fixme1.py                                                  100%[======================================================================================================================================>]     837  --.-KB/s    in 0s      

2024-03-01 05:28:58 (485 MB/s) - 'fixme1.py' saved [837/837]

jordanza-picoctf@webshell:~$ ls
Addadshashanammu  Addadshashanammu.zip  Addadshashanammu.zip.1  README.txt  code.py  codebook.txt  convertme.py  file  fixme1.py  flag  static  warm
jordanza-picoctf@webshell:~$ python fixme1.py
  File "/home/jordanza-picoctf/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
jordanza-picoctf@webshell:~$ nano fi
file       fixme1.py  
jordanza-picoctf@webshell:~$ nano fixme1.py 
jordanza-picoctf@webshell:~$ python fixme1.py
  File "/home/jordanza-picoctf/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
jordanza-picoctf@webshell:~$ nano fixme1.py 
jordanza-picoctf@webshell:~$ python fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}
jordanza-picoctf@webshell:~$ ^C
```

# Notas 
Descargamos el programa y le ejecutamos con el comando python fixme1.py y al ejecutarlo nos marca error en la linea 20 que al ver el codigo podemos ver que tiene un espacio de mas en la linea 20 antes del print asi que con el comando nano podemos editar el codigo y obtener la bander a

