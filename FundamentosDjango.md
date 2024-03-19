---
attachments: [Clipboard_2023-12-02-15-55-26.png, Clipboard_2023-12-02-15-55-41.png, Clipboard_2023-12-02-15-55-50.png, Clipboard_2023-12-02-15-55-56.png]
title: 'UNIDAD 2.3: Fundamentos de Django'
created: '2023-12-02T21:26:49.146Z'
modified: '2023-12-02T22:16:29.984Z'
---

# UNIDAD 2.3: Fundamentos de Django

Cuando se haya instalado Django (sea en Windows o Linux), vamos a realizar la actividad sencilla para pruebas de como funciona la parte de Django:

1. Primero vamos a crear una nueva aplicación en nuestro proyecto de Django, con esto lo haremos con lo siguiente
  - Windows
  ```bash
  C:Users\usuario> cd Desktop 
  C:Users\usuario\Desktop cd ProgramacionRedes
  C:Users\usuario\Desktop\ProgramacionRedes> cd env
  C:Users\usuario\Desktop\ProgramacionRedes\env> cd Scripts
  C:Users\usuario\Desktop\ProgramacionRedes\env\Scripts> activate
  (env)C:Users\usuario\Desktop\ProgramacionRedes\env\Scripts> cd ..
  (env)C:Users\usuario\Desktop\ProgramacionRedes\env> cd ..
  (env)C:Users\usuario\Desktop\ProgramacionRedes> cd mysite 
  (env)C:Users\usuario\Desktop\ProgramacionRedes\mysite> python manage.py startapp webapp
  (env)C:Users\usuario\Desktop\ProgramacionRedes\mysite> cd webapp
  (env)C:Users\usuario\Desktop\ProgramacionRedes\mysite\webapp> 
  ```

  - Linux
  ```bash
  usuario@user:~$ cd Escritorio
  usuario@user:~/Escritorio$ cd ProgramacionRedes
  usuario@user:~/Escritorio/ProgramacionRedes$ source env/bin/activate
  (env)usuario@user:~/Escritorio/ProgramacionRedes$ cd mysite
  (env)usuario@user:~/Escritorio/ProgramacionRedes/mysite$ python manage.py startapp webapp
  (env)usuario@user:~/Escritorio/ProgramacionRedes/mysite$ cd webapp
  (env)usuario@user:~/Escritorio/ProgramacionRedes/mysite/webapp$ 
  ```

2. Posterior vamos a abrir en nuestro editor de código preferido *(Sublime Text 3, Visual Studio Code, nvim, etc)* posterior vamos a abrir las carpetas de **mysite/ y webapp/**

3. Abrimos el archivo de la ruta **ProgramacionRedes/mysite/webapp/views.py** y configuramos lo siguiente:

```py
from django.shortcuts import render
from django.http import HttpResponse

def sumar( request, param1, param2 ):
    resultado = param1 + param2
    cadena = f"El resultado de la suma es: {resultado}"
    return HttpResponse(cadena) 

def restar (request, param1, param2 ):
    resultado = param1 - param2
    cadena = f"El resultado de la resta es: {resultado}"
    return HttpResponse(cadena) 

def multiplicar(request, param1, param2 ):
    resultado = param1 * param2
    cadena = f"El resultado de la multiplicación es: {resultado}"
    return HttpResponse(cadena)

def dividir(request, param1, param2 ):
    resultado = param1 / param2
    cadena = f"El resultado de la division es: {resultado}"
    return HttpResponse(cadena)

# Create your views here.
```

4. Ahora abrimos el archivo de la ruta **ProgramacionRedes/mysite/mysite/urls.py** y configuramos lo siguiente:

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

urlpatterns = [
    path('admin/', admin.site.urls),    
    path('sumar/<int:param1>/<int:param2>',sumar), 
    path('restar/<int:param1>/<int:param2>', restar),
    path('multiplicar/<int:param1>/<int:param2>',multiplicar), 
    path('dividir/<int:param1>/<int:param2>', dividir),

]

```

5. Para probar que funciona, vamos a iniciar el servidor con el comando: ```python manage.py runserver``` (siempre y cuando en enviroment este activado)

---

# CAPTURAS DEL FUNCIONAMIENTO

![](@attachment/Clipboard_2023-12-02-15-55-26.png)
![](@attachment/Clipboard_2023-12-02-15-55-41.png)
![](@attachment/Clipboard_2023-12-02-15-55-50.png)
![](@attachment/Clipboard_2023-12-02-15-55-56.png)




