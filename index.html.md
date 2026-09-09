```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Happy Birthday Nuri 🎂💖</title>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: Arial, sans-serif;
      background:
        radial-gradient(circle at top, #ff9a9e, transparent 45%),
        linear-gradient(135deg, #a18cd1, #fbc2eb);
      overflow: hidden;
      color: white;
    }

    .container {
      width: 90%;
      max-width: 650px;
      padding: 40px 25px;
      text-align: center;
      background: rgba(255, 255, 255, 0.16);
      backdrop-filter: blur(18px);
      border: 1px solid rgba(255,255,255,0.3);
      border-radius: 28px;
      box-shadow: 0 20px 60px rgba(0,0,0,0.25);
      z-index: 10;
    }

    .top-emoji {
      font-size: 65px;
      animation: bounce 1.5s infinite;
    }

    h1 {
      margin-top: 12px;
      font-size: clamp(38px, 9vw, 70px);
      font-weight: 900;
      background: linear-gradient(
        90deg,
        #fff,
        #ffe066,
        #fff,
        #ffb3c6
      );
      background-size: 250%;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      animation: shine 3s linear infinite;
    }

    h2 {
      margin-top: 8px;
      font-size: clamp(28px, 6vw, 45px);
      text-shadow: 0 4px 15px rgba(0,0,0,0.2);
    }

    .heart {
      font-size: 28px;
      animation: heartbeat 1.2s infinite;
      display: inline-block;
    }

    .cake {
      font-size: 75px;
      margin: 18px 0;
      animation: float 2s ease-in-out infinite;
    }

    .message {
      max-width: 520px;
      margin: auto;
      font-size: clamp(16px, 3vw, 20px);
      line-height: 1.7;
      color: #fff;
    }

    .highlight {
      font-weight: bold;
      color: #fff3a3;
    }

    button {
      margin-top: 25px;
      border: none;
      padding: 14px 30px;
      border-radius: 50px;
      background: white;
      color: #d63384;
      font-size: 17px;
      font-weight: bold;
      cursor: pointer;
      transition: 0.3s;
      box-shadow: 0 8px 25px rgba(0,0,0,0.2);
    }

    button:hover {
      transform: scale(1.08);
      background: #ffe066;
      color: #7b2cbf;
    }

    /* Confetti */

    .confetti {
      position: fixed;
      top: -20px;
      width: 10px;
      height: 10px;
      pointer-events: none;
      z-index: 20;
      animation: fall linear forwards;
    }

    @keyframes fall {
      to {
        transform:
          translateY(110vh)
          rotate(720deg);
        opacity: 0;
      }
    }

    @keyframes bounce {
      0%, 100% {
        transform: translateY(0);
      }

      50% {
        transform: translateY(-15px);
      }
    }

    @keyframes float {
      0%, 100% {
        transform: translateY(0);
      }

      50% {
        transform: translateY(-12px);
      }
    }

    @keyframes heartbeat {
      0%, 100% {
        transform: scale(1);
      }

      50% {
        transform: scale(1.25);
      }
    }

    @keyframes shine {
      0% {
        background-position: 0%;
      }

      100% {
        background-position: 250%;
      }
    }

    /* Mobile */

    @media (max-width: 500px) {

      .container {
        padding: 30px 18px;
        border-radius: 22px;
      }

      .top-emoji {
        font-size: 52px;
      }

      .cake {
        font-size: 60px;
        margin: 15px 0;
      }

      .message {
        font-size: 16px;
        line-height: 1.6;
      }

      button {
        padding: 12px 24px;
        font-size: 15px;
      }
    }
  </style>
</head>

<body>

  <div class="container">

    <div class="top-emoji">🎉</div>

    <h1>Happy Birthday!</h1>

    <h2>
      Nuri <span class="heart">❤️</span>
    </h2>

    <div class="cake">🎂</div>

    <p class="message">
      Today is a very special day because it's
      <span class="highlight">Nuri's Birthday! 🎈</span>
      <br><br>

      Wishing you a beautiful day filled with
      happiness, laughter, wonderful memories
      and lots of smiles. ✨
      <br><br>

      May this new year of your life bring you
      many amazing moments and make your dreams
      come true. 🌸
      <br><br>

      <span class="highlight">
        Happy Birthday, Nuri! 🎂💖
      </span>
    </p>

    <button onclick="celebrate()">
      🎊 Celebrate Again
    </button>

  </div>


  <script>

    function createConfetti() {

      const confetti = document.createElement("div");

      confetti.classList.add("confetti");

      const colors = [
        "#ff4d6d",
        "#ffd166",
        "#06d6a0",
        "#4cc9f0",
        "#ffffff",
        "#ff9f1c",
        "#c77dff",
        "#ff85a1"
      ];

      confetti.style.backgroundColor =
        colors[Math.floor(Math.random() * colors.length)];

      confetti.style.left =
        Math.random() * 100 + "vw";

      confetti.style.width =
        Math.random() * 8 + 5 + "px";

      confetti.style.height =
        Math.random() * 8 + 5 + "px";

      confetti.style.borderRadius =
        Math.random() > 0.5 ? "50%" : "2px";

      confetti.style.animationDuration =
        Math.random() * 3 + 2 + "s";

      document.body.appendChild(confetti);

      setTimeout(() => {
        confetti.remove();
      }, 5500);
    }


    function celebrate() {

      for (let i = 0; i < 150; i++) {

        setTimeout(() => {
          createConfetti();
        }, i * 12);

      }

    }


    // Automatic celebration
    window.onload = () => {
      celebrate();
    };

  </script>

</body>
</html>
```