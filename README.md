A tela está preta porque o GitHub Pages desativa os scripts (JavaScript) e quebra o CSS quando o código está salvo em um arquivo README.md.

Para corrigir definitivamente:

Apague o arquivo README.md do seu repositório no GitHub.

Crie um novo arquivo com o nome exato index.html.

Crie outro arquivo em branco chamado .nojekyll (com o ponto no início) para desativar o leitor do GitHub.

Cole o código abaixo dentro do index.html:

HTML
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hall de Entrada — 2026</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #0f172a;
            color: #ffffff;
            font-family: system-ui, -apple-system, sans-serif;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .container {
            width: 100%;
            max-width: 900px;
            background: #1e293b;
            border: 1px solid #334155;
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.5);
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .header {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        .badge {
            align-self: flex-start;
            background: rgba(56, 189, 248, 0.1);
            color: #38bdf8;
            border: 1px solid rgba(56, 189, 248, 0.3);
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 0.75rem;
            font-weight: 700;
            text-transform: uppercase;
        }

        h1 {
            font-size: 2rem;
            font-weight: 800;
        }

        p {
            color: #94a3b8;
            font-size: 0.95rem;
            line-height: 1.5;
        }

        .video-box {
            width: 100%;
            aspect-ratio: 16 / 9;
            background: #000000;
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid #334155;
            position: relative;
        }

        video {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .status {
            display: flex;
            align-items: center;
            gap: 8px;
            color: #4ade80;
            font-size: 0.85rem;
            font-weight: 600;
        }

        .dot {
            width: 8px;
            height: 8px;
            background-color: #4ade80;
            border-radius: 50%;
            box-shadow: 0 0 8px #4ade80;
        }
    </style>
</head>
<body>

    <div class="container">
        <div class="header">
            <span class="badge">2º Ano D • Programação</span>
            <h1>Hall de Entrada</h1>
            <p>Espaço principal de exibição dos projetos. O vídeo abaixo é executado de forma contínua e sem interrupções.</p>
        </div>

        <div class="video-box">
            <video autoplay loop muted playsinline>
                <source src="video.mp4" type="video/mp4">
                Seu navegador não suporta a exibição deste vídeo.
            </video>
        </div>

        <div class="status">
            <span class="dot"></span>
            Exibição contínua ativa
        </div>
    </div>

</body>
</html>