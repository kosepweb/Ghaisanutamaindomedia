<!DOCTYPE html>
<html lang="id">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ghaisan Utama Indomedia</title>
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #eaeaea;
            color: #333;
            line-height: 1.6;
        }

        nav {
            background-color: #1d1d1d;
            color: #fff;
            padding: 15px 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            transition: background-color 0.3s;
        }

        nav.scrolled {
            background-color: #333;
        }

        nav .logo {
            font-size: 2rem;
            font-weight: bold;
            letter-spacing: 1px;
            color: #ff6f61;
        }

        nav ul {
            list-style: none;
            display: flex;
            gap: 20px;
        }

        nav ul li a {
            color: #fff;
            text-decoration: none;
            font-weight: bold;
            transition: color 0.3s, transform 0.3s;
        }

        nav ul li a:hover {
            color: #ff6f61;
            transform: scale(1.05);
        }

        /* Hamburger menu for small screens */
        .hamburger {
            display: none;
            flex-direction: column;
            gap: 5px;
            cursor: pointer;
        }

        .hamburger div {
            width: 25px;
            height: 3px;
            background-color: #fff;
            transition: 0.3s;
        }

        .nav-links {
            display: flex;
            gap: 20px;
        }

        .nav-links.active {
            display: block;
            position: absolute;
            top: 70px;
            left: 0;
            background-color: #1d1d1d;
            width: 100%;
            text-align: center;
            flex-direction: column;
        }

        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)),
                url('foto1.jpg') no-repeat center center/cover;
            height: 100vh;
            color: #fff;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 800px;
            padding: 20px;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            margin: 0;
            padding: 0;
            line-height: 1.2;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
        }

        .hero-content p {
            font-size: 1.4rem;
            margin-top: 20px;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.5);
        }

        .container {
            max-width: 1200px;
            margin: auto;
            padding: 20px;
        }

        .section {
            padding: 80px 20px;
            position: relative;
        }

        .section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: #fff;
            transform: skewY(-4deg);
            transform-origin: top left;
            z-index: -1;
            clip-path: polygon(0 0, 100% 0, 100% 100%, 0 95%);
        }

        h2 {
            text-align: center;
            font-size: 2.8rem;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
            color: #ff6f61;
        }

        h2::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: #ff6f61;
            margin: 10px auto 0;
            border-radius: 2px;
        }

        .timeline {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .timeline-item {
            position: relative;
            padding: 20px;
            border-left: 4px solid #ff6f61;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        .timeline-item h3 {
            font-size: 1.5rem;
            margin-bottom: 10px;
            color: #333;
        }

        .timeline-item p {
            margin: 0;
            color: #666;
        }

        .services-cards {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
        }

        .card {
            background-color: #fff;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            text-align: center;
            flex: 1 1 calc(33% - 40px);
            margin: 20px;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .card:hover {
            transform: scale(1.05);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
        }

        .card h3 {
            margin-bottom: 15px;
            font-size: 1.6rem;
            color: #333;
        }

        .portfolio-gallery {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: nowrap;
            overflow-x: auto;
        }

        .gallery-item {
            flex: 0 0 auto;
            text-align: center;
            margin: 0;
        }

        .gallery-item img {
            width: 150px;
            height: 150px;
            object-fit: contain;
            border-radius: 10px;
            transition: transform 0.3s;
        }

        .gallery-item img:hover {
            transform: scale(1.05);
        }

        footer {
            background-color: #1d1d1d;
            color: #fff;
            text-align: center;
            padding: 20px 0;
        }

        .footer-socials {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 10px;
        }

        .footer-socials a {
            color: #fff;
            text-decoration: none;
            font-size: 1.5rem;
            transition: color 0.3s;
        }

        .footer-socials a:hover {
            color: #ff6f61;
        }

        iframe {
            border: 0;
        }

        /* Modal styles */
        .modal {
            display: none;
            position: fixed;
            z-index: 1001;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0, 0, 0, 0.9);
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            justify-content: center;
            max-width: 90%;
            margin: auto;
        }

        .modal-content img {
            max-width: 45%;
            border-radius: 10px;
            margin: 10px;
            transition: transform 0.3s;
        }

        .modal-content img:hover {
            transform: scale(1.05);
        }

        .close {
            position: absolute;
            top: 20px;
            right: 35px;
            color: #fff;
            font-size: 40px;
            font-weight: bold;
            transition: 0.3s;
            cursor: pointer;
        }

        .close:hover,
        .close:focus {
            color: #ff6f61;
            text-decoration: none;
            cursor: pointer;
        }

        @media only screen and (max-width: 768px) {
            nav ul {
                flex-direction: column;
                align-items: center;
                gap: 10px;
            }

            .nav-links {
                display: none;
                flex-direction: column;
                align-items: center;
                gap: 10px;
                position: absolute;
                top: 60px;
                left: 0;
                right: 0;
                background-color: #333;
                padding: 20px;
                box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            }

            .nav-links.open {
                display: flex;
            }

            .hamburger {
                display: flex;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .hero-content p {
                font-size: 1.2rem;
            }

            .timeline {
                gap: 15px;
            }

            .card {
                flex: 1 1 calc(100% - 40px);
            }

            .portfolio-gallery {
                flex-wrap: wrap;
                justify-content: space-around;
            }

            .gallery-item {
                flex: 1 1 calc(50% - 20px);
            }

            .modal-content img {
                max-width: 100%;
            }
        }
    </style>
</head>

<body>
    <nav>
        <div class="logo">Ghaisan Utama Indomedia</div>
        <div class="hamburger" onclick="toggleMenu()">
            <div></div>
            <div></div>
            <div></div>
        </div>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#about">Tentang Kami</a></li>
            <li><a href="#services">Layanan</a></li>
            <li><a href="#portfolio">Portofolio</a></li>
            <li><a href="#contact">Kontak</a></li>
        </ul>
    </nav>

    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Selamat Datang di Ghaisan Utama Indomedia</h1>
            <p>Kami menghadirkan solusi kreatif untuk kebutuhan bisnis Anda.</p>
        </div>
    </section>

    <section id="about" class="section">
        <div class="container">
            <h2>Tentang Kami</h2>
            <p>Kami adalah perusahaan yang bergerak di bidang digital marketing, desain grafis, dan pengembangan
                web.</p>
        </div>
    </section>

    <section id="services" class="section">
        <div class="container">
            <h2>Layanan Kami</h2>
            <div class="services-cards">
                <div class="card">
                    <h3>Desain Grafis</h3>
                    <p>Kami menyediakan layanan desain grafis yang menarik untuk kebutuhan promosi Anda.</p>
                </div>
                <div class="card">
                    <h3>Pembuatan Website</h3>
                    <p>Kami membuat website yang responsif dan user-friendly untuk bisnis Anda.</p>
                </div>
                <div class="card">
                    <h3>Digital Marketing</h3>
                    <p>Kami membantu meningkatkan visibilitas online bisnis Anda melalui strategi pemasaran digital.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="portfolio" class="section">
        <div class="container">
            <h2>Portofolio Kami</h2>
            <div class="portfolio-gallery">
                <div class="gallery-item">
                    <img src="finisia.png" alt="Project 1 Logo" onclick="openModal()">
                </div>
                <div class="gallery-item">
                    <img src="finisia2.png" alt="Project 2 Logo" onclick="openModal()">
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="section">
        <div class="container">
            <h2>Kontak Kami</h2>
            <p>Email: info@ghaisanutama.com</p>
            <p>WhatsApp: +62 812 3456 7890</p>
        </div>
    </section>

    <footer>
        <p>© 2024 Ghaisan Utama Indomedia. All rights reserved.</p>
        <div class="footer-socials">
            <a href="https://wa.me/6281234567890" target="_blank">WhatsApp</a>
            <a href="https://www.instagram.com/ghaisanutama" target="_blank">Instagram</a>
            <a href="mailto:info@ghaisanutama.com">Email</a>
        </div>
    </footer>

    <div id="portfolioModal" class="modal">
        <span class="close" onclick="closeModal()">&times;</span>
        <div class="modal-content">
            <img src="finisia.png" alt="Portfolio 1">
            <img src="finisia2.png" alt="Portfolio 2">
        </div>
    </div>

    <script>
        // Navbar scroll change
        window.onscroll = function () {
            const navbar = document.querySelector('nav');
            if (window.pageYOffset > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        };

        // Toggle menu
        function toggleMenu() {
            const navLinks = document.querySelector('.nav-links');
            navLinks.classList.toggle('open');
        }

        // Modal handling
        function openModal() {
            document.getElementById("portfolioModal").style.display = "flex";
        }

        function closeModal() {
            document.getElementById("portfolioModal").style.display = "none";
        }
    </script>
</body>

</html>
