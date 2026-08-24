<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hall de Entrada — 2026</title>
    <style>
        *, *::before, *::after {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #080c14;
            background-image: 
                radial-gradient(circle at 50% 30%, rgba(56, 189, 248, 0.15), transparent 70%),
                radial-gradient(circle at 80% 80%, rgba(129, 140, 248, 0.1), transparent 50%);
            color: #f3f4f6;
            font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
            overflow: hidden;
        }

        /* --- TELA INICIAL DE START --- */
        .start-screen {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            gap: 20px;
            max-width: 500px;
            transition: opacity 0.5s ease, transform 0.5s ease;
        }

        .start-screen.hidden {
            opacity: 0;
            transform: scale(0.9);
            pointer-events: none;
            position: absolute;
        }

        .badge {
            padding: 6px 16px;
            border-radius: 9999px;
            background: rgba(56, 189, 248, 0.1);
            border: 1px solid rgba(56, 189, 248, 0.3);
            color: #38bdf8;
            font-size: 0.75rem;
            font-weight: 700;
            letter-spacing: 1px;
            text-transform: uppercase;
        }

        h1.title {
            font-size: 2.8rem;
            font-weight: 800;
            line-height: 1.1;
            background: linear-gradient(135deg, #ffffff 0%, #94a3b8 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        p.subtitle {
            color: #9ca3af;
            font-size: 0.95rem;
            line-height: 1.5;
        }

        .btn-start {
            margin-top: 10px;
            padding: 16px 48px;
            font-size: 1.1rem;
            font-weight: 800;
            letter-spacing: 2px;
            color: #080c14;
            background: #38bdf8;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 0 25px rgba(56, 189, 248, 0.5);
            transition: all 0.3s ease;
        }

        .btn-start:hover {
            transform: translateY(-3px) scale(1.04);
            box-shadow: 0 0 40px rgba(56, 189, 248, 0.8);
            background: #7dd3fc;
        }

        /* --- CONTEÚDO DO HALL --- */
        .hall-card {
            display: none;
            opacity: 0;
            grid-template-columns: 1fr 1.3fr;
            gap: 32px;
            width: 100%;
            max-width: 1050px;
            background: rgba(15, 23, 42, 0.75);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 24px;
            padding: 36px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.7);
            align-items: center;
            transition: opacity 0.6s ease, transform 0.6s ease;
            transform: translateY(20px);
        }

        .hall-card.active {
            display: grid;
            opacity: 1;
            transform: translateY(0);
        }

        .hall-info {
            display: flex;
            flex-direction: column;
            gap: 16px;
        }

        .status {
            display: flex;
            align-items: center;
            gap: 8px;
            color: #22c55e;
            font-size: 0.85rem;
            font-weight: 600;
        }

        .pulse {
            width: 8px;
            height: 8px;
            background-color: #22c55e;
            border-radius: 50%;
            box-shadow: 0 0 10px #22c55e;
            animation: pulse 1.8s infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.3; transform: scale(1.3); }
        }

        .video-box {
            position: relative;
            border-radius: 16px;
            overflow: hidden;
            background: #000;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 20px 30px rgba(0, 0, 0, 0.5);
            aspect-ratio: 16 / 9;
        }

        video {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
            pointer-events: none; /* Impede pausar pelo clique */
            user-select: none;
        }

        @media (max-width: 800px) {
            .hall-card {
                grid-template-columns: 1fr;
                padding: 24px;
            }
        }
    </style>
</head>
<body>

    <!-- TELA INICIAL COM BOTÃO START -->
    <main class="start-screen" id="startScreen">
        <span class="badge">2º Ano D • Programação</span>
        <h1 class="title">Hall de Entrada</h1>
        <p class="subtitle">Pressione o botão para iniciar a exibição dos projetos.</p>
        <button class="btn-start" id="btnStart">START</button>
    </main>

    <!-- PAINEL DO HALL -->
    <div class="hall-card" id="hallCard">
        <div class="hall-info">
            <span class="badge">2º Ano D • Programação</span>
            <h1 class="title" style="font-size: 2.2rem;">Projeto em Exibição</h1>
            <p class="subtitle">Exibição em loop contínuo e sem interrupções.</p>
            <div class="status">
                <span class="pulse"></span> Transmissão Ativa
            </div>
        </div>

        <div class="video-box">
            <video id="myVideo" loop muted playsinline>
                <source src="./video.mp4" type="video/mp4">
                Seu navegador não suporta a exibição deste vídeo.
            </video>
        </div>
    </div>

    <script>
        const btnStart = document.getElementById('btnStart');
        const startScreen = document.getElementById('startScreen');
        const hallCard = document.getElementById('hallCard');
        const video = document.getElementById('myVideo');

        btnStart.addEventListener('click', () => {
            startScreen.classList.add('hidden');

            setTimeout(() => {
                startScreen.style.display = 'none';
                hallCard.classList.add('active');
                video.play();
            }, 500);
        });
    </script>

</body>
</html>