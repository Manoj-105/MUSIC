<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>MAAN - Music Artist</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" />
  <link href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.5/font/bootstrap-icons.css" rel="stylesheet" />
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet" />
  <style>
    body {
      background: #674d66;
      color: #e8e8e8;
      font-family: 'Poppins', sans-serif;
      margin: 0;
      padding: 0;
    }

    .hero {
      text-align: center;
      padding: 60px 20px 40px;
      position: relative;
      background: linear-gradient(135deg, rgba(231,203,222,0.1), rgba(103,77,102,0.8));
      border-radius: 25px;
      max-width: 720px;
      margin: 40px auto 60px;
      box-shadow: 0 0 50px #ebd6dc66;
    }

    /* Music Notes Animation */
    .music-notes {
      position: absolute;
      top: 20px;
      right: 20px;
      display: flex;
      gap: 8px;
      font-size: 1.8rem;
      color: #ebd6dcaa;
      animation: floatNotes 4s linear infinite;
      user-select: none;
      pointer-events: none;
    }

    @keyframes floatNotes {
      0% { transform: translateY(0) translateX(0) rotate(0deg); opacity: 1; }
      50% { transform: translateY(-15px) translateX(5px) rotate(15deg); opacity: 0.7; }
      100% { transform: translateY(0) translateX(0) rotate(0deg); opacity: 1; }
    }

    .artist-image {
      width: 200px;
      height: 200px;
      border-radius: 50%;
      border: 5px solid #ebd6dc;
      box-shadow: 0 0 50px #ebd6dc;
      object-fit: cover;
      margin: 0 auto 20px;
      display: block;
      position: relative;
    }

    /* Play Button Overlay on Artist Image */
    .artist-image-wrapper {
      position: relative;
      display: inline-block;
    }

    .play-button {
      position: absolute;
      bottom: 12px;
      right: 12px;
      background: rgba(235, 214, 220, 0.8);
      border-radius: 50%;
      width: 48px;
      height: 48px;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      box-shadow: 0 0 10px #ebd6dc;
      transition: background 0.3s ease;
    }

    .play-button:hover {
      background: #ebd6dc;
      color: #674d66;
      box-shadow: 0 0 20px #ebd6dc;
    }

    .play-button i {
      font-size: 1.8rem;
      color: #674d66;
    }

    .hero .details {
      background: rgba(255, 255, 255, 0.05);
      padding: 20px;
      border-radius: 20px;
      backdrop-filter: blur(10px);
      max-width: 600px;
      margin: auto;
      box-shadow: 0 0 30px #00000044;
    }

    .section-title {
      font-size: 2.5rem;
      font-weight: 700;
      color: #ebd6dc;
      text-align: center;
      margin-bottom: 20px;
      text-shadow: 0 0 10px #ebd6dc;
    }

    .bio {
      max-width: 700px;
      margin: auto;
      text-align: center;
      font-size: 1.1rem;
      color: #f0e3e8;
      margin-bottom: 40px;
      line-height: 1.5;
    }

    .music-grid {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 30px;
    }

    .audio-card {
      background: rgba(0, 255, 255, 0.05);
      border: 1px solid #ebd6dc;
      border-radius: 20px;
      padding: 20px;
      backdrop-filter: blur(20px);
      box-shadow: 0 0 30px #000000aa;
      transition: transform 0.3s ease, box-shadow 0.3s;
      width: 350px;
    }

    .audio-card:hover {
      transform: scale(1.02);
      box-shadow: 0 0 40px #ebd6dc;
    }

    .audio-card img {
      width: 100%;
      height: 180px;
      object-fit: cover;
      border-radius: 12px;
      margin-bottom: 10px;
      box-shadow: 0 0 15px #000;
    }

    .audio-card h5 {
      font-size: 1.1rem;
      margin-bottom: 10px;
      color: #ebd6dc;
      text-shadow: 2px 2px 5px #ebd6dc;
    }

    .audio-card audio {
      width: 100%;
    }

    .download-btn {
      margin-top: 10px;
      display: inline-block;
      background: radial-gradient(circle at center, #f9f1f5, #e6d6e3, #d0bfd6);
      color: #000;
      padding: 8px 16px;
      border-radius: 10px;
      text-decoration: none;
      font-weight: bold;
      font-size: 0.95rem;
      transition: background 0.3s;
    }

    .download-btn:hover {
      background: #e6d6e3;
    }

    footer {
      background: #382938;
      padding: 30px 20px 10px;
      margin-top: 60px;
      text-align: center;
    }

    .social-icons {
      margin-bottom: 10px;
    }

    .social-icons a {
      font-size: 1.5rem;
      margin: 0 10px;
      display: inline-block;
      transition: transform 0.3s, color 0.3s;
    }

    .social-icons a.instagram { color: #E1306C; }
    .social-icons a.youtube { color: #FF0000; }

    .social-icons a:hover {
      transform: scale(1.3);
      filter: brightness(120%);
    }

      @media (max-width: 768px) {
    .hero {
      padding: 40px 15px 30px;
      margin: 30px 15px;
    }

    .section-title {
      font-size: 1.8rem;
    }

    .bio {
      font-size: 0.95rem;
      padding: 0 10px;
    }

    .music-grid {
      flex-direction: column;
      gap: 20px;
    }

    .audio-card {
      width: 100%;
      padding: 15px;
    }

    .artist-image {
      width: 160px;
      height: 160px;
    }

    .play-button {
      width: 40px;
      height: 40px;
    }

    .play-button i {
      font-size: 1.5rem;
    }
  }

  @media (max-width: 400px) {
    .artist-image {
      width: 130px;
      height: 130px;
    }

    .play-button {
      width: 36px;
      height: 36px;
    }

    .play-button i {
      font-size: 1.3rem;
    }
  }
  </style>
</head>
<body>

  <div class="hero">
    <!-- Music Notes Floating Animation -->
    <div class="music-notes">
      <i class="bi bi-music-note-beamed"></i>
      <i class="bi bi-music-note"></i>
      <i class="bi bi-music-note-beamed"></i>
    </div>

    <!-- Artist Image with Play Button Overlay -->
    <div class="artist-image-wrapper">
      <img src="man.jpeg" alt="MAAN" class="artist-image" />
      <div class="play-button" title="Play Music">
        <i class="bi bi-play-fill"></i>
      </div>
    </div>

    <div class="details">
      <div class="section-title">MAAN</div>
      <div class="bio">
        <p>🎵 Passionate Music Artist | Creator of soulful beats and captivating melodies.<br>
          🎧 Crafting sounds that connect hearts and inspire emotions.<br>
          🔥 Explore the rhythm, feel the vibe, and join the journey of music.</p>
      </div>
    </div>
  </div>

  <div class="container">
    <div class="section-title">🎵 MUSIC</div>
    <div class="music-grid">

      <div class="audio-card">
        <img src="dil mane na.jpeg" alt="dil mane na" />
        <h5>DIL MANE NA</h5>
        <audio controls><source src="dil mane na.mpeg" type="audio/mp3" /></audio>
        <a href="dil mane na.mpeg" download class="download-btn">Download</a>
      </div>

      <div class="audio-card">
        <img src="raatein.jpeg" alt="raatein" />
        <h5>RAATEIN REMIX</h5>
        <audio controls><source src="raatein remix.mpeg" type="audio/mp3" /></audio>
        <a href="raatein remix.mpeg" download class="download-btn">Download</a>
      </div>

      <div class="audio-card">
        <img src="teri aadat.jpeg" alt="teri aadat" />
        <h5>TERI AADAT</h5>
        <audio controls><source src="teri aadat.mpeg" type="audio/mp3" /></audio>
        <a href="teri aadat.mpeg" download class="download-btn">Download</a>
      </div>

      <div class="audio-card">
        <img src="butterfly.jpeg" alt="butterfly" />
        <h5>BUTTERFLY</h5>
        <audio controls><source src="butterfly.mp3.mpeg" type="audio/mp3" /></audio>
        <a href="butterfly.mp3.mpeg" download class="download-btn">Download</a>
      </div>

      <div class="audio-card">
        <img src="sirf tu.jpeg" alt="sirf tu" />
        <h5>SIRF TU</h5>
        <audio controls><source src="sirf tu.mp3.mpeg" type="audio/mp3" /></audio>
        <a href="sirf tu.mp3.mpeg" download class="download-btn">Download</a>
      </div>

      <div class="audio-card">
        <img src="bad habit.jpeg" alt="bad habit" />
        <h5>BAD HABIT</h5>
        <audio controls><source src="bad habit.mpeg" type="audio/mp3" /></audio>
        <a href="bad habit.mpeg" download class="download-btn">Download</a>
      </div>

      <div class="audio-card">
        <img src="aajave mahiyaan.jpeg" alt="aajave mahiyaan" />
        <h5>AAJAVE MAHIYAAN</h5>
        <audio controls><source src="aajave mahiyaan.mpeg" type="audio/mp3" /></audio>
        <a href="aajave mahiyaan.mpeg" download class="download-btn">Download</a>
      </div>

      <div class="audio-card">
        <img src="LOST.png" alt="lost" />
        <h5>LOST</h5>
        <audio controls><source src="lost.mp3.mpeg" type="audio/mp3" /></audio>
        <a href="lost.mp3.mpeg" download class="download-btn">Download</a>
      </div>

    </div>
  </div>

  <footer>
    <div class="social-icons">
      <a href="https://www.instagram.com/thatsmaan_0/" class="instagram" target="_blank"><i class="bi bi-instagram"></i></a>
      <a href="https://www.youtube.com/@maan_music00" class="youtube" target="_blank"><i class="bi bi-youtube"></i></a>
    </div>
    <p class="mt-2">&copy; 2025 MAAN Music. All Rights Reserved.</p>
  </footer>

</body>
</html>
