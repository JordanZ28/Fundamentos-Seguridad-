
# Objetivo 

Run the Python script and convert the given number from decimal to binary to get the flag.[Download Python script](https://artifacts.picoctf.net/c/22/convertme.py)
# Solución 
```
jordanza-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/22/convertme.py
--2024-03-01 05:14:01--  https://artifacts.picoctf.net/c/22/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.16, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: 'convertme.py'

convertme.py                                               100%[======================================================================================================================================>]   1.16K  --.-KB/s    in 0s      

2024-03-01 05:14:01 (505 MB/s) - 'convertme.py' saved [1189/1189]

jordanza-picoctf@webshell:~$ ls
Addadshashanammu  Addadshashanammu.zip  Addadshashanammu.zip.1  README.txt  code.py  codebook.txt  convertme.py  flag  static  warm
jordanza-picoctf@webshell:~$ python convertme.py 
If 50 is in decimal base, what is it in binary base?
Answer: 110010
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_762f748e}
jordanza-picoctf@webshell:~$ 

```

# Notas 
Descargamos el archivo luego lo ejecutamos con el siguiente comando python convertme.py  al ejecutar, nos pide que el 50 en decimal lo convirtamos a binario que seria 110010  y asi obtenemos la contraseña 


