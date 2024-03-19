---
title: 'UNIDAD 2.2: Instalación de Django en Windows/Linux'
created: '2023-12-02T20:57:40.651Z'
modified: '2023-12-02T21:35:50.715Z'
---

# UNIDAD 2.2: Instalación de Django en Windows/Linux

**Para instalar Django** *(ya sea en Windows o Linux)* **primero necesitamos instalar Python en su versión más reciente** *(3.11.6)*

---

# Instalacion de Django en Windows

1. Primero creamos la carpeta llamada **ProgramacionRedes** en el escritorio, luego vamos a la consola presionando **Windows + R** y escribimos en el recuadro la palabra **cmd** y nos abrirá la consola, después colocamos 
```bash
C:Users\usuario> cd Desktop 
C:Users\usuario\Desktop cd ProgramacionRedes
C:Users\usuario\Desktop\ProgramacionRedes> python -m pip venv env
C:Users\usuario\Desktop\ProgramacionRedes> cd env
C:Users\usuario\Desktop\ProgramacionRedes\env> cd Scripts
C:Users\usuario\Desktop\ProgramacionRedes\env\Scripts> activate
(env)C:Users\usuario\Desktop\ProgramacionRedes\env\Scripts> cd ..
(env)C:Users\usuario\Desktop\ProgramacionRedes\env> cd ..
(env)C:Users\usuario\Desktop\ProgramacionRedes>
```
***En caso de no funcionar con entrar en el Desktop, escribiremos lo siguiente:***
```bash
C:Users\usuario> cd OneDrive
C:Users\usuario\OneDrive> cd Escritorio
C:Users\usuario\OneDrive\Escritorio> cd ProgramacionRedes
C:Users\usuario\OneDrive\Escritorio\ProgramacionRedes> #Comienza la instalación en este espacio
```


2. Posterior, vamos a instalar Django con lo siguiente: 

```bash
(env)C:Users\usuario\Desktop\ProgramacionRedes> python -m pip install Django
(env)C:Users\usuario\Desktop\ProgramacionRedes> django-admin startproject mysite
(env)C:Users\usuario\Desktop\ProgramacionRedes> cd mysite
(env)C:Users\usuario\Desktop\ProgramacionRedes\mysite> python manage.py runserver
Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).
December 02, 2023 - 21:11:44
Django version 4.2.6, using settings 'programacion.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
```
3. Con esto ya tendremos instalado Django en nuestro Windows, para comprobar que funciona, en nuestrp navegador web podemos colocar la URL que nos proporciona Django que es **http://127.0.0.1:8000/** y listo

---

# Instalacion de Django en Linux

1. Haciendo lo mismo que Windows, vamos a crear una carpeta nuestro escritorio de nuestra distribución instalada de Linux, a esta carpeta la llamaremos **ProgramacionRedes**, posterior vamos a abrir la terminal con las teclas **Ctrl + Alt + T** y nos abrirá la terminal, posterior escribimos los siguientes comandos:

```bash
usuario@user:~$ cd Escritorio
usuario@user:~/Escritorio$ cd ProgramacionRedes
usuario@user:~/Escritorio/ProgramacionRedes$ 
```

2. Posterior dentro de la carpeta de ProgramacionRedes vamos a instalar Django con lo siguiente:

```bash
usuario@user:~/Escritorio/ProgramacionRedes$ python -m venv env
usuario@user:~/Escritorio/ProgramacionRedes$ source env/bin/activate
(env)usuario@user:~/Escritorio/ProgramacionRedes$ python -m pip install Django
(env)usuario@user:~/Escritorio/ProgramacionRedes$ django-admin startproject mysite
(env)usuario@user:~/Escritorio/ProgramacionRedes$ cd mysite
(env)usuario@user:~/Escritorio/ProgramacionRedes/mysite$ python manage.py runserver
Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).
December 02, 2023 - 21:11:44
Django version 4.2.6, using settings 'programacion.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
```
3. Con esto estará instalado Django en Linux, haciendo lo mismo de entrar a nuestro navegador web y colocar esa URL proporcionada **http://127.0.0.1:8000/**


