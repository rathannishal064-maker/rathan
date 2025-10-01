<title>Cute Kitty Love</title> <style> a[href*="rathan"] { display: none !important; } body { margin: 0; padding: 0; font-family: "Comic Sans MS", cursive, sans-serif; /* INCREASED FONT SIZE HERE */ font-size: 1.2em; background: pink; color: #fff; text-align: center; /* Make sure the body is full screen for jumping */ min-height: 100vh; overflow: hidden; } .page { display: none; } .active { display: block; }
h1, h2, h3 {
  text-shadow: 2px 2px 5px #ff69b4;
button { background: #ff69b4; border: none; padding: 12px 32px; margin: 10px; border-radius: 20px; font-size: 18px; color: white; cursor: pointer; transition: 0.3s; min-width: 120px; } button:hover { background: #ff1493; }

#noBtn { 
    position: absolute;
    transition: none; 
    bottom: 10px;
    right: 10px;
} 

img {
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

.sparkle {
  background: linear-gradient(90deg, #ff69b4, #fff, #ff69b4, #fff);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-size: 300% auto;
  animation: shine 3s linear infinite;
}
@keyframes shine {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}
body > a[href*="rathan"] {
display: none !important; position: absolute; top: -9999px; }

</style>
Will you accept me? I'm still waiting... 🥺
<br>
<button id="yesBtn">Yes 💖</button>
<button id="noBtn">No 🙈</button>
<h2>Yesss thank youuu ❤</h2>
<h3>Trust me we are gonna make it 💍<br>
We will end up in marriage in peace 🕊❤</h3>
<h2 id="countdown">10</h2>
Happy Birthday Diya Ly ❤
Happy Birthday Yams 🎂✨
Have a great year, stay happy gurl, Ly ❤
🔄 Restart
<script> const noBtn = document.getElementById("noBtn"); const yesBtn = document.getElementById("yesBtn"); function jumpButton() { noBtn.style.top = Math.random() * window.innerHeight * 0.75 + "px"; noBtn.style.left = Math.random() * window.innerWidth * 0.75 + "px"; } noBtn.addEventListener("mouseover", jumpButton); noBtn.addEventListener("touchstart", jumpButton); noBtn.addEventListener("click", (e) => { e.preventDefault(); jumpButton(); }); yesBtn.addEventListener("click", () => { showPage("page2"); startCountdown(); }); function showPage(pageId) { document.querySelectorAll(".page").forEach(p => p.classList.remove("active")); document.getElementById(pageId).classList.add("active"); } function startCountdown() { let time = 10; const counter = document.getElementById("countdown"); const interval = setInterval(() => { counter.innerText = time; time--; if (time < 0) { clearInterval(interval); showPage("page3"); } }, 1000); } function restart() { showPage("page1"); } function createHeart() { const heart = document.createElement("div"); heart.className = "heart"; heart.innerHTML = "❤"; heart.style.left = Math.random() * window.innerWidth + "px"; heart.style.fontSize = (20 + Math.random() * 20) + "px"; document.body.appendChild(heart); setTimeout(() => heart.remove(), 5000); } setInterval(createHeart, 500); </script>
