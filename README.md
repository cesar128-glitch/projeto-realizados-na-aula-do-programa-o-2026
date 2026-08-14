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
        /* Reset e Fontes */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #f4f7f6;
            color: #333;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }

        #container {
            max-width: 900px;
            width: 100%;
            background: #ffffff;
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        /* Cabeçalho */
        header h1 {
            color: #1e3c72;
            font-size: 2.5rem;
            margin-bottom: 5px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        header .subtitle {
            font-weight: bold;
            color: #2a5298;
            margin-bottom: 25px;
            font-size: 1.1rem;
        }

        .question {
            background-color: #eef2f5;
            padding: 15px;
            border-radius: 8px;
            font-weight: bold;
            color: #444;
            margin-bottom: 30px;
            border-left: 5px solid #1e3c72;
        }

        /* Seção de Galeria de Impacto (Cards) */
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            margin-bottom: 30px;
        }

        .card {
            background: #fff;
            border: 1px solid #e0e0e0;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 10px rgba(0,0,0,0.05);
            transition: transform 0.2s ease;
        }

        .card:hover {
            transform: translateY(-5px);
        }

        .card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .card figcaption {
            padding: 15px;
            font-weight: bold;
            color: #333;
            background-color: #fafafa;
        }

        /* Mensagem Final */
        .footer-text {
            line-height: 1.6;
            font-size: 1.05rem;
            color: #555;
            margin-top: 20px;
        }

        .highlight {
            font-weight: bold;
            color: #1e3c72;
        }
    </style>
</head>

<body>

    <div id="container">

        <header>
            <h1>GAME DO SABER</h1>
            <p class="subtitle">NOSSA ESCOLA, NOSSO COMPROMISSO</p>
        </header>

        <div class="question">
            <u>O QUE NÓS PODEMOS FAZER PARA TORNAR NOSSA ESCOLA AINDA MELHOR?</u>
        </div>

        <section class="gallery">
            <figure class="card">
                <img src="days.jpeg" alt="Antes e depois do ventilador">
                <figcaption>Antes e depois: "Ventilador"</figcaption>
            </figure>

            <figure class="card">
                <img src="5236443161723305068.jpg" alt="Ação de melhoria na escola">
                <figcaption>Antes e depois: Manutenção</figcaption>
            </figure>

            <figure class="card">
                <img src="7278812297501217892.jpg" alt="Cuidado com o espaço escolar">
                <figcaption>Antes e depois: Espaço Renovado</figcaption>
            </figure>
        </section>

        <footer>
            <p class="footer-text">
                O <span class="highlight">cuidado com o patrimônio da escola</span> é responsabilidade de todos os estudantes e funcionários.<br>
                Os bens duráveis são importantes para o desenvolvimento dos alunos e geram um ambiente muito melhor para todos!
            </p>
        </footer>

    </div>

</body>
</html>