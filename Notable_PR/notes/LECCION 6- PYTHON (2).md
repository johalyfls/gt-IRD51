---
title: LECCION 6- PYTHON
created: '2023-12-04T00:27:11.273Z'
modified: '2023-12-05T01:11:00.259Z'
---

# LECCION 6- PYTHON 

## *I Manejo de archivos de texto*
La función open simplemente abre un determinado fichero.
Puede parecer sencillo pero en gran cantidad de
ocasiones es usada de manera incorrecta.
**content_copy**

¿Qué es un file handle?
Un identificador de archivo, en el contexto de la informática, es un número de referencia temporal que un sistema operativo asigna a un archivo cuya 
apertura solicita un usuario.

La función open devuelve lo que se conoce como file handle, y es dado por el sistema operativo a tu aplicación de Python. Una vez has terminado de usar este file handle 
(que te permite acceder al fichero) es importante devolverlo y cerrarlo. 
Esto se debe en parte a que el sistema operativo tiene un número máximo de ficheros que puede tener abiertos, y no tendría mucho sentido mantener uno abierto si ya no se está usando.

## Abrir un archivo
  try:

## Archivo existente o no
```
  archivo = open( 'prueba.txt', 'w', encoding='utf8' )
  content_copy

  archivo.write( 'Agregamos información al archivo' )
```

## Salto de línea
```
  archivo.write( '\n' )

  archivo.write( 'Adiós' )
  archivo.close()

  except Exception as e:
    print(e)
```

Lectura de archivos
w - write
a - append
r - read
x - create

try:
```
  *Rutas en windows*
  *c:\users\usuario\desktop\archivo.txt*
  archivo = open('./prueba.txt','r',encoding='utf8')
  content_copy
```

## El método read lee todo el archivo
```
    print( archivo.read() )
```

## Leer algunos caracterés
```
    print( archivo.read(5) )
```

## Leer líneas completas
```
    print( archivo.readline() )
```

## Iteración del archivo
```
  for linea in archivo:
    print(linea)
```

## Leer todas la líneas del archivo
```
    print( archivo.readlines() )
```

## Acceder a una línea de la lista
```
    print( archivo.readlines()[0] )
```

## Anexar información append
```
  archivo2 = open('copia.txt','w',encoding='utf8')
  archivo2.write(archivo.read())

  archivo.close()
  archivo2.close()

  except Exception as e:
    print(e)
```

##  *II import csv*

Sentencia with
La sentencia with se usa para ajustar la ejecución de un bloque con métodos definidos por un administrador de contexto. Esto permite que los patrones de uso comunes try…except…finally se encapsulen para una reutilización conveniente.

```
  with open('prueba.txt','r',encoding='utf8') as archivo:
    print(archivo.read())
```

## Crear archivos CSV (excel)
```
cursos = [
{
'id': 1,
'title': 'Curso profesional de Python',
'description': 'Descripción 1'
} ,
{
'id': 2,
'title': 'Curso profesional de Django',
'description': 'Descripción 2'
} ,
{
'id': 3,
'title': 'Curso profesional de Base de datos',
'description': 'Descripción 3'
} ,
]

columnas = ['id', 'title', 'description']

with open('cursos.csv', mode='w') as file:
content_copy

escritura = csv.DictWriter(file, delimiter=',', fieldnames=columnas )
escritura.writeheader()

for curso in cursos:
    escritura.writerow(curso)
```

**Segunda creación de archivos**
```
encabezados = ['id', 'username', 'email']
usuarios = [
['1', 'user1', 'user1@pywombat.com'],
['2', 'user2', 'user2@pywombat.com'],
['3', 'user3', 'user3@pywombat.com'],
['4', 'user4', 'user3@pywombat.com'],
]

with open('usuarios.csv', mode='w') as file:
escritura = csv.writer(file)
escritura.writerow( encabezados ) # Creación columnas
content_copy

for usuario in usuarios:
    escritura.writerow( usuario )
```

## *III import csv*
```
with open('./usuarios.csv') as file:
content_copy

csv_reader = csv.reader(file, delimiter=',')
```

## Leer todas las columnas
```
for columna in csv_reader:
    print( columna )
```

## Saltar primera interación con contador
```
count = 0
for columna in csv_reader:
    if count != 0:
        print( columna )
    count += 1
```

## Saltar iteración con método next
```
next(csv_reader)
for columna in csv_reader:
    print( columna )
```

## Valores de columnas
```
for columna in csv_reader:
    id, username, email, *_ = columna
      print(name, username, email)
```

## Leer archivo como diccionario
```
csv_reader = csv.DictReader(file, delimiter=',')

for row in csv_reader:
    id = row['id']
    username = row['username']
    email = row['email']
      print(f"Id: {id}, Username: {username}, emai: {email}")
```
