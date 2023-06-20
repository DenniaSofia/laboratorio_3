# laboratorio_3
Esta es una web en la que se insertaron tarjetas de información utilizando un archivo JSON. Esta se hizo con la finalidad de comprender 
el funcionamiento de este tipo de tarjetas porque son las que utilizaremos para la revista interactiva que realizaremos como proyecto final
del primer semestre. Fue elaborada como práctica en la clase de Diseño Web para los estudiantes de tercer año de Diseño Gráfico y Multimedia. 
Se utilizó el programa de Visual Studio Code, insertando los códigos correspondientes al html, css y java script facilitados por el docente.
A continuación, se detalla la estructura que está detrás de este tercer ejercicio:

ARCHIVO HTML
Este archivo es el texto de la página web, que está «marcado» con estos códigos para dar instrucciones al navegador web 
obre cómo mostrar el texto.

<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Web de tarjetas</title>
    <link rel="stylesheet" href="estilos.css">
</head>
<body>
    <h1>Tarjetas utilizando JSON
    <div id="tarjetas-container"></div>
    <script src="app.js"></script>
</body>
</html>
  
  
ARCHIVO CSS
La hoja de estilo CSS se utiliza para dar un formato adecuado al HTML. De este modo, se definieron atributos como el diseño, el color
y la forma de los elementos individuales de HTML.

.card {
    border: 1px solid #000045;
    border-radius: 8px;
    padding: 16px;
    margin-bottom: 16px;
    color: rgb(27, 58, 168);
}

.card h2 {
    font-size: 18px;
    margin-bottom: 8px;
}

.card p {
    font-size: 14px;
}
  
  
ARCHIVO JAVA SCRIPT
Mediante el archivo de Java script se logra hacer una página web interactiva. De esta manera, el objetivo es mejorar la experiencia del 
usuario en el sitio web.
  
fetch ('data.json')
.then(response => response.json())
.then(data => {
const tarjetasContainer=document.getElementById('tarjetas-container');

data.forEach(objeto=>{
const tarjeta = document.createElement('div');
tarjeta.classList.add('card');

const titulo = document.createElement('h2');
titulo.textContent = objeto.titulo;
        
const contenido = document.createElement('p');
contenido.textContent = objeto.contenido;

tarjeta.appendChild(titulo);
tarjeta.appendChild(contenido);

tarjetasContainer.appendChild(tarjeta);
});
})
.catch(error => console.error(error));
  
 
ARCHIVO JSON
Este documento digital almacena información organizada, con el fin de hacer más simple su búsqueda y acceso. Este formato permite obtener
código legible para las personas con nombres y valores que funcionan como indicadores de la información que contienen.
  
[
    {
        "titulo": "Tarjeta 1",
        "contenido": "Contenido de la tarjeta 1"
    },
    {
        "titulo": "Tarjeta 2",
        "contenido": "Contenido de la tarjeta 2"
    },
    {
        "titulo": "Tarjeta 3",
        "contenido": "Contenido de la tarjeta 3"
    }

]
  
  
  
  
  
  
  
  
  
  
