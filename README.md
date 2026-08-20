<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Game do Saber - Preservação Escolar</title>
    <style>
        :root {
            --bg-body: #090d16;
            --bg-card: #131c2e;
            --bg-element: #1b273d;
            --accent-blue: #38bdf8;
            --accent-gradient: linear-gradient(135deg, #0284c7 0%, #2563eb 100%);
            --text-primary: #f8fafc;
            --text-secondary: #94a3b8;
            --border-color: #2a3a56;
            --star-gold: #facc15;
            --radius: 16px;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', -apple-system, BlinkMacSystemFont, Roboto, sans-serif;
        }

        body {
            background-color: var(--bg-body);
            color: var(--text-primary);
            padding: 50px 20px;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            min-height: 100vh;
        }

        .container {
            max-width: 1000px;
            width: 100%;
            background-color: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: var(--radius);
            padding: 40px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.6);
        }

        /* HEADER */
        header {
            text-align: center;
            margin-bottom: 35px;
            padding-bottom: 25px;
            border-bottom: 1px solid var(--border-color);
        }

        .logo-title {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            margin-bottom: 8px;
        }

        .logo-title span {
            font-size: 2.2rem;
        }

        h1 {
            color: var(--accent-blue);
            font-size: 2.4rem;
            font-weight: 800;
            letter-spacing: 1px;
            text-transform: uppercase;
        }

        .subtitulo {
            color: var(--text-secondary);
            font-size: 0.95rem;
            font-weight: 700;
            letter-spacing: 2px;
        }

        /* BANNER DESTACADO */
        .banner {
            background: var(--accent-gradient);
            color: #ffffff;
            padding: 22px 25px;
            border-radius: 12px;
            text-align: center;
            font-weight: 700;
            font-size: 1.1rem;
            margin-bottom: 40px;
            box-shadow: 0 10px 25px rgba(2, 132, 199, 0.3);
            line-height: 1.4;
        }

        /* SEÇÕES */
        .titulo-secao {
            color: var(--accent-blue);
            font-size: 1.4rem;
            font-weight: 700;
            margin-bottom: 22px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        /* GALERIA DE CARDS */
        .galeria {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 20px;
            margin-bottom: 45px;
        }

        .card {
            background-color: var(--bg-element);
            border-radius: 14px;
            overflow: hidden;
            border: 1px solid var(--border-color);
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
        }

        .card:hover {
            transform: translateY(-8px);
            border-color: var(--accent-blue);
            box-shadow: 0 12px 24px rgba(56, 189, 248, 0.15);
        }

        .img-box {
            width: 100%;
            height: 190px;
            background-color: #0b1329;
            overflow: hidden;
            position: relative;
        }

        .card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
            transition: transform 0.4s ease;
        }

        .card:hover img {
            transform: scale(1.05);
        }

        .card p {
            padding: 16px 12px;
            text-align: center;
            font-weight: 600;
            font-size: 0.9rem;
            color: #e2e8f0;
            margin-top: auto;
        }

        /* VÍDEOS */
        .videos-container {
            background-color: var(--bg-element);
            padding: 30px;
            border-radius: 16px;
            border: 1px solid var(--border-color);
            margin-bottom: 45px;
        }

        .video-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }

        .video-box {
            aspect-ratio: 16 / 9;
            border-radius: 12px;
            overflow: hidden;
            background-color: #000;
            box-shadow: 0 4px 12px rgba(0,0,0,0.4);
        }

        .video-box iframe {
            width: 100%;
            height: 100%;
            border: 0;
        }

        /* AVALIAÇÃO */
        .avaliacao {
            background-color: var(--bg-element);
            padding: 30px;
            border-radius: 16px;
            border: 1px solid var(--border-color);
            text-align: center;
            margin-bottom: 35px;
        }

        .estrelas {
            display: flex;
            justify-content: center;
            gap: 12px;
            font-size: 2.4rem;
            cursor: pointer;
            margin: 18px 0;
            color: #475569;
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
            text-shadow: 0 0 10px rgba(250, 204, 21, 0.4);
        }

        .mensagem {
            font-size: 1rem;
            color: var(--accent-blue);
            min-height: 25px;
            font-weight: 600;
        }

        /* RODAPÉ */
        footer {
            text-align: center;
            padding-top: 25px;
            border-top: 1px solid var(--border-color);
            color: var(--text-secondary);
            font-size: 0.85rem;
            line-height: 1.6;
        }

        /* RESPONSIVIDADE */
        @media (max-width: 600px) {
            .container {
                padding: 20px 15px;
            }
            h1 {
                font-size: 1.8rem;
            }
            .banner {
                font-size: 0.95rem;
            }
        }
    </style>
</head>
<body>

    <div class="container">
        <!-- CABEÇALHO -->
        <header>
            <div class="logo-title">
                <span>🎮</span>
                <h1>Game do Saber</h1>
            </div>
            <p class="subtitulo">NOSSA ESCOLA, NOSSO COMPROMISSO</p>
        </header>

        <!-- BANNER PRINCIPAL -->
        <div class="banner">
            O QUE NÓS PODEMOS FAZER PARA TORNAR A NOSSA ESCOLA AINDA MELHOR?
        </div>

        <!-- GALERIA DE FOTOS -->
        <h2 class="titulo-secao">📸 Galeria do Projeto</h2>
        <div class="galeria">
            <div class="card">
                <div class="img-box">
                    <img src="Gemini_Generated_Image_yl6xrmyl6xrmyl6x.png" alt="Antes: Ventilador na sala">
                </div>
                <p>Antes: Sala com Ventilador Antigo</p>
            </div>

            <div class="card">
                <div class="img-box">
                    <img src="Gemini_Generated_Image_7yo3fo7yo3fo7yo3.png" alt="Depois: Ventilador Novo">
                </div>
                <p>Depois: Instalação do Ventilador Novo</p>
            </div>

            <div class="card">
                <div class="img-box">
                    <img src="5236443161723305068.jpg" alt="Manutenção de Carteiras">
                </div>
                <p>Antes e Depois: Manutenção de Carteiras</p>
            </div>

            <div class="card">
                <div class="img-box">
                    <img src="7278812297501217892.jpg" alt="Conservação da Sala">
                </div>
                <p>Antes e Depois: Conservação da Sala</p>
            </div>
        </div>

        <!-- VÍDEOS EDUCATIVOS -->
        <div class="videos-container">
            <h2 class="titulo-secao">🎬 Vídeos e Recomendações</h2>
            <div class="video-grid">
                <div class="video-box">
                    <iframe src="https://www.youtube.com/embed/OzsfOLBmbkU" title="Preservação do Patrimônio Escolar" allowfullscreen></iframe>
                </div>
                <div class="video-box">
                    <iframe src="https://www.youtube.com/embed/HqFGprxZCwA" title="Cuidando da Nossa Escola" allowfullscreen></iframe>
                </div>
            </div>
        </div>

        <!-- SEÇÃO DE AVALIAÇÃO INTERATIVA -->
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

        <!-- RODAPÉ -->
        <footer>
            O cuidado com o patrimônio da escola é responsabilidade de todos os estudantes e comunidade.<br>
            © 2026 Game do Saber. Todos os direitos reservados.
        </footer>
    </div>

    <!-- SCRIPT DE INTERAÇÃO -->
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
                "Obrigado pelo feedback! Vamos trabalhar para melhorar.",
                "Agradecemos a sua opinião! Vamos continuar evoluindo.",
                "Que bom que gostou das melhorias da escola!",
                "Muito obrigado pelo apoio ao nosso projeto!",
                "Incrível! Nota máxima para a conservação da nossa escola! 🎉"
            ];

            txt.textContent = respostas[qtd - 1];
        }
    </script>

</body>
</html>