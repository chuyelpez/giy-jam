---
title: 'UNIDAD 1.9: Programación Orientada a Objetos en Python'
created: '2023-09-18T00:13:00.339Z'
modified: '2023-09-29T14:24:19.928Z'
---

# UNIDAD 1.9: Programación Orientada a Objetos en Python

**Dentro de Python, la programación orientada a Objetos o también abreviada POO es la que nos permite hacer uso de los objetos que extraemos de la realidad que podamos programar, todo aquello que tiene un valor es considerado programable, así sea una pelota de goma hasta un centro de base de datos en el espacio, así que dentro de Python funciona igual, pero utilizando una de las palabras más usuales y conocidas del mundo de la programación y son las <span style="color:cyan">Clases</span> y aquí un ejemplo de su sintaxis:**

`````py
class Clase:
	pass
`````

**La palabra <span style="color:cyan">class</span> define una clase y la palabra <span style="color:cyan">pass</span> funciona para que acabe con la clase (pero solo si en algunos casos no tiene que hacer nada).**

**Ahora vamos a ver un ejemplo más habitual cuando hablamos de la clase Persona y es la siguiente:**

`````py
class Persona:
	def __init__(self):
		self.nombre = "Jorge"
		self.estatura = 1.66
		self.grado_estudios = "Universidad"


persona1 = Persona()
print (type(persona1), persona1.nombre, persona1.estatura, persona1.grado_estudios)
`````

**Lo que hace al final de todo es imprimir de la clase Persona los datos que tiene almacenada en esa clase, junto con la palabra <span style="color:cyan">def__init__(self)</span> nos permite hacer la parte del constructor y de poder asignar en esos espacios e inicializarlos, despues se busca igualar a una nueva variable con esa clase e imprimir todos los datos que sean necesarios de entender en su concepto total**

**Existe otra forma de declarar mejor los datos de una clase y se hace de la siguiente forma:**

`````py
class Personaa:
	def __init__(self, nombre, estatura, grado_estudios):
		self.nombre = nombre
		self.estatura = estatura
		self.grado_estudios = grado_estudios

personaa1 = Personaa("Alberto", 1.78, "Preparatoria")
print(personaa1.nombre, personaa1.estatura, personaa1.grado_estudios)
`````

**Para los programadores saben que esta sintaxis es la de un constructor más claro y que tiene una forma inusual de entender mejor la forma de declarar mejor una clase.**

**NOTA:** Puedes dentro de esa misma clase asignar N cantidad de objetos que deseas, lo unico que cambian son los valores, ya que no puedes tener mismos valores con diferentes personas, eso puede alterar un error al momento de una solución de algoritmos.

---

# RESULTADOS

**Aquí los resultados de los ejemplos anteriores:**

![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/Clases.png)





