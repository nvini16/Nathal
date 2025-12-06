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
            padding: 40px 20px 20px;
        }

        h1 {
            font-size: 3rem;
            margin-bottom: 10px;
            text-shadow: 0 0 15px rgba(255, 255, 255, 0.8);
        }

        p {
            font-size: 1.2rem;
            max-width: 600px;
            margin: 0 auto 20px;
        }

        /* Botão */
        .btn-natal {
            margin-top: 20px;
            padding: 12px 26px;
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

        /* Carrossel */
        .carrossel-container {
            width: 90%;
            max-width: 700px;
            margin: 40px auto;
            position: relative;
            overflow: hidden;
            border-radius: 14px;
            box-shadow: 0 0 20px rgba(0,0,0,0.5);
        }

        .carrossel {
            display: flex;
            transition: transform 0.5s ease-in-out;
        }

        .carrossel img {
            width: 100%;
            flex-shrink: 0;
            height: 380px;
            object-fit: cover;
        }

        .controle {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            font-size: 2rem;
            background: rgba(0,0,0,0.4);
            padding: 10px;
            cursor: pointer;
            user-select: none;
        }

        .esq {
            left: 10px;
        }

        .dir {
            right: 10px;
        }

        /* Neve */
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

        footer {
            margin-top: 50px;
            padding: 20px;
            opacity: 0.8;
            font-size: 0.9rem;
        }
    </style>
</head>
<body>

    <header>
        <h1>✨ Feliz Natal ✨</h1>
        <p>Que a serenidade desta época toque sua vida e renove seu caminho.</p>
        <button class="btn-natal" onclick="mensagemNatal()">Mensagem Especial</button>
    </header>

    <!-- Carrossel -->
    <div class="carrossel-container">
        <div class="carrossel" id="carrossel">
            <img src="https://images.pexels.com/photos/1721161/pexels-photo-1721161.jpeg" alt="Natal 1">
            <img src="https://images.pexels.com/photos/1303086/pexels-photo-1303086.jpeg" alt="Natal 2">
            <img src="https://images.pexels.com/photos/1661905/pexels-photo-1661905.jpeg" alt="Natal 3">
        </div>

        <div class="controle esq" onclick="voltar()">❮</div>
        <div class="controle dir" onclick="avancar()">❯</div>
    </div>

    <div class="neve"></div>

    <footer>
        © 2025 — Site de Natal.
    </footer>

    <script>
        // Carrossel
        let index = 0;

        function atualizarCarrossel() {
            const carrossel = document.getElementById("carrossel");
            const largura = carrossel.clientWidth;
            carrossel.style.transform = `translateX(${-index * largura}px)`;
        }

        function avancar() {
            const total = document.querySelectorAll("#carrossel img").length;
            index = (index + 1) % total;
            atualizarCarrossel();
        }

        function voltar() {
            const total = document.querySelectorAll("#carrossel img").length;
            index = (index - 1 + total) % total;
            atualizarCarrossel();
        }

        setInterval(avancar, 4000);

        // Neve
        function criarFloco() {
            const floco = document.createElement("div");
            floco.innerHTML = "❄";
            floco.style.position = "absolute";
            floco.style.top = "-20px";
            floco.style.left = Math.random() * 100 + "%";
            floco.style.fontSize = (Math.random() * 20 + 10) + "px";
            floco.style.opacity = Math.random();
            floco.style.animation = `cair ${(Math.random() * 6) + 5}s linear`;
            document.querySelector(".neve").appendChild(floco);

            setTimeout(() => floco.remove(), 12000);
        }

        setInterval(criarFloco, 200);

        const animacao = document.createElement("style");
        animacao.innerHTML = `
            @keyframes cair {
                to { transform: translateY(120vh); }
            }
        `;
        document.head.appendChild(animacao);

        // Mensagem
        function mensagemNatal() {
            alert("🎅 Um feliz Natal e boas festas a todos!");
        }
    </script>

</body>
</html>
