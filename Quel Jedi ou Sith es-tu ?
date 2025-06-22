<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Quel Jedi ou Sith es-tu ?</title>
  <style>
    body {
      background-color: #0b0c10;
      color: #c5c6c7;
      font-family: 'Arial', sans-serif;
      text-align: center;
      padding: 20px;
    }

    h1 {
      color: #66fcf1;
      font-size: 36px;
      margin-bottom: 20px;
    }

    img.logo {
      max-width: 150px;
      margin-bottom: 20px;
    }

    .question {
      background-color: #1f2833;
      margin: 20px auto;
      padding: 20px;
      border-radius: 10px;
      max-width: 600px;
      box-shadow: 0 0 10px #45a29e;
    }

    .options button {
      background-color: #45a29e;
      color: #fff;
      border: none;
      margin: 5px;
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
      border-radius: 5px;
      transition: background 0.3s ease;
    }

    .options button:hover {
      background-color: #66fcf1;
      color: #0b0c10;
    }

    .result {
      display: none;
      margin-top: 30px;
      background-color: #1f2833;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px #66fcf1;
    }

    .score {
      margin-top: 10px;
      color: #66fcf1;
    }
  </style>
</head>
<body>
  <img src="https://zupimages.net/up/25/25/j7gb.png" class="logo" alt="Logo Jedi Sith">
  <h1>Quel Jedi ou Sith es-tu ?</h1>

  <div id="quiz-container">
    <div class="question" id="question-container">
      <h2 id="question-text"></h2>
      <div class="options" id="options-container"></div>
    </div>
  </div>

  <div class="result" id="result-container">
    <h2>Tu es...</h2>
    <p id="result-text"></p>
    <p class="score">Ta destinée est écrite dans les étoiles.</p>
    <button onclick="startQuiz()">Rejouer</button>
  </div>

  <script>
    const questions = [
      {
        question: "Que ferais-tu avec un grand pouvoir ?",
        options: ["Protéger la paix", "Imposer l'ordre", "Équilibrer la force", "Dominer les faibles"],
        result: [0, 1, 2, 3]
      },
      {
        question: "Ton arme de prédilection ?",
        options: ["Sabre laser bleu", "Sabre laser rouge", "Sabre laser vert", "Double lame"],
        result: [0, 3, 1, 2]
      },
      {
        question: "Ton plus grand défaut ?",
        options: ["La peur", "La colère", "L’arrogance", "La compassion"],
        result: [0, 3, 2, 1]
      },
      {
        question: "Quelle est ta voie ?",
        options: ["Le Conseil Jedi", "Le Côté obscur", "La rébellion", "La sagesse de la Force"],
        result: [0, 3, 1, 2]
      },
      {
        question: "Que penses-tu de l’amour ?",
        options: ["Un attachement dangereux", "Une faiblesse à exploiter", "Une force cachée", "Un sacrifice nécessaire"],
        result: [0, 3, 2, 1]
      }
    ];

    const characters = [
      { name: "Obi-Wan Kenobi", description: "Sage, loyal et discipliné. Tu fais passer le devoir avant tout." },
      { name: "Luke Skywalker", description: "L'élu du renouveau. Courageux, hésitant, mais toujours guidé par le cœur." },
      { name: "Ahsoka Tano", description: "Indépendante et déterminée, tu marches sur ta propre voie." },
      { name: "Darth Vader", description: "Puissant, torturé, tu es la tragédie personnifiée du côté obscur." },
      { name: "Darth Maul", description: "Animé par la vengeance, tu es la rage incarnée." },
      { name: "Yoda", description: "Ancien et profond, tu incarnes la sagesse millénaire de la Force." },
      { name: "Kylo Ren", description: "Instable, déchiré entre lumière et obscurité, ton destin est chaotique." },
      { name: "Mace Windu", description: "Rigide mais puissant, tu défends la justice sans compromis." }
    ];

    let currentQuestion = 0;
    let userAnswers = [];

    function startQuiz() {
      currentQuestion = 0;
      userAnswers = [];
      document.getElementById("result-container").style.display = "none";
      document.getElementById("quiz-container").style.display = "block";
      showQuestion();
    }

    function showQuestion() {
      const question = questions[currentQuestion];
      document.getElementById("question-text").innerText = question.question;

      const optionsContainer = document.getElementById("options-container");
      optionsContainer.innerHTML = "";

      question.options.forEach((option, index) => {
        const button = document.createElement("button");
        button.innerText = option;
        button.onclick = () => {
          userAnswers.push(question.result[index]);
          currentQuestion++;
          if (currentQuestion < questions.length) {
            showQuestion();
          } else {
            showResult();
          }
        };
        optionsContainer.appendChild(button);
      });
    }

    function showResult() {
      const resultIndex = userAnswers.reduce((a, b) => a + b, 0) % characters.length;
      const result = characters[resultIndex];

      document.getElementById("result-text").innerText = `${result.name} — ${result.description}`;
      document.getElementById("quiz-container").style.display = "none";
      document.getElementById("result-container").style.display = "block";
    }

    startQuiz();
  </script>
</body>
</html>
