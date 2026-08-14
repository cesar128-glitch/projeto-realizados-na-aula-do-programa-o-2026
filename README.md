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
    <title>Game do Saber</title>
    
    <style>
        /* Reset Básico */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
        }

        body {
            background-color: #f0f2f5;
            color: #1c1e21;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }

        /* Card Principal */
        main {
            background-color: #ffffff;
            max-width: 900px;
            width: 100%;
            padding: 40px;
            border-radius: 12px;
            box-shadow: 0 4px 16px rgba(0, 0, 0, 0.08);
            text-align: center;
        }

        /* Cabeçalho */
        header {
            margin-bottom: 25px;
        }

        h1 {
            color: #0d47a1;
            font-size: 2.2rem;
            margin-bottom: 8px;
            text-transform: uppercase;
        }

        .subtitulo {
            color: #1565c0;
            font-weight: 600;
            font-size: 1.1rem;
            letter-spacing: 0.5px;
        }

        .pergunta-chave {
            background-color: #e3f2fd;
            border-left: 4px solid #1565c0;
            padding: 15px;
            border-radius: 6px;
            margin-bottom: 30px;
            font-weight: bold;
            color: #0d47a1;
        }

        /* Galeria de Fotos */
        .galeria {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .card-foto {
            background-color: #fafafa;
            border: 1px solid #e0e0e0;
            border-radius: 8px;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            transition: transform 0.2s ease, box-shadow 0.2s ease;
        }

        .card-foto:hover {
            transform: translateY(-4px);
            box-shadow: 0 6px 12px rgba(0,0,0,0.1);
        }

        .card-foto img {
            width: 100%;
            height: 220px;
            object-fit: cover; /* Mantém a proporção da imagem sem esticar */
            display: block;
        }

        .card-foto figcaption {
            padding: 12px;
            font-weight: 600;
            color: #424242;
            font-size: 0.95rem;
        }

        /* Rodapé com Mensagem */
        footer p {
            line-height: 1.6;
            color: #555555;
            font-size: 1rem;
        }

        footer strong {
            color: #0d47a1;
        }
    </style>
</head>

<body>

    <main>
        <header>
            <h1>Game do Saber</h1>
            <p class="subtitulo">NOSSA ESCOLA, NOSSO COMPROMISSO</p>
        </header>

        <div class="pergunta-chave">
            O QUE NÓS PODEMOS FAZER PARA TORNAR A NOSSA ESCOLA AINDA MELHOR?
        </div>

        <section class="galeria">
            <figure class="card-foto">
                <img src="days.jpeg" alt="Antes e depois da manutenção do ventilador">
                <figcaption>Antes e depois: Ventilador</figcaption>
            </figure>

            <figure class="card-foto">
                <img src="5236443161723305068.jpg" alt="Ação de melhoria e conservação do espaço escolar">
                <figcaption>Antes e depois: Conservação</figcaption>
            </figure>

            <figure class="card-foto">
                <img src="7278812297501217892.jpg" alt="Revitalização do património escolar">
                <figcaption>Antes e depois: Revitalização</figcaption>
            </figure>
        </section>

        <footer>
            <p>
                O <strong>cuidado com o património da escola</strong> é responsabilidade de todos os estudantes e funcionários. 
                Os bens duradouros são fundamentais para o desenvolvimento de todos e garantem um ambiente escolar muito melhor!
            </p>
        </footer>
    </main>

</body>
</html>