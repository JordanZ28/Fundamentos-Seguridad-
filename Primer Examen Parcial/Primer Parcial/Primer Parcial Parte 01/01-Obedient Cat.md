# Objetivo 
This file has a flag in plain sight (aka "in-the-clear"). [Download flag](https://mercury.picoctf.net/static/33996e32dce022205a6a36f69aba56f0/flag).
# Solución 
```
jordanza-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/33996e32dce022205a6a36f69aba56f0/flag
--2024-02-26 18:20:19--  https://mercury.picoctf.net/static/33996e32dce022205a6a36f69aba56f0/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: 'flag'

flag                  100%[=======================>]      34  --.-KB/s    in 0s      

2024-02-26 18:20:19 (12.8 MB/s) - 'flag' saved [34/34]

jordanza-picoctf@webshell:~$ cat flag
picoCTF{s4n1ty_v3r1f13d_2aa22101}
jordanza-picoctf@webshell:~$ ^C
```
# Notas 
wget sirve para descargar un archivo directamente en la consola 

