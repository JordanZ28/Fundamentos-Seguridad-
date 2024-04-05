
# Objetivo 

Download this image and find the flag.

- [Download image](https://artifacts.picoctf.net/c/216/pico.flag.png)
# Solución 
```
Pimero instalamos la heramienta zsteg 
de la siguiente manera 
Es sudo apt install ruby Y luego sudo gem install zsteg 
una ves ya instalado descargamos la imagen 
y con el siguiente comando  obtendremos la bandera 
zsteg -a pico.flag.png | grep 'pico'

y la bandera sera picoCTF{7h3r3_15_n0_5p00n_a1062667}
```

# Notas 

