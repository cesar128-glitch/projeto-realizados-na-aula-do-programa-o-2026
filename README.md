<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hall de Entrada — Central Multimídia</title>
    <style>
        *, *::before, *::after {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #080c14;
            color: #f1f5f9;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            min-height: 100vh;
            padding: 2rem 1rem;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            gap: 2.5rem;
        }

        header {
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            padding-bottom: 1.5rem;
        }

        .badge {
            display: inline-block;
            padding: 4px 14px;
            border-radius: 20px;
            background: rgba(56, 189, 248, 0.15);
            border: 1px solid rgba(56, 189, 248, 0.4);
            color: #38bdf8;
            font-size: 0.8rem;
            font-weight: 700;
            text-transform: uppercase;
            margin-bottom: 0.75rem;
        }

        h1 {
            font-size: clamp(2rem, 4vw, 3rem);
            font-weight: 900;
        }

        .section-title {
            font-size: 1.1rem;
            font-weight: 800;
            color: #38bdf8;
            text-transform: uppercase;
            letter-spacing: 0.05em;
            margin-bottom: 1rem;
        }

        /* BANNER PROPAGANDA ANOS 90 */
        .ad-banner-90s {
            background: linear-gradient(135deg, #ff007f, #7928ca, #00dfd8);
            padding: 3px;
            border-radius: 16px;
            box-shadow: 0 0 25px rgba(255, 0, 127, 0.3);
        }

        .ad-inner {
            background: #0d1117;
            border-radius: 13px;
            padding: 1.5rem;
            display: grid;
            grid-template-columns: 1fr 1.5fr;
            gap: 1.5rem;
            align-items: center;
        }

        @media (max-width: 768px) {
            .ad-inner {
                grid-template-columns: 1fr;
            }
        }

        .ad-tag {
            background: #ff007f;
            color: #fff;
            font-size: 0.7rem;
            font-weight: 900;
            padding: 2px 8px;
            border-radius: 4px;
            text-transform: uppercase;
            width: fit-content;
            margin-bottom: 0.5rem;
        }

        .video-container {
            width: 100%;
            aspect-ratio: 16 / 9;
            border-radius: 12px;
            overflow: hidden;
            background: #000;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        iframe {
            width: 100%;
            height: 100%;
            border: none;
        }

        /* GRID DE VÍDEOS ALEATÓRIOS DO YOUTUBE */
        .youtube-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
        }

        /* GALERIA DE IMAGENS */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 1rem;
        }

        .gallery-card {
            aspect-ratio: 16 / 10;
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid rgba(255, 255, 255, 0.1);
            background: #1e293b;
            cursor: pointer;
            transition: transform 0.2s, border-color 0.2s;
        }

        .gallery-card:hover {
            transform: translateY(-4px);
            border-color: #38bdf8;
        }

        .gallery-card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        /* MODAL */
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

    <div class="container">
        <header>
            <span class="badge">2º Ano D • Programação</span>
            <h1>Hall de Entrada</h1>
        </header>

        <!-- ESPAÇO PROPAGANDA ANOS 90 -->
        <section class="ad-banner-90s">
            <div class="ad-inner">
                <div>
                    <div class="ad-tag">Nostalgia 90s</div>
                    <h2 style="font-size: 1.5rem; margin-bottom: 0.5rem;">Comercial Clássico Anos 90</h2>
                    <p style="color: #94a3b8; font-size: 0.9rem;">Exibição especial do intervalo comercial retrô pós-avaliação.</p>
                </div>
                <div class="video-container">
                    <iframe src="https://www.youtube.com/embed/5NV6Rdv1a3E" title="Comercial Anos 90" allowfullscreen></iframe>
                </div>
            </div>
        </section>

        <!-- VÍDEOS ALEATÓRIOS DO YOUTUBE -->
        <section>
            <div class="section-title">Vídeos Recomendados do YouTube</div>
            <div class="youtube-grid">
                <div class="video-container">
                    <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="YouTube Video 1" allowfullscreen></iframe>
                </div>
                <div class="video-container">
                    <iframe src="https://www.youtube.com/embed/L_LUpnjgPso" title="YouTube Video 2" allowfullscreen></iframe>
                </div>
            </div>
        </section>

        <!-- GALERIA DE IMAGENS -->
        <section>
            <div class="section-title">Capturas do Projeto</div>
            <div class="gallery-grid">
                <div class="gallery-card" onclick="openModal('./Gemini_Generated_Image_yl6xrmyl6xrmyl6x.png')">
                    <img src="./Gemini_Generated_Image_yl6xrmyl6xrmyl6x.png" alt="Captura 1">
                </div>
                <div class="gallery-card" onclick="openModal('./Gemini_Generated_Image_7yo3fo7yo3fo7yo3.png')">
                    <img src="./Gemini_Generated_Image_7yo3fo7yo3fo7yo3.png" alt="Captura 2">
                </div>
                <div class="gallery-card" onclick="openModal('./7278812297501217892.jpg')">
                    <img src="./7278812297501217892.jpg" alt="Captura 3">
                </div>
                <div class="gallery-card" onclick="openModal('./5236443161723305068.jpg')">
                    <img src="./5236443161723305068.jpg" alt="Captura 4">
                </div>
            </div>
        </section>
    </div>

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