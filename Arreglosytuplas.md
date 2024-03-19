---
tags: [Import-1e6e]
title: 'UNIDAD 1.6: Arreglos y Tuplas'
created: '2023-09-15T01:40:09.530Z'
modified: '2023-09-19T23:50:04.355Z'
---

# UNIDAD 1.6: Arreglos y Tuplas
**En programación sabemos que un arreglo es la construccion ordenada de elementos que podemos implementar en una sola variable, considerando que los arreglos se pueden modificar conforme al algoritmo planteado, aunque una Tupla es aquella que es la misma que un arreglo, solamente que esta no se puede modificar y se puede notar en sus respectivos usos, ahora veremos un ejemplo de estos arreglos y tuplas**

`````py
estudiantes = ["Jorge", "Liz", "Anel", "Miguel"]
print(estudiantes)
`````

Como podemos ver tenemos que en la variable <span style="color:purple">**estudiantes**</span> esta la parte de un arreglo o tambien llamadas **listas**, lo cual esto hace que la cantidad de caracteres o datos que estemos presentando dentro de ese arreglo, cuando se imprima mostrara los datos ya definidos en ese arreglo, al final los podremos cambiar conforme al algoritmo presente se especifique.

**Ahora vamos a hacer la parte de las tuplas que esto es importante de conocer y tenemos el siguiente ejemplo:**

`````py
lenguajes_de_programacion = ("Python", "C++", "Java", "Swift")
print(lenguajes_de_programacion)
`````

Nos daremos cuenta de que tienen casi la misma sintaxis que la de un arreglo, pero lo que cambia son los parentesis, eso define que estamos usando en el valor asignado

**Al final esto es lo que van a imprimir el arreglo y las tuplas:**

`['Jorge', 'Liz', 'Anel', 'Miguel']`

`('Python', 'C++', 'Java', 'Swift')`

---

# Tips para uso de arreglos (listas)

**Primero debemos conocer que dentro de esta información nos ayudara para mejorar los datos del algoritmo**

+ `print(estudiantes[0])`: Permite acceder de forma individual a una lista
+ `print(estudiantes[-1])`: Permite acceder de forma inversa a una lista
+ `print(estudiantes[0:2])`: Permite acceder a los rangos de una lista
+ `print(estudiantes[:3])`: Permite acceder a un indice específico
+ `print(estudiantes[1:])`: Permite acceder a un indice inicial hasta el final
+ `estudiantes[0] = "Alberto"`: Permite cambiar el valor del indice seleccionado
+ `for nombres in estudiantes:`: Permite acceder a las iteraciones en la lista
+ `print(len(estudiantes))`: Permite acceder a la longitud de la lista
+ `estudiantes.append("Luis")`: Permite agregar nuevos elementos a las listas **(sin elegir el lugar de donde se ubicará en la lista)**
+ `estudiantes.insert(4, "Luis")`: Permite agregar nuevos elementos a las listas, pero ya eligiendo el lugar donde se ubicará en la lista
+ `estudiantes.remove("Luis")`: Permite eliminar un elemento de la lista
+ `estudiantes.pop()`: Permite eliminar el ultimo elemento insertado de la lista
+ `del estudiantes[0]`: Permite eliminar un elemento de un espacio o lugar seleccionado
+ `estudiantes.clear()`: Permite eliminar todos los elementos de la lista
+ `del estudiantes`: Permite eliminar toda la lista por completo

# Tips para uso de tuplas 

**Para poder hacer un buen uso de las tuplas, tenemos que conocer algunos de los usos que se utilizan en Python y con ello unos ejemplos de los presentados:**

+ `print(len(lenguajes_de_programacion))`: Permite obtener la longitud de la tupla
+ `print(lenguajes_de_programacion[0])`: Permite acceder al valor del indice indicado
+ `print(lenguajes_de_programacion[-1])`: Permite acceder al valor del indice de forma inversa
+ `print(lenguajes_de_programacion[0:3])`: Permite acceder al rango de valoresd e la tupla
+ `lenguajes_de_programacion = ('JSON',)`: Permite declarar una tupla con un valor existente **(si no se agrega la coma al final, entonces se considera como una cadena y no un elemento de la tupla)**
+ Para poder recorrer un elemento de la tupla es:

`````py
dato = 0

while dato < len(lenguajes_de_programacion):
    print(lenguajes_de_programacion[dato], end = ", ")
    dato += 1
`````

+ Permite cambiar el valor de una tupla **(esto no es buena práctica, debido a que debe ser fija una tupla, pero igual cambia en algunas circunstancias):**

`````py
lenguajes_de_programacion_list = list(lenguajes_de_programacion)

lenguajes_de_programacion_list.append('C')

lenguajes_de_programacion = tuple(lenguajes_de_programacion_list)

print(lenguajes_de_programacion)
`````

+ `del lenguajes_de_programacion`: Elimina la tupla en su totalidad

# Listas y Tuplas de forma ascendente y descendente junto a máximos y mínimos

**Aquí estas formas se utilizan en las dos por igual, pero primero vamos a utilizar las mismas sintaxis de las listas y son:**

`````py
# Listas
aprobados = [8.9, 8.7, 10.0, 9.6]
print("Lista de aprobados ", aprobados)

# Ordenar de menor a mayor 
aprobados.sort()
print("Lista de aprobados ordenada de menor a mayor", aprobados)

# Ordenar de mayor a menor
aprobados = sorted(aprobados, reverse=True)
print("Lista de aprobados ordenada de mayor a menor", aprobados)

# Máximo de una lista
aprobadosM = max(aprobados)
print("El numero máximo de la lista es: ", aprobadosM)

# Mínimo de una lista
aprobadosm = min(aprobados)
print("El numero mínimo de la lista es: ", aprobadosm)
`````
**Ahora siguen con las tuplas y sería de la siguiente manera:**

`````py
# Tuplas
reprobados = (5.5, 2.4, 4.3, 1.1)
print("Tupla de reprobados ", reprobados)

# Ordenar de menor a mayor 
reprobados = tuple(sorted(reprobados))
print("Lista de aprobados ordenada de menor a mayor", reprobados)

#Ordenar de mayor a menor
reprobados = tuple(sorted(reprobados, reverse = True))
print("Lista de aprobados ordenada de mayor a menor", reprobados)

# Máximo de un valor 
reprobadosM = max(reprobados)
print("EL valor máximo de la tupla es: ", reprobadosM)

# Mínimo de un valor 
reprobadosm = min(reprobados)
print("EL valor mínimo de la tupla es: ", reprobadosm)
`````
**Nota:** En el caso de las tuplas cambia su valor del **sort()** y se usa el **tuple(sorted())** para los valores de tipo ascendentes o descendentes, con ello no se confunde una lista de una tupla, pero si quedan iguales los máximos y mínimos

---

# RESULTADOS

**Aquí los resultados de los ejemplos anteriores:**
![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/Arreglos y tuplas.png)

**LISTAS:**
![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/Listas.png)

**TUPLAS:**
![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/Tuplas.png)


