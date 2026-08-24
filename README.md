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

        html, body {
            width: 100vw;
            height: 100vh;
            overflow: hidden;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background-color: #030712;
            color: #ffffff;
        }

        /* TELA DE START (FULLSCREEN) */
        .start-screen {
            position: fixed;
            inset: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 24px;
            background: radial-gradient(circle at center, #111827 0%, #030712 100%);
            z-index: 10;
            transition: opacity 0.6s ease, transform 0.6s ease;
        }

        .start-screen.hidden {
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
        }

        h1.title {
            font-size: clamp(2.5rem, 6vw, 4.5rem);
            font-weight: 900;
            line-height: 1.1;
            margin-bottom: 16px;
            background: linear-gradient(180deg, #ffffff 0%, #64748b 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        p.subtitle {
            font-size: 1.1rem;
            color: #94a3b8;
            max-width: 500px;
            margin-bottom: 40px;
            line-height: 1.6;
        }

        .btn-start {
            padding: 20px 64px;
            font-size: 1.25rem;
            font-weight: 900;
            letter-spacing: 4px;
            color: #030712;
            background: #38bdf8;
            border: none;
            border-radius: 60px;
            cursor: pointer;
            box-shadow: 0 0 30px rgba(56, 189, 248, 0.5);
            transition: all 0.3s ease;
        }

        .btn-start:hover {
            transform: translateY(-3px) scale(1.05);
            background: #00f0ff;
            box-shadow: 0 0 50px rgba(0, 240, 255, 0.8);
        }

        /* PALCO DO VÍDEO (HALL DE ENTRADA) */
        .hall-stage {
            position: fixed;
            inset: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            background: #000;
            opacity: 0;
            transition: opacity 0.8s ease;
            z-index: 1;
        }

        .hall-stage.active {
            opacity: 1;
        }

        .video-container {
            width: 90vw;
            max-width: 1200px;
            height: 80vh;
            border-radius: 24px;
            overflow: hidden;
            border: 1px solid rgba(255, 255, 255, 0.15);
            box-shadow: 0 0 50px rgba(0, 0, 0, 0.9);
        }

        video {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
            pointer-events: none;
        }
    </style>
</head>
<body>

    <!-- TELA INICIAL: START -->
    <section class="start-screen" id="startScreen">
        <span class="tag">2º Ano D • Programação</span>
        <h1 class="title">HALL DE ENTRADA</h1>
        <p class="subtitle">Clique no botão abaixo para acessar a exibição do projeto.</p>
        <button class="btn-start" id="btnStart">START</button>
    </section>

    <!-- PALCO DE EXIBIÇÃO -->
    <main class="hall-stage" id="hallStage">
        <div class="video-container">
            <video id="myVideo" loop muted playsinline>
                <source src="./video.mp4" type="video/mp4">
                Seu navegador não suporta este vídeo.
            </video>
        </div>
    </main>

    <script>
        const btnStart = document.getElementById('btnStart');
        const startScreen = document.getElementById('startScreen');
        const hallStage = document.getElementById('hallStage');
        const video = document.getElementById('myVideo');

        btnStart.addEventListener('click', () => {
            startScreen.classList.add('hidden');
            hallStage.classList.add('active');
            video.play();
        });
    </script>

</body>
</html>