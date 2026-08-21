<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Projetos de Programação 2026</title>
    <style>
        :root {
            --bg-color: #0b0f19;
            --card-bg: rgba(22, 27, 34, 0.7);
            --accent-color: #58a6ff;
            --border-color: rgba(255, 255, 255, 0.1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: var(--bg-color);
            background-image: radial-gradient(circle at 50% 0%, #1e293b 0%, #0b0f19 70%);
            color: #f0f6fc;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            padding: 20px;
        }

        .badge {
            background: rgba(88, 166, 255, 0.15);
            color: var(--accent-color);
            border: 1px solid rgba(88, 166, 255, 0.3);
            padding: 6px 14px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 600;
            margin-bottom: 12px;
            letter-spacing: 0.5px;
            text-transform: uppercase;
        }

        h1 {
            font-size: 2.2rem;
            font-weight: 700;
            margin-bottom: 24px;
            text-align: center;
            background: linear-gradient(135deg, #ffffff 0%, #8b949e 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .video-card {
            position: relative;
            width: 100%;
            max-width: 850px;
            background: var(--card-bg);
            backdrop-filter: blur(12px);
            border: 1px solid var(--border-color);
            border-radius: 16px;
            padding: 12px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.6);
        }

        .video-wrapper {
            position: relative;
            width: 100%;
            border-radius: 10px;
            overflow: hidden;
            background-color: #000000;
        }

        video {
            width: 100%;
            height: auto;
            display: block;
            pointer-events: none; /* Desativa totalmente a interação e a pausa */
            user-select: none;
        }
    </style>
</head>
<body>

    <span class="badge">2º Ano D - Programação</span>
    <h1>Projetos Realizados em Aula</h1>

    <div class="video-card">
        <div class="video-wrapper">
            <video autoplay loop muted playsinline>
                <source src="./video.mp4" type="video/mp4">
                Seu navegador não suporta a exibição deste vídeo.
            </video>
        </div>
    </div>

</body>
</html>