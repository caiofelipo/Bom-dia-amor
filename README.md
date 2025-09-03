
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Lírio do Amor 🌸</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(to top, #fff0f5, #ffe4e1);
      font-family: 'Arial', sans-serif;
    }

    .flower {
      position: relative;
      width: 450px;
      height: 450px;
    }

    .petal {
      position: absolute;
      width: 140px;
      height: 220px;
      background: #ffb6c1;
      border-radius: 50% 50% 0 0;
      transform-origin: bottom center;
      display: flex;
      justify-content: center;
      align-items: center;
      cursor: pointer;
      text-align: center;
      font-weight: bold;
      color: #5a2d2d;
      transition: transform 0.5s, opacity 0.5s, background 0.3s;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }

    .petal:hover {
      background: #ff8fa3;
    }

    .petal.clicked {
      background: #d46a6a;
      color: #fff;
      pointer-events: none;
    }

    .center {
      position: absolute;
      top: 50%;
      left: 50%;
      width: 100px;
      height: 100px;
      background: #ffd700;
      border-radius: 50%;
      transform: translate(-50%, -50%);
      z-index: 10;
      box-shadow: 0 0 15px rgba(0,0,0,0.2);
    }
  </style>
</head>
<body>
  <div class="flower">
    <div class="center"></div>
    <!-- pétalas -->
    <div class="petal" data-message="Você é minha alegria" style="top:0; left:50%; transform:translateX(-50%) rotate(0deg);">Clique aqui</div>
    <div class="petal" data-message="Meu coração é seu" style="top:15%; left:90%; transform:translate(-50%) rotate(60deg);">Clique aqui</div>
    <div class="petal" data-message="Ao seu lado tudo é paz" style="top:55%; left:90%; transform:translate(-50%) rotate(120deg);">Clique aqui</div>
    <div class="petal" data-message="Você é meu sonho bom" style="bottom:0; left:50%; transform:translateX(-50%) rotate(180deg);">Clique aqui</div>
    <div class="petal" data-message="Te amar é viver" style="top:55%; left:10%; transform:translate(-50%) rotate(240deg);">Clique aqui</div>
    <div class="petal" data-message="Você é meu sempre" style="top:15%; left:10%; transform:translate(-50%) rotate(300deg);">Clique aqui</div>
  </div>

  <script>
    const petals = document.querySelectorAll('.petal');
    let clickedCount = 0;

    petals.forEach(petal => {
      petal.addEventListener('click', () => {
        alert(petal.dataset.message); // mostra a frase
        petal.classList.add('clicked');
        clickedCount++;

        // quando todas forem clicadas, vai para outra página
        if (clickedCount === petals.length) {
          setTimeout(() => {
            window.location.href = "bomdia.html";
          }, 800);
        }
      });
    });
  </script>
</body>
</html>
