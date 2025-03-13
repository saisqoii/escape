<html lang="nl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Escape Room - Doodverklaard</title>
    <link href="https://fonts.googleapis.com/css2?family=Creepster&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Creepster', cursive;
            text-align: center;
            background-color: black;
            color: red;
            padding: 20px;
        }
        .container {
            max-width: 600px;
            margin: auto;
            background: #222;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(255, 0, 0, 0.8);
            border: 2px solid red;
            margin-top: 20px;
        }
        input, button {
            padding: 10px;
            margin: 10px;
            font-size: 16px;
            font-family: 'Creepster', cursive;
            background: black;
            color: red;
            border: 2px solid red;
        }
        button:hover {
            background: red;
            color: black;
        }
        .hidden {
            display: none;
        }
        .end-container {
            max-width: 800px;
            margin: auto;
            background: #111;
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 0 30px rgba(255, 0, 0, 1);
            border: 3px solid red;
        }
    </style>
</head>
<body>
    <div class="container" id="riddle1">
        <h1>Escape Room: Doodverklaard</h1>
        <p>heb je opgelet?</p>
        <p><strong>"Wat is de naam van het hoofdpersonage"</strong></p>
        <input type="text" id="answer1" placeholder="Jouw antwoord">
        <button onclick="checkAnswer(1, 'isa')">Controleer</button>
        <p id="message1"></p>
    </div>
    
    <div class="container hidden" id="riddle2">
        <p><strong>"Hoe oud is isa?"</strong></p>
        <input type="text" id="answer2" placeholder="Jouw antwoord">
        <button onclick="checkAnswer(2, '17')">Controleer</button>
        <p id="message2"></p>
    </div>

    <div class="container hidden" id="riddle3">
        <p><strong>"In welk genre valt het boek?"</strong></p>
        <input type="text" id="answer3" placeholder="Jouw antwoord">
        <button onclick="checkAnswer(3, 'Thriller')">Controleer</button>
        <p id="message3"></p>
    </div>

    <div class="container hidden" id="riddle4">
        <p><strong>"voor wat vecht isa?"</strong></p>
        <input type="text" id="answer4" placeholder="Jouw antwoord">
        <button onclick="checkAnswer(4, 'id', 'identiteit')">Controleer</button>
        <p id="message4"></p>
    </div>
    
    <div class="container hidden" id="riddle5">
        <p><strong>" Wat wil de organisatie van Isa afnemen?"</strong></p>
        <input type="text" id="answer5" placeholder="Jouw antwoord">
        <button onclick="checkAnswer(5, 'herinneringen')">Controleer</button>
        <p id="message5"></p>
    </div>

    <div class="end-container hidden" id="endScreen">
        <h1>🎉 yippie!! 🎉</h1>
        <p>gewonnen , maar ben je eerste?.</p>
        <p>roep bingo voor de prijs!🍬</h2>
    </div>

    <script>
        function checkAnswer(step, ...correctAnswers) {
            let answer = document.getElementById(`answer${step}`)?.value.toLowerCase().trim();
            if (correctAnswers.includes(answer)) {
                document.getElementById(`riddle${step}`).classList.add("hidden");
                if (document.getElementById(`riddle${step + 1}`)) {
                    document.getElementById(`riddle${step + 1}`).classList.remove("hidden");
                } else {
                    document.getElementById("endScreen").classList.remove("hidden");
                }
            } else {
                document.getElementById(`message${step}`).innerHTML = "Probeer opnieuw...";
            }
        }
    </script>
</body>
</html>
