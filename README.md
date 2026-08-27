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
            --tag-antes: #ef4444;
            --tag-depois: #22c55e;
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
            padding: 30px 15px;
        }

        .container {
            max-width: 850px;
            width: 100%;
            background-color: var(--bg-container);
            border: 1px solid var(--border-color);
            border-radius: 20px;
            padding: 30px 20px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.6);
        }

        header {
            text-align: center;
            margin-bottom: 25px;
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
            font-size: 2rem;
        }

        h1 {
            color: var(--accent-color);
            font-size: 1.8rem;
            font-weight: 800;
            letter-spacing: 1px;
            text-transform: uppercase;
        }

        .subtitulo {
            color: var(--text-secondary);
            font-size: 0.85rem;
            font-weight: 700;
            letter-spacing: 2px;
        }

        .banner {
            background: var(--accent-gradient);
            color: #ffffff;
            padding: 18px;
            border-radius: 14px;
            text-align: center;
            font-weight: 700;
            font-size: 0.95rem;
            margin-bottom: 30px;
            box-shadow: 0 8px 20px rgba(2, 132, 199, 0.3);
            line-height: 1.5;
        }

        .titulo-secao {
            color: var(--accent-color);
            font-size: 1.25rem;
            font-weight: 700;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        /* Galeria em 2 colunas para alinhar Antes / Depois */
        .galeria {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            margin-bottom: 40px;
        }

        .card {
            background-color: var(--bg-card);
            border-radius: 14px;
            overflow: hidden;
            border: 1px solid var(--border-color);
            transition: transform 0.25s ease, border-color 0.25s ease;
            display: flex;
            flex-direction: column;
        }

        .card:hover {
            transform: translateY(-4px);
            border-color: var(--border-highlight);
        }

        .card-header-tag {
            padding: 8px 12px;
            font-size: 0.75rem;
            font-weight: 800;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            border-bottom: 1px solid var(--border-color);
        }

        .tag-antes {
            color: var(--tag-antes);
            background-color: rgba(239, 68, 68, 0.1);
        }

        .tag-depois {
            color: var(--tag-depois);
            background-color: rgba(34, 197, 94, 0.1);
        }

        .tag-geral {
            color: var(--accent-color);
            background-color: rgba(56, 189, 248, 0.1);
        }

        .img-box {
            width: 100%;
            height: 200px;
            background-color: #0b1329;
            position: relative;
            overflow: hidden;
        }

        .card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        .card-body {
            padding: 12px;
            text-align: center;
            background-color: var(--bg-card);
            margin-top: auto;
        }

        .card-title {
            font-weight: 600;
            font-size: 0.9rem;
            color: var(--text-primary);
        }

        .videos-container {
            background-color: var(--bg-card);
            padding: 20px;
            border-radius: 16px;
            border: 1px solid var(--border-color);
            margin-bottom: 40px;
        }

        .video-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
        }

        .video-box {
            width: 100%;
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
            padding: 25px;
            border-radius: 16px;
            border: 1px solid var(--border-color);
            text-align: center;
            margin-bottom: 30px;
        }

        .estrelas {
            display: flex;
            justify-content: center;
            gap: 10px;
            font-size: 2.2rem;
            cursor: pointer;
            margin: 15px 0;
            color: var(--border-color);
            user-select: none;
        }

        .estrelas span.ativo {
            color: var(--star-gold);
            text-shadow: 0 0 12px rgba(250, 204, 21, 0.5);
        }

        .mensagem {
            font-size: 0.9rem;
            color: var(--accent-color);
            min-height: 24px;
            font-weight: 600;
        }

        footer {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid var(--border-color);
            color: var(--text-secondary);
            font-size: 0.8rem;
            line-height: 1.6;
        }

        a[href*="github.com"] {
            display: none !important;
        }

        @media (max-width: 650px) {
            .galeria, .video-grid {
                grid-template-columns: 1fr;
            }
            .card-full {
                grid-column: span 1 !important;
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

        <h2 class="titulo-secao">📸 Galeria do Projeto</h2>
        <div class="galeria">
            <!-- Par 1: Ventiladores -->
            <div class="card">
                <div class="card-header-tag tag-antes">🔴 ANTES</div>
                <div class="img-box">
                    <img src="Gemini_Generated_Image_7yo3fo7yo3fo7yo3.png" alt="Antes: Ventilador Antigo" onerror="corrigirExtensao(this)">
                </div>
                <div class="card-body">
                    <div class="card-title">Ventilador Antigo</div>
                </div>
            </div>

            <div class="card">
                <div class="card-header-tag tag-depois">🟢 DEPOIS</div>
                <div class="img-box">
                    <img src="Gemini_Generated_Image_yl6xrmyl6xrmyl6x.jpg" alt="Depois: Ventilador Novo" onerror="corrigirExtensao(this)">
                </div>
                <div class="card-body">
                    <div class="card-title">Ventilador Novo</div>
                </div>
            </div>

            <!-- Par 2: Sala de Aula -->
            <div class="card">
                <div class="card-header-tag tag-antes">🔴 ANTES</div>
                <div class="img-box">
                    <img src="5236443161723305068.jpg" alt="Antes: Sala Desorganizada" onerror="corrigirExtensao(this)">
                </div>
                <div class="card-body">
                    <div class="card-title">Sala Desorganizada</div>
                </div>
            </div>

            <div class="card">
                <div class="card-header-tag tag-depois">🟢 DEPOIS</div>
                <div class="img-box">
                    <img src="7278812297501217892.jpg" alt="Depois: Sala Organizada" onerror="corrigirExtensao(this)">
                </div>
                <div class="card-body">
                    <div class="card-title">Sala Conservada</div>
                </div>
            </div>

            <!-- Foto de Destaque / Restauração -->
            <div class="card card-full" style="grid-column: span 2;">
                <div class="card-header-tag tag-geral">⭐ RESULTADO FINAL</div>
                <div class="img-box" style="height: 240px;">
                    <img src="3786742617542964504.jpg" alt="Restauração Concluída" onerror="corrigirExtensao(this)">
                </div>
                <div class="card-body">
                    <div class="card-title">Restauração e Conservação do Ambiente</div>
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