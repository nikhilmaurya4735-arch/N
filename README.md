<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Proposal for You ❤️</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(270deg, #ff9a9e, #fad0c4, #fbc2eb, #a1c4fd, #c2e9fb);
      background-size: 1000% 1000%;
      animation: bgMove 20s ease infinite;
      overflow: hidden;
      font-family: 'Comic Sans MS', cursive, sans-serif;
    }

    @keyframes bgMove {
      0% {background-position: 0% 50%;}
      50% {background-position: 100% 50%;}
      100% {background-position: 0% 50%;}
    }

    .container {
      text-align: center;
      color: white;
      z-index: 2;
      animation: fadeIn 2s ease-in-out;
    }

    @keyframes fadeIn {
      from {opacity: 0; transform: scale(0.8);}
      to {opacity: 1; transform: scale(1);}
    }

    h1 {
      font-size: 3em;
      text-shadow: 0 0 15px #ff4b2b, 0 0 25px #ff416c;
      animation: pulse 2s infinite alternate;
    }

    @keyframes pulse {
      from {transform: scale(1);}
      to {transform: scale(1.1);}
    }

    .buttons {
      margin-top: 30px;
    }

    .btn {
      padding: 15px 30px;
      margin: 10px;
      font-size: 1.2em;
      border: none;
      border-radius: 30px;
      cursor: pointer;
      transition: 0.3s;
      color: white;
      box-shadow: 0 0 10px rgba(255,255,255,0.6);
    }

    .yes {
      background: linear-gradient(45deg, #ff416c, #ff4b2b);
    }

    .no {
      background: linear-gradient(45deg, #6a11cb, #2575fc);
    }

    .btn:hover {
      transform: scale(1.2) rotate(-2deg);
      box-shadow: 0 0 25px white;
    }

    .message {
      font-size: 2em;
      margin-top: 20px;
      display: none;
    }

    /* Fireworks */
    .firework {
      position: absolute;
      width: 5px;
      height: 5px;
      background: white;
      border-radius: 50%;
      animation: explode 1s ease-out forwards;
    }

    @keyframes explode {
      from {transform: scale(1); opacity: 1;}
      to {transform: scale(3); opacity: 0;}
    }
  </style>
</head>
<body>
  <div class="container" id="proposal">
    <h1>Will You Be Mine Forever? 💖</h1>
    <div class="buttons">
      <button class="btn yes" onclick="sayYes()">Yes 💕</button>
      <button class="btn no" onclick="sayNo()">No 😢</button>
    </div>
    <div class="message" id="message"></div>
  </div>

  <script>
    function sayYes() {
      document.getElementById("message").style.display = "block";
      document.getElementById("message").innerHTML = "Yay! You said YES! 🎉💖";
      launchFireworks();
    }

    function sayNo() {
      document.getElementById("message").style.display = "block";
      document.getElementById("message").innerHTML = "Oh no... 😢 But I’ll still love you ❤️";
    }

    function launchFireworks() {
      for (let i = 0; i < 30; i++) {
        let firework = document.createElement("div");
        firework.className = "firework";
        firework.style.left = Math.random() * window.innerWidth + "px";
        firework.style.top = Math.random() * window.innerHeight + "px";
        firework.style.background = getRandomColor();
        document.body.appendChild(firework);

        setTimeout(() => { firework.remove(); }, 1000);
      }
    }

    function getRandomColor() {
      const colors = ["#ff4b2b", "#ff416c", "#ffd700", "#00ffcc", "#ff69b4", "#00bfff"];
      return colors[Math.floor(Math.random() * colors.length)];
    }
  </script>
</body>
</html>
