<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Game do Saber</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            background-color: #0b1329;
            color: #ffffff;
            padding: 40px 15px;
            display: flex;
            justify-content: center;
            min-height: 100vh;
        }

        .container {
            max-width: 900px;
            width: 100%;
            background-color: #1e293b;
            border: 1px solid #334155;
            border-radius: 16px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
        }

        header {
            text-align: center;
            margin-bottom: 25px;
            padding-bottom: 15px;
            border-bottom: 1px solid #334155;
        }

        h1 {
            color: #38bdf8;
            font-size: 2.2rem;
        }

        .subtitulo {
            color: #94a3b8;
            font-size: 0.95rem;
            margin-top: 5px;
            font-weight: bold;
        }

        .banner {
            background: linear-gradient(135deg, #0284c7, #2563eb);
            color: #ffffff;
            padding: 16px;
            border-radius: 10px;
            text-align: center;
            font-weight: bold;
            margin-bottom: 30px;
        }

        .titulo-secao {
            color: #38bdf8;
            font-size: 1.3rem;
            margin-bottom: 15px;
        }

        .galeria {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            justify-content: center;
            margin-bottom: 35px;
        }

        .card {
            flex: 1 1 220px;
            max-width: 260px;
            background-color: #0f172a;
            border-radius: 10px;
            overflow: hidden;
            border: 1px solid #334155;
        }

        .card img {
            width: 100%;
            height: 170px;
            object-fit: cover;
            display: block;
        }

        .card p {
            padding: 12px;
            text-align: center;
            font-weight: bold;
            font-size: 0.85rem;
            color: #e2e8f0;
        }

        .videos-container {
            background-color: #0f172a;
            padding: 20px;
            border-radius: 12px;
            border: 1px solid #334155;
            margin-bottom: 35px;
        }

        .video-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            justify-content: center;
        }

        .video-box {
            flex: 1 1 260px;
            max-width: 380px;
            aspect-ratio: 16 / 9;
            border-radius: 8px;
            overflow: hidden;
            background-color: #000;
        }

        .video-box iframe {
            width: 100%;
            height: 100%;
            border: 0;
        }

        .avaliacao {
            background-color: #0f172a;
            padding: 20px;
            border-radius: 12px;
            border: 1px solid #334155;
            text-align: center;
            margin-bottom: 25px;
        }

        .estrelas {
            display: flex;
            justify-content: center;
            gap: 8px;
            font-size: 2rem;
            cursor: pointer;
            margin: 10px 0;
            color: #475569;
        }

        .estrelas span.ativo {
            color: #facc15;
        }

        .mensagem {
            font-size: 0.9rem;
            color: #38bdf8;
            min-height: 20px;
            font-weight: bold;
        }

        footer {
            text-align: center;
            padding-top: 15px;
            border-top: 1px solid #334155;
            color: #64748b;
            font-size: 0.85rem;
        }
    </style>
</head>
<body>

    <div class="container">
        <header>
            <h1>GAME DO SABER</h1>
            <p class="subtitulo">NOSSA ESCOLA, NOSSO COMPROMISSO</p>
        </header>

        <div class="banner">
            O QUE NÓS PODEMOS FAZER PARA TORNAR A NOSSA ESCOLA AINDA MELHOR?
        </div>

        <h2 class="titulo-secao">Galeria do Projeto</h2>
        <div class="galeria">
            <div class="card">
                <img src="193340.jpg" alt="Ventilador">
                <p>Antes e depois: Ventilador</p>
            </div>
            <div class="card">
                <img src="5236443161723305068.jpg" alt="Manutenção">
                <p>Antes e depois: Manutenção</p>
            </div>
            <div class="card">
                <img src="7278812297501217892.jpg" alt="Conservação">
                <p>Antes e depois: Conservação</p>
            </div>
            <div class="card">
                <img src="Gemini_Generated_Image_yl6xrmyl6xrmyl6x.png" alt="Ação 1">
                <p>Antes e depois: Ação 1</p>
            </div>
            <div class="card">
                <img src="Gemini_Generated_Image_7yo3fo7yo3fo7yo3.png" alt="Ação 2">
                <p>Antes e depois: Ação 2</p>
            </div>
        </div>

        <div class="videos-container">
            <h2 class="titulo-secao">Vídeos Recomendados</h2>
            <div class="video-grid">
                <div class="video-box">
                    <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="Vídeo 1" allowfullscreen></iframe>
                </div>
                <div class="video-box">
                    <iframe src="https://www.youtube.com/embed/L_LUpnjgPso" title="Vídeo 2" allowfullscreen></iframe>
                </div>
            </div>
        </div>

        <div class="avaliacao">
            <h2 class="titulo-secao">Avalie o Projeto</h2>
            <div class="estrelas" id="estrelas">
                <span onclick="votar(1)">★</span>
                <span onclick="votar(2)">★</span>
                <span onclick="votar(3)">★</span>
                <span onclick="votar(4)">★</span>
                <span onclick="votar(5)">★</span>
            </div>
            <div class="mensagem" id="msg">Clique nas estrelas para avaliar!</div>
        </div>

        <footer>
            O cuidado com o patrimônio da escola é responsabilidade de todos.<br>
            2026 Game do Saber.
        </footer>
    </div>

    <script>
        function votar(qtd) {
            const itens = document.querySelectorAll('#estrelas span');
            const txt = document.getElementById('msg');
            
            itens.forEach((el, idx) => {
                if (idx < qtd) {
                    el.classList.add('ativo');
                } else {
                    el.classList.remove('ativo');
                }
            });

            const respostas = [
                "Obrigado! Vamos trabalhar para melhorar.",
                "Agradecemos o retorno! Vamos avançar.",
                "Que bom que gostou do projeto!",
                "Muito obrigado pelo apoio!",
                "Excelente! Nota máxima para a nossa escola!"
            ];

            txt.textContent = respostas[qtd - 1];
        }
    </script>

</body>
</html>