
# Objetivo 

A second message has come in the mail, and it seems almost identical to the first one. Maybe the same thing will work again. Download the message [here](https://artifacts.picoctf.net/c/183/message.txt).
# Solución 
```
┌──(jordan㉿kali)-[~/Pico/Examen3/R4]
└─$ wget https://artifacts.picoctf.net/c/183/message.txt
--2024-05-14 21:00:04--  https://artifacts.picoctf.net/c/183/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.11, 3.161.225.60, 3.161.225.3, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.11|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 638 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                     100%[=====================================================>]     638  --.-KB/s    in 0s      

2024-05-14 21:00:04 (12.5 MB/s) - ‘message.txt’ saved [638/638]

                                                                                                                              
┌──(jordan㉿kali)-[~/Pico/Examen3/R4]
└─$ ls 
message.txt
                                                                                                                              
┌──(jordan㉿kali)-[~/Pico/Examen3/R4]
└─$ cat message.txt 
LKOb (bwvek ove lgqkhej kwj osgx) gej g kyqj vo lvrqhkje bjlhetky lvrqjktktvu. Lvukjbkgukb gej qejbjukjz dtkw g bjk vo lwgssjuxjb dwtlw kjbk kwjte lejgktftky, kjlwutlgs (guz xvvxstux) bitssb, guz qevmsjr-bvsftux gmtstky. Lwgssjuxjb hbhgssy lvfje g uhrmje vo lgkjxvetjb, guz dwju bvsfjz, jglw ytjszb g bketux (lgssjz g osgx) dwtlw tb bhmrtkkjz kv gu vustuj blvetux bjeftlj. LKOb gej g xejgk dgy kv sjgeu g dtzj geegy vo lvrqhkje bjlhetky bitssb tu g bgoj, sjxgs juftevurjuk, guz gej wvbkjz guz qsgyjz my rguy bjlhetky xevhqb gevhuz kwj dvesz ove ohu guz qeglktlj. Ove kwtb qevmsjr, kwj osgx tb: qtlvLKO{OE3AH3ULY_4774LI5_4E3_L001_6J0659OM}                                                                                                                              
┌──(jordan㉿kali)-[~/Pico/Examen3/R4]
└─$ 

|   |
|---|
|Los CTF (abreviatura de capturar la bandera) son un tipo de competencia de seguridad informática. A los concursantes se les presenta una serie de desafíos que ponen a prueba su creatividad, habilidades técnicas (y de búsqueda en Google) y capacidad de resolución de problemas. Los desafíos generalmente cubren una serie de categorías y, cuando se resuelven, cada una produce una cadena (llamada marca) que se envía a un servicio de puntuación en línea. Los CTF son una excelente manera de aprender una amplia gama de habilidades de seguridad informática en un entorno seguro y legal, y son organizados y jugados por muchos grupos de seguridad de todo el mundo para divertirse y practicar. Para este problema, el indicador es: picoCTF{FR3QU3NCY_4774CK5_4R3_C001_6E0659FB}|


Se utilizo esta pagina para poder cifrar el mensaje 
[Quipqiup - CryptoQuip y solucionador de criptogramas](https://quipqiup.com/#google_vignette)
```
# Notas 

