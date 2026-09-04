<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Crush Mo Si Ayns? 💗</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: "Poppins", Arial, sans-serif;
      background: linear-gradient(135deg, #ffd6e7, #e8d7ff);
      overflow: hidden;
    }

    .container {
      width: 90%;
      max-width: 430px;
      background: white;
      padding: 35px 25px;
      border-radius: 25px;
      text-align: center;
      box-shadow: 0 15px 40px rgba(0,0,0,0.15);
      position: relative;
      z-index: 2;
    }

    h1 {
      color: #ff4f91;
      margin-bottom: 10px;
    }

    p {
      color: #555;
      font-size: 16px;
    }

    button {
      border: none;
      padding: 13px 25px;
      margin: 10px 5px;
      border-radius: 30px;
      font-size: 16px;
      cursor: pointer;
      transition: 0.2s;
    }

    button:hover {
      transform: scale(1.08);
    }

    .yes {
      background: #ff4f91;
      color: white;
    }

    .no {
      background: #eee;
      color: #555;
    }

    .reason-container {
      display: none;
      margin-top: 20px;
    }

    select {
      width: 100%;
      padding: 13px;
      border-radius: 12px;
      border: 2px solid #ffc1d8;
      font-size: 15px;
      margin-top: 10px;
      outline: none;
    }

    .done {
      background: #9b5de5;
      color: white;
      display: none;
      margin-top: 15px;
    }

    .message {
      display: none;
      margin-top: 20px;
      font-size: 18px;
      color: #ff4f91;
      font-weight: bold;
    }

    .heart {
      position: fixed;
      bottom: -20px;
      font-size: 25px;
      animation: float 5s linear infinite;
      opacity: 0.7;
    }

    @keyframes float {
      from {
        transform: translateY(0) rotate(0deg);
        opacity: 0.8;
      }
      to {
        transform: translateY(-110vh) rotate(360deg);
        opacity: 0;
      }
    }
  </style>
</head>

<body>

  <div class="container">

    <div id="question">
      <h1>Crush mo si Ayns?? 💗</h1>
      <p>Be honest haaa 👀</p>

      <button class="yes" onclick="sayYes()">YES 💕</button>
      <button class="no" onclick="sayNo()">NO 😭</button>
    </div>

    <div class="reason-container" id="reasonBox">
      <h2>Why naman? 😭</h2>
      <p>
        Choose your reason... pero pag-isipan mo mabuti 😤
      </p>

      <select id="reason" onchange="checkReason()">
        <option value="">-- Choose a reason --</option>
        <option value="cute">Hindi kasi... super cute ni Ayns 😭💗</option>
        <option value="handsome">Hindi kasi... super handsome ni Ayns 😭✨</option>
        <option value="shy">Nahihiya lang ako umamin 👉👈</option>
        <option value="notyet">Hindi pa... pero baka soon 👀</option>
        <option value="secret">Secret muna 🤫</option>
      </select>

      <button class="done" id="doneBtn" onclick="finishNo()">
        DONE 💗
      </button>
    </div>

    <div class="message" id="message"></div>

  </div>

  <script>
    function sayYes() {
      document.getElementById("question").style.display = "none";

      const message = document.getElementById("message");
      message.innerHTML = `
        AYYYYY 😳💗<br><br>
        Crush mo pala si Ayns!!<br>
        Alam ko na ehhh HAHAHA 😭💕<br><br>
        <span style="font-size:30px;">💗💗💗</span>
      `;
      message.style.display = "block";

      createHearts();
    }

    function sayNo() {
      document.getElementById("question").style.display = "none";
      document.getElementById("reasonBox").style.display = "block";
    }

    function checkReason() {
      const reason = document.getElementById("reason").value;
      const doneBtn = document.getElementById("doneBtn");

      if (reason !== "") {
        doneBtn.style.display = "inline-block";
      } else {
        doneBtn.style.display = "none";
      }
    }

    function finishNo() {
      const reason = document.getElementById("reason").value;
      const message = document.getElementById("message");

      document.getElementById("reasonBox").style.display = "none";

      let text = "";

      if (reason === "cute") {
        text = "Super cute talaga ni Ayns ehhh 😭💗";
      } else if (reason === "handsome") {
        text = "Super handsome talaga ni Ayns 😭✨";
      } else if (reason === "shy") {
        text = "Ayyy nahihiya lang palaaa 👉👈💗";
      } else if (reason === "notyet") {
        text = "OHHH baka may chance pa pala 👀💕";
      } else if (reason === "secret") {
        text = "SECRET?! Hmmmmm suspicious 😏💗";
      }

      message.innerHTML = `
        ${text}<br><br>
        Okayyy, noted! 😭💕<br>
        <span style="font-size:30px;">💗✨🥹</span>
      `;

      message.style.display = "block";
      createHearts();
    }

    function createHearts() {
      for (let i = 0; i < 20; i++) {
        const heart = document.createElement("div");

        heart.className = "heart";
        heart.innerHTML = ["💗", "💕", "💖", "❤️", "✨"][Math.floor(Math.random() * 5)];

        heart.style.left = Math.random() * 100 + "vw";
        heart.style.animationDelay = Math.random() * 3 + "s";
        heart.style.animationDuration = (3 + Math.random() * 4) + "s";

        document.body.appendChild(heart);

        setTimeout(() => {
          heart.remove();
        }, 7000);
      }
    }
  </script>

</body>
</html>
