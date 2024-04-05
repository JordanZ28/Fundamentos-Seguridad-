
# Objetivo 

Can you get the flag?Go to this [website](http://saturn.picoctf.net:58519/) and see what you can discover.
# Solución 
```

Como podemos ver visitamos una Pagina web donde encontramos contiene una descripcion lo que vamos a realizar es ver el codigo funte de la paginal el cual podemos ver que contiene dos partes de la bandera una llamada style.css que contiene 

body {
  background-color: lightblue;
}

/*  picoCTF{1nclu51v17y_1of2_  */

y la otra parte contiene script.js

  
function greetings()
{
  alert("This code is in a separate file!");
}

//  f7w_2of2_b8f4b022}

picoCTF{1nclu51v17y_1of2_f7w_2of2_b8f4b022}
```
# Notas 
La bandera es picoCTF{1nclu51v17y_1of2_f7w_2of2_b8f4b022}