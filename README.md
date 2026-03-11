# for-cinta.html
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Untukmu, Cintaku 💕</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;400&display=swap');

    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      min-height: 100vh;
      background: linear-gradient(135deg, #1a0020, #3d0050, #1a0030);
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      overflow-x: hidden;
      font-family: 'Poppins', sans-serif;
    }

    /* ============================
       SPLASH SCREEN (LAYAR AWAL)
    ============================= */
    #splash {
      position: fixed;
      inset: 0;
      z-index: 9999;
      background: linear-gradient(160deg, #1a0020, #5c0060, #1a0030);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      transition: opacity 0.9s ease, visibility 0.9s ease;
    }

    #splash.hide {
      opacity: 0;
      visibility: hidden;
      pointer-events: none;
    }

    .splash-heart {
      font-size: 5em;
      animation: sHeartbeat 1.1s ease-in-out infinite;
      filter: drop-shadow(0 0 20px #ff1493);
    }

    @keyframes sHeartbeat {
      0%, 100% { transform: scale(1); }
      50%       { transform: scale(1.2); }
    }

    .splash-title {
      font-family: 'Great Vibes', cursive;
      font-size: 3.2em;
      color: #ff69b4;
      text-shadow: 0 0 30px #ff1493, 0 0 60px #ff69b4;
      margin-top: 14px;
      animation: glowText 2s ease-in-out infinite alternate;
    }

    @keyframes glowText {
      from { text-shadow: 0 0 15px #ff1493, 0 0 30px #ff69b4; }
      to   { text-shadow: 0 0 35px #ff1493, 0 0 70px #ff69b4, 0 0 100px #ff69b4; }
    }

    .splash-sub {
      font-size: 0.78em;
      color: rgba(255,200,220,0.7);
      letter-spacing: 2px;
      margin-top: 8px;
    }

    .splash-btn {
      margin-top: 42px;
      padding: 14px 36px;
      border-radius: 50px;
      border: 2px solid #ff69b4;
      background: rgba(255, 20, 147, 0.2);
      color: #fff;
      font-size: 1em;
      font-family: 'Poppins', sans-serif;
      letter-spacing: 2px;
      cursor: pointer;
      backdrop-filter: blur(8px);
      box-shadow: 0 0 24px rgba(255,20,147,0.5);
      animation: btnPulse 1.5s ease-in-out infinite;
      transition: background 0.3s;
      -webkit-tap-highlight-color: transparent;
    }

    .splash-btn:hover, .splash-btn:active {
      background: rgba(255, 20, 147, 0.45);
    }

    @keyframes btnPulse {
      0%, 100% { box-shadow: 0 0 16px rgba(255,20,147,0.5); }
      50%       { box-shadow: 0 0 36px rgba(255,20,147,1); }
    }

    .splash-note {
      margin-top: 18px;
      font-size: 0.65em;
      color: rgba(255,150,200,0.5);
      letter-spacing: 1px;
    }

    /* Partikel kecil di splash */
    .splash-hearts-bg {
      position: absolute;
      inset: 0;
      pointer-events: none;
      overflow: hidden;
    }

    .s-heart {
      position: absolute;
      top: -30px;
      animation: sFall linear infinite;
      opacity: 0;
      font-size: 16px;
    }

    @keyframes sFall {
      0%   { transform: translateY(0); opacity: 0.8; }
      100% { transform: translateY(110vh); opacity: 0; }
    }

    /* ============================
       KONTEN UTAMA
    ============================= */
    .love-rain {
      position: fixed;
      inset: 0;
      pointer-events: none;
      z-index: 0;
    }

    .heart {
      position: absolute;
      top: -40px;
      animation: rainFall linear infinite;
      opacity: 0;
      text-shadow: 0 0 8px #ff1493, 0 0 15px #ff69b4;
    }

    @keyframes rainFall {
      0%   { transform: translateY(0) rotate(0deg); opacity: 0.9; }
      80%  { opacity: 0.6; }
      100% { transform: translateY(110vh) rotate(20deg); opacity: 0; }
    }

    .card {
      position: relative;
      z-index: 10;
      background: rgba(255, 255, 255, 0.07);
      border: 1.5px solid rgba(255, 105, 180, 0.4);
      backdrop-filter: blur(12px);
      border-radius: 28px;
      padding: 36px 28px;
      max-width: 360px;
      width: 90%;
      text-align: center;
      box-shadow: 0 0 40px rgba(255,20,147,0.3), 0 0 80px rgba(255,105,180,0.1);
      animation: floatCard 4s ease-in-out infinite;
      margin-top: 20px;
    }

    @keyframes floatCard {
      0%, 100% { transform: translateY(0); }
      50%       { transform: translateY(-10px); }
    }

    .title {
      font-family: 'Great Vibes', cursive;
      font-size: 3em;
      color: #ff69b4;
      animation: glow 2s ease-in-out infinite alternate;
    }

    @keyframes glow {
      from { text-shadow: 0 0 10px #ff1493, 0 0 20px #ff69b4; }
      to   { text-shadow: 0 0 25px #ff1493, 0 0 50px #ff69b4, 0 0 70px #ff69b4; }
    }

    .subtitle {
      font-size: 0.75em;
      color: rgba(255,200,220,0.7);
      letter-spacing: 3px;
      text-transform: uppercase;
      margin-bottom: 24px;
      margin-top: 6px;
    }

    .divider {
      color: #ff69b4;
      font-size: 1.3em;
      letter-spacing: 6px;
      margin-bottom: 22px;
      opacity: 0.8;
    }

    .quote {
      font-size: 0.88em;
      color: rgba(255,220,235,0.95);
      line-height: 1.85;
      font-weight: 300;
      font-style: italic;
      margin-bottom: 18px;
      padding: 0 6px;
    }

    .quote span {
      color: #ff69b4;
      font-weight: 600;
      font-style: normal;
    }

    .message {
      background: rgba(255,20,147,0.1);
      border-left: 3px solid #ff69b4;
      border-radius: 0 12px 12px 0;
      padding: 14px 16px;
      margin: 18px 0;
      text-align: left;
    }

    .message p {
      font-size: 0.82em;
      color: rgba(255,220,235,0.9);
      line-height: 1.8;
    }

    .nama {
      font-family: 'Great Vibes', cursive;
      font-size: 2em;
      color: #ff69b4;
      text-shadow: 0 0 15px #ff1493;
      margin-top: 18px;
    }

    .stars {
      font-size: 1em;
      color: #ffd700;
      letter-spacing: 5px;
      margin-top: 10px;
      animation: twinkle 1.5s ease-in-out infinite alternate;
    }

    @keyframes twinkle {
      from { opacity: 0.5; }
      to   { opacity: 1; }
    }

    .footer-heart {
      position: relative;
      z-index: 10;
      margin: 18px 0 80px;
      font-size: 1.6em;
      animation: heartbeat 1.2s ease-in-out infinite;
    }

    @keyframes heartbeat {
      0%, 100% { transform: scale(1); }
      50%       { transform: scale(1.3); }
    }

    /* ============================
       NOW PLAYING BAR
    ============================= */
    .now-playing {
      position: fixed;
      bottom: 0; left: 0;
      width: 100%;
      z-index: 999;
      background: rgba(30,0,40,0.88);
      backdrop-filter: blur(10px);
      border-top: 1px solid rgba(255,105,180,0.3);
      padding: 10px 18px;
      display: flex;
      align-items: center;
      gap: 12px;
      transform: translateY(100%);
      transition: transform 0.5s ease;
    }

    .now-playing.show { transform: translateY(0); }

    .np-icon { font-size: 1.6em; animation: spin 3s linear infinite; }

    @keyframes spin {
      from { transform: rotate(0deg); }
      to   { transform: rotate(360deg); }
    }

    .np-info { flex: 1; }
    .np-title { font-size: 0.82em; color: #ff69b4; font-weight: 600; }
    .np-artist { font-size: 0.7em; color: rgba(255,200,220,0.7); }

    .np-wave { display: flex; align-items: flex-end; gap: 3px; height: 20px; }

    .np-wave span {
      display: block; width: 3px;
      background: #ff69b4; border-radius: 2px;
      animation: wave 0.8s ease-in-out infinite;
    }

    .np-wave span:nth-child(1) { animation-delay: 0s;    height: 8px; }
    .np-wave span:nth-child(2) { animation-delay: 0.15s; height: 16px; }
    .np-wave span:nth-child(3) { animation-delay: 0.3s;  height: 10px; }
    .np-wave span:nth-child(4) { animation-delay: 0.45s; height: 18px; }
    .np-wave span:nth-child(5) { animation-delay: 0.6s;  height: 6px; }

    @keyframes wave {
      0%, 100% { transform: scaleY(0.4); }
      50%       { transform: scaleY(1); }
    }

    .np-pause-btn {
      font-size: 1.2em;
      cursor: pointer;
      background: rgba(255,20,147,0.2);
      border: 1px solid #ff69b4;
      border-radius: 50%;
      width: 34px; height: 34px;
      display: flex; align-items: center; justify-content: center;
      -webkit-tap-highlight-color: transparent;
    }

    /* YouTube tersembunyi */
    #yt-player {
      position: fixed;
      bottom: -300px; left: -300px;
      width: 1px; height: 1px;
      opacity: 0; pointer-events: none;
    }
  </style>
</head>
<body>

  <!-- ===== SPLASH SCREEN ===== -->
  <div id="splash" onclick="startExperience()">
    <div class="splash-hearts-bg" id="splashBg"></div>
    <div class="splash-heart">💖</div>
    <div class="splash-title">My Love</div>
    <div class="splash-sub">✦ Sebuah Pesan Untukmu ✦</div>
    <button class="splash-btn">♥ &nbsp; Buka Pesanmu &nbsp; ♥</button>
    <div class="splash-note">🎵 dengan musik My Love - Westlife</div>
  </div>

  <!-- YOUTUBE PLAYER TERSEMBUNYI -->
  <div id="yt-player"></div>

  <!-- HUJAN LOVE -->
  <div class="love-rain" id="loveRain"></div>

  <!-- KARTU CINTA -->
  <div class="card">
    <div class="title">My Love</div>
    <div class="subtitle">✦ FOR BUBUB NAURA STRAWBERRY🍓 ✦</div>
    <div class="divider">♥ ♥ ♥</div>

    <p class="quote">
      Dalam setiap detak jantungku,<br>
      hanya ada satu nama yang selalu kusebut —<br>
      <span>namamu, cintaku.</span>
    </p>

    <div class="message">
      <p>
        aku tuh beneran sesuka itu sama cara kamu jadi diri sendiri. makasih ya udah selalu tampil apa adanya kalau lagi sama aku, nggak perlu pura-pura jadi orang lain. buat aku, semua versi kamu pas lagi ketawa receh, pas lagi serius, sampe pas lagi berantakan pun itu yang bikin kamu spesial banget di mata aku.
 tapi please semangat terus ya, jangan pernah kepikiran buat nyerah. Inget kalau aku bakal selalu ada di belakang kamu, apa pun kondisinya. aku bakal tetep jadi supporter nomor satu kamu yang paling berisik buat nemenin semua proses dan mimpi-mimpi kamu. jangan pernah ngerasa sendirian atau putus asa ya, ada aku di sini yang selalu bangga punya kamu.
makasih ya udah hebat banget sejauh ini dan udah milih aku buat nemenin kamu. aku nggak butuh kamu jadi sempurna buat dunia, aku cuma pengen kamu tetep jadi kamu yang sekarang. You
're more than enough, and I’m so lucky to have you. I got your back, always!"
          
        Semangat ya buat semua kegiatan kamu, aku tahu kamu lagi capek dan banyak pikiran, tapi ingat ya kalau kamu nggak sendirian. Aku di sini selalu bangga sama apa pun yang kamu kerjain. Jangan lupa makan dan istirahat yang cukup. Kalau butuh tempat cerita, aku selalu siap dengerin. You’re doing great, and I’m always on your side.💕
      </p>
    </div>

    <p class="quote">
      <span>"Cinta bukan sekadar kata-kata,</span><br>
      tapi rasa yang terus tumbuh<br>
      setiap kali aku melihatmu."
    </p>

    <div class="divider">♥ ♥ ♥</div>

    <p style="font-size:0.78em; color:rgba(255,200,220,0.7); margin-bottom:4px;">Dengan sepenuh hati dari</p>
    <div class="nama">revv</div>
    <div class="stars">★ ★ ★ ★ ★</div>
  </div>

  <div class="footer-heart">💗</div>

  <!-- NOW PLAYING BAR -->
  <div class="now-playing" id="nowPlaying">
    <div class="np-icon">💿</div>
    <div class="np-info">
      <div class="np-title">My Love</div>
      <div class="np-artist">Westlife 💕</div>
    </div>
    <div class="np-wave">
      <span></span><span></span><span></span><span></span><span></span>
    </div>
    <div class="np-pause-btn" id="pauseBtn" onclick="togglePause()">⏸</div>
  </div>

  <!-- YOUTUBE IFrame API -->
  <script src="https://www.youtube.com/iframe_api"></script>
  <script>

    /* ===== HUJAN LOVE DI SPLASH ===== */
    const splashBg = document.getElementById('splashBg');
    const sym = ['❤','💕','💖','💗','💓','💞','♥'];
    for (let i = 0; i < 30; i++) {
      const s = document.createElement('div');
      s.className = 's-heart';
      s.textContent = sym[Math.floor(Math.random() * sym.length)];
      s.style.cssText = `
        left:${Math.random()*100}vw;
        font-size:${10+Math.random()*14}px;
        animation-duration:${3+Math.random()*5}s;
        animation-delay:${Math.random()*6}s;
      `;
      splashBg.appendChild(s);
    }

    /* ===== HUJAN LOVE KONTEN ===== */
    const rainContainer = document.getElementById('loveRain');
    for (let i = 0; i < 45; i++) {
      const h = document.createElement('div');
      h.className = 'heart';
      h.textContent = sym[Math.floor(Math.random() * sym.length)];
      h.style.cssText = `
        left:${Math.random()*100}vw;
        font-size:${12+Math.random()*18}px;
        animation-duration:${4+Math.random()*6}s;
        animation-delay:${Math.random()*8}s;
      `;
      rainContainer.appendChild(h);
    }

    /* ===== YOUTUBE PLAYER ===== */
    let player;
    let isPaused = false;
    const VIDEO_ID = 'ulOByTE4Cqk'; // My Love - Westlife

    function onYouTubeIframeAPIReady() {
      player = new YT.Player('yt-player', {
        height: '1', width: '1',
        videoId: VIDEO_ID,
        playerVars: {
          autoplay: 0,
          controls: 0,
          loop: 1,
          playlist: VIDEO_ID,
          modestbranding: 1,
          rel: 0,
          playsinline: 1
        },
        events: {
          onReady: function(e) {
            e.target.setVolume(85);
          },
          onStateChange: function(e) {
            if (e.data === YT.PlayerState.PLAYING) {
              document.getElementById('nowPlaying').classList.add('show');
              document.getElementById('pauseBtn').textContent = '⏸';
            } else if (e.data === YT.PlayerState.PAUSED) {
              document.getElementById('pauseBtn').textContent = '▶';
            }
          }
        }
      });
    }

    /* ===== MULAI EXPERIENCE (TAP SPLASH) ===== */
    function startExperience() {
      // Sembunyikan splash
      document.getElementById('splash').classList.add('hide');

      // Langsung putar musik begitu user tap
      if (player && typeof player.playVideo === 'function') {
        player.playVideo();
      } else {
        // Jika player belum siap, tunggu sebentar lalu play
        setTimeout(function() {
          if (player) player.playVideo();
        }, 1200);
      }
    }

    /* ===== TOMBOL PAUSE/PLAY DI NOW PLAYING ===== */
    function togglePause() {
      if (!player) return;
      if (isPaused) {
        player.playVideo();
        isPaused = false;
      } else {
        player.pauseVideo();
        isPaused = true;
      }
    }

  </script>
</body>
</html>
