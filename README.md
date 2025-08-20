# Time-together
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Z ❤️ E Forever</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      overflow: hidden;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      font-family: 'Segoe UI', sans-serif;
      background: radial-gradient(ellipse at bottom, #0a0f1f 0%, #000 100%);
      color: white;
      text-align: center;
      position: relative;
    }

    h1 {
      font-size: 2.5em;
      margin-bottom: 20px;
      text-shadow: 0 0 20px #ff99cc, 0 0 40px #ff4d94;
      z-index: 2;
    }

    #timer {
      font-size: 1.6em;
      font-weight: bold;
      text-shadow: 0 0 15px #ffccff, 0 0 30px #ff66b2;
      z-index: 2;
    }

    /* Moon */
    .moon {
      position: absolute;
      top: 40px;
      right: 80px;
      width: 100px;
      height: 100px;
      background: radial-gradient(circle at 30% 30%, #fff, #ddd);
      border-radius: 50%;
      box-shadow: 0 0 40px #fff, 0 0 80px #ccc;
    }

    /* Stars */
    .star {
      position: absolute;
      width: 2px;
      height: 2px;
      background: white;
      border-radius: 50%;
      animation: twinkle 2s infinite alternate;
    }

    @keyframes twinkle {
      from { opacity: 0.2; }
      to { opacity: 1; }
    }

    /* Roses at bottom */
    .roses {
      position: absolute;
      bottom: 0;
      width: 100%;
      height: 180px;
      background-image: url('https://i.ibb.co/dGr5g5W/roses.png');
      background-size: cover;
      background-repeat: repeat-x;
      z-index: 1;
    }

    /* Floating hearts */
    .heart {
      position: absolute;
      bottom: -50px;
      width: 20px;
      height: 20px;
      background: red;
      transform: rotate(45deg);
      animation: floatUp 8s linear infinite;
      z-index: 2;
    }

    .heart::before, .heart::after {
      content: "";
      position: absolute;
      width: 20px;
      height: 20px;
      background: inherit;
      border-radius: 50%;
    }

    .heart::before { top: -10px; left: 0; }
    .heart::after { left: -10px; top: 0; }

    @keyframes floatUp {
      0% { transform: translateY(0) scale(0.6) rotate(45deg); opacity: 1; }
      100% { transform: translateY(-110vh) scale(1) rotate(45deg); opacity: 0; }
    }

    /* Glowing text */
    #loveLetters {
      position: absolute;
      top: 20px;
      font-size: 2em;
      font-weight: bold;
      text-shadow: 0 0 10px #ff6699, 0 0 20px #ff99cc;
      animation: glow 3s infinite alternate;
      z-index: 2;
    }

    @keyframes glow {
      from { text-shadow: 0 0 10px #ff6699, 0 0 20px #ff99cc; }
      to { text-shadow: 0 0 20px #ff3366, 0 0 40px #ff66b2; }
    }
  </style>
</head>
<body>
  <div id="loveLetters">Z ❤️ E</div>
  <div class="moon"></div>
  <h1>Our Journey Together</h1>
  <div id="timer"></div>
  <div class="roses"></div>

  <script>
    // Start date and time
    const startDate = new Date("January 28, 2025 16:30:00").getTime();

    function updateTimer() {
      const now = new Date().getTime();
      const distance = now - startDate;

      const days = Math.floor(distance / (1000 * 60 * 60 * 24));
      const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((distance % (1000 * 60)) / 1000);

      document.getElementById("timer").innerHTML =
        days + " Days " + hours + " Hours " + minutes + " Minutes " + seconds + " Seconds ";
    }
    setInterval(updateTimer, 1000);

    // Floating hearts
    function createHeart() {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.background = ["red", "pink", "white"][Math.floor(Math.random() * 3)];
      heart.style.animationDuration = (5 + Math.random() * 5) + "s";
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 10000);
    }
    setInterval(createHeart, 700);

    // Stars
    function createStar() {
      const star = document.createElement("div");
      star.className = "star";
      star.style.top = Math.random() * 50 + "vh";
      star.style.left = Math.random() * 100 + "vw";
      star.style.animationDuration = (1 + Math.random() * 3) + "s";
      document.body.appendChild(star);
    }
    for (let i = 0; i < 50; i++) createStar();
  </script>
</body>
</html>
