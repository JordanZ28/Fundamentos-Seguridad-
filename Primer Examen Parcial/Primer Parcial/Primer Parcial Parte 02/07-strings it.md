# Objetivo 

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings) without running it?
# Solución 
```

jordanza-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings
--2024-03-01 05:41:36--  https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 776032 (758K) [application/octet-stream]
Saving to: 'strings'

strings                                                    100%[======================================================================================================================================>] 757.84K  1.84MB/s    in 0.4s    

2024-03-01 05:41:36 (1.84 MB/s) - 'strings' saved [776032/776032]

jordanza-picoctf@webshell:~$ ls
Addadshashanammu  Addadshashanammu.zip  Addadshashanammu.zip.1  README.txt  code.py  codebook.txt  convertme.py  file  fixme1.py  flag  static  strings  warm
jordanza-picoctf@webshell:~$ strings strings | grep picoCTF
picoCTF{5tRIng5_1T_7f766a23}
jordanza-picoctf@webshell:~$ 

```

# Notas 
Descargamos el archivo el reto para obtener la bandera es no ejecutarlo por lo cual utilizamos el siguiente comando 
trings strings | grep picoCTF que nos imprimir la bandera ya que con el comando strings imprime las secuencias de caracteres imprimibles que tienen al menos 4 caracteres (o el número con las opciones a continuación) y van seguidos de un carácter no imprimible
