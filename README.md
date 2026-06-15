# flashcards-de-estudo-com-HTML-e-CSS<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Projeto: Pseudoclasses e Interações</title>
  
  <style>
    /* ==========================================================================
       1. RESET E CONFIGURAÇÕES GERAIS
       ========================================================================== */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background-color: #f0f3f5;
      color: #2c3e50;
      line-height: 1.6;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 40px 20px;
    }

    header {
      text-align: center;
      margin-bottom: 40px;
      max-width: 600px;
    }

    h1 {
      margin-bottom: 10px;
      color: #1a252f;
    }

    /* Estilo padrão para links do projeto */
    .link-projeto {
      color: #3498db;
      text-decoration: none;
      font-weight: bold;
      transition: color 0.2s;
    }

    /* :visited - Aplicado quando o link já foi clicado */
    .link-projeto:visited {
      color: #9b59b6; /* Muda para roxo sutil */
    }


    /* ==========================================================================
       2. O CARD 3D (Uso de :hover e :focus-within)
       ========================================================================== */
    .cartao {
      background-color: transparent;
      width: 300px;
      height: 200px;
      perspective: 1000px; /* Cria o efeito de profundidade 3D */
      margin-bottom: 30px;
    }

    .cartao-interno {
      position: relative;
      width: 100%;
      height: 100%;
      text-align: center;
      transition: transform 0.6s;
      transform-style: preserve-3d;
    }

    /* :hover - Gira o card quando o mouse passa por cima */
    .cartao:hover .cartao-interno {
      transform: rotateY(180deg);
    }

    /* :focus-within - Gira o card quando o link dentro dele ganha foco (via TAB) */
    .cartao:focus-within .cartao-interno {
      transform: rotateY(180deg);
    }

    /* Faces do Card */
    .face-frente, .face-verso {
      position: absolute;
      width: 100%;
      height: 100%;
      backface-visibility: hidden; /* Esconde a face oposta */
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      border-radius: 12px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
      padding: 20px;
    }

    .face-frente {
      background-color: #34495e;
      color: white;
    }

    .face-verso {
      background-color: #2ecc71;
      color: white;
      transform: rotateY(180deg); /* Já começa invertido */
    }


    /* ==========================================================================
       3. BOTÃO INTERATIVO (Uso de :hover, :focus e :active)
       ========================================================================== */
    .botao-interativo {
      background-color: #3498db;
      color: white;
      border: none;
      padding: 12px 24px;
      font-size: 1rem;
      font-weight: bold;
      border-radius: 8px;
      cursor: pointer;
      box-shadow: 0 4px 6px rgba(52, 152, 219, 0.2);
      
      /* Suaviza as transições de cor e sombra */
      transition: background-color 0.2s, transform 0.1s, box-shadow 0.2s;
      outline: none; /* Remove o contorno padrão para fazermos o nosso */
    }

    /* :hover - Mouse por cima do botão */
    .botao-interativo:hover {
      background-color: #2980b9; /* Escurece o azul */
    }

    /* :focus - Navegação via teclado (Tab) */
    .botao-interativo:focus {
      box-shadow: 0 0 0 4px #74b9ff; /* Cria uma "aura" azul de destaque */
    }

    /* :active - No exato momento do clique */
    .botao-interativo:active {
      background-color: #1f618d; /* Fica ainda mais escuro */
      transform: scale(0.98);    /* Dá um leve efeito de "afundar" */
    }

    /* Espaçador simples */
    .instrucoes {
      margin-top: 20px;
      font-size: 0.9rem;
      color: #7f8c8d;
      text-align: center;
    }
  </style>
</head>
<body>

  <header>
    <h1>Laboratório de Pseudoclasses</h1>
    <p>Interações visuais trazem vida e dão respostas imediatas para quem usa a página.</p>
  </header>

  <div class="cartao">
    <div class="cartao-interno">
      <div class="face-frente">
        <h3>Passe o mouse aqui</h3>
        <p>(Ou use o Tab no teclado)</p>
      </div>
      <div class="face-verso">
        <h3>Olha o <code>:focus-within</code>!</h3>
        <p>Você chegou aqui através deste <a href="https://example.com" target="_blank" class="link-projeto">Link de Teste</a>.</p>
      </div>
    </div>
  </div>

  <button class="botao-interativo">
    Clique em Mim
  </button>

  <div class="instrucoes">
    <p><strong>Como testar tudo:</strong></p>
    <p>1. Passe o mouse no card para ver o <code>:hover</code>.</p>
    <p>2. Clique e segure o botão azul para ver o <code>:active</code>.</p>
    <p>3. Pressione a tecla <strong>TAB</strong> no seu teclado para ver o <code>:focus</code> no botão e o <code>:focus-within</code> virar o card.</p>
  </div>

</body>
</html>
