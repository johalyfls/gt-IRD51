---
title: LECCION 8- INSTALACION Y FUNDAMENTOS DJANGO
created: '2023-12-04T00:28:11.584Z'
modified: '2023-12-05T14:57:12.289Z'
---

# LECCION 8- INSTALACION Y FUNDAMENTOS DJANGO

## *Instalacion Django*

Tenemos que instalar PYTHON la version 3.11 desde la pagina principal 

## Una vez instalado tendras que abrir el cmd
En el cmd daremos python --version

Posteriormente  tenemos que crear una carpeta llamada Programacion-de-Redes en Escritorio

## Abrimos la carpeta desde el cmd con el comando
  cd C:\Users\Equipo\Desktop\Programacion-de-Redes

Una vez abierta la carpeta daremos 
  dir
  >esto sirve para poder ver lo que hay dentro de nuestra carpeta el cual encontraremos dos que son .env y mysite

## Abrimos 
  cd .env
  cd Scripts
  activate

## Instalamos de Django un entorno visual
  python -m pip install Django 

## Realizamos la creacion de proyecto web Django
  django-admin startproject mysite

## Salimos de esas carpetas y abrimos 
  cd mysite
al dar dir veremos que estan instaladas manage.py y mysite

## Ejecutamos el comando
  python
  >>>import django
  >>>print(django.get_version())
  4.2.5
  >>>exit()

## Realizamos la activacion de entorno virtual existente:
    dir
    cd .env
    cd Scripts
    activate
    cd ..
    cd ..
    cd mysite
    python manage.py runserver
Y comprobamos que corra nuestro django con ese codigo.

## *Fundamentos Django*
```python
def sumar (request, param1, param2):
    resultado = param1 + param2
    cadena = f"El resultado de la suma es: {resultado} "
    return HttpResponse(cadena)

def restar (request, param1, param2):
    resultado = param1 - param2
    cadena = f"El resultado de la resta es: {resultado} "
    return HttpResponse(cadena)

def multiplicar (request, param1, param2):
    resultado = param1 * param2
    cadena = f"El resultado de la multiplicacion es: {resultado} "
    return HttpResponse(cadena)

def dividir (request, param1, param2):
    resultado = param1 / param2
    cadena = f"El resultado de la division es: {resultado} "
    return HttpResponse(cadena)
```

>Este código define cuatro funciones (sumar, restar, multiplicar y dividir) en un marco web de Python, probablemente Django o Flask, basado en el uso de HttpResponse. Cada función realiza una operación matemática específica y devuelve una respuesta HTTP que contiene el resultado en una cadena formateada.
