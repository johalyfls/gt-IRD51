---
title: LECCION 7- JSON
created: '2023-12-04T00:27:31.884Z'
modified: '2023-12-05T13:07:59.833Z'
---

# LECCION 7- JSON

## *JSON*

---
attachments: [Clipboard_2023-09-28-22-23-44.png, Clipboard_2023-09-28-22-23-45.png, Clipboard_2023-09-28-22-23-51.png, Clipboard_2023-09-28-22-26-06.png, Clipboard_2023-09-28-22-27-21.png, Clipboard_2023-09-28-22-40-24.png, Clipboard_2023-09-28-23-00-36.png, Clipboard_2023-09-28-23-01-36.png, Clipboard_2023-09-28-23-05-23.png, Clipboard_2023-09-28-23-12-14.png]
title: VI.- Archivos JSON
created: '2023-09-29T03:22:47.512Z'
modified: '2023-09-29T04:12:24.584Z'
---

## Archivos JSON
![](@attachment/Clipboard_2023-09-28-23-01-36.png)

## Introducción: 
**¿Qué es JSON?**
![](@attachment/Clipboard_2023-09-28-22-23-51.png)

El formato JSON fue inspirado por la sintaxis de JavaScript (un lenguaje de programación usado para desarrollo web). Pero desde entonces se ha convertido en un formato de datos independiente del lenguaje de programación. La mayoría de los lenguajes de programación que usamos hoy en día pueden generar y leer JSON.

---

**Importancia y usos de JSON**

JSON es un formato usado para almacenar o representar datos. Sus usos más frecuentes incluyen desarrollo web y creación de archivos de configuración.


Veamos por qué:

* **Desarrollo web:** JSON se usa comúnmente en aplicaciones web para enviar información desde el servidor al cliente o desde el cliente al servidor.

![](@attachment/Clipboard_2023-09-28-22-26-06.png)


* **Archivos de configuración:** el formato JSON también es usado para almacenar configuraciones y ajustes. Por ejemplo, para crear una aplicación para Chrome, debes incluir un archivo JSON llamado manifest.json para especificar el nombre de la aplicación, su descripción, versión actual y otras propiedades.

![](@attachment/Clipboard_2023-09-28-22-27-21.png)

---

**Estructura y formato JSON**

Ahora que ya sabes cómo se usa el formato JSON, veamos su estructura básica con un ejemplo que representa una orden de pizza:
	
```json
{ 
	"tamano": "mediana",
	"precio": 156.7,
	"toppings": ["champinones", "pepperoni", "albahaca"],
	"queso_extra": false,
	"delivery": true,
	"cliente": {
		"nombre": "Jane Doe",
		"telefono": null,
		"correo": "janedoe@email.com"
	}
}
```

> **Dato:** no se incluyen acentos en los ejemplos para evitar cualquier incompatibilidad entre JSON y caracteres especiales.

---

**Estas son las características principales del formato JSON:**

+ Posee una secuencia de pares clave-valor rodeados por un par de llaves {}.
+ Cada clave se asocia a un valor con este formato:

	
```json
"clave": <valor> 
```

> **Dato:** Los valores que incluyen comillas simples deben estar rodeados por comillas dobles.

---

Los pares clave-valor deben estar separados por una coma. Solo el último par no debe estar seguido de una coma.

```json
{
	"tamano": "mediana", # ¡Coma!
	"precio": 15.67
}
```


 > **Dato:** Generalmente estructuramos los archivos JSON con distintos niveles de indentación para que la información sea más fácil de leer.

---

**Tipos de datos JSON: claves y valores**

Los archivos JSON tienen reglas específicas que determinan los tipos de datos que son válidos para las claves y para los valores.

* Las claves deben ser cadenas de caracteres.
* Los valores pueden ser cadenas de caracteres, números, arreglos, valores Booleanos (true/ false), null, o un objeto JSON.

Según la documentación de Python:

* Las claves en los pares clave/valor de JSON siempre son de tipo str. Cuando se convierte un diccionario a JSON, todas las claves del diccionario se convierten a cadenas de caracteres.

---

**JSON vs. diccionarios de Python**

* JSON y los diccionarios pueden parecer muy similares inicialmente (visualmente) pero en realidad son muy diferentes. Veamos cómo están relacionados y cómo se complementan para lograr que Python sea una herramienta poderosa para trabajar con archivos JSON.

* JSON es un formato de archivo usado para representar y almacenar información mientras que un diccionario de Python es una estructura de datos (objeto) que se almacena en la memoria del dispositivo mientras se ejecuta el programa de Python.

---

**Cómo JSON y los diccionarios de Python funcionan juntos**
![](@attachment/Clipboard_2023-09-28-22-40-24.png)

Cuando trabajamos con archivos JSON en Python, no podemos simplemente leerlos y usar la información en nuestro programa directamente.

Esto se debe a que el archivo completo estaría representado como una sola cadena de caracteres y no podríamos acceder a los pares clave-valor de forma individual.

A menos que...

Usemos los pares clave-valor del archivo JSON para crear un diccionario de Python que podamos usar en nuestro programa para leer, usar y modificar la información si es necesario.

Esta es la relación principal entre JSON y los diccionarios de Python. JSON es la representación en forma de cadena de caracteres de la información y los diccionarios son las estructuras de datos en memoria que se crean cuando se ejecuta el programa.

Genial. Ahora que ya sabes más sobre JSON, comencemos a ver los aspectos prácticos de cómo puedes trabajar con JSON en Python.

---

**El módulo JSON**

Afortunadamente para nosotros, Python tiene un módulo incorporado llamado json. Se instala automáticamente cuando instalas Python e incluye funciones que te ayudarán a trabajar con archivos y cadenas de caracteres JSON.

**Cómo importar el módulo JSON**

Para usar json en nuestro programa, solo necesitamos escribir una sentencia de importación al inicio del archivo.

De esta forma:
```python
import json
```
Con esta línea podrás tener acceso a las funciones definidas en el módulo. Usaremos varias de ellas en los ejemplos.

> **Dato:** si escribes esta sentencia de importación necesitarás usar la siguiente sintaxis para llamar a la función definida en el módulo json:

![](@attachment/Clipboard_2023-09-28-23-05-23.png)

---

**Python y cadenas de caracteres JSON**

Para mostrarte cómo funcionan algunas de las funciones más importantes del módulo json, usaremos una cadena de caracteres con varias líneas en formato JSON.

**Cadena de caracteres JSON**

Usaremos la siguiente cadena de caracteres en los ejemplos. Es una cadena de caracteres de varias líneas en Python que cumple las reglas del formato JSON.

```
python
datos_JSON =  """
    {
      "tamano": "mediana",
      "precio": 15.67,
      "toppings": ["champinones", "queso extra", "pepperoni", "albahaca"],
      "cliente": {
        "nombre": "Jane Doe",
        "telefono": "455-344-234",
        "correo": "janedoe@email.com"
      }
    }
"""
```

* Para definir una cadena de caracteres de varias líneas en Python, usamos tres comillas dobles.
* Luego, asignamos la cadena de caracteres a la variable datos_JSON.

---

**De una cadena de caracteres JSON a un diccionario de Python**

Usaremos una cadena de caracteres con el formato JSON para crear un diccionario de Python al cual podemos tener acceso para usarlo y modificarlo en nuestro programa.

Para hacerlo, usaremos la función loads() del módulo json, pasando la cadena de caracteres como argumento.

Esta es la sintaxis básica:
![](@attachment/Clipboard_2023-09-28-23-12-14.png)
Este es el código:
```
python
# Importar el módulo
import json
```

# Cadena de caracteres en el formato JSON
```
datos_JSON =  
  {
    "tamano": "mediana",
    "precio": 15.67,
    "toppings": ["champinones", "queso extra", "pepperoni", "albahaca"],
    "cliente": {
      "nombre": "Jane Doe",
      "telefono": "455-344-234",
      "correo": "janedoe@email.com"
    }
  }
```

## Convertir cadena de caracteres JSON a un diccionario
datos_diccionario = json.loads(datos_JSON)

## Acceder a datos del diccionario
```
		print(data_dict["tamano"])
		print(data_dict["precio"])
		print(data_dict["toppings"])
		print(data_dict["cliente"])
```
