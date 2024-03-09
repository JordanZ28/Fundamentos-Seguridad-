
# Objetivo 

There is some interesting information hidden around this site [http://mercury.picoctf.net:27278/](http://mercury.picoctf.net:27278/). Can you find it?
# Solución 
```
Ingresamos a la link  luego nos vamos a inspeccionar el codigo y podemos ver en la parte de abajo un pedaso de la bandera 
  

|   |   |
|---|---|
||<!doctype html>|
||<html>|
||<head>|
||<title>Scavenger Hunt</title>|
||<link href="[https://fonts.googleapis.com/css?family=Open+Sans\|Roboto](https://fonts.googleapis.com/css?family=Open+Sans\|Roboto)" rel="stylesheet">|
||<link rel="stylesheet" type="text/css" href="[mycss.css](http://mercury.picoctf.net:27278/mycss.css)">|
||<script type="application/javascript" src="[myjs.js](http://mercury.picoctf.net:27278/myjs.js)"></script>|
||</head>|
|||
||<body>|
||<div class="container">|
||<header>|
||<h1>Just some boring HTML</h1>|
||</header>|
|||
||<button class="tablink" onclick="openTab('tabintro', this, '#222')" id="defaultOpen">How</button>|
||<button class="tablink" onclick="openTab('tababout', this, '#222')">What</button>|
|||
||<div id="tabintro" class="tabcontent">|
||<h3>How</h3>|
||<p>How do you like my website?</p>|
||</div>|
|||
||<div id="tababout" class="tabcontent">|
||<h3>What</h3>|
||<p>I used these to make this site: <br/>|
||HTML <br/>|
||CSS <br/>|
||JS (JavaScript)|
||</p>|
||<!-- Here's the first part of the flag: picoCTF{t -->|
||</div>|
|||
||</div>|
|||
||</body>|
||</html>|
||

Luego podemos ver que se tiene dos archivo uno de nombre [mycss.css](http://mercury.picoctf.net:27278/mycss.css)">  el cual al ingresar 

div.container {
    width: 100%;
}

header {
    background-color: black;
    padding: 1em;
    color: white;
    clear: left;
    text-align: center;
}

body {
    font-family: Roboto;
}

h1 {
    color: white;
}

p {
    font-family: "Open Sans";
}

.tablink {
    background-color: #555;
    color: white;
    float: left;
    border: none;
    outline: none;
    cursor: pointer;
    padding: 14px 16px;
    font-size: 17px;
    width: 50%;
}

.tablink:hover {
    background-color: #777;
}

.tabcontent {
    color: #111;
    display: none;
    padding: 50px;
    text-align: center;
}

#tabintro { background-color: #ccc; }
#tababout { background-color: #ccc; }

/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */

Nos da la segunada parte de la bandera 
Luego agregamos el el link la palabra [mercury.picoctf.net:27278/robots.txt](http://mercury.picoctf.net:27278/robots.txt) para poder obtener la 3  parte de la bandera 

User-agent: *
Disallow: /index.html
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?

luego utilizando otra extencion  [view-source:mercury.picoctf.net:27278/.htaccess](view-source:http://mercury.picoctf.net:27278/.htaccess) obtenemos la 4 parte de la bandera 
|   |   |
|---|---|
||# Part 4: 3s_2_lO0k|
||# I love making websites on my Mac, I can Store a lot of information there.|

y como ultima extencion agregamos [view-source:mercury.picoctf.net:27278/.DS_Store](view-source:http://mercury.picoctf.net:27278/.DS_Store) obteniendo la ultima parte de la bandera 
Congrats! You completed the scavenger hunt. Part 5: _a69684fd}
```

# Notas 
Extenciones  que nos ayudaron a obtener la bandera robots.txt, .htaccess y .Ds_Store 
picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_a69684fd}