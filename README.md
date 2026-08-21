<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hall de Entrada — Projetos 2026</title>
    <style>
        *, *::before, *::after {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #0d1117;
            background-image: 
                radial-gradient(at 0% 0%, rgba(56, 189, 248, 0.12) 0px, transparent 50%),
                radial-gradient(at 100% 100%, rgba(99, 102, 241, 0.12) 0px, transparent 50%);
            color: #f3f4f6;
            font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 2rem 1rem;
        }

        .hall-wrapper {
            width: 100%;
            max-width: 1100px;
            background: rgba(17, 24, 39, 0.75);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 24px;
            padding: 2.5rem;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.6);
        }

        .hall-grid {
            display: grid;
            grid-template-columns: 1fr 1.3fr;
            gap: 2.5rem;
            align-items: center;
        }

        .hall-info {
            display: flex;
            flex-direction: column;
            gap: 1.25rem;
        }

        .badge {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.4rem 0.9rem;
            border-radius: 9999px;
            background: rgba(56, 189, 248, 0.1);
            border: 1px solid rgba(56, 189, 248, 0.3);
            color: #38bdf8;
            font-size: 0.75rem;
            font-weight: 700;
            letter-spacing: 0.05em;
            text-transform: uppercase;
            width: fit-content;
        }

        .dot {
            width: 6px;
            height: 6px;
            background-color: #38bdf8;
            border-radius: 50%;
            box-shadow: 0 0 8px #38bdf8;
        }

        h1 {
            font-size: 2.5rem;
            font-weight: 800;
            line-height: 1.15;
            background: linear-gradient(135deg, #ffffff 0%, #94a3b8 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        p {
            color: #9ca3af;
            font-size: 1rem;
            line-height: 1.6;
        }

        .live-tag {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            color: #22c55e;
            font-size: 0.875rem;
            font-weight: 600;
        }

        .pulse {
            width: 8px;
            height: 8px;
            background-color: #22c55e;
            border-radius: 50%;
            box-shadow: 0 0 10px #22c55e;
            animation: pulse-animation 1.5s infinite ease-in-out;
        }

        @keyframes pulse-animation {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.3; transform: scale(1.3); }
        }

        .video-card {
            position: relative;
            border-radius: 16px;
            overflow: hidden;
            background-color: #000;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.4);
        }

        video {
            width: 100%;
            height: 100%;
            display: block;
            object-fit: cover;
            pointer-events: none; /* Impede pausar pelo clique */
            user-select: none;
        }

        @media (max-width: 768px) {
            .hall-grid {
                grid-template-columns: 1fr;
                gap: 1.5rem;
            }
            .hall-wrapper {
                padding: 1.5rem;
            }
            h1 {
                font-size: 1.875rem;
            }
        }
    </style>
</head>
<body>

    <main class="hall-wrapper">
        <div class="hall-grid">
            <section class="hall-info">
                <div class="badge">
                    <span class="dot"></span>
                    2º Ano D • Programação
                </div>
                <h1>Hall de Entrada</h1>
                <p>Espaço principal de exibição dos projetos. O vídeo abaixo é executado de forma contínua e sem interrupções.</p>
                <div class="live-tag">
                    <span class="pulse"></span> Exibição contínua ativa
                </div>
            </section>

            <div class="video-card">
                <video autoplay loop muted playsinline>
                    <source src="./video.mp4" type="video/mp4">
                    Seu navegador não suporta a exibição deste vídeo.
                </video>
            </div>
        </div>
    </main>

</body>
</html>