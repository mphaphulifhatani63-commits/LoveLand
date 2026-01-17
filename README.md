<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Valentine Surprise</title>

  <style>
    /* ===== Body & general ===== */
    body {
      margin: 0;
      padding: 20px;
      font-family: 'Arial', sans-serif;
      background: #fff0f5;
      overflow-x: hidden;
    }

    /* ===== Floating hearts background ===== */
    .hearts {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 0;
    }

    .heart {
      position: absolute;
      bottom: -20px;
      font-size: 20px;
      animation: floatUp 8s linear infinite;
      opacity: 0.7;
    }

    @keyframes floatUp {
      from {
        transform: translateY(0);
        opacity: 0.8;
      }
      to {
        transform: translateY(-110vh);
        opacity: 0;
      }
    }

    /* ===== Card container ===== */
    .card {
      position: relative;
      z-index: 10; /* ensures it's above hearts */
      background: white;
      max-width: 600px;
      margin: 60px auto;
      padding: 30px;
      border-radius: 20px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.1);
      text-align: center;
    }

    /* ===== Image ===== */
    .card img {
      width: 100%;
      max-width: 320px;
      height: auto;
      display: block;
      margin: 0 auto 20px;
      border-radius: 15px;
      object-fit: cover;
    }

    /* ===== Text ===== */
    h1 {
      font-size: 2.5em;
      margin-bottom: 10px;
    }

    p {
      font-size: 1.1em;
      line-height: 1.6;
      margin-bottom: 15px;
    }

    /* ===== Buttons ===== */
    button {
      font-size: 1em;
      padding: 12px 20px;
      margin: 8px;
      border-radius: 25px;
      border: none;
      cursor: pointer;
      transition: transform 0.2s;
    }

    button:hover {
      transform: scale(1.05);
    }

    .yes {
      background-color: #e63946;
      color: white;
    }

    .ofcourse {
      background-color: #ff8fab;
      color: white;
    }

    .no {
      background-color: #ddd;
      color: #555;
    }

    /* ===== Surprise message ===== */
    #surprise {
      opacity: 0;
      transform: translateY(10px);
      margin-top: 30px;
      font-size: 1.4em;
      color: #e63946;
      transition: opacity 1.2s ease, transform 1.2s ease;
    }

    #surprise.show {
      opacity: 1;
      transform: translateY(0);
    }

    /* ===== Mobile responsiveness ===== */
    @media (max-width: 480px) {
      h1 {
        font-size: 1.8em;
      }

      .card {
        padding: 20px;
      }

      .card img {
        max-width: 100%;
      }

      button {
        width: 100%;
        margin: 6px 0;
      }
    }

  </style>
</head>

<body>
  <!-- Floating hearts -->
  <div class="hearts" id="hearts-container"></div>

  <!-- Main card -->
  <div class="card">
    <img src="IMG_0309.jpeg" alt="Valentine">

    <h1>Will you be my Valentine? 💕</h1>

    <p>
      I know I didn’t go about asking you to be my girlfriend the right way,
      but I will live the rest of my life trying to make this up to you.
      So for starters…
    </p>

    <p><strong>Will you be my Valentine?</strong></p>

    <button class="ofcourse" onclick="sayYes()">Of course!</button>
    <button class="no" onclick="moveButton(this)">I’m good thanks</button>
    <button class="yes" onclick="sayYes()">Yes ❤️</button>

    <div id="surprise">
      I love you ❤️ and I want you to know that you are a 
      <strong>planned girlfriend</strong> 💖
    </div>
  </div>

  <script>
    /* ===== Floating hearts script ===== */
    const heartsContainer = document.getElementById('hearts-container');

    function createHeart() {
      const heart = document.createElement('div');
      heart.className = 'heart';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.fontSize = (10 + Math.random() * 20) + 'px';
      heart.innerText = '💖';
      heartsContainer.appendChild(heart);

      setTimeout(() => {
        heartsContainer.removeChild(heart);
      }, 8000);
    }

    setInterval(createHeart, 300);

    /* ===== Button scripts ===== */
    function sayYes() {
      document.getElementById('surprise').classList.add('show');
    }

    function moveButton(btn) {
      const containerWidth = btn.parentElement.offsetWidth;
      const btnWidth = btn.offsetWidth;
      const maxLeft = containerWidth - btnWidth;
      const randomX = Math.random() * maxLeft;
      const randomY = Math.random() * 50;
      btn.style.position = 'relative';
      btn.style.transform = `translate(${randomX}px, -${randomY}px)`;
    }
  </script>
</body>
</html>
