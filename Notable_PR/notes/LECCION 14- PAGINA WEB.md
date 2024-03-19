---
title: LECCION 14- PAGINA WEB
created: '2023-12-05T01:42:40.530Z'
modified: '2023-12-05T01:48:31.018Z'
---

# LECCION 14- PAGINA WEB

## *Pagina web*
```
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    {% load static %}
    <link rel="stylesheet" href="{% static 'site/dist/css/styles.css' %}">
    <title>Index</title>
</head>
<body>

    <form id="prueba">
        <div id="imc-container">
            <h2>Calculadora de Índice de Masa Corporal (IMC)</h2>
            <label for="weight">Peso (kg):</label>
            <input type="text" id="weight" placeholder="Ingrese su peso" required>
            <br>
            <label for="height">Altura (m):</label>
            <input type="text" id="height" placeholder="Ingrese su altura" required>
            <br>
            <button type="button" onclick="calcularIMC()" id="guardar">Calcular</button>
        </div>
    </form>
    <p id="result"></p>
    <script src="{% static 'site/dist/js/script.js'%}"></script>

</body>
</html>


body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

#container {
    display: flex;
    flex-direction: column;
    align-items: center;
}

#imc-container {
    background-color: #fff;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    text-align: center;
    margin-bottom: 20px; /* Espacio entre el formulario y el resultado */
}

#result {
    font-size: 18px;
    margin-top: 10px;
}




const calcularIMC = () => {
    let guardar = document.getElementById('guardar');
    guardar.addEventListener('submit', (event) => {
        event.preventDefault();
    });
    
        let peso = parseFloat(document.getElementById('weight').value);
        let altura = parseFloat(document.getElementById('height').value);

        if (!isNaN(peso) && !isNaN(altura)) {
            let imc = peso / (altura * altura);
            let result = document.getElementById('result');
            result.innerHTML = 'Su IMC es: ' + imc.toFixed(2) + '<br>';

            if (imc < 18.5) {
                result.innerHTML += 'Peso Insuficiente';
            } else if (imc >= 18.5 && imc < 24.9) {
                result.innerHTML += 'Peso Normal';
            } else if (imc >= 25 && imc < 29.9) {
                result.innerHTML += 'Sobrepeso';
            } else if (imc >= 30 && imc < 34.9) {
                result.innerHTML += 'Obesidad Tipo I';
            } else if (imc >= 35 && imc < 39.9) {
                result.innerHTML += 'Obesidad Tipo II';
            } else {
                result.innerHTML += 'Obesidad Tipo III';
            }
        }
};

calcularIMC();
```

>Este código implementa una calculadora de Índice de Masa Corporal (IMC) con HTML, CSS y JavaScript. El formulario permite al usuario ingresar su peso y altura, y al hacer clic en "Calcular", se calcula el IMC. El resultado se presenta en la página, clasificando el estado de peso del usuario en categorías como Peso Normal, Sobrepeso u Obesidad. El diseño utiliza estilos CSS para crear una interfaz limpia y centrada en la pantalla.
