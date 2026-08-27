<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Game do Saber - Preservação Escolar</title>
    <style>
        :root {
            --bg-main: #070d19;
            --bg-container: #0f172a;
            --bg-card: #1e293b;
            --border-color: #334155;
            --border-highlight: #0284c7;
            --accent-color: #38bdf8;
            --accent-gradient: linear-gradient(135deg, #0284c7 0%, #2563eb 50%, #4f46e5 100%);
            --text-primary: #f8fafc;
            --text-secondary: #94a3b8;
            --star-gold: #facc15;
            --success-color: #4ade80;
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
            padding: 40px 20px;
        }

        .container {
            max-width: 800px;
            width: 100%;
            background-color: var(--bg-container);
            border: 1px solid var(--border-color);
            border-radius: 24px;
            padding: 40px 30px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.6);
        }

        header {
            text-align: center;
            margin-bottom: 35px;
            padding-bottom: 25px;
            border-bottom: 1px solid var(--border-color);
        }

        .header-title {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 14px;
            margin-bottom: 10px;
        }

        .header-title span {
            font-size: 2.5rem;
        }

        h1 {
            color: var(--accent-color);
            font-size: 2.2rem;
            font-weight: 800;
            letter-spacing: 1.5px;
            text-transform: uppercase;
        }

        .subtitulo {
            color: var(--text-secondary);
            font-size: 0.9rem;
            font-weight: 700;
            letter-spacing: 3px;
        }

        .banner {
            background: var(--accent-gradient);
            color: #ffffff;
            padding: 24px;
            border-radius: 16px;
            text-align: center;
            font-weight: 700;
            font-size: 1.1rem;
            margin-bottom: 40px;
            box-shadow: 0 10px 25px rgba(2, 132, 199, 0.35);
            line-height: 1.6;
        }

        .status-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
            margin-bottom: 40px;
        }

        .status-box {
            background-color: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: 14px;
            padding: 16px;
            text-align: center;
        }

        .status-num {
            font-size: 1.6rem;
            font-weight: 800;
            color: var(--accent-color);
        }

        .status-label {
            font-size: 0.8rem;
            color: var(--text-secondary);
            margin-top: 4px;
            text-transform: uppercase;
            font-weight: 600;
        }

        .titulo-secao {
            color: var(--accent-color);
            font-size: 1.4rem;
            font-weight: 700;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .galeria {
            display: flex;
            flex-direction: column;
            gap: 30px;
            margin-bottom: 50px;
        }

        .card {
            background-color: var(--bg-card);
            border-radius: 16px;
            overflow: hidden;
            border: 1px solid var(--border-color);
            transition: transform 0.3s ease, border-color 0.3s ease, box-shadow 0.3s ease;
        }

        .card:hover {
            transform: translateY(-4px);
            border-color: var(--border-highlight);
            box-shadow: 0 12px 30px rgba(56, 189, 248, 0.15);
        }

        .card-header-tag {
            padding: 10px 16px;
            font-size: 0.75rem;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--accent-color);
            background-color: rgba(56, 189, 248, 0.08);
            border-bottom: 1px solid var(--border-color);
        }

        .img-box {
            width: 100%;
            height: 320px;
            background-color: #0b1329;
            position: relative;
            overflow: hidden;
        }

        .card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
            transition: transform 0.4s ease;
        }

        .card:hover img {
            transform: scale(1.03);
        }

        .card-body {
            padding: 18px;
            text-align: center;
        }

        .card-title {
            font-weight: 700;
            font-size: 1.05rem;
            color: var(--text-primary);
        }

        .videos-container {
            background-color: var(--bg-card);
            padding: 30px;
            border-radius: 18px;
            border: 1px solid var(--border-color);
            margin-bottom: 50px;
        }

        .video-grid {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .video-box {
            width: 100%;
            aspect-ratio: 16 / 9;
            border-radius: 12px;
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
            padding: 35px 25px;
            border-radius: 18px;
            border: 1px solid var(--border-color);
            text-align: center;
            margin-bottom: 40px;
        }

        .estrelas {
            display: flex;
            justify-content: center;
            gap: 14px;
            font-size: 2.5rem;
            cursor: pointer;
            margin: 20px 0;
            color: var(--border-color);
            user-select: none;
        }

        .estrelas span {
            transition: transform 0.2s ease, color 0.2s ease;
        }

        .estrelas span:hover,
        .estrelas span.ativo {
            color: var(--star-gold);
            text-shadow: 0 0 15px rgba(250, 204, 21, 0.6);
        }

        .estrelas span:hover {
            transform: scale(1.25);
        }

        .mensagem {
            font-size: 1rem;
            color: var(--accent-color);
            min-height: 28px;
            font-weight: 600;
        }

        footer {
            text-align: center;
            padding-top: 25px;
            border-top: 1px solid var(--border-color);
            color: var(--text-secondary);
            font-size: 0.85rem;
            line-height: 1.7;
        }

        a[href*="github.com"] {
            display: none !important;
        }

        @media (max-width: 600px) {
            .status-grid {
                grid-template-columns: 1fr;
            }
            .img-box {
                height: 230px;
            }
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

        <div class="status-grid">
            <div class="status-box">
                <div class="status-num">5</div>
                <div class="status-label">Fotos Registradas</div>
            </div>
            <div class="status-box">
                <div class="status-num">2</div>
                <div class="status-label">Vídeos Educativos</div>
            </div>
            <div class="status-box">
                <div class="status-num">100%</div>
                <div class="status-label">Engajamento</div>
            </div>
        </div>

        <h2 class="titulo-secao">📸 Galeria do Projeto</h2>
        <div class="galeria">
            <div class="card">
                <div class="card-header-tag">Item #01 • Equipamentos</div>
                <div class="img-box">
                    <img src="Gemini_Generated_Image_7yo3fo7yo3fo7yo3.png" alt="Antes: Ventilador Antigo" onerror="corrigirExtensao(this)">
                </div>
                <div class="card-body">
                    <div class="card-title">Antes: Ventilador Antigo</div>
                </div>
            </div>

            <div class="card">
                <div class="card-header-tag">Item #02 • Substituição</div>
                <div class="img-box">
                    <img src="Gemini_Generated_Image_yl6xrmyl6xrmyl6x.jpg" alt="Depois: Ventilador Novo" onerror="corrigirExtensao(this)">
                </div>
                <div class="card-body">
                    <div class="card-title">Depois: Ventilador Novo</div>
                </div>
            </div>

            <div class="card">
                <div class="card-header-tag">Item #03 • Infraestrutura</div>
                <div class="img-box">
                    <img src="5236443161723305068.jpg" alt="Antes e depois: Manutenção" onerror="corrigirExtensao(this)">
                </div>
                <div class="card-body">
                    <div class="card-title">Antes e depois: Manutenção</div>
                </div>
            </div>

            <div class="card">
                <div class="card-header-tag">Item #04 • Cuidado Contínuo</div>
                <div class="img-box">
                    <img src="7278812297501217892.jpg" alt="Antes e depois: Conservação" onerror="corrigirExtensao(this)">
                </div>
                <div class="card-body">
                    <div class="card-title">Antes e depois: Conservação</div>
                </div>
            </div>

            <div class="card">
                <div class="card-header-tag">Item #05 • Restauração de Ambientes</div>
                <div class="img-box">
                    <img src="3786742617542964504.jpg" alt="Antes e depois: Restauração" onerror="corrigirExtensao(this)">
                </div>
                <div class="card-body">
                    <div class="card-title">Antes e depois: Restauração</div>
                </div>
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

            localStorage.setItem('voto_projeto', qtd);
            txt.textContent = "Obrigado pela avaliação! Redirecionando...";

            setTimeout(() => {
                window.location.href = 'https://www.youtube.com/watch?v=L_jWHffIx5E';
            }, 1200);
        }

        window.addEventListener('DOMContentLoaded', () => {
            const votoSalvo = localStorage.getItem('voto_projeto');
            if (votoSalvo) {
                const itens = document.querySelectorAll('#estrelas span');
                itens.forEach((el, idx) => {
                    if (idx < votoSalvo) el.classList.add('ativo');
                });
                document.getElementById('msg').textContent = `Você já avaliou com ${votoSalvo} estrela(s)!`;
            }
        });
    </script>

</body>
</html>