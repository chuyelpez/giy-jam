---
tags: [Import-a778]
title: 'UNIDAD 1.5: Sentencias o Estructuras de Control'
created: '2023-09-15T01:39:59.790Z'
modified: '2023-09-19T00:19:53.951Z'
---



# UNIDAD 1.5: Sentencias o Estructuras de Control

**Para este nuevo tema, aquí se hablara de lo más usado en programación, que son las sentencias o estructuras de control, esto trata de condicionales que algunas son de dar un verdadero o falso o que tienen que cubrir cierta condicion para poder ejecutarse N cantidad de veces hasta que deje de hacerlo o que se repitan en un bucle que un bucle es mas que todo una repeticion infinita de una condición que no puede cambiar su valor al final, para ello vamos a explicar algunas de las siguientes sentencias y son:**

+ **If - elif - else -> Sentencia SÍ**
+ **While -> Mientras**
+ **For -> Para**

**Dentro de estas 3 sentencias son las mas habituales de utilizar, por ello es que vamos a definir que algunos de estos son iguales y otros pueden variar segun el lenguaje que se este aprendiendo.**

---

# Sentencia If - elif - else

**Esta sentencia lo que hace es que <span style = "color: red"> **if (si)** </span> un valor entra en condicion con otro valor y da un resultado verdadero, este hara las instrucciones que le coloquen dentro de esa condicion verdadera, pero en caso de que sea falsa, entonces hara uso de la palabra <span style = "color: red"> **else (de lo contrario)** </span>** **las instrucciones falsas que se presenten para poder hacer esa ejecución final de la sentencia**

**Para entender mejor, vamos a comparar dos valores que el numero 1 tiene que ser menor al numero 2 y tiene que decir que 1 es menor que dos, para que si en caso de que no se cumpla, diga que 2 es mayor que 1 y veremos aquí el ejemplo:**

`````py
numero1 = 1
numero2 = 2
if numero1 <= numero2:
	print ( " El", numero1 , "es menor que" , numero2 )
else:
	print ( " El", numero1 , "es mayor que" , numero2 )
`````

**NOTA:** En este caso el uso de elif es cuando vamos a hacer dentro de un If una nueva condicion si es que llega a ser verdadera, también aplica si es que es falsa.

---

# Sentencia While

**Esta sentencia lo que hace es la repeticion de un codigo verdaderp hasta que llegue a su algoritmo falso, es decir que nos permite hacer un bucle hasta que llegue a su valor condicionado, pero si no se tiene un dato muy estructurado entonces no se llegara a un fin**

**Para entender mejor, vamos a tener un valor que vamos a condicionar y mientras que en un valor que vale 10 no sea menor o igual a 20 entonces se repetira cantidad de impresiones usando un incremento de 1 en 1, aquí el ejemplo:**

`````py
valor1 = 10

while valor1 <= 20:
	print("El valor es: ", valor1)
	valor1 += 1
`````

**Al final el resultado tendrá que dar varias impresiones hasta llegar al valor final de 20**

**NOTA:** No se usa en muchos casos while, solo en casos donde se requieran que un algoritmo si llegue a tener un incremento de algun dato que tenga que hacer el uso, no siempre se utiliza, aunque para prácticar funciona de maravilla.

---

# Sentencia For

**Esta sentencia en su traducción al español significa Para, esto dice que en un valor dentro o en otro valor que va a ser condicionado tiene que cumplir con el valor que es, ya que si no llega a cumplirlo, entonces no hará nada al respecto, pero este tiene una cualidad de que es una de las sentencias que se usan mucho para poder resolver algoritmos más complejos respecto a su uso, así que de aqui tiene un uso práctico en toda su resolución de Python**

**Para entender mejor, vamos a colocar el nombre de Jorge Alberto Sanchez Cobos y junto a un dato vacio llamado valor haremos que imprima el caracter del nombre uno por uno, aquí el siguiente ejemplo:**

`````py
nombre = "Jorge Alberto Sanchez Cobos"

for valor in nombre:
	print(valor)
`````

**Al final el el resultado que dara son muchos caracteres del nombre empezando desde la J hasta la s**

*CURIOSIDAD:* En programación existen más sentencias o estructuras de control, existe la Do - While y la Switch, pero en Python no existen para no darle mucha complejidad al algoritmo, pero en otros lenguajes estos son utiles y se aquí una breve explicación:

***Switch:*** Se usa como una sentencia de opciones multiples que mediante un valor buscara entre esas opciones el valor correcto y hacer el algoritmo que tenga esa opción seleccionada, en su caso si no hay ninguna entonces hara el algoritmo negativo por default

***Do - While:*** Esta sentencia se le puede decir que es lo negativo del While, que si este hace que si es verdadera la condición entonces se repetira hasta encontrar su condicion falsa, lo cual el Do - While hace lo contrario, mientras la condición sea falsa se repetira infinitamente, hasta que rompa el bucle con su condición verdadera

---

# RESULTADOS

**Aquí los resultados de los ejemplos anteriores:**

![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/Sentencias 1.png)
![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/Sentencias 2.png)
