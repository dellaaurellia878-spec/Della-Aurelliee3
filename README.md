<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Della Aurellia · Portfolio</title>
  <!-- Font Inter -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700&display=swap" rel="stylesheet" />
  <!-- Font Awesome 6 (gratis) -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      scroll-behavior: smooth;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: #fafafa;
      color: #1e1e1e;
      line-height: 1.6;
      opacity: 0;
      animation: fadeBody 0.5s ease forwards;
    }
    @keyframes fadeBody {
      to { opacity: 1; }
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 24px;
    }

    /* preloader */
    #preloader {
      position: fixed;
      inset: 0;
      background: #fff;
      display: flex;
      align-items: center;
      justify-content: center;
      z-index: 9999;
      transition: opacity 0.5s;
    }
    #preloader.hidden {
      opacity: 0;
      pointer-events: none;
    }
    .loader {
      width: 44px;
      height: 44px;
      border: 4px solid #e0e0e0;
      border-top: 4px solid #a07c5b;
      border-radius: 50%;
      animation: spin 0.8s linear infinite;
    }
    @keyframes spin {
      to { transform: rotate(360deg); }
    }

    /* navbar */
    nav {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      background: rgba(255, 255, 255, 0.85);
      backdrop-filter: blur(10px);
      box-shadow: 0 2px 20px rgba(0, 0, 0, 0.03);
      z-index: 1000;
      padding: 12px 0;
      transition: background 0.2s;
    }
    .nav-container {
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
    }
    .logo {
      font-weight: 700;
      font-size: 1.4rem;
      letter-spacing: -0.5px;
      color: #1e1e1e;
    }
    .logo span {
      color: #a07c5b;
    }
    .nav-links {
      display: flex;
      gap: 20px;
      list-style: none;
      font-weight: 500;
      font-size: 0.9rem;
      flex-wrap: wrap;
    }
    .nav-links a {
      text-decoration: none;
      color: #2c2c2c;
      transition: color 0.2s;
      position: relative;
    }
    .nav-links a::after {
      content: '';
      position: absolute;
      bottom: -4px;
      left: 0;
      width: 0;
      height: 2px;
      background: #a07c5b;
      transition: width 0.25s;
    }
    .nav-links a:hover {
      color: #a07c5b;
    }
    .nav-links a:hover::after {
      width: 100%;
    }
    .hamburger {
      display: none;
      font-size: 1.6rem;
      background: none;
      border: none;
      color: #1e1e1e;
      cursor: pointer;
    }

    /* sections */
    section {
      padding: 80px 0 60px;
    }
    .section-title {
      font-size: 2rem;
      font-weight: 600;
      letter-spacing: -0.02em;
      margin-bottom: 40px;
      position: relative;
    }
    .section-title::after {
      content: '';
      display: block;
      width: 50px;
      height: 3px;
      background: #a07c5b;
      margin-top: 8px;
    }

    /* card lembut */
    .card-soft {
      background: #fff;
      border-radius: 24px;
      padding: 28px;
      box-shadow: 0 12px 30px rgba(0, 0, 0, 0.03);
      transition: transform 0.2s, box-shadow 0.2s;
    }
    .card-soft:hover {
      transform: translateY(-4px);
      box-shadow: 0 20px 40px rgba(0, 0, 0, 0.06);
    }

    /* hero */
    .hero {
      min-height: 80vh;
      display: flex;
      align-items: center;
      padding-top: 80px;
    }
    .hero-grid {
      display: flex;
      align-items: center;
      gap: 50px;
      flex-wrap: wrap;
    }
    .hero-content {
      flex: 1 1 400px;
    }
    .hero-content h1 {
      font-size: 3rem;
      font-weight: 600;
      letter-spacing: -1px;
      line-height: 1.2;
    }
    .hero-content .tagline {
      font-size: 1.2rem;
      color: #5a5a5a;
      margin: 8px 0 6px;
    }
    .hero-content p {
      color: #3d3d3d;
      max-width: 460px;
      margin: 16px 0 28px;
    }
    .hero-avatar {
      flex: 0 0 180px;
      text-align: center;
    }
    .hero-avatar img {
      width: 180px;
      height: 180px;
      object-fit: cover;
      border-radius: 50%;
      box-shadow: 0 20px 40px rgba(0, 0, 0, 0.05);
      border: 4px solid #fff;
    }
    .btn-group {
      display: flex;
      gap: 14px;
      flex-wrap: wrap;
    }
    .btn {
      display: inline-block;
      padding: 12px 32px;
      border-radius: 60px;
      font-weight: 500;
      text-decoration: none;
      transition: all 0.25s;
      border: 1px solid transparent;
      font-size: 0.95rem;
      background: #1e1e1e;
      color: #fff;
      cursor: pointer;
    }
    .btn-outline {
      background: transparent;
      border-color: #1e1e1e;
      color: #1e1e1e;
    }
    .btn-outline:hover {
      background: #1e1e1e;
      color: #fff;
    }
    .btn-primary {
      background: #a07c5b;
      border-color: #a07c5b;
      color: #fff;
    }
    .btn-primary:hover {
      background: #8b6a4b;
      border-color: #8b6a4b;
    }

    /* about */
    .about-grid {
      display: grid;
      grid-template-columns: 1fr 2fr;
      gap: 40px;
      align-items: start;
    }
    .about-photo img {
      width: 100%;
      max-width: 240px;
      border-radius: 28px;
      box-shadow: 0 16px 32px rgba(0, 0, 0, 0.05);
    }
    .about-detail {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }
    .badge-list {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 6px;
    }
    .badge {
      background: #f0edea;
      padding: 6px 18px;
      border-radius: 60px;
      font-size: 0.8rem;
      font-weight: 500;
      color: #2c2c2c;
    }

    /* CV */
    .cv-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 30px;
    }
    .cv-item {
      border-left: 3px solid #a07c5b;
      padding-left: 18px;
      margin-bottom: 20px;
    }
    .cv-item h4 {
      font-weight: 600;
      font-size: 1.05rem;
    }
    .cv-item p {
      color: #4a4a4a;
      font-size: 0.95rem;
    }

    /* gallery karya */
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
      gap: 24px;
    }
    .gallery-card {
      background: #fff;
      border-radius: 20px;
      overflow: hidden;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.02);
      transition: 0.25s;
    }
    .gallery-card:hover {
      transform: scale(1.01);
      box-shadow: 0 16px 32px rgba(0, 0, 0, 0.06);
    }
    .gallery-card img {
      width: 100%;
      height: 180px;
      object-fit: cover;
    }
    .gallery-card .info {
      padding: 16px 18px 20px;
    }
    .gallery-card .info h4 {
      font-weight: 600;
      font-size: 1.1rem;
    }
    .gallery-card .info .category {
      color: #a07c5b;
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 0.5px;
      font-weight: 600;
    }
    .btn-small {
      padding: 6px 18px;
      font-size: 0.8rem;
      border-radius: 40px;
      background: #f0edea;
      border: none;
      font-weight: 500;
      cursor: pointer;
      transition: 0.2s;
    }
    .btn-small:hover {
      background: #d9d2c9;
    }

    /* foto masonry */
    .masonry {
      column-count: 3;
      column-gap: 20px;
    }
    .masonry-item {
      break-inside: avoid;
      margin-bottom: 20px;
      border-radius: 20px;
      overflow: hidden;
      cursor: pointer;
      transition: 0.2s;
      background: #fff;
    }
    .masonry-item img {
      width: 100%;
      display: block;
    }
    .masonry-item:hover {
      opacity: 0.9;
    }

    /* lightbox sederhana (modal) */
    .lightbox {
      display: none;
      position: fixed;
      inset: 0;
      background: rgba(0, 0, 0, 0.8);
      align-items: center;
      justify-content: center;
      z-index: 2000;
      padding: 24px;
    }
    .lightbox.active {
      display: flex;
    }
    .lightbox img {
      max-width: 90%;
      max-height: 90%;
      border-radius: 16px;
      box-shadow: 0 30px 60px rgba(0, 0, 0, 0.3);
    }
    .lightbox .close-light {
      position: absolute;
      top: 30px;
      right: 40px;
      font-size: 2.5rem;
      color: #fff;
      cursor: pointer;
      opacity: 0.7;
      transition: 0.2s;
      background: none;
      border: none;
    }
    .lightbox .close-light:hover {
      opacity: 1;
    }

    /* artikel */
    .blog-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
      gap: 30px;
    }
    .blog-card {
      background: #fff;
      border-radius: 24px;
      overflow: hidden;
      box-shadow: 0 6px 18px rgba(0, 0, 0, 0.02);
    }
    .blog-card img {
      width: 100%;
      height: 160px;
      object-fit: cover;
    }
    .blog-card .body {
      padding: 18px 20px 24px;
    }
    .blog-card .body .meta {
      color: #7a7a7a;
      font-size: 0.8rem;
      display: flex;
      gap: 12px;
      margin: 6px 0 10px;
    }

    /* sosial */
    .social-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 24px;
      justify-content: center;
    }
    .social-card {
      background: #fff;
      padding: 20px 30px;
      border-radius: 60px;
      box-shadow: 0 6px 16px rgba(0, 0, 0, 0.02);
      display: flex;
      align-items: center;
      gap: 12px;
      font-weight: 500;
      text-decoration: none;
      color: #1e1e1e;
      transition: 0.2s;
    }
    .social-card i {
      font-size: 1.6rem;
      width: 32px;
      color: #a07c5b;
    }
    .social-card:hover {
      background: #f5f1ec;
      transform: scale(1.02);
    }

    /* kontak */
    .contact-wrap {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 50px;
    }
    .contact-form input,
    .contact-form textarea {
      width: 100%;
      padding: 14px 18px;
      border: 1px solid #e0e0e0;
      border-radius: 30px;
      font-family: inherit;
      margin-bottom: 16px;
      background: #fff;
      transition: 0.2s;
    }
    .contact-form input:focus,
    .contact-form textarea:focus {
      border-color: #a07c5b;
      outline: none;
    }
    .contact-info p {
      display: flex;
      align-items: center;
      gap: 12px;
      margin: 14px 0;
    }
    .contact-info i {
      width: 24px;
      color: #a07c5b;
    }

    /* testimoni */
    .testi-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
      gap: 30px;
    }
    .testi-card {
      background: #fff;
      border-radius: 28px;
      padding: 28px 22px;
      box-shadow: 0 6px 16px rgba(0, 0, 0, 0.02);
    }
    .testi-card .avatar {
      width: 56px;
      height: 56px;
      background: #a07c5b;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: 600;
      font-size: 1.4rem;
      color: #fff;
      margin-bottom: 12px;
    }

    /* footer */
    footer {
      background: #fff;
      padding: 40px 0 24px;
      border-top: 1px solid #f0f0f0;
    }
    .footer-content {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: center;
      gap: 20px;
    }
    .footer-social a {
      color: #2c2c2c;
      margin-left: 16px;
      font-size: 1.2rem;
      transition: 0.2s;
    }
    .footer-social a:hover {
      color: #a07c5b;
    }

    /* back to top */
    #backTop {
      position: fixed;
      bottom: 40px;
      right: 40px;
      background: #1e1e1e;
      color: #fff;
      border: none;
      border-radius: 60px;
      padding: 12px 16px;
      font-size: 1.2rem;
      cursor: pointer;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.08);
      opacity: 0;
      transition: 0.3s;
      pointer-events: none;
    }
    #backTop.show {
      opacity: 1;
      pointer-events: auto;
    }
    #backTop:hover {
      background: #a07c5b;
    }

    /* reveal */
    .reveal {
      opacity: 0;
      transform: translateY(30px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }
    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* responsive */
    @media (max-width: 992px) {
      .about-grid {
        grid-template-columns: 1fr;
      }
      .contact-wrap {
        grid-template-columns: 1fr;
      }
      .cv-grid {
        grid-template-columns: 1fr;
      }
    }
    @media (max-width: 768px) {
      .nav-links {
        display: none;
        flex-direction: column;
        width: 100%;
        padding: 16px 0;
        gap: 12px;
      }
      .nav-links.open {
        display: flex;
      }
      .hamburger {
        display: block;
      }
      .hero-grid {
        flex-direction: column-reverse;
        text-align: center;
      }
      .hero-content p {
        margin-left: auto;
        margin-right: auto;
      }
      .btn-group {
        justify-content: center;
      }
      .masonry {
        column-count: 2;
      }
      .section-title::after {
        margin-left: auto;
        margin-right: auto;
      }
    }
    @media (max-width: 480px) {
      .masonry {
        column-count: 1;
      }
      .social-card {
        padding: 14px 22px;
      }
    }
  </style>
</head>
<body>

  <!-- preloader -->
  <div id="preloader"><div class="loader"></div></div>

  <!-- navbar -->
  <nav>
    <div class="container nav-container">
      <div class="logo">Della<span>.</span></div>
      <button class="hamburger" id="hamburger" aria-label="Menu"><i class="fas fa-bars"></i></button>
      <ul class="nav-links" id="navLinks">
        <li><a href="#beranda">Beranda</a></li>
        <li><a href="#tentang">Tentang</a></li>
        <li><a href="#cv">CV</a></li>
        <li><a href="#karya">Hasil Karya</a></li>
        <li><a href="#foto">Foto</a></li>
        <li><a href="#artikel">Artikel</a></li>
        <li><a href="#sosial">Media Sosial</a></li>
        <li><a href="#kontak">Kontak</a></li>
        <li><a href="#testimoni">Testimoni</a></li>
      </ul>
    </div>
  </nav>

  <main>

    <!-- BERANDA -->
    <section id="beranda" class="hero">
      <div class="container hero-grid">
        <div class="hero-content">
          <p class="tagline">Halo, saya</p>
          <h1>Della Aurellia</h1>
          <p style="font-size:1.1rem; font-weight:400;">pelajar · kreatif · berjiwa juang</p>
          <p>Saya seorang pelajar yang aktif dan tangguh, selalu bersemangat mengeksplorasi desain, fotografi, dan teknologi.</p>
          <div class="btn-group">
            <a href="#karya" class="btn btn-primary">Lihat Hasil Karya</a>
            <a href="#kontak" class="btn btn-outline">Hubungi Saya</a>
          </div>
        </div>
        <div class="hero-avatar">
          <img src="https://ui-avatars.com/api/?name=Della+Aurellia&size=200&background=a07c5b&color=fff&bold=true" alt="Della Aurellia" />
        </div>
      </div>
    </section>

    <!-- TENTANG -->
    <section id="tentang" class="container reveal">
      <h2 class="section-title">Tentang Kami</h2>
      <div class="about-grid">
        <div class="about-photo">
          <img src="https://ui-avatars.com/api/?name=Della+Aurellia&size=300&background=a07c5b&color=fff&bold=true" alt="foto Della" />
        </div>
        <div class="about-detail">
          <h3>Della Aurellia</h3>
          <p style="color:#5a5a5a;">pelajar · SMKN 42</p>
          <p><em>“saya adalah seorang pelajar yang aktif dan berjiwa juang dan tangguh”</em></p>
          <p>Saya memiliki ketertarikan besar pada dunia desain visual, fotografi, dan pengembangan web. Setiap proyek adalah petualangan baru untuk belajar dan berkarya.</p>
          <div><strong>Pendidikan</strong><br/>SMKN 42 (2023–sekarang)</div>
          <div><strong>Pengalaman</strong><br/>Magang desain grafis (2025), fotografer dokumentasi</div>
          <div><strong>Minat</strong><br/>Desain UI/UX, fotografi, konten kreatif, public speaking</div>
          <div><strong>Keahlian</strong>
            <div class="badge-list">
              <span class="badge">Figma</span>
              <span class="badge">Photoshop</span>
              <span class="badge">HTML/CSS</span>
              <span class="badge">Fotografi</span>
              <span class="badge">Canva</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CV -->
    <section id="cv" class="container reveal">
      <h2 class="section-title">CV Digital</h2>
      <div class="cv-grid">
        <div>
          <h3>Profil</h3>
          <p>Pelajar SMKN 42 dengan semangat tinggi di bidang kreatif. Disiplin, adaptif, dan selalu haus akan ilmu baru.</p>
          <div style="margin-top:24px;"><h3>Pendidikan</h3>
            <div class="cv-item"><h4>SMKN 42</h4><p>2023 – sekarang · Jurusan Desain</p></div>
          </div>
          <div><h3>Pengalaman</h3>
            <div class="cv-item"><h4>Magang Desain Grafis</h4><p>2025 · Studio Kreatif</p></div>
            <div class="cv-item"><h4>Fotografer Event</h4><p>2024 · Berbagai acara sekolah</p></div>
          </div>
        </div>
        <div>
          <h3>Organisasi</h3>
          <div class="cv-item"><h4>Paskibra</h4><p>Anggota aktif 2024–sekarang</p></div>
          <div class="cv-item"><h4>Klub Fotografi</h4><p>Koordinator dokumentasi</p></div>
          <div><h3>Prestasi</h3>
            <div class="cv-item"><h4>Juara 2 Lomba Desain Poster</h4><p>2025</p></div>
          </div>
          <div><h3>Keahlian</h3>
            <div class="badge-list"><span class="badge">Figma</span><span class="badge">Canva</span><span class="badge">Lightroom</span></div>
          </div>
          <div><h3>Sertifikat</h3>
            <div class="cv-item"><h4>Dasar Desain Grafis</h4><p>BNSP 2025</p></div>
          </div>
          <a href="#" class="btn btn-primary" style="margin-top:20px; display:inline-block;">Download CV (PDF)</a>
        </div>
      </div>
    </section>

    <!-- HASIL KARYA -->
    <section id="karya" class="container reveal">
      <h2 class="section-title">Hasil Karya</h2>
      <div class="gallery-grid">
        <div class="gallery-card"><img src="https://placehold.co/600x400/e6ddd3/2c2c2c?text=Poster+Event" alt="karya1"/><div class="info"><span class="category">Desain</span><h4>Poster Event</h4><p>Poster untuk acara sekolah</p><button class="btn-small">Lihat Detail</button></div></div>
        <div class="gallery-card"><img src="https://placehold.co/600x400/d9d2c9/2c2c2c?text=Potret+Urban" alt="karya2"/><div class="info"><span class="category">Fotografi</span><h4>Potret Urban</h4><p>Eksplorasi warna kota</p><button class="btn-small">Lihat Detail</button></div></div>
        <div class="gallery-card"><img src="https://placehold.co/600x400/cfc6ba/2c2c2c?text=Mockup+App" alt="karya3"/><div class="info"><span class="category">UI/UX</span><h4>Aplikasi Belajar</h4><p>Mockup aplikasi edukasi</p><button class="btn-small">Lihat Detail</button></div></div>
        <div class="gallery-card"><img src="https://placehold.co/600x400/b8ada0/2c2c2c?text=Ilustrasi" alt="karya4"/><div class="info"><span class="category">Ilustrasi</span><h4>Karakter Digital</h4><p>Ilustrasi vektor</p><button class="btn-small">Lihat Detail</button></div></div>
      </div>
    </section>

    <!-- FOTO dengan lightbox -->
    <section id="foto" class="container reveal">
      <h2 class="section-title">Foto</h2>
      <div class="masonry" id="masonryGrid">
        <div class="masonry-item"><img src="https://placehold.co/400x500/d9d2c9/2c2c2c?text=Foto+1" alt="foto1" class="foto-thumb" /></div>
        <div class="masonry-item"><img src="https://placehold.co/400x300/cfc6ba/2c2c2c?text=Foto+2" alt="foto2" class="foto-thumb" /></div>
        <div class="masonry-item"><img src="https://placehold.co/400x600/b8ada0/2c2c2c?text=Foto+3" alt="foto3" class="foto-thumb" /></div>
        <div class="masonry-item"><img src="https://placehold.co/400x400/a89b8d/2c2c2c?text=Foto+4" alt="foto4" class="foto-thumb" /></div>
        <div class="masonry-item"><img src="https://placehold.co/400x350/d9d2c9/2c2c2c?text=Foto+5" alt="foto5" class="foto-thumb" /></div>
        <div class="masonry-item"><img src="https://placehold.co/400x500/cfc6ba/2c2c2c?text=Foto+6" alt="foto6" class="foto-thumb" /></div>
      </div>
    </section>

    <!-- Lightbox -->
    <div class="lightbox" id="lightbox">
      <button class="close-light" id="closeLight">&times;</button>
      <img id="lightboxImg" src="" alt="preview" />
    </div>

    <!-- ARTIKEL -->
    <section id="artikel" class="container reveal">
      <h2 class="section-title">Artikel</h2>
      <div class="blog-grid">
        <div class="blog-card"><img src="https://placehold.co/600x300/e6ddd3/2c2c2c?text=Thumbnail" alt="artikel1"/><div class="body"><h4>Tips Desain untuk Pemula</h4><div class="meta"><span>12 Mei 2025</span><span>Desain</span></div><p>Panduan singkat memulai desain grafis</p><button class="btn-small">Baca Selengkapnya</button></div></div>
        <div class="blog-card"><img src="https://placehold.co/600x300/d9d2c9/2c2c2c?text=Thumbnail" alt="artikel2"/><div class="body"><h4>Fotografi dengan HP</h4><div class="meta"><span>28 April 2025</span><span>Fotografi</span></div><p>Tips mengambil foto estetik dengan ponsel</p><button class="btn-small">Baca Selengkapnya</button></div></div>
        <div class="blog-card"><img src="https://placehold.co/600x300/cfc6ba/2c2c2c?text=Thumbnail" alt="artikel3"/><div class="body"><h4>Belajar UI/UX Dasar</h4><div class="meta"><span>10 Maret 2025</span><span>UI/UX</span></div><p>Pengantar user interface untuk pelajar</p><button class="btn-small">Baca Selengkapnya</button></div></div>
      </div>
    </section>

    <!-- MEDIA SOSIAL -->
    <section id="sosial" class="container reveal">
      <h2 class="section-title">Media Sosial</h2>
      <div class="social-grid">
        <a href="#" class="social-card"><i class="fab fa-instagram"></i> @bbvterfliee._</a>
        <a href="#" class="social-card"><i class="fab fa-tiktok"></i> @oreL</a>
        <a href="#" class="social-card"><i class="fab fa-youtube"></i> @Urell</a>
        <a href="#" class="social-card"><i class="fab fa-facebook"></i> Della Aurellia</a>
        <a href="#" class="social-card"><i class="fab fa-linkedin"></i> Della Aurellia</a>
      </div>
    </section>

    <!-- KONTAK -->
    <section id="kontak" class="container reveal">
      <h2 class="section-title">Kontak</h2>
      <div class="contact-wrap">
        <form class="contact-form">
          <input type="text" placeholder="Nama" value="Della Aurellia" />
          <input type="email" placeholder="Email" value="dellaaurelliaa878@gmail.com" />
          <textarea rows="4" placeholder="Pesan"></textarea>
          <button type="submit" class="btn btn-primary">Kirim Pesan</button>
        </form>
        <div class="contact-info">
          <p><i class="fas fa-envelope"></i> dellaaurellia878@gmail.com</p>
          <p><i class="fas fa-phone"></i> 0857-0998-0651</p>
          <p><i class="fab fa-instagram"></i> @bbvterfliee._</p>
          <p><i class="fab fa-tiktok"></i> @oreL</p>
          <p style="margin-top:20px;">Senang berkenalan dan berkolaborasi. Jangan ragu untuk menyapa!</p>
        </div>
      </div>
    </section>

    <!-- TESTIMONI -->
    <section id="testimoni" class="container reveal">
      <h2 class="section-title">Testimoni</h2>
      <div class="testi-grid">
        <div class="testi-card"><div class="avatar">A</div><h4>Ahmad</h4><p style="color:#5a5a5a;">Teman sekelas</p><p>“Kreatif dan selalu punya ide segar! Della orang yang menyenangkan untuk bekerja sama.”</p></div>
        <div class="testi-card"><div class="avatar">S</div><h4>Siti</h4><p style="color:#5a5a5a;">Klien fotografi</p><p>“Hasil fotonya bagus dan prosesnya profesional. Sangat direkomendasikan!”</p></div>
        <div class="testi-card"><div class="avatar">R</div><h4>Rina</h4><p style="color:#5a5a5a;">Guru</p><p>“Siswa yang tekun dan cepat belajar. Karya-karyanya selalu menarik.”</p></div>
      </div>
    </section>

  </main>

  <!-- FOOTER -->
  <footer>
    <div class="container footer-content">
      <div>© 2026 Della Aurellia · Made with <i class="fas fa-heart" style="color:#a07c5b;"></i></div>
      <div class="footer-social">
        <a href="#"><i class="fab fa-instagram"></i></a>
        <a href="#"><i class="fab fa-tiktok"></i></a>
        <a href="#"><i class="fab fa-youtube"></i></a>
        <a href="#"><i class="fab fa-linkedin"></i></a>
      </div>
    </div>
  </footer>

  <!-- back to top -->
  <button id="backTop" aria-label="Kembali ke atas"><i class="fas fa-arrow-up"></i></button>

  <script>
    // preloader
    window.addEventListener('load', () =>
