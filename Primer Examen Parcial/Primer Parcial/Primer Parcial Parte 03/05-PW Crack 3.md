
# Objetivo 
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/16/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/16/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/16/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

# Solución
```
jordanza-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/16/level3.py
--2024-03-01 18:42:21--  https://artifacts.picoctf.net/c/16/level3.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.128, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1337 (1.3K) [application/octet-stream]
Saving to: 'level3.py'

level3.py                                                  100%[======================================================================================================================================>]   1.31K  --.-KB/s    in 0s      

2024-03-01 18:42:21 (442 MB/s) - 'level3.py' saved [1337/1337]

jordanza-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/16/level3.flag.txt.enc
--2024-03-01 18:42:34--  https://artifacts.picoctf.net/c/16/level3.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.16, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level3.flag.txt.enc'

level3.flag.txt.enc                                        100%[======================================================================================================================================>]      31  --.-KB/s    in 0s      

2024-03-01 18:42:34 (13.7 MB/s) - 'level3.flag.txt.enc' saved [31/31]

jordanza-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/16/level3.hash.bin
--2024-03-01 18:42:51--  https://artifacts.picoctf.net/c/16/level3.hash.bin
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.128, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level3.hash.bin'

level3.hash.bin                                            100%[======================================================================================================================================>]      16  --.-KB/s    in 0s      

2024-03-01 18:42:51 (5.93 MB/s) - 'level3.hash.bin' saved [16/16]

jordanza-picoctf@webshell:~$ ls 
Addadshashanammu      Addadshashanammu.zip.1  code.py       convertme.py  fixme1.py  flag                 level1.py            level2.py            level3.hash.bin  static   warm
Addadshashanammu.zip  README.txt              codebook.txt  file          fixme2.py  level1.flag.txt.enc  level2.flag.txt.enc  level3.flag.txt.enc  level3.py        strings
jordanza-picoctf@webshell:~$ nano level3.py
jordanza-picoctf@webshell:~$ nano level3.flag.txt.enc 
jordanza-picoctf@webshell:~$ nano level3.hash.bin     
jordanza-picoctf@webshell:~$ nano level3.py
jordanza-picoctf@webshell:~$ python level3.py
Please enter correct password for flag: 3ac8
That password is incorrect
jordanza-picoctf@webshell:~$ python level3.py
Please enter correct password for flag: 4b17
That password is incorrect
jordanza-picoctf@webshell:~$ python level3.py  
Please enter correct password for flag: ec27
That password is incorrect
jordanza-picoctf@webshell:~$ python level3.py
Please enter correct password for flag: 4e66
That password is incorrect
jordanza-picoctf@webshell:~$ python level3.py
Please enter correct password for flag: 865e
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_2b072a90}
jordanza-picoctf@webshell:~$ 
```

# Notas 
Verificar cual de las siguientes el la contraseña 
 ["6997", "3ac8", "f0ac", "4b17", "ec27", "4e66", "865e"]
La contraseña correcta es 865e
