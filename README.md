# khunsamsid-
A Secret romantic website  
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LoveBox — The Secret Between Us 36 🌙👀</title>
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;400;700&display=swap" rel="stylesheet">
    <style>
        /* --- GLOBAL STYLES & VARIABLES --- */
        :root {
            --bg-color: #0d001a;
            --primary-color: #bb86fc; /* Deep purple highlight */
            --secondary-color: #ff8c94; /* Soft pink for text/glow */
            --white: #ffffff;
            --font-elegant: 'Great Vibes', cursive;
            --font-body: 'Poppins', sans-serif;
            --transition-speed: 0.5s;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            cursor: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path fill="%23ff8c94" d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/></svg>'), auto;
        }

        body {
            background-color: var(--bg-color);
            color: var(--white);
            font-family: var(--font-body);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            overflow-x: hidden;
            position: relative;
        }

        /* --- BACKGROUND EFFECTS --- */
        .stars {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
            z-index: -1;
        }

        .star {
            position: absolute;
            color: var(--secondary-color);
            font-size: 1.5rem;
            opacity: 0.7;
            text-shadow: 0 0 5px var(--secondary-color), 0 0 10px var(--primary-color);
            animation: float-sparkle 15s infinite alternate ease-in-out;
        }

        @keyframes float-sparkle {
            0% { transform: translate(0, 0) rotate(0deg); opacity: 0.7; }
            50% { transform: translate(50px, -50px) rotate(180deg); opacity: 0.85; }
            100% { transform: translate(-20px, 30px) rotate(360deg); opacity: 0.7; }
        }

        /* Initial positions for stars */
        .star:nth-child(1) { top: 10%; left: 5%; animation-delay: 0s; font-size: 2rem; }
        .star:nth-child(2) { top: 30%; right: 10%; animation-delay: 2s; font-size: 1.5rem; }
        .star:nth-child(3) { bottom: 20%; left: 15%; animation-delay: 4s; }
        .star:nth-child(4) { bottom: 5%; right: 30%; animation-delay: 6s; font-size: 2.5rem; }
        .star:nth-child(5) { top: 50%; left: 50%; animation-delay: 8s; }
        .star:nth-child(6) { bottom: 40%; right: 5%; animation-delay: 10s; font-size: 1.8rem; }


        /* --- SHARED COMPONENTS --- */
        .container {
            flex-grow: 1;
            max-width: 1000px;
            margin: 0 auto;
            padding: 20px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
        }

        .section {
            min-height: 80vh;
            display: none;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            width: 100%;
            padding: 40px 20px;
            opacity: 0;
            transition: opacity 1s ease-in-out, transform 1s ease-in-out;
        }

        .section.active {
            display: flex;
            opacity: 1;
            transform: translateY(0);
        }

        h1 {
            font-family: var(--font-elegant);
            font-size: clamp(2.5rem, 6vw, 5rem);
            color: var(--secondary-color);
            text-shadow: 0 0 10px var(--secondary-color), 0 0 20px var(--primary-color);
            margin-bottom: 10px;
        }

        h2 {
            font-size: clamp(1.2rem, 3vw, 2rem);
            font-weight: 300;
            margin-bottom: 40px;
            color: var(--white);
        }

        /* Glowing Button Style */
        .glowing-btn {
            background-color: var(--primary-color);
            color: var(--white);
            border: none;
            padding: 15px 30px;
            font-size: 1.2rem;
            font-family: var(--font-body);
            font-weight: 700;
            border-radius: 50px;
            cursor: pointer;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: all 0.3s ease-in-out;
            box-shadow: 0 0 10px var(--primary-color), 0 0 20px var(--primary-color);
            position: relative;
            overflow: hidden;
        }

        .glowing-btn:hover {
            background-color: var(--secondary-color);
            box-shadow: 0 0 15px var(--secondary-color), 0 0 30px var(--secondary-color), 0 0 45px var(--primary-color);
            transform: scale(1.05);
        }

        /* Floating heart animation on hover */
        .glowing-btn:hover::before {
            content: '❤️';
            position: absolute;
            top: -10px;
            right: -10px;
            font-size: 1.5rem;
            animation: heart-float 1s ease-out;
        }

        @keyframes heart-float {
            0% { opacity: 1; transform: translate(0, 0); }
            100% { opacity: 0; transform: translate(15px, -30px); }
        }

        /* --- LANDING PAGE (HOME) --- */
        #home-section .fade-in-message {
            margin-top: 50px;
            font-family: var(--font-elegant);
            font-size: 1.5rem;
            color: var(--secondary-color);
            opacity: 0;
            animation: fadeIn 2s ease-in 2s forwards;
            text-shadow: 0 0 5px var(--secondary-color);
        }

        @keyframes fadeIn {
            to { opacity: 1; }
        }

        /* --- QUIZ SECTION --- */
        #quiz-section {
            padding-top: 50px;
        }

        #quiz-form {
            background: rgba(255, 255, 255, 0.05);
            padding: 30px;
            border-radius: 15px;
            max-width: 600px;
            width: 100%;
            margin-top: 20px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .question-container {
            margin-bottom: 25px;
            text-align: left;
        }

        .question-container h3 {
            font-size: 1.3rem;
            color: var(--secondary-color);
            margin-bottom: 15px;
        }

        .option-card {
            display: block;
            background: rgba(187, 134, 252, 0.1);
            color: var(--white);
            padding: 10px 15px;
            margin-bottom: 10px;
            border-radius: 8px;
            border: 2px solid transparent;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .option-card:hover {
            border-color: var(--primary-color);
            background: rgba(187, 134, 252, 0.2);
        }

        .option-card input[type="radio"] {
            display: none;
        }
        
        .option-card span {
            display: block;
            border-radius: 6px;
            padding: 5px 0;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .option-card input[type="radio"]:checked + span {
            border-color: var(--secondary-color);
            background: rgba(255, 140, 148, 0.3);
            box-shadow: 0 0 8px var(--secondary-color);
        }

        #quiz-submit {
            margin-top: 20px;
        }

        /* --- STAR JAR / SCORING AREA --- */
        #star-jar {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            padding: 15px 25px;
            margin-bottom: 30px;
            border: 2px solid var(--secondary-color);
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: 100%;
            max-width: 600px;
            font-size: 1.2rem;
            text-shadow: 0 0 5px var(--secondary-color);
        }

        #star-count {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-color);
            margin-left: 10px;
        }


        /* --- FINAL SURPRISE PAGE --- */
        #final-section .typing-container {
            max-width: 700px;
            min-height: 250px;
            padding: 30px;
            background: rgba(255, 255, 255, 0.08);
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            margin-bottom: 40px;
            text-align: left;
        }

        #typing-message, #flirty-lines {
            font-family: var(--font-elegant);
            font-size: clamp(1.5rem, 4vw, 2.5rem);
            color: var(--white);
            line-height: 1.5;
            min-height: 150px;
            display: inline-block;
            white-space: pre-wrap;
            overflow: hidden;
        }

        #flirty-lines {
            color: var(--secondary-color);
            text-align: center;
            font-size: clamp(1.2rem, 3vw, 2rem);
            margin-bottom: 30px;
        }

        .flirty-line {
            opacity: 0;
            transition: opacity 1s ease-in;
            display: block;
            margin: 10px 0;
        }

        #reveal-surprise-btn, #bypass-btn {
            display: none;
            margin-top: 20px;
        }

        #surprise-reveal {
            display: none;
            margin-top: 50px;
            font-size: clamp(1.5rem, 4vw, 2.5rem);
            font-family: var(--font-elegant);
            color: var(--secondary-color);
            text-shadow: 0 0 10px var(--secondary-color);
            animation: pulse 1.5s infinite alternate;
            white-space: pre-wrap;
            line-height: 1.5;
            max-width: 700px;
        }

        @keyframes pulse {
            0% { transform: scale(1); opacity: 0.8; }
            100% { transform: scale(1.05); opacity: 1; }
        }

        /* --- MEDIA QUERIES (Responsiveness) --- */
        @media (max-width: 768px) {
            h1 { font-size: 3rem; }
            h2 { font-size: 1.2rem; }
            .glowing-btn { padding: 12px 25px; font-size: 1rem; }
            #quiz-form { padding: 20px; }
            .question-container h3 { font-size: 1.1rem; }
            #final-section .typing-container { padding: 20px; }
            #typing-message { font-size: 1.5rem; }
            #star-jar { font-size: 1rem; padding: 10px 15px; }
            #star-count { font-size: 1.3rem; }
        }
    </style>
</head>
<body>
    <!-- Background Stars/Moons -->
    <div class="stars">
        <div class="star">✨</div>
        <div class="star">🌙</div>
        <div class="star">💖</div>
        <div class="star">✨</div>
        <div class="star">🌙</div>
        <div class="star">💖</div>
    </div>

    <!-- Background Music (Optional Autoplay) -->
    <audio id="bg-music" loop>
        <!-- Add your music source here -->
    </audio>

    <main class="container">
        <!-- 1. LANDING PAGE (Home) -->
        <section id="home-section" class="section active">
            <h1>LoveBox — The Secret Between Us 36 🌙👀</h1>
            <h2>A small piece of us, hidden in this LoveBox.</h2>
            <button class="glowing-btn" onclick="nextSection('quiz-section')">Open the Box 💌</button>
            <p class="fade-in-message">Made with love, by your secret keeper — Siddhu 💞</p>
        </section>

        <!-- 2. FUN & LOVE QUIZ (Interactive Game Section) -->
        <section id="quiz-section" class="section">
            <h1>Unlock Our Secret ✨</h1>
            <h2>Collect 6 Stars to open the LoveBox!</h2>
            
            <div id="star-jar">
                <span>Star Jar:</span>
                <span id="star-count">0 / 6 🌟</span>
            </div>

            <form id="quiz-form">
                <!-- 1. The Classic Feel Question -->
                <div class="question-container">
                    <h3>1. What’s my favorite word for love?</h3>
                    <label class="option-card"><input type="radio" name="q1" value="Care" required><span>Care</span></label>
                    <label class="option-card"><input type="radio" name="q1" value="Peace"><span>Peace</span></label>
                    <label class="option-card"><input type="radio" name="q1" value="Vibe"><span>Vibe</span></label>
                    <label class="option-card"><input type="radio" name="q1" value="You (mine )"><span>You (mine )</span></label>
                </div>

                <!-- 2. Food & Mood Vibe -->
                <div class="question-container">
                    <h3>2. When I’m angry, what helps most (for melt me )?</h3>
                    <label class="option-card"><input type="radio" name="q2" value="Talk softly" required><span>Talk softly</span></label>
                    <label class="option-card"><input type="radio" name="q2" value="to be naughty and cute"><span>to be naughty and cute</span></label>
                    <label class="option-card"><input type="radio" name="q2" value="Say sorry"><span>Say sorry</span></label>
                    <label class="option-card"><input type="radio" name="q2" value="Send food 😂"><span>Send food 😂</span></label>
                </div>
                
                <!-- 3. Dream Travel Together -->
                <div class="question-container">
                    <h3>3. My dream place to go with you?</h3>
                    <label class="option-card"><input type="radio" name="q3" value="Paris" required><span>Paris</span></label>
                    <label class="option-card"><input type="radio" name="q3" value="Dubai"><span>Dubai</span></label>
                    <label class="option-card"><input type="radio" name="q3" value="Sky"><span>Sky</span></label>
                    <label class="option-card"><input type="radio" name="q3" value="Anywhere with You 💕"><span>Anywhere with You 💕</span></label>
                </div>

                <!-- 4. Late Night Mood -->
                <div class="question-container">
                    <h3>4. What do I usually do when I can’t sleep?</h3>
                    <label class="option-card"><input type="radio" name="q4" value="Scroll" required><span>Scroll</span></label>
                    <label class="option-card"><input type="radio" name="q4" value="Eat"><span>Eat</span></label>
                    <label class="option-card"><input type="radio" name="q4" value="Think about you more"><span>Think about you more</span></label>
                    <label class="option-card"><input type="radio" name="q4" value="Watch Reels"><span>Watch Reels</span></label>
                </div>

                <!-- 5. Communication Style -->
                <div class="question-container">
                    <h3>5. When I say “Theek hai”, what does it usually mean?</h3>
                    <label class="option-card"><input type="radio" name="q5" value="I’m fine" required><span>I’m fine</span></label>
                    <label class="option-card"><input type="radio" name="q5" value="I’m done"><span>I’m done</span></label>
                    <label class="option-card"><input type="radio" name="q5" value="I’m ignoring you"><span>I’m ignoring you</span></label>
                    <label class="option-card"><input type="radio" name="q5" value="I still care but won’t say it 😌"><span>I still care but won’t say it 😌</span></label>
                </div>
                
                <!-- 6. Favorite Way to Express Love -->
                <div class="question-container">
                    <h3>6. How do I mostly show love?</h3>
                    <label class="option-card"><input type="radio" name="q6" value="Words" required><span>Words</span></label>
                    <label class="option-card"><input type="radio" name="q6" value="Gifts"><span>Gifts</span></label>
                    <label class="option-card"><input type="radio" name="q6" value="Time"><span>Time</span></label>
                    <label class="option-card"><input type="radio" name="q6" value="Actions & silence 😶❤️"><span>Actions & silence 😶❤️</span></label>
                </div>

                <!-- 7. Mood Swing Hint -->
                <div class="question-container">
                    <h3>7. When I act cold, what’s the truth behind it?</h3>
                    <label class="option-card"><input type="radio" name="q7" value="I don’t care" required><span>I don’t care</span></label>
                    <label class="option-card"><input type="radio" name="q7" value="I’m bored"><span>I’m bored</span></label>
                    <label class="option-card"><input type="radio" name="q7" value="I’m hurt or protecting myself 🖤"><span>I’m hurt or protecting myself 🖤</span></label>
                    <label class="option-card"><input type="radio" name="q7" value="Just moody"><span>Just moody</span></label>
                </div>

                <!-- 8. What makes me melt instantly? (BONUS SWAP) -->
                <div class="question-container">
                    <h3>8. What makes me melt instantly?</h3>
                    <label class="option-card"><input type="radio" name="q8" value="Compliments" required><span>Compliments</span></label>
                    <label class="option-card"><input type="radio" name="q8" value="Food"><span>Food</span></label>
                    <label class="option-card"><input type="radio" name="q8" value="When you act innocent 😳"><span>When you act innocent 😳</span></label>
                    <label class="option-card"><input type="radio" name="q8" value="when You being flirty and naughty"><span>when You being flirty and naughty</span></label>
                </div>

                <!-- 9. My Comfort Zone -->
                <div class="question-container">
                    <h3>9. Where do I feel the safest?</h3>
                    <label class="option-card"><input type="radio" name="q9" value="My room" required><span>My room</span></label>
                    <label class="option-card"><input type="radio" name="q9" value="With you naughty"><span>With you naughty</span></label>
                    <label class="option-card"><input type="radio" name="q9" value="Traveling"><span>Traveling</span></label>
                    <label class="option-card"><input type="radio" name="q9" value="with bhagwan ji"><span>with bhagwan ji</span></label>
                </div>

                <!-- 10. Secret Code -->
                <div class="question-container">
                    <h3>10. What does “36..!! 🌙👀” mean to us?</h3>
                    <label class="option-card"><input type="radio" name="q10" value="A random number" required><span>A random number</span></label>
                    <label class="option-card"><input type="radio" name="q10" value="Our birthdates"><span>Our birthdates</span></label>
                    <label class="option-card"><input type="radio" name="q10" value="A Secret code"><span>A Secret code</span></label>
                </div>

                <button type="submit" id="quiz-submit" class="glowing-btn">Unlock Secret Box</button>
            </form>
        </section>

        <!-- 3. FINAL SURPRISE PAGE (Secret Gift Section) -->
        <section id="final-section" class="section">
            <!-- Content for Goal Met -->
            <div id="goal-met-content">
                <h2>You passed! You know my heart perfectly 🥰</h2>
                <div class="typing-container">
                    <span id="typing-message"></span>
                </div>
                <button id="reveal-surprise-btn" class="glowing-btn">Tap to reveal the final letter 💝</button>
            </div>

            <!-- Content for Goal Missed -->
            <div id="goal-missed-content" style="display: none;">
                <h2 style="color: var(--primary-color);">Oops! Didn't quite hit the target... 😉</h2>
                <div id="flirty-lines">
                    <!-- Flirty lines appear here -->
                    <span class="flirty-line" id="line-1">Maybe you need a cheat sheet... or maybe just a distraction.</span>
                    <span class="flirty-line" id="line-2">Don't worry, cutie. I'll forgive you later. First, come closer...</span>
                </div>
                <p style="margin-bottom: 20px;">Ready to open the LoveBox anyway?</p>
                <button id="bypass-btn" class="glowing-btn">Yes, open it without the stars! 💋</button>
            </div>

            <div id="surprise-reveal">
                No matter how far you are, how things not working out.. I Always want to choose you among all 8 billion people.. You always to my heart and now in my Love box too.. I love you my gf (Simran ji)
                I proud that I have you.. !!🌙💌
            </div>
        </section>
    </main>

    <script>
        // --- QUIZ DATA ---
        const correctAnswers = {
            q1: 'You (mine )',
            q2: 'to be naughty and cute',
            q3: 'Anywhere with You 💕',
            q4: 'Think about you more',
            q5: 'I still care but won’t say it 😌',
            q6: 'Actions & silence 😶❤️',
            q7: 'I’m hurt or protecting myself 🖤',
            q8: 'when You being flirty and naughty',
            q9: 'with bhagwan ji',
            q10: 'A Secret code'
        };
        const GOAL_SCORE = 6;
        let currentScore = 0;

        // --- CUSTOM MESSAGES ---
        const finalMessageGoalMet = `Even from miles away, you’re my teddy, mine, calm, and my favorite part of every day.
I know this LoveBox may not be perfect, but it’s about 'us' — real, rare, and ours only. 💫`;


        // --- UTILITY FUNCTIONS ---
        function nextSection(nextId) {
            const currentSection = document.querySelector('.section.active');
            const nextSection = document.getElementById(nextId);

            if (currentSection) {
                currentSection.classList.remove('active');
                currentSection.style.transform = 'translateY(-20px)';
                currentSection.style.opacity = '0';
            }

            setTimeout(() => {
                if (nextSection) {
                    nextSection.classList.add('active');
                    nextSection.style.transform = 'translateY(0)';
                    nextSection.style.opacity = '1';

                    if (nextId === 'final-section') {
                        handleFinalPage();
                    }
                }
            }, 500);
        }

        function updateStarJar() {
            document.getElementById('star-count').textContent = `${currentScore} / ${GOAL_SCORE} 🌟`;
        }

        // Function to style the selected option
        function applyCardStyle(card, isSelected) {
            const span = card.querySelector('span');
            if (isSelected) {
                span.style.borderColor = 'var(--secondary-color)';
                span.style.background = 'rgba(255, 140, 148, 0.3)';
                span.style.boxShadow = '0 0 8px var(--secondary-color)';
            } else {
                span.style.borderColor = 'transparent';
                span.style.background = 'rgba(187, 134, 252, 0.1)';
                span.style.boxShadow = 'none';
            }
        }

        // --- QUIZ INTERACTIVITY ---
        document.addEventListener('DOMContentLoaded', () => {
            updateStarJar(); // Initialize jar

            // Attach style change listener to all option cards
            document.querySelectorAll('.option-card').forEach(card => {
                card.addEventListener('click', () => {
                    const radio = card.querySelector('input[type="radio"]');
                    if (radio) {
                        radio.checked = true;
                        
                        // Deselect other cards in the same question
                        const parent = card.closest('.question-container');
                        parent.querySelectorAll('.option-card').forEach(siblingCard => {
                            applyCardStyle(siblingCard, siblingCard === card);
                        });
                    }
                });
            });

            // Quiz Submission Handler
            document.getElementById('quiz-form').addEventListener('submit', function(event) {
                event.preventDefault();
                currentScore = 0;
                
                // Score the quiz
                const questionNames = Object.keys(correctAnswers);
                let allAnswered = true;

                questionNames.forEach(qName => {
                    const selectedOption = document.querySelector(`input[name="${qName}"]:checked`);
                    if (selectedOption) {
                        if (selectedOption.value === correctAnswers[qName]) {
                            currentScore++;
                        }
                    } else {
                        allAnswered = false;
                    }
                });

                if (allAnswered) {
                    updateStarJar();
                    // Transition to final page
                    setTimeout(() => {
                        nextSection('final-section');
                    }, 500);
                } else {
                    // Replaced alert() with a console log/temporary message, as alerts are blocked
                    console.error('Please answer all 10 questions to unlock the secret!'); 
                    alert('Please answer all 10 questions to unlock the secret!');
                }
            });
        });


        // --- FINAL PAGE LOGIC ---
        const typingElement = document.getElementById('typing-message');
        const revealBtn = document.getElementById('reveal-surprise-btn');
        
        function startTypingAnimation() {
            typingElement.innerHTML = '';
            typingElement.style.borderRight = '3px solid var(--secondary-color)'; 
            let i = 0;
            
            const typingInterval = setInterval(() => {
                if (i < finalMessageGoalMet.length) {
                    // Replace newline character with HTML <br> tag for proper wrapping
                    const char = finalMessageGoalMet.charAt(i);
                    if (char === '\n') {
                        typingElement.innerHTML += '<br>';
                    } else {
                        typingElement.innerHTML += char;
                    }
                    i++;
                } else {
                    clearInterval(typingInterval);
                    typingElement.style.borderRight = 'none';
                    revealBtn.style.display = 'block';
                }
            }, 60);
        }

        function showFlirtyLines() {
            const line1 = document.getElementById('line-1');
            const line2 = document.getElementById('line-2');
            const bypassBtn = document.getElementById('bypass-btn');

            setTimeout(() => { line1.style.opacity = 1; }, 500);
            setTimeout(() => { line2.style.opacity = 1; }, 1500);
            setTimeout(() => { bypassBtn.style.display = 'block'; }, 2500);

            // Attach listener to bypass button
            bypassBtn.addEventListener('click', () => {
                document.getElementById('goal-missed-content').style.display = 'none';
                document.getElementById('goal-met-content').style.display = 'block';
                // Trigger the main typing message after bypass
                startTypingAnimation();
            });
        }


        function handleFinalPage() {
            document.getElementById('goal-met-content').style.display = 'none';
            document.getElementById('goal-missed-content').style.display = 'none';
            
            if (currentScore >= GOAL_SCORE) {
                // Goal Met
                document.getElementById('goal-met-content').style.display = 'block';
                startTypingAnimation();
            } else {
                // Goal Missed
                document.getElementById('goal-missed-content').style.display = 'block';
                showFlirtyLines();
            }
        }


        /* --- FINAL SURPRISE REVEAL --- */
        document.getElementById('reveal-surprise-btn').addEventListener('click', () => {
            document.getElementById('reveal-surprise-btn').style.display = 'none';
            document.getElementById('surprise-reveal').style.display = 'block';
        });

    </script>
</body>
</html>