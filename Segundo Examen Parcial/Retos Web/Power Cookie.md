
# Objetivo 
Can you get the flag?Go to this [website](http://saturn.picoctf.net:57741/) and see what you can discover.

# Solución 
```
Al entrar a la pagina nos encontramos con un boton que nos dice que si queremos continuar como invitado pero aparece Lo sentimos, pero no tenemos servicios para huéspedes en este momento a hora inspeccionaremos la pagina nos encontramos con guest.js que al abrir contien 
function continueAsGuest()
{
  window.location.href = '/check.php';
  document.cookie = "isAdmin=0";
}
lo que vamos hacer es cambiar isAdmin=0  de 0 a 1

para poder obtener la bandera 
picoCTF{gr4d3_A_c00k13_5d2505be}

```
# Notas 

