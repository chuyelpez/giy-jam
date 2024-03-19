---
title: 'UNIDAD 1.7: Diccionarios'
created: '2023-09-17T20:57:57.419Z'
modified: '2023-09-19T00:25:04.745Z'
---

# UNIDAD 1.7: Diccionarios

**Para entender lo que es un diccionario, son las que hacen todo lo importante en cada tipo de dato, digamos que es la involucrada en hacer el uso de almacenar todo en un espacio libre que nos hara poder hacer uso de sus variables en algoritmos distintos y poder resolver mejor el conflicto**

**Así se declara un diccionario**

`````py
diccionario = {
'nombre': "Jorge",
'edad': 19,
'matricula': 222211412
}
`````

**Esto nos muestra de mejor manera el uso de este mismo, veremos que su sintaxis incluye comillas simples y dos puntos, además de destacar que hace uso de las llaves que muchos diran que pueden ser tuplas, pero no, esta es la sintaxis de un diccionario**

**Ahora para poder imprimir todos o alguno de los valores expuestos sería de la siguiente manera:**

`print (diccionario ['matricula'])`

**Pero para obtener el valor de este usaremos la palabra <span style="color:purple">**get**</span>**

`print (diccionario.get('nombre'))`

**NOTA:** Estos son pequeños tips que te ayudaran con los diccionarios

+ `print ('nombre' in diccionario)`: Nos dirá si existe un valor dentro de ese parámetro
+ `print ("Jorge" in diccionario.values())`: Nos indicará si ese valor ya existe dentro de ese parámetro

*EXTRA:* La palabra en el print 'f' sirve para formatear cadenas 

---

# Retornar indices o valores de un diccionario usando For


**Dentro de los diccionarios tenemos algunos de los famosos retornos de datos, a veces necesitaremos para saber de que dato estamos tratando y que valores existen dentro de ese diccionario, pero para entender mejor aquí un ejemplo con los datos anteriores**

+ **Para retornar un indice o espacio donde se guardaron valores sería así:**

`````py
for indices in diccionario.keys():
	print (indices)
`````

**Lo que hace .keys() es retornar o regresar las llaves o identificadores de donde se guardaron en el diccionario, esto como dije permite saber con que identificadores estamos tratando para resolver el algoritmo**

+ **Para retornar un valor o dato que fueron asignados de los indices anteriores sería así:**

`````py
for valores in diccionario.values():
	print (valores)
`````

**Lo que hace .values() es regresar los valores de las llaves o identificadores anteriores, con ello es más facil saber que datos fueron almacenados en el diccionario y tener un mejor desarrollo del algoritmo**

**NOTA:** Existen mas formas de modificar un diccionario con estas reglas

+ `diccionario.pop('nombre')`: Permite borrar parámetros del diccionario
+ `diccionario.clear()`: Limpia todo el diccionario 
+ `del diccionario`: Elimina un dato además de liberar memoria
+ `diccionario['edad'] = 19`: Permite añadir nuevos parámetros al diccionario

--- 

# RESULTADOS

**Aquí los resultados de los ejemplos anteriores:**

![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/Diccionarios.png)

