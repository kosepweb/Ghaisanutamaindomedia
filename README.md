
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
    flex-wrap: nowrap; /* Mencegah logo berpindah ke baris berikutnya */
    overflow-x: auto; /* Menambahkan scroll horizontal jika jumlah logo melebihi lebar layar */
}

.gallery-item {
    flex: 0 0 auto; /* Mencegah item mengecil */
    text-align: center;
    margin: 0;
}

.gallery-item img {
    width: 150px; /* Atur lebar logo */
    height: 150px; /* Atur tinggi logo */
    object-fit: contain; /* Menjaga proporsi logo dengan penyesuaian ukuran */
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
    </style>
</head>

<body>
    <!-- Navigation -->
    <nav id="navbar">
        <div class="logo">Ghaisan Utama Indomedia</div>
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">Tentang Kami</a></li>
            <li><a href="#services">Layanan</a></li>
            <li><a href="#portfolio">Portofolio</a></li>
            <li><a href="#contact">Kontak</a></li>
            <li><a href="#legalitas">Legalitas</a></li>
        </ul>
    </nav>

    <!-- Home Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1></h1>
            <p></p>
        </div>
    </section>

    <section id="about" class="section about">
        <div class="container">
            <h2>About Us</h2>
            <div class="timeline">
                <div class="timeline-item">
                    <h3>2009</h3>
                    <p>Pada tahun 2009, bendera ALPRODUCTION beralih menjadi perusahaan perseorangan. Berfokus pada bidang Event Organizer dan Profesional Exhibition Organizer, kami memulai perjalanan ini dengan pengalaman, kemampuan, dan keterampilan sumber daya manusia yang terlibat sejak awal, sehingga dapat bekerja dengan baik.</p>
                </div>
                <div class="timeline-item">
                    <h3>2011</h3>
                    <p>Bisnis berkembang ke berbagai bidang. Pada tahun 2011, terbentuk Media Majalah, Eventku Magazine.</p>
                </div>
                <div class="timeline-item">
                    <h3>2012</h3>
                    <p>Terbentuk designeRoom, Konsultan Perencana & Konstruksi, Konsultan Pengawasan, Pelaksana Konstruksi, Pengelolaan Real Estate, Pekerjaan Interior/Eksterior.</p>
                </div>
                <div class="timeline-item">
                    <h3>2013</h3>
                    <p>Terbentuk CV. Ghaisan Utama Indomedia yang menaungi berbagai jenis usaha di bidang entertaind dan konstruksi.</p>
                </div>
                <div class="timeline-item">
                    <h3>2014</h3>
                    <p>Terbentuk jasa Multimedia (Photo, Video & Design Grafis).</p>
                </div>
                <div class="timeline-item">
                    <h3>2015</h3>
                    <p>Terbentuk Finisia Production, Production House yang memproduksi Film Layar lebar, Series & Iklan Cinematography.</p>
                </div>
                <div class="timeline-item">
                    <h3>2018</h3>
                    <p>Terbentuk Kopi Batas (KOBA), PT. Ghaisan Maharga Perkasa & PT. Ghaisan Utama Indoprima.</p>
                </div>
                <div class="timeline-item">
                    <h3>2020</h3>
                    <p>Terbentuk Yayasan Insan Sahasra Zawawi, dengan brand Gerakan 1.000 Kebaikan. Kami berkomitmen memberikan pelayanan produk dan jasa yang berkualitas, konsisten, dan memiliki nilai tambah demi tercapainya tujuan bersama. Dengan dukungan sumber daya manusia yang berkemampuan tinggi dan berpengalaman di bidang masing-masing, Ghaisan Utama Indomedia mampu menyediakan berbagai jasa di bidang Konstruksi, Multimedia, & Event Organizer dengan prinsip kemitraan yang selalu mengedepankan kualitas dan kepuasan (Value of Money).</p>
                </div>
            </div>
        </div>
    </section>
    

    <section id="services" class="section services">
        <div class="container">
            <h2>VISI, MISI & SERVICES</h2>
            <div class="services-cards">
                <div class="card">
                    <h3>VISI</h3>
                    <p>Menjadi Pemimpin Industri Kreatif di Indonesia Timur</p>
                </div>
                <div class="card">
                    <h3>MISI</h3>
                    <p>Menjadi parner bisnis yang Realible dengan menanamkan nilai Profesionalisme dalam menciptakan karya yang mengesankan</p>
                </div>
                <div class="card">
                    <img src="icon2.png" alt="Layanan 1 Icon" style="width: 200px; height: 100px;">
                    <h3>Event Organizer Services</h3>
                    <p>DIdirikan tahun 2009, dan sampai sekarang telah menjadi partner terpercaya oleh banyak perusahaan dan pribadi, untuk keperluan event organizing. Mulai dari acara formal ataupun non-formal yang selalu berhasil meninggalkan kesan tersendiri bagi client</p>
                </div>
                <div class="card">
                    <img src="icon23.png" alt="Layanan 2 Icon" style="width: 200px; height: 100px;">
                    <h3>Contruction Services</h3>
                    <p>Didirikan ditahun 2012 sampai sekarang, didukung tim teknis dan arsitek berpengalaman, menjadi Konsultan Perencanaan serta Pelaksanaan Konstruksi Perumahaan, Pengelolaan Real Estate, Renovasi Rumah dan Kantor Eksterior/Interior</p>
                </div>
                <div class="card">
                    <img src="icon3.png" alt="Layanan 3 Icon" style="width: 200px; height: 100px;">
                    <h3>Cinematography Services</h3>
                    <p>Didirikan ditahun 2015, dan sampai sekarang telah membuat beberapa film layar lebar dengan jumlah penoton yang lebih dari lima ratus ribu orang. Disamping itu Finisia, juga telah memproduksi beberapa video, berupa compay profile, comercial dan lain-lain.</p>
                </div>
            </div>
        </div>
    </section>
    

    <!-- Portfolio Section -->
    <section id="portfolio" class="section portfolio">
        <div class="container">
            <h2>Portofolio</h2>
            <div class="portfolio-gallery">
                <!-- Project 1 -->
                <div class="gallery-item">
                    <img id="projectLogo1" src="finisia.png" alt="Project 1 Logo">
                </div>
                <!-- Project 2 -->
                <div class="gallery-item">
                    <img id="projectLogo2" src="LOGO-ALPRO1.png" alt="Project 2 Logo">
                </div>
                <!-- Project 3 -->
                <div class="gallery-item">
                    <img id="projectLogo3" src="drlogo.png" alt="Project 3 Logo">
                </div>
            </div>
        </div>
    </section>

  <!-- Contact Section -->
  <section id="contact" class="section contact">
    <div class="container">
        <h2>Kontak Kami</h2>
        <p>Untuk informasi lebih lanjut atau konsultasi, silakan hubungi kami melalui:</p>
        <ul>
            <li>Email: <a href="mailto:gumedia.po@gmail.com">info@ghaisanindomedia.com</a></li>
            <li>Telepon: <a href="tel:+621234567890">+62 123-4567-890</a></li>
            <li>Alamat: Jl. Bakti Komp Ruko Bakti soho center, Kota Makassar, Sulawesi Selatan</li>
        </ul>
    </div>
</section>
<footer>
    <p>&copy; 2009-2024 Ghaisan Utama Indomedia. All rights reserved.</p>
    <div class="footer-socials">
        <a href="#">Instagram</a>
        <a href="#">Facebook</a>
        <a href="https://wa.me/621234567890" target="_blank">WhatsApp</a>
    </div>
</footer>


    <!-- Modal for Gallery 1 -->
    <div id="galleryModal1" class="modal">
        <span class="close">&times;</span>
        <div class="modal-content">
            <img src="up1.jpg" alt="Image 1">
            <img src="halomakassar.jpg" alt="Image 2">
            <img src="anakmudapalsu.jpg" alt="Image 3">
            <img src="keluarmain.jpg" alt="Image 4">
            <img src="up2.jpg" alt="Image 5">
        </div>
    </div>

    <!-- Modal for Gallery 2 -->
    <div id="galleryModal2" class="modal">
        <span class="close">&times;</span>
        <div class="modal-content">
            <img src="giias15.jpg" alt="Image 1">
            <img src="giias16.jpg" alt="Image 2">
            <img src="GIIAS17.jpg" alt="Image 3">
            <img src="GIIAS18.jpg" alt="Image 4">
            <img src="giias19.jpg" alt="Image 5">
            <img src="rei.jpg" alt="Image 5">
            <img src="karangtaruna.jpg" alt="Image 5">
            <img src="FEED BMO 1 copy.jpg" alt="Image 5">
        </div>
    </div>

    <!-- Modal for Gallery 3 -->
    <div id="galleryModal3" class="modal">
        <span class="close">&times;</span>
        <div class="modal-content">
            <img src="dr1.jpg" alt="Image 1">
            <img src="dr2.jpg" alt="Image 2">
            <img src="dr3.jpg" alt="Image 3">
            <img src="dr4.jpg" alt="Image 4">
            <img src="dr5.jpg" alt="Image 5">
            <img src="dr6.jpg" alt="Image 4">
        </div>
    </div>

    <script>
        // Navbar scroll effect
        window.onscroll = function () {
            var navbar = document.getElementById('navbar');
            if (window.pageYOffset > 100) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        };

        // Function to open modal for each project
        function openModal(modalId) {
            var modal = document.getElementById(modalId);
            modal.style.display = 'flex';
        }

        // Function to close modal
        var closeButtons = document.getElementsByClassName('close');
        for (var i = 0; i < closeButtons.length; i++) {
            closeButtons[i].onclick = function () {
                this.parentElement.style.display = 'none';
            };
        }

        // Close modal if user clicks anywhere outside of the modal content
        window.onclick = function (event) {
            if (event.target.classList.contains('modal')) {
                event.target.style.display = 'none';
            }
        }

        // Add event listeners to the project logos
        document.getElementById('projectLogo1').addEventListener('click', function () {
            openModal('galleryModal1');
        });
        document.getElementById('projectLogo2').addEventListener('click', function () {
            openModal('galleryModal2');
        });
        document.getElementById('projectLogo3').addEventListener('click', function () {
            openModal('galleryModal3');
        });
    </script>
</body>

</html>
