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

        html, body {
            width: 100%;
            height: 100%;
            overflow: hidden;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background-color: #050811;
            color: #ffffff;
        }

        /* --- TELA INICIAL: HALL DE ENTRADA (100vh) --- */
        .hall-screen {
            position: fixed;
            inset: 0;
            width: 100vw;
            height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 20px;
            z-index: 10;
            background: radial-gradient(circle at center, #111827 0%, #050811 100%);
            transition: opacity 0.8s cubic-bezier(0.16, 1, 0.3, 1), transform 0.8s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .hall-screen.hidden {
            opacity: 0;
            transform: scale(1.05);
            pointer-events: none;
        }

        .tag {
            padding: 8px 20px;
            border-radius: 50px;
            background: rgba(56, 189, 248, 0.1);
            border: 1px solid rgba(56, 189, 248, 0.3);
            color: #38bdf8;
            font-size: 0.85rem;
            font-weight: 700;
            letter-spacing: 2px;
            text-transform: uppercase;
            margin-bottom: 24px;
            box-shadow: 0 0 15px rgba(56, 189, 248, 0.2);
        }

        h1.main-title {
            font-size: clamp(2.5rem, 6vw, 4.5rem);
            font-weight: 900;
            line-height: 1.1;
            margin-bottom: 16px;
            background: linear-gradient(180deg, #ffffff 0%, #64748b 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        p.description {
            font-size: clamp(1rem, 2vw, 1.25rem);
            color: #94a3b8;
            max-width: 600px;
            margin-bottom: 40px;
            line-height: 1.6;
        }

        /* Botão START Gigante e Neons */
        .btn-start {
            position: relative;
            padding: 20px 64px;
            font-size: 1.25rem;
            font-weight: 900;
            letter-spacing: 4px;
            color: #050811;
            background: #38bdf8;
            border: none;
            border-radius: 60px;
            cursor: pointer;
            box-shadow: 0 0 30px rgba(56, 189, 248, 0.6);
            transition: all 0.4s ease;
        }

        .btn-start:hover {
            transform: translateY(-4px) scale(1.05);
            background: #00f0ff;
            box-shadow: 0 0 50px rgba(0, 240, 255, 0.9);
        }

        /* --- TELA DO VÍDEO (100vh Fullscreen) --- */
        .video-stage {
            position: fixed;
            inset: 0;
            width: 100vw;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: #000;
            opacity: 0;
            transition: opacity 1s ease;
            z-index: 1;
        }

        .video-stage.active {
            opacity: 1;
        }

        .video-container {
            width: 90vw;
            max-width: 1200px;
            height: 80vh;
            border-radius: 24px;
            overflow: hidden;
            box-shadow: 0 0 50px rgba(0, 0, 0, 0.9), 0 0 20px rgba(56, 189, 248, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        video {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
            pointer-events: none; /* Bloqueia clique para não pausar */
        }
    </style>
</head>
<body>

    <!-- HALL DE ENTRADA -->
    <section class="hall-screen" id="hallScreen">
        <span class="tag">2º Ano D • Programação</span>
        <h1 class="main-title">HALL DE ENTRADA</h1>
        <p class="description">Espaço principal de apresentação dos projetos realizados em aula durante o ano letivo.</p>
        <button class="btn-start" id="btnStart">START</button>
    </section>

    <!-- PALCO DO VÍDEO -->
    <main class="video-stage" id="videoStage">
        <div class="video-container">
            <video id="projectVideo" loop muted playsinline>
                <source src="./video.mp4" type="video/mp4">
                Seu navegador não suporta a exibição deste vídeo.
            </video>
        </div>
    </main>

    <script>
        const btnStart = document.getElementById('btnStart');
        const hallScreen = document.getElementById('hallScreen');
        const videoStage = document.getElementById('videoStage');
        const video = document.getElementById('projectVideo');

        btnStart.addEventListener('click', () => {
            hallScreen.classList.add('hidden');
            videoStage.classList.add('active');
            
            // Inicia reprodução
            video.play();
        });
    </script>

</body>
</html>