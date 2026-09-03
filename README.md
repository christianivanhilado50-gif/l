<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Coffee Date? 🎀💗</title>

  <style>
    /* =========================
       RESET
    ========================== */

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    /* =========================
       PAGE
    ========================== */

    body {
      min-height: 100vh;
      padding: 20px;

      display: flex;
      justify-content: center;
      align-items: center;

      font-family: "Trebuchet MS", Arial, sans-serif;

      color: #8a4560;

      background:
        radial-gradient(circle at 10% 10%, #ffffff 0%, transparent 25%),
        radial-gradient(circle at 90% 90%, #ffb6d0 0%, transparent 30%),
        radial-gradient(circle at 50% 0%, #ffd1e2 0%, transparent 40%),
        linear-gradient(135deg, #ffc9dd, #fff0f6, #ffc4da);

      overflow: hidden;
    }

    /* =========================
       MAIN CARD
    ========================== */

    .card {
      width: min(100%, 430px);
      max-height: 95vh;

      padding: 35px 25px;

      text-align: center;

      background: rgba(255, 255, 255, 0.93);

      border: 2px solid rgba(255, 182, 208, 0.7);
      border-radius: 32px;

      box-shadow:
        0 18px 45px rgba(214, 83, 122, 0.25),
        0 5px 15px rgba(214, 83, 122, 0.1);

      backdrop-filter: blur(12px);

      position: relative;
      z-index: 10;

      overflow-y: auto;
    }

    /* =========================
       CORNER BOWS
    ========================== */

    .corner-bow {
      position: absolute;
      font-size: 30px;

      animation: wiggle 2s ease-in-out infinite;
    }

    .bow-left {
      top: 12px;
      left: 15px;
    }

    .bow-right {
      top: 12px;
      right: 15px;
      animation-delay: .5s;
    }

    @keyframes wiggle {
      0%, 100% {
        transform: rotate(-8deg);
      }

      50% {
        transform: rotate(8deg) scale(1.08);
      }
    }

    /* =========================
       CUTE CHARACTER
    ========================== */

    .character {
      position: relative;
      display: inline-block;

      margin-top: 5px;

      font-size: 72px;
      line-height: 1;

      animation: characterBounce 2s ease-in-out infinite;

      filter:
        drop-shadow(
          0 7px 8px rgba(214, 83, 122, 0.15)
        );
    }

    .character-bow {
      position: absolute;

      top: -18px;
      right: -15px;

      font-size: 34px;

      animation: bowFloat 1.8s ease-in-out infinite;
    }

    @keyframes characterBounce {
      0%, 100% {
        transform: translateY(0);
      }

      50% {
        transform: translateY(-9px);
      }
    }

    @keyframes bowFloat {
      0%, 100% {
        transform: rotate(-10deg);
      }

      50% {
        transform: rotate(10deg) scale(1.1);
      }
    }

    /* =========================
       HEADINGS
    ========================== */

    h1 {
      margin: 15px 0 10px;

      font-size: 30px;
      line-height: 1.2;

      color: #e05280;
    }

    .success h1 {
      font-size: 35px;
    }

    /* =========================
       TEXT
    ========================== */

    .question {
      margin-bottom: 25px;

      font-size: 18px;
      line-height: 1.6;
    }

    .tiny {
      margin-top: 18px;

      font-size: 13px;
      color: #c27a94;
    }

    /* =========================
       DECORATIONS
    ========================== */

    .decorations {
      margin: 8px 0 15px;

      font-size: 21px;
      letter-spacing: 5px;

      animation: sparkle 2s ease-in-out infinite;
    }

    @keyframes sparkle {
      0%, 100% {
        opacity: .7;
      }

      50% {
        opacity: 1;
      }
    }

    /* =========================
       BUTTON AREA
    ========================== */

    .buttons {
      min-height: 120px;

      display: flex;
      justify-content: center;
      align-items: center;

      gap: 15px;

      position: relative;
    }

    /* =========================
       BUTTONS
    ========================== */

    button {
      border: none;
      border-radius: 50px;

      padding: 14px 28px;

      font-family: inherit;
      font-size: 17px;
      font-weight: bold;

      cursor: pointer;

      transition:
        transform 0.35s ease,
        background 0.25s ease,
        box-shadow 0.25s ease;

      -webkit-tap-highlight-color: transparent;
      user-select: none;
    }

    button:active {
      transform: scale(0.96);
    }

    /* YES BUTTON */

    #yesBtn {
      position: relative;
      z-index: 3;

      background: linear-gradient(
        135deg,
        #f06f9a,
        #df4f7d
      );

      color: white;

      box-shadow:
        0 7px 18px rgba(214, 83, 122, 0.3);
    }

    #yesBtn:hover {
      background: linear-gradient(
        135deg,
        #e85c89,
        #d94776
      );

      box-shadow:
        0 9px 23px rgba(214, 83, 122, 0.38);
    }

    /* NO BUTTON */

    #noBtn {
      position: relative;
      z-index: 2;

      background: #ffe3ed;
      color: #9a7180;

      border: 1px solid #f8bfd2;
    }

    #noBtn:hover {
      background: #ffd5e4;
    }

    /* =========================
       MESSAGE
    ========================== */

    #message {
      min-height: 28px;

      margin-top: 10px;

      font-weight: bold;

      color: #dc507d;

      transition: opacity 0.2s ease;
    }

    /* =========================
       HIDDEN
    ========================== */

    .hidden {
      display: none !important;
    }

    /* =========================
       SUCCESS
    ========================== */

    .success {
      animation: pop 0.6s ease;
    }

    @keyframes pop {
      0% {
        transform: scale(0.5);
        opacity: 0;
      }

      100% {
        transform: scale(1);
        opacity: 1;
      }
    }

    /* =========================
       THANK YOU BOX
    ========================== */

    .thank-you {
      margin-top: 20px;

      padding: 23px 18px;

      background:
        linear-gradient(
          135deg,
          #fff0f6,
          #ffdce9
        );

      border: 2px solid #f6bfd2;

      border-radius: 25px;

      box-shadow:
        inset 0 0 20px rgba(255, 255, 255, .7),
        0 8px 20px rgba(214, 83, 122, .12);
    }

    .thank-you p {
      font-size: 17px;
      line-height: 1.7;
    }

    .important {
      color: #df4f7d;
      font-weight: bold;
    }

    /* =========================
       CHAT BUBBLE
    ========================== */

    .chat-bubble {
      position: relative;

      margin: 22px auto 5px;

      max-width: 330px;

      padding: 15px 18px;

      background: white;

      border: 2px solid #f5bfd2;

      border-radius: 20px;

      color: #98506a;

      font-size: 15px;
      line-height: 1.5;

      box-shadow:
        0 5px 15px rgba(214, 83, 122, .1);
    }

    .chat-bubble::after {
      content: "";

      position: absolute;

      bottom: -10px;
      left: 50%;

      width: 18px;
      height: 18px;

      background: white;

      border-right: 2px solid #f5bfd2;
      border-bottom: 2px solid #f5bfd2;

      transform:
        translateX(-50%)
        rotate(45deg);
    }

    /* =========================
       FINAL MESSAGE
    ========================== */

    .final-note {
      margin-top: 25px;

      color: #bd718b;

      font-size: 14px;
      line-height: 1.6;
    }

    /* =========================
       FLOATING HEARTS
    ========================== */

    .hearts {
      position: fixed;
      inset: 0;

      overflow: hidden;

      pointer-events: none;

      z-index: 1;
    }

    .heart {
      position: absolute;

      bottom: -40px;

      opacity: 0;

      animation:
        floatUp 5s linear forwards;

      user-select: none;
    }

    @keyframes floatUp {

      0% {
        transform:
          translateY(0)
          rotate(0deg);

        opacity: 0;
      }

      15% {
        opacity: 1;
      }

      100% {
        transform:
          translateY(-110vh)
          rotate(360deg);

        opacity: 0;
      }
    }

    /* =========================
       SPARKLES
    ========================== */

    .sparkle {
      position: fixed;

      color: #f38aaa;

      pointer-events: none;

      z-index: 2;

      animation:
        sparkleFloat
        3s
        ease-in-out
        infinite;
    }

    @keyframes sparkleFloat {

      0%, 100% {
        opacity: .3;
        transform: scale(.8);
      }

      50% {
        opacity: 1;
        transform: scale(1.2);
      }
    }

    /* =========================
       MOVING CAT
    ========================== */

    .moving-cat {
      position: fixed;

      bottom: 15px;
      left: -100px;

      font-size: 55px;

      z-index: 20;

      pointer-events: none;

      animation:
        catWalk 12s linear infinite,
        catBounce .6s ease-in-out infinite;
    }

    @keyframes catWalk {

      0% {
        left: -100px;
      }

      48% {
        left: calc(100vw - 70px);
      }

      50% {
        left: calc(100vw - 70px);
      }

      98% {
        left: -100px;
      }

      100% {
        left: -100px;
      }
    }

    @keyframes catBounce {

      0%, 100% {
        margin-bottom: 0;
      }

      50% {
        margin-bottom: 8px;
      }
    }

    /* =========================
       CAT BOW
    ========================== */

    .cat-bow {
      position: absolute;

      top: -8px;
      right: -5px;

      font-size: 23px;

      animation:
        catBow
        .8s
        ease-in-out
        infinite;
    }

    @keyframes catBow {

      0%, 100% {
        transform: rotate(-10deg);
      }

      50% {
        transform: rotate(10deg) scale(1.1);
      }
    }

    /* =========================
       CAT SPEECH
    ========================== */

    .cat-message {
      position: fixed;

      bottom: 80px;
      left: 20px;

      padding: 10px 15px;

      background: white;

      border: 2px solid #f5bfd2;

      border-radius: 18px;

      color: #d95780;

      font-size: 13px;
      font-weight: bold;

      box-shadow:
        0 5px 15px rgba(214, 83, 122, .15);

      z-index: 21;

      animation:
        messageFloat
        2s
        ease-in-out
        infinite;
    }

    @keyframes messageFloat {

      0%, 100% {
        transform: translateY(0);
      }

      50% {
        transform: translateY(-5px);
      }
    }

    /* =========================
       FLOATING FLOWERS
    ========================== */

    .flower {
      position: fixed;

      bottom: -50px;

      font-size: 25px;

      pointer-events: none;

      z-index: 2;

      animation:
        flowerFloat
        7s
        linear
        forwards;
    }

    @keyframes flowerFloat {

      0% {
        transform:
          translateY(0)
          rotate(0deg);

        opacity: 0;
      }

      15% {
        opacity: 1;
      }

      100% {
        transform:
          translateY(-110vh)
          rotate(360deg);

        opacity: 0;
      }
    }

    /* =========================
       EXTRA FLOATING BOWS
    ========================== */

    .floating-bow {
      position: fixed;

      font-size: 30px;

      pointer-events: none;

      z-index: 3;

      animation:
        bowDrift
        5s
        ease-in-out
        infinite;
    }

    @keyframes bowDrift {

      0%, 100% {
        transform:
          translateY(0)
          rotate(-10deg);
      }

      50% {
        transform:
          translateY(-20px)
          rotate(10deg);
      }
    }

    /* =========================
       MOBILE
    ========================== */

    @media (max-width: 420px) {

      body {
        padding: 15px;
      }

      .card {
        padding: 30px 20px;
        border-radius: 28px;
      }

      .character {
        font-size: 63px;
      }

      h1 {
        font-size: 27px;
      }

      .success h1 {
        font-size: 31px;
      }

      .question {
        font-size: 17px;
      }

      .buttons {
        gap: 10px;
      }

      button {
        padding: 13px 22px;
        font-size: 16px;
      }

      .moving-cat {
        font-size: 45px;
      }

      .cat-message {
        left: 10px;
        bottom: 65px;
      }
    }

    /* =========================
       REDUCED MOTION
    ========================== */

    @media (prefers-reduced-motion: reduce) {

      *,
      *::before,
      *::after {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
      }
    }
  </style>
</head>

<body>

  <!-- =========================
       FLOATING DECORATIONS
  ========================== -->

  <div
    class="hearts"
    id="hearts"
    aria-hidden="true">
  </div>

  <span
    class="sparkle"
    style="top:10%;left:8%;">
    ✦
  </span>

  <span
    class="sparkle"
    style="top:25%;right:8%;animation-delay:.7s;">
    ✧
  </span>

  <span
    class="sparkle"
    style="bottom:15%;left:10%;animation-delay:1.2s;">
    ♡
  </span>

  <span
    class="sparkle"
    style="bottom:20%;right:12%;animation-delay:.4s;">
    ✦
  </span>


  <!-- EXTRA BOWS -->

  <div
    class="floating-bow"
    style="top:12%;left:20%;">
    🎀
  </div>

  <div
    class="floating-bow"
    style="top:45%;right:15%;animation-delay:1s;">
    🎀
  </div>

  <div
    class="floating-bow"
    style="bottom:30%;left:7%;animation-delay:2s;">
    🎀
  </div>


  <!-- =========================
       MOVING CAT
  ========================== -->

  <div class="moving-cat">

    🐱

    <span class="cat-bow">
      🎀
    </span>

  </div>

  <div class="cat-message">
    Meowww~ 💗
  </div>


  <!-- =========================
       MAIN CARD
  ========================== -->

  <main class="card">

    <!-- Corner bows -->

    <div class="corner-bow bow-left">
      🎀
    </div>

    <div class="corner-bow bow-right">
      🎀
    </div>


    <!-- =========================
         QUESTION PAGE
    ========================== -->

    <section id="questionPage">

      <div class="character">

        🧸

        <span class="character-bow">
          🎀
        </span>

      </div>


      <div class="decorations">
        🌷 💗 ✨ 🎀 ✨ 💗 🌷
      </div>


      <h1>
        Coffee Date? 🍵💗
      </h1>


      <p class="question">

        Hi Nicolaiii heheee 💗<br>

        Would you like to go on a<br>

        <strong>
          Coffee date
        </strong>

        with me? 🌷✨

      </p>


      <!-- BUTTONS -->

      <div class="buttons">

        <button
          id="yesBtn"
          type="button">

          YES 💗

        </button>


        <button
          id="noBtn"
          type="button">

          NO 😭

        </button>

      </div>


      <div
        id="message"
        aria-live="polite">
      </div>


      <p class="tiny">
        Choose wisely... 👀🎀
      </p>

    </section>


    <!-- =========================
         SUCCESS PAGE
    ========================== -->

    <section
      id="successPage"
      class="hidden">

      <div class="success">


        <!-- Cute teddy -->

        <div class="character">

          🧸

          <span class="character-bow">
            🎀
          </span>

        </div>


        <div class="decorations">
          💗 🎀 🌷 ✨ 🎀 🌷 💗
        </div>


        <h1>
          YEEHEYYY!! 🥳💗
        </h1>


        <p class="question">
          Thank youuu for saying yes hehe 🥹🎀
        </p>


        <!-- Sweet message -->

        <div class="thank-you">

          <p>
            I’m really happyyy you said yes! 🥹💗
          </p>

          <br>

          <p>

            No pressure on the date haaa.

            <span class="important">
              Chat me whenever you're freeee
            </span>

            because I respect your time and I want
            us to enjoy it when we're both available. 🌷

          </p>

        </div>


        <!-- Chat bubble -->

        <div class="chat-bubble">

          💌 Just chat me when you're free,
          okayyy? I'll be waiting hehe 🎀

        </div>


        <div class="final-note">

          Take your timeee 🤍<br>

          No rush, no pressure — just a cute
          little coffee date when the time is right. 🍵💗

        </div>


        <div
          class="decorations"
          style="margin-top:22px;">

          🎀 💕 🎀 💕 🎀

        </div>

      </div>

    </section>

  </main>


  <!-- =========================
       JAVASCRIPT
  ========================== -->

  <script>

    /* =========================
       ELEMENTS
    ========================== */

    const questionPage =
      document.getElementById("questionPage");

    const successPage =
      document.getElementById("successPage");

    const yesBtn =
      document.getElementById("yesBtn");

    const noBtn =
      document.getElementById("noBtn");

    const message =
      document.getElementById("message");

    const heartsContainer =
      document.getElementById("hearts");


    /* =========================
       NO BUTTON MESSAGES
    ========================== */

    const noMessages = [

      "Try again 😭💗",

      "Are you sure? 🥺🎀",

      "Think again hehe 👀",

      "Wrong button 😭",

      "The YES button is waiting... 💗",

      "Pleaseeee 🥹🌷",

      "You can't escape the coffee date 😌💗",

      "One more chance? 🥺💕"

    ];


    let noCount = 0;


    /* =========================
       NO BUTTON
    ========================== */

    noBtn.addEventListener(
      "click",
      sayNo
    );


    function sayNo() {

      const currentMessage =
        noMessages[
          Math.min(
            noCount,
            noMessages.length - 1
          )
        ];

      message.textContent =
        currentMessage;

      noCount++;


      /* YES gets bigger */

      const yesSize =
        Math.min(
          3,
          1 + noCount * 0.25
        );

      yesBtn.style.transform =
        `scale(${yesSize})`;


      /* NO gets smaller */

      const noSize =
        Math.max(
          0.55,
          1 - noCount * 0.08
        );

      noBtn.style.transform =
        `scale(${noSize})`;


      /* Final message */

      if (noCount >= 7) {

        yesBtn.style.transform =
          "scale(3)";

        message.textContent =
          "Okayyyy... YES na lang 😭💗🎀";
      }


      createHearts(5);

    }


    /* =========================
       YES BUTTON
    ========================== */

    yesBtn.addEventListener(
      "click",
      sayYes
    );


    function sayYes() {

      questionPage
        .classList
        .add("hidden");

      successPage
        .classList
        .remove("hidden");


      /* Heart celebration */

      createHearts(35);

      createFlowers(20);


      /* Second celebration */

      setTimeout(() => {

        createHearts(20);
        createFlowers(10);

      }, 900);

    }


    /* =========================
       FLOATING HEARTS
    ========================== */

    function createHearts(count = 18) {

      const emojis = [

        "💗",
        "💕",
        "💖",
        "💘",
        "🌸",
        "✨",
        "🎀",
        "🤍",
        "🌷",
        "♡"

      ];


      for (
        let i = 0;
        i < count;
        i++
      ) {

        setTimeout(() => {

          const heart =
            document.createElement("div");

          heart.classList.add(
            "heart"
          );


          heart.textContent =
            emojis[
              Math.floor(
                Math.random() *
                emojis.length
              )
            ];


          heart.style.left =
            Math.random() * 100 + "vw";


          heart.style.animationDuration =
            (3 + Math.random() * 3) + "s";


          heart.style.fontSize =
            (16 + Math.random() * 18) + "px";


          heart.style.transform =
            `rotate(
              ${Math.random() * 40 - 20}deg
            )`;


          heartsContainer.appendChild(
            heart
          );


          setTimeout(() => {

            heart.remove();

          }, 6500);

        }, i * 80);

      }

    }


    /* =========================
       FLOATING FLOWERS
    ========================== */

    function createFlowers(count = 8) {

      const flowers = [

        "🌸",
        "🌷",
        "🌺",
        "🌼",
        "🪻",
        "💐"

      ];


      for (
        let i = 0;
        i < count;
        i++
      ) {

        setTimeout(() => {

          const flower =
            document.createElement("div");

          flower.classList.add(
            "flower"
          );


          flower.textContent =
            flowers[
              Math.floor(
                Math.random() *
                flowers.length
              )
            ];


          flower.style.left =
            Math.random() * 100 + "vw";


          flower.style.fontSize =
            (18 + Math.random() * 20) + "px";


          flower.style.animationDuration =
            (5 + Math.random() * 4) + "s";


          document.body.appendChild(
            flower
          );


          setTimeout(() => {

            flower.remove();

          }, 9000);

        }, i * 300);

      }

    }


    /* =========================
       INITIAL DECORATIONS
    ========================== */

    setTimeout(() => {

      createHearts(10);

      createFlowers(8);

    }, 700);


    /* =========================
       CONTINUOUS FLOWERS
    ========================== */

    setInterval(() => {

      createFlowers(3);

    }, 5000);

  </script>

</body>
</html>
