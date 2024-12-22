<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Página de Amor</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #fff;
      color: #333;
    }
    #sparkles {
      position: absolute;
      width: 100%;
      height: 100%;
      pointer-events: none;
      overflow: hidden;
    }
    .sparkle {
      position: absolute;
      width: 5px;
      height: 5px;
      background: gold;
      border-radius: 50%;
      animation: sparkle 1s linear infinite;
    }
    @keyframes sparkle {
      0% {
        opacity: 1;
        transform: scale(1);
      }
      100% {
        opacity: 0;
        transform: scale(3);
      }
    }
    #text {
      display: none;
      margin: 20px auto;
      max-width: 800px;
      font-size: 1.2rem;
      color: #444;
    }
    #arrow {
      display: none;
      font-size: 2rem;
      cursor: pointer;
      margin-top: 20px;
    }
    #background {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: url('https://example.com/andromeda.jpg') no-repeat center center/cover;
      z-index: -1;
    }
    #finalText {
      display: none;
      margin-top: 20px;
      color: red;
      font-size: 1.5rem;
      text-shadow: 1px 1px 2px #000;
    }
    #finalText .heart {
      color: pink;
      font-size: 2rem;
      margin: 0 5px;
    }
  </style>
</head>
<body>
  <div id="sparkles"></div>
  <button id="mainButton">Dale Click</button>
  <div id="text">
    <p>Tu copa nunca estará vacía porque yo seré tu vino, tu plato nunca estará vacío porque yo seré tu pan, tu corazón nunca estará solo porque yo seré tu compañero. Juntos llenaremos cada momento de amor, risas y aventuras. Juntos crearemos un hogar lleno de calor, comprensión y apoyo. Juntos enfrentaremos cada desafío con valentía, sabiduría y amor. Te amo ahora y siempre, mi amor.</p>
    <p>Te amo más que ayer, pero menos que mañana. Te amo hasta la última gota de sangre.</p>
    <div id="arrow">⬇️</div>
  </div>
  <div id="background"></div>
  <div id="finalText">
    <p>Tu piel es pálida, como la luna en el cielo y tus ojos brillan, como estrellas en la noche. Mi corazón late, con un ritmo lento y fuerte, cuando te miro, mi amor, mi sed de ti se despierta. En la oscuridad, nos encontramos, nuestros labios se unen, en un beso eterno.</p>
    <p>Te amo <span class="heart">❤️</span> <span class="heart">❤️</span> <span class="heart">❤️</span></p>
    <p>La sangre late, en nuestras venas y nuestro amor crece, con cada gota que compartimos. Nuestro vínculo es fuerte, como la muerte misma, en la noche eterna, donde las sombras reinan, nuestro amor es un susurro, que solo los muertos escuchan. Aunque el tiempo pase, y el mundo cambie, nuestro amor permanecerá, dibujado en las estrellas, eterno y sin fin.</p>
  </div>

  <script>
    const mainButton = document.getElementById('mainButton');
    const text = document.getElementById('text');
    const arrow = document.getElementById('arrow');
    const background = document.getElementById('background');
    const finalText = document.getElementById('finalText');
    const sparkles = document.getElementById('sparkles');

    function createSparkle(x, y) {
      const sparkle = document.createElement('div');
      sparkle.classList.add('sparkle');
      sparkle.style.left = `${x}px`;
      sparkle.style.top = `${y}px`;
      sparkles.appendChild(sparkle);
      setTimeout(() => sparkle.remove(), 1000);
    }

    mainButton.addEventListener('click', (e) => {
      text.style.display = 'block';
      for (let i = 0; i < 50; i++) {
        const x = Math.random() * window.innerWidth;
        const y = Math.random() * window.innerHeight;
        createSparkle(x, y);
      }
      mainButton.style.display = 'none';
    });

    arrow.addEventListener('click', () => {
      background.style.display = 'block';
      text.style.display = 'none';
      finalText.style.display = 'block';
    });

    text.addEventListener('transitionend', () => {
      arrow.style.display = 'block';
    });
  </script>
</body>
</html>
