
# Objetivo 
How about some hide and seek heh? Look at this image [here](https://artifacts.picoctf.net/c/241/atbash.jpg).

# Solución 
```
┌──(jordan㉿kali)-[~/Pico/Cry/Cry2/Hid]
└─$ steghide extract -sf atbash.jpg 
Enter passphrase: 
wrote extracted data to "encrypted.txt".
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Cry/Cry2/Hid]
└─$ cat encrypted.txt 
krxlXGU{zgyzhs_xizxp_7142uwv9}
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Cry/Cry2/Hid]
└─$ 

ulilizanod el cyberchef  se obtuvo la bandera  con el atbas 

picoCTF{atbash_crack_7142fde9}
```
# Notas 
Se utiliso la herramienta Steghide es una herramienta de esteganografía que permite ocultar archivos privados dentro de una imagen o archivo de audio Los tipos de imagen BMP y JPEG, así como los formatos de audio AU y WAV son compatibles. El archivo está encriptado por defecto usando el algoritmo Rijndael, con un tamaño de clave de 128 bits.