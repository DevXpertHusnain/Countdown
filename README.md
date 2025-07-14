

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Special Countdown</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }

        body {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);
            color: #fff;
            overflow: hidden;
        }

        .container {
            text-align: center;
            padding: 1.5rem;
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
            z-index: 10;
            max-width: 800px;
            width: 90%;
        }

        h1 {
            font-size: 2.5rem;
            margin-bottom: 2rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
            color: #ff4757;
        }

        .countdown {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            flex-wrap: wrap;
        }

        .countdown-item {
            text-align: center;
            min-width: 120px;
        }

        .countdown-number {
            font-size: 3rem;
            font-weight: bold;
            background: rgba(255, 255, 255, 0.2);
            padding: 1rem;
            border-radius: 10px;
            margin-bottom: 0.5rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            color: #fff;
        }

        .countdown-label {
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            color: #ff4757;
            font-weight: bold;
        }

        .heart {
            position: absolute;
            pointer-events: none;
            animation: float 6s ease-in-out infinite;
            opacity: 0.6;
            display: block;
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0) rotate(0deg);
            }
            50% {
                transform: translateY(-20px) rotate(5deg);
            }
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 2rem;
                margin-bottom: 1.5rem;
                padding: 0 1rem;
            }
            
            .countdown {
                gap: 0.5rem;
            }
            
            .countdown-item {
                min-width: auto;
                width: 22%;
            }
            
            .countdown-number {
                font-size: 1.8rem;
                padding: 0.5rem;
            }
            
            .countdown-label {
                font-size: 0.7rem;
                letter-spacing: 1px;
            }
        }

        @media (max-width: 480px) {
            h1 {
                font-size: 1.6rem;
            }
            
            .countdown-number {
                font-size: 1.5rem;
            }
            
            .countdown-label {
                font-size: 0.6rem;
            }

            .heart {
                display: none;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>For Someone Special's  Birthday🎈🎂   A💞</h1>
        <div class="countdown">
            <div class="countdown-item">
                <div class="countdown-number" id="days">00</div>
                <div class="countdown-label">Days</div>
            </div>
            <div class="countdown-item">
                <div class="countdown-number" id="hours">00</div>
                <div class="countdown-label">Hours</div>
            </div>
            <div class="countdown-item">
                <div class="countdown-number" id="minutes">00</div>
                <div class="countdown-label">Minutes</div>
            </div>
            <div class="countdown-item">
                <div class="countdown-number" id="seconds">00</div>
                <div class="countdown-label">Seconds</div>
            </div>
        </div>
    </div>

    <!-- Floating hearts background -->
    <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/350f613f-830e-4840-8467-0bdfa7a90aa6.png" alt="Small pink heart shape floating in background" class="heart" style="top: 20%; left: 10%;">
    <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/3e763122-cfc5-40c3-88d3-a96a29cacd24.png" alt="Medium pink heart shape floating in background" class="heart" style="top: 60%; left: 80%; animation-delay: 1s;">
    <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/c069351a-ab85-4f82-a8e6-bf5ef8fabf06.png" alt="Small pink heart shape floating in background" class="heart" style="top: 80%; left: 30%; animation-delay: 2s;">
    <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/2b4e1f61-fdce-4fba-9ad1-50e56a9b1122.png" alt="Medium pink heart shape floating in background" class="heart" style="top: 30%; left: 65%; animation-delay: 3s;">
    <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/389244eb-0a0f-4bd2-884f-0376aa1ddbd8.png" alt="Tiny pink heart shape floating in background" class="heart" style="top: 75%; left: 15%; animation-delay: 4s;">

    <script>
        const targetDate = new Date('July 15, 2025 00:00:00').getTime();
        
        function updateCountdown() {
            const now = new Date().getTime();
            const distance = targetDate - now;
            
            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);
            
            document.getElementById('days').textContent = days.toString().padStart(2, '0');
            document.getElementById('hours').textContent = hours.toString().padStart(2, '0');
            document.getElementById('minutes').textContent = minutes.toString().padStart(2, '0');
            document.getElementById('seconds').textContent = seconds.toString().padStart(2, '0');
            
            // Add pulse animation when numbers change
            document.querySelectorAll('.countdown-number').forEach(el => {
                el.classList.add('pulse');
                setTimeout(() => el.classList.remove('pulse'), 300);
            });
        }
        
        // Initial call
        updateCountdown();
        
        // Update every second
        setInterval(updateCountdown, 1000);

        // Create floating hearts (optimized for mobile)
        function createHeart() {
            if (window.innerWidth < 480) return;
            
            const heart = document.createElement('img');
            heart.src = 'https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/ffd45567-fe85-4f19-b65c-2c32e8bcbc10.png';
            heart.alt = 'Small decorative heart floating in background';
            heart.className = 'heart';
            
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.top = Math.random() * 100 + 'vh';
            heart.style.animationDuration = (Math.random() * 3 + 3) + 's';
            heart.style.animationDelay = (Math.random() * 5) + 's';
            heart.style.opacity = Math.random() * 0.4 + 0.3;
            heart.style.width = (Math.random() * 20 + 15) + 'px';
            
            document.body.appendChild(heart);
            
            setTimeout(() => {
                heart.remove();
            }, 8000);
        }
        
        // Create hearts periodically
        setInterval(createHeart, 500);
    </script>
</body>
</html>
