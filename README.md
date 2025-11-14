<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Black Goose - AI Content Hub</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        /* -------------------- Global -------------------- */
        body {
            margin: 0;
            font-family: 'Inter', sans-serif;
            background-color: #0a0a0a;
            color: #fff;
        }
        h1,h2,h3 { margin: 0; }
        a { text-decoration: none; color: inherit; }

        /* -------------------- Header -------------------- */
        header {
            background: linear-gradient(90deg, #4f46e5, #6366f1);
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 4px 10px rgba(0,0,0,0.3);
        }
        header h1 { font-size: 2rem; font-weight: 700; }
        nav a {
            margin-left: 1.5rem;
            font-weight: 600;
            transition: all 0.3s ease;
        }
        nav a:hover { text-decoration: underline; }

        /* -------------------- Hero -------------------- */
        #hero {
            text-align: center;
            padding: 6rem 2rem;
            background: linear-gradient(180deg, #111 0%, #1a1a1a 100%);
        }
        #hero h2 { font-size: 2.5rem; color: #4f46e5; margin-bottom: 1rem; }
        #hero p { font-size: 1.2rem; max-width: 600px; margin: 0 auto; }

        /* -------------------- Sections -------------------- */
        section { padding: 4rem 2rem; max-width: 1000px; margin: 0 auto; }
        section h2 { color: #4f46e5; margin-bottom: 1rem; font-size: 2rem; }

        .card-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .card {
            background: #1f1f1f;
            padding: 1.5rem;
            border-radius: 1rem;
            box-shadow: 0 4px 15px rgba(0,0,0,0.5);
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.7);
        }
        .card button {
            margin-top: 1rem;
            background: #4f46e5;
            color: #fff;
            border: none;
            padding: 0.7rem 1.2rem;
            font-weight: 600;
            border-radius: 0.5rem;
            cursor: pointer;
            transition: background 0.3s;
        }
        .card button:hover { background: #6366f1; }

        .output {
            margin-top: 1rem;
            background: #0f0f0f;
            padding: 1rem;
            border-radius: 0.5rem;
            min-height: 60px;
            white-space: pre-wrap;
            font-family: monospace;
        }

        /* -------------------- Footer -------------------- */
        footer {
            text-align: center;
            padding: 2rem;
            background: #111;
            font-size: 0.9rem;
            color: #aaa;
        }

        /* -------------------- Responsive -------------------- */
        @media(max-width: 600px){
            header { flex-direction: column; align-items: flex-start; }
            nav { margin-top: 0.5rem; }
            nav a { margin-left: 0; margin-right: 1rem; }
        }
    </style>
</head>
<body>

<header>
    <h1>Black Goose</h1>
    <nav>
        <a href="#ideas">Idées</a>
        <a href="#scripts">Scripts</a>
        <a href="#captions">Captions</a>
        <a href="#planner">Planification</a>
    </nav>
</header>

<section id="hero">
    <h2>Hub IA pour créateurs de contenu</h2>
    <p>Génère des idées, des scripts, des captions et planifie tes posts pour TikTok, Instagram, YouTube et plus encore. Black Goose centralise tout ton workflow créatif.</p>
</section>

<!-- -------------------- Idées -------------------- -->
<section id="ideas">
    <h2>Idées de contenu</h2>
    <div class="card-container">
        <div class="card">
            <h3>Générateur d'idées</h3>
            <p>Obtiens des idées virales adaptées à chaque plateforme.</p>
            <button onclick="generateIdea()">Générer une idée</button>
            <div class="output" id="ideaOutput"></div>
        </div>
    </div>
</section>

<!-- -------------------- Scripts -------------------- -->
<section id="scripts">
    <h2>Scripts & Scénarios</h2>
    <div class="card-container">
        <div class="card">
            <h3>Mini-script vidéo</h3>
            <p>Crée rapidement un script pour tes vidéos.</p>
            <button onclick="generateScript()">Générer un script</button>
            <div class="output" id="scriptOutput"></div>
        </div>
    </div>
</section>

<!-- -------------------- Captions -------------------- -->
<section id="captions">
    <h2>Captions & Hashtags</h2>
    <div class="card-container">
        <div class="card">
            <h3>Captions optimisées</h3>
            <p>Des captions et hashtags prêts à l’emploi pour tes posts.</p>
            <button onclick="generateCaption()">Générer caption & hashtags</button>
            <div class="output" id="captionOutput"></div>
        </div>
    </div>
</section>

<!-- -------------------- Planification -------------------- -->
<section id="planner">
    <h2>Planification</h2>
    <div class="card-container">
        <div class="card">
            <h3>Calendrier créatif</h3>
            <p>Ajoute tes idées au calendrier et garde la trace de tes posts.</p>
            <button onclick="addToPlanner()">Ajouter idée</button>
            <div class="output" id="plannerOutput">Calendrier vide pour le moment...</div>
        </div>
    </div>
</section>

<footer>
    &copy; 2025 Black Goose. Tous droits réservés.
</footer>

<script>
    const ideas = [
        "TikTok: 10 astuces productivité",
        "Reel Instagram: transformation avant/après",
        "YouTube Shorts: top 5 outils AI pour créateurs",
        "Vidéo challenge tendance avec twist original",
        "Story Instagram: tutoriel rapide",
        "TikTok: hacks invisibles pour booster ton reach",
        "Short YouTube: mini guide création AI"
    ];

    const scripts = [
        "Intro dynamique + Hook + 3 étapes + Call-to-action",
        "Présentation du thème + Astuce 1 + Astuce 2 + Astuce 3 + Conclusion",
        "Question aux spectateurs + Démo rapide + Call-to-action",
        "Mini tutoriel étape par étape + Punchline finale",
        "Storytelling: contexte + problème + solution + CTA"
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
        if(idea && !planner.includes(idea)) { planner.push(idea); }
        document.getElementById("plannerOutput").innerText = planner.length ? planner.join("\n") : "Calendrier vide pour le moment...";
    }
</script>

</body>
</html>
