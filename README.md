" UNKNOWN MESSAGE "
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NOTE FOR YOU</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Outfit:wght@300;600&display=swap');

        * { box-sizing: border-box; margin: 0; padding: 0; }

        body {
            margin: 0;
            font-family: 'Outfit', sans-serif;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: linear-gradient(45deg, #ff9a9e, #fad0c4, #a1c4fd, #c2e9fb);
            background-size: 400% 400%;
            animation: gradientBG 10s ease infinite;
            overflow: hidden;
            flex-direction: column;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        
        .emoji {
            position: fixed;
            bottom: -50px;
            font-size: 24px;
            user-select: none;
            z-index: 1;
            animation: floatUp linear infinite;
        }

        @keyframes floatUp {
            0% { transform: translateY(0) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-110vh) rotate(360deg); opacity: 0; }
        }

        
        .card {
            position: relative;
            z-index: 10; 
            background: rgba(255, 255, 255, 0.25);
            backdrop-filter: blur(15px);
            -webkit-backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 30px;
            padding: 40px;
            text-align: center;
            box-shadow: 0 15px 35px rgba(0,0,0,0.1);
            width: 340px;
            max-height: 80vh; /* Restricts height to make it scrollable */
            overflow-y: auto; /* Enable vertical scrolling */
        }

        h2 { color: white; margin-bottom: 20px; text-shadow: 0 2px 4px rgba(0,0,0,0.1); }

        input {
            width: 100%;
            padding: 15px;
            border-radius: 15px;
            border: none;
            margin-bottom: 20px;
            outline: none;
            background: rgba(255, 255, 255, 0.8);
            text-align: center;
            font-size: 1rem;
        }

        button {
            width: 100%;
            padding: 15px;
            border-radius: 15px;
            border: none;
            background: linear-gradient(90deg, #ff8da1, #ffacc5);
            color: white;
            font-weight: 600;
            cursor: pointer;
            transition: 0.3s;
            text-transform: uppercase;
        }

        button:hover { transform: translateY(-3px); box-shadow: 0 5px 15px rgba(255,141,161,0.4); }

        #private-content { display: none; }

    </style>
</head>
<body>

    <audio id="bgMusic" loop>
        <source src="statue.mp3" type="audio/mpeg">
    </audio>

    <div id="login-screen" class="card">
        <h2>Enter Key 🥰</h2>
        <input type="password" id="keyInput" placeholder="Password...">
        <button onclick="unlockSite()">OPEN NOTE</button>
    </div>

    <div id="private-content" class="card">
        <h2> 𝚕𝚘𝚟𝚒𝚗𝚐 𝚢𝚘𝚞 𝚏𝚛𝚘𝚖 𝚊𝚏𝚊𝚛 💕</h2>
        <p style="color: white; line-height: 1.5;">I admired you quietly, keeping my heart in check because I knew our paths would never align. I cherished every glance, every small smile, every moment I could see you real even when I knew I could never be part of it. I chose appreciation over expectation, patience over confession, and silence over asking for more. Not because I was okay with less, but because admiration sometimes means loving without taking.
There were moments I wished things could be different, that our worlds could overlap even a little. But deep down, I knew you could never meet me halfway, and my heart had to learn to hold that ache without breaking. Loving quietly like this doesn't scream—it lingers softly, teaching you how to carry longing without losing yourself.
So I continue to admire without expecting. To care without hoping. To keep my feelings tucked safely inside, knowing that even from a distance, loving someone quietly can still be beautiful and still hurt.</p>
        <button onclick="lockSite()" style="margin-top: 20px; background: #666;">CLOSE</button>
    </div>

    <script>
        const song = document.getElementById("bgMusic");

        
        function createEmoji() {
            const emoji = document.createElement('div');
            emoji.className = 'emoji';
            emoji.innerText = '🥰';
            
            
            emoji.style.left = Math.random() * 100 + 'vw';
            
            
            emoji.style.fontSize = (Math.random() * 20 + 20) + 'px';
            
            
            const duration = Math.random() * 5 + 5;
            emoji.style.animationDuration = duration + 's';
            
            
            emoji.style.opacity = Math.random() * 0.5 + 0.5;

            document.body.appendChild(emoji);

            
            setTimeout(() => {
                emoji.remove();
            }, duration * 1000);
        }

        
        setInterval(createEmoji, 500);

        function unlockSite() {
            const pass = document.getElementById("keyInput").value;
            if(pass === "aisha") {
                document.getElementById("login-screen").style.display = "none";
                document.getElementById("private-content").style.display = "block";
                song.play();
            } else {
                alert("Wrong Key! Try again 🌸");
            }
        }

        function lockSite() {
            song.pause();
            song.currentTime = 0;
            document.getElementById("keyInput").value = "";
            document.getElementById("private-content").style.display = "none";
            document.getElementById("login-screen").style.display = "block";
        }
    </script>
</body>
</html>
