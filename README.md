<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hall de Entrada • Projetos 2026</title>
    <style>
        :root {
            --bg-gradient: linear-gradient(135deg, #0b0f19 0%, #111827 50%, #0d1117 100%);
            --card-bg: rgba(22, 27, 34, 0.75);
            --border-glow: rgba(88, 166, 255, 0.25);
            --accent: #58a6ff;
            --text-main: #f0f6fc;
            --text-muted: #8b949e;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: var(--bg-gradient);
            color: var(--text-main);
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 24px;
        }

        /* Container do Hall com efeito Glassmorphism e animação */
        .hall-card {
            display: grid;
            grid-template-columns: 1fr 1.2fr;
            gap: 32px;
            width: 100%;
            max-width: 1050px;
            background: var(--card-bg);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid var(--border-glow);
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 25px 60px rgba(0, 0, 0, 0.7);
            animation: fadeIn 0.8s cubic-bezier(0.16, 1, 0.3, 1) forwards;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Lado esquerdo: Conteúdo da entrada */
        .hall-content {
            display: flex;
            flex-direction: column;
            justify-content: center;
            gap: 18px;
        }

        .badge {
            align-self: flex-start;
            background: rgba(88, 166, 255, 0.12);
            color: var(--accent);
            border: 1px solid rgba(88, 166, 255, 0.3);
            padding: 6px 14px;
            border-radius: 50px;
            font-size: 0.75rem;
            font-weight: 700;
            letter-spacing: 1px;
            text-transform: uppercase;
        }

        h1 {
            font-size: 2.2rem;
            font-weight: 800;
            line-height: 1.25;
            background: linear-gradient(180deg, #ffffff 0%, #cbd5e1 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        p {
            color: var(--text-muted);
            font-size: 0.95rem;
            line-height: 1.6;
        }

        .status {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-size: 0.85rem;
            color: #3fb950;
            font-weight: 600;
            margin-top: 6px;
        }

        .dot {
            width: 8px;
            height: 8px;
            background-color: #3fb950;
            border-radius: 50%;
            box-shadow: 0 0 10px #3fb950;
            animation: pulse 1.8s infinite ease-in-out;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.3; transform: scale(1.2); }
        }

        /* Lado direito: Vídeo com bloqueio de pausa */
        .video-container {
            position: relative;
            width: 100%;
            border-radius: 14px;
            overflow: hidden;
            background: #000;
            border: 1px solid rgba(255, 255, 255, 0.08);
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.5);
        }

        video {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
            pointer-events: none; /* Desativa totalmente cliques no vídeo */
            user-select: none;
        }

        /* Responsividade para mobile */
        @media (max-width: 820px) {
            .hall-card {
                grid-template-columns: 1fr;
                padding: 28px;
                gap: 24px;
            }

            h1 {
                font-size: 1.75rem;
            }
        }
    </style>
</head>
<body>

    <main class="hall-card">
        <!-- Painel de Recepção -->
        <article class="hall-content">
            <span class="badge">2º Ano D • Programação</span>
            <h1>Hall de Entrada</h1>
            <p>Espaço de apresentação do projeto desenvolvido em aula. A exibição roda em loop automático e sem interrupções.</p>
            <div class="status">
                <span class="dot"></span> Transmissão Contínua
            </div>
        </article>

        <!-- Player de Vídeo -->
        <div class="video-container">
            <video autoplay loop muted playsinline>
                <source src="./video.mp4" type="video/mp4">
                Seu navegador não suporta a exibição deste vídeo.
            </video>
        </div>
    </main>

</body>
</html>