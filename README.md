<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Game do Saber - Preservação Escolar</title>
    <style>
        :root {
            --bg-body: #0b1329;
            --bg-card: #1e293b;
            --bg-element: #0f172a;
            --accent: #38bdf8;
            --accent-gradient: linear-gradient(135deg, #0284c7 0%, #2563eb 100%);
            --text-main: #f8fafc;
            --text-muted: #94a3b8;
            --border: #334155;
            --star-gold: #facc15;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
        }

        body {
            background-color: var(--bg-body);
            color: var(--text-main);
            padding: 50px 20px;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            min-height: 100vh;
        }

        .container {
            max-width: 980px;
            width: 100%;
            background-color: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 20px;
            padding: 40px 30px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5);
        }

        header {
            text-align: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 1px solid var(--border);
        }

        h1 {
            color: var(--accent);
            font-size: 2.3rem;
            font-weight: 800;
            letter-spacing: 1px;
            margin-bottom: 8px;
        }

        .subtitulo {
            color: var(--text-muted);
            font-size: 0.95rem;
            font-weight: 700;
            letter-spacing: 1.5px;
        }

        .banner {
            background: var(--accent-gradient);
            color: #ffffff;
            padding: 20px;
            border-radius: 12px;
            text-align: center;
            font-weight: 700;
            font-size: 1.05rem;
            margin-bottom: 40px;
            box-shadow: 0 8px 20px rgba(2, 132, 199, 0.25);
        }

        .titulo-secao {
            color: var(--accent);
            font-size: 1.35rem;
            font-weight: 700;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .galeria {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
            margin-bottom: 45px;
        }

        .card {
            flex: 1 1 240px;
            max-width: 280px;
            background-color: var(--bg-element);
            border-radius: 14px;
            overflow: hidden;
            border: 1px solid var(--border);
            transition: transform 0.2s ease, border-color 0.2s ease;
        }

        .card:hover {
            transform: translateY(-6px);
            border-color: var(--accent);
        }

        .img-box {
            width: 100%;
            height: 180px;
            background-color: var(--border);
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        .card p {
            padding: 14px 10px;
            text-align: center;
            font-weight: 600;
            font-size: 0.9rem;
            color: #e2e8f0;
        }

        .videos-container {
            background-color: var(--bg-element);
            padding: 30px;
            border-radius: 16px;
            border: 1px solid var(--border);
            margin-bottom: 45px;
        }

        .video-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
        }

        .video-box {
            flex: 1 1 300px;
            max-width: 420px;
            aspect-ratio: 16 / 9;
            border-radius: 10px;
            overflow: hidden;
            background-color: #000;
        }

        .video-box iframe {
            width: 100%;
            height: 100%;
            border: 0;
        }

        .avaliacao {
            background-color: var(--bg-element);
            padding: 30px;
            border-radius: 16px;
            border: 1px solid var(--border);
            text-align: center;
            margin-bottom: 30px;
        }

        .estrelas {
            display: flex;
            justify-content: center;
            gap: 12px;
            font-size: 2.2rem;
            cursor: pointer;
            margin: 15px 0;
            color: var(--border);
            user-select: none;
        }

        .estrelas span {
            transition: color 0.15s ease, transform 0.15s ease;
        }

        .estrelas span:hover {
            transform: scale(1.2);
        }

        .estrelas span.ativo {
            color: var(--star-gold);
        }

        .mensagem {
            font-size: 0.95rem;
            color: var(--accent);
            min-height: 24px;
            font-weight: 600;
        }

        footer {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid var(--border);
            color: var(--text-muted);
            font-size: 0.85rem;
            line-height: 1.6;
        }
    </style>
</head>
<body>

    <div class="container">
        <header>
            <h1>🎮 GAME DO SABER</h1>
            <p class="subtitulo">NOSSA ESCOLA, NOSSO COMPROMISSO</p>
        </header>

        <div class="banner">
            O QUE NÓS PODEMOS FAZER PARA TORNAR A NOSSA ESCOLA AINDA MELHOR?
        </div>

        <h2 class="titulo-secao">📸 Galeria do Projeto</h2>
        <div class="galeria">
            <div class="card">
                <div class="img-box">
                    <img src="193340.jpg" alt="Ventilador" onerror="this.onerror=null; this.src='https://via.placeholder.com/300x200?text=Imagem+Ventilador';">
                </div>
                <p>Antes e depois: Ventilador</p>
            </div>
            <div class="card">
                <div class="img-box">
                    <img src="5236443161723305068.jpg" alt="Manutenção">
                </div>
                <p>Antes e depois: Manutenção</p>
            </div>
            <div class="card">
                <div class="img-box">
                    <img src="7278812297501217892.jpg" alt="Conservação">
                </div>
                <p>Antes e depois: Conservação</p>
            </div>
            <div class="card">
                <div class="img-box">
                    <img src="Gemini_Generated_Image_yl6xrmyl6xrmyl6x.png" alt="Ação 1">
                </div>
                <p>Antes e depois: Ação 1</p>
            </div>
            <div class="card">
                <div class="img-box">
                    <img src="Gemini_Generated_Image_7yo3fo7yo3fo7yo3.png" alt="Ação 2">
                </div>
                <p>Antes e depois: Ação 2</p>
            </div>
        </div>

        <div class="videos-container">
            <h2 class="titulo-secao">🎬 Vídeos Sobre Preservação Escolar</h2>
            <div class="video-grid">
                <div class="video-box">
                    <iframe src="https://www.youtube.com/embed/OzsfOLBmbkU" title="Patrimônio Escolar" allowfullscreen></iframe>
                </div>
                <div class="video-box">
                    <iframe src="https://www.youtube.com/embed/HqFGprxZCwA" title="Conservação das Instalações da Escola" allowfullscreen></iframe>
                </div>
            </div>
        </div>

        <div class="avaliacao">
            <h2 class="titulo-secao" style="justify-content: center;">⭐ Avalie o Nosso Projeto</h2>
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
            O cuidado com o patrimônio da escola é responsabilidade de todos os estudantes e comunidade.<br>
            © 2026 Game do Saber.
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