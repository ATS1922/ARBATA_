<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Konsultan Transportasi Darat - PT. ARBATA SERAYA ADIGUNA</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700;800&family=Open+Sans:wght@400;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* CSS VARIABEL & RESET */
        :root {
            --primary-dark: #0b1120;
            --secondary-dark: #1e293b;
            --accent-teal: #0d9488;
            --accent-gold: #d4af37;
            --text-light: #f8fafc;
            --text-muted: #94a3b8;
            --bg-light: #f8fafc;
            --glass-bg: rgba(15, 23, 42, 0.85);
            --glass-border: rgba(255, 255, 255, 0.1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth; /* Smooth Scroll */
            scroll-padding-top: 80px;
        }

        body {
            font-family: 'Open Sans', sans-serif;
            color: var(--text-light);
            background-color: var(--primary-dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        h1, h2, h3, h4 {
            font-family: 'Montserrat', sans-serif;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        /* ANIMASI REVEAL */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* NAVBAR (Glassmorphism & Sticky) */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            background: var(--glass-bg);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            z-index: 1000;
            border-bottom: 1px solid var(--glass-border);
            padding: 15px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: all 0.3s ease;
        }

        header.scrolled {
            padding: 10px 5%;
            background: rgba(11, 17, 32, 0.95);
        }

        .logo-container {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo-img {
            height: 45px;
            width: auto;
            object-fit: contain;
            /* Jika logo belum ada, tampilkan teks fallback */
        }

        .nav-links {
            display: flex;
            gap: 25px;
            align-items: center;
        }

        .nav-links a {
            font-size: 14px;
            font-weight: 600;
            transition: color 0.3s;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent-gold);
            transition: width 0.3s;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-links a:hover {
            color: var(--accent-gold);
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--accent-gold), #b5952f);
            color: var(--primary-dark);
            padding: 10px 24px;
            border-radius: 50px;
            font-weight: 700;
            font-size: 14px;
            transition: transform 0.3s, box-shadow 0.3s;
            box-shadow: 0 4px 15px rgba(212, 175, 55, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(212, 175, 55, 0.5);
        }

        .menu-toggle {
            display: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--text-light);
        }

        /* HERO SECTION */
        .hero {
            height: 100vh;
            min-height: 650px;
            background: linear-gradient(135deg, rgba(11, 17, 32, 0.9) 0%, rgba(11, 17, 32, 0.7) 100%), url('https://images.unsplash.com/photo-1541888946425-d81bb19240f5?q=80&w=2070&auto=format&fit=crop') center/cover;
            display: flex;
            align-items: center;
            padding: 0 5%;
            position: relative;
            margin-top: 0;
        }

        .hero-content {
            display: flex;
            justify-content: space-between;
            width: 100%;
            align-items: flex-end;
            padding-bottom: 50px;
            padding-top: 100px;
            gap: 40px;
        }

        .hero-text {
            max-width: 60%;
        }

        .hero-subtitle {
            color: var(--accent-gold);
            font-weight: 700;
            letter-spacing: 3px;
            font-size: 13px;
            margin-bottom: 20px;
            display: inline-block;
            background: rgba(212, 175, 55, 0.1);
            padding: 5px 15px;
            border-radius: 50px;
            border: 1px solid rgba(212, 175, 55, 0.3);
        }

        .hero-text h1 {
            font-size: 4.5rem;
            line-height: 1.05;
            margin-bottom: 25px;
            text-transform: uppercase;
            text-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }

        .hero-text h1 span {
            color: var(--accent-gold);
        }

        .hero-text p {
            color: var(--text-muted);
            font-size: 1.1rem;
            margin-bottom: 35px;
            max-width: 600px;
            line-height: 1.8;
        }

        .hero-buttons {
            display: flex;
            gap: 20px;
        }

        .btn-outline {
            background: rgba(255, 255, 255, 0.05);
            color: var(--text-light);
            padding: 10px 24px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 50px;
            font-weight: 600;
            font-size: 14px;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 8px;
            backdrop-filter: blur(5px);
        }

        .btn-outline:hover {
            background: var(--text-light);
            color: var(--primary-dark);
            border-color: var(--text-light);
        }

        .hero-stats {
            background: rgba(30, 41, 59, 0.5);
            backdrop-filter: blur(15px);
            -webkit-backdrop-filter: blur(15px);
            padding: 35px;
            border-radius: 16px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-left: 4px solid var(--accent-gold);
            min-width: 280px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
        }

        .stat-item {
            margin-bottom: 25px;
        }

        .stat-item:last-child {
            margin-bottom: 0;
        }

        .stat-number {
            font-size: 2.2rem;
            font-weight: 800;
            font-family: 'Montserrat', sans-serif;
            background: linear-gradient(to right, #fff, #94a3b8);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .stat-label {
            font-size: 0.9rem;
            color: var(--text-muted);
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* QUICK NAV / SBU BAR */
        .quick-nav {
            background: var(--secondary-dark);
            display: flex;
            justify-content: space-around;
            padding: 25px 5%;
            flex-wrap: wrap;
            gap: 15px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
        }

        .quick-nav-item {
            display: flex;
            align-items: center;
            gap: 12px;
            font-size: 0.95rem;
            font-weight: 600;
            color: var(--text-muted);
            transition: all 0.3s;
            padding: 8px 16px;
            border-radius: 8px;
            cursor: pointer;
        }

        .quick-nav-item:hover {
            color: var(--accent-gold);
            background: rgba(255, 255, 255, 0.05);
            transform: translateY(-3px);
        }

        .quick-nav-item i {
            color: var(--accent-gold);
            font-size: 1.3rem;
        }

        /* ABOUT SECTION */
        .about {
            background-color: #ffffff;
            color: var(--primary-dark);
            padding: 100px 5%;
            position: relative;
        }

        .about-container {
            display: flex;
            gap: 60px;
            align-items: center;
            max-width: 1400px;
            margin: 0 auto;
        }

        .about-text {
            flex: 1;
        }

        .section-tag {
            color: var(--accent-teal);
            font-weight: 700;
            font-size: 0.9rem;
            letter-spacing: 2px;
            display: block;
            margin-bottom: 15px;
            text-transform: uppercase;
        }

        .about-text h2 {
            font-size: 2.8rem;
            margin-bottom: 25px;
            color: var(--primary-dark);
            line-height: 1.2;
        }

        .about-text p {
            color: #475569;
            margin-bottom: 20px;
            font-size: 1.05rem;
            line-height: 1.8;
        }

        .address-box {
            background: var(--bg-light);
            padding: 25px;
            border-left: 5px solid var(--accent-teal);
            margin: 30px 0;
            border-radius: 0 12px 12px 0;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }

        .address-box p {
            margin-bottom: 8px;
            font-size: 1rem;
            color: var(--primary-dark);
        }

        .about-image {
            flex: 1;
            height: 500px;
            background: url('https://images.unsplash.com/photo-1503387762-592deb58ef4e?q=80&w=2031&auto=format&fit=crop') center/cover;
            border-radius: 16px;
            position: relative;
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }

        .about-image::after {
            content: '';
            position: absolute;
            inset: 0;
            border-radius: 16px;
            border: 2px solid rgba(13, 148, 136, 0.3);
            pointer-events: none;
        }

        /* SBU SECTION */
        .sbu-section {
            padding: 100px 5%;
            background-color: var(--primary-dark);
            color: var(--text-light);
        }

        .sbu-header {
            text-align: center;
            margin-bottom: 60px;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }

        .sbu-header .section-tag {
            color: var(--accent-gold);
        }

        .sbu-header h2 {
            font-size: 2.8rem;
            margin-bottom: 20px;
            color: #fff;
        }

        .sbu-header p {
            color: var(--text-muted);
            font-size: 1.1rem;
        }

        .sbu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
            max-width: 1400px;
            margin: 0 auto;
        }

        .sbu-card {
            background: var(--secondary-dark);
            padding: 35px;
            border-radius: 16px;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            border: 1px solid rgba(255, 255, 255, 0.05);
            position: relative;
            overflow: hidden;
        }

        .sbu-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, var(--accent-teal), var(--accent-gold));
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.4s;
        }

        .sbu-card:hover::before {
            transform: scaleX(1);
        }

        .sbu-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
            border-color: rgba(255, 255, 255, 0.15);
        }

        .sbu-code {
            font-size: 1.8rem;
            font-weight: 800;
            color: var(--accent-gold);
            margin-bottom: 15px;
            font-family: 'Montserrat', sans-serif;
            display: inline-block;
            padding: 5px 15px;
            background: rgba(212, 175, 55, 0.1);
            border-radius: 8px;
        }

        .sbu-card h3 {
            font-size: 1.2rem;
            margin-bottom: 15px;
            color: #fff;
            line-height: 1.4;
        }

        .sbu-card p {
            font-size: 0.95rem;
            color: var(--text-muted);
            line-height: 1.7;
        }

        /* FOOTER */
        footer {
            background-color: #05080f;
            padding: 60px 5% 30px;
            text-align: center;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
        }

        .footer-logo {
            height: 60px;
            margin-bottom: 25px;
            object-fit: contain;
        }

        .footer-text {
            color: var(--text-muted);
            font-size: 0.95rem;
            margin-bottom: 15px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .footer-bottom {
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            padding-top: 25px;
            margin-top: 40px;
            font-size: 0.85rem;
            color: #475569;
        }

        /* RESPONSIVE DESIGN */
        @media (max-width: 992px) {
            .hero-text h1 {
                font-size: 3.5rem;
            }
            .hero-content {
                flex-direction: column;
                align-items: flex-start;
                gap: 50px;
                padding-top: 120px;
                padding-bottom: 80px;
            }
            .hero-text {
                max-width: 100%;
            }
            .hero-stats {
                width: 100%;
                display: grid;
                grid-template-columns: 1fr 1fr;
                gap: 25px;
            }
            .about-container {
                flex-direction: column;
            }
            .about-image {
                width: 100%;
                height: 400px;
            }
        }

        @media (max-width: 768px) {
            .menu-toggle {
                display: block;
            }
            .nav-links {
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background: var(--glass-bg);
                backdrop-filter: blur(15px);
                flex-direction: column;
                padding: 30px;
                display: none;
                gap: 20px;
                box-shadow: 0 20px 30px rgba(0,0,0,0.5);
                border-bottom: 1px solid var(--glass-border);
            }
            .nav-links.active {
                display: flex;
            }
            .hero-text h1 {
                font-size: 2.8rem;
            }
            .hero-stats {
                grid-template-columns: 1fr;
            }
            .quick-nav {
                flex-direction: column;
                align-items: stretch;
                gap: 10px;
            }
            .quick-nav-item {
                justify-content: flex-start;
            }
            .about-text h2 {
                font-size: 2.2rem;
            }
        }
    </style>
</head>
<body>

    <!-- HEADER / NAVBAR -->
    <header id="header">
        <div class="logo-container">
            <!-- PASTIKAN FILE LOGO BERNAMA 'logo.png' ADA DI FOLDER YANG SAMA -->
            <img src="logo.png" alt="PT. ARBATA SERAYA ADIGUNA" class="logo-img" onerror="this.style.display='none'; this.parentElement.innerHTML='<span style=\'color:var(--accent-gold); font-weight:800; font-size:1.2rem; letter-spacing:1px;\'>PT. ARBATA</span>'">
        </div>
        <div class="menu-toggle" id="mobile-menu">
            <i class="fas fa-bars"></i>
        </div>
        <nav class="nav-links" id="nav-links">
            <a href="#home">Home</a>
            <a href="#about">Tentang Kami</a>
            <a href="#sbu">Lingkup SBU</a>
            <a href="#kontak">Kontak</a>
            <a href="#kontak" class="btn-primary">Hubungi Kami</a>
        </nav>
    </header>

    <!-- HERO SECTION -->
    <section class="hero" id="home">
        <div class="hero-content">
            <div class="hero-text reveal">
                <span class="hero-subtitle">KONSULTAN TRANSPORTASI DARAT</span>
                <h1>Solusi <span>Rekayasa & Desain</span> Infrastruktur Masa Depan</h1>
                <p>Direktori Konstruksi — Profil perusahaan PT. ARBATA SERAYA ADIGUNA. Ringkasan identitas badan usaha, cakupan subklasifikasi SBU yang tercatat, serta referensi publik untuk penilaian awal mitra atau penyedia.</p>
                <div class="hero-buttons">
                    <a href="#sbu" class="btn-primary">Lingkup Pekerjaan <i class="fas fa-arrow-right" style="margin-left:5px;"></i></a>
                    <a href="#about" class="btn-outline"><i class="fas fa-play"></i> Profil Perusahaan</a>
                </div>
            </div>
            <div class="hero-stats reveal">
                <div class="stat-item">
                    <div class="stat-number">6</div>
                    <div class="stat-label">Subklasifikasi SBU</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">Bekasi</div>
                    <div class="stat-label">Lokasi Operasional</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">Konsultan</div>
                    <div class="stat-label">Kategori Usaha</div>
                </div>
            </div>
        </div>
    </section>

    <!-- QUICK NAV / ICON BAR -->
    <div class="quick-nav reveal">
        <div class="quick-nav-item"><i class="fas fa-drafting-compass"></i> Desain Rekayasa</div>
        <div class="quick-nav-item"><i class="fas fa-road"></i> Teknik Sipil Transportasi</div>
        <div class="quick-nav-item"><i class="fas fa-water"></i> Teknik Sipil Air</div>
        <div class="quick-nav-item"><i class="fas fa-building"></i> Struktur Bangunan</div>
        <div class="quick-nav-item"><i class="fas fa-hard-hat"></i> Konsultansi Konstruksi</div>
    </div>

    <!-- ABOUT SECTION -->
    <section class="about" id="about">
        <div class="about-container">
            <div class="about-text reveal">
                <span class="section-tag">TENTANG PT. ARBATA SERAYA ADIGUNA</span>
                <h2>Membangun Konektivitas yang Berkelanjutan</h2>
                <p>Kami adalah perusahaan konsultan yang berfokus pada penyediaan jasa desain rekayasa, nasihat, dan konsultansi di bidang konstruksi dan transportasi darat. Kami berkomitmen untuk memberikan hasil kerja yang presisi, inovatif, dan sesuai dengan standar regulasi yang berlaku.</p>
                <p><em>Data disajikan secara informatif berdasarkan sumber terbuka dan pembaruan platform; keabsahan administratif harus dibuktikan melalui dokumen asli dan prosedur resmi yang berlaku.</em></p>
                
                <div class="address-box">
                    <p><strong><i class="fas fa-map-marker-alt" style="color: var(--accent-teal); margin-right:8px;"></i> Alamat Kantor:</strong></p>
                    <p>Jl. Tengah No.69, RT.001/RW.006, Cimuning, Kec. Mustika Jaya, Kota Bks, Jawa Barat 17155, Indonesia.</p>
                </div>
            </div>
            <div class="about-image reveal"></div>
        </div>
    </section>

    <!-- SBU SECTION -->
    <section class="sbu-section" id="sbu">
        <div class="sbu-header reveal">
            <span class="section-tag">KONTEKS BIDANG PEKERJAAN</span>
            <h2>Subklasifikasi SBU Tercatat</h2>
            <p>Berikut adalah 6 (enam) subklasifikasi yang terdaftar pada perusahaan kami beserta ringkasan lingkup pekerjaan.</p>
        </div>

        <div class="sbu-grid">
            <!-- RE108 -->
            <div class="sbu-card reveal">
                <div class="sbu-code">RE108</div>
                <h3>Jasa Desain Rekayasa Lainnya</h3>
                <p>Jasa desain rekayasa khusus lainnya. Termasuk desain rekayasa akustik dan vibrasi, sistem pengendalian lalu-lintas, pengembangan prototype dan desain detail dari produk baru serta jasa desain rekayasa khusus lainnya.</p>
            </div>

            <!-- RE107 -->
            <div class="sbu-card reveal">
                <div class="sbu-code">RE107</div>
                <h3>Jasa Nasehat dan Konsultansi Jasa Rekayasa Konstruksi</h3>
                <p>Jasa konsultansi di bidang jasa konstruksi yang meliputi jasa nasihat dalam pembinaan usaha dan kelembagaan, pembinaan penyelenggaraan dan pembinaan investasi konstruksi serta pembinaan kompetensi dan keahlian Tenaga Kerja Konstruksi oleh Pemerintah baik Pemerintah Pusat maupun Pusat.</p>
            </div>

            <!-- RE104 -->
            <div class="sbu-card reveal">
                <div class="sbu-code">RE104</div>
                <h3>Jasa Desain Rekayasa untuk Pekerjaan Teknik Sipil Transportasi</h3>
                <p>Jasa pembuatan desain rekayasa engineering untuk pekerjaan rekayasa sipil transportasi seperti jembatan, jalan layang, dan jalan raya. Jasa Desain meliputi salah satu dari kombinasi layanan berikut: perencanaan awal, estimasi biaya, dan spesifikasi dalam rangka menterjemahkan kon...</p>
            </div>

            <!-- RE103 -->
            <div class="sbu-card reveal">
                <div class="sbu-code">RE103</div>
                <h3>Jasa Desain Rekayasa untuk Pekerjaan Teknik Sipil Air</h3>
                <p>Jasa pembuatan desain rekayasa (engineering) untuk pekerjaan rekayasa sipil keairan seperti dam, catchment basins, sistem irigasi, pekerjaan pengendalian banjir, pelabuhan, pekerjaan penyaluran air dan sanitasi serta sistem saluran air limbah industri.</p>
            </div>

            <!-- RE102 -->
            <div class="sbu-card reveal">
                <div class="sbu-code">RE102</div>
                <h3>Jasa Desain Rekayasa untuk Konstruksi Pondasi serta Struktur Bangunan</h3>
                <p>Jasa desain rekayasa struktur untuk load bearing framework dari bangunan perumahan dan komersial, bangunan institusi dan industrial. Jasa desain ini meliputi satu atau kombinasi dari kegiatan berikut: Estimasi biaya, spesifikasi dan rencana pendahuluan untuk mendefinisikan konsep...</p>
            </div>

            <!-- RE101 -->
            <div class="sbu-card reveal">
                <div class="sbu-code">RE101</div>
                <h3>Jasa Nasehat dan Konsultansi Rekayasa Teknik</h3>
                <p>Pekerjaaan yang dihandle oleh RE101 meliputi rekomendasi, nasihat dan asistensi mengenai rekayasa teknik, termasuk didalamnya melaksanakan studi kelayakan dan dampak dari proyek contohnya antara lain: Studi dampak topografi dan geologi dalam desain, konstruksi dan biaya dari jala...</p>
            </div>
        </div>
    </section>

    <!-- FOOTER -->
    <footer id="kontak">
        <!-- PASTIKAN FILE LOGO BERNAMA 'logo.png' ADA DI FOLDER YANG SAMA -->
        <img src="logo.png" alt="PT. ARBATA SERAYA ADIGUNA" class="footer-logo" onerror="this.style.display='none'">
        <p class="footer-text">Konsultan Transportasi Darat & Direktori Konstruksi</p>
        <p class="footer-text"><i class="fas fa-map-marker-alt" style="color: var(--accent-gold);"></i> Jl. Tengah No.69, Cimuning, Mustika Jaya, Kota Bekasi, Jawa Barat 17155</p>
        <div class="footer-bottom">
            <p>&copy; 2026 PT. ARBATA SERAYA ADIGUNA. All Rights Reserved.</p>
        </div>
    </footer>

    <!-- JAVASCRIPT UNTUK MOBILE MENU & ANIMASI -->
    <script>
        // 1. Mobile Menu Toggle
        const mobileMenu = document.getElementById('mobile-menu');
        const navLinks = document.getElementById('nav-links');

        mobileMenu.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            // Ganti ikon hamburger ke X
            const icon = mobileMenu.querySelector('i');
            if(navLinks.classList.contains('active')) {
                icon.classList.remove('fa-bars');
                icon.classList.add('fa-times');
            } else {
                icon.classList.remove('fa-times');
                icon.classList.add('fa-bars');
            }
        });

        // Menutup menu saat link diklik
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
                const icon = mobileMenu.querySelector('i');
                icon.classList.remove('fa-times');
                icon.classList.add('fa-bars');
            });
        });

        // 2. Sticky Header Effect on Scroll
        const header = document.getElementById('header');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });

        // 3. Scroll Reveal Animation (Animasi Muncul saat di-scroll)
        const revealElements = document.querySelectorAll('.reveal');

        const revealObserver = new IntersectionObserver((entries, observer) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('active');
                    observer.unobserve(entry.target); // Animasi hanya jalan sekali
                }
            });
        }, {
            threshold: 0.1, // Muncul saat 10% elemen terlihat
            rootMargin: "0px 0px -50px 0px"
        });

        revealElements.forEach(el => {
            revealObserver.observe(el);
        });
    </script>
</body>
</html>
