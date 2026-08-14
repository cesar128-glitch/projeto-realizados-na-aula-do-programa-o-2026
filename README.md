<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Game do Saber - Nossa Escola, Nosso Compromisso</title>
    <style>
        /* Reset e Configurações Gerais */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, Helvetica, sans-serif;
            scroll-behavior: smooth;
        }

        body {
            background-color: #f8fafc;
            color: #334155;
            line-height: 1.6;
        }

        /* Menu de Navegação Fixo */
        nav {
            background-color: #1e3a8a;
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.15);
        }

        .nav-container {
            max-width: 1100px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 20px;
        }

        .logo {
            color: #ffffff;
            font-size: 1.4rem;
            font-weight: bold;
        }

        .nav-links {
            list-style: none;
            display: flex;
            gap: 20px;
        }

        .nav-links a {
            color: #e2e8f0;
            text-decoration: none;
            font-weight: 600;
            transition: color 0.2s;
        }

        .nav-links a:hover {
            color: #60a5fa;
        }

        /* Banner Principal (Hero Section) */
        .hero {
            background: linear-gradient(135deg, #1d4ed8, #3b82f6);
            color: white;
            text-align: center;
            padding: 120px 20px 70px;
        }

        .hero h1 {
            font-size: 2.8rem;
            margin-bottom: 10px;
        }

        .hero p {
            font-size: 1.2rem;
            opacity: 0.9;
        }

        /* Estrutura das Seções */
        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 50px 20px;
        }

        .secao {
            background: #ffffff;
            border-radius: 12px;
            padding: 40px;
            margin-bottom: 40px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.05);
        }

        .titulo-secao {
            color: #1e3a8a;
            font-size: 1.8rem;
            margin-bottom: 20px;
            border-bottom: 3px solid #3b82f6;
            display: inline-block;
            padding-bottom: 5px;
        }

        /* Galeria de Imagens */
        .galeria-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
            margin-top: 20px;
        }

        .card {
            flex: 1 1 300px;
            max-width: 330px;
            background: #f1f5f9;
            border-radius: 10px;
            overflow: hidden;
            border: 1px solid #cbd5e1;
        }

        .card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .card-body {
            padding: 15px;
            text-align: center;
        }

        .card-body h3 {
            color: #1e293b;
            font-size: 1.1rem;
            margin-bottom: 5px;
        }

        /* Lista de Dicas */
        .dicas-lista {
            list-style: none;
            margin-top: 15px;
        }

        .dicas-lista li {
            background: #eff6ff;
            margin-bottom: 10px;
            padding: 15px;
            border-left: 5px solid #3b82f6;
            border-radius: 4px;
            font-weight: 500;
        }

        /* Rodapé */
        footer {
            background-color: #0f172a;
            color: #94a3b8;
            text-align: center;
            padding: 30px 20px;
            font-size: 0.9rem;
        }

        /* Responsividade para celular */
        @media (max-width: 768px) {
            .nav-container {
                flex-direction: column;
                gap: 10px;
            }
            .hero h1 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>

    <nav>
        <div class="nav-container">
            <div class="logo">🎮 Game do Saber</div>
            <ul class="nav-links">
                <li><a href="#inicio">Início</a></li>
                <li><a href="#sobre">Sobre</a></li>
                <li><a href="#galeria">Projetos</a></li>
                <li><a href="#dicas">Como Ajudar</a></li>
            </ul>
        </div>
    </nav>

    <header id="inicio" class="hero">
        <h1>GAME DO SABER</h1>
        <p>NOSSA ESCOLA, NOSSO COMPROMISSO</p>
    </header>

    <main class="container">

        <section id="sobre" class="secao">
            <h2 class="titulo-secao">Sobre o Projeto</h2>
            <p>
                O <strong>Game do Saber</strong> é uma iniciativa criada para conscientizar toda a comunidade escolar sobre a importância do cuidado com o patrimônio público. A escola é um espaço de todos e para todos, e manter nossas instalações bem cuidadas garante um ambiente de aprendizado agradável e motivador.
            </p>
        </section>

        <section id="galeria" class="secao">
            <h2 class="titulo-secao">Antes e Depois das Ações</h2>
            <p style="margin-bottom: 20px;">Confira as melhorias realizadas com o apoio de alunos e funcionários:</p>
            
            <div class="galeria-grid">
                <article class="card">
                    <img src="days.jpeg" alt="Manutenção de Ventiladores">
                    <div class="card-body">
                        <h3>Manutenção dos Ventiladores</h3>
                        <p>Higienização e conserto dos aparelhos das salas de aula.</p>
                    </div>
                </article>

                <article class="card">
                    <img src="5236443161723305068.jpg" alt="Conservação de Ambientes">
                    <div class="card-body">
                        <h3>Manutenção Geral</h3>
                        <p>Ajuste de carteiras, janelas e equipamentos coletivos.</p>
                    </div>
                </article>

                <article class="card">
                    <img src="7278812297501217892.jpg" alt="Revitalização de Espaços">
                    <div class="card-body">
                        <h3>Revitalização dos Espaços</h3>
                        <p>Pintura e organização de áreas de convivência.</p>
                    </div>
                </article>
            </div>
        </section>

        <section id="dicas" class="secao">
            <h2 class="titulo-secao">O Que Você Pode Fazer?</h2>
            <ul class="dicas-lista">
                <li><strong>Cuidado com o mobiliário:</strong> Não risque bancadas, mesas ou paredes.</li>
                <li><strong>Economia de recursos:</strong> Apague as luzes e desligue os ventiladores ao sair da sala.</li>
                <li><strong>Uso consciente:</strong> Mantenha banheiros e áreas comuns limpos e organizados.</li>
                <li><strong>Comunicação:</strong> Viu algo quebrado? Avise a equipe gestora da escola imediatamente.</li>
            </ul>
        </section>

    </main>

    <footer>
        <p>© 2026 Game do Saber - Projeto de Preservação do Patrimônio Escolar.</p>
        <p>Desenvolvido pelos estudantes da nossa escola.</p>
    </footer>

</body>
</html>