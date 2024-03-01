
# Objetivo 

Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/4/fixme2.py)
# Solución 
```
jordanza-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/4/fixme2.py
--2024-03-01 17:48:02--  https://artifacts.picoctf.net/c/4/fixme2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.43, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1029 (1.0K) [application/octet-stream]
Saving to: 'fixme2.py'

fixme2.py                                                  100%[======================================================================================================================================>]   1.00K  --.-KB/s    in 0s      

2024-03-01 17:48:02 (661 MB/s) - 'fixme2.py' saved [1029/1029]

jordanza-picoctf@webshell:~$ ls
Addadshashanammu  Addadshashanammu.zip  Addadshashanammu.zip.1  README.txt  code.py  codebook.txt  convertme.py  file  fixme1.py  fixme2.py  flag  static  strings  warm
jordanza-picoctf@webshell:~$ python fixme2.py  
  File "/home/jordanza-picoctf/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
jordanza-picoctf@webshell:~$ nano fixme2.py
jordanza-picoctf@webshell:~$ python fixme2.py 
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}
jordanza-picoctf@webshell:~$ 



```

# Notas 
Descargamos el archivo lo corremos y identificamos el error que se encuentra en la linea 22 que es = que en este caso debería de ir de la siguiente manera ==

