To: The love of my Life❤️

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>My Valentine 💖</title>
  <style>
    body {
      font-family: 'Georgia', serif;
      background: linear-gradient(to bottom, #ffd6e8, #fff);
      text-align: center;
      padding: 40px;
      color: #4a2c2a;
      overflow: hidden;
    }

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

    .card {
      position: relative;
      z-index: 1;
      background: white;
      max-width: 600px;
      margin: auto;
      padding: 30px;
      border-radius: 20px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.1);
    }

    img {
      width: 100%;
      border-radius: 15px;
      margin-bottom: 20px;
      object-fit: cover;
    }

    h1 {
      font-size: 2.5em;
      margin-bottom: 10px;
    }

    p {
      font-size: 1.1em;
      line-height: 1.6;
      margin-bottom: 25px;
    }

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
  </style>
</head>
<body>

  <!-- Floating Hearts -->
  <div class="hearts" id="hearts"></div>

  <div class="card">
    <img src="IMG_0309.jpeg" alt="Us 💕">

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
    function sayYes() {
      const surprise = document.getElementById("surprise");
      setTimeout(() => {
        surprise.classList.add("show");
      }, 100);
    }

    function moveButton(btn) {
      btn.style.position = "absolute";
      btn.style.top = Math.random() * 80 + "%";
      btn.style.left = Math.random() * 80 + "%";
    }

    const heartsContainer = document.getElementById("hearts");

    function createHeart() {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.innerHTML = "❤️";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = Math.random() * 4 + 6 + "s";
      heart.style.fontSize = Math.random() * 10 + 15 + "px";

      heartsContainer.appendChild(heart);

      setTimeout(() => heart.remove(), 10000);
    }

    setInterval(createHeart, 500);
  </script>

</body>
</html>
