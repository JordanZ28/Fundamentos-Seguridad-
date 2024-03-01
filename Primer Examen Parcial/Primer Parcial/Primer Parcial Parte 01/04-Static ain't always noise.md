
# Objetivo 

Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/static)? This [BASH script](https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/ltdis.sh) might help!
# Solución 
```
jordanza-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/static
--2024-02-26 18:52:58--  https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/static
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8376 (8.2K) [application/octet-stream]
Saving to: 'static'

static                                                     100%[======================================================================================================================================>]   8.18K  --.-KB/s    in 0s      

2024-02-26 18:52:58 (274 MB/s) - 'static' saved [8376/8376]

jordanza-picoctf@webshell:~$ ls
README.txt  flag  static  warm
jordanza-picoctf@webshell:~$ strings static | grep pico
picoCTF{d15a5m_t34s3r_f6c48608}
jordanza-picoctf@webshell:~$ 
```
# Notas 
Aqui utilizamos el comando strings static | grep pico que nos permite extrae 

