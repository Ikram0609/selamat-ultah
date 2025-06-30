<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Selamat Ulang Tahun Rustam ke-21 🎉</title>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      padding: 0;
      background: radial-gradient(circle at top, #ffccd5, #ffe6f0);
      font-family: 'Comic Sans MS', cursive, sans-serif;
      color: #ff4081;
      overflow-x: hidden;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .container {
      max-width: 900px;
      width: 100%;
      padding: 20px;
      text-align: center;
    }

    h1 {
      margin-top: 20px;
      font-size: 2.4rem;
      animation: fadeIn 2s ease-in-out;
    }

    .balloons {
      display: flex;
      justify-content: center;
      gap: 15px;
      flex-wrap: wrap;
      margin-top: 20px;
      animation: fadeIn 2s ease-in-out;
    }

    .balloon {
      width: 40px;
      height: 80px;
      animation: floatBalloon 3s ease-in-out infinite;
    }

    @keyframes floatBalloon {
      0% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
      100% { transform: translateY(0); }
    }

    .heart-container {
      position: relative;
      width: 100%;
      max-width: 600px;
      height: 80vw;
      max-height: 500px;
      margin: 20px auto;
      animation: pulseHeart 6s ease-in-out infinite;
    }

    .photo {
      position: absolute;
      width: 12vw;
      height: 12vw;
      max-width: 70px;
      max-height: 70px;
      object-fit: cover;
      border-radius: 15px;
      border: 2px solid white;
      box-shadow: 0 0 10px #ff4081;
      animation: float 6s ease-in-out infinite;
    }

    .controls {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 15px;
      margin-top: 20px;
    }

    button {
      padding: 12px 24px;
      font-size: 1rem;
      background-color: #ff4081;
      color: white;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      box-shadow: 0 4px 6px rgba(0,0,0,0.2);
      transition: transform 0.2s ease;
    }

    button:hover {
      transform: scale(1.05);
    }

    .message {
      font-size: 1.2rem;
      margin: 30px auto;
      max-width: 700px;
      padding: 0 20px;
      animation: fadeIn 3s ease-in-out;
      line-height: 1.7;
    }

    audio {
      display: none;
    }

    #stars {
      position: fixed;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      background: transparent;
      pointer-events: none;
      z-index: -1;
    }

    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }

    @keyframes fadeIn {
      0% { opacity: 0; transform: translateY(-20px); }
      100% { opacity: 1; transform: translateY(0); }
    }

    @keyframes pulseHeart {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.05); }
    }

    @media (max-width: 768px) {
      h1 {
        font-size: 2rem;
      }

      .photo {
        width: 14vw;
        height: 14vw;
      }

      .message {
        font-size: 1rem;
      }

      button {
        font-size: 0.9rem;
        padding: 10px 18px;
      }
    }

    @media (max-width: 480px) {
      .photo {
        width: 16vw;
        height: 16vw;
      }

      .controls {
        flex-direction: column;
        gap: 10px;
      }
    }
  </style>
</head>
<body>
  <canvas id="stars"></canvas>

  <!-- 🎈 SVG Balon-Balon di Atas -->
  <div class="balloons">
    <svg class="balloon" viewBox="0 0 32 64" xmlns="http://www.w3.org/2000/svg">
      <path d="M16,0 C24,0 30,10 30,20 C30,30 24,40 16,40 C8,40 2,30 2,20 C2,10 8,0 16,0 Z" fill="#FF5E5E"/>
      <line x1="16" y1="40" x2="16" y2="64" stroke="#aaa" stroke-width="2"/>
    </svg>
    <svg class="balloon" viewBox="0 0 32 64" xmlns="http://www.w3.org/2000/svg">
      <path d="M16,0 C24,0 30,10 30,20 C30,30 24,40 16,40 C8,40 2,30 2,20 C2,10 8,0 16,0 Z" fill="#7ED6DF"/>
      <line x1="16" y1="40" x2="16" y2="64" stroke="#aaa" stroke-width="2"/>
    </svg>
    <svg class="balloon" viewBox="0 0 32 64" xmlns="http://www.w3.org/2000/svg">
      <path d="M16,0 C24,0 30,10 30,20 C30,30 24,40 16,40 C8,40 2,30 2,20 C2,10 8,0 16,0 Z" fill="#FFD93D"/>
      <line x1="16" y1="40" x2="16" y2="64" stroke="#aaa" stroke-width="2"/>
    </svg>
  </div>

  <div class="container">
    <h1>Selamat Ulang Tahun Rustam yang ke-21! 🎂</h1>

    <div class="heart-container" id="heart1"></div>
    <div class="heart-container" id="heart2"></div>

    <div class="controls">
      <button onclick="playMusic()">▶️ Putar Musik</button>
      <button onclick="stopMusic()">⏹️ Stop Musik</button>
    </div>

    <div class="message">
      Semoga di usia yang ke-21 ini, Rustam menjadi pribadi yang makin kuat, bijaksana, dan penuh cinta. Terima kasih sudah menjadi sosok yang spesial. Semoga semua impianmu tercapai dan kebahagiaan selalu menyertaimu. 💖🎉<br><br>
      Dari seseorang yang selalu bucin padamu~ 🥰
    </div>
  </div>

  <audio id="bgMusic" loop>
    <source src="lagu.mp3" type="audio/mpeg" />
    Browser kamu tidak mendukung audio.
  </audio>

  <script>
    function renderHeart(containerId, startIndex, count) {
      const container = document.getElementById(containerId);
      const angleStep = (2 * Math.PI) / count;

      for (let i = 0; i < count; i++) {
        const angle = i * angleStep;
        const x = 35 * Math.sin(angle) ** 3;
        const y = -(
          30 * Math.cos(angle)
          - 12 * Math.cos(2 * angle)
          - 7 * Math.cos(3 * angle)
          - 2.5 * Math.cos(4 * angle)
        );

        const img = document.createElement('img');
        img.src = `foto${startIndex + i}.jpg`;
        img.className = 'photo';
        img.style.left = `${45 + x}%`; // geser pusat love ke kiri
        img.style.top = `${50 + y}%`;
        container.appendChild(img);
      }
    }

    renderHeart("heart1", 1, 22);
    renderHeart("heart2", 23, 23);

    const music = document.getElementById('bgMusic');
    function playMusic() { music.play(); }
    function stopMusic() {
      music.pause();
      music.currentTime = 0;
    }

    function createConfetti() {
      const confetti = document.createElement('div');
      confetti.style.width = "10px";
      confetti.style.height = "10px";
      confetti.style.background = `hsl(${Math.random()*360},100%,70%)`;
      confetti.style.position = "fixed";
      confetti.style.top = "-10px";
      confetti.style.left = `${Math.random()*100}%`;
      confetti.style.zIndex = 1;
      confetti.style.opacity = 0.8;
      confetti.style.transform = `rotate(${Math.random()*360}deg)`;
      confetti.style.transition = "top 4s ease-in, transform 4s";
      document.body.appendChild(confetti);
      setTimeout(() => {
        confetti.style.top = "100%";
        confetti.style.transform += ` rotate(${Math.random()*360}deg)`;
      }, 50);
      setTimeout(() => confetti.remove(), 4000);
    }
    setInterval(createConfetti, 300);

    const starCanvas = document.getElementById('stars');
    const ctx = starCanvas.getContext('2d');
    starCanvas.width = window.innerWidth;
    starCanvas.height = window.innerHeight;
    let stars = [];
    for (let i = 0; i < 100; i++) {
      stars.push({ x: Math.random() * starCanvas.width, y: Math.random() * starCanvas.height, r: Math.random() * 1.5 + 0.5 });
    }
    function drawStars() {
      ctx.clearRect(0, 0, starCanvas.width, starCanvas.height);
      for (let s of stars) {
        ctx.beginPath();
        ctx.arc(s.x, s.y, s.r, 0, 2 * Math.PI);
        ctx.fillStyle = 'rgba(255,255,255,0.7)';
        ctx.fill();
      }
      requestAnimationFrame(drawStars);
    }
    drawStars();
  </script>
</body>
</html>
