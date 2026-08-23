<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Untuk Kamu ❤️</title>

    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #ff758c, #ff7eb3);
            overflow: hidden;
        }

        .container {
            width: 90%;
            max-width: 450px;
            background: white;
            padding: 35px 25px;
            border-radius: 25px;
            text-align: center;
            box-shadow: 0 15px 40px rgba(0,0,0,0.2);
            position: relative;
            z-index: 2;
        }

        .heart {
            font-size: 65px;
            animation: heartbeat 1.2s infinite;
        }

        @keyframes heartbeat {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.2);
            }
        }

        h1 {
            color: #ff4f70;
            margin-bottom: 15px;
        }

        p {
            color: #555;
            line-height: 1.7;
            font-size: 16px;
        }

        .question {
            font-size: 20px;
            font-weight: bold;
            color: #333;
            margin-top: 25px;
        }

        button {
            border: none;
            padding: 13px 25px;
            border-radius: 30px;
            font-size: 16px;
            cursor: pointer;
            margin: 10px;
            transition: 0.3s;
        }

        #yes {
            background: #ff4f70;
            color: white;
        }

        #yes:hover {
            transform: scale(1.1);
            background: #ff3158;
        }

        #no {
            background: #eee;
            color: #555;
            position: relative;
        }

        #result {
            display: none;
            margin-top: 20px;
            font-size: 20px;
            color: #ff4f70;
            font-weight: bold;
        }

        .floating-heart {
            position: absolute;
            bottom: -50px;
            font-size: 25px;
            animation: floatUp 6s linear infinite;
            opacity: 0.8;
        }

        @keyframes floatUp {
            from {
                transform: translateY(0);
                opacity: 0;
            }
            20% {
                opacity: 1;
            }
            to {
                transform: translateY(-110vh);
                opacity: 0;
            }
        }
    </style>
</head>

<body>

    <div class="container">
        <div class="heart">👉👈</div>

        <h1>Hai, Kak Alanis!</h1>

        <p>
            Sebenarnya ada sesuatu yang sudah lama ingin aku sampaikan. Aku nyaman banget ngobrol dan dekat sama kamu. Makin lama, aku sadar kalau perasaanku ke kamu bukan cuma sekadar teman dan kakak. Jadi aku mau jujur… aku suka sama kamu. 
        </p>

        <p>
            Mungkin aku bukan orang yang paling sempurna ataupun orang pertama tapi bagiku kamu lah orang pertama yang aku sukai
        </p>

        <div class="question">
            Jadi... kakak mau nggak jadi pacarku? ❤️
        </div>

        <br>

        <button id="yes" onclick="diterima()">
            MAU ❤️
        </button>

        <button id="no" onmouseover="lari()">
            Nggak 😭
        </button>

        <div id="result">
            YEEEAY! ❤️🥹<br>
            Mulai hari ini kita punya cerita baru.
        </div>
    </div>

    <script>
        function diterima() {
            document.getElementById("result").style.display = "block";

            document.getElementById("yes").innerHTML =
                "akhirnya ❤️";

            buatHati();
        }

        function lari() {
            const button = document.getElementById("no");

            const maxX = window.innerWidth - button.offsetWidth - 20;
            const maxY = window.innerHeight - button.offsetHeight - 20;

            const x = Math.random() * maxX;
            const y = Math.random() * maxY;

            button.style.position = "fixed";
            button.style.left = x + "px";
            button.style.top = y + "px";
        }

        function buatHati() {
            for (let i = 0; i < 30; i++) {
                const heart = document.createElement("div");

                heart.innerHTML = "❤️";
                heart.classList.add("floating-heart");

                heart.style.left = Math.random() * 100 + "vw";
                heart.style.animationDuration =
                    (3 + Math.random() * 4) + "s";

                heart.style.fontSize =
                    (15 + Math.random() * 25) + "px";

                document.body.appendChild(heart);

                setTimeout(() => {
                    heart.remove();
                }, 7000);
            }
        }
    </script>

</body>
</html>
