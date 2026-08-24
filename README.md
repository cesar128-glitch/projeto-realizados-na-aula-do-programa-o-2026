<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hall de Entrada — Showcase 2026</title>
    <style>
        :root {
            --bg-dark: #030712;
            --primary-cyan: #38bdf8;
            --primary-glow: rgba(56, 189, 248, 0.4);
            --accent-purple: #818cf8;
            --text-main: #f9fafb;
            --text-sub: #9ca3af;
            --glass-bg: rgba(15, 23, 42, 0.7);
            --glass-border: rgba(255, 255, 255, 0.12);
        }

        *, *::before, *::after {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html, body {
            width: 100%;
            height: 100%;
            overflow: hidden;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            background-color: var(--bg-dark);
            color: var(--text-main);
        }

        /* Fundo de Imagem do Hall com Blur */
        .bg-image-overlay {
            position: fixed;
            inset: 0;
            background: url('./imagem.jpg') center/cover no-repeat;
            filter: brightness(0.25) blur(10px);
            transform: scale(1.05);
            z-index: 0;
            transition: transform 10s ease-out;
        }

        /* Canvas de Partículas Interativas */
        #particlesCanvas {
            position: fixed;
            inset: 0;
            z-index: 1;
            pointer-events: none;
        }

        /* --- TELA INICIAL: START --- */
        .start-screen {
            position: fixed;
            inset: 0;
            z-index: 10;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 2rem;
            text-align: center;
            transition: opacity 0.8s cubic-bezier(0.16, 1, 0.3, 1), transform 0.8s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .start-screen.hidden {
            opacity: 0;
            transform: scale(1.08);
            pointer-events: none;
        }

        .card-glass-hero {
            background: var(--glass-bg);
            backdrop-filter: blur(24px);
            -webkit-backdrop-filter: blur(24px);
            border: 1px solid var(--glass-border);
            border-radius: 32px;
            padding: 3.5rem 2.5rem;
            max-width: 650px;
            width: 100%;
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.8), 0 0 40px rgba(56, 189, 248, 0.15);
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 1.5rem;
        }

        .badge {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.5rem 1.25rem;
            border-radius: 9999px;
            background: rgba(56, 189, 248, 0.1);
            border: 1px solid rgba(56, 189, 248, 0.3);
            color: var(--primary-cyan);
            font-size: 0.8rem;
            font-weight: 700;
            letter-spacing: 0.1em;
            text-transform: uppercase;
        }

        .pulse-dot {
            width: 8px;
            height: 8px;
            background-color: var(--primary-cyan);
            border-radius: 50%;
            box-shadow: 0 0 10px var(--primary-cyan);
            animation: pulse 2s infinite ease-in-out;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.3; transform: scale(1.3); }
        }

        h1.title-hero {
            font-size: clamp(2.2rem, 5vw, 3.8rem);
            font-weight: 900;
            line-height: 1.1;
            background: linear-gradient(180deg, #ffffff 0%, #94a3b8 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        p.subtitle-hero {
            color: var(--text-sub);
            font-size: 1.05rem;
            line-height: 1.6;
            max-width: 480px;
        }

        /* Botão START Neon */
        .btn-start {
            position: relative;
            margin-top: 1rem;
            padding: 1.25rem 4rem;
            font-size: 1.2rem;
            font-weight: 900;
            letter-spacing: 0.25em;
            color: var(--bg-dark);
            background: var(--primary-cyan);
            border: none;
            border-radius: 9999px;
            cursor: pointer;
            box-shadow: 0 0 30px var(--primary-glow);
            transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1);
            overflow: hidden;
        }

        .btn-start:hover {
            transform: translateY(-3px) scale(1.05);
            background: #00f0ff;
            box-shadow: 0 0 50px rgba(0, 240, 255, 0.8);
        }

        .btn-start:active {
            transform: translateY(0) scale(0.98);
        }

        /* --- PALCO PRINCIPAL (HALL INTERATIVO) --- */
        .hall-stage {
            position: fixed;
            inset: 0;
            z-index: 2;
            display: grid;
            grid-template-columns: 1fr 1.4fr;
            gap: 2rem;
            padding: 2.5rem;
            max-width: 1400px;
            margin: auto;
            align-items: center;
            opacity: 0;
            transform: translateY(30px);
            pointer-events: none;
            transition: opacity 0.8s ease 0.2s, transform 0.8s ease 0.2s;
        }

        .hall-stage.active {
            opacity: 1;
            transform: translateY(0);
            pointer-events: all;
        }

        /* Coluna Esquerda: Informações e Galeria de Imagens */
        .hall-info-panel {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            padding: 2.5rem;
            border-radius: 24px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.6);
        }

        .gallery-preview {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 0.75rem;
            margin-top: 0.5rem;
        }

        .gallery-thumb {
            aspect-ratio: 4 / 3;
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid var(--glass-border);
            cursor: pointer;
            position: relative;
            transition: transform 0.3s ease, border-color 0.3s ease;
        }

        .gallery-thumb:hover {
            transform: translateY(-4px);
            border-color: var(--primary-cyan);
        }

        .gallery-thumb img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        /* Coluna Direita: Player de Vídeo Principal */
        .video-wrapper {
            position: relative;
            width: 100%;
            aspect-ratio: 16 / 9;
            background: #000;
            border-radius: 24px;
            overflow: hidden;
            border: 1px solid var(--glass-border);
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.8), 0 0 30px rgba(56, 189, 248, 0.15);
        }

        video {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
            pointer-events: none; /* Bloqueia clique para não pausar */
            user-select: none;
        }

        .live-badge {
            position: absolute;
            top: 1rem;
            left: 1rem;
            background: rgba(0, 0, 0, 0.6);
            backdrop-filter: blur(8px);
            border: 1px solid rgba(255, 255, 255, 0.15);
            padding: 0.4rem 1rem;
            border-radius: 50px;
            font-size: 0.75rem;
            font-weight: 700;
            color: #22c55e;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            z-index: 5;
        }

        /* Modal para visualizar imagem da galeria */
        .image-modal {
            position: fixed;
            inset: 0;
            z-index: 100;
            background: rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(12px);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.4s ease;
        }

        .image-modal.active {
            opacity: 1;
            pointer-events: all;
        }

        .image-modal img {
            max-width: 90%;
            max-height: 85vh;
            border-radius: 16px;
            border: 1px solid var(--glass-border);
            box-shadow: 0 0 50px rgba(0,0,0,0.8);
        }

        /* Responsividade */
        @media (max-width: 1024px) {
            .hall-stage {
                grid-template-columns: 1fr;
                padding: 1.5rem;
                overflow-y: auto;
            }
        }
    </style>
</head>
<body>

    <!-- Fundo Visual com Imagem -->
    <div class="bg-image-overlay" id="bgOverlay"></div>

    <!-- Canvas de Partículas em JS -->
    <canvas id="particlesCanvas"></canvas>

    <!-- TELA DE APRESENTAÇÃO (START) -->
    <section class="start-screen" id="startScreen">
        <div class="card-glass-hero">
            <span class="badge">
                <span class="pulse-dot"></span>
                2º Ano D • Programação
            </span>
            <h1 class="title-hero">HALL DE ENTRADA</h1>
            <p class="subtitle-hero">Espaço interativo de exibição dos projetos. Pressione o botão para acessar o painel de demonstração.</p>
            <button class="btn-start" id="btnStart">START</button>
        </div>
    </section>

    <!-- PALCO INTERATIVO DO HALL -->
    <main class="hall-stage" id="hallStage">
        <!-- Painel de Informações e Galeria -->
        <section class="hall-info-panel">
            <span class="badge" style="width: fit-content;">Projetos 2026</span>
            <h2 style="font-size: 2rem; font-weight: 800;">Painel de Exibição</h2>
            <p style="color: var(--text-sub); font-size: 0.95rem; line-height: 1.6;">
                Navegue pelas capturas de tela das aulas ou acompanhe a transmissão contínua no player ao lado.
            </p>

            <h3 style="font-size: 0.9rem; text-transform: uppercase; letter-spacing: 1px; color: var(--primary-cyan); margin-top: 0.5rem;">Galeria do Projeto</h3>
            <div class="gallery-preview">
                <div class="gallery-thumb" onclick="openModal('./imagem.jpg')">
                    <img src="./imagem.jpg" alt="Projeto 1" onerror="this.src='https://via.placeholder.com/300x200/1e293b/ffffff?text=Imagem+1'">
                </div>
                <div class="gallery-thumb" onclick="openModal('./imagem.jpg')">
                    <img src="./imagem.jpg" alt="Projeto 2" onerror="this.src='https://via.placeholder.com/300x200/1e293b/ffffff?text=Imagem+2'">
                </div>
                <div class="gallery-thumb" onclick="openModal('./imagem.jpg')">
                    <img src="./imagem.jpg" alt="Projeto 3" onerror="this.src='https://via.placeholder.com/300x200/1e293b/ffffff?text=Imagem+3'">
                </div>
            </div>
        </section>

        <!-- Player de Vídeo em Loop -->
        <section class="video-wrapper">
            <div class="live-badge">
                <span class="pulse-dot" style="background:#22c55e; box-shadow:0 0 10px #22c55e;"></span>
                Exibição Contínua
            </div>
            <video id="mainVideo" loop muted playsinline>
                <source src="./video.mp4" type="video/mp4">
                Seu navegador não suporta reprodução de vídeo.
            </video>
        </section>
    </main>

    <!-- MODAL DE IMAGEM -->
    <div class="image-modal" id="imageModal" onclick="closeModal()">
        <img id="modalImg" src="" alt="Ampliação">
    </div>

    <!-- SCRIPT JS AVANÇADO -->
    <script>
        // --- 1. GERENCIADOR DO SISTEMA DE PARTÍCULAS ---
        const canvas = document.getElementById('particlesCanvas');
        const ctx = canvas.getContext('2d');
        let particles = [];

        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        window.addEventListener('resize', resizeCanvas);
        resizeCanvas();

        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 2 + 0.5;
                this.speedX = (Math.random() - 0.5) * 0.5;
                this.speedY = (Math.random() - 0.5) * 0.5;
                this.opacity = Math.random() * 0.5 + 0.2;
            }
            update() {
                this.x += this.speedX;
                this.y += this.speedY;

                if (this.x < 0 || this.x > canvas.width) this.speedX *= -1;
                if (this.y < 0 || this.y > canvas.height) this.speedY *= -1;
            }
            draw() {
                ctx.fillStyle = `rgba(56, 189, 248, ${this.opacity})`;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
            }
        }

        function initParticles() {
            particles = [];
            for (let i = 0; i < 60; i++) {
                particles.push(new Particle());
            }
        }

        function animateParticles() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particles.forEach(p => {
                p.update();
                p.draw();
            });
            requestAnimationFrame(animateParticles);
        }

        initParticles();
        animateParticles();

        // --- 2. TRANSIÇÃO DO BOTÃO START ---
        const btnStart = document.getElementById('btnStart');
        const startScreen = document.getElementById('startScreen');
        const hallStage = document.getElementById('hallStage');
        const bgOverlay = document.getElementById('bgOverlay');
        const video = document.getElementById('mainVideo');

        btnStart.addEventListener('click', () => {
            startScreen.classList.add('hidden');
            bgOverlay.style.transform = 'scale(1)'; // Efeito de zoom na imagem de fundo
            
            setTimeout(() => {
                startScreen.style.display = 'none';
                hallStage.classList.add('active');
                video.play().catch(e => console.log("Aviso de auto-play:", e));
            }, 600);
        });

        // --- 3. MODAL DE GALERIA ---
        const modal = document.getElementById('imageModal');
        const modalImg = document.getElementById('modalImg');

        function openModal(src) {
            modalImg.src = src;
            modal.classList.add('active');
        }

        function closeModal() {
            modal.classList.remove('active');
        }
    </script>

</body>
</html>