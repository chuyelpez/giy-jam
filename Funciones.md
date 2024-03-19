---
title: 'UNIDAD 1.8: Funciones'
created: '2023-09-17T21:24:31.427Z'
modified: '2023-09-19T00:26:59.084Z'
---

# UNIDAD 1.8: Funciones

**Una función son actividades o tareas que permiten resolver algoritmos con mucha mas funcionalidad**

**Esta es la sintaxis para poder declarar una función:**

`````py
def funcion():
		#instrucciones
`````

**Dentro de esta simple sintaxis podemos ver que tenemos instrucciones dentro, pero no todas las funciones son iguales, ya que tenemos algunas que son de tipo *Void*, *Return*, y *Argumentos*. Con ello es como vamos a poder resolver los múltiples de algoritmos que se presenten, así que vamos a ver cuales son.**

---

# Función de tipo Void

**Esta es fácil de entender y se refiere a que va a regresar un valor sin retornar o devolver algo, solo hara una simple instrucción como un print y aquí el ejemplo:**

`````py
def funcion_void(apellido):
	print("Tu apellido es: " + apellido)

funcion_void("Sanchez")
`````

**Es sencilla de entender, así que vamos con la siguiente.**

---

# Función de tipo Return

**Esta función igual es fácil de entender solo que ahora si va a retornar uno o más parametros que tengamos dentro de la función, por ello vamos a ver un ejemplo de ello:**

`````py
def funcion_return(a, b):
	return a - b

print (funcion_return (50, 20))
`````

**Es igual sencilla de entender, aunque vemos que tenemos dos parametros declarados para esta función, pero después tenemos que retornar un valor final, así es como funciona esta función, vamos con la última.**

---

# Función de tipo Argumentos 

**Esta puede ser algo dificil de comprender, pero si lo denominamos como algo práctico entonces sabremos que son cadenas de caracteres a poder evaluar y aquí un ejemplo:**

`````py
def funcion_argumentos(nombre):
	print ("Saludando a: " + nombre)

nombre = "Jorchito"
funcion_argumentos(nombre)
`````

**Primero declaramos un valor o variables para poder mandar a llamar en sus múltiples datos presentados, despues los guardamos y los exponemos en la función, con ello es que tenemos mas aclarado lo que tenemos que resolver y ejecutar** 

---

# Función de tipo Kwargs

**Un Kwarg no es mas que terminos de argumentos que se pueden aplicar dentro de la función especifica para resolver algoritmo como listas u otras necesidades, con ello podemos tener en cuenta las facilidades con las que podemos tomar consideración de esto mismo, ahora aquí un ejemplo:**

`````py
def funcion_kwargs( ** terminos):
	for indice, valor in terminos.items():
		print (f"{indice}:{valor}")

terminos = {'ter1': "Jorge", 'ter2': "Anel", 'ter3': "Roberto"}
funcion_kwargs( ** terminos)
`````

---

# Función de tipo Recursiva

**Son casi parecidas a la función anterior, solamente que aquí se repiten infinidad de veces, solo que de esta forma es como se aprenden mejor los datos de la estructura de la función, aquí un ejemplo de como funciona:**
 
`````py
def funcion_recursiva(numero):
	if numero == 1:
		return 1
	else:
		return numero + funcion_recursiva(numero - 1)

print (funcion_recursiva(5))
`````

**NOTA:** Esta función puede servir en caso de usos matemáticos, pero puede tener otras funciones más especiales al momento de hacer algoritmos especiales, pero eso ya depende de lo que tenga que realizar.

---

# RESULTADOS

**Aquí los resultados de los ejemplos anteriores:**

![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/Funciones.png)
