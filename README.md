<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Princess</title>
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Pacifico&family=Dancing+Script:wght@700&family=Comic+Neue:wght@700&family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #6b2b80, #8e44ad, #6c5ce7);
            color: white;
            font-family: 'Dancing Script', cursive;
            min-height: 100vh;
            overflow-x: hidden;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 20px;
            position: relative;
        }

        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(5px);
            z-index: -1;
        }

        /* Animasi Bunga Jatuh */
        .flower {
            position: fixed;
            top: -50px;
            font-size: 24px;
            animation: fall linear forwards, fadeOut 1s ease-in forwards;
            z-index: -1;
            text-shadow: 0 0 8px rgba(255, 255, 255, 0.6);
            opacity: 0.8;
        }

        @keyframes fall {
            to {
                transform: translateY(105vh) rotate(360deg);
            }
        }

        @keyframes fadeOut {
            0%, 90% {
                opacity: 0.8;
            }
            100% {
                opacity: 0;
            }
        }

        /* Container Utama */
        .container {
            max-width: 800px;
            width: 100%;
            text-align: center;
            z-index: 10;
            position: relative;
            padding: 20px;
        }

        /* Judul dengan animasi huruf - FONT DIUBAH MENJADI SAMBUNG */
        .title {
            font-family: 'Great Vibes', cursive;
            font-size: 4.5rem;
            margin-bottom: 30px;
            opacity: 0;
            animation: fadeIn 2s forwards;
            text-shadow: 3px 3px 0px rgba(0, 0, 0, 0.2);
            color: #fff;
            letter-spacing: 2px;
            font-weight: normal;
        }

        .title span {
            display: inline-block;
            opacity: 0;
            animation: letterAnimation 0.5s forwards;
        }

        @keyframes letterAnimation {
            from {
                opacity: 0;
                transform: translateY(50px) rotate(-10deg);
            }
            to {
                opacity: 1;
                transform: translateY(0) rotate(0);
            }
        }

        /* Foto dengan animasi dan glow */
        .photo-container {
            margin: 30px auto;
            width: 280px;
            height: 280px;
            border-radius: 50%;
            padding: 5px;
            box-shadow: 0 0 25px rgba(255, 255, 255, 0.8),
                        0 0 45px rgba(192, 0, 255, 0.8),
                        0 0 65px rgba(192, 0, 255, 0.6);
            animation: glow 2s infinite alternate, zoomIn 1.5s forwards;
            overflow: hidden;
            background: linear-gradient(135deg, #8e44ad, #6c5ce7);
        }

        .photo {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
            transition: transform 0.5s;
            border: 4px solid transparent;
        }

        .photo:hover {
            transform: scale(1.05);
        }

        @keyframes glow {
            from {
                box-shadow: 0 0 20px rgba(255, 255, 255, 0.7),
                            0 0 40px rgba(192, 0, 255, 0.7),
                            0 0 60px rgba(192, 0, 255, 0.5);
            }
            to {
                box-shadow: 0 0 30px rgba(255, 255, 255, 0.9),
                            0 0 50px rgba(192, 0, 255, 0.8),
                            0 0 70px rgba(192, 0, 255, 0.6);
            }
        }

        @keyframes zoomIn {
            from {
                opacity: 0;
                transform: scale(0.5);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        /* Kue ulang tahun - DITURUNKAN POSISINYA */
        .cake-container {
            margin: 60px auto 40px; /* Ditambah margin atas untuk menurunkan kue */
            position: relative;
            height: 250px;
            animation: slideIn 1.5s forwards;
            z-index: 20;
        }

        .cake {
            position: relative;
            width: 200px;
            height: 160px;
            margin: 0 auto;
        }

        .layer {
            position: absolute;
            border-radius: 10px;
        }

        .layer-bottom {
            width: 200px;
            height: 80px;
            background: linear-gradient(to right, #f9c6d0, #f6a5b5, #f9c6d0);
            bottom: 0;
            z-index: 1;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .layer-middle {
            width: 170px;
            height: 65px;
            background: linear-gradient(to right, #f6a5b5, #f3849d, #f6a5b5);
            bottom: 80px;
            left: 15px;
            z-index: 2;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .layer-top {
            width: 140px;
            height: 50px;
            background: linear-gradient(to right, #f3849d, #f06384, #f3849d);
            bottom: 145px;
            left: 30px;
            z-index: 3;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .decoration {
            position: absolute;
            width: 100%;
            height: 20px;
            background: linear-gradient(to right, #ff9eb5, #ff7a9a, #ff9eb5);
            bottom: 70px;
            border-radius: 10px;
            z-index: 4;
        }

        .candle {
            position: absolute;
            width: 10px;
            height: 45px;
            background: linear-gradient(to bottom, #fff, #f9c6d0);
            bottom: 160px;
            left: 95px;
            z-index: 4;
            border-radius: 5px;
        }

        .flame {
            position: absolute;
            width: 18px;
            height: 35px;
            background: linear-gradient(to bottom, #ffdd00, #ff5500);
            border-radius: 50% 50% 20% 20%;
            bottom: 195px;
            left: 91px;
            z-index: 5;
            animation: flicker 0.8s infinite alternate;
            box-shadow: 0 0 15px #ff9900, 0 0 30px #ff5500;
            transform-origin: bottom;
        }

        @keyframes flicker {
            0%, 100% {
                transform: scale(1) rotate(-2deg);
                opacity: 1;
            }
            25% {
                transform: scale(1.1) rotate(2deg);
            }
            50% {
                transform: scale(0.9) rotate(-2deg);
                opacity: 0.9;
            }
            75% {
                transform: scale(1.05) rotate(2deg);
            }
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(100px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Quote - FONT DIUBAH MENJADI TIDAK SAMBUNG */
        .quote-container {
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 20px;
            margin: 30px auto;
            max-width: 500px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .quote {
            font-family: 'Roboto', sans-serif;
            font-size: 1.8rem;
            opacity: 0;
            animation: fadeIn 2s forwards 2s;
            line-height: 1.5;
            font-weight: bold;
        }

        .quote span {
            opacity: 0;
            display: inline-block;
            margin-right: 5px; /* Tambahkan spasi antar kata */
        }

        .quote span:last-child {
            margin-right: 0; /* Hapus margin untuk kata terakhir */
        }

        @keyframes fadeIn {
            to {
                opacity: 1;
            }
        }

        /* BUKU ESTETIK - MENGANTI AMPLOP */
        .book-container {
            margin: 40px auto;
            width: 320px;
            height: 420px;
            position: relative;
            cursor: pointer;
            perspective: 1200px;
        }

        .book {
            position: absolute;
            width: 100%;
            height: 100%;
            transform-style: preserve-3d;
            transition: transform 1.2s ease-in-out;
            z-index: 10;
        }

        .book-cover {
            position: absolute;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #8e44ad, #6c5ce7);
            border-radius: 10px 15px 15px 10px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            backface-visibility: hidden;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
            border: 2px solid rgba(255, 255, 255, 0.2);
            z-index: 2;
            transform-origin: left;
            transition: transform 1.2s ease-in-out;
        }

        .book-cover:before {
            content: '';
            position: absolute;
            top: 20px;
            right: 20px;
            bottom: 20px;
            left: 20px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 5px 10px 10px 5px;
        }

        .book-spine {
            position: absolute;
            left: 0;
            top: 10%;
            width: 15px;
            height: 80%;
            background: linear-gradient(to right, #6b2b80, #8e44ad);
            border-radius: 5px 0 0 5px;
            box-shadow: inset -2px 0 5px rgba(0, 0, 0, 0.3);
        }

        .book-title {
            font-family: 'Great Vibes', cursive;
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 15px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            color: white;
            z-index: 1;
        }

        .book-subtitle {
            font-family: 'Dancing Script', cursive;
            font-size: 1.5rem;
            text-align: center;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
            color: #f9c6d0;
            z-index: 1;
        }

        .book-pages {
            position: absolute;
            width: 100%;
            height: 100%;
            background: #f9f3f3;
            border-radius: 10px 15px 15px 10px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
            z-index: 1;
            overflow: hidden;
            opacity: 0;
            transition: opacity 0.5s ease 0.6s;
        }

        .book-content {
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            background: linear-gradient(to bottom, #f9f3f3, #f0e6e6);
            border-radius: 5px;
            padding: 15px;
            position: relative;
            box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.1);
        }

        .book-content:before {
            content: '';
            position: absolute;
            top: 0;
            left: 30px;
            right: 30px;
            height: 1px;
            background: rgba(0, 0, 0, 0.1);
        }

        .book-photo {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            object-fit: cover;
            margin: 20px auto;
            border: 4px solid #ff2e63;
            box-shadow: 0 0 20px rgba(255, 46, 99, 0.5);
        }

        .love-text {
            font-family: 'Great Vibes', cursive;
            font-size: 3.5rem;
            font-weight: bold;
            color: #ff2e63;
            text-shadow: 2px 2px 0px rgba(0, 0, 0, 0.1);
            margin-top: 20px;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        /* Status buku terbuka */
        .book-open .book-cover {
            transform: rotateY(-160deg);
        }

        .book-open .book-pages {
            opacity: 1;
        }

        /* Credit */
        .credit {
            margin-top: 50px;
            font-family: Arial, sans-serif;
            font-size: 1rem;
            opacity: 0.8;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .title {
                font-size: 3.5rem;
            }
            
            .photo-container {
                width: 220px;
                height: 220px;
            }
            
            .quote {
                font-size: 1.5rem;
            }
            
            .cake {
                transform: scale(0.9);
            }
            
            .book-container {
                transform: scale(0.9);
            }
            
            .book-title {
                font-size: 2rem;
            }
            
            .love-text {
                font-size: 3rem;
            }
        }

        @media (max-width: 480px) {
            .title {
                font-size: 2.8rem;
            }
            
            .photo-container {
                width: 200px;
                height: 200px;
            }
            
            .quote {
                font-size: 1.3rem;
            }
            
            .cake {
                transform: scale(0.8);
            }
            
            .book-container {
                transform: scale(0.8);
            }
            
            .book-title {
                font-size: 1.8rem;
            }
            
            .love-text {
                font-size: 2.5rem;
            }
            
            .book-photo {
                width: 150px;
                height: 150px;
            }
        }
    </style>
</head>
<body>
    <!-- Background bunga akan di-generate oleh JavaScript -->
    
    <div class="container">
        <h1 class="title" id="animated-title">Happy Birthday Princesss</h1>
        
        <div class="photo-container">
            <!-- Ganti URL dengan foto dari drive Anda -->
            <img src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi_9JMGh7SKqikXTw8t-eeWjxKz07IDEzeCzYsDKuEgij493q81lP20uNSk6v92qkZgmSAlbw5EubczBYt3XHOozprXMsyGqucc_9-c9eBzd4aiJK7Kvm6hJo-LY0HhErLQBA_Es2ECLCXEoqT6jZqvpqhWHDQThXka3ZKnAwruD6iKYBKJfk_TxUhRvC4/s320/princesss.jpg" class="photo">
        </div>
        
        <!-- Kue diturunkan dengan menambah margin atas -->
        <div class="cake-container">
            <div class="cake">
                <div class="layer layer-bottom"></div>
                <div class="decoration"></div>
                <div class="layer layer-middle"></div>
                <div class="layer layer-top"></div>
                <div class="candle"></div>
                <div class="flame"></div>
            </div>
        </div>
        
        <div class="quote-container">
            <p class="quote" id="animated-quote">"happy birthday sayang semoga semua keinginan kamu bisa tercapai dan aku akan selalu support kamu"</p>
        </div>
        
        <!-- BUKU MENGANTI AMPLOP -->
        <div class="book-container" onclick="toggleBook()">
            <div class="book">
                <div class="book-cover">
                    <div class="book-spine"></div>
                    <h2 class="book-title">My Princess</h2>
                    <p class="book-subtitle">Click to Open</p>
                </div>
                <div class="book-pages">
                    <div class="book-content">
                        <img src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgckXrY5xHh95QZZ49IFD34H6z9XIG_xi2AMZiwy1dzYZek1Qj9D5VUKJpXpMj1AZE-jW7GAOX2UC6cRhn_E1BXZ07_UNxX1_mizPs0ixo0zSzHI6JMbAqkqz1kodYbZ-14cGJGWaG5JlmKn8Ve1O1y_HNlBX3OzTPynryRbNMlTlyiXnbhprS3NKd-ODU/s320/princeess%202.jpg" alt="Foto Princess" class="book-photo">
                        <p class="love-text">I Love You</p>
                    </div>
                </div>
            </div>
        </div>
        
        <p class="credit">Made with ❤️</p>
    </div>

    <script>
        // Animasi judul satu per satu huruf
        document.addEventListener('DOMContentLoaded', function() {
            // Animasi judul
            const title = document.getElementById('animated-title');
            const titleText = title.textContent;
            title.textContent = '';
            
            for (let i = 0; i < titleText.length; i++) {
                const span = document.createElement('span');
                span.textContent = titleText[i];
                span.style.animationDelay = `${i * 0.1}s`;
                title.appendChild(span);
            }
            
            // Animasi quote - DIPERBAIKI: dipisah per kata, bukan per huruf
            const quote = document.getElementById('animated-quote');
            const quoteText = quote.textContent;
            quote.textContent = '';
            
            // Pisahkan teks menjadi kata-kata
            const words = quoteText.split(' ');
            
            for (let i = 0; i < words.length; i++) {
                const span = document.createElement('span');
                span.textContent = words[i] + ' '; // Tambahkan spasi setelah setiap kata
                span.style.animationDelay = `${2 + i * 0.2}s`; // Delay lebih lama antar kata
                quote.appendChild(span);
            }
            
            // Set timeout untuk animasi span quote
            setTimeout(() => {
                const spans = quote.querySelectorAll('span');
                spans.forEach(span => {
                    span.style.animation = 'letterAnimation 0.5s forwards';
                });
            }, 2000);
            
            // Membuat bunga jatuh
            createFlowers();
        });
        
        // Fungsi untuk membuat bunga berjatuhan
        function createFlowers() {
            const flowers = ['🌸', '🌹', '🌺', '🌻', '🌷', '💐'];
            const container = document.body;
            
            setInterval(() => {
                const flower = document.createElement('div');
                flower.className = 'flower';
                flower.textContent = flowers[Math.floor(Math.random() * flowers.length)];
                
                // Posisi acak
                flower.style.left = `${Math.random() * 100}vw`;
                
                // Durasi acak antara 5-15 detik
                const duration = 5 + Math.random() * 10;
                flower.style.animationDuration = `${duration}s`;
                
                container.appendChild(flower);
                
                // Hapus elemen setelah animasi selesai
                setTimeout(() => {
                    flower.remove();
                }, duration * 1000);
            }, 300);
        }
        
        // Fungsi untuk membuka dan menutup buku
        function toggleBook() {
            const book = document.querySelector('.book');
            book.classList.toggle('book-open');
        }
        
        // Ganti URL foto dengan foto dari drive Anda
        // Untuk foto dari Google Drive, pastikan link yang digunakan adalah link langsung ke gambar
        // Anda bisa dapatkan dengan mengubah link sharing menjadi "Siapa pun dengan link dapat melihat"
        // lalu ganti bagian akhir dengan ucpid menjadi export?format=jpg atau png
        // Contoh: https://drive.google.com/uc?export=view&id=ID_FILE_ANDA
        document.addEventListener('DOMContentLoaded', function() {
            // Ganti dengan link foto Anda
            const mainPhoto = "https://drive.google.com/uc?export=view&id=YOUR_IMAGE_ID";
            const bookPhoto = "https://drive.google.com/uc?export=view&id=YOUR_IMAGE_ID";
            
            // Jika ingin menggunakan foto dari drive, hapus komentar di bawah dan ganti YOUR_IMAGE_ID
            // document.querySelector('.photo').src = mainPhoto;
            // document.querySelector('.book-photo').src = bookPhoto;
        });
    </script>
</body>
</html>
