<!DOCTYPE html>
<html lang="pt-br">

<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GAME-SABER</title>
<link rel="stylesheet" href="style.css">

<style>
div {
height: 100vh;
display: flex;
align-items: center;
justify-content: center;
text-align: center;
}

img {
width: 30%;
}


</style>

</head>

<body>

<div id="container">

<h1><b><u> GAME DO SABER </u></b></h1>
<p>NOSSA ESCOLA NOSSO COMPROMISSO</p>
<p style="text-align: center;"> <u>O QUE NÓS PODEMOS FAZER PARA TORNAR NOSSA ESCOLA AINDA MELHOR?</u></p>

<figure>
<img src="days.jpeg">
<figcaption><b>antes e depois - "ventilador"</b></figcaption>
</figure>

<p style="text-align: center;"> O cuidade com o patrimônio da escola é responsabilidade <br>
de todos os estudantes e funcionários, os bens duráveis são importantes para o desenvolvimento <br>
dos estudantes e gera um ambiente melhor para todos os envolvidos.</p>


</div>
</body>
</html>
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GAME DO SABER</title>
    <style>
        /* Reset para limpar formatações antigas */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            background-color: #f4f4f9;
            padding: 20px;
            display: flex;
            justify-content: center;
        }

        /* Cartão principal do site */
        .container {
            max-width: 850px;
            width: 100%;
            background: #ffffff;
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
            text-align: center;
        }

        h1 {
            color: #1a365d;
            margin-bottom: 5px;
        }

        .subtitulo {
            color: #2b6cb0;
            font-weight: bold;
            margin-bottom: 20px;
        }

        .pergunta {
            background-color: #ebf8ff;
            border: 2px solid #3182ce;
            padding: 12px;
            border-radius: 8px;
            margin-bottom: 25px;
            font-weight: bold;
            color: #2b6cb0;
        }

        /* Alinhamento das imagens */
        .galeria {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
            margin-bottom: 25px;
        }

        .card {
            flex: 1 1 230px;
            background: #fafafa;
            border: 1px solid #ddd;
            border-radius: 8px;
            padding: 10px;
        }

        /* Evita que a foto estoure a tela */
        .card img {
            width: 100%;
            height: 180px;
            object-fit: cover;
            border-radius: 5px;
        }

        .card p {
            margin-top: 8px;
            font-size: 0.9rem;
            font-weight: bold;
            color: #333;
        }

        .texto-final {
            line-height: 1.6;
            color: #4a5568;
            font-size: 1rem;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>GAME DO SABER</h1>
        <p class="subtitulo">NOSSA ESCOLA, NOSSO COMPROMISSO</p>

        <div class="pergunta">
            O QUE NÓS PODEMOS FAZER PARA TORNAR NOSSA ESCOLA AINDA MELHOR?
        </div>

        <div class="galeria">
            <div class="card">
                <img src="days.jpeg" alt="Ventilador">
                <p>Antes e depois: Ventilador</p>
            </div>

            <div class="card">
                <img src="5236443161723305068.jpg" alt="Manutenção">
                <p>Antes e depois: Manutenção</p>
            </div>

            <div class="card">
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