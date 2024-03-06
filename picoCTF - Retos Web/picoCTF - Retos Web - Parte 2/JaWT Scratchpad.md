# Objetivo 
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/61864/` or http://jupiter.challenges.picoctf.org:61864

# Solución 
```
picoCTF{jawt_was_just_what_you_thought_1ca14548}

```
Se utilizo la pagina jwt para poder descifrar la cookie que se obtuvo un al utilizar un extensión 
donde se utilizo john has --wordlist=/rockyou/rockyou.txt --format=HMAC-sha256 
que el rockyou contiene un txt de varias contraseñas que estamos utilizando en consola para poder utilizar este comando primero debemos de instalar el john  para poder obtener la bandera 
después de usar el comando nos da una mensaje para poder usar en jwt que es ilovepico asi cambiando la cookie para poder obtener la bandera 
# Notas 

Utilizar el cokies y el jwt para poder identificar 
lugo utilizar consola 
jwt 

# Referencia 
[JSON Web Tokens - jwt.io](https://jwt.io/)