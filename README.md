<!DOCTYPE html>
<html lang="kk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Жандос & Айжарық — Тойға шақыру</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background-color: #fcf8f2;
            font-family: 'Georgia', serif;
            color: #4a3b32;
            text-align: center;
        }
        .container {
            max-width: 500px;
            margin: 0 auto;
            padding: 20px;
            box-sizing: border-box;
        }
        h1 {
            font-size: 2.2rem;
            color: #b8860b;
            margin-top: 25px;
            letter-spacing: 2px;
        }
        .names {
            font-size: 2rem;
            color: #b8860b;
            font-weight: bold;
            margin: 20px 0;
        }
        .ampersand {
            font-size: 1.5rem;
            color: #4a3b32;
            display: block;
            margin: 5px 0;
        }
        .invitation-text {
            font-size: 1.15rem;
            line-height: 1.8;
            margin: 25px 10px;
            padding: 25px 20px;
            border: 2px dashed #b8860b;
            background-color: #ffffff;
            border-radius: 15px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.05);
        }
        /* Слайдер стилі */
        .slider {
            position: relative;
            width: 100%;
            height: 380px;
            overflow: hidden;
            border-radius: 15px;
            box-shadow: 0 6px 20px rgba(0,0,0,0.15);
            margin-bottom: 25px;
        }
        .slider img {
            position: absolute;
            width: 100%;
            height: 100%;
            object-fit: cover;
            opacity: 0;
            transition: opacity 1s ease-in-out;
        }
        .slider img.active {
            opacity: 1;
        }
        /* Музыка батырмасы */
        .music-btn {
            background-color: #b8860b;
            color: white;
            border: none;
            padding: 12px 30px;
            font-size: 1rem;
            border-radius: 25px;
            cursor: pointer;
            box-shadow: 0 4px 10px rgba(184, 134, 11, 0.3);
            margin-bottom: 25px;
            font-family: 'Georgia', serif;
            transition: transform 0.2s;
        }
        .music-btn:active {
            transform: scale(0.95);
        }
        .info-title {
            color: #b8860b;
            font-weight: bold;
            margin-top: 15px;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>ТОЙҒА ШАҚЫРУ</h1>
        
        <button class="music-btn" id="musicBtn" onclick="toggleMusic()">🎵 Музыканы қосу</button>
        <audio id="bgMusic" loop>
            <source src="https://muznavo.net/music/dl/zigitter_toby_-_ak_bosaga_(muznavo.net).mp3" type="audio/mp3">
        </audio>

        <div class="slider">
            <img src="IMG-20260610-WA0001.jpg" class="active" alt="Фото 1">
            <img src="IMG-20260610-WA0002.jpg" alt="Фото 2">
            <img src="IMG-20260610-WA0003.jpg" alt="Фото 3">
            <img src="IMG-20260610-WA0004.jpg" alt="Фото 4">
            <img src="IMG-20260610-WA0005.jpg" alt="Фото 5">
            <img src="IMG-20260610-WA0006.jpg" alt="Фото 6">
        </div>

        <div class="invitation-text">
            <p>Құрметті ағайын-туыс, құда-жекжат, дос-жаран!</p>
            
            <div class="names">
                Жандос
                <span class="ampersand">&</span>
                Айжарық
            </div>

            <p>Балаларымыздың үйлену тойына арналған ақ дастарханымыздың <strong>Қадірменді Қонағы</strong> болуға шақырамыз.</p>
            
            <hr style="border: 0; border-top: 1px solid #b8860b; margin: 20px 0;">
            
            <div class="info-title">ӨТЕТІН УАҚЫТЫ:</div>
            <p>2026 жыл, 24 Маусым (6-шы айдың 24-і)<br>Сағат 17:00-де</p>
            
            <div class="info-title">МЕКЕН-ЖАЙЫ:</div>
            <p>«Алтын-Орда» той сарайы</p>
            
            <hr style="border: 0; border-top: 1px solid #b8860b; margin: 20px 0;">
            
            <div class="info-title">ТОЙ ИЕЛЕРІ:</div>
            <p>Ата-анасы: Хобыланды — Меруерт</p>
        </div>
    </div>

    <script>
        // Слайд-шоу скрипті
        const images = document.querySelectorAll('.slider img');
        let currentIndex = 0;

        setInterval(() => {
            images[currentIndex].classList.remove('active');
            currentIndex = (currentIndex + 1) % images.length;
            images[currentIndex].classList.add('active');
        }, 3000); // Әр 3 секунд сайын сурет ауысады

        // Музыканы қосу/өшіру скрипті
        const music = document.getElementById('bgMusic');
        const btn = document.getElementById('musicBtn');

        function toggleMusic() {
            if (music.paused) {
                music.play().catch(e => console.log("Музыка ойнату басталмады"));
                btn.innerHTML = "⏸ Музыканы өшіру";
            } else {
                music.pause();
                btn.innerHTML = "🎵 Музыканы қосу";
            }
        }
    </script>

</body>
</html>
