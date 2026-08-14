<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Game do Saber</title>
    <style>
        /* Reset Básico */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #0f172a;
            color: #f8fafc;
            padding: 20px;
            display: flex;
            justify-content: center;
        }

        /* Container Principal */
        .wrapper {
            max-width: 950px;
            width: 100%;
            background-color: #1e293b;
            border-radius: 16px;
            padding: 35px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
        }

        /* Cabeçalho */
        header {
            text-align: center;
            margin-bottom: 30px;
            border-bottom: 2px solid #334155;
            padding-bottom: 20px;
        }

        h1 {
            color: #38bdf8;
            font-size: 2.4rem;
            letter-spacing: 1px;
        }

        .subtitulo {
            color: #94a3b8;
            font-size: 1.1rem;
            margin-top: 5px;
            font-weight: 600;
        }

        /* Seção de Pergunta */
        .pergunta-box {
            background: linear-gradient(135deg, #0284c7, #2563eb);
            padding: 18px;
            border-radius: 10px;
            text-align: center;
            font-weight: bold;
            font-size: 1.1rem;
            margin-bottom: 35px;
            box-shadow: 0 4px 12px rgba(37, 99, 235, 0.3);
        }

        /* Títulos das Seções */
        .secao-titulo {
            color: #38bdf8;
            font-size: 1.4rem;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        /* Galeria de Fotos da Escola */
        .galeria {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
            margin-bottom: 40px;
        }

        .card-foto {
            flex: 1 1 260px;
            max-width: 280px;
            background-color: #334155;
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid #475569;
            transition: transform 0.2s ease;
        }

        .card-foto:hover {
            transform: translateY(-5px);
        }

        .card-foto img {
            width: 100%;
            height: 180px;
            object-fit: cover;
            display: block;
        }

        .card-foto p {
            padding: 12px;
            text-align: center;
            font-weight: 600;
            font-size: 0.95rem;
            color: #f1f5f9;
        }

        /* Seção de Vídeos do YouTube (Propagandas/Recomendações) */
        .youtube-section {
            background-color: #0f172a;
            padding: 25px;
            border-radius: 12px;
            border: 1px solid #334155;
            margin-bottom: 40px;
        }

        .video-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
        }

        .video-card {
            flex: 1 1 280px;
            max-width: 400px;
            aspect-ratio: 16 / 9;
            border-radius: 8px;
            overflow: hidden;
            background-color: #000;
        }

        .video-card iframe {
            width: 100%;
            height: 100%;
            border: none;
        }

        /* Sistema de Avaliação (Estrelas) */
        .avaliacao-section {
            background-color: #334155;
            padding: 25px;
            border-radius: 12px;
            text-align: center;
            margin-bottom: 30px;
        }

        .estrelas {
            display: flex;
            justify-content: center;
            gap: 10px;
            font-size: 2rem;
            cursor: pointer;
            margin: 15px 0;
            color: #64748b;
        }

        .estrelas span {
            transition: color 0.2s;
        }

        .estrelas span:hover,
        .estrelas span.ativo {
            color: #facc15;
        }

        .mensagem-avaliacao {
            font-size: 0.95rem;
            color: #cbd5e1;
            min-height: 24px;
        }

        /* Rodapé */
        footer {
            text-align: center;
            padding-top: 15px;
            border-top: 1px solid #334155;
            color: #94a3b8;
            font-size: 0.9rem;
        }
    </style>
</head>
<body>

    <div class="wrapper">
        <header>
            <h1>🎮 GAME DO SABER</h1>
            <p class="subtitulo">NOSSA ESCOLA, NOSSO COMPROMISSO</p>
        </header>

        <div class="pergunta-box">
            O QUE NÓS PODEMOS FAZER PARA TORNAR A NOSSA ESCOLA AINDA MELHOR?
        </div>

        <h2 class="secao-titulo">📸 Galeria do Projeto</h2>
        <div class="galeria">
            <div class="card-foto">
                <img src="days.jpeg" alt="Ventilador">
                <p>Antes e depois: Ventilador</p>
            </div>
            <div class="card-foto">
                <img src="5236443161723305068.jpg" alt="Manutenção">
                <p>Antes e depois: Manutenção</p>
            </div>
            <div class="card-foto">
                <img src="7278812297501217892.jpg" alt="Conservação">
                <p>Antes e depois: Conservação</p>
            </div>
        </div>

        <div class="youtube-section">
            <h2 class="secao-titulo">🎬 Vídeos e Recomendações</h2>
            <div class="video-grid">
                <div class="video-card">
                    <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="Vídeo Recomendado 1" allowfullscreen></iframe>
                </div>
                <div class="video-card">
                    <iframe src="https://www.youtube.com/embed/L_LUpnjgPso" title="Vídeo Recomendado 2" allowfullscreen></iframe>
                </div>
            </div>
        </div>

        <div class="avaliacao-section">
            <h2 style="color: #ffffff;">⭐ Avalie o Nosso Projeto</h2>
            <p style="color: #94a3b8; font-size: 0.9rem; margin-top: 5px;">O que você achou desta iniciativa na escola?</p>
            
            <div class="estrelas" id="estrelas">
                <span onclick="avaliar(1)">★</span>
                <span onclick="avaliar(2)">★</span>
                <span onclick="avaliar(3)">★</span>
                <span onclick="avaliar(4)">★</span>
                <span onclick="avaliar(5)">★</span>
            </div>
            <div class="mensagem-avaliacao" id="mensagemAvaliacao">Clique nas estrelas para avaliar!</div>
        </div>

        <footer>
            O cuidado com o patrimônio da escola é responsabilidade de todos os estudantes e funcionários.<br>
            © 2026 Game do Saber.
        </footer>
    </div>

    <script>
        function avaliar(nota) {
            const estrelas = document.querySelectorAll('#estrelas span');
            const mensagem = document.getElementById('mensagemAvaliacao');
            
            estrelas.forEach((estrela, index) => {
                if (index < nota) {
                    estrela.classList.add('ativo');
                } else {
                    estrela.classList.remove('ativo');
                }
            });

            const textos = [
                "Poxa! Vamos trabalhar para melhorar. 😞",
                "Obrigado pelo feedback! Vamos evoluir. 😐",
                "Legal! Bom ver seu apoio. 🙂",
                "Muito bom! Que legal que você gostou! 😀",
                "Incrível! Muito obrigado pela nota máxima! 🔥"
            ];

            mensagem.textContent = textos[nota - 1];
        }
    </script>

</body>
</html>