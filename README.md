<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Feliz Natal 🎄</title>

    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: "Georgia", serif;
            background: linear-gradient(to bottom, #c00, #400);
            color: #fff;
            text-align: center;
            overflow-x: hidden;
        }

        header {
            padding: 50px 20px;
        }

        h1 {
            font-size: 3rem;
            margin-bottom: 10px;
            text-shadow: 0 0 15px rgba(255, 255, 255, 0.8);
        }

        p {
            font-size: 1.3rem;
            max-width: 600px;
            margin: 0 auto;
        }

        .neve {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
            z-index: 9999;
        }

        .btn-natal {
            margin-top: 30px;
            padding: 14px 28px;
            background: #fff;
            color: #900;
            border-radius: 8px;
            border: none;
            font-size: 1.1rem;
            cursor: pointer;
            transition: .3s;
        }

        .btn-natal:hover {
            transform: scale(1.05);
            background: #ffeaea;
        }

        footer {
            margin-top: 60px;
            padding: 20px;
            opacity: 0.8;
            font-size: 0.9rem;
        }
    </style>
</head>
<body>

    <header>
        <h1>☃️ Feliz Natal 🎄</h1>
        <p>Que esta época ilumine sua mente, renove sua energia e traga a serenidade necessária para um novo ciclo.</p>
        <button class="btn-natal" onclick="mensagemNatal()"> Mensagem</button>
    </header>

    <div class="neve"></div>

    <footer>
        © 2025 — Site de Natal desenvolvido para fins comemorativos.
    </footer>

    <script>
        // Função para gerar neve animada
        function criarFloco() {
            const floco = document.createElement("div");
            floco.classList.add("floco");
            floco.innerHTML = "❄";
            floco.style.position = "absolute";
            floco.style.top = "-20px";
            floco.style.left = Math.random() * 100 + "%";
            floco.style.fontSize = (Math.random() * 20 + 10) + "px";
            floco.style.opacity = Math.random();
            floco.style.animation = `cair ${(Math.random() * 5) + 5}s linear`;
            document.querySelector(".neve").appendChild(floco);

            setTimeout(() => floco.remove(), 10000);
        }

        setInterval(criarFloco, 200);

        // Animação da neve
        const style = document.createElement('style');
        style.innerHTML = `
            @keyframes cair {
                to {
                    transform: translateY(120vh);
                }
            }
        `;
        document.head.appendChild(style);

        // Mensagem natalina
        function mensagemNatal() {
            alert("🎅 Um feliz natal pra todos!");
        }
    </script>

</body>
</html>
