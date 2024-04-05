
# Objetivo 

The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:56615/) out.
# Solución 
``` 
entramos a la pagina utilizando [saturn.picoctf.net:56615/robots.txt](http://saturn.picoctf.net:56615/robots.txt) se nos muestra 
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/

donde encontramos una parte codificada en base 64 aqui utilizaremos la heramienta cyberchef para poder convertir eso 

y nos da  anMvbXlmaWxlLnR4dA== a  js/myfile.txt 

asi que agragamos lo covertido [saturn.picoctf.net:56615/js/myfile.txt](http://saturn.picoctf.net:56615/js/myfile.txt) 
y asi obtenemos la bandera 



```
# Notas 

