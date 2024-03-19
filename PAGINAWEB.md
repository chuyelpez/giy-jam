---
attachments: [Clipboard_2023-12-03-10-48-20.png, Clipboard_2023-12-03-10-48-28.png, Clipboard_2023-12-03-10-48-41.png, Clipboard_2023-12-03-10-48-47.png]
title: 'UNIDAD 3.3: PÁGINA WEB FUNCIONAL CON HTML, CSS Y JS EN DJANGO'
created: '2023-12-03T16:35:12.778Z'
modified: '2023-12-03T16:48:47.547Z'
---

# UNIDAD 3.3: PÁGINA WEB FUNCIONAL CON HTML, CSS Y JS EN DJANGO

> Dentro de esta nueva actividad será rapida hacer una página web funcional con un HTML, CSS Y JS en nuestro proyecto de Django, para ello vamos a ir paso a paso para hacer rápida y sencilla esta validación de nuestra página web

1. Primero vamos a crear las carpetas y archivos correspondientes y serán en la ruta **ProgramacionRedes/mysite/webapp/static** y crearemos una carpeta llamada **site/** luego otra carpeta llamada **dist/** y luego creamos las carpetas llamadas **assets/** **css/** y **js/** y luego fuera de la carpeta **static/** vamos a crear una carpeta llamada **web/** y allí crearemos nuestros archivos HTML

2. Crearemos nuestros archivos empezando por la página HTML que será como nuestra portada de inicio con un bootstrap y a ese archivo lo llamaremos **pagina.html** y colocamos el código
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
  <title>Seguridad en la Red</title>
  <link href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>

<div class="container mt-5">
  <h1 class="mb-4">Seguridad en la Red</h1>

  <div class="alert alert-info">
    <h4 class="alert-heading">Contraseñas Seguras</h4>
    <p>Una contraseña segura es crucial para proteger tu información en línea. Asegúrate de utilizar una combinación de letras, números y caracteres especiales.</p>
  </div>

  <div class="alert alert-warning">
    <h4 class="alert-heading">Evita el Phishing</h4>
    <p>No hagas clic en enlaces sospechosos y evita proporcionar información confidencial en sitios web no seguros. Verifica siempre la autenticidad de los correos electrónicos.</p>
  </div>

  <div class="alert alert-success">
    <h4 class="alert-heading">Conexiones Seguras</h4>
    <p>Al navegar en la web, asegúrate de que las conexiones sean seguras (HTTPS). Evita utilizar redes Wi-Fi públicas para transacciones sensibles.</p>
  </div>

  <footer class="mt-5">
    <p class="text-muted">© 2023 Seguridad en la Red</p>
  </footer>
</div>

<a href="{% url 'section-main' %}" class="btn btn-primary">Formulario</a>

<script src="https://code.jquery.com/jquery-3.2.1.slim.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"></script>

</body>
</html>

```

Luego creamos nuestro formulario que será para la parte de la página funcional y se llamará **index.html** y colocamos el código

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    {% load static %}
    <link rel="stylesheet" href="{% static 'site/dist/css/styles.css' %}">
    <title>Index</title>
</head>
<body>

    <h1>Formulario</h1>

    <form id="guarda">

    <input type="text" id="name" placeholder="Escribe tu nombre"> <br>

    <input type="text" id="last_name" placeholder="Escribe tu apellido"> <br>

    <input type="number" id="age" placeholder="Escribe tu edad"> <br>

    <select id="sex">
        <option selected>Tipo</option>
        <option>Hombre</option>
        <option>Mujer</option>
    </select> <br>

    <input type="email" id="email" placeholder="Escribe tu email"> <br>

    <input type="submit" value="Guardar" id="guarda" onclick="datos()">

    <input type="reset" value="Limpiar" id="limpia">

    </form>

    <p id="comprobado"></p>

    <a href="{% url 'section-pagina' %}" class="btn btn-primary">Pagina principal</a>

    <script src="{% static 'site/dist/js/script.js'%}"></script>


</body>
</html>
```

Ahora creamos dentro de la carpeta **static/site/dist/css/** el archivo llamado **styles.css** y colocamos el código

```css
body {
  font-family: 'Arial', sans-serif;
  background-color: #f4f4f4;
  margin: 0;
  padding: 0;
}

h1 {
  text-align: center;
  color: #333;
}

form {
  max-width: 400px;
  margin: 20px auto;
  background-color: #fff;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

input, select {
  width: 100%;
  padding: 10px;
  margin-bottom: 15px;
  box-sizing: border-box;
}

input[type="submit"], input[type="reset"] {
  background-color: #4caf50;
  color: #fff;
  cursor: pointer;
}

input[type="submit"]:hover, input[type="reset"]:hover {
  background-color: #45a049;
}

#comprobado {
  text-align: center;
  margin-top: 10px;
  color: #333;
}


a {
  text-align: center;
  margin-top: 10px;
  color: #333;
}
```

Por último colocamos en la ruta **static/site/dist/js/** nuestro archivo js llamado **script.js**

```js
const datos = () => {

  let guardar = document.getElementById('guarda');
  guardar.addEventListener('submit', (event) => {
      event.preventDefault();
  });
  
  let nombre = document.getElementById("name").value;
  let apellido = document.getElementById("last_name").value;
  let edad = document.getElementById("age").value;
  let genero = document.getElementById("sex").value;
  let correo = document.getElementById("email").value;
  let probar = document.getElementById("comprobado");
  
  probar.innerHTML = `
          Nombre: ${nombre} <br>
          Apellido: ${apellido} <br>
          Edad: ${edad} <br>
          Genero: ${genero} <br>
          Correo: ${correo} <br>
      `
}

datos();
```

3. Por último creamos nuestras vistas y rutas en **views.py** y **urls.py**

- views.py
```py
from django.shortcuts import render
from django.http import HttpResponse
from persona.models import Persona as PersonaModel
from persona.models import Domicilio as DomicilioModel
from django.shortcuts import redirect
import datetime
import time
import os

def index(request):
    return render(request, 'web/index.html')

def pagina(request):
    return render(request, 'web/pagina.html')
```

- urls.py
```py
"""
URL configuration for programacion project.

The `urlpatterns` list routes URLs to views. For more information please see:
    https://docs.djangoproject.com/en/4.2/topics/http/urls/
Examples:
Function views
    1. Add an import:  from my_app import views
    2. Add a URL to urlpatterns:  path('', views.home, name='home')
Class-based views
    1. Add an import:  from other_app.views import Home
    2. Add a URL to urlpatterns:  path('', Home.as_view(), name='home')
Including another URLconf
    1. Import the include() function: from django.urls import include, path
    2. Add a URL to urlpatterns:  path('blog/', include('blog.urls'))
"""
from django.contrib import admin
from django.urls import path
from webapp.views import *

path('web/index/', index, name='section-main'),
path('web/pagina/', pagina, name='section-pagina'),
```

**Y LISTO, CON ESTO TENDREMOS FUNCIONANDO NUESTRA PÁGINA WEB FUNCIONAL CON ESTILOS Y UNA VALIDACIÓN DE NUESTRO FORMULARIO**

---

# CAPTURAS DE FUNCIONAMIENTO

![](@attachment/Clipboard_2023-12-03-10-48-20.png)

![](@attachment/Clipboard_2023-12-03-10-48-28.png)

![](@attachment/Clipboard_2023-12-03-10-48-41.png)

![](@attachment/Clipboard_2023-12-03-10-48-47.png)
