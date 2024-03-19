---
attachments: [Clipboard_2023-12-03-10-29-33.png, Clipboard_2023-12-03-10-29-49.png, Clipboard_2023-12-03-10-29-58.png, Clipboard_2023-12-03-10-30-14.png, Clipboard_2023-12-03-10-30-20.png, Clipboard_2023-12-03-10-30-28.png, Clipboard_2023-12-03-10-30-36.png, Clipboard_2023-12-03-10-31-42.png, Clipboard_2023-12-03-10-31-59.png, Clipboard_2023-12-03-10-32-10.png, Clipboard_2023-12-03-10-32-16.png, Clipboard_2023-12-03-10-32-22.png, Clipboard_2023-12-03-10-32-37.png, Clipboard_2023-12-03-10-32-45.png]
title: UNIDAD 3.2 CRUD con un formulario HTML para el admin de Django (Persona y Domicilio)
created: '2023-12-02T22:48:27.761Z'
modified: '2023-12-03T19:46:38.835Z'
---

# UNIDAD 3.2 CRUD con un formulario HTML para el admin de Django (Persona y Domicilio)

> Antes de hacer este famoso CRUD en un formulario de HTML, debemos recordar que anteriormente ya se realizo un CRUD en Django, pero ahora este lo haremos a través de un formulario donde podamos tanto crear, consultar, modificar y eliminar personas y domicilios sin utilizar la interfaz del administrador de Django,para ello vamos a comenzar a crea estos pasos sencillos.

* ***ANTES DE CREAR ESTE FORMULARIO, PRIMERO DEBEMOS CREAR NUESTRO MODELO DE DOMICILIO QUE AÚN NO EXISTE EN NUESTRO MODELO DE PERSONA, ASÍ QUE VAMOS A CREAR RAPIDAMENTE ESTE MODELO***

1. Primero vamos a la carpeta de **persona/models.py** y colocamos el código para crear el modelo de domicilio y de igual forma que el modelo de persona lo tenga presente

```py
from django.db import models

class Domicilio(models.Model):
    calle = models.CharField(max_length=255)
    no_calle = models.IntegerField()
    pais = models.CharField(max_length=255)
    objects = models.Manager()
    
    def __str__(self):
        return f"Domicilio: {self.calle} {self.no_calle} {self.pais}"

class Persona(models.Model):
    nombre = models.CharField(max_length=255)
    apellido = models.CharField(max_length=255)
    email = models.CharField(max_length=255)
    domicilio = models.ForeignKey(Domicilio, on_delete=models.SET_NULL, null=True)
    objects = models.Manager()
    
    def __str__(self) -> str:
        return f"Persona {self.id}: {self.nombre} {self.apellido} {self.email}"
```
Al igual que **admin.py**

```py
from django.contrib import admin
from persona.models import Domicilio, Persona


# Register your models here.
admin.site.register(Persona)
admin.site.register(Domicilio)
```
2. Dentro de nuestra consola/terminal vamos a escribir esta serie de instrucciones una vez que hayamos activado el enviroment de nuestro proyecto de Django, y colocamos las siguientes líneas

```bash
(env) usuario@user:~/Escritorio/ProgramacionRedes/mysite$ python manage.py makemigrations
# ESPERAREMOS A QUE NOS MUESTRE LA MIGRACIÓN DEL MODELO DE DOMICILIO
# CUANDO LO MUESTRE COLOCAMOS
(env) usuario@user:~/Escritorio/ProgramacionRedes/mysite$ python manage.py sqlmigrate persona 0002
# ESTO LO VA A GUARDAR EN OTRA MIGRACIÓN PROPUESTA Y QUE ES LIBRE DE COLOCAR, YA QUE SI USAMOS LA PRIMERA PUEDE BORRAR EL MODELO DE PERSONA Y ESO ESTARÍA FATAL, POR ELLO EN EL 0002
# CUANDO HAYA GUARDADO EN 0002 COLOCAMOS
(env) usuario@user:~/Escritorio/ProgramacionRedes/mysite$ python manage.py migrate
# MIGRARÁ EL MODELO EN EL ADMIN DE DJANGO Y AL FINAL LO TENDREMOS QUE MOSTRAR ACTIVANDO EL SERVIDOR Y VERLO CON LA RUTA admin/
```

**UNA VEZ CREADA ESTE MODELO, AHORA SÍ YA PODEMOS TRABAJAR EN CREAR NUESTRO FORMULARIO**

---

# CREACIÓN DE FORMULARIO CRUD EN HTML DEL MODELO DE PERSONA EN DJANGO


1. Primero debemos de crear esta prueba para el modelo de **Persona** por ello vamos a crear dentro de nuestra ruta **ProgramacionRedes/mysite/webapp/** crearemos una carpeta que se llame **persona-crud** y vamos a crear los siguientes archivos html con estas respectivas líneas de código:

- index.html
```html
{% extends "layouts/layouts.html" %}

{% block title %} index.html {% endblock %}

{% block content %} 
    
<div class="container text-center">
    <div class="row align-items-center">
        <div class="col">
            <h1>
                SAP CRUD
            </h1>
            <a class="btn btn-primary btn-sm" href="{% url 'crud-create' %}">Crear usuario</a>
        </div>
    </div>
    <div class="row align-items-center">
        <div class="col">
            <table class="table">
                <thead>
                    <th scope="col">Id</th>
                    <th scope="col">Nombre</th>
                    <th scope="col">Apellido</th>
                    <th scope="col">Email</th>
                    <th scope="col">Domicilio</th>
                    <th scope="col">Acciones</th>
                </thead>
                <tbody>
                    {% for register in registers %}
                    <tr>
                        <td>{{ register.id }}</td>
                        <td>{{ register.nombre }}</td>
                        <td>{{ register.apellido }}</td>
                        <td>{{ register.email }}</td>
                        <td>{{ register.domicilio }}</td>
                        <td>
                            <a 
                                class="btn btn-warning btn-sm"
                                href="{% url 'crud-show' register.id %}"
                            >
                                Ver detalles
                            </a>
                        </td>
                        <td>
                            <a 
                                class="btn btn-success btn-sm"
                                href="{% url 'crud-edit' register.id %}"
                            >
                                Editar registro
                            </a>
                        </td>
                        <td>
                            <a 
                                class="btn btn-danger btn-sm"
                                href="{% url 'crud-delete' register.id %}"
                            >
                                Eliminar registro
                            </a>
                        </td>
                    </tr>
                  {% endfor %}
                </tbody>
            </table>
        </div>
    </div>
</div>

{% endblock %}
```

- create.html
```html
{% extends "layouts/layouts.html" %}

{% block title %} index.html {% endblock %}

{% block content %} 
    
<div class="container text-center">
    <div class="col">
        <h1>SAP CRUD</h1>
    </div>
    <div class="row align-items-center">
        <div class="row align-items-center w-50 p-3 position-absolute top-50 start-50 translate-middle">
            <form method="POST" action="{% url 'crud-store' %}">
                {% csrf_token %}
                <div class="form-grup">
                    <label for="Nombre">Nombre</label>
                    <input 
                        type="text"
                        class="form-control"
                        name="nombre"
                        placeholder="Nombre"
                        >
                </div>
                <div class="form-grup">
                    <label for="Apellido">Apellido</label>
                    <input 
                        type="text"
                        class="form-control"
                        name="apellido"
                        placeholder="Apellido"
                        >
                </div>
                <div class="form-grup">
                    <label for="Email">Email</label>
                    <input 
                        type="text"
                        class="form-control"
                        name="email"
                        placeholder="Emali"
                        >
                </div>
                <div class="form-grup">
                    <label for="Nombre">Domicilio</label>
                    <select class="form-control" 
                        name="domicilio"
                        >
                            <option selected>Elegir domicilio</option>
                            {% for register in registers_domicilios %}
                            <option value="{{ register.id }}">{{ register }}</option>
                            {% endfor %}
                    </select>
                </div>
                <div class="form-grup p-2">
                    <button 
                        type="submit"
                        class="btn btn-primary">
                         Registrar
                    </button>
                    <a href="{% url 'crud-index' %}"
                >
                    Regresar
                </a>
                </div>
            </form>
        </div>
    </div>
</div>

{% endblock %}
```

- show.html
```html
{% extends "layouts/layouts.html" %}

{% block title %} show.html {% endblock %}

{% block content %} 
    
    <div class="container text-center">
        <div class="row align-items-center">
            <div class="col">
                <h1>
                    SAP CRUD
                </h1>
            </div>
        </div>
        <div class="row align-items-center">
            <div class="col">
                <form method="POST" action="{% url 'crud-show' register_persona.id%}">
                    {% csrf_token %}
                    <div class="form-group">
                        <label for="Nombre">Nombre</label>
                        <input 
                            type="text"
                            class="form-control"
                            name="nombre"
                            value="{{register_persona.nombre}}"
                            readonly
                        >
                    </div>
                    <div class="form-group">
                        <label for="Apellido">Apellido</label>
                        <input 
                            type="text"
                            class="form-control"
                            name="apellido"
                            value="{{register_persona.apellido}}" 
                            readonly                           
                        >
                    </div>
                    <div class="form-group">
                        <label for="Email">Email</label>
                        <input 
                            type="text"
                            class="form-control"
                            name="email"
                            value="{{register_persona.email}}"
                            readonly
                        >
                    </div>
                    <div class="form-group">
                        <label for="Domicilio">Domicilio</label>
                        <select 
                            class="form-control"
                            name="domicilio"     
                            disabled                   
                        >
                            <option selected>Elegir domicilio:</option>
                            {% for register in registers_domicilios %}
                                <option 
                                    value="{{ register.id }}"
                                    {% if register.id == register_persona.domicilio.id %}
                                        selected = "selected"
                                    {% endif %}                                    
                                >
                                    {{ register }}
                                </option>
                            {% endfor %}
                        </select>
                    </div>                    
                </form>
                <a href="{% url 'crud-index' %}"
                >
                    Regresar
                </a>
            </div>
        </div>
    </div>

{% endblock %}
```

- edit.html
```html
{% extends "layouts/layouts.html" %}

{% block title %} edit.html {% endblock %}

{% block content %} 
    
    <div class="container text-center">
        <div class="row align-items-center">
            <div class="col">
                <h1>
                    SAP CRUD
                </h1>
            </div>
        </div>
        <div class="row align-items-center">
            <div class="col">
                <form method="POST" action="{% url 'crud-update' register_persona.id %}">
                    {% csrf_token %}
                    <div class="form-group">
                        <label for="Nombre">Nombre</label>
                        <input 
                            type="text"
                            class="form-control"
                            name="nombre"
                            value="{{register_persona.nombre}}"
                        >
                    </div>
                    <div class="form-group">
                        <label for="Apellido">Apellido</label>
                        <input 
                            type="text"
                            class="form-control"
                            name="apellido"
                            value="{{register_persona.apellido}}"
                        >
                    </div>
                    <div class="form-group">
                        <label for="Email">Email</label>
                        <input 
                            type="text"
                            class="form-control"
                            name="email"
                            value="{{register_persona.email}}"
                        >
                    </div>
                    <div class="form-group">
                        <label for="Domicilio">Domicilio</label>
                        <select 
                            class="form-control"
                            name="domicilio"
                        >
                            <option selected>Elegir domicilio:</option>
                            {% for register in registers_domicilios %}
                                <option 
                                    value="{{ register.id }}"
                                    {% if register.id == register_persona.domicilio.id %}
                                        selected = "selected"
                                    {% endif %}
                                >
                                    {{ register }}
                                </option>
                            {% endfor %}
                        </select>
                    </div>
                    <button
                        type="submit"
                        class="btn btn-primary mt-1"
                    >
                        Actualizar registros
                    </button>
                </form>
                <a href="{% url 'crud-index' %}"
                >
                    Regresar
                </a>
            </div>
        </div>
    </div>

{% endblock %}
```

> ***NOTA: EN LA PARTE DEL INDEX.HTML SE DARÁN CUENTA DE QUE HAY UN BOTON QUE SE LLAMA "ELIMINAR REGISTRO" EN ESE BOTON NO ME ENVIARÁ A UN HTML EN CONCRETO, SI NO QUE BORRARÁ EL REGISTRO DE FORMA AUTOMÁTICA EN EL INDEX***

2. Ahora si nosotros vemos este formulario, nos dará error al momento de mostrarlo porque no mostrará alguna acción dentro del mismo, por ello vamos a la parte de nuestra ruta de **ProgramacionRedes/mysite/webapp/views.py** y colocaremos el siguiente código:
```py
from django.shortcuts import render
from django.http import HttpResponse
from persona.models import Persona as PersonaModel
from persona.models import Domicilio as DomicilioModel
from django.shortcuts import redirect

#CRUD PERSONA
def index_crud(request):
    no_register = PersonaModel.objects.count()
    registers = PersonaModel.objects.all()
    return render(request, 'persona-crud/index.html', {'no_register':no_register, 'registers': registers})

def crud_create(request):
    registers_domicilios = DomicilioModel.objects.all()
    return render(request, 'persona-crud/create.html', {'registers_domicilios':registers_domicilios})

def crud_store(request):
    if request.method == "POST":
        new_persona = PersonaModel(nombre=request.POST["nombre"], email=request.POST["email"], apellido=request.POST["apellido"])
        new_persona.save()
        return redirect('crud-index')
    
def crud_edit(request, id):
    registers_domicilios = DomicilioModel.objects.all()
    register_persona = PersonaModel.objects.get(pk=id)
    return render(request, 'persona-crud/edit.html', {'registers_domicilios':registers_domicilios, 'register_persona':register_persona})

def crud_show(request, id):
    registers_domicilios = DomicilioModel.objects.all()
    register_persona = PersonaModel.objects.get(pk=id)
    return render(request, 'persona-crud/show.html', {'registers_domicilios':registers_domicilios, 'register_persona':register_persona})

def crud_update(request, id):
    if request.method == "POST":
        register_domicilio = DomicilioModel.objects.get(pk=request.POST["domicilio"])
        register_persona = PersonaModel.objects.get(pk=id)
        register_persona.nombre = request.POST["nombre"]
        register_persona.apellido = request.POST["apellido"]
        register_persona.email = request.POST["email"]
        register_persona.domicilio = register_domicilio
        register_persona.save()
        return redirect('crud-index')

def crud_delete(request, id):
    register_persona = PersonaModel.objects.get(pk=id)
    register_persona.delete()
    return redirect('crud-index')
```

+ index_crud: Permite que podamos ver todo el contenido de la persona/domicilio y los pueda mostrar como una forma de consulta predeterminada en el documento de **persona-crud/index.html**
+ crud_create: Permite poder crear tanto personas/domicilios en nuestro formulario y los guardará en el documento **index.html**
+ crud_store: Permite hacer la parte de la validación de la creacion de personas/domicilios con lo cual será sencillo de hacer rápido sin mandar a llamar ningun otro documento HTML
+ crud_edit: Permite hacer la modificación de nuestros datos para mandarlos a llamar y mostrar lo que quiere cambiar utilizando el ID en HTML 
+ crud_show: Solamente permite visualizar el contenido de nuestra persona/domicilio a modificar o eliminar
+ crud_update: Hace la parte de validación de nuestro **crud_edit** para que se pudean actualizar con el ID aplicado
+ crud_delete; Solamente hace la parte de eliminar todo el registro tanto creado como ya modificado de nuestra persona/domicilio en el HTML

3. Una vez explicados y creados nuestras funciones que harán funcionar al formulario, vamos a crear las URL's asignadas en la parte de **ProgramacionRedes/mysite/mysite/urls.py** y colocaremos lo siguiente

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

#INDEX CRUD
    path('persona-crud/index', index_crud, name="crud-index"),
    #CREATE CRUD
    path('persona-crud/create', crud_create, name="crud-create"),
    #STORE CRUD
    path('persona-crud/store', crud_store, name="crud-store"),
    #EDIT CRUD
    path('persona-crud/edit/<int:id>', crud_edit, name="crud-edit"),
    #UPDATE CRUD
    path('persona-crud/update/<int:id>', crud_update, name="crud-update"),
    #SHOW CRUD
    path('persona-crud/show/<int:id>', crud_show, name="crud-show"),
    #DELETE CRUD
    path('persona-crud/delete/<int:id>', crud_delete, name="crud-delete"),
```

**UNA VEZ YA CREADA ESTA PARTE, INICIAMOS NUESTRO SERVIDOR Y ABRIMOS LA PARTE DE persona-crud/index PARA QUE MUESTRE EL INDEX PRINCIPAL CON LAS PERSONAS YA CREADAS DE NUESTRO MODELO DE PERSONA**

---

# CREACIÓN DE FORMULARIO CRUD EN HTML DEL MODELO DE DOMICILIO EN DJANGO

1. Solamente haremos la parte de la misma copía de nuestro modelo persona en el HTML, pero en lugar de la carpeta **persona-crud** será **domicilio-crud** y copiamos lo siguiente:

- index-domicilio.html
```html
{% extends "layouts/layouts.html" %}

{% block title %} index.html {% endblock %}

{% block content %} 
    
<div class="container text-center">
    <div class="row align-items-center">
        <div class="col">
            <h1>
                SAP CRUD
            </h1>
            <a class="btn btn-primary btn-sm" href="{% url 'crud-create-domicilio' %}"> Crear domicilio</a>
        </div>
    </div>
    <div class="row align-items-center">
        <div class="col">
            <table class="table">
                <thead>
                    <th scope="col">Id</th>
                    <th scope="col">Calle</th>
                    <th scope="col">No_calle</th>
                    <th scope="col">Pais</th>                    
                    <th scope="col">Acciones</th>
                </thead>
                <tbody>
                    {% for register in registers %}
                    <tr>
                        <td>{{ register.id }}</td>
                        <td>{{ register.calle }}</td>
                        <td>{{ register.no_calle }}</td>
                        <td>{{ register.pais }}</td>                        
                        <td>
                            <a 
                                class="btn btn-warning btn-sm"
                                href="{% url 'crud-show-domicilio' register.id %}"
                            >
                                Ver detalles
                            </a>
                        </td>
                        <td>
                            <a 
                                class="btn btn-success btn-sm"
                                href="{% url 'crud-edit-domicilio' register.id %}"
                            >
                                Editar registro
                            </a>
                        </td>
                        <td>
                            <a 
                                class="btn btn-danger btn-sm"
                                href="{% url 'crud-delete-domicilio' register.id %}"
                            >
                                Eliminar registro
                            </a>
                        </td>
                    </tr>
                  {% endfor %}
                </tbody>
            </table>
        </div>
    </div>
</div>

{% endblock %}
```

- create-domicilio.html
```html
{% extends "layouts/layouts.html" %}

{% block title %} index.html {% endblock %}

{% block content %} 
    
<div class="container text-center">
    <div class="col">
        <h1>SAP CRUD</h1>
    </div>
    <div class="row align-items-center">
        <div class="row align-items-center w-50 p-3 position-absolute top-50 start-50 translate-middle">
            <form method="POST" action="{% url 'crud-store-domicilio' %}">
                {% csrf_token %}
                <div class="form-grup">
                    <label for="Nombre">Calle</label>
                    <input 
                        type="text"
                        class="form-control"
                        name="calle"
                        placeholder="Calle"
                        >
                </div>
                <div class="form-grup">
                    <label for="Apellido">No calle</label>
                    <input 
                        type="text"
                        class="form-control"
                        name="no_calle"
                        placeholder="No calle"
                        >
                </div>
                <div class="form-grup">
                    <label for="Email">Pais</label>
                    <input 
                        type="text"
                        class="form-control"
                        name="pais"
                        placeholder="Pais"
                        >
                </div>            
                <div class="form-grup p-2">
                    <button 
                        type="submit"
                        class="btn btn-primary">
                         Registrar
                    </button>
                    <a href="{% url 'crud-index-domicilio' %}"
                >
                    Regresar
                </a>
                </div>
---
attachments: [Clipboard_2023-12-03-10-29-33.png, Clipboard_2023-12-03-10-29-49.png, Clipboard_2023-12-03-10-29-58.png, Clipboard_2023-12-03-10-30-14.png, Clipboard_2023-12-03-10-30-20.png, Clipboard_2023-12-03-10-30-28.png, Clipboard_2023-12-03-10-30-36.png, Clipboard_2023-12-03-10-31-42.png, Clipboard_2023-12-03-10-31-59.png, Clipboard_2023-12-03-10-32-10.png, Clipboard_2023-12-03-10-32-16.png, Clipboard_2023-12-03-10-32-22.png, Clipboard_2023-12-03-10-32-37.png, Clipboard_2023-12-03-10-32-45.png]
title: UNIDAD 3.2 CRUD con un formulario HTML para el admin de Django (Persona y Domicilio)
created: '2023-12-02T22:48:27.761Z'
modified: '2023-12-03T19:46:38.835Z'
---

# UNIDAD 3.2 CRUD con un formulario HTML para el admin de Django (Persona y Domicilio)

> Antes de hacer este famoso CRUD en un formulario de HTML, debemos recordar que anteriormente ya se realizo un CRUD en Django, pero ahora este lo haremos a través de un formulario donde podamos tanto crear, consultar, modificar y eliminar personas y domicilios sin utilizar la interfaz del administrador de Django,para ello vamos a comenzar a crea estos pasos sencillos.

* ***ANTES DE CREAR ESTE FORMULARIO, PRIMERO DEBEMOS CREAR NUESTRO MODELO DE DOMICILIO QUE AÚN NO EXISTE EN NUESTRO MODELO DE PERSONA, ASÍ QUE VAMOS A CREAR RAPIDAMENTE ESTE MODELO***

1. Primero vamos a la carpeta de **persona/models.py** y colocamos el código para crear el modelo de domicilio y de igual forma que el modelo de persona lo tenga presente

```py
from django.db import models

class Domicilio(models.Model):
    calle = models.CharField(max_length=255)
    no_calle = models.IntegerField()
    pais = models.CharField(max_length=255)
    objects = models.Manager()
    
    def __str__(self):
        return f"Domicilio: {self.calle} {self.no_calle} {self.pais}"

class Persona(models.Model):
    nombre = models.CharField(max_length=255)
    apellido = models.CharField(max_length=255)
    email = models.CharField(max_length=255)
    domicilio = models.ForeignKey(Domicilio, on_delete=models.SET_NULL, null=True)
    objects = models.Manager()
    
    def __str__(self) -> str:
        return f"Persona {self.id}: {self.nombre} {self.apellido} {self.email}"
```
Al igual que **admin.py**

```py
from django.contrib import admin
from persona.models import Domicilio, Persona


# Register your models here.
admin.site.register(Persona)
admin.site.register(Domicilio)
```
2. Dentro de nuestra consola/terminal vamos a escribir esta serie de instrucciones una vez que hayamos activado el enviroment de nuestro proyecto de Django, y colocamos las siguientes líneas

```bash
(env) usuario@user:~/Escritorio/ProgramacionRedes/mysite$ python manage.py makemigrations
# ESPERAREMOS A QUE NOS MUESTRE LA MIGRACIÓN DEL MODELO DE DOMICILIO
# CUANDO LO MUESTRE COLOCAMOS
(env) usuario@user:~/Escritorio/ProgramacionRedes/mysite$ python manage.py sqlmigrate persona 0002
# ESTO LO VA A GUARDAR EN OTRA MIGRACIÓN PROPUESTA Y QUE ES LIBRE DE COLOCAR, YA QUE SI USAMOS LA PRIMERA PUEDE BORRAR EL MODELO DE PERSONA Y ESO ESTARÍA FATAL, POR ELLO EN EL 0002
# CUANDO HAYA GUARDADO EN 0002 COLOCAMOS
(env) usuario@user:~/Escritorio/ProgramacionRedes/mysite$ python manage.py migrate
# MIGRARÁ EL MODELO EN EL ADMIN DE DJANGO Y AL FINAL LO TENDREMOS QUE MOSTRAR ACTIVANDO EL SERVIDOR Y VERLO CON LA RUTA admin/
```

**UNA VEZ CREADA ESTE MODELO, AHORA SÍ YA PODEMOS TRABAJAR EN CREAR NUESTRO FORMULARIO**

---

# CREACIÓN DE FORMULARIO CRUD EN HTML DEL MODELO DE PERSONA EN DJANGO


1. Primero debemos de crear esta prueba para el modelo de **Persona** por ello vamos a crear dentro de nuestra ruta **ProgramacionRedes/mysite/webapp/** crearemos una carpeta que se llame **persona-crud** y vamos a crear los siguientes archivos html con estas respectivas líneas de código:

- index.html
```html
{% extends "layouts/layouts.html" %}

{% block title %} index.html {% endblock %}

{% block content %} 
    
<div class="container text-center">
    <div class="row align-items-center">
        <div class="col">
            <h1>
                SAP CRUD
            </h1>
            <a class="btn btn-primary btn-sm" href="{% url 'crud-create' %}">Crear usuario</a>
        </div>
    </div>
    <div class="row align-items-center">
        <div class="col">
            <table class="table">
                <thead>
                    <th scope="col">Id</th>
                    <th scope="col">Nombre</th>
                    <th scope="col">Apellido</th>
                    <th scope="col">Email</th>
                    <th scope="col">Domicilio</th>
                    <th scope="col">Acciones</th>
                </thead>
                <tbody>
                    {% for register in registers %}
                    <tr>
                        <td>{{ register.id }}</td>
                        <td>{{ register.nombre }}</td>
                        <td>{{ register.apellido }}</td>
                        <td>{{ register.email }}</td>
                        <td>{{ register.domicilio }}</td>
                        <td>
                            <a 
                                class="btn btn-warning btn-sm"
                                href="{% url 'crud-show' register.id %}"
                            >
                                Ver detalles
                            </a>
                        </td>
                        <td>
                            <a 
                                class="btn btn-success btn-sm"
                                href="{% url 'crud-edit' register.id %}"
                            >
                                Editar registro
                            </a>
                        </td>
                        <td>
                            <a 
                                class="btn btn-danger btn-sm"
                                href="{% url 'crud-delete' register.id %}"
                            >
                                Eliminar registro
                            </a>
                        </td>
                    </tr>
                  {% endfor %}
                </tbody>
            </table>
        </div>
    </div>
</div>

{% endblock %}
```

- create.html
```html
{% extends "layouts/layouts.html" %}

{% block title %} index.html {% endblock %}

{% block content %} 
    
<div class="container text-center">
    <div class="col">
        <h1>SAP CRUD</h1>
    </div>
    <div class="row align-items-center">
        <div class="row align-items-center w-50 p-3 position-absolute top-50 start-50 translate-middle">
            <form method="POST" action="{% url 'crud-store' %}">
                {% csrf_token %}
                <div class="form-grup">
                    <label for="Nombre">Nombre</label>
                    <input 
                        type="text"
                        class="form-control"
                        name="nombre"
                        placeholder="Nombre"
                        >
                </div>
                <div class="form-grup">
                    <label for="Apellido">Apellido</label>
                    <input 
                        type="text"
                        class="form-control"
                        name="apellido"
                        placeholder="Apellido"
                        >
                </div>
                <div class="form-grup">
                    <label for="Email">Email</label>
                    <input 
                        type="text"
                        class="form-control"
                        name="email"
                        placeholder="Emali"
                        >
                </div>
                <div class="form-grup">
                    <label for="Nombre">Domicilio</label>
                    <select class="form-control" 
                        name="domicilio"
                        >
                            <option selected>Elegir domicilio</option>
                            {% for register in registers_domicilios %}
                            <option value="{{ register.id }}">{{ register }}</option>
                            {% endfor %}
                    </select>
                </div>
                <div class="form-grup p-2">
                    <button 
                        type="submit"
                        class="btn btn-primary">
                         Registrar
                    </button>
                    <a href="{% url 'crud-index' %}"
                >
                    Regresar
                </a>
                </div>
            </form>
        </div>
    </div>
</div>

{% endblock %}
```

- show.html
```html
{% extends "layouts/layouts.html" %}

{% block title %} show.html {% endblock %}

{% block content %} 
    
    <div class="container text-center">
        <div class="row align-items-center">
            <div class="col">
                <h1>
                    SAP CRUD
                </h1>
            </div>
        </div>
        <div class="row align-items-center">
            <div class="col">
                <form method="POST" action="{% url 'crud-show' register_persona.id%}">
                    {% csrf_token %}
                    <div class="form-group">
                        <label for="Nombre">Nombre</label>
                        <input 
                            type="text"
                            class="form-control"
                            name="nombre"
                            value="{{register_persona.nombre}}"
                            readonly
                        >
                    </div>
                    <div class="form-group">
                        <label for="Apellido">Apellido</label>
                        <input 
                            type="text"
                            class="form-control"
                            name="apellido"
                            value="{{register_persona.apellido}}" 
                            readonly                           
                        >
                    </div>
                    <div class="form-group">
                        <label for="Email">Email</label>
                        <input 
                            type="text"
                            class="form-control"
                            name="email"
                            value="{{register_persona.email}}"
                            readonly
                        >
                    </div>
                    <div class="form-group">
                        <label for="Domicilio">Domicilio</label>
                        <select 
                            class="form-control"
                            name="domicilio"     
                            disabled                   
                        >
                            <option selected>Elegir domicilio:</option>
                            {% for register in registers_domicilios %}
                                <option 
                                    value="{{ register.id }}"
                                    {% if register.id == register_persona.domicilio.id %}
                                        selected = "selected"
                                    {% endif %}                                    
                                >
                                    {{ register }}
                                </option>
                            {% endfor %}
                        </select>
                    </div>                    
                </form>
                <a href="{% url 'crud-index' %}"
                >
                    Regresar
                </a>
            </div>
        </div>
    </div>

{% endblock %}
```

