# BlackGoose.github.io
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Black Goose - Content Creator AI Hub</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            margin: 0;
            font-family: 'Inter', sans-serif;
            background: #0f0f0f;
            color: #fff;
        }
        header {
            background: linear-gradient(90deg, #4f46e5, #6366f1);
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 1000;
        }
        header h1 {
            margin: 0;
            font-size: 1.8rem;
            font-weight: 700;
        }
        nav a {
            color: #fff;
            margin-left: 1.5rem;
            text-decoration: none;
            font-weight: 600;
        }
        nav a:hover {
            text-decoration: underline;
        }
        section {
            padding: 4rem 2rem;
            max-width: 1000px;
            margin: 0 auto;
        }
        h2 {
            font-size: 2rem;
            margin-bottom: 1rem;
            color: #4f46e5;
        }
        button {
            background: #4f46e5;
            color: #fff;
            border: none;
            padding: 0.7rem 1.5rem;
            font-size: 1rem;
            font-weight: 600;
            border-radius: 0.5rem;
            cursor: pointer;
            margin-top: 1rem;
        }
        button:hover {
            background: #6366f1;
        }
        .output {
            margin-top: 1rem;
            background: #1f1f1f;
            padding: 1rem;
            border-radius: 0.5rem;
            min-height: 50px;
            white-space: pre-wrap;
        }
        footer {
            text-align: center;
            padding: 2rem;
            background: #111;
            margin-top: 2rem;
            font-size: 0.9rem;
            color: #aaa;
        }
        /* Responsive */
        @media(max-width: 600px){
            header {
                flex-direction: column;
                align-items: flex-start;
            }
            nav {
                margin-top: 0.5rem;
            }
            nav a {
                margin-left: 0;
                margin-right: 1rem;
            }
        }
    </style>
</head>
<body>

<header>
    <h1>Black Goose</h1>
    <nav>
        <a href="#ideas">Idées</a>
        <a href="#scripts">Scripts</a>
        <a href="#captions">Captions & Hashtags</a>
        <a href="#planner">Planification</a>
    </nav>
</header>

<section id="hero">
    <h2>Bienvenue sur Black Goose</h2>
    <p>Le hub ultime pour les créateurs de contenu. Génère des idées, des scripts, des hashtags, et planifie tes publications avec style.</p>
</section>

<section id="ideas">
    <h2>Idées de contenu</h2>
    <p>Génère des idées de vidéos ou posts viraux pour TikTok, YouTube, Instagram.</p>
    <button onclick="generateIdea()">Générer une idée</button>
    <div class="output" id="ideaOutput"></div>
</section>

<section id="scripts">
    <h2>Script & Scénario</h2>
    <p>Crée un mini script pour ta prochaine vidéo.</p>
    <button onclick="generateScript()">Générer un script</button>
    <div class="output" id="scriptOutput"></div>
</section>

<section id="captions">
    <h2>Captions & Hashtags</h2>
    <p>Obtiens des captions accrocheuses et des hashtags optimisés.</p>
    <button onclick="generateCaption()">Générer caption & hashtags</button>
    <div class="output" id="captionOutput"></div>
</section>

<section id="planner">
    <h2>Planification</h2>
    <p>Planifie tes publications et garde une trace de tes idées.</p>
    <button onclick="addToPlanner()">Ajouter une idée au calendrier</button>
    <div class="output" id="plannerOutput">Calendrier vide pour le moment...</div>
</section>

<footer>
    &copy; 2025 Black Goose. Tous droits réservés.
</footer>

<script>
    const ideas = [
        "Vidéo TikTok: 10 astuces productivité",
        "Reel Instagram: transformation avant/après",
        "YouTube Shorts: top 5 outils AI pour créateurs",
        "Vidéo challenge tendance avec twist original",
        "Story Instagram: tutoriel rapide"
    ];

    const scripts = [
        "Intro dynamique + Hook + 3 étapes + Call-to-action",
        "Présentation du thème + Astuce 1 + Astuce 2 + Astuce 3 + Conclusion",
        "Question aux spectateurs + Démonstration rapide + Appel à commenter",
        "Mini tutoriel étape par étape + Punchline finale",
        "Vidéo storytelling: contexte + problème + solution + call-to-action"
    ];

    const captions = [
        "Boost ton contenu avec ces astuces #ContentCreator #Viral",
        "Découvre le secret derrière cette idée #TikTokTips #CreatorAI",
        "Transforme tes vidéos avec ce hack #SocialMedia #BlackGoose",
        "Gagne du temps et crée mieux #AIContent #CreatorLife",
        "Rends ton feed incroyable avec ces idées #InstaGrowth #ViralVideo"
    ];

    let planner = [];

    function generateIdea() {
        const randomIdea = ideas[Math.floor(Math.random() * ideas.length)];
        document.getElementById("ideaOutput").innerText = randomIdea;
    }

    function generateScript() {
        const randomScript = scripts[Math.floor(Math.random() * scripts.length)];
        document.getElementById("scriptOutput").innerText = randomScript;
    }

    function generateCaption() {
        const randomCaption = captions[Math.floor(Math.random() * captions.length)];
        document.getElementById("captionOutput").innerText = randomCaption;
    }

    function addToPlanner() {
        const idea = document.getElementById("ideaOutput").innerText;
        if (idea && !planner.includes(idea)) {
            planner.push(idea);
        }
        document.getElementById("plannerOutput").innerText = planner.length ? planner.join("\n") : "Calendrier vide pour le moment...";
    }
</script>

</body>
</html>

