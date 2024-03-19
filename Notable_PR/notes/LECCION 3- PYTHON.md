---
title: LECCION 3- PYTHON
created: '2023-12-03T22:33:35.178Z'
modified: '2023-12-05T00:12:13.760Z'
---

# LECCION 3- PYTHON

## *Sentencia if-else*
La estructura  if/elif/else es una forma común de controlar el flujo de un programa, lo que te permite ejecutar bloques de código específicos según el valor de algunos datos.

## Nota recordar uso de tabulación para sectores/bloque de código
```
  condicion = True

  if condicion == True:
      print("Condición verdadera")
  elif condicion == False:
      print('Condición falsa')
  else:
      print('Condición invalida')
```

## Validar contenido de una cadena
```
  cadena = ''

  if cadena:
      print(f'Cadena con valor: {cadena}')
  else:
      print(f'Cadena sin valor: {cadena}')
```

## Operador ternario
```
    print('Condición verdadera') if condicion else print('Condición falsa')

  valor = ("Falso", "Verdadero")[condicion]
    print(valor)

    print(("Falso","Verdadero")[condicion])

  condicion2 = False
  valor = (("Falso","Valor invalido")[condicion2],"Verdadero")[condicion2]
    print(valor)

  salida = False
  validacion = salida or 'No se devolvió nada'
    print(validacion)

    print(f"{False}:{int(False)} {True}:{int(True)}")
```

## *Sentencia/ciclo While*
El bucle while evalúa una condición y luego ejecuta un bloque de código si la condición es verdadera. El bloque de código se ejecuta repetidamente hasta que la condición llega ser o es falsa.

```
  condicion = True
  while condicion:
      print("Ejecutando ciclo while")
  else:
      print('Fin de ciclo while')
```

```
  contador = 0

  while contador < 3:
      print(f"Valor: {contador}")
      contador += 1 # contador = contador + 1
```

    También se pueden hacer contadores decendentes o asendentes

## *Ciclo For*
Es una herramienta muy útil en Python que permite iterar sobre objetos iterables y realizar operaciones repetitivas de manera sencilla y eficiente. Entre sus principales ventajas se encuentra su facilidad de uso y su capacidad para recorrer cualquier objeto iterable.

    Una cadena es un arreglo de caractéres
    Especificar orden

    H o l a
    0 1 2 3

    for variable_almacenamiento in arreglo/conjunto/iterable

Las palabras reservadas, como su nombre lo indican,son palabras las cuales el lenguaje de programación ya ha reservado para realizar ciertas tareas.

```
  cadena = "Hola"

  for caracter in cadena:
      print(caracter)

  for letra in "Holanda":
      if letra == "a":
          print(letra)
          break

  for var in range(10):
      if var % 2 == 0:
          print(f'Valor: {var}')

  for var in range(10):
      if var % 2 != 0:
          continue

      print(f'Valor: {var}')

```

