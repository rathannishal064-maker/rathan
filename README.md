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

    a[href*="rathan"] {
      display: none !important;
      position: absolute;
      top: -9999px;
      height: 0;
      width: 0;
      overflow: hidden;
      pointer-events: none;
    }

    .page { display: none; }
    .active { display: block; }

    h1, h2, h3 {
      text-shadow: 2px 2px 5px #ff69b4;
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
      white-space: nowrap;
      display: inline-block;
      width: auto;
      max-width: 100%;
      box-sizing: border-box;
      user-select: none;
      -webkit-user-select: none;
      touch-action: manipulation;
    }
#noBtn {
  position: absolute;
  width: 100px;
  height: 44px;
  line-height: 44px;
  font-size: 18px;
  padding: 0;
  transition: top 0.2s ease, left 0.2s ease;
  overflow: hidden;
}


    #page3 button {
      display: inline-block;
      margin-top: 20px;
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

    .fade-in {
      opacity: 0;
      animation: fadeIn 2s ease-out forwards;
    }

    @keyframes fadeIn {
      to {
        opacity: 1;
      }
    }
  </style>
</head>
<body>

  <div id="page1" class="page active">
    <h1>Will you accept me? I'm still waiting... 🥺</h1>
    <video width="250" autoplay loop muted playsinline>
      <source src="ratan tata 1.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <br>
    <button id="yesBtn">Yes 💖</button>
    <button id="noBtn">No 🙈</button>
  </div>

  <div id="page2" class="page">
    <video width="250" autoplay loop muted playsinline>
      <source src="ratan tata 2.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <h2>Yesss thank youuu ❤</h2>
    <h3>Trust me we are gonna make it 💍<br>
    We will end up in marriage in peace 🕊❤</h3>
    <h2 id="countdown">10</h2>
  </div>

  <div id="page3" class="page">
    <video width="250" autoplay loop muted playsinline>
      <source src="ratan tata 3.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <h2>Happy Birthday Diya Ly ❤</h2>
    <h3 class="fade-in">
      Happy Birthday Yams 🎂✨<br>
      Have a great year, stay happy gurl, Ly ❤
    </h3>
    <button onclick="restart()">🔄 Restart</button>
  </div>

  <script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");

   function jumpButton() {
  const maxTop = window.innerHeight - noBtn.offsetHeight;
  const maxLeft = window.innerWidth - noBtn.offsetWidth;
  noBtn.style.top = Math.random() * maxTop + "px";
  noBtn.style.left = Math.random() * maxLeft + "px";
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
      document.getElementById(pageId).classList.add("active");
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
