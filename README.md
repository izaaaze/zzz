<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>last day uas</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600&family=Poppins:wght@400&display=swap" rel="stylesheet">
    <style>
        body {
            margin: 0;
            font-family: 'Poppins', sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background: linear-gradient(135deg, #FFC0CB, #FF6F61);
            overflow: hidden;
        }

        .container {
            text-align: center;
            position: relative;
            width: 100%;
            height: 100%;
        }

        h1 {
            font-family: 'Dancing Script', cursive;
            font-size: 2.5rem;
            color: #FFF;
            margin-top: 20px;
            display: none;
            transition: transform 1s ease-out, font-size 1s ease-out;
        }

        h1.show-message {
            display: block;
            transform: scale(1.5); /* Membesarkan teks */
        }

        button {
            padding: 15px 25px;
            font-size: 1.2rem;
            color: #FFF;
            background: #FF6F61;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            transition: transform 0.3s ease-out;
            animation: pulse 0.5s infinite alternate;
        }

        button:hover {
            background: #e14a3b;
        }

        @keyframes pulse {
            0% {
                transform: scale(1);
                box-shadow: 0 0 10px #FF6F61;
            }
            50% {
                transform: scale(1.1);
                box-shadow: 0 0 20px #FF6F61;
            }
            100% {
                transform: scale(1);
                box-shadow: 0 0 10px #FF6F61;
            }
        }

        .hearts {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }

        .heart {
            position: absolute;
            width: 20px;
            height: 20px;
            background: #FF6F61;
            clip-path: polygon(50% 0%, 100% 35%, 80% 100%, 50% 70%, 20% 100%, 0% 35%);
            animation: spread 3s infinite ease-out;
        }

        @keyframes spread {
            from {
                transform: translate(0, 0) scale(1);
                opacity: 1;
            }
            to {
                transform: translate(calc(100vw * (Math.random() - 0.5)), calc(100vh * (Math.random() - 0.5))) scale(0.5);
                opacity: 0;
            }
        }

        .notification {
            font-size: 1.2rem;
            color: #fff;
            margin-top: 15px;
            opacity: 0;
            transition: opacity 1s ease;
            position: absolute;
            top: 10px;
            left: 50%;
            transform: translateX(-50%);
        }

        .notification.show {
            opacity: 1;
        }

        /* Responsif untuk layar kecil (misalnya iPhone 6) */
        @media screen and (max-width: 375px) {
            h1 {
                font-size: 1.8rem;
            }
            button {
                padding: 10px 20px;
                font-size: 1rem;
            }
        }

        /* Teks Footer */
        .footer {
            font-size: 1rem;
            color: #FFF;
            margin-top: 50px;
            font-family: 'Poppins', sans-serif;
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
        }
    </style>
</head>
<body>
    <div class="container">
        <button id="annoying-button" onclick="moveButton()">Klik aku!</button>
        <h1 id="message-1">LAST DAY UAS??</h1>
        <h1 id="message-2">cemangat nailacuantiks!!</h1>
        <h1 id="message-3">semoga diberikan kemudahan</h1>
        <h1 id="message-4">see u hehehe</h1>
        <div class="hearts"></div>
    </div>
    <audio id="click-sound" src="https://www.soundjay.com/button/beep-07.mp3" preload="auto"></audio>
    <audio id="final-sound" src="https://www.soundjay.com/button/beep-08b.mp3" preload="auto"></audio>
    
    <!-- Footer -->
    <div class="footer">☠️Dibuat oleh Admin Hengker☠️</div>

    <script>
        const button = document.getElementById('annoying-button');
        const message1 = document.getElementById('message-1');
        const message2 = document.getElementById('message-2');
        const message3 = document.getElementById('message-3');
        const message4 = document.getElementById('message-4');        
        const heartContainer = document.querySelector('.hearts');
        const clickSound = document.getElementById('click-sound');
        const finalSound = document.getElementById('final-sound');
        let counter = 0;

        // Variasi pesan yang akan muncul saat tombol diklik setelah klik ke-3
        const variations = [
            "guys klik guys😁",
            "klikkkk disini nayyy👈",
            "hampir🤏",
            "teroooos!!!!!",
            "sabarrrrr cinai😀 ",
            "ayo cemangat💪",
            "sikit lagi⏳",
            "lagi lagi lagi 😜",
            "one more👊1",
        ];

        function moveButton() {
            clickSound.play(); // Mainkan suara tombol klik
            if (counter == 0) {
                // Ganti teks tombol pada klik pertama
                button.innerText = "klik dong";
            } else {
                // Ganti teks tombol setiap kali setelah klik pertama
                button.innerText = variations[counter - 1]; 
            }

            if (counter < 10) { // Tombol bisa diklik hingga 20 kali
                const randomX = Math.random() * 65 + 25; // X acak lebih jauh
                const randomY = Math.random() * 65 + 25; // Y acak lebih jauh
                button.style.left = `${randomX}%`;
                button.style.top = `${randomY}%`;

                counter++;
            } else {
                finalSound.play(); // Mainkan suara terakhir
                message1.classList.add('show-message'); // Menambahkan kelas untuk efek pembesaran teks
                message2.classList.add('show-message'); // Menambahkan kelas untuk efek pembesaran teks
                
                // Menambahkan jeda untuk pesan-pesan berikutnya
                setTimeout(() => {
                    message3.classList.add('show-message');
                }, 000);  // Pesan 3 muncul setelah 000 detik

                setTimeout(() => {
                    message4.classList.add('show-message');
                }, 0000);  // Pesan 4 muncul setelah 0 detik

                createHearts(); // Menampilkan efek hati
                button.innerHTML = "💖"; // Tampilkan pesan akhir dan emotikon
                button.style.pointerEvents = 'none'; // Nonaktifkan tombol setelah selesai
            }
        }

        function createHearts() {
            for (let i = 0; i < 50; i++) {
                const heart = document.createElement('div');
                heart.classList.add('heart');
                heart.style.left = `${Math.random() * 100}%`;
                heart.style.top = `${Math.random() * 100}%`;
                heart.style.animationDelay = `${Math.random() * 2}s`;
                heartContainer.appendChild(heart);
            }
        }
    </script>
</body>
</html>
