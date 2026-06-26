proyect/ Calculadora Web
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora Web</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<div class="calculadora">
    <h2>Calculadora</h2>

    <input type="text" id="pantalla" readonly>

    <div class="botones">
        <button onclick="limpiar()" class="rojo">C</button>
        <button onclick="borrar()">⌫</button>
        <button onclick="agregar('%')">%</button>
        <button onclick="agregar('/')">÷</button>

        <button onclick="agregar('7')">7</button>
        <button onclick="agregar('8')">8</button>
        <button onclick="agregar('9')">9</button>
        <button onclick="agregar('*')">×</button>

        <button onclick="agregar('4')">4</button>
        <button onclick="agregar('5')">5</button>
        <button onclick="agregar('6')">6</button>
        <button onclick="agregar('-')">-</button>

        <button onclick="agregar('1')">1</button>
        <button onclick="agregar('2')">2</button>
        <button onclick="agregar('3')">3</button>
        <button onclick="agregar('+')">+</button>

        <button onclick="agregar('0')" class="doble">0</button>
        <button onclick="agregar('.')">.</button>
        <button onclick="calcular()" class="verde">=</button>
    </div>
</div>
css/
body{
    margin:0;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
    background:linear-gradient(135deg,#4facfe,#00f2fe);
    font-family:Arial, sans-serif;
}

.calculadora{
    background:#222;
    padding:20px;
    border-radius:15px;
    box-shadow:0 0 20px rgba(0,0,0,.4);
    width:320px;
}

h2{
    color:white;
    text-align:center;
}

#pantalla{
    width:100%;
    height:60px;
    font-size:28px;
    text-align:right;
    margin-bottom:15px;
    border:none;
    border-radius:10px;
    padding-right:10px;
    box-sizing:border-box;
}

.botones{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:10px;
}

button{
    height:60px;
    font-size:22px;
    border:none;
    border-radius:10px;
    cursor:pointer;
    background:#444;
    color:white;
    transition:.2s;
}

button:hover{
    background:#666;
}

.rojo{
    background:#e74c3c;
}

.verde{
    background:#27ae60;
}

.doble{
    grid-column:span 2;
}
js/
let pantalla = document.getElementById("pantalla");

function agregar(valor){
    pantalla.value += valor;
}

function limpiar(){
    pantalla.value = "";
}

function borrar(){
    pantalla.value = pantalla.value.slice(0,-1);
}

function calcular(){
    try{
        pantalla.value = eval(pantalla.value);
    }catch{
        pantalla.value = "Error";
    }
}
<script src="script.js"></script>
</body>
</html>
