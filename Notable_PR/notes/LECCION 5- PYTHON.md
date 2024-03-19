---
title: LECCION 5- PYTHON
created: '2023-12-04T00:26:48.167Z'
modified: '2023-12-05T00:55:16.131Z'
---

# LECCION 5- PYTHON

## *I Funciones*
**content_copy**

Se puede entender una función como un conjunto de líneas de código que realizan una tarea específica y pueden tomar “Argumentos” para diferentes “Parámetros” que modifiquen su funcionamiento y los datos de salida. 
Una función te permite implementar operaciones que son habitualmente utilizadas en un programa y, de esta manera, reducir la cantidad de código

## Definir función
Las definiciones podemos definirlas en otros archivos y podemos importarlas
```
  def miFuncion():
    print('Saludos desde mi función')

  miFuncion()
```

## Parámetros función
La diferencia de un parametro y un argumento, es que el parametro es una variable dentro de la función y el argumento es el valor enviado a la función
```
  def miFuncionParametros(nombre,apellido):
    print(f"Saludos: {nombre} {apellido}")

  miFuncionParametros("Juan","Lopez")

  Return
  def sumar(a,b):
  return a + b

    print(f"Resultado {sumar(10,20)}")
```
**Valores por default de una función**
```
  def sumar2(a=0,b=0):
  return a+b

    print(f"Sumar1: {sumar2()}",f"Sumar2: {sumar2(10,20)}")
```

## *II Iterar nombres de una cantidad desconocida*

**Nota al definir *args python lo define como una tupla**
```
  def listarNombres(*nombres):
    print(type(nombres))
  for nombre in nombres:
    print(nombre)

  listarNombres('Juan','Carla','Maria','Hernesto')

  listarNombres('Laura','Carlos')

  keyword args kwargs
  def listarTerminos(**terminos):
  for llave,valor in terminos.items():
    print(f"{llave}:{valor}")

  listarTerminos(IDE="Integrated development Enviroment",PK="Primary key")

  kwargs = {"arg1": 10, "arg2": 100, "arg3": 1000}

  listarTerminos(**kwargs)
```

## *III Tipos de valores como Parámetros*

```
  def desplegar(nombres):
  for nombre in nombres:
    print(nombre)

  nombres = ['Juan','Carlos','Guillermo']

  desplegar(nombres)
```

**Un string es una lista de caracterés**
```
  desplegar('Carlos')
```

**Error al enviar un argumento no iterable**
```
  desplegar(10)
  desplegar(10,20)
  desplegar((10,20))
```

## Validar tipos de datos
```
  def desplegar2(valores):
  if type(valores) is tuple or type(valores) is list or type(valores) is str:
  for valor in valores:
    print(valor)
  else:
    print(valores)

  desplegar2(['Juan','Karla','Ivonne'])
  desplegar2(('Diana','Liliana','Zafiro'))
  desplegar2('Cadena de texto')
  desplegar2(10)
```

## **IV Tipos de valores como Parámetros**
```
  def desplegar(nombres):
  for nombre in nombres:
    print(nombre)

  nombres = ['Juan','Carlos','Guillermo']

  desplegar(nombres)
```

**Un string es una lista de caracterés**
```
  desplegar('Carlos')
```

**Error al enviar un argumento no iterable**
```
  desplegar(10)
  desplegar(10,20)
  desplegar((10,20))
```

## Validar tipos de datos
```
  def desplegar2(valores):
  if type(valores) is tuple or type(valores) is list or type(valores) is str:
  for valor in valores:
    print(valor)
  else:
    print(valores)

  desplegar2(['Juan','Karla','Ivonne'])
  desplegar2(('Diana','Liliana','Zafiro'))
  desplegar2('Cadena de texto')
  desplegar2(10)
```
