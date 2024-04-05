
# Objetivo 

Can you get the flag?Go to this [website](http://saturn.picoctf.net:50920/) and see what you can discover.
# Solución 
```
Al ver el sito web se nos pide un usuario y contraseña y al ingresar admin y 12345 como usario y contraseña nos sale como error asi que inpeccionando la pagina podemos encontra un archivo con el nombre de 
secure.js que en este contiene el usuario y la contraseña permitidas 
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}

y asi obtenemos la bandera picoCTF{j5_15_7r4n5p4r3n7_05df90c8}


```

# Notas 
la bandera es picoCTF{j5_15_7r4n5p4r3n7_05df90c8} 

