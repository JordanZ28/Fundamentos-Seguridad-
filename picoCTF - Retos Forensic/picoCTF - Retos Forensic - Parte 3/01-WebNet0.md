
# Objetivo 
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.
# Solución 
```
Se descarga un archivo y una llave y se almacena en una carpeta 
Se tiene una captura de paquetes y una llave utilizando el wiresahark par poder obtener la bandera 
donde se tiene una comunicacion tls 

Se abre el wiresahark como no se puede ver nada en los paquetes agregamos un protocolo Tls que en ese podemos agraegar la llave que nos dan para poder desifrar los paquetes agregando la llave nos vamos a buscar un string que inice con picoCTF que nos encuentra en donde es donde viene la bandera y asi extreamos la bandarea para poder completar el reto 


```
# Notas 

