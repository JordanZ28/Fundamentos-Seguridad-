
# Objetivo 

There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 35652`, but it doesn't speak English...
# Solución 
``` jordanza-picoctf@webshell:~$ nc mercury.picoctf.net 35652
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
57 
98 
51 
98 
55 
51 
57 
50 
125 
10 

picoCTF{g00d_k1tty!_n1c3_k1tty!_9b3b7392}
```
Se hizo el cambio a la pagina cyberchef donde se utilizo la formula charcode y a base 10 para poder obtener la llave

# Notas 

Se utilizo la pagina  cyber chef en el cual utilizamos un convertidor de ascii utilizando  From charcode delimiter=space Base=10 

# Referencias 
[From Charcode - CyberChef (gchq.github.io)](https://gchq.github.io/CyberChef/#recipe=From_Charcode('Space',10)&input=MTEyIA0KMTA1IA0KOTkgDQoxMTEgDQo2NyANCjg0IA0KNzAgDQoxMjMgDQoxMDMgDQo0OCANCjQ4IA0KMTAwIA0KOTUgDQoxMDcgDQo0OSANCjExNiANCjExNiANCjEyMSANCjMzIA0KOTUgDQoxMTAgDQo0OSANCjk5IA0KNTEgDQo5NSANCjEwNyANCjQ5IA0KMTE2IA0KMTE2IA0KMTIxIA0KMzMgDQo5NSANCjU3IA0KOTggDQo1MSANCjk4IA0KNTUgDQo1MSANCjU3IA0KNTAgDQoxMjUgDQoxMCA)