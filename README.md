<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Pour toi 💖</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(#ffe6eb, #fff);
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Georgia', serif;
      overflow: hidden;
    }

    .container {
      text-align: center;
      background: white;
      padding: 40px;
      border-radius: 20px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.1);
      max-width: 360px;
      position: relative;
      z-index: 2;
    }

    img {
      width: 100%;
      border-radius: 15px;
      margin-bottom: 25px;
    }

    h1 {
      color: #c9184a;
      margin-bottom: 30px;
      font-size: 24px;
    }

    button {
      font-size: 18px;
      padding: 14px 30px;
      margin: 10px;
      border-radius: 30px;
      border: none;
      cursor: pointer;
      transition: all 0.4s ease;
    }

    #yes {
      background-color: #ff4d6d;
      color: white;
    }

    #no {
      background-color: #e0e0e0;
      color: #555;
    }

    #yes.big {
      transform: scale(1.7);
    }

    .message {
      margin-top: 25px;
      font-size: 22px;
      color: #c9184a;
      display: none;
      line-height: 1.5;
      font-weight: bold;
    }

    /* Cœurs & fleurs */
    .float {
      position: absolute;
      bottom: -30px;
      font-size: 24px;
      animation: floatUp 5s linear forwards;
      z-index: 1;
    }

    @keyframes floatUp {
      from {
        transform: translateY(0);
        opacity: 1;
      }
      to {
        transform: translateY(-120vh);
        opacity: 0;
      }
    }
  </style>
</head>

<body>

  <div class="container">

    <!-- TA PHOTO -->
    <img src="photo.jpg" alt="Nous deux">

    <!-- QUESTION -->
    <h1>Veux-tu être ma valentine Cassidy 😔 ?</h1>

    <!-- CHOIX -->
    <button id="yes" onclick="yesClick()">Oui ❤️</button>
    <button id="no">Non</button>

    <!-- MESSAGE FINAL -->
    <div class="message" id="msg">
      Mon cœur je t’aime ❤️
    </div>

    <!-- MUSIQUE -->
    <audio id="music">
      <source src="music.mp3" type="audio/mpeg">
    </audio>

  </div>

  <script>
    function yesClick() {
      document.getElementById("yes").classList.add("big");
      document.getElementById("no").style.display = "none";
      document.getElementById("msg").style.display = "block";
      document.getElementById("music").play();
      launchLove();
    }

    function launchLove() {
      const symbols = ["❤️", "🌸", "🌹", "💐", "💖"];

      for (let i = 0; i < 40; i++) {
        const el = document.createElement("div");
        el.className = "float";
        el.innerText = symbols[Math.floor(Math.random() * symbols.length)];
        el.style.left = Math.random() * 100 + "vw";
        el.style.animationDuration = (3 + Math.random() * 3) + "s";
        document.body.appendChild(el);

        setTimeout(() => {
          el.remove();
        }, 6000);
      }
    }
  </script>

</body>
</html>
