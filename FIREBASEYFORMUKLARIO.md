---
attachments: [Clipboard_2023-12-03-13-04-19.png, Clipboard_2023-12-03-13-05-14.png, Clipboard_2023-12-03-13-06-40.png, Clipboard_2023-12-03-13-07-02.png, Clipboard_2023-12-03-13-08-25.png, Clipboard_2023-12-03-13-10-07.png, Clipboard_2023-12-03-13-10-49.png, Clipboard_2023-12-03-13-11-40.png, Clipboard_2023-12-03-13-13-56.png, Clipboard_2023-12-03-13-18-21.png, Clipboard_2023-12-03-13-18-22.png, Clipboard_2023-12-03-13-21-52.png, Clipboard_2023-12-03-13-23-43.png, Clipboard_2023-12-03-13-36-54.png, Clipboard_2023-12-03-13-37-08.png, Clipboard_2023-12-03-13-43-01.png, Clipboard_2023-12-03-13-43-11.png, Clipboard_2023-12-03-13-43-24.png]
title: 'UNIDAD 3.4: FIREBASE Y FORMULARIO'
created: '2023-12-03T16:49:05.293Z'
modified: '2023-12-03T19:43:24.556Z'
---

# UNIDAD 3.4: FIREBASE Y FORMULARIO 

> Firebase es una plataforma de desarrollo de aplicaciones móviles y web que ofrece una variedad de servicios y herramientas para simplificar el desarrollo y mejorar la calidad de las aplicaciones. Fue adquirida por Google en 2014 y desde entonces ha experimentado un crecimiento significativo.

Bueno, sabemos que firebase pertenece a Google, por ello vamos a necesitar dos cosas importantes

- Cuenta de Google (sea personal o institucional)
- Acceso a Internet estable (de preferencia que sea una velocidad de 100Mb)

1. Vamos a crear nuestro proyecto de firebase, por ello vamos a la URL de firebase y es la siguiente **https://firebase.google.com/?authuser=1&hl=es-419**
2. Le daremos en **Comienza ahora**, posterior le daremos en el boton llamado **Crear un proyecto**
3. Configuramos el nombre de nuestro proyecto (en mi caso se llamará **prueba-ird41** ) y aceptamos los términos y condiciones y le damos en **Continuar**
4. Le daremos en **Continuar** y seleccionamos por default la *Ubicación de Analytics* en **México**, aceptamos las condiciones de Google Analytics y en el boton **Crear proyecto**
5. Una vez haya terminado de crearse, vamos a la parte de **Continuar** y seleccionamos en la parte interfior izquierda una sección llamada *Todos los productos* y la seleccionamos, luego buscamos una opción llamada **Realtime Database** y la elegimos. Posterior presionamos el boton que se llama **Crear una base de datos** 
6. Nos pedirá la *Ubicación de Realtime Database* y dejamos la que esta por default y le damos en **Siguiente**, luego nos dira dos opciones, si seleccionamos el **modo bloqueado** no nos permitirá cambiar nada ni hacer nada con esa base de datos, pero tenemos que seleccionar el **modo de prueba** para poder manipular con el formulario esta base de datos y le damos en **Habilitar**
7. Ya tendremos nuestra base de datos en tiempo real, ahora solamente tenemos que ir en la parte superior izquierda donde dice **Descripción general** y seleccionamos un icono que tiene esta forma **</>** y la seleccionamos
8. En la opcion de *Registrar app* le daremos un nombre (pueden poner el que gusten, en mi caso sera appweb) y selccionamos la opcion de *Además, configura Firebase Hosting para esta app* y dejamos la que esta en default que es nuestro proyecto de firebase anteriormente creada y le damos **Registrar app**
9. Nos pedirá que seleccionemos *Usar npm* ó *Usar una etiqueta < script >* y seleccionamos la segunda, posterior en un recuadro nos dirá en una etiqueta *< script >*  y copiamos todo ese código y lo guardamos en un editor de texto y lo usaremos más adelante y le daremos en **Siguiente**. Luego en **Siguiente** y luego en **Ir a la consola**
10. Ya tendremos la parte de nuestro firebase configurado como una app web, esto permitirá que el formulario se ejecute con éxito en todo momento que queramos mandar nuestros registros al mismo.
---

# CREACION DEL APP WEB DE FIREBASE Y FORMULARIO

Bueno, una vez hayamos configurado nuestro proyecto en Firebase, vamos a realizar lo siguiente para poder hacer que envie registros que le mandemos desde un documento HTML y junto a su etiqueta < script > desde el proyecto de Django, así que vamos a realizar esto de forma rápida y sencilla

1. Primero vamos a crear un archivo en la ruta **ProgramacionRedes/mysite/webapp/templates** y se llamará **firebase.html** posterior primero vamos a pegar este código en nuestro HTML

```html
{% extends "layouts/layouts.html" %}

{% block title %} Firebase DataBase Realtime {% endblock %}

{% block content %}
    
<script type="module">
  // Import the functions you need from the SDKs you need
    import { initializeApp } from "https://www.gstatic.com/firebasejs/10.6.0/firebase-app.js";
    import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.6.0/firebase-analytics.js";
    import { getDatabase, ref, set } from "https://www.gstatic.com/firebasejs/10.6.0/firebase-database.js";
    
    // TODO: Add SDKs for Firebase products that you want to use
    // https://firebase.google.com/docs/web/setup#available-libraries
  
    // Your web app's Firebase configuration
    // For Firebase JS SDK v7.20.0 and later, measurementId is optional
    const firebaseConfig = {
    apiKey: "AIzaSyCTMEsGU5_w8e_kXhn2fRIM_7UIYJcSn_A",
    authDomain: "prueba-ird41.firebaseapp.com",
    databaseURL: "https://prueba-ird41-default-rtdb.firebaseio.com",
    projectId: "prueba-ird41",
    storageBucket: "prueba-ird41.appspot.com",
    messagingSenderId: "263936402996",
    appId: "1:263936402996:web:dc6ef11b9aedde0f8e8c61",
    measurementId: "G-RZ2F4T90L3"
    };
  
    // Initialize Firebase
    const app = initializeApp(firebaseConfig);
    const analytics = getAnalytics(app);
    const database = getDatabase(app);

    const data = [
        { "id": 1, "name":"Jorge"},
        { "id": 2, "name":"Santiago"},
    ]

    data.map( (alumno) =>{

        set(ref(database, 'nombres/' + alumno.id), {
            'id':alumno.id,
            'name':alumno.name,
        });

    } );

    set(ref(database, 'alumnos/' + 1), {
        "id": 1,
        "nombre": "Jorge",
        "apellido": "Sánchez Cobos",
        "edad": 19
    });

    set(ref(database, 'alumnos/' + 2), {
        "id": 2,
        "nombre": "Santiago",
        "apellido": "Ledezma Cobos",
        "edad": 1
    });

  </script>

{% endblock %}
```

***ANTES QUE TODO, DEBEMOS COPIAR EL CÓDIGO ANTERIOMENTE GUARDADO EN UN TXT Y LO VAMOS A PEGAR Y TENDREMOS NUESTRO ARCHIVO YA CREADO***

2. Ahora creamos las vistas y urls en los archivos **views.py** y **urls.py** y colocamos lo siguiente:

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

def firebase (request):
  return render(request, 'firebase.html')
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

#FIREBASE
path('firebase/', firebase, name="firebase"),
```

**AL FINAL INICIAMOS EL SERVIDOR Y PROBAMOS CON LAS RUTAS MENCIONADAS ANTERIORMENTE Y VEREMOS QUE NUESTRO DOCUMENTO ESTA VACIO, PERO SI INSPECCIONAMOS EL CÓDIGO DE JAVASCRIPT VEREMOS QUE ESTA SIN ERROR Y SOLAMENTE QUEDA VER NUESTRO FIREBASE Y VEREMOS LOS DATOS QUE SE GUARDARON EXITOSAMENTE**

---

# CREACION DEL FORMULARIO DE FIREBASE

Ya que hayamos logrado la parte del firebase y ver que se registraron los datos en la base de datos, vamos a la parte de la creación del formulario, por ello vamos a crear un nuevo archivo en la misma ruta que la del firebase y se llamará **form-firebase.html** y colocamos el siguiente código:

```html
{% extends "layouts/layouts.html" %}
{% block title %} firebase {% endblock %}

{% block content %}

    <div class="container text-center">
        <div class="row align-items-center">
            <div class="col">
                <h1>Formulario de Firebase</h1>
                <code id="code"></code>
                <form id="form">

                    <div class="form-group row mt-2">  
                        <label for="email" class="col-sm-2 col-form-label">Email</label>
                        <input type="email" class="form-control" id="email">
                    </div>

                    <div class="form-group row mt-2">  
                        <label for="nombre" class="col-sm-2 col-form-label">Nombre</label>
                        <input type="text" class="form-control" id="nombre">
                    </div>

                    <div class="form-group row mt-2">  
                        <label for="apellidos" class="col-sm-2 col-form-label">Apellidos</label>
                        <input type="text" class="form-control" id="apellidos">
                    </div>

                    <div class="form-group row mt-2">  
                        <label for="edad" class="col-sm-2 col-form-label">Edad</label>
                        <input type="number" class="form-control" id="edad">
                    </div>

                    <button type="submit" class="btn btn-primary mb-2 mt-2">Enviar</button>

                </form>
            </div>
        </div>
    </div>

    <script type="module">
        // Import the functions you need from the SDKs you need
        import { initializeApp } from "https://www.gstatic.com/firebasejs/10.6.0/firebase-app.js";
        import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.6.0/firebase-analytics.js";
        import { getDatabase, ref, set, child, get } from "https://www.gstatic.com/firebasejs/10.6.0/firebase-database.js";
        
        // TODO: Add SDKs for Firebase products that you want to use
        // https://firebase.google.com/docs/web/setup#available-libraries
      
        // Your web app's Firebase configuration
        // For Firebase JS SDK v7.20.0 and later, measurementId is optional
        const firebaseConfig = {
            apiKey: "AIzaSyCTMEsGU5_w8e_kXhn2fRIM_7UIYJcSn_A",
            authDomain: "prueba-ird41.firebaseapp.com",
            databaseURL: "https://prueba-ird41-default-rtdb.firebaseio.com",
            projectId: "prueba-ird41",
            storageBucket: "prueba-ird41.appspot.com",
            messagingSenderId: "263936402996",
            appId: "1:263936402996:web:dc6ef11b9aedde0f8e8c61",
            measurementId: "G-RZ2F4T90L3"
        };
      
        // Initialize Firebase
        const app = initializeApp(firebaseConfig);
        const analytics = getAnalytics(app);
        const database = getDatabase(app);
        
        const codeAdd = (data) => {
            const code = document.getElementById("code");
            code.innerHTML = data;
        }

        const code = () => 
        {
            const dbRef = ref(getDatabase());
            get(child(dbRef, 'alumno/')).then((snapshot) => {
                if(snapshot.exists()) 
                {
                    codeAdd(JSON.stringify(snapshot.val()));                
                }
                else
                {
                    console.log("No hay información disponible");                
                }            
            }).catch((error) => {
                console.error(error);
            });
        }

        code();

    

        const form = document.getElementById("form");

        form.addEventListener("submit", (event) => {
            event.preventDefault();
            const date = Date.now();
            const email = document.getElementById("email").value;
            const nombre = document.getElementById("nombre").value;
            const apellidos = document.getElementById("apellidos").value;
            const edad = document.getElementById("edad").value;

            if(email !== "" && nombre !== "" && apellidos !== "" && edad !== "")
            {
                set(ref(database, 'alumno/' + date), {
                    'email': email,
                    'nombre': nombre,
                    'apellidos': apellidos,
                    'edad': edad
                });
                alert("Envio de información");
                window.location.reload();
            }
            else
            {
                alert("Datos faltantes");
            }
            
        });
    
        //const data = [
        //    { "id": 1, "name":"Alondra"},
        //    { "id": 2, "name":"Anel"},
        //]
    
        //data.map( (alumno) =>{
    
          //  set(ref(database, 'nombres/' + alumno.id), {
            //    'id':alumno.id,
              //  'name':alumno.name,
            //});
    
        //} );
    
        //set(ref(database, 'alumnos/' + 1), {
          //  "id": 1,
            //"nombre": "Anel",
//            "apellido": "Peña Vazquez",
  //          "edad": 19
    //    });
    
      //  set(ref(database, 'alumnos/' + 2), {
        //    "id": 2,
          //  "nombre": "Perla",
            //"apellido": "Peña Vazquez",
            //"edad": 19
        //});


    
      </script>

{% endblock %}
```

2. Solamente queda crear las vistas y rutas en **views.py** y **urls.py** y colocamos lo siguiente:

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

def form (request):
    return render(request, 'form-firebase.html')
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

#FIREBASE
path('form/', form),
```

**AL FINAL VAMOS A CREAR NUESTROS REGISTROS LLENANDO LA INFORMACIÓN Y VEREMOS QUE CUANDO LOS ENVIEMOS NOS DIRA QUE LOS DATOS FUERON ENVIADOS Y SE VAN A IMPRIMIR EN NUESTRO FORMULARIO LO QUE HEMOS CREADO Y LO TENDREMOS QUE VER EN NUESTRO FIREBASE Y CON ESTO TENDREMOS NUESTRO FORMULARIO FUNCIONAL**

---

# CAPTURAS DE FUNCIONALIDAD

- CREACION DEL PROYECTO DE FIREBASE

![](@attachment/Clipboard_2023-12-03-13-04-19.png)

![](@attachment/Clipboard_2023-12-03-13-05-14.png)

![](@attachment/Clipboard_2023-12-03-13-06-40.png)

![](@attachment/Clipboard_2023-12-03-13-07-02.png)

![](@attachment/Clipboard_2023-12-03-13-08-25.png)

![](@attachment/Clipboard_2023-12-03-13-10-07.png)

![](@attachment/Clipboard_2023-12-03-13-10-49.png)

![](@attachment/Clipboard_2023-12-03-13-11-40.png)

![](@attachment/Clipboard_2023-12-03-13-13-56.png)

![](@attachment/Clipboard_2023-12-03-13-18-21.png)

![](@attachment/Clipboard_2023-12-03-13-21-52.png)

![](@attachment/Clipboard_2023-12-03-13-23-43.png)

- CONFIGURACION DEL FIREBASE Y SU FORMULARIO (MOSTRANDO LA INFORMACIÓN ENVIADA)

- FUNCION DE FIREBASE.HTML

![](@attachment/Clipboard_2023-12-03-13-36-54.png)

![](@attachment/Clipboard_2023-12-03-13-37-08.png)

- FUNCION DE FORM-FIREBASE.HTML

![](@attachment/Clipboard_2023-12-03-13-43-01.png)

![](@attachment/Clipboard_2023-12-03-13-43-11.png)

![](@attachment/Clipboard_2023-12-03-13-43-24.png)


