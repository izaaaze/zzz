<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Last Day UAS</title>
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
            font-size: 2rem;
            color: #FFF;
            margin-top: 20px;
            display: none;
            transition: transform 1s ease-out, font-size 1s ease-out;
        }

        h1.show-message {
            display: block;
            transform: scale(1.2);
        }

        button {
            padding: 12px 20px;
            font-size: 1rem;
            color: #FFF;
            background: #FF6F61;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            position: absolute;
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

        @media screen and (max-width: 375px) {
            h1 {
                font-size: 1.6rem;
            }
            button {
                padding: 10px 15px;
                font-size: 0.9rem;
            }
        }

        .footer {
            font-size: 1rem;
            color: #FFF;
            margin-top: 50px;
            position: absolute;
            bottom: 10px;
            left: 50%;
            transform: translateX(-50%);
        }
    </style>
</head>
<body>
    <div class="container">
        <button id="annoying-button" onclick="moveButton()">Klik aku!</button>
        <h1 id="message-1">LAST DAY UAS??</h1>
        <h1 id="message-2">Cemangat nailacuantiks!!</h1>
        <h1 id="message-3">Semoga diberikan kemudahan</h1>
        <h1 id="message-4">See u hehehe</h1>
        <div class="hearts"></div>
    </div>
    <div class="footer">☠️Dibuat oleh Admin Hengker☠️</div>

    <script>
        const button = document.getElementById('annoying-button');
        const message1 = document.getElementById('message-1');
        const message2 = document.getElementById('message-2');
        const message3 = document.getElementById('message-3');
        const message4 = document.getElementById('message-4');
        const heartContainer = document.querySelector('.hearts');
        let counter = 0;

        const messages = [
            "guys klik guys😁",
            "klikkkk disini nayyy👈",
            "hampir🤏",
            "teroooos!!!!!",
            "sabar cinai😀",
            "ayo cemangat💪",
            "sikit lagi⏳",
            "lagi lagi lagi 😜",
            "one more👊"
        ];

        function moveButton() {
            if (counter < messages.length) {
                const randomX = Math.random() * 75;
                const randomY = Math.random() * 75;
                button.style.left = `${randomX}%`;
                button.style.top = `${randomY}%`;
                button.innerText = messages[counter];
                counter++;
            } else {
                message1.classList.add('show-message');
                setTimeout(() => message2.classList.add('show-message'), 500);
                setTimeout(() => message3.classList.add('show-message'), 1000);
                setTimeout(() => message4.classList.add('show-message'), 1500);
                button.remove();
                createHearts();
            }
        }

        function createHearts() {
            for (let i = 0; i < 30; i++) {
                const heart = document.createElement('div');
                heart.classList.add('heart');
                heart.style.left = `${Math.random() * 100}%`;
                heart.style.top = `${Math.random() * 100}%`;
                heartContainer.appendChild(heart);
            }
        }
    </script>
</body>
</html>
