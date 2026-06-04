<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>A Special Question For You ✨</title>
    <!-- Google Fonts for Elegant Typography -->
    <link rel="preconnect" href="https://googleapis.com">
    <link rel="preconnect" href="https://gstatic.com" crossorigin>
    <link href="https://googleapis.com/css2?family=Dancing+Script:wght@700&family=Quicksand:wght@500;700&display=swap" rel="family">
    
    <style>
        :root {
            --primary-pink: #ff6584;
            --dark-pink: #ff3366;
            --light-pink: #ffeef2;
            --glass-bg: rgba(255, 255, 255, 0.75);
            --glass-border: rgba(255, 182, 193, 0.4);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Quicksand', sans-serif;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: linear-gradient(135deg, #ffe5ec 0%, #ffc2d1 50%, #ffb3c6 100%);
            overflow: hidden;
            position: relative;
        }

        /* Premium Floating Particles Background */
        #particle-canvas {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            pointer-events: none;
        }

        /* Cinematic Glassmorphism Container */
        .card-wrapper {
            position: relative;
            z-index: 10;
            width: 90%;
            max-width: 480px;
            perspective: 1000px;
        }

        .proposal-card {
            background: var(--glass-bg);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid var(--glass-border);
            padding: 40px 30px;
            border-radius: 32px;
            box-shadow: 0 20px 40px rgba(255, 101, 132, 0.15), 
                        inset 0 1px 0 rgba(255, 255, 255, 0.6);
            text-align: center;
            transition: all 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
            transform-style: preserve-3d;
        }

        /* Premium Image/GIF Holder */
        .image-container {
            width: 160px;
            height: 160px;
            margin: 0 auto 25px auto;
            border-radius: 50%;
            border: 4px solid white;
            box-shadow: 0 8px 24px rgba(255, 101, 132, 0.2);
            overflow: hidden;
            background: #fff;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .image-container img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        h1 {
            font-family: 'Dancing Script', cursive;
            color: var(--dark-pink);
            font-size: 42px;
            margin-bottom: 12px;
            text-shadow: 1px 1px 0px rgba(255,255,255,0.8);
        }

        .subtitle {
            color: #664d55;
            font-size: 16px;
            margin-bottom: 35px;
            font-weight: 500;
        }

        /* Interactive Professional Layout Action Row */
        .action-row {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 25px;
            min-height: 60px;
            position: relative;
        }

        .btn {
            padding: 14px 38px;
            font-size: 18px;
            font-weight: 700;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: transform 0.2s cubic-bezier(0.175, 0.885, 0.32, 1.275), 
                        box-shadow 0.2s, background-color 0.3s;
            font-family: 'Quicksand', sans-serif;
        }

        #yes-button {
            background: linear-gradient(135deg, var(--primary-pink) 0%, var(--dark-pink) 100%);
            color: white;
            box-shadow: 0 10px 25px rgba(255, 51, 102, 0.35);
            z-index: 12;
        }

        #yes-button:hover {
            transform: scale(1.08) translateY(-2px);
            box-shadow: 0 14px 30px rgba(255, 51, 102, 0.45);
        }

        #yes-button:active {
            transform: scale(0.98) translateY(0);
        }

        #no-button {
            background: white;
            color: var(--primary-pink);
            border: 2px solid rgba(255, 101, 132, 0.3);
            box-shadow: 0 6px 15px rgba(0,0,0,0.05);
            position: absolute;
            transition: left 0.25s cubic-bezier(0.19, 1, 0.22, 1), 
                        top 0.25s cubic-bezier(0.19, 1, 0.22, 1), 
                        transform 0.1s;
        }

        /* Success State UI Changes */
        .success-state {
            display: none;
            animation: scaleUp 0.6s cubic-bezier(0.34, 1.56, 0.64, 1) forwards;
        }

        @keyframes scaleUp {
            0% { transform: scale(0.8); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }

        .celebration-text {
            font-family: 'Dancing Script', cursive;
            font-size: 48px;
            color: var(--dark-pink);
            margin-top: 15px;
        }
    </style>
</head>
<body>

    <!-- Particle Engine Layer -->
    <canvas id="particle-canvas"></canvas>

    <!-- Main Dynamic Application Container -->
    <div class="card-wrapper">
        
        <!-- Proposal Interface -->
        <div id="proposal-card" class="proposal-card">
            <div class="image-container">
                <!-- Premium dynamic placeholder. You can swap this URL with your custom cute photo/GIF link anytime! -->
                <img id="display-gif" src="https://giphy.com" alt="Cute Valentine Cartoon">
            </div>
            <h1>Will you be my Valentine?</h1>
            <p class="subtitle">Every moment with you feels like a beautiful fairytale...</p>
            
            <div class="action-row" id="action-row">
                <button id="yes-button" class="btn">Yes, I will!</button>
                <button id="no-button" class="btn">No</button>
            </div>
        </div>

        <!-- Professional Success View State -->
        <div id="success-card" class="proposal-card success-state">
            <div class="image-container">
                <img src="https://giphy.com" alt="Happy Love Cartoon">
            </div>
            <h1 class="celebration-text">It's an absolute Yes! 💖</h1>
            <p class="subtitle" style="margin-bottom: 0; font-size: 18px;">You've made me the happiest person in the universe. I love you! ✨</p>
        </div>

    </div>

    <!-- Interactive Script Architecture -->
    <script>
        const noBtn = document.getElementById('no-button');
        const yesBtn = document.getElementById('yes-button');
        const actionRow = document.getElementById('action-row');
        const proposalCard = document.getElementById('proposal-card');
        const successCard = document.getElementById('success-card');
        const displayGif = document.getElementById('display-gif');

        // Set initial alignment configuration for the No button inside the row wrapper
        function initButtonLayout() {
            const rowRect = actionRow.getBoundingClientRect();
            const yesRect = yesBtn.getBoundingClientRect();
            
            // Calculate standard geometric position next to Yes button
            const initialLeft = yesRect.right - rowRect.left + 25; 
            noBtn.style.left = initialLeft + 'px';
            noBtn.style.top = '6px';
        }
        window.addEventListener('load', initButtonLayout);
        window.addEventListener('resize', initButtonLayout);

        // Smart Evasive Movement Physics Architecture for the "No" Action
        function evadeButton() {
            // Update to a pleading/sad face placeholder when they try to click "No"
            displayGif.src = "https://giphy.com";

            const padding = 30;
            // Generate coordinates over the entire viewport screen range
            const maxX = window.innerWidth - noBtn.offsetWidth - padding;
            const maxY = window.innerHeight - noBtn.offsetHeight - padding;

            const randomX = Math.max(padding, Math.floor(Math.random() * maxX));
            const randomY = Math.max(padding, Math.floor(Math.random() * maxY));

            // Shift element configuration dynamically out of standard document layout bounds
            noBtn.style.position = 'fixed';
            noBtn.style.left = randomX + 'px';
            noBtn.style.top = randomY + 'px';
        }

        // Trigger evasion instantly on cursor move-in, touch start, or attempt to click
        noBtn.addEventListener('mouseenter', evadeButton);
        noBtn.addEventListener('click', evadeButton);
        noBtn.addEventListener('touchstart', (e) => {
            e.preventDefault();
            evadeButton();
        });

        // Yes Button Viewport Controller Execution Flow
        yesBtn.addEventListener('click', () => {
            proposalCard.style.display = 'none';
            successCard.style.display = 'block';
            triggerSuccessExplosion();
        });

        /* ==========================================
           PROFESSIONAL CANVAS HEART PARTICLE ENGINE
           ========================================== */
