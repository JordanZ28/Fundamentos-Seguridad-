
# Objetivo 

Can you decrypt this message?Decrypt this [message](https://artifacts.picoctf.net/c/159/cipher.txt) using this key "CYLAB".
# Solución 
```
┌──(jordan㉿kali)-[~/Pico/Examen3/R5]
└─$ wget https://artifacts.picoctf.net/c/159/cipher.txt                                               
--2024-05-14 21:26:37--  https://artifacts.picoctf.net/c/159/cipher.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.60, 3.161.225.3, 3.161.225.11, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.60|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43 [application/octet-stream]
Saving to: ‘cipher.txt’

cipher.txt                      100%[====================================================>]      43  --.-KB/s    in 0s      

2024-05-14 21:26:38 (27.4 MB/s) - ‘cipher.txt’ saved [43/43]

                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Examen3/R5]
└─$ ls 
cipher.txt
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Examen3/R5]
└─$ cat cipher.txt 
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_f85729e7}
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Examen3/R5]
└─$ 


utilizamos el cyberchef para obtener la bandera 
picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_d85729g7}

```

# Notas 

