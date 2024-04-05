
# Objetivo 
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it.Download the data [here](https://artifacts.picoctf.net/c/125/anthem.flag.txt).

# Solución 
```
Descargamos el archivo ya descargado le aplicamos un cat para ver su contenido  cat anthem.flag.txt 
y nos muestra mucho texto entoces agragamos un grep con la palabra pico para poder encontrar la bandera 
cat anthem.flag.txt  | grep 'pico'
picoCTF{gr3p_15_@w3s0m3_58f5c024}

```
# Notas 

