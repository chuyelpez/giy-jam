---
title: 'UNIDAD 1.10: EJERCICIOS'
created: '2023-09-23T04:17:42.984Z'
modified: '2023-09-23T04:57:20.015Z'
---

# UNIDAD 1.10: EJERCICIOS

**Aquí se agregan algunos de los ejercicios previamente resueltos en clase y que presentan una forma de ver el uso de la sintaxis con estos pequeños ejemplos que no tienen mucha dificultar y con ello se colocara los ejercicios y código de los ejemplos y captura de sus resultados, así que comenzamos:**

---

# EJERCICIOS 1

+ **Ejercicio 1: Crear una variable llamada `nombre` con tu nombre y luego imprimirlo.**
+ **Ejercicio 2: Crear una variable llamada `edad` con tu edad y luego imprimirlo.**
+ **Ejercicio 3: Crear una lista llamada `colores` con tres colores y luego imprimir la lista.**
+ **Ejercicio 4:Crear una tupla llamada `coordenadas` con dos números que representen una ubicación geográfica y luego imprimir la tupla.**
+ **Ejercicio 5: Crear un diccionario llamado "persona" con claves como `nombre` y `edad` y luego imprimir el diccionario.**
+ **Ejercicio 6: Crear una cadena de texto multilineal que represente un poema e imprimirlo.**
+ **Ejercicio 7: Crear una variable booleana llamada `es_mayor_de_edad` que sea verdadera si tienes 18 años o más, y luego imprimir el valor.**
+ **Ejercicio 8: Crear una tupla llamada `dias_semana` con los nombres de los días de la semana y luego imprimir el tercer día.**

***SINTAXIS DE LOS EJERCICIOS MENCIONADOS:***

`````py
# EJERCICIO 1: CREAR UN HOLA MUNDO

print("Mi nombre es Jorge Alberto Sanchez Cobos, grupo IRD41 y este es mi Hola Mundo")

# EJERCICIO 2: IMPRIMIR UNA VARIABLE LLAMADA EDAD E IMPRIMIRLA
edad = 19
print(edad)

# EJERCICIO 3: DEFINIR UNA LISTA CON COLORES E IMPRIMIRLOS

colores = ["Verde", "Rojo", "Azul", "Amarillo"]
print(colores)

# EJERCICIO 4: CREAR UNA TUPLA CON COORDENADAS E IMPRIMIRLOS

coordenadas = (18.82732, -90.63521)
print(coordenadas)

# EJERCICIO 5: CREAR UN DICCIONARIO QUE TENGA DE ATRIBUTO NOMBRE Y EDAD

diccionario = {
    'Nombre': "Jorge",
    'Edad': 19
}

print(diccionario)

# EJERCICIO 6: CREAR UN TEXTO MULTILINEAL

"""
ESTE ES UN MENSAJE SOBRE CÓMO ESCRIBIR EN ESTE LENGUAJE DE PROGRAMACIÓN.
PRESENTAMOS UNA FORMA PRÁCTICA DE APRENDER A UTILIZARLO,
DESTACANDO SU FACILIDAD Y LA CAPACIDAD DE MONITOREAR LAS HABILIDADES ADQUIRIDAS.
"""


# EJERCICIO 7: DECLARAR UNA VARIABLE DE EDAD Y DENTRO DE ESA VARIABLE EVALUAR DENTRO DE ESA EDAD ES MAYOR O IGUAL A 18

EDAD = 19
valor = EDAD >= 18
print(valor)

# EJERCICIO 8: CREAR UNA TUPLA CON LOS DIAS DE LA SEMANA DE LUNES HASTA EL DOMINGO Y RETORNAR EL VALOR CON EL POSICIONAL DE 2

Semana = ("Lunes", "Martes", "Miercoles", "Jueves", "Viernes", "Sabado", "Domingo")
print(Semana[2])
`````

***RESULTADOS:***

![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/EJERCICIOS 1.png)

---

# EJERCICIOS 2

+ **Ejercicio 1 # Calcular la suma de dos numeros e imprimir el resultado**
+ **Ejercicio 2 # Calcular la resta de dos numeros e imprimir el resultado**
+ **Ejercicio 3 # Calcular el producto de dos números e imprimir el resultado (*)**
+ **Ejercicio 4 # Calcular la división de dos numeros e imprimir el resultado**
+ **Ejercicio 5 # Calcular el residuo de una división de dos numeros e imprimir el resultado**
+ **Ejercicio 6 # Calcular la potencia de dos numeros e imprimir el resultado**
+ **Ejercicio 7 # Calcular el cosiente de una división de dos numeros e imprimir el resultado**
+ **Ejercicio 8 # Verificar si un número es igual a otro e imprimirlo**

***SINTAXIS DE LOS EJERCICIOS MENCIONADOS:***

`````py
numero1 = input("Ingresa tu primer numero: ")
numero2 = input("Ingresa tu segundo numero: ")

a = int(numero1)
b = int(numero2)

# EJERCICIO 1: Calcular la suma de 2 numeros e imprimir el resultado

suma = a + b
print ("El resultado de la suma es: ", suma)

# EJERCICIO 2: Calcular la resta de 2 numeros e imprimir el resultado

resta = a - b
print ("El resultado de la resta es: ", resta)

# EJERCICIO 3: Calcular el producto de 2 numeros e imprimir el resultado

producto = a * b
print ("El resultado de la multiplicacion es: ", producto)

# EJERCICIO 4: Calcular la division de 2 numeros e imprimir el resultado

division = a / b
print ("El resultado de la division es: ", division)

# EJERCICIO 5: Imprimir el residuo de la division de 2 numeros

residuo = a % b
print ("El resultado de la division con residuo es: ", residuo)

# EJERCICIO 6: Calcular la potencia de 2 numeros e imprimir el resultado

potencia = a ** b
print ("El resultado de la potencia es: ", potencia)

# EJERCICIO 7: Calcular el cociente de una division de 2 numeros e imprimir el resultado

cociente = a // b
print ("El resultado de la division con su cociente es: ", cociente)

# EJERCICIO 8: Verificar si un numero es igual a otro e imprimirlo

verificar = a == b
print ("El valor es: ", verificar)
`````

***RESULTADOS:***

![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/EJERCICIOS 2.png)

---

# EJERCICIOS 3

+ **Ejercicio 1: #Crear una lista llamada `numeros` con números enteros, luego imprimir la lista y limpiar la lista.**
+ **Ejercicio 2:  3Crear una lista llamada `frutas` con nombres de frutas, luego imprimir la lista y limpiar la lista.**
+ **Ejercicio 3: #Crear una lista vacía llamada `lista_vacia` y luego imprimir la lista.**
+ **Ejercicio 4: #Crear una lista llamada `numeros` con números enteros y luego imprimir el tercer número de la lista.**
+ **Ejercicio 5: #Crear una lista llamada `frutas` con nombres de frutas y #luego agregar una fruta adicional a la lista. Imprimir la lista actualizada.**
+ **Ejercicio 6: #Crear una lista llamada `numeros` con números enteros y luego calcular la suma de todos los números en la lista.**
+ **Ejercicio 7: #Crear una lista llamada `frutas` con nombres de frutas y luego imprimir la longitud de la lista.**
+ **Ejercicio 8: #Crear una lista llamada `numeros` con números enteros y luego ordenarla en orden ascendente. Imprimir la lista ordenada.**
+ **Ejercicio 9: Crear una lista llamada `numeros` con números enteros y luego encontrar el número más grande en la lista. Imprimir el número más grande.**
+ **Ejercicio 10: Crear una lista llamada `numeros` con números enterosy luego encontrar el número más pequeño en la lista. Im primir el número más pequeño.**

***SINTAXIS DE LOS EJERCICIOS MENCIONADOS:***

`````py
# EJERCICIO 1: Crear una lista llamada "numeros" con 3 enteros y limpiar la lista

numeros = [10, 4, 67]
numeros.clear()
print("El arreglo de numeros vacio: ", numeros)

# EJERCICIO 2: Crear una lista llamada "frutas" y luego imprimir la lista

frutas = ["Fresa", "Platano", "Manzana"]
print("El arreglo frutas : ", frutas)

# EJERCICIO 3: Crear una lista llamada "lista_vacia" e imprimir

lista_vacia = []
print("Lista vacia: ", lista_vacia)

# EJERCICIO 4: Crear una lista con numeros enteros y luego imprimir el tercer lugar

numeros2 = [24, 83, 66, 39, 50]
print("Posicion numero 3 del arreglo: ", numeros2[3])

# EJERCICIO 5: Crear una lista llamada "frutas" con nombres de frutas y luego agregar una fruta adicional a la lista e imprimir

frutas2 = ["Fresa", "Platano", "Manzana"]
frutas2.insert(3, "Sandia")
print("Arreglo agregandole una fruta: ", frutas2)

# EJERCICIO 6: Crear una lista llamada "numero enteros" y calcular una suma de todos los numeros e imprimir 

numeros_enteros = [46, 78, 23, 10, 98]
for valores in numeros_enteros:
	suma = valores+ valores

print("La suma de la lista es de: ", suma)

# EJERCICIO 7: Crear una lista llamada "frutas" con nombres de frutas y luego imprimir la longitud de la lista

frutas3 = ["Fresa", "Platano", "Manzana"]
print("La longitud es de: ", len(frutas3))

# EJERCICIO 8: Crear una lista llamada "numeros" con numeros enteros y ordenar la lista en orden ascendente e imprimir

numeros3 = [5, 27, 15, 8, 100]
print("Lista de numeros desordenados:", numeros3)
numeros3.sort()
print("Lista de numeros ordenados:", numeros3)
	

# EJERCICIO 9: Crear una lista llamada "numeros" con numeros enteros y que imprima el valor mas grande de la lista

numeros4 = [5, 27, 15, 8, 100]
maximo = max(numeros4)
print("El numero mas grande es: ", maximo)

# EJERCICIO 10: Crear una lista llamada "numeros" con numeros enteros y que imprimir el valor mmas pequeño de la lista

numeros5 = [5, 27, 15, 8, 100]
minimo = min(numeros5)
print("El numero mas pequeño es: ", minimo)
`````
***RESULTADOS:***

![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/EJERCICIOS 3.png)

---

# EJERCICIOS 4

+ **Ejercicio 1:** Crea un diccionario vacío llamado `mi_diccionario`.
+ **Ejercicio 2:** Agrega tres pares clave-valor al diccionario `mi_diccionario` relacionados con nombres y edades.
+ **Ejercicio 3:** Accede a la edad dentro de `mi_diccionario` primer elemento.
+ **Ejercicio 4:** Modifica la segunda edad dentro de  en `mi_diccionario`.
+ **Ejercicio 5:** Itera a través de las claves en `mi_diccionario` e imprime cada clave.
+ **Ejercicio 6:** Itera a través de los valores en `mi_diccionario` e imprime cada valor.
+ **Ejercicio 7:** Borra todos los elementos de `mi_diccionario`.
+ **Ejercicio 8:** Crea un diccionario llamado `frutas` con tres frutas y sus cantidades correspondientes como valores.
+ **Ejercicio 9:** Incrementa en 2 la cantidad de manzanas en `frutas`.
+ **Ejercicio 10:** Escribe una función llamada `buscar_fruta` que tome el nombre de una fruta como argumento y devuelva la cantidad de esa fruta en el diccionario `frutas`.
+ **Ejercicio 11:** Escribe una función llamada `agregar_fruta` que tome el nombre de una fruta y una cantidad como argumentos y agregue esta fruta al diccionario `frutas`.
+ **Ejercicio 12:** Escribe una función llamada `eliminar_fruta` que tome el nombre de una fruta como argumento y elimine esa fruta del diccionario `frutas`.

***SINTAXIS DE LOS EJERCICIOS MENCIONADOS:***

`````py
# EJERCICIO 1

mi_diccionario = {}
print("EJERCICIO 1:", mi_diccionario)

# EJERCICIO 2
mi_diccionario = {
	'dict1': 
	{
	'name1': "Jorge",
	'age1': 19
	},
	'dict2': {
	'name2': "Paulina",
	'age2': 39
	},
	'dict3': {
	'name3': "Santiago",
	'age3': 1
	}
}
print("EJERCICIO 2: ", mi_diccionario)

# EJERCICIO 3

print("EJERCICIO 3: ", mi_diccionario['dict1']['age1'])

# EJERCICIO 4

mi_diccionario['dict2']['age2'] = 50
print("EJERCICIO 4: ", mi_diccionario['dict2']['age2'])

# EJERCICIO 5
for claves in mi_diccionario.keys():
	print("EJERCICIO 5: ", claves)

# EJERCICIO 6
for valores in mi_diccionario.values():
	print("EJERCICIO 6: ", valores)

# EJERCICIO 7
mi_diccionario.clear()
print("EJERCICIO 7: ", mi_diccionario)

# EJERCICIO 8
i = 1
frutas = {}
while i <= 3:
	fruta = input("Nombre de la fruta: ")
	cantidad = int(input("Cantidad de esa fruta: "))
	frutas[fruta] = cantidad
	i += 1


print("EJERCICIO 8. ", frutas)

# EJERCICIO 9

cantidad = 0 

for nombres in frutas.keys():
    if nombres == 'Manzanas':
        cantidad = frutas['Manzanas']
        cantidad += 2

print("EJERCICIO 9. Cantidad de manzanas:", cantidad)


# EJERCICIO 10

def buscar_fruta(fruta):
	for buscar in frutas.keys():
		if buscar == fruta:
			cantidad = frutas.get(fruta)
			if cantidad == cantidad:
				print("EJERCICIO 10: ", fruta, "son: ", cantidad)

fruta = input("Escribe el nombre de la fruta a buscar: ")
buscar_fruta(fruta)

# EJERCICIO 11

def agregar_fruta(fruta, cantidad):
	print("EJERCICIO 11: Frutas no agregadas: ", frutas)
	if fruta != frutas.keys():
		frutas[fruta] = cantidad
		print("EJERCICIO 11: Fruta agregada: ", frutas)
	else:
		print("EJERCICIO 11: Esa fruta ya existe y no la puedes agregar")

fruta = input("Escribe una fruta nueva para agregar al diccionario: ")
cantidad = int(input("Ahora su cantidad: "))
agregar_fruta(fruta, cantidad)

# EJERCICIO 12

def eliminar_fruta(fruta):
	if fruta in frutas:
		del frutas[fruta]
		print("EJERCICIO 12: ", frutas)
	else:
		print("EJERCICIO 12: La fruta no existe y no se puede eliminar")


fruta = input("Escribe la fruta que deseas eliminar: ")
eliminar_fruta(fruta)
`````
***RESULTADOS:***

![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/EJERCICIOS 4.png)

---

# EJERCICIOS 5

+ **Ejercicio 1:** Pedir al usuario un número e imprimir si es positivo, negativo o igual a cero.
+ **Ejercicio 2:** Pedir al usuario dos números e imprimir cuál es el mayor de los dos.
+ **Ejercicio 3:** Pedir al usuario un número e imprimir si es par o impar.
+ **Ejercicio 4:** Pedir al usuario su edad e imprimir si es mayor de edad (mayor o igual a 18 años) o menor de edad.
+ **Ejercicio 5:** Pedir al usuario un número e imprimir si es mayor, menor o igual a 10.
+ **Ejercicio 6:** Pedir al usuario dos números e imprimir si son iguales o diferentes.
+ **Ejercicio 7:** Pedir al usuario una contraseña e imprimir "Contraseña correcta" si es igual a "secreto", de lo contrario, imprimir "Contraseña incorrecta".
+ **Ejercicio 8:** Pedir al usuario un número e imprimir si es positivo y menor que 10.
+ **Ejercicio 9:** Pedir al usuario dos números e imprimir si ambos son pares.
+ **Ejercicio 10:** Pedir al usuario su edad y su género (hombre o mujer) e imprimir "Bienvenido" si es un hombre mayor de 21 años o una mujer mayor de 18 años. De lo contrario, imprimir "Acceso denegado".
+ **Ejercicio 11:** Pedir al usuario dos números e imprimir el mayor de los dos, pero si son iguales, imprimir "Los números son iguales".
+ **Ejercicio 12:** Pedir al usuario un número del 1 al 7 e imprimir el día de la semana correspondiente. Si el número está fuera de ese rango, imprimir "Número inválido".

***SINTAXIS DE LOS EJERCICIOS MENCIONADOS:***

`````py
#EJERCICIO 1

numero = input("E1. Digita un numero: ")
verificar = int(numero)

if verificar > 0:
	print("El numero es positivo", verificar)
elif verificar < 0:
	print("El numero es negativo", verificar)
elif verificar == 0:
	print("El numero es igual a 0", 0)


# EJERCICIO 2

dato1 = int(input("E2. Digita primer numero: "))
dato2 = int(input("E2. Digita segundo numero: "))

if dato1 > dato2:
	print("El", dato1, "es mayor que", dato2)
else:
	print("El", dato2, "es mayor que", dato1)

# EJERCICIO 3

par_impar = int(input("E3. Digita un numero: "))
verifica = par_impar % 2

if verifica == 0:
	print("El numero", par_impar, "es par")
else: 
	print("El numero", par_impar, "es impar")

# EJERCICIO 4

edad = int(input("E4. Digita tu edad: "))

if edad >= 18:
	print("Tienes", edad, "y eres mayor de edad")
else:
	print("Tienes", edad, "y eres menor de edad")

# EJERCICIO 5

numero = int(input("E5. Digita el numero: "))

if numero < 10:
	print("El numero", numero, "es menor que 10")
elif numero > 10:
	print("El numero", numero, "es mayor que 10")
elif numero == 10:
	print("El numero", numero, "es igual que 10")

# EJERCICIO 6

dato1 = int(input("E6. Digita primer numero: "))
dato2 = int(input("E6. Digita segundo numero: "))

if dato1 != dato2:
	print("El", dato1, "es distinto al", dato2)
else:
	print("El", dato1, "es igual al", dato2)

# EJERCICIO 7

contra = input("E7. Escribe el password secreto: ")
secreto = "1111"

if contra == secreto:
	print("Password correcto")
else:
	print("Password incorrecto")

# EJERCICIO 8

numero = int(input("E8. Escribe un numero: "))

if numero > 0:
	if numero < 10:
		print("El numero", numero, "es positivo y menor que 10")
	else:
		print("El numero", numero, "es positivo pero mayor que 10")

# EJERCICIO 9

num1 = int(input("E9. Escribe el primer numero: "))
num2 = int(input("E9. Escribe el segundo numero: "))

par1 = num1 % 2
par2 = num2 % 2

if par1 == 0 and par2 == 0:
	print("Los numeros", num1, "y", num2, "son pares")
else:
	print("Un o los numeros", num1, "y", num2, "son impar o impares ")

# EJERCICIO 10

edad = int(input("E10. Escribe tu edad: "))
genero = input("E10. Escribe tu genero: ")

if genero == "hombre" and edad >= 21:
	print("Bienvenido")
elif genero == "mujer" and edad >= 18:
	print("Bienvenido")
else:
---
title: 'UNIDAD 1.10: EJERCICIOS'
created: '2023-09-23T04:17:42.984Z'
modified: '2023-09-23T04:57:20.015Z'
---

# UNIDAD 1.10: EJERCICIOS

**Aquí se agregan algunos de los ejercicios previamente resueltos en clase y que presentan una forma de ver el uso de la sintaxis con estos pequeños ejemplos que no tienen mucha dificultar y con ello se colocara los ejercicios y código de los ejemplos y captura de sus resultados, así que comenzamos:**

---

# EJERCICIOS 1

+ **Ejercicio 1: Crear una variable llamada `nombre` con tu nombre y luego imprimirlo.**
+ **Ejercicio 2: Crear una variable llamada `edad` con tu edad y luego imprimirlo.**
+ **Ejercicio 3: Crear una lista llamada `colores` con tres colores y luego imprimir la lista.**
+ **Ejercicio 4:Crear una tupla llamada `coordenadas` con dos números que representen una ubicación geográfica y luego imprimir la tupla.**
+ **Ejercicio 5: Crear un diccionario llamado "persona" con claves como `nombre` y `edad` y luego imprimir el diccionario.**
+ **Ejercicio 6: Crear una cadena de texto multilineal que represente un poema e imprimirlo.**
+ **Ejercicio 7: Crear una variable booleana llamada `es_mayor_de_edad` que sea verdadera si tienes 18 años o más, y luego imprimir el valor.**
+ **Ejercicio 8: Crear una tupla llamada `dias_semana` con los nombres de los días de la semana y luego imprimir el tercer día.**

***SINTAXIS DE LOS EJERCICIOS MENCIONADOS:***

`````py
# EJERCICIO 1: CREAR UN HOLA MUNDO

print("Mi nombre es Jorge Alberto Sanchez Cobos, grupo IRD41 y este es mi Hola Mundo")

# EJERCICIO 2: IMPRIMIR UNA VARIABLE LLAMADA EDAD E IMPRIMIRLA
edad = 19
print(edad)

# EJERCICIO 3: DEFINIR UNA LISTA CON COLORES E IMPRIMIRLOS

colores = ["Verde", "Rojo", "Azul", "Amarillo"]
print(colores)

# EJERCICIO 4: CREAR UNA TUPLA CON COORDENADAS E IMPRIMIRLOS

coordenadas = (18.82732, -90.63521)
print(coordenadas)

# EJERCICIO 5: CREAR UN DICCIONARIO QUE TENGA DE ATRIBUTO NOMBRE Y EDAD

diccionario = {
    'Nombre': "Jorge",
    'Edad': 19
}

print(diccionario)

# EJERCICIO 6: CREAR UN TEXTO MULTILINEAL

"""
ESTE ES UN MENSAJE SOBRE CÓMO ESCRIBIR EN ESTE LENGUAJE DE PROGRAMACIÓN.
PRESENTAMOS UNA FORMA PRÁCTICA DE APRENDER A UTILIZARLO,
DESTACANDO SU FACILIDAD Y LA CAPACIDAD DE MONITOREAR LAS HABILIDADES ADQUIRIDAS.
"""


# EJERCICIO 7: DECLARAR UNA VARIABLE DE EDAD Y DENTRO DE ESA VARIABLE EVALUAR DENTRO DE ESA EDAD ES MAYOR O IGUAL A 18

EDAD = 19
valor = EDAD >= 18
print(valor)

# EJERCICIO 8: CREAR UNA TUPLA CON LOS DIAS DE LA SEMANA DE LUNES HASTA EL DOMINGO Y RETORNAR EL VALOR CON EL POSICIONAL DE 2

Semana = ("Lunes", "Martes", "Miercoles", "Jueves", "Viernes", "Sabado", "Domingo")
print(Semana[2])
`````

***RESULTADOS:***

![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/EJERCICIOS 1.png)

---

# EJERCICIOS 2

+ **Ejercicio 1 # Calcular la suma de dos numeros e imprimir el resultado**
+ **Ejercicio 2 # Calcular la resta de dos numeros e imprimir el resultado**
+ **Ejercicio 3 # Calcular el producto de dos números e imprimir el resultado (*)**
+ **Ejercicio 4 # Calcular la división de dos numeros e imprimir el resultado**
+ **Ejercicio 5 # Calcular el residuo de una división de dos numeros e imprimir el resultado**
+ **Ejercicio 6 # Calcular la potencia de dos numeros e imprimir el resultado**
+ **Ejercicio 7 # Calcular el cosiente de una división de dos numeros e imprimir el resultado**
+ **Ejercicio 8 # Verificar si un número es igual a otro e imprimirlo**

***SINTAXIS DE LOS EJERCICIOS MENCIONADOS:***

`````py
numero1 = input("Ingresa tu primer numero: ")
numero2 = input("Ingresa tu segundo numero: ")

a = int(numero1)
b = int(numero2)

# EJERCICIO 1: Calcular la suma de 2 numeros e imprimir el resultado

suma = a + b
print ("El resultado de la suma es: ", suma)

# EJERCICIO 2: Calcular la resta de 2 numeros e imprimir el resultado

resta = a - b
print ("El resultado de la resta es: ", resta)

# EJERCICIO 3: Calcular el producto de 2 numeros e imprimir el resultado

producto = a * b
print ("El resultado de la multiplicacion es: ", producto)

# EJERCICIO 4: Calcular la division de 2 numeros e imprimir el resultado

division = a / b
print ("El resultado de la division es: ", division)

# EJERCICIO 5: Imprimir el residuo de la division de 2 numeros

residuo = a % b
print ("El resultado de la division con residuo es: ", residuo)

# EJERCICIO 6: Calcular la potencia de 2 numeros e imprimir el resultado

potencia = a ** b
print ("El resultado de la potencia es: ", potencia)

# EJERCICIO 7: Calcular el cociente de una division de 2 numeros e imprimir el resultado

cociente = a // b
print ("El resultado de la division con su cociente es: ", cociente)

# EJERCICIO 8: Verificar si un numero es igual a otro e imprimirlo

verificar = a == b
print ("El valor es: ", verificar)
`````

***RESULTADOS:***

![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/EJERCICIOS 2.png)

---

# EJERCICIOS 3

+ **Ejercicio 1: #Crear una lista llamada `numeros` con números enteros, luego imprimir la lista y limpiar la lista.**
+ **Ejercicio 2:  3Crear una lista llamada `frutas` con nombres de frutas, luego imprimir la lista y limpiar la lista.**
+ **Ejercicio 3: #Crear una lista vacía llamada `lista_vacia` y luego imprimir la lista.**
+ **Ejercicio 4: #Crear una lista llamada `numeros` con números enteros y luego imprimir el tercer número de la lista.**
+ **Ejercicio 5: #Crear una lista llamada `frutas` con nombres de frutas y #luego agregar una fruta adicional a la lista. Imprimir la lista actualizada.**
+ **Ejercicio 6: #Crear una lista llamada `numeros` con números enteros y luego calcular la suma de todos los números en la lista.**
+ **Ejercicio 7: #Crear una lista llamada `frutas` con nombres de frutas y luego imprimir la longitud de la lista.**
+ **Ejercicio 8: #Crear una lista llamada `numeros` con números enteros y luego ordenarla en orden ascendente. Imprimir la lista ordenada.**
+ **Ejercicio 9: Crear una lista llamada `numeros` con números enteros y luego encontrar el número más grande en la lista. Imprimir el número más grande.**
+ **Ejercicio 10: Crear una lista llamada `numeros` con números enterosy luego encontrar el número más pequeño en la lista. Im primir el número más pequeño.**

***SINTAXIS DE LOS EJERCICIOS MENCIONADOS:***

`````py
# EJERCICIO 1: Crear una lista llamada "numeros" con 3 enteros y limpiar la lista

numeros = [10, 4, 67]
numeros.clear()
print("El arreglo de numeros vacio: ", numeros)

# EJERCICIO 2: Crear una lista llamada "frutas" y luego imprimir la lista

frutas = ["Fresa", "Platano", "Manzana"]
print("El arreglo frutas : ", frutas)

# EJERCICIO 3: Crear una lista llamada "lista_vacia" e imprimir

lista_vacia = []
print("Lista vacia: ", lista_vacia)

# EJERCICIO 4: Crear una lista con numeros enteros y luego imprimir el tercer lugar

numeros2 = [24, 83, 66, 39, 50]
print("Posicion numero 3 del arreglo: ", numeros2[3])

# EJERCICIO 5: Crear una lista llamada "frutas" con nombres de frutas y luego agregar una fruta adicional a la lista e imprimir

frutas2 = ["Fresa", "Platano", "Manzana"]
frutas2.insert(3, "Sandia")
print("Arreglo agregandole una fruta: ", frutas2)

# EJERCICIO 6: Crear una lista llamada "numero enteros" y calcular una suma de todos los numeros e imprimir 

numeros_enteros = [46, 78, 23, 10, 98]
for valores in numeros_enteros:
	suma = valores+ valores

print("La suma de la lista es de: ", suma)

# EJERCICIO 7: Crear una lista llamada "frutas" con nombres de frutas y luego imprimir la longitud de la lista

frutas3 = ["Fresa", "Platano", "Manzana"]
print("La longitud es de: ", len(frutas3))

# EJERCICIO 8: Crear una lista llamada "numeros" con numeros enteros y ordenar la lista en orden ascendente e imprimir

numeros3 = [5, 27, 15, 8, 100]
print("Lista de numeros desordenados:", numeros3)
numeros3.sort()
print("Lista de numeros ordenados:", numeros3)
	

# EJERCICIO 9: Crear una lista llamada "numeros" con numeros enteros y que imprima el valor mas grande de la lista

numeros4 = [5, 27, 15, 8, 100]
maximo = max(numeros4)
print("El numero mas grande es: ", maximo)

# EJERCICIO 10: Crear una lista llamada "numeros" con numeros enteros y que imprimir el valor mmas pequeño de la lista

numeros5 = [5, 27, 15, 8, 100]
minimo = min(numeros5)
print("El numero mas pequeño es: ", minimo)
`````
***RESULTADOS:***

![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/EJERCICIOS 3.png)

---

# EJERCICIOS 4

+ **Ejercicio 1:** Crea un diccionario vacío llamado `mi_diccionario`.
+ **Ejercicio 2:** Agrega tres pares clave-valor al diccionario `mi_diccionario` relacionados con nombres y edades.
+ **Ejercicio 3:** Accede a la edad dentro de `mi_diccionario` primer elemento.
+ **Ejercicio 4:** Modifica la segunda edad dentro de  en `mi_diccionario`.
+ **Ejercicio 5:** Itera a través de las claves en `mi_diccionario` e imprime cada clave.
+ **Ejercicio 6:** Itera a través de los valores en `mi_diccionario` e imprime cada valor.
+ **Ejercicio 7:** Borra todos los elementos de `mi_diccionario`.
+ **Ejercicio 8:** Crea un diccionario llamado `frutas` con tres frutas y sus cantidades correspondientes como valores.
+ **Ejercicio 9:** Incrementa en 2 la cantidad de manzanas en `frutas`.
+ **Ejercicio 10:** Escribe una función llamada `buscar_fruta` que tome el nombre de una fruta como argumento y devuelva la cantidad de esa fruta en el diccionario `frutas`.
+ **Ejercicio 11:** Escribe una función llamada `agregar_fruta` que tome el nombre de una fruta y una cantidad como argumentos y agregue esta fruta al diccionario `frutas`.
+ **Ejercicio 12:** Escribe una función llamada `eliminar_fruta` que tome el nombre de una fruta como argumento y elimine esa fruta del diccionario `frutas`.

***SINTAXIS DE LOS EJERCICIOS MENCIONADOS:***

`````py
# EJERCICIO 1

mi_diccionario = {}
print("EJERCICIO 1:", mi_diccionario)

# EJERCICIO 2
mi_diccionario = {
	'dict1': 
	{
	'name1': "Jorge",
	'age1': 19
	},
	'dict2': {
	'name2': "Paulina",
	'age2': 39
	},
	'dict3': {
	'name3': "Santiago",
	'age3': 1
	}
}
print("EJERCICIO 2: ", mi_diccionario)

# EJERCICIO 3

print("EJERCICIO 3: ", mi_diccionario['dict1']['age1'])

# EJERCICIO 4

mi_diccionario['dict2']['age2'] = 50
print("EJERCICIO 4: ", mi_diccionario['dict2']['age2'])

# EJERCICIO 5
for claves in mi_diccionario.keys():
	print("EJERCICIO 5: ", claves)

# EJERCICIO 6
for valores in mi_diccionario.values():
	print("EJERCICIO 6: ", valores)

# EJERCICIO 7
mi_diccionario.clear()
print("EJERCICIO 7: ", mi_diccionario)

# EJERCICIO 8
i = 1
frutas = {}
while i <= 3:
	fruta = input("Nombre de la fruta: ")
	cantidad = int(input("Cantidad de esa fruta: "))
	frutas[fruta] = cantidad
	i += 1


print("EJERCICIO 8. ", frutas)

# EJERCICIO 9

cantidad = 0 

for nombres in frutas.keys():
    if nombres == 'Manzanas':
        cantidad = frutas['Manzanas']
        cantidad += 2

print("EJERCICIO 9. Cantidad de manzanas:", cantidad)


# EJERCICIO 10

def buscar_fruta(fruta):
	for buscar in frutas.keys():
		if buscar == fruta:
			cantidad = frutas.get(fruta)
			if cantidad == cantidad:
				print("EJERCICIO 10: ", fruta, "son: ", cantidad)

fruta = input("Escribe el nombre de la fruta a buscar: ")
buscar_fruta(fruta)

# EJERCICIO 11

def agregar_fruta(fruta, cantidad):
	print("EJERCICIO 11: Frutas no agregadas: ", frutas)
	if fruta != frutas.keys():
		frutas[fruta] = cantidad
		print("EJERCICIO 11: Fruta agregada: ", frutas)
	else:
		print("EJERCICIO 11: Esa fruta ya existe y no la puedes agregar")

fruta = input("Escribe una fruta nueva para agregar al diccionario: ")
cantidad = int(input("Ahora su cantidad: "))
agregar_fruta(fruta, cantidad)

# EJERCICIO 12

def eliminar_fruta(fruta):
	if fruta in frutas:
		del frutas[fruta]
		print("EJERCICIO 12: ", frutas)
	else:
		print("EJERCICIO 12: La fruta no existe y no se puede eliminar")


fruta = input("Escribe la fruta que deseas eliminar: ")
eliminar_fruta(fruta)
`````
***RESULTADOS:***

![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/EJERCICIOS 4.png)

---

# EJERCICIOS 5

+ **Ejercicio 1:** Pedir al usuario un número e imprimir si es positivo, negativo o igual a cero.
+ **Ejercicio 2:** Pedir al usuario dos números e imprimir cuál es el mayor de los dos.
+ **Ejercicio 3:** Pedir al usuario un número e imprimir si es par o impar.
+ **Ejercicio 4:** Pedir al usuario su edad e imprimir si es mayor de edad (mayor o igual a 18 años) o menor de edad.
+ **Ejercicio 5:** Pedir al usuario un número e imprimir si es mayor, menor o igual a 10.
+ **Ejercicio 6:** Pedir al usuario dos números e imprimir si son iguales o diferentes.
+ **Ejercicio 7:** Pedir al usuario una contraseña e imprimir "Contraseña correcta" si es igual a "secreto", de lo contrario, imprimir "Contraseña incorrecta".
+ **Ejercicio 8:** Pedir al usuario un número e imprimir si es positivo y menor que 10.
+ **Ejercicio 9:** Pedir al usuario dos números e imprimir si ambos son pares.
+ **Ejercicio 10:** Pedir al usuario su edad y su género (hombre o mujer) e imprimir "Bienvenido" si es un hombre mayor de 21 años o una mujer mayor de 18 años. De lo contrario, imprimir "Acceso denegado".
+ **Ejercicio 11:** Pedir al usuario dos números e imprimir el mayor de los dos, pero si son iguales, imprimir "Los números son iguales".
+ **Ejercicio 12:** Pedir al usuario un número del 1 al 7 e imprimir el día de la semana correspondiente. Si el número está fuera de ese rango, imprimir "Número inválido".

***SINTAXIS DE LOS EJERCICIOS MENCIONADOS:***

`````py
#EJERCICIO 1

numero = input("E1. Digita un numero: ")
verificar = int(numero)

if verificar > 0:
	print("El numero es positivo", verificar)
elif verificar < 0:
	print("El numero es negativo", verificar)
elif verificar == 0:
	print("El numero es igual a 0", 0)


# EJERCICIO 2

dato1 = int(input("E2. Digita primer numero: "))
dato2 = int(input("E2. Digita segundo numero: "))

if dato1 > dato2:
	print("El", dato1, "es mayor que", dato2)
else:
	print("El", dato2, "es mayor que", dato1)

# EJERCICIO 3

par_impar = int(input("E3. Digita un numero: "))
verifica = par_impar % 2

if verifica == 0:
	print("El numero", par_impar, "es par")
else: 
	print("El numero", par_impar, "es impar")

# EJERCICIO 4

edad = int(input("E4. Digita tu edad: "))

if edad >= 18:
	print("Tienes", edad, "y eres mayor de edad")
else:
	print("Tienes", edad, "y eres menor de edad")

# EJERCICIO 5

numero = int(input("E5. Digita el numero: "))

if numero < 10:
	print("El numero", numero, "es menor que 10")
elif numero > 10:
	print("El numero", numero, "es mayor que 10")
elif numero == 10:
	print("El numero", numero, "es igual que 10")

# EJERCICIO 6

dato1 = int(input("E6. Digita primer numero: "))
dato2 = int(input("E6. Digita segundo numero: "))

if dato1 != dato2:
	print("El", dato1, "es distinto al", dato2)
else:
	print("El", dato1, "es igual al", dato2)

# EJERCICIO 7

contra = input("E7. Escribe el password secreto: ")
secreto = "1111"

if contra == secreto:
	print("Password correcto")
else:
	print("Password incorrecto")

# EJERCICIO 8

numero = int(input("E8. Escribe un numero: "))

if numero > 0:
	if numero < 10:
		print("El numero", numero, "es positivo y menor que 10")
	else:
		print("El numero", numero, "es positivo pero mayor que 10")

# EJERCICIO 9

num1 = int(input("E9. Escribe el primer numero: "))
num2 = int(input("E9. Escribe el segundo numero: "))

par1 = num1 % 2
par2 = num2 % 2

if par1 == 0 and par2 == 0:
	print("Los numeros", num1, "y", num2, "son pares")
else:
	print("Un o los numeros", num1, "y", num2, "son impar o impares ")

# EJERCICIO 10

edad = int(input("E10. Escribe tu edad: "))
genero = input("E10. Escribe tu genero: ")

if genero == "hombre" and edad >= 21:
	print("Bienvenido")
elif genero == "mujer" and edad >= 18:
	print("Bienvenido")
else:
	print("Acceso denegado")

# EJERCICIO 11

num1 = int(input("E11. Escribe el primer numero: "))
num2 = int(input("E11. Escribe el segundo numero: "))

if num1 > num2:
	print(num1, "es mayor")
elif num2 > num1:
	print(num2, "es mayor")
elif num1 == num2:
	print("Los numeros son iguales")

# EJERCICIO 12

aleatorio = int(input("E12. Digita un numero desde el 1 al 7: "))

if aleatorio <= 0 or aleatorio > 7:
	print("Ese numero no esta invalido")
elif aleatorio == 1:
	print("Lunes")
elif aleatorio == 2:
	print("Martes")
elif aleatorio == 3:
	print("Miercoles")
elif aleatorio == 4:
	print("Jueves")
elif aleatorio == 5:
	print("Viernes")
elif aleatorio == 6:
	print("Sabado")
elif aleatorio == 7:
	print("Domingo")
`````

***RESULTADOS:***

![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/EJERCICIOS 5.png)

---

# EJERCICIOS 6

+ **Ejercicio 1:** Imprimir los números del 1 al 10 utilizando un bucle `for`.
+ **Ejercicio 2:** Imprimir los números pares del 2 al 20 utilizando un bucle `for`.
+ **Ejercicio 3:** Imprimir los números del 10 al 1 en orden descendente utilizando un bucle `for`.
+ **Ejercicio 4:** Pedir al usuario un número `n` e imprimir los números del 1 al `n` utilizando un bucle `for`.
+ **Ejercicio 5:** Calcular la suma de los números del 1 al 100 utilizando un bucle `for` y luego imprimir el resultado.
+ **Ejercicio 6:** Calcular el producto de los números del 1 al 10 utilizando un bucle `for` y luego imprimir el resultado.
+ **Ejercicio 7:** Pedir al usuario un número `n` e imprimir la tabla de multiplicar del `n` del 1 al 10 utilizando un bucle `for`.
+ **Ejercicio 8:** Imprimir los números del 1 al 10 utilizando un bucle `while`.
+ **Ejercicio 9:** Pedir al usuario un número `n` e imprimir los números del 1 al `n` utilizando un bucle `while`.
+ **Ejercicio 10:** Calcular la suma de los números del 1 al 100 utilizando un bucle `while` y luego imprimir el resultado.
+ **Ejercicio 11:** Calcular el producto de los números del 1 al 10 utilizando un bucle `while` y luego imprimir el resultado.
+ **Ejercicio 12:** Pedir al usuario un número `n` e imprimir la tabla de multiplicar del `n` del 1 al 10 utilizando un bucle `while`.

***SINTAXIS DE LOS EJERCICIOS MENCIONADOS:***

`````py
# EJERCICIO 1

i = 0

for i in range(0, 10):
	i += 1
	print("EJERCICIO 1: ", i)

# EJERCICIO 2

i = 0
for i in range(1, 22):
	dato = i % 2
	if dato == 0:
		print("EJERCICIO 2: ", i)

# EJERCICIO 3

i = 0
for i in range(10, 1, -1):
	print("EJERCICIO 3: ", i)

# EJERCICIO 4

numero = int(input("Escribe un numero: "))
for i in range(1, numero):
	i += 1
	print("EJERCICIO 4: ", i)

# EJERCICIO 5
suma = 0

for i in range(1, 101):
	suma += i 

print("EJERCICIO 5: ", suma)
	
# EJERCICIO 6
producto = 1

for i in range(1, 11):
	producto *= i

print("EJERCICIO 6: ", producto)

# EJERCICIO 7

numero = int(input("Digita un numero: "))

for i in range(1, 11):
	tabla = i * numero
	print(numero, "X", i, "=", tabla)

# EJERCICIO 8

valor = 1

while valor <= 10:
	print("EJERCICIO 8: ", valor)
	valor += 1

# EJERCICIO 9

valor = int(input("Inserta un numero: "))
i = 1
while i <= valor:
	print("EJERCICIO 9: ", i)
	i += 1
# EJERCICIO 10

i = 1
suma = 0

while i <= 100:
    suma += i
    i += 1

print("EJERCICIO 10: ", suma)

# EJERCICIO 11

i = 1
numero = 1

while numero <= 10:
	i *= numero
	numero += 1

print("EJERCICIO 11: ", i)

# EJERCICIO 12

numero = int(input("Numero: "))
i = 1

while i <= 10:
	tabla = numero * i 
	print(numero, "x", i, "=", tabla)
	i += 1
`````
***RESULTADOS:***

![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/EJERCICIOS 6-A.png)
![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/EJERCICIOS 6-B.png)
![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/EJERCICIOS 6-C.png)
![Alt](/home/jorchitoxyz/Imágenes/Capturas de pantalla/EJERCICIOS 6-D.png)

