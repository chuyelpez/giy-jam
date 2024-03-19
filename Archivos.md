---
title: 'UNIDAD 1.11: Archivos'
created: '2023-09-28T13:47:37.004Z'
modified: '2023-12-03T22:35:07.328Z'
---

# UNIDAD 1.11: Archivos

**En Python existen muchas de las librerías que nos permiten la parte de creación de scripts o documentos que llevamos usando a lo largo de la vida y toca hablar de ellos.**

**Hay una libreria llamada *csv* que nos permite hacer la creación de un documento de cualquier extensión de texto, como seria un .docx, .pptx, .xls, .sql, ect...**

**Primero vamos a ver como es la creación de un documento de tipo txt en blanco en Python y está sería el código:**

`````py
try:
    fichero = open("ejemplar.txt", "w", encoding="utf8")
    fichero.write('Este ejemplar tiene texto de una forma fija')
    fichero.write('\n')
    fichero.write('este es otra segunda linea que muestra informacion')
    fichero.close()

except Exception as e:
    print(e)
`````

**Lo que trata de decir la primer línea del codigo en el *try* es que en español dice 'Poner' y esto permite hacer la validación de la sintaxis que coloquemos dentro de esta instrucción, pero no solo debemos colocar el try, tambien requiere de otra instrucción llamada *except* que nos permite hacer la validación final de nuestro código y que podamos hacer este uso real para creación de archivos o de estructuras que tengamos que revisar con precisión.**

**Ahora dentro de Python podemos colocar la ruta para abrir el archivo y eso depende del sistema operativo que estemos utilizando, aquí un ejemplo de la sintaxis con sus rutas:**

`````py
# RUTA DE LINUX EN PYTHON
try:
    fichero = open("/home/jorchitoxyz/Escritorio/Programas/ejemplar.txt", "r", encoding="utf8")
    print(fichero.read())

except Exception as e:
    print(e)

# RUTA WINDOWS EN PYTHON
try:
    fichero = open("c:\\users\\usuario\\desktop\\ejemplar.txt", "r", encoding="utf8")
    print(fichero.read())
except Exception as i:
    print(i)
`````

**Existen mas formas de poder imprimir, iterar o agregar información de un archivo existente a otro nuevo, y aquí estan los siguientes:**

+ `print(fichero.read())`: Permite leer todo el contenido del archivo 
+ `print(fichero.read(5))`: Permite leer solo los caracteres que se indican con el número de la posición
+ `print(fichero.readline())`: Es lo mismo que el primer comando, aunque lee una línea completa sin faltar ningún caracter.
+ `for linea in fichero: print(linea)`: Permite hacer una iteración de cada linea del archivo que se selecciona
+ `print(fichero.readlines())`: Esta ahora lee todas las líneas del archivo sin llegar a faltar ningún caracter
+ `print(fichero.readlines()[0])`: Permite acceder a la línea del archivo que este dentro de esa lista
 `````py
fichero = open("/home/jorchitoxyz/Escritorio/Programas/ejemplar.txt", "r", encoding="utf8")
    fichero2 = open('ejemplar2.txt','w',encoding='utf8')
    fichero2.write(fichero.read())

    fichero.close()
    fichero2.close()
`````
Permite que se agrege la misma información al nuevo archivo



