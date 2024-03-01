# Objetivo 
Using netcat (nc) is going to be pretty important. Can you connect to `jupiter.challenges.picoctf.org` at port `41120` to get the flag?
# Solución 
```
jordanza-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 41120
You're on your way to becoming the net cat master
picoCTF{nEtCat_Mast3ry_3214be47}

jordanza-picoctf@webshell:~$ 
```
# Notas 
nos conectamos con el siguiente comando nc jupiter.challenges.picoctf.org 41120 para poder obtener la bandera

El nc se utiliza para casi cualquier cosa bajo el sol que implique TCP o UDP. Puede abrir conexiones TCP, enviar paquetes UDP, escuchar en puertos TCP y UDP arbitrarios, realizar escaneo de puertos y tratar con IPv4 e IPv6. A diferencia de **[telnet](https://linux.die.net/man/1/telnet)**(1), **nc** scripts muy bien, y separa el error mensajes en error estándar en lugar de enviarlos a la salida estándar, como **[hace telnet](https://linux.die.net/man/1/telnet)**(1) con algunos.