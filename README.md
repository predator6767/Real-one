<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Special Question</title>

<style>
body {
  margin: 0;
  height: 100vh;
  background: linear-gradient(135deg, #ff9a9e, #fad0c4);
  font-family: Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
}

.container {
  text-align: center;
  background: rgba(255,255,255,0.2);
  padding: 30px;
  border-radius: 20px;
  backdrop-filter: blur(10px);
  box-shadow: 0 10px 30px rgba(0,0,0,0.2);
}

h1 {
  color: white;
  font-size: 2rem;
  margin-bottom: 20px;
  animation: fadeIn 2s ease-in-out;
}

.buttons {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-top: 20px;
}

button {
  padding: 12px 25px;
  border: none;
  border-radius: 30px;
  font-size: 16px;
  cursor: pointer;
  transition: 0.3s;
}

#yes {
  background: #ff4d6d;
  color: white;
}

#no {
  background: white;
  color: #ff4d6d;
  position: relative;
}

#yes:hover {
  transform: scale(1.1);
}

.heart {
  position: absolute;
  color: #ff4d6d;
  animation: float 6s linear infinite;
}

@keyframes float {
  0% { transform: translateY(100vh) scale(0.5); opacity: 1; }
  100% { transform: translateY(-10vh) scale(1); opacity: 0; }
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(-20px); }
  to { opacity: 1; transform: translateY(0); }
}

#message {
  margin-top: 20px;
  font-size: 1.3rem;
  color: white;
}
</style>
</head>

<body>

<div class="container">
  <h1>Hey... I have a question for you 💭</h1>

  <div class="buttons">
    <button id="yes" onclick="sayYes()">Yes 💖</button>
    <button id="no" onmouseover="moveNo()">No 😅</button>
  </div>

  <div id="message"></div>
</div>

<script>
function sayYes() {
  document.getElementById("message").innerHTML =
    "Yay! You just made someone really happy 💖✨";
}

// Make "No" button move away
function moveNo() {
  const btn = document.getElementById("no");
  const x = Math.random() * (window.innerWidth - 100);
  const y = Math.random() * (window.innerHeight - 100);
  btn.style.position = "absolute";
  btn.style.left = x + "px";
  btn.style.top = y + "px";
}

// Floating hearts
function createHeart() {
  const heart = document.createElement("div");
  heart.classList.add("heart");
  heart.innerHTML = "❤";
  heart.style.left = Math.random() * window.innerWidth + "px";
  heart.style.fontSize = Math.random() * 20 + 10 + "px";
  document.body.appendChild(heart);

  setTimeout(() => {
    heart.remove();
  }, 6000);
}

setInterval(createHeart, 300);
</script>

</body>
</html>
