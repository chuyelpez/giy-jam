---
attachments: [Clipboard_2023-12-03-16-32-23.png, Clipboard_2023-12-03-16-32-33.png, Clipboard_2023-12-03-16-32-43.png, Clipboard_2023-12-03-16-32-51.png]
title: 'UNIDAD 3.5: EXAMEN FINAL - USO DE UN API USANDO METODOS GET, POST, PUT Y DELETE EN POSTMAN'
created: '2023-12-03T19:44:18.513Z'
modified: '2023-12-03T22:32:51.802Z'
---

# UNIDAD 3.5: EXAMEN FINAL - USO DE UN API USANDO METODOS GET, POST, PUT Y DELETE EN POSTMAN

> Postman es una plataforma de colaboración para el desarrollo de API (Interfaz de Programación de Aplicaciones). Se utiliza para simplificar el proceso de desarrollo, prueba y documentación de API. Postman ofrece varias herramientas y características que facilitan a los desarrolladores la creación, prueba y gestión de solicitudes HTTP relacionadas con sus API.

Una vez entendida la parte de como trabajar con Postman, vamos a realizar con una simple API la parte del GET (obtener), POST (enviar), PUT (poner) y DELETE (eliminar), así que vamos a ir paso a paso con lo siguiente:

**ANTES TENEMOS QUE INSTALAR POSTMAN EN WINDOWS/LINUX EN NUESTRO DISPOSITIVO**

- Windows:

> Visita el sitio web oficial de Postman: https://www.postman.com/downloads/. En la página de descargas, elige la versión de Postman adecuada para Windows y haz clic en el botón de descarga. Una vez que se complete la descarga, abre el archivo de instalación (generalmente tiene una extensión .exe). Sigue las instrucciones del instalador. Puedes seleccionar las opciones de instalación predeterminadas o personalizadas según tus preferencias. Después de completar la instalación, deberías tener un acceso directo a Postman en tu menú de inicio o en el escritorio. También puedes buscar "Postman" en el menú de inicio para encontrarlo. Inicia Postman haciendo clic en su icono.

- Linux:

```bash
sudo apt update
sudo apt install snapd
sudo snap install postman
postman
```

**UNA VEZ INSTALADO POSTMAN, VAMOS A REALIZAR LAS ACTIVIDADES ESENCIALES, POR ELLO VAMOS A REALIZAR ESTOS PASOS**

1. Primero vamos en la parte superior izquierda le damos clic en **My Workspace > New** y seleccionamos la opción **HTTP**
2. Una vez creado ese espacio de trabajo, utilizaremos la API de *jsonplaceholder*, vamos a seleccionar en donde dice **GET** y la dejamos así, solamente en el recuadro que esta en blanco colocamos esta URL de la API: **https://jsonplaceholder.typicode.com/posts** y no colocamos parámetros y le damos en el boton llamado **Send** y esperamos que nos muestre todo el JSON de la API mencionada
3. Cuando hayamos logrado el GET, vamos a realizar el POST, por ello hacemos lo mismo con el paso 2 y seleccionamos donde dice **GET** en **POST** no cambiamos parametros, pero si en la parte de **Body** y le ponemos la opción de **none** y le damos en **Send** 
4. Haciendo lo mismo que el paso 2, vamos a cambiar en lugar de **GET** por **PUT** y haciendo lo mismo que el paso 3, solamente cambiamos la URL y dejamos esta **https://jsonplaceholder.typicode.com/posts/10** y le damos en **Send**
5. Haciendo lo mismo que el paso 2 al 4 vamos a dejarlo como esta la URL anterior y le damos en **Send**

**CON ESTO TENDREMOS NUESTRA API DE POSTMAN FUNCIONANDO CON LOS MÉTODOS DE GET, POST, PUT Y DELETE**

---

# CAPTURAS DE FUNCIONAMIENTO

![](@attachment/Clipboard_2023-12-03-16-32-23.png)

![](@attachment/Clipboard_2023-12-03-16-32-33.png)

![](@attachment/Clipboard_2023-12-03-16-32-43.png)

![](@attachment/Clipboard_2023-12-03-16-32-51.png)

