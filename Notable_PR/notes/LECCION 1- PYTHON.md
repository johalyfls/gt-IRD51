---
title: LECCION 1- PYTHON
created: '2023-12-04T00:06:51.946Z'
modified: '2023-12-05T00:02:07.605Z'
---

# LECCION 1- PYTHON

## *Imprimir* 
```
    print("Hello word")
```

## *Variables*
## Declarar un variable
```
  miVariable = "Hola desde python"
```
## Mandar a imprimir variable
```
    print(miVariable)
```

## Una variable podremos cambiar su valor
```
  miVariable = 10

    print(miVariable)
```

## Nota se hará referencia a las direcciones de memoria
``` 
  x = 10
  y = 2
  z = x + y

    print(z)
```

## Saber dirección de memoria, las direcciones puede cambiar en cada ejecución
    print(id(z))

## *Tipos de datos*
## Tipos númericos
```
  x = 10
  cadena = "Cadena de texto"
    print(x)
```

## Tipos de variables
```
    print(type(x),type(cadena))
```

## Pista de tipo de dato
```
  y:int = 10
  #y = "Cadena"
    print(y,type(y))
```

## Variables de tipo bool
```
  x = True
    print(x,type(x))
```

## Tipo de dato float
```
  x = 18.4
    print(x,type(x))
```

## Manejo de cadenas
## Concatenación unión de dos o mas cadenas
```
  miGrupoFavorito = "Evanescence" + " " + "The best rock band"
    print("Mi grupo favorito es: " + miGrupoFavorito)
    print("Mi grupo favorito es:",miGrupoFavorito)
```

## Error común de Concatenación
## + sobrecarga de operadores
```
  a = "1"
  b = "2"
    print(a+b)
    print(int(a)+int(b))
```

## Bool (boolean)= Valor verdadero o falso
```
  valorVerdadero = True
  valorFalso = False
    print(valorVerdadero,valorFalso,type(valorVerdadero))
```

## Expresión para obtener una expresión verdadera o falsa
```
  miVariable = 3 > 2
    print(miVariable)

  if miVariable:
    print("Es verdadero")
  else:
    print("Es falso")

```
## *Entrada de datos*
## Función input para procesar la entrada de un usuario
```
  resultado = input("Ingresar texto: ")
    print("Valor proporcionado: ",resultado)
```

## Suma de valores ingresados
## Si no se hace una conversiòn correcta se obtendrà un
## Exception value error
```
    print("Suma de datos ingresados")

  a = int(input("Ingrese primer valor: "))
  b = int(input("Ingrese segundo valor: "))

    print("Resultado:",a+b)

    print("Fin del programa")
```
