---
title: LECCION 13- FIREBASE
created: '2023-12-04T00:30:59.596Z'
modified: '2023-12-05T01:42:38.535Z'
---

# LECCION 13- FIREBASE

## *FIREBASE*

JavaScript es un lenguaje de programación versátil y ampliamente utilizado que se ejecuta en el navegador web del usuario. Desarrollado inicialmente para agregar interactividad a las páginas web, ha evolucionado hasta convertirse en un lenguaje de programación del lado del cliente robusto y esencial en el desarrollo web moderno. 

```
{% extends "layout/layout.html" %}

{% block title %} form-firebase.html {% endblock %}

{% block content %}
    <div class="container text-center">
      <div class="row align-items-center">
        <div class="col">
            <h1>
                Form Firebase
            </h1>
            <code id="code"></code>
            <form id="form">
              <div class="form-group row mt-2">
                <label for="email" class="col-sm-2 col-form-label">Email</label>
                <div class="col-sm-8">
                  <input type="text" class="form-control" id="email">
                </div>
              </div>
              <div class="form-group row mt-2">
                <label for="name" class="col-sm-2 col-form-label">Nombre</label>
                <div class="col-sm-8">
                  <input type="text" class="form-control" id="name">
                </div>
              </div>
              <div class="form-group row mt-2">
                <label for="lastname" class="col-sm-2 col-form-label">Apellidos</label>
                <div class="col-sm-8">
                  <input type="text" class="form-control" id="lastname">
                </div>
              </div>
              <div class="form-group row mt-2">
                <label for="age" class="col-sm-2 col-form-label">Edad</label>
                <div class="col-sm-8">
                  <input type="number" class="form-control" id="age">
                </div>
              </div>
              <button type="submit" class="btn btn-primary mb-2 mt-2">Enviar formulario</button>
            </form>
        </div>
      </div>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script&gt;
    <script type="module">
        // Import the functions you need from the SDKs you need
        import { initializeApp } from "https://www.gstatic.com/firebasejs/10.6.0/firebase-app.js&quot;;
        import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.6.0/firebase-analytics.js&quot;;
        import { getDatabase, child, ref, set, get } from "https://www.gstatic.com/firebasejs/10.6.0/firebase-database.js&quot;;

        // TODO: Add SDKs for Firebase products that you want to use
        // https://firebase.google.com/docs/web/setup#available-libraries

        // Your web app's Firebase configuration
        // For Firebase JS SDK v7.20.0 and later, measurementId is optional
        const firebaseConfig = {
           //Credenciales
        };

        // Initialize Firebase
        const app = initializeApp(firebaseConfig);
        const analytics = getAnalytics(app);
        const database = getDatabase(app);


        const codeAdd = (data) => {
            const code = document.getElementById("code");
            code.innerHTML = data;
        }

        const code = () => {
            const dbRef = ref(getDatabase());
            get(child(dbRef, 'alumno/')).then((snapshot) => {
              if (snapshot.exists()) {
                codeAdd(JSON.stringify(snapshot.val()));
              } else {
                console.log("No hay información disponible");
              }
            }).catch((error) => {
              console.error(error);
            });
        }

        code();

        const form = document.getElementById("form");

        form.addEventListener("submit", (event) => {

            event.preventDefault();

            const date = Date.now();
            const name = document.getElementById("name").value;
            const email = document.getElementById("email").value;
            const lastname = document.getElementById("lastname").value;
            const age = document.getElementById("age").value;

            if( name !== "" && email !== "" && lastname !== "" && age !== "" )
            {
                set(ref(database, 'alumno/' + date), {
                    'name':name,
                    'email':email,
                    'lastname':lastname,
                    'age':age
                });
                Swal.fire({
                  icon: "success",
                  title: "Los datos han sido almacenados.",
                  showConfirmButton: false,
                  timer: 1500
                });
                window.location.reload();
            }else{
                Swal.fire({
                  icon: "error",
                  title: "El formulario no cumple las condiciones",
                  showConfirmButton: false,
                  timer: 1500
                });
            }
        });
    </script>
{% endblock %} 
```

>Este código corresponde a una plantilla HTML con integración de JavaScript y Firebase para la creación de un formulario web.  
