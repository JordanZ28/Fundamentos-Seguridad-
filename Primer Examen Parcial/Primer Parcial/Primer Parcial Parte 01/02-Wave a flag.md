
# Objetivo 
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm) has extraordinarily helpful information...
# Solución 
```
jordanza-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm
--2024-02-26 18:29:06--  https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: 'warm'

warm                                                       100%[======================================================================================================================================>]  10.68K  --.-KB/s    in 0s      

2024-02-26 18:29:06 (226 MB/s) - 'warm' saved [10936/10936]

jordanza-picoctf@webshell:~$ ls
README.txt  flag  warm
jordanza-picoctf@webshell:~$ ./warm
-bash: ./warm: Permission denied
jordanza-picoctf@webshell:~$ ./warm -b
-bash: ./warm: Permission denied
jordanza-picoctf@webshell:~$ ./warm -h
-bash: ./warm: Permission denied
jordanza-picoctf@webshell:~$ chmod +x warm
jordanza-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_30e77291}
jordanza-picoctf@webshell:~$ 
```
# Notas 
chmod +x  Asigna Permisos de ejecución a un archivo binario 
