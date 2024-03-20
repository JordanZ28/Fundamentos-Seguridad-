
# Objetivo 
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

# Solución 
```
Se descarga un archivo y una llave y se almacena en una carpeta 
Se tiene una captura de paquetes y una llave utilizando el wiresahark par poder obtener la bandera

Utilizando el wireshark nos vamos a las preferencias en protocolos tls donde cargamos la llave que se nos dio para poder desencriptar ciertos paqeuetes 
Donde podemos identicar una descarga d eun imgaen en el paquete 47 donde extraemos la imagen y la gurdamos en nuestra carpeta para poder abril la imagen despues con un strings extraer la bandera con el sigueiente comando strings vulture.jpg -n15 para poder obtener la bandera 

```
# Notas 

