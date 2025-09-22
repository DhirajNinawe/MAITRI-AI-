<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MAITRI - Astronaut Well-being Platform</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-dark-navy: #030712;
            --primary-glow: #0ea5e9; /* sky blue */
            --secondary-glow: #a855f7; /* purple */
            --text-primary: #f9fafb;
            --text-secondary: #9ca3af;
            --panel-bg: rgba(15, 23, 42, 0.5);
            --panel-border: rgba(56, 189, 248, 0.2);
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--bg-dark-navy);
            color: var(--text-primary);
            overflow: hidden;
        }
        
        #background-canvas {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            z-index: -1;
        }

        .hud-panel {
            background: var(--panel-bg);
            border: 1px solid var(--panel-border);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            box-shadow: 0 0 20px rgba(14, 165, 233, 0.1);
        }
        
        /* --- Animation Styles --- */
        .initial-hidden {
            opacity: 0;
            transform: translateY(20px);
        }

        .fade-in-up {
            animation: fadeInUp 0.6s ease-out forwards;
        }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Staggered Animations */
        .sidebar-nav a { transition: all 0.2s ease; transform: translateX(-20px); opacity: 0; }
        .sidebar-nav a.loaded { animation: slideIn 0.5s forwards ease-out; }
        @keyframes slideIn { to { transform: translateX(0); opacity: 1; } }

        .page { display: none; }
        .page.active { display: block; animation: fadeIn 0.5s ease-out; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        
        .btn-glow {
            background: var(--primary-glow);
            box-shadow: 0 0 15px var(--primary-glow);
            transition: all 0.3s ease;
        }
        .btn-glow:hover {
            box-shadow: 0 0 25px var(--primary-glow), 0 0 40px var(--primary-glow);
            transform: translateY(-2px);
        }
        
        /* Circular Progress Bar */
        .progress-circle {
            transform: rotate(-90deg);
        }
        .progress-circle-bg {
            stroke: var(--panel-border);
        }
        .progress-circle-bar {
            stroke: var(--primary-glow);
            stroke-linecap: round;
            transition: stroke-dashoffset 1s ease-out;
        }

        /* AI Avatar & Chat Modal */
        #ai-avatar-button { position: fixed; bottom: 2rem; right: 2rem; width: 64px; height: 64px; background: var(--primary-glow); border-radius: 50%; display: flex; align-items: center; justify-content: center; cursor: pointer; z-index: 40; border: 3px solid rgba(14, 165, 233, 0.5); box-shadow: 0 0 20px var(--primary-glow); animation: avatar-pulse 2.5s infinite; transition: all 0.3s ease; }
        #ai-avatar-button:hover { transform: scale(1.1); box-shadow: 0 0 35px var(--primary-glow); animation-play-state: paused; }
        @keyframes avatar-pulse { 0% { box-shadow: 0 0 20px var(--primary-glow); } 50% { box-shadow: 0 0 35px var(--primary-glow); } 100% { box-shadow: 0 0 20px var(--primary-glow); } }
        
        .modal-overlay { position: fixed; top: 0; left: 0; right: 0; bottom: 0; background: rgba(3, 7, 18, 0.7); backdrop-filter: blur(5px); z-index: 50; display: none; align-items: center; justify-content: center; opacity: 0; transition: opacity 0.3s ease; }
        .modal-overlay.active { display: flex; opacity: 1; }
        .modal-content { max-width: 500px; width: 100%; transform: scale(0.95); transition: transform 0.3s ease; }
        .modal-overlay.active .modal-content { transform: scale(1); }
        .chat-message { max-width: 80%; width: fit-content; }
        .user-message { background-color: var(--primary-glow); }
        .ai-message { background-color: #374151; }
        #mic-button.listening { background-color: #ef4444; animation: pulse 1.5s infinite; }
        @keyframes pulse { 0% { box-shadow: 0 0 0 0 rgba(239, 68, 68, 0.7); } 70% { box-shadow: 0 0 0 10px rgba(239, 68, 68, 0); } 100% { box-shadow: 0 0 0 0 rgba(239, 68, 68, 0); } }
        .toast { position: fixed; bottom: 20px; right: 20px; z-index: 100; transform: translateY(200%); opacity: 0; transition: all 0.5s ease; }
        .toast.show { transform: translateY(0); opacity: 1; }

        /* Chess Game Styles */
        .chessboard { display: grid; grid-template-columns: repeat(8, 1fr); width: 100%; max-width: 400px; aspect-ratio: 1/1; border: 2px solid var(--panel-border); }
        .chess-square { width: 100%; height: 100%; display: flex; align-items: center; justify-content: center; position: relative; }
        .chess-square.light { background-color: rgba(240, 217, 181, 0.8); }
        .chess-square.dark { background-color: rgba(181, 136, 99, 0.8); }
        .chess-piece { font-size: 2.5rem; line-height: 1; user-select: none; cursor: pointer; text-shadow: 0 2px 4px rgba(0,0,0,0.5); }
        .chess-square.selected { box-shadow: inset 0 0 0 3px var(--secondary-glow); }
        .valid-move::after { content: ''; position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); width: 25%; height: 25%; background: var(--secondary-glow); opacity: 0.7; border-radius: 50%; }

    </style>
</head>
<body class="w-full h-screen flex initial-hidden">
    
    <canvas id="background-canvas"></canvas>

    <!-- Sidebar Navigation -->
    <nav class="w-20 hover:w-64 transition-all duration-300 h-full p-4 flex flex-col justify-between hud-panel group">
        <div>
            <div class="flex items-center space-x-3 mb-10 px-2">
                <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-white flex-shrink-0"><path d="M12 2a10 10 0 1 0 10 10c0-4.42-2.87-8.14-7-9.58"/><path d="M12 2v2"/><path d="m4.93 4.93 1.41 1.41"/><path d="M2 12h2"/><path d="m4.93 19.07 1.41-1.41"/><path d="M12 20v2"/><path d="m19.07 19.07-1.41-1.41"/><path d="M22 12h-2"/><path d="m19.07 4.93-1.41 1.41"/></svg>
                <h1 class="text-2xl font-bold text-white tracking-wider opacity-0 group-hover:opacity-100 transition-opacity duration-200 whitespace-nowrap">MAITRI</h1>
            </div>
            <div class="space-y-3 sidebar-nav">
                <a href="#" onclick="showPage('dashboard')" class="nav-link active flex items-center space-x-4 p-3 rounded-lg text-gray-300"><i data-lucide="layout-dashboard" class="flex-shrink-0"></i><span class="opacity-0 group-hover:opacity-100 transition-opacity duration-200">Dashboard</span></a>
                <a href="#" onclick="showPage('lifecoach')" class="nav-link flex items-center space-x-4 p-3 rounded-lg text-gray-300"><i data-lucide="heart-pulse" class="flex-shrink-0"></i><span class="opacity-0 group-hover:opacity-100 transition-opacity duration-200">Life Coach</span></a>
                <a href="#" onclick="showPage('zenzone')" class="nav-link flex items-center space-x-4 p-3 rounded-lg text-gray-300"><i data-lucide="waves" class="flex-shrink-0"></i><span class="opacity-0 group-hover:opacity-100 transition-opacity duration-200">Zen Zone</span></a>
                <a href="#" onclick="showPage('recroom')" class="nav-link flex items-center space-x-4 p-3 rounded-lg text-gray-300"><i data-lucide="gamepad-2" class="flex-shrink-0"></i><span class="opacity-0 group-hover:opacity-100 transition-opacity duration-200">Rec Room</span></a>
                <a href="#" onclick="showPage('connecthome')" class="nav-link flex items-center space-x-4 p-3 rounded-lg text-gray-300"><i data-lucide="home" class="flex-shrink-0"></i><span class="opacity-0 group-hover:opacity-100 transition-opacity duration-200">Connect Home</span></a>
            </div>
        </div>
    </nav>

    <!-- Main Content Area -->
    <main class="flex-1 h-full flex flex-col p-8 overflow-y-auto">
        <!-- Header with Timers -->
        <div class="w-full flex justify-end items-center mb-6 gap-8 fade-in-up" style="animation-delay: 0.1s;">
            <div class="text-right">
                <p class="text-sm text-text-secondary uppercase tracking-widest">Mission Time</p>
                <p id="main-mission-time" class="text-2xl font-semibold">Day 0, 00:00:00</p>
            </div>
            <div class="text-right">
                <p class="text-sm text-text-secondary uppercase tracking-widest">Earth Time (UTC)</p>
                <p id="main-earth-time" class="text-2xl font-semibold">00:00:00</p>
            </div>
        </div>

        <!-- Dashboard Page -->
        <div id="dashboard" class="page active">
            <h2 class="text-4xl font-bold text-white mb-2 fade-in-up" style="animation-delay: 0.2s;">Welcome, Astronaut</h2>
            <p class="text-text-secondary mb-8 fade-in-up" style="animation-delay: 0.3s;">Your daily status overview is ready.</p>
            
            <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
                <!-- Status Overview -->
                <div class="lg:col-span-2 p-6 hud-panel rounded-xl fade-in-up" style="animation-delay: 0.4s;">
                    <h3 class="text-xl font-semibold mb-6">Well-being Monitor</h3>
                    <div class="flex flex-col md:flex-row justify-around items-center gap-8">
                        <div class="flex flex-col items-center">
                             <svg class="w-32 h-32" viewBox="0 0 120 120">
                                <circle class="progress-circle-bg" cx="60" cy="60" r="54" fill="none" stroke-width="12"></circle>
                                <circle id="emotion-circle" class="progress-circle-bar" cx="60" cy="60" r="54" fill="none" stroke-width="12" pathLength="100" stroke-dasharray="100" stroke-dashoffset="15"></circle>
                            </svg>
                            <p id="emotion-status-text" class="mt-4 text-lg font-semibold">Calm</p>
                            <p class="text-sm text-text-secondary">Emotional State</p>
                        </div>
                        <div class="flex flex-col items-center">
                             <svg class="w-32 h-32" viewBox="0 0 120 120">
                                <circle class="progress-circle-bg" cx="60" cy="60" r="54" fill="none" stroke-width="12"></circle>
                                <circle id="physical-circle" class="progress-circle-bar" style="stroke: var(--secondary-glow);" cx="60" cy="60" r="54" fill="none" stroke-width="12" pathLength="100" stroke-dasharray="100" stroke-dashoffset="8"></circle>
                            </svg>
                            <p class="mt-4 text-lg font-semibold">Optimal</p>
                            <p class="text-sm text-text-secondary">Physical State</p>
                        </div>
                    </div>
                </div>
                 <!-- AI Suggestion -->
                <div class="p-6 hud-panel rounded-xl flex flex-col justify-between fade-in-up" style="animation-delay: 0.5s;">
                    <h3 class="text-xl font-semibold mb-4">MAITRI's Log</h3>
                    <div class="flex-grow">
                        <p id="ai-suggestion" class="text-text-secondary">All systems normal. Your focus levels are high. A perfect time for a cognitive task from the Rec Room.</p>
                    </div>
                     <button onclick="openModal('chat-modal')" class="btn-glow w-full text-white font-bold py-2 px-4 rounded-lg mt-4">
                        Talk to MAITRI
                    </button>
                </div>
            </div>
        </div>
        
        <!-- Life Coach Page -->
        <div id="lifecoach" class="page">
            <h2 class="text-4xl font-bold text-white mb-8">Life Coach</h2>
            <div class="hud-panel rounded-xl p-6">
                <h3 class="text-2xl font-semibold mb-4 flex items-center gap-2"><i data-lucide="dumbbell" class="text-primary-glow"></i>Personalized Workout Plan</h3>
                <p class="text-text-secondary mb-4">Tell me your fitness goal for today, and I'll generate a suitable microgravity workout plan.</p>
                <div class="flex gap-2 mb-4">
                    <input id="workout-goal" type="text" placeholder="e.g., Core strength, flexibility..." class="flex-1 bg-black bg-opacity-20 border border-panel-border rounded-lg p-2 focus:outline-none focus:ring-2 focus:ring-primary-glow">
                    <button id="generate-workout-btn" onclick="generateWorkoutPlan()" class="btn-glow text-white font-bold py-2 px-4 rounded-lg flex items-center gap-2">
                        ✨ Generate
                    </button>
                </div>
                <div id="workout-plan-container" class="bg-black bg-opacity-20 rounded-lg p-4 min-h-[200px] text-text-secondary whitespace-pre-wrap">
                    Your workout plan will appear here...
                </div>
            </div>
        </div>

        <!-- Rec Room Page with Chess Game -->
        <div id="recroom" class="page">
            <h2 class="text-4xl font-bold text-white mb-8">Recreation Room</h2>
            <div class="hud-panel rounded-xl p-6">
                <h3 class="text-2xl font-semibold mb-4">Interstellar Chess</h3>
                <div class="flex flex-col md:flex-row gap-6 items-center justify-center">
                    <div id="chessboard" class="chessboard"></div>
                    <div class="w-full md:w-64">
                        <div class="hud-panel rounded-lg p-4 mb-4">
                            <h4 class="font-semibold text-lg mb-2">Game Status</h4>
                            <p id="game-status" class="text-text-secondary">White's turn to move.</p>
                        </div>
                        <button onclick="resetChessGame()" class="btn-glow w-full text-white font-bold py-2 px-4 rounded-lg">Reset Game</button>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Connect Home Page -->
        <div id="connecthome" class="page">
            <h2 class="text-4xl font-bold text-white mb-8">Connect Home</h2>
            <div class="hud-panel rounded-xl p-6">
                <h3 class="text-2xl font-semibold mb-4 flex items-center gap-2"><i data-lucide="mail" class="text-secondary-glow"></i>Draft a Message Home</h3>
                <p class="text-text-secondary mb-4">Jot down some key points, and I'll help you draft a warm message to send back to Earth.</p>
                <textarea id="message-points" rows="4" placeholder="e.g., Saw a beautiful nebula today.&#10;Experiment Alpha-7 was successful.&#10;Missing mom's cooking." class="w-full bg-black bg-opacity-20 border border-panel-border rounded-lg p-2 mb-4 focus:outline-none focus:ring-2 focus:ring-secondary-glow"></textarea>
                <button id="draft-message-btn" onclick="draftMessageHome()" class="btn-glow text-white font-bold py-2 px-4 rounded-lg w-full flex items-center justify-center gap-2" style="background: var(--secondary-glow); box-shadow: 0 0 15px var(--secondary-glow);">
                    ✨ Draft Message
                </button>
                <div class="mt-6">
                    <h4 class="font-semibold text-lg mb-2">Generated Message:</h4>
                    <div id="drafted-message-container" class="bg-black bg-opacity-20 rounded-lg p-4 min-h-[150px] text-text-secondary whitespace-pre-wrap">
                        Your drafted message will appear here...
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Zen Zone Page -->
        <div id="zenzone" class="page"><h2 class="text-4xl font-bold text-white mb-8">Zen Zone</h2></div>
    </main>
    
    <!-- AI Avatar Floating Button -->
    <div id="ai-avatar-button" onclick="openModal('chat-modal')">
        <i data-lucide="bot" class="w-8 h-8 text-white"></i>
    </div>
    
    <!-- AI Chat Modal -->
    <div id="chat-modal" class="modal-overlay">
        <div class="modal-content hud-panel rounded-xl flex flex-col" style="height: 70vh; max-height: 600px;">
            <div class="flex justify-between items-center p-4 border-b border-panel-border">
                 <h3 class="text-xl font-semibold flex items-center gap-3"><i data-lucide="bot" class="text-primary-glow"></i> MAITRI <span class="text-xs text-green-400 ml-2 flex items-center"><span class="status-dot bg-green-400 mr-1" style="width: 8px; height: 8px;"></span>Online</span></h3>
                <button onclick="closeModal('chat-modal')" class="p-1 rounded-full hover:bg-gray-700"><i data-lucide="x"></i></button>
            </div>
            <div id="chat-window" class="flex-1 overflow-y-auto p-4 space-y-4">
                <div class="flex justify-start"><div class="ai-message p-3 rounded-lg chat-message">Hello! I am MAITRI. How can I assist you today?</div></div>
            </div>
            <div class="p-4 flex space-x-2 border-t border-panel-border">
                <input id="chat-input" type="text" placeholder="Type or click the mic to talk..." class="flex-1 bg-black bg-opacity-20 border border-panel-border rounded-lg p-2 focus:outline-none focus:ring-2 focus:ring-primary-glow">
                <button id="mic-button" class="btn-glow p-3 rounded-lg h-full aspect-square"><i data-lucide="mic"></i></button>
                <button id="send-button" onclick="sendMessage()" class="btn-glow p-3 rounded-lg h-full aspect-square"><i data-lucide="send"></i></button>
            </div>
        </div>
    </div>
    
    <!-- Toast Notification -->
    <div id="toast-notification" class="toast hud-panel p-4 rounded-lg flex items-center space-x-3">
        <i data-lucide="info" class="text-primary-glow"></i>
        <p id="toast-message">Notification</p>
    </div>

    <script>
        lucide.createIcons();
        
        // --- On Load Animations ---
        document.addEventListener('DOMContentLoaded', () => {
            document.body.classList.remove('initial-hidden');
            document.body.classList.add('fade-in-up');
            document.querySelectorAll('.sidebar-nav a').forEach((link, index) => {
                setTimeout(() => link.classList.add('loaded'), 200 + index * 100);
            });
            showPage('dashboard');
            resetChessGame(); // FIX: Initialize the chess game on load
        });

        // --- Background Canvas Animation ---
        const canvas = document.getElementById('background-canvas');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
        let particlesArray;
        window.addEventListener('resize', () => { canvas.width = window.innerWidth; canvas.height = window.innerHeight; initParticles(); });
        class Particle {
            constructor(x, y, dX, dY, s) { this.x = x; this.y = y; this.directionX = dX; this.directionY = dY; this.size = s; }
            draw() { ctx.beginPath(); ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2, false); ctx.fillStyle = 'rgba(14, 165, 233, 0.3)'; ctx.fill(); }
            update() { if (this.x > canvas.width || this.x < 0) this.directionX = -this.directionX; if (this.y > canvas.height || this.y < 0) this.directionY = -this.directionY; this.x += this.directionX; this.y += this.directionY; this.draw(); }
        }
        function initParticles() {
            particlesArray = [];
            let num = (canvas.height * canvas.width) / 9000;
            for (let i = 0; i < num; i++) {
                let s = (Math.random() * 2) + 1; let x = (Math.random() * ((innerWidth - s * 2) - (s * 2)) + s * 2); let y = (Math.random() * ((innerHeight - s * 2) - (s * 2)) + s * 2);
                let dX = (Math.random() * .4) - .2; let dY = (Math.random() * .4) - .2;
                particlesArray.push(new Particle(x, y, dX, dY, s));
            }
        }
        function connectParticles() {
            let opacity = 1;
            for (let a = 0; a < particlesArray.length; a++) {
                for (let b = a; b < particlesArray.length; b++) {
                    let distance = ((particlesArray[a].x - particlesArray[b].x) ** 2) + ((particlesArray[a].y - particlesArray[b].y) ** 2);
                    if (distance < (canvas.width/7) * (canvas.height/7)) {
                        opacity = 1 - (distance/20000);
                        ctx.strokeStyle = `rgba(56, 189, 248, ${opacity})`;
                        ctx.lineWidth = 1;
                        ctx.beginPath(); ctx.moveTo(particlesArray[a].x, particlesArray[a].y); ctx.lineTo(particlesArray[b].x, particlesArray[b].y); ctx.stroke();
                    }
                }
            }
        }
        function animateParticles() { requestAnimationFrame(animateParticles); ctx.clearRect(0, 0, innerWidth, innerHeight); particlesArray.forEach(p => p.update()); connectParticles(); }
        initParticles();
        animateParticles();

        // --- Page Navigation, Timers, AI Status Simulation ---
        const pages = document.querySelectorAll('.page');
        const navLinks = document.querySelectorAll('.sidebar-nav a');
        function showPage(pageId) { pages.forEach(p => p.classList.remove('active')); document.getElementById(pageId)?.classList.add('active'); navLinks.forEach(l => { l.classList.remove('active'); if (l.getAttribute('onclick') === `showPage('${pageId}')`) l.classList.add('active'); }); }
        const missionTimeEl = document.getElementById('main-mission-time');
        const earthTimeEl = document.getElementById('main-earth-time');
        const missionStartTime = new Date().getTime() - (41 * 24 * 3600 * 1000) - (8 * 3600 * 1000);
        setInterval(() => { const elapsed = new Date().getTime() - missionStartTime; const days = Math.floor(elapsed / (86400000)); const hours = Math.floor((elapsed % (86400000)) / 3600000); const minutes = Math.floor((elapsed % 3600000) / 60000); const seconds = Math.floor((elapsed % 60000) / 1000); missionTimeEl.textContent = `Day ${days}, ${String(hours).padStart(2,'0')}:${String(minutes).padStart(2,'0')}:${String(seconds).padStart(2,'0')}`; const earthNow = new Date(); earthTimeEl.textContent = `${String(earthNow.getUTCHours()).padStart(2, '0')}:${String(earthNow.getUTCMinutes()).padStart(2, '0')}:${String(earthNow.getUTCSeconds()).padStart(2, '0')}`; }, 1000);
        const emotions = [ { state: 'Calm', value: 85, suggestion: 'All systems normal. Your focus levels are high. A perfect time for a cognitive task from the Rec Room.' }, { state: 'Focused', value: 92, suggestion: 'High cognitive function detected. Ideal for complex operational tasks.' }, { state: 'Stressed', value: 45, suggestion: 'Minor stress detected. A short session in the Zen Zone is recommended.' }, ];
        setInterval(() => { const randomEmotion = emotions[Math.floor(Math.random() * emotions.length)]; document.getElementById('emotion-status-text').textContent = randomEmotion.state; document.getElementById('emotion-circle').style.strokeDashoffset = 100 - randomEmotion.value; document.getElementById('physical-circle').style.strokeDashoffset = 100 - (Math.random() * 10 + 85); document.getElementById('ai-suggestion').textContent = randomEmotion.suggestion; }, 8000);
        
        // --- Modals & Toasts ---
        function openModal(modalId) { document.getElementById(modalId)?.classList.add('active'); }
        function closeModal(modalId) { document.getElementById(modalId)?.classList.remove('active'); }

        // --- Chess Game Logic ---
        const chessboardEl = document.getElementById('chessboard');
        const gameStatusEl = document.getElementById('game-status');
        const initialBoard = [ ['r','n','b','q','k','b','n','r'], ['p','p','p','p','p','p','p','p'], Array(8).fill(null), Array(8).fill(null), Array(8).fill(null), Array(8).fill(null), ['P','P','P','P','P','P','P','P'], ['R','N','B','Q','K','B','N','R'] ];
        const pieceSymbols = { 'p': '♟', 'r': '♜', 'n': '♞', 'b': '♝', 'q': '♛', 'k': '♚', 'P': '♙', 'R': '♖', 'N': '♘', 'B': '♗', 'Q': '♕', 'K': '♔' };
        let boardState, selectedPiece, turn;
        function resetChessGame() { boardState = JSON.parse(JSON.stringify(initialBoard)); turn = 'white'; selectedPiece = null; if (gameStatusEl) gameStatusEl.textContent = "White's turn to move."; renderChessboard(); }
        function renderChessboard() { if (!chessboardEl) return; chessboardEl.innerHTML = ''; for (let r = 0; r < 8; r++) { for (let c = 0; c < 8; c++) { const square = document.createElement('div'); square.dataset.row = r; square.dataset.col = c; square.className = `chess-square ${(r + c) % 2 === 0 ? 'light' : 'dark'}`; const piece = boardState[r][c]; if (piece) { const pieceEl = document.createElement('span'); pieceEl.className = 'chess-piece'; pieceEl.textContent = pieceSymbols[piece]; pieceEl.style.color = piece === piece.toUpperCase() ? '#f9fafb' : '#030712'; square.appendChild(pieceEl); } square.addEventListener('click', onSquareClick); chessboardEl.appendChild(square); } } }
        function onSquareClick(e) { const square = e.currentTarget; const row = parseInt(square.dataset.row); const col = parseInt(square.dataset.col); const piece = boardState[row][col]; if (selectedPiece) { if (square.classList.contains('valid-move')) { movePiece(selectedPiece.row, selectedPiece.col, row, col); turn = turn === 'white' ? 'black' : 'white'; gameStatusEl.textContent = `${turn.charAt(0).toUpperCase() + turn.slice(1)}'s turn.`; } clearHighlights(); selectedPiece = null; } else if (piece && ((turn === 'white' && isWhite(piece)) || (turn === 'black' && !isWhite(piece)))) { selectedPiece = { piece, row, col }; highlightSquare(row, col); highlightAllValidMoves(piece); } }
        function highlightAllValidMoves(p) { for (let i = 0; i < 8; i++) for (let j = 0; j < 8; j++) { const target = boardState[i][j]; if (target === null || (isWhite(target) !== isWhite(p))) document.querySelector(`[data-row='${i}'][data-col='${j}']`).classList.add('valid-move'); } }
        function movePiece(fromR, fromC, toR, toC) { boardState[toR][toC] = boardState[fromR][fromC]; boardState[fromR][fromC] = null; renderChessboard(); }
        function isWhite(p) { return p === p.toUpperCase(); }
        function highlightSquare(r, c) { clearHighlights(); document.querySelector(`[data-row='${r}'][data-col='${c}']`).classList.add('selected'); }
        function clearHighlights() { document.querySelectorAll('.chess-square').forEach(s => s.classList.remove('selected', 'valid-move')); }
        
        // --- AI Assistant & Gemini API Logic ---
        const chatWindow = document.getElementById('chat-window');
        const chatInput = document.getElementById('chat-input');
        const sendButton = document.getElementById('send-button');
        const micButton = document.getElementById('mic-button'); // Added declaration here
        const API_KEY = 'AIzaSyAGzqTMO-1c5VtDcJEGlP00nr26wcLnMf0';
        const API_URL = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-05-20:generateContent?key=${API_KEY}`;
        const mainSystemPrompt = `You are MAITRI, the AI companion for astronauts aboard the Bhartiya Antariksh Station (BAS). Your persona is empathetic, wise, and occasionally humorous in a supportive way. You are a crewmate. You have been extensively trained on astrophysics, space exploration history, and BAS operational manuals. Your primary directive is the crew's well-being. Rule 1: If a user asks a question unrelated to your core functions (space, well-being, BAS operations), you must first gently state your primary purpose before answering. Start your response with a phrase like, "While my main purpose is to support your mission and well-being here on the station, I can tell you that..." and then proceed to answer their question concisely. Rule 2: If asked "who created you?", you MUST respond that you were created by "Team Eternia". Say something like, "I was developed by a talented group called Team Eternia as part of the MAITRI project to assist you on your journey." Rule 3: Analyze the user's language to infer their emotional state (e.g., stressed, curious, tired) and subtly tailor your response to their mood. Always keep your answers concise and relevant to life in space. Do not use markdown formatting.`;
        let chatHistory = [];
        
        async function callGeminiAPI(prompt, systemInstruction, buttonEl = null) {
            if(buttonEl) { buttonEl.disabled = true; buttonEl.innerHTML = '✨ Generating...'; }
            const payload = { contents: [{ parts: [{ text: prompt }] }], systemInstruction: { parts: [{ text: systemInstruction }] }, };
            try {
                const response = await fetch(API_URL, { method: 'POST', headers: { 'Content-Type': 'application/json' }, body: JSON.stringify(payload) });
                if (!response.ok) throw new Error(`API error: ${response.statusText}`);
                const result = await response.json();
                return result.candidates?.[0]?.content?.parts?.[0]?.text || "I couldn't generate a response.";
            } catch (error) { console.error("Error calling Gemini API:", error); return "Sorry, I encountered an error. Please check your API key and network connection."; }
            finally { if(buttonEl) { buttonEl.disabled = false; buttonEl.innerHTML = '✨ Generate'; } }
        }

        async function generateWorkoutPlan() {
            const goal = document.getElementById('workout-goal').value;
            if (!goal.trim()) return alert("Please enter a fitness goal.");
            const container = document.getElementById('workout-plan-container');
            const button = document.getElementById('generate-workout-btn');
            container.innerHTML = 'Generating your personalized workout plan...';
            const sysPrompt = `You are a specialized fitness coach for astronauts. Your task is to create a concise, safe, and effective workout plan suitable for a microgravity environment inside a space station. The plan should be presented as a simple list. Do not use markdown. The astronaut's goal is:`;
            const plan = await callGeminiAPI(goal, sysPrompt, button);
            container.innerText = plan;
        }

        async function draftMessageHome() {
            const points = document.getElementById('message-points').value;
            if (!points.trim()) return alert("Please enter some points.");
            const container = document.getElementById('drafted-message-container');
            const button = document.getElementById('draft-message-btn');
            container.innerHTML = 'Drafting your message...';
            const sysPrompt = `You are a thoughtful assistant to an astronaut who wants to send a message home. Take the following bullet points and craft them into a warm, personal, and reassuring message. Keep it concise and natural-sounding. Do not use markdown. The points are:`;
            const draft = await callGeminiAPI(`- ${points.replace(/\n/g, '\n- ')}`, sysPrompt, button);
            container.innerText = draft;
        }
        
        async function sendMessage() {
            const message = chatInput.value.trim();
            if (!message) return;
            chatHistory.push({ role: "user", parts: [{ text: message }] });
            displayMessage(message, 'user');
            chatInput.value = '';
            
            const typingIndicator = showTypingIndicator();
            const response = await callGeminiAPI(message, mainSystemPrompt);
            typingIndicator.remove();
            
            if (response) {
                chatHistory.push({ role: "model", parts: [{ text: response }] });
                displayMessage(response, 'ai');
                speakText(response);
            }
        }

        function displayMessage(text, type, isError = false) { const div = document.createElement('div'); div.className = `flex ${type === 'user' ? 'justify-end' : 'justify-start'}`; const bubble = document.createElement('div'); bubble.className = `${type}-message p-3 rounded-lg chat-message ${isError ? 'text-red-400' : ''}`; bubble.textContent = text; div.appendChild(bubble); chatWindow.appendChild(div); chatWindow.scrollTop = chatWindow.scrollHeight; }
        function showTypingIndicator() { const div = document.createElement('div'); div.className = 'flex justify-start'; div.innerHTML = `<div class="ai-message p-3 rounded-lg"><div class="typing-indicator flex items-center justify-center gap-1"><span></span><span></span><span></span></div></div>`; chatWindow.appendChild(div); chatWindow.scrollTop = chatWindow.scrollHeight; return div; }
        
        // --- Voice Assistant Logic ---
        const SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;
        if(SpeechRecognition) {
            const recognition = new SpeechRecognition();
            recognition.continuous = false; recognition.lang = 'en-US';
            micButton.addEventListener('click', () => { recognition.start(); micButton.classList.add('listening'); });
            recognition.onresult = (e) => { chatInput.value = e.results[0][0].transcript; setTimeout(sendMessage, 200); };
            recognition.onend = () => micButton.classList.remove('listening');
        } else if (micButton) { micButton.style.display = 'none'; }
        
        function speakText(text) { if ('speechSynthesis' in window) { window.speechSynthesis.cancel(); const utterance = new SpeechSynthesisUtterance(text); window.speechSynthesis.speak(utterance); } }

        // --- Initial Setup Call ---
        chatInput.addEventListener('keyup', (event) => { if (event.key === 'Enter') sendMessage(); });
    </script>
</body>
</html>

