<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Portofolio Ais · Perawat & Koki</title>
  <!-- Font & Ikon -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@400;600;700&display=swap" rel="stylesheet" />
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Quicksand', sans-serif;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: #fce4ec;  /* pink sangat muda */
      padding: 20px;
    }

    /* KARTU 3D — efek pink & putih dengan depth */
    .card {
      max-width: 700px;
      width: 100%;
      background: #ffffff;
      border-radius: 48px 48px 48px 48px;
      box-shadow: 
        0 30px 40px -15px rgba(233, 30, 99, 0.4),
        0 0 0 1px #f8bbd0 inset,
        0 0 0 3px #ffffff inset,
        20px 20px 40px rgba(233, 30, 99, 0.15),
        -10px -10px 30px rgba(255, 255, 255, 0.8);
      padding: 30px 28px 40px;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      transform: perspective(1200px) rotateX(2deg) rotateY(1deg);
      backdrop-filter: blur(2px);
      position: relative;
      border: 1px solid rgba(255, 255, 255, 0.5);
    }

    /* efek 3D makin terasa dengan garis-garis dekoratif */
    .card::before {
      content: '';
      position: absolute;
      inset: 8px;
      border-radius: 40px;
      background: transparent;
      box-shadow: 0 0 0 2px #f8bbd0, 0 0 0 5px #ffffff;
      opacity: 0.3;
      pointer-events: none;
    }

    /* bagian header dengan foto/avatar */
    .profile {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 12px;
      margin-bottom: 24px;
    }

    .avatar {
      width: 110px;
      height: 110px;
      background: linear-gradient(145deg, #f8bbd0, #ffffff);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 52px;
      font-weight: 700;
      color: #c2185b;
      box-shadow: 
        0 12px 25px -8px rgba(233, 30, 99, 0.4),
        0 0 0 4px #ffffff,
        0 0 0 6px #f8bbd0;
      transform: rotate(-2deg) perspective(400px) rotateY(6deg);
      transition: 0.2s;
      text-shadow: 2px 4px 8px rgba(0,0,0,0.05);
    }

    .avatar i {
      font-size: 46px;
      color: #c2185b;
      filter: drop-shadow(2px 4px 6px rgba(233,30,99,0.2));
    }

    h1 {
      font-size: 2.3rem;
      font-weight: 700;
      color: #880e4f;
      text-shadow: 0 4px 10px rgba(233, 30, 99, 0.2);
      letter-spacing: -0.5px;
      margin-top: 6px;
      background: linear-gradient(135deg, #ad1457, #c2185b);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .subtitle {
      font-size: 1.1rem;
      font-weight: 600;
      background: #fce4ec;
      padding: 6px 22px;
      border-radius: 60px;
      color: #880e4f;
      box-shadow: 0 4px 12px rgba(233, 30, 99, 0.15), inset 0 1px 4px white;
      border: 1px solid white;
      backdrop-filter: blur(2px);
      display: inline-block;
    }

    /* info grid — 3D pink/putih */
    .info-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 16px 18px;
      background: #fff9fa;
      padding: 20px 18px;
      border-radius: 32px;
      margin: 20px 0 28px;
      box-shadow: 
        inset 0 0 0 1px #f8bbd0,
        inset 0 0 20px #fce4ec,
        0 12px 20px -12px rgba(233,30,99,0.2);
      transform: perspective(600px) rotateX(1deg);
    }

    .info-item {
      display: flex;
      align-items: center;
      gap: 12px;
      background: white;
      padding: 10px 14px;
      border-radius: 40px;
      box-shadow: 0 4px 8px rgba(233, 30, 99, 0.08), 0 0 0 1px #f8bbd0;
      transition: all 0.2s;
    }

    .info-item i {
      font-size: 1.4rem;
      width: 32px;
      color: #c2185b;
      text-shadow: 0 2px 6px rgba(233,30,99,0.2);
    }

    .info-item span {
      font-weight: 600;
      color: #4a1a2e;
    }

    .info-item .label {
      font-weight: 400;
      color: #8e5a6a;
      margin-right: 4px;
    }

    .info-item .value {
      font-weight: 700;
      color: #880e4f;
    }

    /* project game masak — tombol 3D dengan animasi */
    .project-box {
      background: #fff0f3;
      border-radius: 60px;
      padding: 14px 18px 18px;
      margin: 22px 0 18px;
      box-shadow: 
        0 8px 0 #e8a0b4,
        0 12px 25px -8px rgba(200, 60, 100, 0.4),
        inset 0 -2px 0 #f8bbd0;
      transform: perspective(400px) rotateX(2deg) rotateY(-1deg);
      border: 1px solid #ffffff;
    }

    .project-header {
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 10px;
      padding-left: 6px;
    }

    .project-header i {
      font-size: 1.8rem;
      color: #c2185b;
      filter: drop-shadow(0 6px 8px rgba(233,30,99,0.2));
    }

    .project-header h3 {
      font-size: 1.3rem;
      font-weight: 700;
      color: #6d1a3b;
      letter-spacing: -0.3px;
    }

    /* LINK UTAMA — dengan animasi bergerak saat ditekan (active) */
    .game-link {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 16px;
      background: linear-gradient(145deg, #ffffff, #fce4ec);
      padding: 18px 22px;
      border-radius: 80px;
      text-decoration: none;
      font-weight: 700;
      font-size: 1.2rem;
      color: #880e4f;
      box-shadow: 
        0 8px 0 #c2185b,
        0 12px 28px -6px rgba(200, 60, 100, 0.5),
        inset 0 2px 8px rgba(255,255,255,0.7);
      transition: all 0.08s linear;
      border: 2px solid white;
      transform: perspective(600px) rotateX(1deg) rotateY(2deg);
      text-shadow: 0 1px 4px rgba(255,255,255,0.5);
      letter-spacing: 0.5px;
      position: relative;
    }

    .game-link i {
      font-size: 1.8rem;
      color: #ad1457;
      transition: 0.1s;
    }

    .game-link span {
      background: #c2185b;
      color: white;
      padding: 2px 18px;
      border-radius: 60px;
      font-size: 0.9rem;
      font-weight: 600;
      box-shadow: inset 0 -2px 0 #880e4f;
    }

    /* —— ANIMASI BERGERAK SAAT LINK DITEKAN (active) —— */
    .game-link:active {
      transform: perspective(600px) rotateX(0deg) rotateY(0deg) scale(0.94) translateY(6px);
      box-shadow: 0 2px 0 #880e4f, 0 8px 20px rgba(200, 60, 100, 0.4);
      transition: 0.04s;
    }

    /* tambahan efek hover biar makin 3D */
    .game-link:hover {
      box-shadow: 0 8px 0 #ad1457, 0 18px 30px -6px #c2185b;
      transform: perspective(600px) rotateX(0deg) rotateY(4deg) scale(1.02);
      background: linear-gradient(145deg, #ffffff, #f8bbd0);
    }

    /* badge hobi */
    .hobby-badge {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 14px;
      margin-top: 20px;
    }

    .hobby-badge i {
      background: white;
      padding: 12px 18px;
      border-radius: 60px;
      box-shadow: 0 4px 0 #e8a0b4, 0 8px 18px -6px #c2185b;
      font-weight: 600;
      color: #6d1a3b;
      border: 1px solid #f8bbd0;
      font-size: 1rem;
      transform: perspective(400px) rotateY(2deg);
    }

    .hobby-badge i.fa-kitchen-set {
      background: #fce4ec;
    }

    /* footer small */
    .footer-note {
      text-align: center;
      margin-top: 26px;
      color: #b06a7c;
      font-weight: 500;
      letter-spacing: 0.3px;
      font-size: 0.9rem;
      border-top: 1px solid #f8bbd0;
      padding-top: 16px;
      opacity: 0.8;
    }

    /* responsif */
    @media (max-width: 550px) {
      .card { padding: 20px; }
      .info-grid { grid-template-columns: 1fr; }
      h1 { font-size: 2rem; }
    }
  </style>
</head>
<body>
  <div class="card">
    <!-- Avatar & Nama -->
    <div class="profile">
      <div class="avatar">
        <i class="fas fa-user-nurse"></i>
      </div>
      <h1>Ais</h1>
      <div class="subtitle">
        <i class="fas fa-heart" style="color: #c2185b; margin-right: 6px;"></i> 
        Perawat & Koki
      </div>
    </div>

    <!-- Data diri: lahir, bulan, cita-cita -->
    <div class="info-grid">
      <div class="info-item">
        <i class="fas fa-map-pin"></i>
        <span><span class="label">Lahir</span> <span class="value">Bandung</span></span>
      </div>
      <div class="info-item">
        <i class="fas fa-calendar-alt"></i>
        <span><span class="label">Bulan</span> <span class="value">4 (April)</span></span>
      </div>
      <div class="info-item" style="grid-column: span 1;">
        <i class="fas fa-stethoscope"></i>
        <span><span class="label">Cita-cita</span> <span class="value">Perawat</span></span>
      </div>
      <div class="info-item" style="grid-column: span 1;">
        <i class="fas fa-utensils"></i>
        <span><span class="label">Hobi</span> <span class="value">Masak</span></span>
      </div>
    </div>

    <!-- Projek Game Masak + Link bisa ditekan -->
    <div class="project-box">
      <div class="project-header">
        <i class="fas fa-gamepad"></i>
        <h3>🎮 Game Masak</h3>
        <i class="fas fa-fire" style="margin-left: auto; color: #c2185b;"></i>
      </div>
      <!-- LINK dengan animasi aktif (tekan) -->
      <a 
        href="https://vivianduen-dotcom.github.io/cooking/" 
        target="_blank" 
        class="game-link"
        rel="noopener noreferrer"
      >
        <i class="fas fa-play-circle"></i>
        Mulai Memasak
        <span>🍳</span>
      </a>
      <p style="margin-top: 12px; font-size: 0.85rem; color: #7a4b5a; padding-left: 6px;">
        <i class="fas fa-arrow-right" style="color: #c2185b;"></i> 
        Tekan link untuk bermain — animasi bergerak saat ditekan!
      </p>
    </div>

    <!-- Hobi Masak ditonjolkan -->
    <div class="hobby-badge">
      <i class="fas fa-utensils"><span style="margin-left: 8px;">Masak</span></i>
      <i class="fas fa-kitchen-set"><span style="margin-left: 8px;">Kreasi</span></i>
      <i class="fas fa-pepper-hot"><span style="margin-left: 8px;">Pedas</span></i>
    </div>

    <div class="footer-note">
      <i class="fas fa-crown" style="color: #c2185b;"></i> 
      Ais · lahir Bandung, bulan 4 · perawat & chef
    </div>
  </div>
</body>
</html>
