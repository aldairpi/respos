<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¡Sorpresa de Cumpleaños!</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: linear-gradient(135deg, #ff4081, #ff79b0);
            flex-direction: column;
            color: white;
            text-align: center;
            overflow: hidden;
        }

        #mensaje {
            font-size: 2.5em;
            display: none;
            margin-top: 20px;
            animation: aparecer 1s ease-out;
        }

        #boton {
            padding: 15px 30px;
            font-size: 1.5em;
            background-color: white;
            color: #ff4081;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        #boton:hover {
            background-color: #ff79b0;
        }

        .confetti {
            position: fixed;
            width: 10px;
            height: 10px;
            background-color: #ff4081;
            top: -10px;
            left: 50%;
            animation: confetti-fall 2s linear infinite;
        }

        @keyframes confetti-fall {
            0% {
                transform: translateY(0) rotate(0);
                opacity: 1;
            }
            100% {
                transform: translateY(100vh) rotate(720deg);
                opacity: 0;
            }
        }

        @keyframes aparecer {
            from { opacity: 0; transform: scale(0.9); }
            to { opacity: 1; transform: scale(1); }
        }

        .mensaje-adicional {
            display: none;
            font-size: 1.2em;
            margin-top: 10px;
            animation: aparecer 2s ease-out;
        }
    </style>
</head>
<body>

    <button id="boton" onclick="mostrarSorpresa()">¡Haz clic aquí para tu sorpresa!</button>
    <div id="mensaje">¡Feliz cumpleaños, Chabe! 🎉</div>
    <div class="mensaje-adicional">Que todos tus sueños se hagan realidad hoy y siempre. 💖</div>
    <div class="mensaje-adicional">¡Eres una persona increíble y mereces todo lo mejor! 😊</div>
    <div class="mensaje-adicional">Pásalo bonito, ¡y no te olvides de los 30 que me debes! 😅🥹</div>
    <div class="mensaje-adicional">ESE QUE SEA TU REGALO DE CUMPLE  😅🥹</div>

    <script>
        function mostrarSorpresa() {
            document.getElementById("mensaje").style.display = "block";
            const mensajes = document.getElementsByClassName("mensaje-adicional");
            let delay = 1000; // 1 segundo de delay
            for (let i = 0; i < mensajes.length; i++) {
                setTimeout(() => {
                    mensajes[i].style.display = "block";
                }, delay);
                delay += 2000; // Incremento de 2 segundos entre mensajes
            }
            crearConfetti();
        }

        function crearConfetti() {
            for (let i = 0; i < 100; i++) {
                let confetti = document.createElement("div");
                confetti.className = "confetti";
                confetti.style.left = Math.random() * window.innerWidth + "px";
                confetti.style.backgroundColor = "hsl(" + Math.random() * 360 + ", 100%, 50%)";
                confetti.style.animationDuration = Math.random() * 3 + 2 + "s";
                document.body.appendChild(confetti);
                setTimeout(() => {
                    confetti.remove();
                }, 5000);
            }
        }
    </script>
</body>
</html>
