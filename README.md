#**Secangkir Kopi**
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Secangkir Kopi - Nikmati Rasa Sebenarnya</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
    
    <style>
        /* --- CSS VARIABLES & RESET --- */
        :root {
            --primary-color: #4b3621;
            --secondary-color: #d4a373;
            --bg-color: #faf7f2;
            --text-color: #333;
            --white: #ffffff;
            --border: 1px solid #ccc;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            outline: none;
            border: none;
            text-decoration: none;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            overflow-x: hidden; /* Mencegah scroll horizontal */
        }

        /* --- NAVBAR --- */
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.4rem 7%;
            background-color: rgba(255, 255, 255, 0.95);
            border-bottom: 1px solid #eee;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 9999;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        .navbar .logo {
            font-size: 2rem;
            font-weight: 700;
            color: var(--primary-color);
            font-family: 'Playfair Display', serif;
        }

        .navbar .logo span {
            color: var(--secondary-color);
        }

        .navbar .navbar-nav a {
            color: var(--text-color);
            display: inline-block;
            font-size: 1rem;
            margin: 0 1rem;
            font-weight: 500;
            transition: 0.3s;
        }

        .navbar .navbar-nav a:hover {
            color: var(--secondary-color);
            border-bottom: 2px solid var(--secondary-color);
        }

        .navbar-extra a {
            color: var(--text-color);
            margin: 0 0.5rem;
            font-size: 1.2rem;
            cursor: pointer;
        }

        .navbar-extra a:hover {
            color: var(--secondary-color);
        }

        #hamburger-menu {
            display: none;
        }

        /* --- SHOPPING CART SIDEBAR --- */
        .shopping-cart {
            position: fixed;
            top: 0;
            right: -100%; /* Sembunyi di kanan */
            height: 100vh;
            width: 35rem;
            padding: 2rem;
            background-color: var(--white);
            color: var(--text-color);
            z-index: 99999;
            transition: 0.3s;
            box-shadow: -2px 0 5px rgba(0,0,0,0.2);
            overflow-y: auto;
        }

        .shopping-cart.active {
            right: 0;
        }

        .shopping-cart h2 {
            font-family: 'Playfair Display', serif;
            margin-bottom: 2rem;
            text-align: center;
            color: var(--primary-color);
        }

        .cart-item {
            position: relative;
            margin: 1rem 0;
            display: flex;
            align-items: center;
            gap: 1.5rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid #eee;
        }

        .cart-item img {
            height: 80px;
            width: 80px;
            border-radius: 50%;
            object-fit: cover;
        }

        .cart-item h3 {
            font-size: 1.2rem;
            padding-bottom: 0.5rem;
        }

        .cart-item .item-price {
            font-size: 1rem;
            font-weight: bold;
        }

        .cart-item .remove-item {
            position: absolute;
            right: 0;
            cursor: pointer;
            color: #ff4d4d;
            font-size: 1.2rem;
        }

        .cart-total {
            margin-top: 2rem;
            text-align: center;
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--primary-color);
        }

        .checkout-btn {
            margin-top: 1rem;
            display: inline-block;
            width: 100%;
            padding: 1rem;
            background-color: var(--primary-color);
            color: var(--white);
            text-align: center;
            font-weight: bold;
            cursor: pointer;
            transition: 0.3s;
            border-radius: 5px;
        }

        .checkout-btn:hover {
            background-color: var(--secondary-color);
        }

        .close-cart {
            position: absolute;
            top: 1rem;
            left: 1rem;
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* --- HERO SECTION --- */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1497935586351-b67a49e012bf?ixlib=rb-1.2.1&auto=format&fit=crop&w=1351&q=80');
            background-repeat: no-repeat;
            background-size: cover;
            background-position: center;
            position: relative;
        }

        .hero .content {
            padding: 1.4rem 7%;
            max-width: 60rem;
        }

        .hero .content h1 {
            font-size: 3.5rem;
            color: var(--white);
            text-shadow: 1px 1px 3px rgba(1, 1, 3, 0.5);
            line-height: 1.2;
            font-family: 'Playfair Display', serif;
        }

        .hero .content h1 span {
            color: var(--secondary-color);
        }

        .hero .content p {
            font-size: 1.2rem;
            margin-top: 1rem;
            line-height: 1.6;
            font-weight: 300;
            color: var(--white);
            text-shadow: 1px 1px 3px rgba(1, 1, 3, 0.5);
        }

        .hero .content .cta {
            margin-top: 2rem;
            display: inline-block;
            padding: 1rem 3rem;
            font-size: 1.2rem;
            color: var(--white);
            background-color: var(--secondary-color);
            border-radius: 0.5rem;
            box-shadow: 1px 1px 3px rgba(1, 1, 3, 0.5);
            transition: 0.3s;
        }

        .hero .content .cta:hover {
            background-color: var(--primary-color);
        }

        /* --- ABOUT & MENU & CONTACT --- */
        .about, .menu, .contact {
            padding: 6rem 7% 2rem;
        }

        .about h2, .menu h2, .contact h2 {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: var(--primary-color);
            font-family: 'Playfair Display', serif;
        }

        .about h2 span, .menu h2 span, .contact h2 span {
            color: var(--secondary-color);
        }

        /* ABOUT STYLES */
        .row {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
        }

        .about .row .about-img {
            flex: 1 1 30rem;
        }

        .about .row .about-img img {
            width: 100%;
            border-radius: 10px;
        }

        .about .row .content {
            flex: 1 1 30rem;
            padding: 0 1rem;
        }

        .about .row .content h3 {
            font-size: 1.8rem;
            margin-bottom: 1rem;
        }

        .about .row .content p {
            margin-bottom: 1rem;
            font-size: 1rem;
            line-height: 1.6;
        }

        /* MENU STYLES */
        .menu-card-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .menu-card {
            background: var(--white);
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            overflow: hidden;
            text-align: center;
            transition: 0.3s;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .menu-card:hover {
            transform: translateY(-5px);
        }

        .menu-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .menu-card-content {
            padding: 1.5rem;
        }

        .menu-card h3 {
            font-size: 1.3rem;
            color: var(--primary-color);
            margin-bottom: 0.5rem;
        }

        .menu-card-price {
            font-weight: 700;
            color: var(--secondary-color);
            font-size: 1.2rem;
            margin-bottom: 1rem;
        }

        /* Tombol Add to Cart */
        .add-to-cart-btn {
            background-color: var(--primary-color);
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 20px;
            cursor: pointer;
            transition: 0.3s;
            font-size: 0.9rem;
            margin-top: 0.5rem;
        }

        .add-to-cart-btn:hover {
            background-color: var(--secondary-color);
        }
        
        .add-to-cart-btn i {
            margin-right: 5px;
        }

        /* CONTACT STYLES */
        .contact .row {
            align-items: center;
            background-color: var(--white);
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            overflow: hidden;
        }

        .contact .map {
            flex: 1 1 30rem;
            width: 100%;
            height: 400px;
            background-color: #ddd; 
        }

        .contact form {
            flex: 1 1 30rem;
            padding: 2rem;
            text-align: center;
        }

        .contact form .input-group {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
            background-color: var(--bg-color);
            border: 1px solid #ccc;
            border-radius: 5px;
            padding: 0.8rem;
        }

        .contact form .input-group input {
            width: 100%;
            padding-left: 1rem;
            background: none;
            font-size: 1rem;
        }
        
        .contact form .btn {
            margin-top: 1rem;
            display: inline-block;
            padding: 0.8rem 3rem;
            font-size: 1rem;
            color: var(--white);
            background-color: var(--primary-color);
            cursor: pointer;
            border-radius: 5px;
            transition: 0.3s;
        }

        /* FOOTER */
        footer {
            background-color: var(--primary-color);
            text-align: center;
            padding: 2rem 0;
            margin-top: 3rem;
        }

        footer .socials {
            padding-bottom: 1.5rem;
        }

        footer .socials a {
            color: var(--white);
            margin: 0.8rem;
            font-size: 1.5rem;
        }

        footer .socials a:hover {
            color: var(--secondary-color);
        }

        footer .links {
            margin-bottom: 1.5rem;
        }

        footer .links a {
            color: var(--white);
            padding: 0.7rem 1rem;
        }

        footer .credit {
            font-size: 0.9rem;
            color: var(--white);
        }

        /* MEDIA QUERIES */
        @media (max-width: 768px) {
            html {
                font-size: 80%;
            }

            #hamburger-menu {
                display: inline-block;
            }

            .navbar .navbar-nav {
                position: absolute;
                top: 100%;
                right: -100%;
                background-color: var(--white);
                width: 70%;
                height: 100vh;
                transition: 0.3s;
                border-left: 1px solid #ccc;
            }

            .navbar .navbar-nav.active {
                right: 0;
            }

            .navbar .navbar-nav a {
                display: block;
                margin: 1.5rem;
                padding: 0.5rem;
                font-size: 1.5rem;
            }
            
            .shopping-cart {
                width: 100%;
            }
        }
    </style>
</head>
<body>

    <nav class="navbar">
        <a href="#" class="logo">Secangkir<span>Kopi</span>.</a>

        <div class="navbar-nav">
            <a href="#home">Home</a>
            <a href="#about">Tentang Kami</a>
            <a href="#menu">Menu</a>
            <a href="#contact">Kontak</a>
        </div>

        <div class="navbar-extra">
            <a href="#" id="shopping-cart-button"><i class="fas fa-shopping-cart"></i></a>
            <a href="#" id="hamburger-menu"><i class="fas fa-bars"></i></a>
        </div>
    </nav>

    <div class="shopping-cart" id="shopping-cart">
        <div class="close-cart" id="close-cart"><i class="fas fa-times"></i></div>
        <h2>Keranjang Belanja</h2>
        
        <div id="cart-items-container">
            <p style="text-align:center; margin-top:20px; color:#666;">Keranjang masih kosong.</p>
        </div>

        <div class="cart-total">
            Total: <span id="cart-total-price">IDR 0</span>
        </div>
        <div class="checkout-btn" onclick="checkout()">Checkout Sekarang</div>
    </div>

    <section class="hero" id="home">
        <main class="content">
            <h1>Awali Harimu Dengan <span>Secangkir Kopi</span></h1>
            <p>Rasakan kenikmatan biji kopi pilihan yang dipetik langsung dari petani lokal terbaik. Aroma yang menenangkan untuk jiwa yang lelah.</p>
            <a href="#menu" class="cta">Beli Sekarang</a>
        </main>
    </section>

    <section class="about" id="about">
        <h2><span>Tentang</span> Kami</h2>
        <div class="row">
            <div class="about-img">
                <img src="https://images.unsplash.com/photo-1442512595367-4273253ae50b?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Tentang Kami">
            </div>
            <div class="content">
                <h3>Kenapa Memilih Kopi Kami?</h3>
                <p>Secangkir Kopi hadir sejak tahun 2023 dengan misi membawa cita rasa kopi otentik Indonesia ke lidah Anda. Kami percaya setiap seduhan memiliki cerita.</p>
                <p>Kami bekerja sama langsung dengan petani di Gayo, Toraja, dan Flores untuk memastikan biji kopi yang kami gunakan adalah kualitas terbaik.</p>
            </div>
        </div>
    </section>

    <section class="menu" id="menu">
        <h2><span>Menu</span> Kami</h2>

        <div class="menu-card-container">
            <div class="menu-card">
                <img src="https://images.unsplash.com/photo-1572442388796-11668a67e53d?ixlib=rb-1.2.1&auto=format&fit=crop&w=1353&q=80" alt="Espresso">
                <div class="menu-card-content">
                    <h3>Classic Espresso</h3>
                    <div class="menu-card-price">IDR 20.000</div>
                    <p>Ekstrak kopi murni dengan crema yang tebal.</p>
                    <button class="add-to-cart-btn" onclick="addToCart('Classic Espresso', 20000, 'https://images.unsplash.com/photo-1572442388796-11668a67e53d?ixlib=rb-1.2.1&auto=format&fit=crop&w=1353&q=80')">
                        <i class="fas fa-shopping-cart"></i> Tambah
                    </button>
                </div>
            </div>
            <div class="menu-card">
                <img src="https://images.unsplash.com/photo-1570968992193-6e584a3921b7?ixlib=rb-1.2.1&auto=format&fit=crop&w=1353&q=80" alt="Cappuccino">
                <div class="menu-card-content">
                    <h3>Creamy Cappuccino</h3>
                    <div class="menu-card-price">IDR 28.000</div>
                    <p>Perpaduan espresso, susu panas, dan busa lembut.</p>
                    <button class="add-to-cart-btn" onclick="addToCart('Creamy Cappuccino', 28000, 'https://images.unsplash.com/photo-1570968992193-6e584a3921b7?ixlib=rb-1.2.1&auto=format&fit=crop&w=1353&q=80')">
                        <i class="fas fa-shopping-cart"></i> Tambah
                    </button>
                </div>
            </div>
            <div class="menu-card">
                <img src="https://images.unsplash.com/photo-1461023058943-48dbf1399f98?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Latte">
                <div class="menu-card-content">
                    <h3>Hazelnut Latte</h3>
                    <div class="menu-card-price">IDR 32.000</div>
                    <p>Espresso dengan susu creamy dan sirup hazelnut.</p>
                    <button class="add-to-cart-btn" onclick="addToCart('Hazelnut Latte', 32000, 'https://images.unsplash.com/photo-1461023058943-48dbf1399f98?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80')">
                        <i class="fas fa-shopping-cart"></i> Tambah
                    </button>
                </div>
            </div>
            <div class="menu-card">
                <img src="https://images.unsplash.com/photo-1544787219-7f47ccb76574?ixlib=rb-1.2.1&auto=format&fit=crop&w=1267&q=80" alt="V60">
                <div class="menu-card-content">
                    <h3>Manual Brew V60</h3>
                    <div class="menu-card-price">IDR 35.000</div>
                    <p>Metode seduh manual untuk karakter asli biji kopi.</p>
                    <button class="add-to-cart-btn" onclick="addToCart('Manual Brew V60', 35000, 'https://images.unsplash.com/photo-1544787219-7f47ccb76574?ixlib=rb-1.2.1&auto=format&fit=crop&w=1267&q=80')">
                        <i class="fas fa-shopping-cart"></i> Tambah
                    </button>
                </div>
            </div>
        </div>
    </section>

    <section class="contact" id="contact">
        <h2><span>Kontak</span> Kami</h2>
        <div class="row">
            <div class="map">
               <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d126907.03126768832!2d106.789139!3d-6.229728!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2e69f3e945e34b9d%3A0x5371bf0fdad786a2!2sJakarta%2C%20Daerah%20Khusus%20Ibukota%20Jakarta!5e0!3m2!1sid!2sid!4v1646272548842!5m2!1sid!2sid" allowfullscreen="" loading="lazy" style="width:100%; height:100%; border:0;"></iframe>
            </div>
            <form action="">
                <div class="input-group">
                    <i class="fas fa-user"></i>
                    <input type="text" placeholder="Nama Lengkap">
                </div>
                <div class="input-group">
                    <i class="fas fa-envelope"></i>
                    <input type="email" placeholder="Email">
                </div>
                <div class="input-group">
                    <i class="fas fa-phone"></i>
                    <input type="number" placeholder="No HP">
                </div>
                <button type="button" class="btn" onclick="alert('Pesan terkirim!')">Kirim Pesan</button>
            </form>
        </div>
    </section>

    <footer>
        <div class="socials">
            <a href="#"><i class="fab fa-instagram"></i></a>
            <a href="#"><i class="fab fa-twitter"></i></a>
            <a href="#"><i class="fab fa-facebook"></i></a>
        </div>
        <div class="links">
            <a href="#home">Home</a>
            <a href="#about">Tentang Kami</a>
            <a href="#menu">Menu</a>
            <a href="#contact">Kontak</a>
        </div>
        <div class="credit">
            <p>Created by <a href="">NamaAnda</a>. | © 2024.</p>
        </div>
    </footer>

    <script>
        // --- Toggle Elements ---
        const navbarNav = document.querySelector('.navbar-nav');
        const shoppingCart = document.querySelector('#shopping-cart');
        
        // Toggle Hamburger Menu
        document.querySelector('#hamburger-menu').onclick = (e) => {
            navbarNav.classList.toggle('active');
            e.preventDefault();
        };

        // Toggle Shopping Cart
        document.querySelector('#shopping-cart-button').onclick = (e) => {
            shoppingCart.classList.toggle('active');
            e.preventDefault();
        };

        // Close Shopping Cart with X button
        document.querySelector('#close-cart').onclick = (e) => {
            shoppingCart.classList.remove('active');
            e.preventDefault();
        }

        // Close Sidebar ketika klik di luar
        const hamburger = document.querySelector('#hamburger-menu');
        const cartBtn = document.querySelector('#shopping-cart-button');
        
        document.addEventListener('click', function(e) {
            if(!hamburger.contains(e.target) && !navbarNav.contains(e.target)) {
                navbarNav.classList.remove('active');
            }
            if(!cartBtn.contains(e.target) && !shoppingCart.contains(e.target)) {
                shoppingCart.classList.remove('active');
            }
        });

        // --- KERANJANG BELANJA LOGIC ---
        
        // Array untuk menyimpan item
        let cart = [];

        // Fungsi format Rupiah
        const rupiah = (number) => {
            return new Intl.NumberFormat('id-ID', {
                style: 'currency',
                currency: 'IDR',
                minimumFractionDigits: 0
            }).format(number);
        }

        // Fungsi Menambah Item ke Keranjang
        function addToCart(name, price, image) {
            // Cek apakah item sudah ada di cart
            const existingItem = cart.find(item => item.name === name);

            if (existingItem) {
                existingItem.quantity++;
            } else {
                cart.push({
                    name: name,
                    price: price,
                    image: image,
                    quantity: 1
                });
            }

            updateCartUI();
            
            // Buka sidebar otomatis saat tambah item
            shoppingCart.classList.add('active');
        }

        // Fungsi Hapus Item
        function removeItem(name) {
            cart = cart.filter(item => item.name !== name);
            updateCartUI();
        }

        // Fungsi Update Tampilan Keranjang
        function updateCartUI() {
            const cartContainer = document.getElementById('cart-items-container');
            const totalPriceElement = document.getElementById('cart-total-price');
            
            cartContainer.innerHTML = '';
            let total = 0;

            if(cart.length === 0) {
                cartContainer.innerHTML = '<p style="text-align:center; margin-top:20px; color:#666;">Keranjang masih kosong.</p>';
            }

            cart.forEach(item => {
                total += item.price * item.quantity;

                const itemElement = document.createElement('div');
                itemElement.classList.add('cart-item');
                itemElement.innerHTML = `
                    <img src="${item.image}" alt="${item.name}">
                    <div class="item-detail">
                        <h3>${item.name}</h3>
                        <div class="item-price">${rupiah(item.price)} x ${item.quantity}</div>
                    </div>
                    <i class="fas fa-trash remove-item" onclick="removeItem('${item.name}')"></i>
                `;
                cartContainer.appendChild(itemElement);
            });

            totalPriceElement.innerText = rupiah(total);
        }

        // Fungsi Checkout Sederhana
        function checkout() {
            if (cart.length === 0) {
                alert("Keranjang belanja Anda kosong.");
                return;
            }
            
            let total = 0;
            let message = "Halo, saya ingin memesan:\n";
            
            cart.forEach(item => {
                message += `- ${item.name} (${item.quantity}x) - ${rupiah(item.price * item.quantity)}\n`;
                total += item.price * item.quantity;
            });
            
            message += `\nTotal Harga: ${rupiah(total)}`;
            
            // Contoh alert (Bisa diganti redirect ke WhatsApp)
            alert(message + "\n\n(Fitur Checkout: Di sini Anda bisa arahkan ke WhatsApp API)");
            
            // Untuk redirect ke WhatsApp, uncomment baris bawah ini:
            // window.open(`https://wa.me/6281234567890?text=${encodeURIComponent(message)}`);
        }
    </script>
</body>
</html>
