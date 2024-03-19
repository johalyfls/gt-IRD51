---
title: LECCION 2- PYTHON
created: '2023-12-03T22:27:16.527Z'
modified: '2023-12-05T00:08:13.772Z'
---

# LECCION 2- PYTHON

## *Operadores aritméticos*
Indican que se relacionan a las operaciones matemáticas que usan con frecuencia y son de común conocimiento. 

"""
    Operación           Símbolo
    ============================
    Adición             +
    Substracción        -
    Multiplicación      *
    División            /
    División entera     //
    Exponente           **
    Módulo/Residuo      %
"""

**Codigo en Python:** 
```
  operandoA = 3
  operandoB = 2

    print(f"Resultado de suma: {operandoA+operandoB}")
    print(f"Resultado de resta: {operandoA-operandoB}")
    print(f"Resultado de multiplicación: {operandoA*operandoB}")
    print(f"Resultado de división: {operandoA/operandoB}")
    print(f"Resultado de división entera: {operandoA//operandoB}")
    print(f"Resultado de exponente: {operandoA**operandoB}")
    print(f"Resultado de residuo: {operandoA%operandoB}")
```

## *Operador de asignación*
Se utiliza para asignar un valor a una variable. Además del operador de asignación existen otros operadores de asignación compuestos que realizan una operación básica sobre la variable a la que se le asigna el valor.

```
  miVariable = 10
    print(miVariable)
```

## Reasignación
```
  miVariable = miVariable + 1
```

## Sintaxis más reducida
## Incremento con reasignación
```
  miVariable += 1
    print(miVariable)
```

## Decremento
```
  miVariable -= 2
    print(miVariable)
```

## Multiplicación
```
  miVariable *= 3
    print(miVariable)
```

## División
```
  miVariable /= 2
    print(miVariable)
```

## *Operadores de comparación*
"""
    Los operadores de comparación se utilizan para comparar dos o más valores. El resultado de estos operadores siempre es True o False.

    Operador	    Descripción
    >               Mayor que. True si el operando de                  la izquierda es estrictamente                      mayor que el de la derecha; 
                    False en caso contrario.

    >=	            Mayor o igual que. True si el                      operando de la izquierda es mayor                  o igual que el de la derecha; 
                    False en caso contrario.

    <	              Menor que. True si el operando de                  la izquierda es estrictamente                      menor que el de la derecha; 
                    False en caso contrario.

    <=	            Menor o igual que. True si el                      operando de la izquierda es menor                  o igual que el de la derecha; 
                    False en caso contrario.

    ==	            Igual. True si el operando de la                   izquierda es igual que el de la                    derecha; 
                    False en caso contrario.

    !=	            Distinto. True si los operandos                    son distintos; 
                    False en caso contrario
"""
**Codigo en Python:** 
```
  a = 4
  b = 2

    print(a>b)
    print(a>=b)
    print(a<b)
    print(a<=b)
    print(a==b)
    print(a!=b)
```

## *Operadores lógicos o booleanos*
"""
    Se usan para combinar dos valores Booleanos y devolver un resultado verdadero, falso o nulo.

    Operación	Descripción:
    a or b	    Solo se evalúa el segundo operando si              el primero es falso.

    a and b	    Solo se evalúa el segundo operando si              el primero es verdadero.

    not a	      Si a se evalúa a falso, entonces                   devuelve True.
"""
**Codigo en Python:** 
```
  a = True 
  b = False

    print(a or b)

    b = True
    print(a and b)

    print(not b)
```
