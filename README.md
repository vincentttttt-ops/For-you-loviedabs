<!DOCTYPE html>
<html>
<head>
  <title>For You</title>

  <style>
    body {
      margin: 0;
      font-family: Arial;
      background: linear-gradient(to right, #ffd1dc, #ffe4ec);
      overflow-x: hidden;
    }

    .center {
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      flex-direction: column;
      text-align: center;
      padding: 20px;
    }

    .card {
      background: white;
      padding: 25px;
      border-radius: 15px;
      width: 90%;
      max-width: 500px;
      box-shadow: 0 10px 20px rgba(0,0,0,0.2);
    }

    h1 {
      color: #e91e63;
    }

    p {
      color: #333;
      line-height: 1.6;
    }

    button {
      margin-top: 15px;
      padding: 10px 15px;
      border: none;
      border-radius: 10px;
      background: #e91e63;
      color: white;
      cursor: pointer;
    }

    .hidden {
      display: none;
      margin-top: 15px;
      font-weight: bold;
      color: #e91e63;
    }

    .gallery {
      display: flex;
      gap: 10px;
      justify-content: center;
      flex-wrap: wrap;
      margin-top: 15px;
    }

    .gallery img {
      width: 120px;
      height: 120px;
      object-fit: cover;
      border-radius: 10px;
    }

    .heart {
      position: fixed;
      top: -10px;
      color: #e91e63;
      animation: fall 5s linear infinite;
      font-size: 20px;
    }

    @keyframes fall {
      0% {transform: translateY(-10px);}
      100% {transform: translateY(110vh);}
    }
  </style>
</head>

<body>

<audio autoplay loop>
  <source src="song.mp3" type="audio/mpeg">
</audio>

<div class="center">
  <div class="card">
    <h1>Happy Birthday</h1>

    <p>
      Dear love,<br><br>
      You bring peace. You bring happiness.  
      I stay grateful for you every day.<br><br>
      I wish you joy, health, and success.<br><br>
      I stay here for you.
    </p>

    <button onclick="showMessage()">Open Surprise</button>

    <div id="msg" class="hidden">
      You matter more than you know ❤️
    </div>

    <div class="gallery">
      <img src="1.jpg">
      <img src="2.jpg">
      <img src="3.jpg">
    </div>
  </div>
</div>

<script>
function showMessage() {
  document.getElementById("msg").style.display = "block";
}

function hearts() {
  const h = document.createElement("div");
  h.classList.add("heart");
  h.innerHTML = "❤️";
  h.style.left = Math.random() * 100 + "vw";
  h.style.animationDuration = (2 + Math.random() * 3) + "s";
  document.body.appendChild(h);

  setTimeout(() => {
    h.remove();
  }, 5000);
}

setInterval(hearts, 300);
</script>

</body>
</html>
