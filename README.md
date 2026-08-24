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
            background-color: #030712;
            color: #f9fafb;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 2rem;
        }

        .main-card {
            width: 100%;
            max-width: 1100px;
            background: rgba(15, 23, 42, 0.95);
            border: 1px solid rgba(255, 255, 255, 0.12);
            border-radius: 24px;
            padding: 2.5rem;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.8);
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }

        .header {
            display: flex;
            flex-direction: column;
            gap: 0.75rem;
        }

        .badge {
            align-self: flex-start;
            padding: 6px 16px;
            border-radius: 9999px;
            background: rgba(56, 189, 248, 0.1);
            border: 1px solid rgba(56, 189, 248, 0.3);
            color: #38bdf8;
            font-size: 0.8rem;
            font-weight: 700;
            letter-spacing: 0.05em;
            text-transform: uppercase;
        }

        h1 {
            font-size: clamp(1.8rem, 4vw, 2.8rem);
            font-weight: 900;
            color: #ffffff;
        }

        p.desc {
            color: #9ca3af;
            font-size: 1rem;
            line-height: 1.6;
        }

        .grid-content {
            display: grid;
            grid-template-columns: 1.2fr 1fr;
            gap: 1.5rem;
        }

        @media (max-width: 850px) {
            .grid-content {
                grid-template-columns: 1fr;
            }
        }

        .video-box {
            width: 100%;
            aspect-ratio: 16 / 9;
            background: #000;
            border-radius: 16px;
            overflow: hidden;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        video {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .gallery-title {
            font-size: 0.9rem;
            font-weight: 700;
            color: #38bdf8;
            margin-bottom: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 0.05em;
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 0.75rem;
        }

        .gallery-item {
            aspect-ratio: 16 / 10;
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid rgba(255, 255, 255, 0.1);
            cursor: pointer;
            transition: transform 0.2s ease, border-color 0.2s ease;
            background: #1e293b;
        }

        .gallery-item:hover {
            transform: scale(1.03);
            border-color: #38bdf8;
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        .modal {
            position: fixed;
            inset: 0;
            background: rgba(0, 0, 0, 0.9);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 100;
            padding: 20px;
        }

        .modal.active {
            display: flex;
        }

        .modal img {
            max-width: 90vw;
            max-height: 85vh;
            border-radius: 12px;
        }
    </style>
</head>
<body>

    <main class="main-card">
        <div class="header">
            <span class="badge">2º Ano D • Programação</span>
            <h1>Hall de Entrada</h1>
            <p class="desc">Acesse o vídeo do projeto usando os controles do player ou clique em qualquer imagem abaixo para ampliar.</p>
        </div>

        <div class="grid-content">
            <div class="video-box">
                <video controls playsinline poster="./Gemini_Generated_Image_yl6xrmyl6xrmyl6x.png">
                    <source src="./video.mp4" type="video/mp4">
                    Seu navegador não suporta reprodução de vídeo.
                </video>
            </div>

            <div>
                <div class="gallery-title">Capturas do Projeto</div>
                <div class="gallery-grid">
                    <div class="gallery-item" onclick="openModal('./Gemini_Generated_Image_yl6xrmyl6xrmyl6x.png')">
                        <img src="./Gemini_Generated_Image_yl6xrmyl6xrmyl6x.png" alt="Captura 1">
                    </div>
                    <div class="gallery-item" onclick="openModal('./Gemini_Generated_Image_7yo3fo7yo3fo7yo3.png')">
                        <img src="./Gemini_Generated_Image_7yo3fo7yo3fo7yo3.png" alt="Captura 2">
                    </div>
                    <div class="gallery-item" onclick="openModal('./7278812297501217892.jpg')">
                        <img src="./7278812297501217892.jpg" alt="Captura 3">
                    </div>
                    <div class="gallery-item" onclick="openModal('./5236443161723305068.jpg')">
                        <img src="./5236443161723305068.jpg" alt="Captura 4">
                    </div>
                </div>
            </div>
        </div>
    </main>

    <div class="modal" id="modal" onclick="closeModal()">
        <img id="modalImg" src="" alt="Imagem Ampliada">
    </div>

    <script>
        function openModal(src) {
            document.getElementById('modalImg').src = src;
            document.getElementById('modal').classList.add('active');
        }
        function closeModal() {
            document.getElementById('modal').classList.remove('active');
        }
    </script>

</body>
</html>