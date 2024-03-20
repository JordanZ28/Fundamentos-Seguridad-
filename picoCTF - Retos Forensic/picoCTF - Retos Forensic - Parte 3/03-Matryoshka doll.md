
# Objetivo 

Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/f6cc2560a70b1ea811c151accba5390f/dolls.jpg)
# Solución 
```
Descargamos el archivo y lo guardamos en una carpeta 
empezamos viendo que contiene de metadatos y no contiene nada a hora aplicamos un string en el que podemos identificar que tiene algo oculto 
Utilizamos la herramienta binwalk para poder confirmar que contiene algo mas que es una imagen y un zip 
asi que con la heramienta binwalk extraemos y obtenemos una sub carpeta donde abrimos la carpeta y contiene dos carpetas abrimos la carpeta con el nombre de base_imagen y contiene una imagen de una muñeca 
a hora repetimos lo que realizamos pero a hora a la imagen con el nombre de 2_c.jpg 
donde repetimos lo mismo que realizamos 
donde a hora encontramos otra imgaen de una muneca un poco mas pequena y le volvemos a realizar con la heramienta binwalk a hora a la imagen 3_c.jpg 
volvemos a repetir el prcedimeinto y llegamos a otra muñeca a hora mas pequena con el nombre de la imagen 4_c.jpg y le volvemos aplicar el mismo procediemiento 
pero a hora dectectai¿mos que esta imagen contiene la bandera en un archivo txt de nombre flag.txt que lo abrimos con un cat y ahi viene la bandera 




```
# Notas 

