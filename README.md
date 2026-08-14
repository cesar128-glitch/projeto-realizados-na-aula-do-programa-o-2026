<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GAME DO SABER</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, Helvetica, sans-serif;
        }

        body {
            background-color: #f0f2f5;
            padding: 20px;
            display: flex;
            justify-content: center;
        }

        .main-card {
            max-width: 900px;
            width: 100%;
            background: #ffffff;
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            text-align: center;
        }

        h1 {
            color: #1a365d;
            font-size: 2rem;
            margin-bottom: 5px;
        }

        .subtitulo {
            color: #2b6cb0;
            font-weight: bold;
            margin-bottom: 20px;
        }

        .pergunta {
            background-color: #ebf8ff;
            border-left: 5px solid #3182ce;
            padding: 15px;
            border-radius: 6px;
            margin-bottom: 30px;
            font-weight: bold;
            color: #2b6cb0;
        }

        .galeria-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .card-item {
            background: #fafafa;
            border: 1px solid #e2e8f0;
            border-radius: 8px;
            padding: 12px;
        }

        .card-item img {
            width: 100%;
            height: 180px;
            object-fit: cover;
            border-radius: 6px;
            display: block;
        }

        .card-item p {
            margin-top: 10px;
            font-size: 0.9rem;
            font-weight: bold;
            color: #2d3748;
        }

        .texto-final {
            line-height: 1.6;
            color: #4a5568;
            font-size: 1rem;
        }
    </style>
</head>
<body>

    <div class="main-card">
        <h1>GAME DO SABER</h1>
        <p class="subtitulo">NOSSA ESCOLA, NOSSO COMPROMISSO</p>

        <div class="pergunta">
            O QUE NÓS PODEMOS FAZER PARA TORNAR NOSSA ESCOLA AINDA MELHOR?
        </div>

        <div class="galeria-grid">
            <div class="card-item">
                <img src="days.jpeg" alt="Ventilador">
                <p>Antes e depois: Ventilador</p>
            </div>

            <div class="card-item">
                <img src="5236443161723305068.jpg" alt="Manutenção">
                <p>Antes e depois: Manutenção</p>
            </div>

            <div class="card-item">
                <img src="7278812297501217892.jpg" alt="Conservação">
                <p>Antes e depois: Conservação</p>
            </div>
        </div>

        <p class="texto-final">
            O cuidado com o patrimônio da escola é responsabilidade de todos os estudantes e funcionários.
            Os bens duráveis são importantes para o desenvolvimento dos estudantes e geram um ambiente melhor para todos!
        </p>
    </div>

</body>
</html>