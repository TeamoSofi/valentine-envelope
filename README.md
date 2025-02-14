<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sobre de San Valentín</title>
    <style>
        body {
            background: #f8c8dc;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
            position: relative;
            overflow: hidden;
        }
        .background-elements {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
        }
        .background-elements img {
            position: absolute;
            width: 150px;
            animation: float 3s infinite ease-in-out alternate;
        }
        .snoopy { top: 10%; left: 5%; }
        .snoopy2 { bottom: 10%; right: 5%; }
        .snoopy3 { top: 20%; right: 10%; }
        .snoopy4 { bottom: 30%; left: 15%; }
        .snoopy5 { top: 50%; left: 50%; transform: translate(-50%, -50%); }
        
        @keyframes float {
            0% { transform: translateY(0); }
            100% { transform: translateY(-10px); }
        }
        
        .star {
            position: absolute;
            width: 20px;
            height: 20px;
            background: gold;
            border-radius: 50%;
            box-shadow: 0 0 10px gold;
            animation: twinkle 1.5s infinite alternate;
        }
        
        @keyframes twinkle {
            0% { opacity: 0.5; transform: scale(1); }
            100% { opacity: 1; transform: scale(1.2); }
        }
        
        .envelope {
            position: relative;
            width: 300px;
            height: 200px;
            background: #f4a4b4;
            border-radius: 10px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            overflow: hidden;
            cursor: pointer;
        }
        .flap {
            position: absolute;
            top: 0;
            width: 100%;
            height: 100px;
            background: #e68fa4;
            clip-path: polygon(50% 0%, 100% 100%, 0% 100%);
            transition: transform 1s;
            transform-origin: top;
        }
        .card {
            position: absolute;
            bottom: -150px;
            left: 50%;
            transform: translateX(-50%);
            width: 85%;
            height: 120px;
            background: white;
            text-align: center;
            padding: 20px;
            font-size: 18px;
            color: #d14769;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            transition: bottom 1.2s ease-in-out;
            opacity: 0;
        }
        .golden-heart {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 30px;
            color: gold;
        }
        .open .flap { transform: rotateX(180deg); }
        .open .card { bottom: 40px; opacity: 1; transition: bottom 1.2s ease-in-out, opacity 0.5s ease-in; }
    </style>
</head>
<body>
    <div class="background-elements">
        <img src="https://upload.wikimedia.org/wikipedia/en/5/53/Snoopy_Peanuts.png" class="snoopy">
        <img src="https://upload.wikimedia.org/wikipedia/en/5/53/Snoopy_Peanuts.png" class="snoopy2">
        <img src="https://upload.wikimedia.org/wikipedia/en/5/53/Snoopy_Peanuts.png" class="snoopy3">
        <img src="https://upload.wikimedia.org/wikipedia/en/5/53/Snoopy_Peanuts.png" class="snoopy4">
        <img src="https://upload.wikimedia.org/wikipedia/en/5/53/Snoopy_Peanuts.png" class="snoopy5">
    </div>
    <div class="envelope" id="envelope">
        <div class="flap"></div>
        <div class="golden-heart">💛</div>
        <div class="card" id="card">¡Feliz San Valentín Mi Wawita Mosha! le agradezco por estar en mi vida, y hacerla mas feliz cada que estoy junto a usted  ❤️</div>
    </div>
    <audio id="music" preload="auto">
        <source src="https://www.bensound.com/bensound-music/bensound-romantic.ogg" type="audio/ogg">
        <source src="https://www.bensound.com/bensound-music/bensound-romantic.mp3" type="audio/mp3">
        Tu navegador no soporta la reproducción de audio.
    </audio>
    <script>
        document.addEventListener("DOMContentLoaded", function() {
            const envelope = document.getElementById("envelope");
            const music = document.getElementById("music");
            
            envelope.addEventListener("click", function() {
                this.classList.toggle("open");
                if (this.classList.contains("open")) {
                    music.play().catch(error => console.error("Error al reproducir la música", error));
                } else {
                    music.pause();
                    music.currentTime = 0;
                }
            });
        });
    </script>
