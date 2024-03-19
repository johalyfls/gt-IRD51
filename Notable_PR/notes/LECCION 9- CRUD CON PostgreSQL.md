---
attachments: [Clipboard_2023-12-04-19-45-42.png, Clipboard_2023-12-04-19-46-16.png, Clipboard_2023-12-04-19-46-28.png, Clipboard_2023-12-04-19-46-40.png, Clipboard_2023-12-04-19-47-01.png]
title: LECCION 9- CRUD CON PostgreSQL
created: '2023-12-04T00:28:39.235Z'
modified: '2023-12-05T01:57:48.847Z'
---

# LECCION 9- CRUD CON PostgreSQL

## *Crud Prueba de Modelo (migraciones, PosgreSQL)*

### Se realiza la siguente configuración el archivo mysite\mysite\settings.py
**1.- Se comentará la configuración por defecto de Django con Sqlite3**

```
python
"""
DATABASES = {
'default': {
'EGINE' : 'django.db.backends.sqllite3',
'NAME' : BASE_DIR / 'db.sqlite3',
}
}
"""
```

**2.- Crear base de datos "sap_db", apoyarse en el vídeo para crear base de datos**

**3.- Se añadirá la nueva configuración, para el uso de PostgreSQL**
![](@attachment/Clipboard_2023-12-04-09-29-46.png)

## Instalacion psycopg2
![](@attachment/Clipboard_2023-12-04-09-30-27.png)

Revisar tablas creadas en la base de datos en PGAdmin

### Crear nueva aplicación encargada de gestionar personas (Sistema de Administración de
Personas) 
![](@attachment/Clipboard_2023-12-04-09-28-14.png)

## *Crud en Django*

## Crud de persona y domicilio
```
def index_crud(request):
no_register = PersonaModel.objects.count()
registers = PersonaModel.objects.all()
return render(request, 'persona-crud/index.html', {'no_register':no_register, 'registers': registers})

def index_domicilio_crud(request):
no_register = DomicilioModel.objects.count()
registers = DomicilioModel.objects.all()
return render(request, 'domicilio-crud/index.html', {'no_register':no_register, 'registers': registers})

def create_crud(request):
registers_domicilios = DomicilioModel.objects.all()
return render(request, 'persona-crud/create.html', {'registers_domicilios':registers_domicilios})

def create_domicilio_crud(request):
registers_domicilios = DomicilioModel.objects.all()
return render(request, 'domicilio-crud/create.html', {'registers_domicilios':registers_domicilios})

def crud_store(request):
if request.method == "POST":
register_domicilio = DomicilioModel.objects.get(pk=request.POST["domicilio"])
new_persona = PersonaModel(nombre=request.POST["nombre"], email=request.POST["email"], apellido=request.POST["apellido"], domicilio=request.POST[register_domicilio])
new_persona.save()
return redirect('crud-index')

def crud_domicilio_store(request):
if request.method == "POST":
register_domicilio = DomicilioModel.objects.get(pk=request.POST["domicilio"])
new_domicilio = DomicilioModel(calle=request.POST["calle"], no_calle=request.POST["no_calle"], pais=request.POST["pais"])
new_domicilio.save()
return redirect('crud-index-domicilio')

def crud_edit(request, id):
registers_domicilios = DomicilioModel.objects.all()
register_persona = PersonaModel.objects.get(pk=id)
return render(request, 'persona-crud/edit.html', {'registers_domicilios':registers_domicilios, 'register_persona':register_persona})

def crud_domicilio_edit(request, id):
registers_domicilios = DomicilioModel.objects.all()
register_domicilio = DomicilioModel.objects.get(pk=id)
return render(request, 'domicilio-crud/edit.html', {'registers_domicilios':registers_domicilios, 'register_domicilio':register_domicilio})

def crud_show(request, id):
registers_domicilios = DomicilioModel.objects.all()
register_persona = PersonaModel.objects.get(pk=id)
return render(request, 'persona-crud/show.html', {'registers_domicilios':registers_domicilios, 'register_persona':register_persona})

def crud_domicilio_show(request, id):
registers_domicilios = DomicilioModel.objects.all()
registers_domicilio = DomicilioModel.objects.get(pk=id)
return render(request, 'domicilio-crud/show.html', {'registers_domicilios':registers_domicilios, 'register_domicilio':registers_domicilio})

def crud_update(request, id):
if request.method == "POST":
register_domicilio = DomicilioModel.objects.get(pk=request.POST["domicilio"])
register_persona = PersonaModel.objects.get(pk=id)
register_persona.nombre = request.POST["nombre"]
register_persona.apellido = request.POST["apellido"]
register_persona.email = request.POST["email"]
register_persona.domicilio = register_domicilio
register_persona.save()
return redirect('crud-index')

def crud_domicilio_update(request, id):
if request.method == "POST":
register_domicilio = DomicilioModel.objects.get(pk=id)
register_domicilio.calle = request.POST["calle"]
register_domicilio.no_calle = request.POST["no_calle"]
register_domicilio.pais = request.POST["pais"]
register_domicilio.save()
return redirect('crud-index-domicilio')

def crud_delete(request, id):
register_persona = PersonaModel.objects.get(pk=id)
register_persona.delete()
return redirect('crud-index')

def crud_domicilio_delete(request, id):
register_domicilio = DomicilioModel.objects.get(pk=id)
register_domicilio.delete()
return redirect('crud-index-domicilio')

En nuestra aplicacion de personas, configuramos los models, en este caso el de domicilio
class Domicilio(models.Model):
calle = models.CharField(max_length=255)
no_calle = models.IntegerField()
pais = models.CharField(max_length=255)
objects = models.Manager()
content_copy

def __str__(self):
    return f"Domicilio: {self.calle} {self.no_calle} {self.pais}"
```
Despues creamos dentro de TEMPLATES, nuestras platillas con las cuales iremos a trabajar
![](@attachment/Clipboard_2023-12-04-19-47-01.png)

En este caso se trabajaron con domiclio-crud
En el cual tenemos nuestro INDEX, EDIT Y SHOW en punto HTML
![](@attachment/Clipboard_2023-12-04-19-46-16.png)
![](@attachment/Clipboard_2023-12-04-19-46-28.png)
![](@attachment/Clipboard_2023-12-04-19-46-40.png)

Para finalizar declaramos nuestras URL
![](@attachment/Clipboard_2023-12-04-19-45-42.png)
