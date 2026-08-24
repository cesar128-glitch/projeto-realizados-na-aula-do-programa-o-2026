<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hall de Entrada • Projetos 2026</title>
    <style>
        *, *::before, *::after {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #090d16;
            background-image: 
                radial-gradient(circle at 50% 20%, rgba(56, 189, 248, 0.15) 0%, transparent 60%),
                radial-gradient(circle at 80% 80%, rgba(99, 102, 241, 0.1) 0%, transparent 50%);
            color: #f3f4f6;
            font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
            overflow: hidden;
        }

        /* --- TELA INICIAL (START) --- */
        .start-screen {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            gap: 20px;
            max-width: 600px;
            transition: opacity 0.6s ease, transform 0.6s ease;
        }

        .start-screen.hidden {
            opacity: 0;
            transform: scale(0.95);
            pointer-events: none;
            position: absolute;
        }

        .badge {
            padding: 6px 16px;
            border-radius: 9999px;
            background: rgba(56, 189, 248, 0.1);
            border: 1px solid rgba(56, 189, 248, 0.3);
            color: #38bdf8;
            font-size: 0.8rem;
            font-weight: 700;
            letter-spacing: 1px;
            text-transform: uppercase;
        }

        h1.welcome-title {
            font-size: 2.8rem;
            font-weight: 800;
            line-height: 1.2;
            background: linear-gradient(135deg, #ffffff 0%, #94a3b8 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        p.welcome-text {
            color: #9ca3af;
            font-size: 1rem;
            line-height: 1.6;
        }

        /* Botão Start Estilizado */
        .btn-start {
            margin-top: 10px;
            padding: 16px 48px;
            font-size: 1.1rem;
            font-weight: 800;
            letter-spacing: 2px;
            color: #090d16;
            background: #38bdf8;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 0 25px rgba(56, 189, 248, 0.5);
            transition: all 0.3s ease;
        }

        .btn-start:hover {
            transform: translateY(-3px) scale(1.03);
            box-shadow: 0 0 40px rgba(56, 189, 248, 0.8);
            background: #7dd3fc;
        }

        .btn-start:active {
            transform: translateY(0) scale(0.98);
        }

        /* --- PAINEL DO HALL (EXIBIDO APÓS O START) --- */
        .hall-container {
            display: none;
            opacity: 0;
            grid-template-columns: 1fr 1.3fr;
            gap: 32px;
            width: 100%;
            max-width: 1100px;
            background: rgba(17, 24, 39, 0.8);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 24px;
            padding: 36px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.7);
            align-items: center;
            transition: opacity 0.6s ease;
        }

        .hall-container.active {
            display: grid;
            opacity: 1;
        }

        .hall-info {
            display: flex;
            flex-direction: column;
            gap: 16px;
        }

        .status-tag {
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
            animation: pulse-animation 1.5s infinite ease-in-out;
        }

        @keyframes pulse-animation {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.3; transform: scale(1.3); }
        }

        .video-box {
            position: relative;
            border-radius: 16px;
            overflow: hidden;
            background-color: #000;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 20px 30px rgba(0, 0, 0, 0.5);
        }

        video {
            width: 100%;
            height: 100%;
            display: block;
            object-fit: cover;
            pointer-events: none; /* Bloqueia cliques para impedir pausa */
            user-select: none;
        }

        @media (max-width: 800px) {
            .hall-container {
                grid-template-columns: 1fr;
                padding: 24px;
            }
            h1.welcome-title {
                font-size: 2.2rem;
            }
        }
    </style>
</head>
<body>

    <!-- Tela Inicial com Botão Start -->
    <main class="start-screen" id="startScreen">
        <span class="badge">2º Ano D • Programação</span>
        <h1 class="welcome-title">Hall de Entrada</h1>
        <p class="welcome-text">Clique no botão abaixo para dar início à exibição dos projetos realizados em aula.</p>
        <button class="btn-start" id="btnStart">START</button>
    </main>

    <!-- Painel Principal (Aparece após o Start) -->
    <section class="hall-container" id="hallContainer">
        <div class="hall-info">
            <span class="badge">2º Ano D • Programação</span>
            <h1 class="welcome-title" style="font-size: 2rem;">Projeto em Exibição</h1>
            <p class="welcome-text">Demonstração contínua rodando em loop sem interrupções.</p>
            <div class="status-tag">
                <span class="pulse"></span> Transmissão Ativa
            </div>
        </div>

        <div class="video-box">
            <video id="mainVideo" loop muted playsinline>
                <source src="./video.mp4" type="video/mp4">
                Seu navegador não suporta a exibição deste vídeo.
            </video>
        </div>
    </section>

    <script>
        const btnStart = document.getElementById('btnStart');
        const startScreen = document.getElementById('startScreen');
        const hallContainer = document.getElementById('hallContainer');
        const video = document.getElementById('mainVideo');

        btnStart.addEventListener('click', () => {
            // Esconde a tela do Start
            startScreen.classList.add('hidden');

            setTimeout(() => {
                startScreen.style.display = 'none';
                
                // Exibe o painel do Hall
                hallContainer.classList.add('active');
                
                // Inicia o vídeo
                video.play();
            }, 600);
        });
    </script>

</body>
</html>