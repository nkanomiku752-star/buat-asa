# buat-asa
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Love for Asa</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #ff6b6b, #ff8e8e, #ffb6b6);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            overflow-x: hidden;
            color: #fff;
            text-align: center;
        }

        .container {
            max-width: 800px;
            padding: 3rem 2rem;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .hearts-container {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
            margin: 3rem 0;
        }

        .heart {
            font-size: 4rem;
            color: #ff4757;
            text-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
            animation: float 3s ease-in-out infinite;
            transition: transform 0.3s ease;
        }

        .heart:hover {
            transform: scale(1.3);
        }

        .heart:nth-child(2n) {
            animation-delay: 1s;
            color: #ff9f43;
        }

        .heart:nth-child(3n) {
            animation-delay: 2s;
            color: #ff6b81;
        }

        .heart:nth-child(4n) {
            animation-delay: 1.5s;
            color: #ff7675;
        }

        .name-display {
            font-size: 5rem;
            font-weight: bold;
            color: #fff;
            text-shadow: 0 4px 15px rgba(0, 0, 0, 0.4);
            margin: 2rem 0;
            font-family: 'Georgia', serif;
            letter-spacing: 3px;
            background: linear-gradient(45deg, #ff4757, #ff9f43, #ff6b81);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: glow 2s ease-in-out infinite alternate;
        }

        .love-message {
            font-size: 3rem;
            font-weight: bold;
            color: #fff;
            text-shadow: 0 4px 15px rgba(0, 0, 0, 0.4);
            margin: 3rem 0;
            padding: 2rem;
            background: rgba(255, 255, 255, 0.15);
            border-radius: 20px;
            animation: pulse 2s ease-in-out infinite;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        .floating-hearts {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .floating-heart {
            position: absolute;
            font-size: 2.5rem;
            color: #ff4757;
            opacity: 0.4;
            animation: floatUp 8s linear infinite;
        }

        .interactive-section {
            margin: 2rem 0;
        }

        .love-button {
            background: linear-gradient(45deg, #ff4757, #ff6b81);
            border: none;
            padding: 18px 35px;
            font-size: 1.4rem;
            color: white;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 6px 20px rgba(255, 71, 87, 0.4);
            font-weight: bold;
        }

        .love-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(255, 71, 87, 0.6);
            background: linear-gradient(45deg, #ff6b81, #ff4757);
        }

        .love-button:active {
            transform: translateY(0);
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0px) rotate(0deg);
            }
            25% {
                transform: translateY(-15px) rotate(5deg);
            }
            50% {
                transform: translateY(-25px) rotate(0deg);
            }
            75% {
                transform: translateY(-15px) rotate(-5deg);
            }
        }

        @keyframes floatUp {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 0.5;
            }
            90% {
                opacity: 0.5;
            }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }

        @keyframes pulse {
            0%, 100% {
                transform: scale(1);
                box-shadow: 0 0 20px rgba(255, 71, 87, 0.3);
            }
            50% {
                transform: scale(1.02);
                box-shadow: 0 0 30px rgba(255, 71, 87, 0.5);
            }
        }

        @keyframes glow {
            from {
                text-shadow: 0 0 20px rgba(255, 71, 87, 0.5);
            }
            to {
                text-shadow: 0 0 30px rgba(255, 71, 87, 0.8), 0 0 40px rgba(255, 71, 87, 0.6);
            }
        }

        @media (max-width: 768px) {
            .container {
                margin: 1rem;
                padding: 2rem 1.5rem;
            }
            
            .name-display {
                font-size: 3.5rem;
            }
            
            .heart {
                font-size: 3rem;
            }
            
            .love-message {
                font-size: 2rem;
                padding: 1.5rem;
            }
            
            .love-button {
                font-size: 1.2rem;
                padding: 15px 25px;
            }
        }

        footer {
            margin-top: 3rem;
            color: rgba(255, 255, 255, 0.7);
            font-size: 1rem;
        }
    </style>
</head>
<body>
    <div class="floating-hearts" id="floatingHearts"></div>
    
    <div class="container">
        <div class="hearts-container">
            <div class="heart">♥</div>
            <div class="heart">♥</div>
            <div class="heart">♥</div>
            <div class="heart">♥</div>
            <div class="heart">♥</div>
            <div class="heart">♥</div>
            <div class="heart">♥</div>
            <div class="heart">♥</div>
        </div>

        <div class="name-display">
            Asa
        </div>

        <div class="love-message">
            haha loveee youuu pacarkuuuuuu
        </div>

        <div class="hearts-container">
            <div class="heart">♥</div>
            <div class="heart">♥</div>
            <div class="heart">♥</div>
            <div class="heart">♥</div>
            <div class="heart">♥</div>
            <div class="heart">♥</div>
            <div class="heart">♥</div>
            <div class="heart">♥</div>
        </div>

        <div class="interactive-section">
            <button class="love-button" onclick="showLove()">
                💖 Kirim Lebih Banyak Cinta 💖
            </button>
        </div>
    </div>

    <footer>
        Made with ♥ | Special for Asa
    </footer>

    <script>
        // Create floating hearts background
        function createFloatingHearts() {
            const container = document.getElementById('floatingHearts');
            const heartCount = 30;
            
            for (let i = 0; i < heartCount; i++) {
                const heart = document.createElement('div');
                heart.className = 'floating-heart';
                heart.innerHTML = '♥';
                heart.style.left = Math.random() * 100 + 'vw';
                heart.style.animationDuration = (Math.random() * 8 + 6) + 's';
                heart.style.animationDelay = Math.random() * 10 + 's';
                heart.style.fontSize = (Math.random() * 30 + 20) + 'px';
                
                // Random heart colors
                const colors = ['#ff4757', '#ff9f43', '#ff6b81', '#ff7675', '#e84393'];
                heart.style.color = colors[Math.floor(Math.random() * colors.length)];
                
                container.appendChild(heart);
            }
        }

        // Show love animation
        function showLove() {
            const hearts = document.querySelectorAll('.heart');
            hearts.forEach((heart, index) => {
                setTimeout(() => {
                    heart.style.transform = 'scale(1.5) rotate(15deg)';
                    heart.style.textShadow = '0 8px 20px rgba(255, 255, 255, 0.8)';
                    
                    setTimeout(() => {
                        heart.style.transform = 'scale(1) rotate(0deg)';
                        heart.style.textShadow = '0 4px 12px rgba(0, 0, 0, 0.3)';
                    }, 500);
                }, index * 100);
            });

            // Create more temporary floating hearts
            for (let i = 0; i < 15; i++) {
                setTimeout(() => createTemporaryHeart(), i * 120);
            }
            
            // Add pulse effect to the message
            const message = document.querySelector('.love-message');
            message.style.animation = 'none';
            setTimeout(() => {
                message.style.animation = 'pulse 2s ease-in-out infinite';
            }, 10);
        }

        function createTemporaryHeart() {
            const heart = document.createElement('div');
            heart.style.position = 'fixed';
            heart.style.fontSize = '3rem';
            heart.style.zIndex = '1000';
            heart.style.pointerEvents = 'none';
            heart.innerHTML = '♥';
            heart.style.left = Math.random() * 80 + 10 + 'vw';
            heart.style.top = '80vh';
            heart.style.animation = 'floatUp 4s ease-out forwards';
            
            // Random heart colors
            const colors = ['#ff4757', '#ff9f43', '#ff6b81', '#ff7675', '#e84393'];
            heart.style.color = colors[Math.floor(Math.random() * colors.length)];
            
            document.body.appendChild(heart);
            
            setTimeout(() => {
                document.body.removeChild(heart);
            }, 4000);
        }

        // Add click sound effect
        function playHeartSound() {
            const audio = new Audio('data:audio/wav;base64,UklGRnoGAABXQVZFZm10IBAAAAABAAEAQB8AAEAfAAABAAgAZGF0YQoGAACBhYqFbF1fdJivrJBhNjVgodDbq2EcBj+a2/LDciUFLIHO8tiJNwgZaLvt559NEAxQp+PwtmMcBjiR1/LJfzAIJHfH8N2QQAoRXrDl6rp0Jgo+qOLxzIU2CBVjsefvwHUjBCuA0vHgiDgFDGix7vXWeScFJnjR8uCJOAUKZLDr9Nd5JgUfcdTx3o08BQVjsez113kmBRxt0fDcjT4FBWGx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7PXXeSYFGmnP8NyNPgUFY7Hs9dd5JgUaac/w3I0+BQVjsez113kmBRppz/DcjT4FBWOx7P');
            audio.volume = 0.3;
            audio.play().catch(() => {});
        }

        // Initialize
        document.addEventListener('DOMContentLoaded', function() {
            createFloatingHearts();
            
            // Add click effect to hearts
            document.querySelectorAll('.heart').forEach(heart => {
                heart.addEventListener('click', function() {
                    playHeartSound();
                    this.style.transform = 'scale(1.4) rotate(10deg)';
                    this.style.textShadow = '0 6px 15px rgba(255, 255, 255, 0.6)';
                    
                    setTimeout(() => {
                        this.style.transform = 'scale(1) rotate(0deg)';
                        this.style.textShadow = '0 4px 12px rgba(0, 0, 0, 0.3)';
                    }, 300);
                });
            });
            
            // Auto pulse effect for message
            setInterval(() => {
                const message = document.querySelector('.love-message');
                message.style.animation = 'none';
                setTimeout(() => {
                    message.style.animation = 'pulse 2s ease-in-out infinite';
                }, 10);
            }, 5000);
        });
    </script>
</body>
</html>
