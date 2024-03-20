
# Objetivo 
We found this [file](https://mercury.picoctf.net/static/06a5e4ab22ba52cd66a038d51a6cc07b/tunn3l_v1s10n). Recover the flag.

# Solución 
```
creamos una carpeta para poder trabajar con el reto a hora descargamos el archivo luego cemos que tipo de archivo es que en este caso es un archivo BM 
camiamos la extencion del archivo luego utilizando la heramienta hexeditor vamos a modificar unos datos para poder En la pociscion 0e vamos a modificar de BA D0 a 28 00 y en el 0A encontramos otro BA D0 donde inician los datos y aqui igaul cambiamos a 28 00 y ya podemos abri la imagen y ya nos deja pero notamos que la imgaen es un poco pequeña asi que volvemos al hexeditor para cambiar los datos del tamaño en 012 cambiamos el tamaño de 32 01 a 40 04 para poder modificar el alto de la imagen ya guardando esa modificacion y abriendo el archivo podemos ver que la bandera se encuentra ahi en la imagen 



```

# Notas 

