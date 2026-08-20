!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Game do Saber - Preservação Escolar</title>
    <style>
        :root {
            --bg-main: #0b1329;
            --bg-container: #1e293b;
            --bg-card: #0f172a;
            --border-color: #334155;
            --accent-color: #38bdf8;
            --accent-gradient: linear-gradient(135deg, #0284c7 0%, #2563eb 100%);
            --text-primary: #f8fafc;
            --text-secondary: #94a3b8;
            --star-gold: #facc15;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
        }

        body {
            background-color: var(--bg-main);
            color: var(--text-primary);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            padding: 50px 20px;
        }

        .container {
            max-width: 960px;
            width: 100%;
            background-color: var(--bg-container);
            border: 1px solid var(--border-color);
            border-radius: 20px;
            padding: 40px 30px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5);
        }

        header {
            text-align: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 1px solid var(--border-color);
        }

        .header-title {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            margin-bottom: 8px;
        }

        .header-title span {
            font-size: 2.2rem;
        }

        h1 {
            color: var(--accent-color);
            font-size: 2.2rem;
            font-weight: 800;
            letter-spacing: 1px;
            text-transform: uppercase;
        }

        .subtitulo {
            color: var(--text-secondary);
            font-size: 0.9rem;
            font-weight: 700;
            letter-spacing: 2px;
        }

        .banner {
            background: var(--accent-gradient);
            color: #ffffff;
            padding: 20px 24px;
            border-radius: 12px;
            text-align: center;
            font-weight: 700;
            font-size: 1.05rem;
            margin-bottom: 40px;
            box-shadow: 0 8px 20px rgba(2, 132, 199, 0.3);
            line-height: 1.5;
        }

        .titulo-secao {
            color: var(--accent-color);
            font-size: 1.35rem;
            font-weight: 700;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .galeria {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            margin-bottom: 40px;
        }

        @media (max-width: 640px) {
            .galeria {
                grid-template-columns: 1fr;
            }
        }

        .card {
            background-color: var(--bg-card);
            border-radius: 14px;
            overflow: hidden;
            border: 1px solid var(--border-color);
            transition: transform 0.25s ease, border-color 0.25s ease, box-shadow 0.25s ease;
            display: flex;
            flex-direction: column;
        }

        .card:hover {
            transform: translateY(-6px);
            border-color: var(--accent-color);
            box-shadow: 0 10px 25px rgba(56, 189, 248, 0.15);
        }

        .img-box {
            width: 100%;
            height: 200px;
            background-color: #1b273d;
            position: relative;
            overflow: hidden;
        }

        .card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
            transition: transform 0.3s ease;
        }

        .card:hover img {
            transform: scale(1.04);
        }

        .card p {
            padding: 16px 12px;
            text-align: center;
            font-weight: 600;
            font-size: 0.95rem;
            color: #e2e8f0;
            background-color: var(--bg-card);
        }

        .videos-container {
            background-color: var(--bg-card);
            padding: 30px;
            border-radius: 16px;
            border: 1px solid var(--border-color);
            margin-bottom: 40px;
        }

        .video-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
        }

        .video-box {
            aspect-ratio: 16 / 9;
            border-radius: 10px;
            overflow: hidden;
            background-color: #000;
            border: 1px solid var(--border-color);
        }

        .video-box iframe {
            width: 100%;
            height: 100%;
            border: 0;
        }

        .avaliacao {
            background-color: var(--bg-card);
            padding: 30px;
            border-radius: 16px;
            border: 1px solid var(--border-color);
            text-align: center;
            margin-bottom: 30px;
        }

        .estrelas {
            display: flex;
            justify-content: center;
            gap: 12px;
            font-size: 2.3rem;
            cursor: pointer;
            margin: 15px 0;
            color: var(--border-color);
            user-select: none;
        }

        .estrelas span {
            transition: transform 0.2s ease, color 0.2s ease;
        }

        .estrelas span:hover {
            transform: scale(1.25);
        }

        .estrelas span.ativo {
            color: var(--star-gold);
            text-shadow: 0 0 12px rgba(250, 204, 21, 0.5);
        }

        .mensagem {
            font-size: 0.95rem;
            color: var(--accent-color);
            min-height: 24px;
            font-weight: 600;
        }

        footer {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid var(--border-color);
            color: var(--text-secondary);
            font-size: 0.85rem;
            line-height: 1.6;
        }

        /* Oculta textos e links automáticos do GitHub Pages no final da página */
        a[href*="github.com"], 
        .site-footer, 
        body > div:not(.container), 
        body > footer:not(.container) {
            display: none !important;
        }
    </style>
</head>
<body>

    <div class="container">
        <header>
            <div class="header-title">
                <span>🎮</span>
                <h1>GAME DO SABER</h1>
            </div>
            <p class="subtitulo">NOSSA ESCOLA, NOSSO COMPROMISSO</p>
        </header>

        <div class="banner">
            O QUE NÓS PODEMOS FAZER PARA TORNAR A NOSSA ESCOLA AINDA MELHOR?
        </div>

        <h2 class="titulo-secao">📸 Galeria do Projeto</h2>
        <div class="galeria">
            <div class="card">
                <div class="img-box">
                    <img src="Gemini_Generated_Image_7yo3fo7yo3fo7yo3.png" alt="Antes: Ventilador Antigo" onerror="corrigirExtensao(this)">
                </div>
                <p>Antes: Ventilador Antigo</p>
            </div>

            <div class="card">
                <div class="img-box">
                    <img src="Gemini_Generated_Image_yl6xrmyl6xrmyl6x.jpg" alt="Depois: Ventilador Novo" onerror="corrigirExtensao(this)">
                </div>
                <p>Depois: Ventilador Novo</p>
            </div>

            <div class="card">
                <div class="img-box">
                    <img src="5236443161723305068.jpg" alt="Antes e depois: Manutenção" onerror="corrigirExtensao(this)">
                </div>
                <p>Antes e depois: Manutenção</p>
            </div>

            <div class="card">
                <div class="img-box">
                    <img src="7278812297501217892.jpg" alt="Antes e depois: Conservação" onerror="corrigirExtensao(this)">
                </div>
                <p>Antes e depois: Conservação</p>
            </div>
        </div>

        <div class="videos-container">
            <h2 class="titulo-secao">🎬 Vídeos e Recomendações</h2>
            <div class="video-grid">
                <div class="video-box">
                    <iframe src="https://www.youtube-nocookie.com/embed/OzsfOLBmbkU" title="Cuidado com o Patrimônio Escolar" allowfullscreen></iframe>
                </div>
                <div class="video-box">
                    <iframe src="https://www.youtube-nocookie.com/embed/HqFGprxZCwA" title="Conservação da Escola" allowfullscreen></iframe>
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
        function corrigirExtensao(img) {
            img.onerror = null; 
            if (img.src.endsWith('.jpg')) {
                img.src = img.src.replace('.jpg', '.png');
            } else if (img.src.endsWith('.png')) {
                img.src = img.src.replace('.png', '.jpg');
            }
        }

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

            txt.textContent = "Obrigado pela avaliação! Redirecionando para a música...";

            // Redireciona na própria aba após 1 segundo (não é bloqueado pelos navegadores)
            setTimeout(() => {
                window.location.href = 'https://www.youtube.com/watch?v=L_jWHffIx5E';
            }, 1000);
        }
    </script>

</body>
</html>