<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Cute Kitty Love</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: "Comic Sans MS", cursive, sans-serif;
      font-size: 1.2em;
      background: pink;
      color: #fff;
      text-align: center;
      min-height: 100vh;
      overflow: hidden;
    }

    .page {
      display: none;
      height: 100vh;
      width: 100vw;
      background: pink;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    .active {
      display: flex;
    }

    h1, h2, h3 {
      text-shadow: 2px 2px 5px #ff69b4;
      margin: 10px;
    }

    button {
      background: #ff69b4;
      border: none;
      padding: 12px 24px;
      margin: 10px;
      border-radius: 20px;
      font-size: 18px;
      color: white;
      cursor: pointer;
      transition: 0.3s;
    }

    button:hover {
      background: #ff1493;
    }

    #noBtn {
      position: absolute;
      bottom: 10px;
      right: 10px;
    }

    video {
      max-width: 250px;
      margin-top: 20px;
      animation: bounce 1.5s infinite ease-in-out;
    }

    @keyframes bounce {
      0%, 100% { transform: translateY(0) scale(1); }
      50% { transform: translateY(-15px) scale(1.05); }
    }

    .heart {
      position: absolute;
      color: red;
      font-size: 24px;
      animation: floatUp 5s linear infinite;
      z-index: 1;
    }

    @keyframes floatUp {
      from { transform: translateY(100vh); opacity: 1; }
      to { transform: translateY(-10vh); opacity: 0; }
    }

    .fade-glow {
      opacity: 0;
      animation: fadeInGlow 3s ease forwards;
    }

    @keyframes fadeInGlow {
      0% { opacity: 0; text-shadow: none; }
      100% {
        opacity: 1;
        text-shadow: 0 0 10px #fff, 0 0 20px #ff69b4, 0 0 30px #ff69b4;
      }
    }
  </style>
</head>
<body>

  <div id="page1" class="page active">
    <h1>Will you accept me? I'm still waiting... 🥺</h1>
    <video autoplay loop muted playsinline>
      <source src="ratan tata 1.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <br>
    <button id="yesBtn">Yes 💖</button>
    <button id="noBtn">No 🙈</button>
  </div>

  <div id="page2" class="page">
    <video autoplay loop muted playsinline>
      <source src="ratan tata 2.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <h2>Yesss thank youuu ❤</h2>
    <h3>Trust me we are gonna make it 💍<br>
    We will end up in marriage in peace 🕊❤</h3>
    <h2 id="countdown">10</h2>
  </div>

  <div id="page3" class="page">
    <video autoplay loop muted playsinline>
      <source src="ratan tata 3.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <h2>Happy Birthday Diya Ly ❤</h2>
    <h3 id="birthdayMsg">Happy Birthday Yams 🎂✨<br>
    Have a great year, stay happy gurl, Ly ❤</h3>
    <button onclick="restart()">🔄 Restart</button>
  </div>

  <script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");

    function jumpButton() {
      noBtn.style.top = Math.random() * window.innerHeight * 0.75 + "px";
      noBtn.style.left = Math.random() * window.innerWidth * 0.75 + "px";
    }

    noBtn.addEventListener("mouseover", jumpButton);
    noBtn.addEventListener("touchstart", jumpButton);
    noBtn.addEventListener("click", (e) => {
      e.preventDefault();
      jumpButton();
    });

    yesBtn.addEventListener("click", () => {
      showPage("page2");
      startCountdown();
    });

    function showPage(pageId) {
      document.querySelectorAll(".page").forEach(p => p.classList.remove("active"));
      const nextPage = document.getElementById(pageId);
      nextPage.classList.add("active");

      // Trigger glow animation only on page3
      if (pageId === "page3") {
        const msg = document.getElementById("birthdayMsg");
        msg.classList.add("fade-glow");
      }
    }

    function startCountdown() {
      let time = 10;
      const counter = document.getElementById("countdown");
      const interval = setInterval(() => {
        counter.innerText = time;
        time--;
        if (time < 0) {
          clearInterval(interval);
          showPage("page3");
        }
      }, 1000);
    }

    function restart() {
      showPage("page1");
    }

    function createHeart() {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.innerHTML = "❤";
      heart.style.left = Math.random() * window.innerWidth + "px";
      heart.style.fontSize = (20 + Math.random() * 20) + "px";
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 5000);
    }

    setInterval(createHeart, 500);
  </script>
</body>
</html>
