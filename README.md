<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Game do Saber</title>
    <style>
        /* Reset simples */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, Helvetica, sans-serif;
        }

        body {
            background-color: #eef2f5;
            color: #333333;
            display: flex;
            justify-content: center;
            padding: 20px;
        }

        /* Cartão principal da página */
        .site-wrapper {
            max-width: 850px;
            width: 100%;
            background-color: #ffffff;
            border-radius: 12px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
            padding: 30px;
            text-align: center;
        }

        header {
            margin-bottom: 25px;
        }

        h1 {
            color: #1d4ed8;
            font-size: 2.2rem;
            letter-spacing: 1px;
        }

        .subtitulo {
            color: #3b82f6;
            font-size: 1.1rem;
            font-weight: 600;
            margin-top: 5px;
        }

        .banner-pergunta {
            background-color: #eff6ff;
            border: 2px solid #93c5fd;
            color: #1e40af;
            padding: 15px;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: bold;
            margin-bottom: 30px;
        }

        /* Galeria que se ajusta sozinha sem quebrar */
        .galeria {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
            margin-bottom: 30px;
        }

        .card {
            flex: 1 1 220px;
            max-width: 250px;
            background-color: #f8fafc;
            border: 1px solid #e2e8f0;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.04);
        }

        .card img {
            width: 100%;
            height: 170px;
            object-fit: cover;
            display: block;
        }

        .card p {
            padding: 12px;
            font-weight: 600;
            font-size: 0.9rem;
            color: #1e293b;
        }

        footer {
            border-top: 1px solid #e2e8f0;
            padding-top: 20px;
        }

        footer p {
            color: #475569;
            line-height: 1.6;
            font-size: 0.95rem;
        }
    </style>
</head>
<body>

    <div class="site-wrapper">
        <header>
            <h1>GAME DO SABER</h1>
            <p class="subtitulo">NOSSA ESCOLA, NOSSO COMPROMISSO</p>
        </header>

        <div class="banner-pergunta">
            O QUE NÓS PODEMOS FAZER PARA TORNAR A NOSSA ESCOLA AINDA MELHOR?
        </div>

        <main class="galeria">
            <article class="card">
                <img src="days.jpeg" alt="Antes e depois do ventilador">
                <p>Antes e depois: Ventilador</p>
            </article>

            <article class="card">
                <img src="5236443161723305068.jpg" alt="Antes e depois da manutenção">
                <p>Antes e depois: Manutenção</p>
            </article>

            <article class="card">
                <img src="7278812297501217892.jpg" alt="Antes e depois da conservação">
                <p>Antes e depois: Conservação</p>
            </article>
        </main>

        <footer>
            <p>
                O cuidado com o patrimônio da escola é responsabilidade de todos os estudantes e funcionários.
                Os bens duráveis são importantes para o desenvolvimento dos estudantes e geram um ambiente melhor para todos!
            </p>
        </footer>
    </div>

</body>
</html>