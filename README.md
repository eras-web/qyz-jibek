<!DOCTYPE html>
<html lang="kk">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Қыз Жібек - Қазақ Эпосы Пазлы</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1a2a6c, #b21f1f, #1a2a6c);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
            color: #fff;
            overflow-x: hidden;
        }
        
        .header {
            text-align: center;
            padding: 20px;
            margin-bottom: 20px;
            width: 100%;
            max-width: 1000px;
            background: rgba(0, 0, 0, 0.4);
            border-radius: 20px;
            border: 2px solid rgba(255, 215, 0, 0.5);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.5);
        }
        
        h1 {
            font-size: 3.2rem;
            margin-bottom: 10px;
            text-shadow: 0 2px 10px rgba(0, 0, 0, 0.7);
            color: #ffd700;
            font-weight: bold;
            letter-spacing: 2px;
        }
        
        .subtitle {
            font-size: 1.4rem;
            max-width: 800px;
            margin: 0 auto 15px;
            line-height: 1.6;
            color: #f0f0f0;
        }
        
        .container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
            width: 100%;
            max-width: 1400px;
            margin-bottom: 30px;
        }
        
        .puzzle-section {
            background: rgba(25, 25, 35, 0.8);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 25px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
            width: 100%;
            max-width: 800px;
            border: 2px solid rgba(255, 215, 0, 0.3);
        }
        
        .puzzle-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 2px solid rgba(255, 215, 0, 0.3);
        }
        
        .puzzle-title {
            font-size: 2rem;
            font-weight: bold;
            color: #ffd700;
        }
        
        .controls {
            display: flex;
            gap: 15px;
            margin-bottom: 20px;
            flex-wrap: wrap;
            justify-content: center;
        }
        
        button {
            background: linear-gradient(to right, #8e2de2, #4a00e0);
            border: none;
            border-radius: 50px;
            color: white;
            padding: 14px 28px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 2px solid rgba(255, 215, 0, 0.5);
            font-weight: bold;
            letter-spacing: 1px;
            min-width: 180px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        button:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4);
            background: linear-gradient(to right, #9d4edd, #5a1fe0);
        }
        
        button:active {
            transform: translateY(0);
        }
        
        .puzzle-container {
            display: grid;
            grid-template-columns: repeat(7, 1fr);
            gap: 4px;
            background: rgba(0, 0, 0, 0.4);
            padding: 15px;
            border-radius: 15px;
            min-height: 500px;
            border: 1px solid rgba(255, 215, 0, 0.2);
        }
        
        .puzzle-piece {
            background-size: 700% 400%;
            border: 2px solid rgba(255, 255, 255, 0.3);
            border-radius: 10px;
            cursor: grab;
            transition: all 0.3s ease;
            aspect-ratio: 1/1;
            position: relative;
            overflow: hidden;
            box-shadow: inset 0 0 15px rgba(0, 0, 0, 0.3);
            background-color: #2c2c3a;
        }
        
        .puzzle-piece:hover {
            transform: scale(1.08);
            z-index: 10;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.5);
            border-color: rgba(255, 215, 0, 0.7);
        }
        
        .puzzle-piece.correct {
            border: 3px solid #4ade80;
            box-shadow: 0 0 20px rgba(74, 222, 128, 0.6);
            animation: pulse 1.5s infinite;
        }
        
        @keyframes pulse {
            0% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.03);
            }
            100% {
                transform: scale(1);
            }
        }
        
        .info-section {
            background: rgba(25, 25, 35, 0.8);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 25px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
            max-width: 500px;
            border: 2px solid rgba(255, 215, 0, 0.3);
        }
        
        .info-title {
            font-size: 2rem;
            margin-bottom: 20px;
            text-align: center;
            font-weight: bold;
            color: #ffd700;
            text-shadow: 0 2px 5px rgba(0, 0, 0, 0.5);
        }
        
        .info-content {
            line-height: 1.8;
            font-size: 1.15rem;
        }
        
        .info-content p {
            margin-bottom: 20px;
            text-align: justify;
        }
        
        .highlight {
            color: #ffd700;
            font-weight: bold;
            text-shadow: 0 1px 3px rgba(0, 0, 0, 0.5);
        }
        
        .progress-container {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-top: 20px;
            background: rgba(0, 0, 0, 0.4);
            padding: 15px;
            border-radius: 15px;
            border: 1px solid rgba(255, 215, 0, 0.2);
        }
        
        .progress-bar {
            flex-grow: 1;
            height: 25px;
            background: rgba(0, 0, 0, 0.5);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.3);
        }
        
        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #00c9ff, #92fe9d);
            border-radius: 12px;
            width: 0%;
            transition: width 0.5s ease;
            box-shadow: 0 0 15px rgba(0, 201, 255, 0.5);
        }
        
        .timer {
            font-size: 1.3rem;
            font-weight: bold;
            min-width: 100px;
            text-align: center;
            background: rgba(0, 0, 0, 0.5);
            padding: 8px 15px;
            border-radius: 50px;
            border: 1px solid rgba(255, 215, 0, 0.3);
        }
        
        .completed-message {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) scale(0);
            background: linear-gradient(135deg, #1a2a6c, #b21f1f);
            padding: 50px;
            border-radius: 25px;
            text-align: center;
            z-index: 100;
            border: 4px solid #ffd700;
            box-shadow: 0 0 50px rgba(255, 215, 0, 0.8);
            transition: all 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            max-width: 90%;
            width: 600px;
        }
        
        .completed-message.show {
            transform: translate(-50%, -50%) scale(1);
        }
        
        .completed-message h2 {
            font-size: 3.5rem;
            color: #ffd700;
            margin-bottom: 25px;
            text-shadow: 0 3px 10px rgba(0, 0, 0, 0.7);
        }
        
        .completed-message p {
            font-size: 1.8rem;
            margin-bottom: 35px;
            color: #fff;
        }
        
        .piece-counter {
            font-size: 1.3rem;
            font-weight: bold;
            background: rgba(0, 0, 0, 0.5);
            padding: 12px 25px;
            border-radius: 50px;
            border: 1px solid rgba(255, 215, 0, 0.3);
        }
        
        .mobile-warning {
            display: none;
            background: rgba(255, 50, 50, 0.3);
            padding: 15px;
            border-radius: 10px;
            margin-top: 20px;
            text-align: center;
            border: 1px solid rgba(255, 0, 0, 0.5);
            font-size: 1.1rem;
        }
        
        .kazakh-pattern {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            background-image: radial-gradient(circle at 10% 20%, rgba(255, 215, 0, 0.05) 0%, transparent 20%), radial-gradient(circle at 90% 80%, rgba(255, 215, 0, 0.05) 0%, transparent 20%);
            pointer-events: none;
            z-index: -1;
        }
        
        .footer {
            margin-top: auto;
            padding: 15px;
            text-align: center;
            color: rgba(255, 255, 255, 0.7);
            font-size: 1.1rem;
        }
        
        .how-to {
            background: rgba(25, 25, 35, 0.8);
            border-radius: 20px;
            padding: 25px;
            margin-top: 20px;
            max-width: 1000px;
            border: 2px solid rgba(255, 215, 0, 0.3);
        }
        
        .how-to h2 {
            color: #ffd700;
            text-align: center;
            margin-bottom: 20px;
            font-size: 2rem;
        }
        
        .steps {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
        }
        
        .step {
            background: rgba(0, 0, 0, 0.4);
            border-radius: 15px;
            padding: 20px;
            width: 300px;
            text-align: center;
        }
        
        .step-number {
            background: #ffd700;
            color: #1a2a6c;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 15px;
            font-weight: bold;
            font-size: 1.3rem;
        }
        
        .step-title {
            color: #ffd700;
            margin-bottom: 10px;
            font-size: 1.3rem;
        }
        
        @media (max-width: 1100px) {
            .container {
                flex-direction: column;
                align-items: center;
            }
            .info-section {
                max-width: 800px;
                width: 100%;
            }
        }
        
        @media (max-width: 768px) {
            .puzzle-container {
                grid-template-columns: repeat(4, 1fr);
            }
            h1 {
                font-size: 2.5rem;
            }
            .puzzle-title {
                font-size: 1.7rem;
            }
            .mobile-warning {
                display: block;
            }
            button {
                padding: 12px 20px;
                font-size: 1rem;
                min-width: 160px;
            }
        }
        
        @media (max-width: 480px) {
            .puzzle-container {
                grid-template-columns: repeat(3, 1fr);
            }
            .controls {
                flex-direction: column;
                align-items: center;
            }
            button {
                width: 100%;
            }
            h1 {
                font-size: 2rem;
            }
            .subtitle {
                font-size: 1.1rem;
            }
            .info-title {
                font-size: 1.7rem;
            }
            .completed-message {
                padding: 30px;
                width: 95%;
            }
            .completed-message h2 {
                font-size: 2.5rem;
            }
            .completed-message p {
                font-size: 1.4rem;
            }
        }
    </style>
</head>

<body>
    <div class="kazakh-pattern"></div>

    <div class="header">
        <h1>Қыз Жібек Жыры</h1>
        <p class="subtitle">Қазақ халқының тарихи дастандарының бірі - "Қыз Жібек" жыры бойынша 28 бөліктен тұратын анимациялық пазл</p>
    </div>

    <div class="container">
        <div class="puzzle-section">
            <div class="puzzle-header">
                <div class="puzzle-title">Пазлды жинаңыз</div>
                <div class="piece-counter"><span id="pieces-count">0</span> / 28 бөлік дұрыс орналастырылды</div>
            </div>

            <div class="controls">
                <button id="start-btn">Пазлды бастау</button>
                <button id="shuffle-btn">Бөліктерді араластыру</button>
                <button id="solve-btn">Пазлды шешу</button>
                <button id="reset-btn">Қалпына келтіру</button>
            </div>

            <div class="puzzle-container" id="puzzle-container">
                <!-- Пазл бөліктері осы жерде жасалады -->
            </div>

            <div class="progress-container">
                <div class="progress-bar">
                    <div class="progress-fill" id="progress-fill"></div>
                </div>
                <div class="timer">Уақыт: <span id="timer">00:00</span></div>
            </div>

            <div class="mobile-warning">
                Назар аударыңыз: Пазлды жинау үшін компьютерде немесе планшетте қолдану ұсынылады
            </div>
        </div>

        <div class="info-section">
            <h2 class="info-title">"Қыз Жібек" Жыры Туралы</h2>
            <div class="info-content">
                <p><span class="highlight">"Қыз Жібек"</span> - қазақ халқының ең көне лиро-эпикалық дастаны. Жырдың негізгі тақырыбы - Төлеген мен Жібектің махаббаты.</p>

                <p>Дастан бірнеше ғасырлар бойы ауызша тараған. Шамамен XVIІ ғасырда қазақ даласының батыс өңірінде, яғни Кіші жүз қазақтары арасында дүниеге келген жырдың нұсқалары арасында айырмашылық аз, яғни болса, кейбір сюжеттік қосындылар мен суреттеу,
                    баяндаулардағы қысқа немесе кеңінен толғаушылық болса керек.</p>

                <p>Жырды алғаш рет Е.А. Александров 1880 жылы Мұсабай ақыннан жазып алып, ұзын-ырғасын қара сөзбен орысшаға аударған болса, татар мұғалімі Фалиолла Тухватуллин Зайсан өңірінен жазып алып, 1894 жылы Қазан қаласында кітап етіп бастырған.</p>
                    
                <p>Жырда батыр Төлеген мен сұлу Жібектің махаббаты, олардың арасындағы кедергілер, жан-жақты сынақтар бейнеленеді. Жырдың соңында қаһармандар қуанышты бірігеді.</p>

                <p><span class="highlight">Пазл суретінде</span> қазақтың ұлттық киімдерін киген Жібек пен Төлеген.</p>
            </div>
        </div>
    </div>

    <div class="how-to">
        <h2>Пазлды өзіңіз қалай жасайсыз?</h2>
        <div class="steps">
            <div class="step">
                <div class="step-number">1</div>
                <h3 class="step-title">Кодты сақтау</h3>
                <p>Бұл парақтың барлық кодтарын көшіріп, компьютеріңізге .html файл ретінде сақтаңыз</p>
            </div>

            <div class="step">
                <div class="step-number">2</div>
                <h3 class="step-title">Өзгертулер жасау</h3>
                <p>HTML файлын мәтін редакторында ашып, суретті, мәтіндерді өз қалауыңізша өзгертіңіз</p>
            </div>

            <div class="step">
                <div class="step-number">3</div>
                <h3 class="step-title">Желіге шығару</h3>
                <p>Файлды GitHub Pages, Netlify немесе жай браузерден ашып пайдаланыңыз</p>
            </div>
        </div>
    </div>

    <div class="completed-message" id="completed-message">
        <h2>Керемет!</h2>
        <p>Сіз пазлды сәтті жинадыңыз!</p>
        <p>Уақыт: <span id="final-time">00:00</span></p>
        <button id="play-again">Қайта ойнау</button>
    </div>

    <div class="footer">
        Қазақ халқының мәдени мұрасын сақтауға көмектесетін "Қыз Жібек" пазлы
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const puzzleContainer = document.getElementById('puzzle-container');
            const startBtn = document.getElementById('start-btn');
            const shuffleBtn = document.getElementById('shuffle-btn');
            const solveBtn = document.getElementById('solve-btn');
            const resetBtn = document.getElementById('reset-btn');
            const progressFill = document.getElementById('progress-fill');
            const timerDisplay = document.getElementById('timer');
            const piecesCount = document.getElementById('pieces-count');
            const completedMessage = document.getElementById('completed-message');
            const finalTime = document.getElementById('final-time');
            const playAgainBtn = document.getElementById('play-again');

            const PIECES = 28;
            const COLS = 7;
            const ROWS = 4;

            let pieces = [];
            let selectedPiece = null;
            let correctCount = 0;
            let timer = null;
            let seconds = 0;
            let gameStarted = false;

            // Create puzzle pieces
            function createPuzzle() {
                puzzleContainer.innerHTML = '';
                pieces = [];
                correctCount = 0;
                piecesCount.textContent = '0';
                progressFill.style.width = '0%';

                for (let i = 0; i < PIECES; i++) {
                    const piece = document.createElement('div');
                    piece.className = 'puzzle-piece';
                    piece.dataset.index = i;
                    piece.dataset.correctIndex = i;

                    // Set background position for each piece
                    const row = Math.floor(i / COLS);
                    const col = i % COLS;

                    piece.style.backgroundPosition = `${-col * (100/(COLS-1))}% ${-row * (100/(ROWS-1))}%`;

                    // Add event listeners
                    piece.addEventListener('click', () => handlePieceClick(piece));

                    puzzleContainer.appendChild(piece);
                    pieces.push(piece);
                }

                // Set background image
                const allPieces = document.querySelectorAll('.puzzle-piece');
                allPieces.forEach(piece => {
                    piece.style.backgroundImage = "url('ҚЫЗ ЖІБЕК пазл.png')";
                    piece.style.backgroundSize = "700% 400%";
                });
            }

            // Handle piece click
            function handlePieceClick(piece) {
                if (!gameStarted) return;

                if (selectedPiece) {
                    // Swap pieces
                    const tempIndex = selectedPiece.dataset.index;
                    const tempCorrectIndex = selectedPiece.dataset.correctIndex;

                    selectedPiece.dataset.index = piece.dataset.index;
                    selectedPiece.dataset.correctIndex = piece.dataset.correctIndex;

                    piece.dataset.index = tempIndex;
                    piece.dataset.correctIndex = tempCorrectIndex;

                    // Swap background positions
                    const selectedPos = selectedPiece.style.backgroundPosition;
                    const piecePos = piece.style.backgroundPosition;

                    selectedPiece.style.backgroundPosition = piecePos;
                    piece.style.backgroundPosition = selectedPos;

                    selectedPiece.classList.remove('selected');
                    selectedPiece = null;

                    checkPieceCorrectness(selectedPiece);
                    checkPieceCorrectness(piece);
                    checkCompletion();
                } else {
                    // Select a piece
                    selectedPiece = piece;
                    piece.classList.add('selected');

                    // Add animation
                    piece.animate([{
                        transform: 'scale(1)'
                    }, {
                        transform: 'scale(1.1)'
                    }, {
                        transform: 'scale(1)'
                    }], {
                        duration: 300,
                        easing: 'ease-in-out'
                    });
                }
            }

            // Check if piece is in correct position
            function checkPieceCorrectness(piece) {
                if (!piece) return;

                if (piece.dataset.index === piece.dataset.correctIndex) {
                    piece.classList.add('correct');
                    return true;
                } else {
                    piece.classList.remove('correct');
                    return false;
                }
            }

            // Check if puzzle is completed
            function checkCompletion() {
                correctCount = 0;
                pieces.forEach(piece => {
                    if (checkPieceCorrectness(piece)) {
                        correctCount++;
                    }
                });

                piecesCount.textContent = correctCount;
                progressFill.style.width = `${(correctCount / PIECES) * 100}%`;

                if (correctCount === PIECES) {
                    clearInterval(timer);
                    setTimeout(() => {
                        finalTime.textContent = timerDisplay.textContent;
                        completedMessage.classList.add('show');

                        // Add celebration animation
                        puzzleContainer.animate([{
                            transform: 'scale(1)'
                        }, {
                            transform: 'scale(1.05)'
                        }, {
                            transform: 'scale(1)'
                        }], {
                            duration: 1000,
                            easing: 'ease-in-out'
                        });
                    }, 500);
                }
            }

            // Shuffle puzzle
            function shufflePuzzle() {
                if (!gameStarted) return;

                const positions = [...Array(PIECES).keys()];

                // Fisher-Yates shuffle algorithm
                for (let i = positions.length - 1; i > 0; i--) {
                    const j = Math.floor(Math.random() * (i + 1));
                    [positions[i], positions[j]] = [positions[j], positions[i]];
                }

                pieces.forEach((piece, index) => {
                    piece.dataset.index = positions[index];

                    // Update background position based on new index
                    const row = Math.floor(positions[index] / COLS);
                    const col = positions[index] % COLS;
                    piece.style.backgroundPosition = `${-col * (100/(COLS-1))}% ${-row * (100/(ROWS-1))}%`;

                    piece.classList.remove('correct');
                });

                correctCount = 0;
                piecesCount.textContent = '0';
                progressFill.style.width = '0%';
            }

            // Solve puzzle
            function solvePuzzle() {
                pieces.forEach(piece => {
                    piece.dataset.index = piece.dataset.correctIndex;

                    const row = Math.floor(piece.dataset.correctIndex / COLS);
                    const col = piece.dataset.correctIndex % COLS;
                    piece.style.backgroundPosition = `${-col * (100/(COLS-1))}% ${-row * (100/(ROWS-1))}%`;

                    piece.classList.add('correct');

                    // Animate piece to position
                    piece.animate([{
                        transform: 'rotate(0deg) scale(1)'
                    }, {
                        transform: 'rotate(360deg) scale(1.2)'
                    }, {
                        transform: 'rotate(0deg) scale(1)'
                    }], {
                        duration: 800,
                        easing: 'ease-in-out'
                    });
                });

                correctCount = PIECES;
                piecesCount.textContent = PIECES;
                progressFill.style.width = '100%';

                setTimeout(() => {
                    if (correctCount === PIECES) {
                        clearInterval(timer);
                        finalTime.textContent = timerDisplay.textContent;
                        completedMessage.classList.add('show');
                    }
                }, 1000);
            }

            // Start the timer
            function startTimer() {
                seconds = 0;
                timerDisplay.textContent = '00:00';

                if (timer) clearInterval(timer);

                timer = setInterval(() => {
                    seconds++;
                    const mins = Math.floor(seconds / 60).toString().padStart(2, '0');
                    const secs = (seconds % 60).toString().padStart(2, '0');
                    timerDisplay.textContent = `${mins}:${secs}`;
                }, 1000);
            }

            // Start the game
            startBtn.addEventListener('click', () => {
                if (gameStarted) return;

                gameStarted = true;
                startTimer();
                shufflePuzzle();
                startBtn.textContent = 'Ойын басталды';
                startBtn.disabled = true;
            });

            // Shuffle puzzle
            shuffleBtn.addEventListener('click', () => {
                if (gameStarted) shufflePuzzle();
            });

            // Solve puzzle
            solveBtn.addEventListener('click', () => {
                if (gameStarted) solvePuzzle();
            });

            // Reset puzzle
            resetBtn.addEventListener('click', () => {
                gameStarted = false;
                clearInterval(timer);
                timerDisplay.textContent = '00:00';
                createPuzzle();
                startBtn.textContent = 'Пазлды бастау';
                startBtn.disabled = false;
                completedMessage.classList.remove('show');
            });

            // Play again
            playAgainBtn.addEventListener('click', () => {
                completedMessage.classList.remove('show');
                gameStarted = false;
                clearInterval(timer);
                timerDisplay.textContent = '00:00';
                createPuzzle();
                startBtn.textContent = 'Пазлды бастау';
                startBtn.disabled = false;
            });

            // Initialize the puzzle
            createPuzzle();
        });
    </script>
</body>

</html>
