# Retos Bandit 
# Bandido Nivel 12 → Nivel 13

# Objetivo 
La contraseña para el siguiente nivel se almacena en el archivo **data.txt**, que es un volcado hexadecimal de un archivo que se ha comprimido repetidamente. Para este nivel, puede ser útil crear un directorio en /tmp en que se puede trabajar usando mkdir. Por ejemplo: mkdir /tmp/myname123. A continuación, copie el archivo de datos usando cp y cámbiele el nombre usando mv (lea el archivo páginas de manual!)

# Datos de acceso al nivel 
bandit12
ssh -l bandit12 bandit.labs.overthewire.org -p 2220
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
# Solución 
```
bandit12@bandit:~$ xxd -r data.txt | file -
/dev/stdin: gzip compressed data, was "data2.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat |file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat |file -
/dev/stdin: gzip compressed data, was "data4.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat |file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat |file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | file -
/dev/stdin: gzip compressed data, was "data9.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat | file -
/dev/stdin: ASCII text
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
bandit12@bandit:~$
```

# Notas 
xxd un vaciado

# Referencias 
[Volcado hexadecimal - Wikipedia, la enciclopedia libre](https://en.wikipedia.org/wiki/Hex_dump)

