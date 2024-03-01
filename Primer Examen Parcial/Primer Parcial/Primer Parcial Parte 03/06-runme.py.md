
# Objetivo 

Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.[Download runme.py Python script](https://artifacts.picoctf.net/c/34/runme.py)
# Solución 
```
jordanza-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/34/runme.py
--2024-03-01 19:02:19--  https://artifacts.picoctf.net/c/34/runme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.43, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: 'runme.py'

runme.py                                                   100%[======================================================================================================================================>]     270  --.-KB/s    in 0s      

2024-03-01 19:02:19 (2.18 MB/s) - 'runme.py' saved [270/270]

jordanza-picoctf@webshell:~$ python runme.py 
picoCTF{run_s4n1ty_run}
jordanza-picoctf@webshell:~$ 
```
# Notas 
Descargamos el archivo y luego lo corremos para poder obtener la bandera 


