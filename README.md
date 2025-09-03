<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Bom dia, meu amor ❤️</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(to top, #fbc2eb, #a6c1ee);
      font-family: 'Arial', sans-serif;
      overflow: hidden;
    }

    .flower {
      position: relative;
      width: 400px;
      height: 400px;
    }

    .petal {
      position: absolute;
      width: 120px;
      height: 200px;
      background: pink;
      border-radius: 60% 60% 0 0;
      transform-origin: bottom center;
      display: flex;
      justify-content: center;
      align-items: center;
      cursor: pointer;
      text-align: center;
      font-weight: bold;
      color: #fff;
      padding: 10px;
      transition: transform 0.5s, opacity 0.5s;
    }

    .petal.clicked {
      background: #ff8fab;
      pointer-events: none;
    }

    .center {
      position: absolute;
      top: 50%;
      left: 50%;
      width: 80px;
      height: 80px;
      background: yellow;
      border-radius: 50%;
      transform: translate(-50%, -50%);
      z-index: 10;
    }

    .heart {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) scale(0);
      font-size: 5em;
      color: red;
      font-weight: bold;
      transition: transform 1s ease-in-out;
      text-align: center;
    }

    .heart.show {
      transform: translate(-50%, -50%) scale(1);
    }
  </style>
</head>
<body>
  <div class="flower">
    <div class="center"></div>
    <!-- 6 pétalas -->
    <div class="petal" data-message="Você é a luz que ilumina meu dia" style="top:0; left:50%; transform:translateX(-50%) rotate(0deg);">Clique aqui</div>
    <div class="petal" data-message="Seu sorriso é meu maior presente" style="top:20%; left:90%; transform:translate(-50%) rotate(60deg);">Clique aqui</div>
    <div class="petal" data-message="Com você, tudo é mais bonito" style="top:60%; left:90%; transform:translate(-50%) rotate(120deg);">Clique aqui</div>
    <div class="petal" data-message="Você é meu melhor pensamento" style="bottom:0; left:50%; transform:translateX(-50%) rotate(180deg);">Clique aqui</div>
    <div class="petal" data-message="Amar você é fácil demais" style="top:60%; left:10%; transform:translate(-50%) rotate(240deg);">Clique aqui</div>
    <div class="petal" data-message="Obrigado por existir na minha vida" style="top:20%; left:10%; transform:translate(-50%) rotate(300deg);">Clique aqui</div>
  </div>

  <div class="heart" id="heart">❤️<br>Bom dia amor, eu te amo!</div>

  <script>
    const petals = document.querySelectorAll('.petal');
    const heart = document.getElementById('heart');
    let clickedCount = 0;

    petals.forEach(petal => {
      petal.addEventListener('click', () => {
        alert(petal.dataset.message); // mostra a frase da pétala
        petal.classList.add('clicked');
        clickedCount++;

        // quando todas forem clicadas
        if (clickedCount === petals.length) {
          setTimeout(() => {
            heart.classList.add('show');
          }, 500);
        }
      });
    });
  </script>
</body>
</html>
