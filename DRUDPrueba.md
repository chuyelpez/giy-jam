---
attachments: [Clipboard_2023-12-02-16-00-40.png, Clipboard_2023-12-02-16-00-53.png, Clipboard_2023-12-02-16-01-38.png]
title: 'UNIDAD 2.4: CRUD con prueba de modelo (migraciones y PostgresSQL)'
created: '2023-12-02T21:56:06.690Z'
modified: '2023-12-02T22:01:38.537Z'
---

# UNIDAD 2.4: CRUD con prueba de modelo (migraciones y PostgresSQL)

>PostgreSQL, también llamado Postgres, es un sistema de gestión de bases de datos relacional orientado a objetos y de código abierto, publicado bajo la licencia PostgreSQL,​ similar a la BSD o la MIT.
Como muchos otros proyectos de código abierto, el desarrollo de PostgreSQL no es manejado por una empresa o persona, sino que es dirigido por una comunidad de desarrolladores que trabajan de forma desinteresada, altruista, libre o apoyados por organizaciones comerciales. Dicha comunidad es denominada el PGDG (PostgreSQL Global Development Group).
PostgreSQL no tiene un gestor de errores (bugs), haciendo muy difícil conocer el estado de corrección de los mismos.

## Configuración de PostgreSQL en Django

Se realiza la siguente configuración el archivo mysite\mysite\settings.py
>1.- Se comentará la configuración por defecto de Django con Sqlite3
```py
  """
  DATABASES = {
    'default': {
      'EGINE' : 'django.db.backends.sqllite3',
      'NAME'  : BASE_DIR / 'db.sqlite3',
    }
  }
  """
```

**2.- Crear base de datos "sap_db", apoyarse en el vídeo para crear base de datos**

>3.- Se añadirá la nueva configuración, para el uso de PostgreSQL
```py
  DATABASES = {
      'default': {
          'ENGINE': 'django.db.backends.postgresql_psycopg2',
          'NAME': 'sap_db',
          'USER': 'najimi', # postgres # En el caso de windows
          'PASSWORD': 'pass', # contraseña de postgresql
          'HOST': 'localhost',
          'PORT': '5432'
      }
  }
```

>4.- Instalación de pyscopg2 en virtual env
```bash
(env) $ python -m pip install psycopg2-binary
```

>5.- Mostrar migraciones predeterminadas en Django
```bash
(env) $ python manage.py showmigrations
```

>6.- Exportar migraciones predeterminadas
```bash
(env) $ python manage.py migrate
```

>7.- Revisar tablas creadas en la base de datos en PGAdmin

>8.- Crear nueva aplicación encargada de gestionar personas (Sistema de Administración de Personas)
```bash
(env) $ python manage.py startapp persona
```
>9.- Registrar aplicación de personas dentro del archivo mysite\mysite\settings.py como se muestra a continuación
```python
  INSTALLED_APPS = [
      'django.contrib.admin',
      'django.contrib.auth',
      'django.contrib.contenttypes',
      'django.contrib.sessions',
      'django.contrib.messages',
      'django.contrib.staticfiles',
      'webapp',
      'persona'
  ]
```

>10.- Crear modelo de personas dentro de nuestro aplicativo, configurando el archivo: mysite/persona/models.py como se muestra a continuación
```python
from django.db import models

# Create your models here.
class Persona(models.Model):
    nombre = models.CharField(max_length=255)
    apellido = models.CharField(max_length=255)
    email = models.CharField(max_length=255)
    
    def __str__(self) -> str:
        return f"Persona {self.id}: {self.nombre} {self.apellido} {self.email}"
```

>11.- Configurar nuevas migraciones a partir del nuevo Modelo configurado
```bash
(env) $ python manage.py makemigrations
```

>12.- Visualizar código SQL que se va interpretar a base de nuestro modelo
```bash
(env) $ python manage.py sqlmigrate persona 0001
```

>13.- Aplicar nueva migración
```bash
(env) $ python manage.py migrate
```

>14.- Crear super usuario ingresando los datos solicitados, para el acceso de nuestro proyecto en la ruta:
localhost:8000/admin

```bash
(env) $ python manage.py createsuperuser
```

>15.- Registrar clase de personas, para uso en admin, en el archivo mysite/persona/admin.py
```python
from django.contrib import admin
from personas.models import Persona


# Register your models here.
admin.site.register(Persona)
```

>16.- Iniciar servidor de Django, 
dirigirse a la ruta: localhost:8000/admin
ingresar nombre de usuario y contraseña, registrado en createsuperuser
```bash
(env) $ python manage.py runserver
```

---

# CAPTURAS DE FUNCIONAMIENTO

![](@attachment/Clipboard_2023-12-02-16-00-40.png)
![](@attachment/Clipboard_2023-12-02-16-00-53.png)
![](@attachment/Clipboard_2023-12-02-16-01-38.png)
