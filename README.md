<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Oráculo Maya</title>
  <style>
    body {
      font-family: Arial;
      text-align: center;
      background: #1a1a2e;
      color: #f5f5f5;
      padding: 40px;
    }
    button {
      padding: 15px 25px;
      font-size: 16px;
      border: none;
      border-radius: 8px;
      background: #facc15;
      color: black;
      cursor: pointer;
      margin-top: 20px;
    }
    #progress {
      width: 0%;
      height: 20px;
      background: #facc15;
      margin-top: 20px;
      transition: 0.3s;
    }
    #bar {
      width: 100%;
      background: #333;
      margin-top: 20px;
    }
    .hidden {
      display: none;
    }
  </style>
</head>
<body>

<h1>🔮 Oráculo de Astrología Maya</h1>
<p>Consultando energías ancestrales para <b>Sol</b>...</p>

<button onclick="start()">Consultar destino</button>

<div id="bar">
  <div id="progress"></div>
</div>

<h2 id="status"></h2>

<div id="result" class="hidden">
  <h1>🌞 Resultado del Oráculo</h1>
  <p>Los antiguos mayas han hablado:</p>

  <p><b>“Cuando Sol aparece en tu vida, no es coincidencia… es señal de cita.”</b></p>

  <p>Probabilidad cósmica de que digas que sí: <b>99.7%</b></p>

  <button onclick="aceptar()">Aceptar el destino</button>
</div>

<script>
function start() {
  let progress = document.getElementById("progress");
  let status = document.getElementById("status");
  let width = 0;

  let frases = [
    "Leyendo calendario maya...",
    "Interpretando energías cósmicas...",
    "Consultando a los ancestros...",
    "Descifrando señales del universo...",
    "Confirmando nivel de buena onda de Sol..."
  ];

  let interval = setInterval(() => {
    width += Math.random() * 12;
    progress.style.width = width + "%";

    if (width > 100) {
      clearInterval(interval);
      status.innerText = "Profecía completada";
      document.getElementById("result").classList.remove("hidden");
    } else {
      status.innerText = frases[Math.floor(Math.random() * frases.length)];
    }
  }, 400);
}

function aceptar() {
  alert("Perfecto 😎 Ahora solo falta coordinar esa cita.");
}
</script>

</body>
</html>
