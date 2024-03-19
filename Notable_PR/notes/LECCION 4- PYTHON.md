---
title: LECCION 4- PYTHON
created: '2023-12-04T00:26:29.111Z'
modified: '2023-12-05T00:40:38.201Z'
---

# LECCION 4- PYTHON

## *I LISTAS*
Las listas en Python son un tipo de dato que permite almacenar datos de cualquier tipo. 
Son mutables y dinámicas.
Las listas en Python son uno de los tipos o estructuras de datos más versátiles del lenguaje, ya que permiten almacenar un conjunto arbitrario de datos. 
Es decir, podemos guardar en ellas prácticamente lo que sea. 
Si vienes de otros lenguajes de programación, se podría decir que son similares a los arrays.

## Definir una lista de tipo string
```
	nombres = ["Diana","Maria","Luis","Carlos"]

		print(nombres)
```

## Acceder a los elementos de manera individual
```
		print(nombres[0])
		print(nombres[1])
```

## Accedera los elementos de manera inversa
```
		print(nombres[-1])
		print(nombres[-2])
```

## Acceder a rangos de una lista
```
		print(nombres[0:2])
```

## Indicar el índice especifo
```
		print(nombres[:3])
```

## Indicar indice indicado hasta el final
```
		print(nombres[1:])
```

## Cambiar valores de un índice
```
	nombres[0] = "Laura"
		print(nombres[0])
```

## Iterar lista #nombras listas en plural
```
	for nombre in nombres:
	    print(nombre)
```

## Preguntar logitud de una lista
```
		print(len(nombres))
```

## Agregar elemntos a una lista
```
	nombres.append("Nadia")
		print(nombres[-1])
```

## Insertar un elemento en un índice en especifo
```
	nombres.insert(1,"Mariana")
		print(nombres)
```

## Remover un elemento por valor
```
	nombres.remove("Mariana")
		print(nombres)
```

## Remover último valor agregado
```
	nombres.pop()
		print(nombres)
```

## Eliminar un elemento en un índice indicado
```
	del nombres[0]
		print(nombres)
```

## Eliminar todos los elementos de una lista
```
	nombres.clear()
		print(nombres)
```

## ELiminar la lista por completo
```
	del nombres
		print(nombres)
```


## *II TUPLAS*
La tupla es inmutable y guarda el orden de los datos.
A primera vista, las Python tuples se parecen mucho a las conocidas listas de Python. Ambas son listas que contienen y almacenan diversos tipos de contenidos para luego poder presentarlos con claridad. Sin embargo, hay una diferencia: el contenido de una tupla de Python es inmutable. Esto quiere decir que una vez se ha cargado de contenido, permanece inalterable y no puede ser eliminada. Las Python tuples resultan especialmente útiles si el contenido consta de variables que debes conservar en su forma y composición original indispensablemente. 
Usando Python tuples puedes asegurarte de que el contenido está en su estado original.

```
	frutas = ("Naranja","Platano","Guayaba")
```

## Longitud de tupla
```
		print(len(frutas))
```
## Acceder aún elemento
```
		print(frutas[0])
```

## Navegación inversa
```
		print(frutas[-1])
```

## Acceder aún rango de valores
```
		print(frutas[0:4])
```

## Declaración de una tupla de un valor
```
        frutas = ('Naranja',)
```
Si no se agrega una coma al final, se entiende como una cadena

## Recorrer un elemento de la tupla
```
	valor = 0

	while valor < len(frutas):
		print(frutas[valor],end=", ")
	valor += 1
```

## Cambiar el dato de una tupla
```
	frutasLista = list(frutas)

	frutasLista.append('Pera')

	frutas = tuple(frutasLista)

		print('\n',frutas)
```

## Eliminar tupla por completo
```
del frutas
```

## *III SET*

Los set en Python son un tipo que permite almacenar varios elementos y acceder a ellos de una forma muy similar a las listas pero con ciertas diferencias:
Los elementos de un set son único, lo que significa que no puede haber elementos duplicados.
Los set son desordenados, lo que significa que no mantienen el orden de cuando son declarados.
Sus elementos deben ser inmutables.

## Definir un set (sin orden e índices)
```
	planetas = {'Marte','Júpiter','Venus'}

		print(planetas)
```

## Longitud del set
```
		print(len(planetas))
```

## Validar exitencia en un elemento
**Esto mismo se aplica en tuplas y listas**
```
		print('Marte' in planetas)
```

## Agregar elementos a set
```
	planetas.add('Tierra')

		print(planetas)

	planetas.add('Tierra')

		print(planetas)
```

## Eliminar elementos
```
	planetas.remove('Tierra')

		print(planetas)
```

**Si se intenta eliminar un valor que no existe mandará un error keyError**

## Está función no manda error si no existe el elemento
```
	planetas.discard('Tierras')
```

## Limpiar set
```
	planetas.clear()
```

## Eliminar set
```
	del planetas
```
