<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday, Hasfa Meri Janeman!</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <!-- Preload slideshow images for performance -->
    <link rel="preload" href="https://i.imgur.com/wgMGoHS.jpeg" as="image">
    <link rel="preload" href="https://i.imgur.com/fNfbUds.jpeg" as="image">
    <link rel="preload" href="https://i.imgur.com/6pfqJXx.jpeg" as="image">
    <link rel="preload" href="https://i.imgur.com/VZrFifP.jpeg" as="image">
    <style>
        /* 🌸 Base Styling */
        html {
            scroll-behavior: smooth;
            box-sizing: border-box;
        }

        *, *::before, *::after {
            box-sizing: inherit;
        }

        body {
            font-family: 'Roboto', sans-serif;
            color: #333;
            text-align: center;
            margin: 0;
            padding: 0;
            overflow-x: hidden;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            background: #f0f0f0; /* Fallback background */
        }

        /* 🌸 Background Slideshow */
        #background-slideshow {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .background-image {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            opacity: 0;
            transition: opacity 1.5s ease-in-out;
            transform: scale(1.1); /* Slightly zoom for larger appearance */
        }

        .background-image.active {
            opacity: 0.8; /* Slightly transparent for text contrast */
        }

        /* 🌸 Container */
        .container {
            width: 100%;
            max-width: clamp(300px, 90vw, 1000px);
            padding: clamp(10px, 3vw, 20px);
        }

        /* 🌸 Teaser Sections */
        .teaser, .message, .surprise {
            background: rgba(255, 255, 255, 0.5); /* More transparent popup */
            backdrop-filter: blur(5px);
            padding: clamp(15px, 4vw, 25px);
            border-radius: 15px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            margin: clamp(5px, 2vw, 10px);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            min-height: 50vh;
        }

        /* 🌟 Lights Effect */
        #lights {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            opacity: 1;
            transition: opacity 1.5s ease-in-out;
            z-index: 1000;
            pointer-events: none;
        }

        #lights.lights-active {
            opacity: 0;
        }

        /* 🌸 Hidden Elements */
        .hidden {
            display: none;
        }

        /* 🌸 Headings and Text */
        h1 {
            color: #e91e63;
            font-size: clamp(1.5rem, 4vw, 2.8rem);
            margin-bottom: 15px;
        }

        h1 .hasfa {
            color: #ff4081;
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        .subtitle {
            font-size: clamp(0.9rem, 2.5vw, 1.2rem);
            line-height: 1.6;
            color: #333;
        }

        /* 🌸 Buttons with Glow */
        button {
            background: #e91e63;
            color: white;
            border: none;
            padding: clamp(10px, 3vw, 14px) clamp(20px, 5vw, 28px);
            font-size: clamp(0.9rem, 2.5vw, 1.1rem);
            border-radius: 8px;
            cursor: pointer;
            transition: background 0.3s, transform 0.2s, box-shadow 0.3s;
            margin: clamp(5px, 1.5vw, 10px);
            touch-action: manipulation;
            box-shadow: 0 0 10px rgba(233, 30, 99, 0.5), 0 0 20px rgba(233, 30, 99, 0.3);
            animation: glow 1.5s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { box-shadow: 0 0 10px rgba(233, 30, 99, 0.5), 0 0 20px rgba(233, 30, 99, 0.3); }
            to { box-shadow: 0 0 15px rgba(233, 30, 99, 0.7), 0 0 25px rgba(233, 30, 99, 0.4); }
        }

        button:hover {
            background: #c2185b;
            transform: scale(1.05);
        }

        button:disabled {
            background: #ccc;
            box-shadow: none;
            cursor: not-allowed;
            transform: none;
            opacity: 0.6;
        }

        /* 🌸 Decorations */
        .decorations {
            margin: clamp(10px, 3vw, 20px) 0;
        }

        .decoration {
            max-width: clamp(50px, 15vw, 80px);
            margin: 5px;
            opacity: 0;
            animation: fadeIn 1s ease-in forwards;
        }

        @keyframes fadeIn {
            to { opacity: 1; }
        }

        /* 🎈 Balloons Animation */
        .balloon {
            width: clamp(25px, 8vw, 40px);
            height: clamp(40px, 12vw, 60px);
            border: 2px solid gold;
            border-radius: 50% 50% 40% 40%;
            position: absolute;
            bottom: -100px;
            animation: floatUp 6s ease-in-out infinite;
            will-change: transform, opacity;
        }

        .balloon:nth-child(1) { left: 10%; background: #f06292; animation-delay: 0s; }
        .balloon:nth-child(2) { left: 30%; background: #e91e63; animation-delay: 1s; }
        .balloon:nth-child(3) { left: 50%; background: #ff4081; animation-delay: 2s; }
        .balloon:nth-child(4) { left: 70%; background: #c2185b; animation-delay: 3s; }

        @keyframes floatUp {
            0% { bottom: -100px; opacity: 1; transform: translateX(0); }
            50% { transform: translateX(10px); }
            100% { bottom: 100%; opacity: 0; transform: translateX(-10px); }
        }

        /* 🎂 Cake + Candles */
        .cake {
            max-width: 100%;
            max-height: clamp(120px, 30vw, 200px);
            border-radius: 10px;
            margin: 20px 0;
        }

        .candles-on .candle {
            width: 8px;
            height: 25px;
            background: #ffeb3b;
            display: inline-block;
            margin: 0 8px;
            position: relative;
            top: -40px;
        }

        .candles-on .candle::after {
            content: '';
            width: 5px;
            height: 8px;
            background: #ff5722;
            position: absolute;
            top: -8px;
            left: 1.5px;
            border-radius: 50%;
            animation: flicker 0.2s ease-in-out infinite alternate;
        }

        @keyframes flicker {
            from { opacity: 1; }
            to { opacity: 0.7; }
        }

        .candles-off .candle::after {
            display: none;
        }

        .candles-off .candle::before {
            content: '';
            width: 5px;
            height: 10px;
            background: rgba(200, 200, 200, 0.5);
            position: absolute;
            top: -10px;
            left: 1.5px;
            animation: smoke 1.5s ease-out forwards;
        }

        @keyframes smoke {
            0% { transform: translateY(0); opacity: 0.5; }
            100% { transform: translateY(-30px); opacity: 0; }
        }

        /* 💌 Surprise Message with Enhanced Popup Animation */
        #surpriseMessage {
            opacity: 0;
            transform: scale(0.7) translateY(50px);
            transition: opacity 1s ease-in-out, transform 1s ease-in-out;
            background: rgba(255, 240, 245, 0.9);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 8px 20px rgba(233, 30, 99, 0.3);
            max-width: 80%;
            margin: 20px auto;
            font-size: clamp(1rem, 2.5vw, 1.2rem);
            line-height: 1.6;
            word-wrap: break-word;
        }

        #surpriseMessage.show {
            opacity: 1;
            transform: scale(1) translateY(0);
        }

        /* ❤️ Floating Hearts */
        .heart {
            position: absolute;
            width: 15px;
            height: 15px;
            background: #e91e63;
            transform: rotate(-45deg);
            animation: floatHeart 5s ease-in-out infinite;
            will-change: transform, opacity;
        }

        .heart::before, .heart::after {
            content: '';
            width: 15px;
            height: 15px;
            background: #e91e63;
            border-radius: 50%;
            position: absolute;
        }

        .heart::before { top: -7.5px; left: 0; }
        .heart::after { left: 7.5px; top: 0; }

        @keyframes floatHeart {
            0% { transform: translateY(100vh) rotate(-45deg); opacity: 1; }
            50% { transform: translateY(50vh) rotate(-45deg) translateX(10px); }
            100% { transform: translateY(-100vh) rotate(-45deg); opacity: 0; }
        }

        /* 📱 Responsive Design */
        @media (max-width: 600px) {
            .container { padding: 8px; }
            .teaser, .message, .surprise { min-height: 60vh; padding: 12px; }
            .decoration { max-width: 50px; }
            .cake { max-height: 150px; }
            .balloon { width: 25px; height: 40px; }
            h1 { font-size: clamp(1.4rem, 4vw, 1.8rem); }
            .subtitle { font-size: clamp(0.8rem, 2.5vw, 1rem); }
            button { padding: 8px 16px; }
            #surpriseMessage { max-width: 90%; font-size: clamp(0.9rem, 2vw, 1rem); }
        }

        @media (max-width: 400px) {
            .balloon { width: 20px; height: 35px; }
            button { padding: 8px 14px; font-size: 0.9rem; }
        }

        @media (min-width: 1200px) {
            .container { max-width: 1100px; }
            .teaser, .message, .surprise { min-height: 45vh; }
            h1 { font-size: clamp(2rem, 3vw, 3rem); }
        }

        /* ✨ Accessibility: Reduced Motion */
        @media (prefers-reduced-motion: reduce) {
            .balloon, .heart, .background-image, #lights, .hasfa, button, #surpriseMessage {
                animation: none !important;
                transition: none !important;
                opacity: 1 !important;
                transform: none !important;
                box-shadow: 0 0 10px rgba(233, 30, 99, 0.5) !important;
            }
        }

        /* ✨ Gentle Glow Overlay */
        body::after {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            background: radial-gradient(circle at center, transparent 40%, rgba(255, 240, 200, 0.15) 80%);
            opacity: 0.6;
        }
    </style>
</head>
<body>
    <div id="background-slideshow">
        <div class="background-image active" style="background-image: url('https://i.imgur.com/wgMGoHS.jpeg');"></div>
        <div class="background-image" style="background-image: url('https://i.imgur.com/fNfbUds.jpeg');"></div>
        <div class="background-image" style="background-image: url('https://i.imgur.com/6pfqJXx.jpeg');"></div>
        <div class="background-image" style="background-image: url('https://i.imgur.com/VZrFifP.jpeg');"></div>
    </div>
    <div class="container">
        <!-- Teaser Sequence -->
        <section id="teaser1" class="teaser">
            <h1><span class="hasfa">Hafsa</span> Meri Guriyaaa, Ready for Your Surprise? 🎉❤️</h1>
            <p class="subtitle">My darling Hasfa, something special awaits you, Meri Janeman!</p>
            <button id="teaserBtn1" aria-label="Proceed to the next birthday surprise step">Yes, I'm Ready!</button>
        </section>

        <section id="teaser2" class="teaser hidden">
            <h1>Sure, Meri <span class="hasfa">Monjulika</span>? Just Kidding! 😜</h1>
            <p class="subtitle">Hafsa, you know I love teasing you, Meri Payari Si Begummmmm!</p>
            <button id="teaserBtn2" aria-label="Proceed to the next birthday surprise step">Show Me Already!</button>
        </section>

        <section id="teaser3" class="teaser hidden">
            <h1>Oops, Sorry, Meri <span class="hasfa">Monjulika</span>! Last Time! 😅</h1>
            <p class="subtitle">Meri Guriyaaa, click for your birthday magic!</p>
            <button id="teaserBtn3" aria-label="Reveal the birthday surprise">Click Here, Meri Janeman!</button>
        </section>

        <!-- Main Content -->
        <div id="mainContent" class="hidden">
            <div id="lights"></div>

            <header>
                <h1>Happy Birthday, <span class="hasfa">Hasfa</span> Meri Payari Si Begummmmm! 🎉❤️</h1>
                <p class="subtitle">For you, Hasfa, my darling Meri Janeman—I love you more than words!</p>
            </header>

            <section class="decorations">
                <h2>Let’s Make It Magical, Meri Guriyaaa!</h2>
                <div class="controls">
                    <button id="decorBtn" aria-label="Start the birthday decorations">Start the Magic! 🎀</button>
                    <button id="lightsBtn" class="hidden" aria-label="Turn on the lights">Lights On! ✨</button>
                    <button id="balloonsBtn" class="hidden" aria-label="Release the balloons">Balloons! 🎈</button>
                    <button id="cakeBtn" class="hidden" aria-label="Show the birthday cake">Cake Time! 🎂</button>
                    <button id="blowCakeBtn" class="hidden" aria-label="Blow out the candles">Blow the Candles! 🕯️</button>
                    <button id="playPauseBtn" class="hidden" aria-label="Pause background music">Pause Music</button>
                </div>

                <div id="decoration-container" class="hidden">
                    <img src="https://i.imgur.com/fNfbUds.jpeg" alt="Decoration 1" class="decoration" loading="lazy" onerror="this.src='local-fallback-decoration1.jpg';">
                    <img src="https://i.imgur.com/4xLZD5t.jpeg" alt="Decoration 2" class="decoration" loading="lazy" onerror="this.src='local-fallback-decoration2.jpg';">
                    <img src="https://i.imgur.com/dqwkbLP.jpeg" alt="Decoration 3" class="decoration" loading="lazy" onerror="this.src='local-fallback-decoration3.jpg';">
                </div>

                <div id="balloon-container" class="hidden">
                    <div class="balloon"></div>
                    <div class="balloon"></div>
                    <div class="balloon"></div>
                    <div class="balloon"></div>
                </div>

                <div id="cake" class="hidden">
                    <img src="https://i.imgur.com/bB4fcs5.jpeg" alt="Hafsa’s Birthday Cake" class="cake" loading="lazy" onerror="this.src='local-fallback-cake.jpg';">
                    <div id="candles" class="candles-on">
                        <div class="candle"></div>
                        <div class="candle"></div>
                        <div class="candle"></div>
                    </div>
                </div>

                <audio id="bgMusic">
                    <source src="https://cdn.pixabay.com/audio/2023/08/07/audio_ae4b4a6f9c.mp3" type="audio/mp3">
                    Your browser does not support the audio element.
                </audio>
            </section>

            <section class="surprise">
                <button id="revealBtn" aria-label="Reveal the birthday surprise message">Hafsa, Meri Guriyaaa, Your Surprise! 🎁</button>
                <p id="surpriseMessage" class="hidden">Happy Birthday meri guriyaaaaa meri chanda meri janeman meri darling my baby Hafsa 🥳🥹 today is all about you and I, Muhammad, just want to tell you how much you mean to me 🫀 every moment we spend together is pure magic and every smile of yours makes my heart beat faster ❤️‍🔥🥺 you are my world my happiness my everything 🌏🥹 being with you makes life brighter and every memory we create is a treasure I will never forget 🫶🏻🥹 the laughter the late talks the little moments we share all of it stays in my heart forever 🤌🏻🥳 you make even ordinary days feel special and being around you feels like home 🌏🥺 thank you for your love your kindness your warmth and the way you care for me 🫀❤️‍🔥 you inspire me to be better and your presence makes everything beautiful 🥹🙈 today I hope you feel how loved you are how amazing you are and how much joy you bring into my life 🥳🥹 every dream you have I hope comes true and every wish you make is granted 🌏❤️‍🔥 meri guriyaaaaa meri chanda meri janeman meri darling my baby I love you and I always will 🫀❤️‍🔥 the time we spend together is too memorable and more 🥺🫶🏻 every second with you is a blessing and I can’t wait for all the moments we still have ahead 🥹🤌🏻 Forever yours, Muhammad!</p>
            </section>

            <footer>
                <p>Made with all my love for you, Hasfa, Meri Janeman 💕 | October 24, 2025</p>
            </footer>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // 🌸 Background Slideshow
            const images = document.querySelectorAll('.background-image');
            let currentImageIndex = 0;

            function changeBackground() {
                try {
                    images[currentImageIndex].classList.remove('active');
                    currentImageIndex = (currentImageIndex + 1) % images.length;
                    images[currentImageIndex].classList.add('active');
                } catch (error) {
                    console.error('Error in slideshow:', error);
                }
            }

            if (images.length > 0) {
                images[currentImageIndex].classList.add('active');
                setInterval(changeBackground, 4500); // Reliable timing for slideshow
            } else {
                console.warn('No background images found.');
            }

            // 🌸 Element References
            const teaser1 = document.getElementById('teaser1');
            const teaser2 = document.getElementById('teaser2');
            const teaser3 = document.getElementById('teaser3');
            const mainContent = document.getElementById('mainContent');
            const decorBtn = document.getElementById('decorBtn');
            const lightsBtn = document.getElementById('lightsBtn');
            const balloonsBtn = document.getElementById('balloonsBtn');
            const cakeBtn = document.getElementById('cakeBtn');
            const blowCakeBtn = document.getElementById('blowCakeBtn');
            const revealBtn = document.getElementById('revealBtn');
            const playPauseBtn = document.getElementById('playPauseBtn');
            const lights = document.getElementById('lights');
            const decorationContainer = document.getElementById('decoration-container');
            const balloonContainer = document.getElementById('balloon-container');
            const cake = document.getElementById('cake');
            const candles = document.getElementById('candles');
            const audio = document.getElementById('bgMusic');

            // Prevent button spam with accessibility
            function disableButton(btn, duration) {
                if (btn) {
                    btn.disabled = true;
                    btn.setAttribute('aria-disabled', 'true');
                    setTimeout(() => {
                        btn.disabled = false;
                        btn.setAttribute('aria-disabled', 'false');
                    }, duration);
                }
            }

            // Teaser sequence
            if (teaser1 && teaser2 && teaser3 && mainContent) {
                document.getElementById('teaserBtn1').addEventListener('click', (e) => {
                    disableButton(e.target, 1000);
                    teaser1.classList.add('hidden');
                    teaser2.classList.remove('hidden');
                });

                document.getElementById('teaserBtn2').addEventListener('click', (e) => {
                    disableButton(e.target, 1000);
                    teaser2.classList.add('hidden');
                    teaser3.classList.remove('hidden');
                });

                document.getElementById('teaserBtn3').addEventListener('click', (e) => {
                    disableButton(e.target, 1000);
                    teaser3.classList.add('hidden');
                    mainContent.classList.remove('hidden');
                    setTimeout(() => {
                        if (lights) lights.classList.add('lights-active');
                    }, 100);
                });
            } else {
                console.warn('One or more teaser elements not found.');
            }

            // Decoration sequence
            if (decorBtn && lightsBtn && balloonsBtn && cakeBtn && blowCakeBtn && playPauseBtn &&
                lights && decorationContainer && balloonContainer && cake) {
                decorBtn.addEventListener('click', (e) => {
                    disableButton(e.target, 1000);
                    decorBtn.classList.add('hidden');
                    lightsBtn.classList.remove('hidden');
                    playPauseBtn.classList.remove('hidden');
                    decorationContainer.classList.remove('hidden');
                    if (audio) audio.play().catch(err => console.error('Audio play failed:', err));
                });

                lightsBtn.addEventListener('click', (e) => {
                    disableButton(e.target, 1500);
                    lights.classList.add('lights-active');
                    lightsBtn.classList.add('hidden');
                    setTimeout(() => balloonsBtn.classList.remove('hidden'), 1500);
                });

                balloonsBtn.addEventListener('click', (e) => {
                    disableButton(e.target, 1000);
                    balloonContainer.classList.remove('hidden');
                    balloonsBtn.classList.add('hidden');
                    cakeBtn.classList.remove('hidden');
                });

                cakeBtn.addEventListener('click', (e) => {
                    disableButton(e.target, 1000);
                    cake.classList.remove('hidden');
                    cakeBtn.classList.add('hidden');
                    blowCakeBtn.classList.remove('hidden');
                });

                blowCakeBtn.addEventListener('click', (e) => {
                    disableButton(e.target, 1000);
                    candles.classList.remove('candles-on');
                    candles.classList.add('candles-off');
                    setTimeout(() => revealBtn.classList.remove('hidden'), 500);
                });
            } else {
                console.warn('One or more decoration elements not found.');
            }

            // Surprise reveal
            if (revealBtn) {
                revealBtn.addEventListener('click', (e) => {
                    disableButton(e.target, 1000);
                    const surpriseMessage = document.getElementById('surpriseMessage');
                    if (surpriseMessage) {
                        surpriseMessage.classList.remove('hidden');
                        setTimeout(() => surpriseMessage.classList.add('show'), 10);
                    }
                });
            }

            // Audio controls
            if (playPauseBtn && audio) {
                playPauseBtn.addEventListener('click', () => {
                    if (audio.paused) {
                        audio.play().catch(err => console.error('Audio play failed:', err));
                        playPauseBtn.textContent = 'Pause Music';
                        playPauseBtn.setAttribute('aria-label', 'Pause background music');
                    } else {
                        audio.pause();
                        playPauseBtn.textContent = 'Play Music';
                        playPauseBtn.setAttribute('aria-label', 'Play background music');
                    }
                });
            }

            // ❤️ Floating hearts with limit
            let heartCount = 0;
            const maxHearts = 8;
            function createHeart() {
                if (heartCount < maxHearts) {
                    const heart = document.createElement('div');
                    heart.className = 'heart';
                    heart.style.left = Math.random() * 90 + 5 + 'vw';
                    document.body.appendChild(heart);
                    heartCount++;
                    setTimeout(() => {
                        heart.remove();
                        heartCount--;
                    }, 5000);
                }
                requestAnimationFrame(createHeart);
            }
            setTimeout(() => requestAnimationFrame(createHeart), 1000);

            // Handle image load errors
            images.forEach(img => {
                img.addEventListener('error', () => {
                    console.error('Image load failed, using fallback:', img.style.backgroundImage);
                    img.style.backgroundImage = 'url(local-fallback-bg.jpg)';
                });
            });[indexhtml.html](https://github.com/user-attachments/files/23108948/indexhtml.html)

        });
    </script>
</body>
</html>
