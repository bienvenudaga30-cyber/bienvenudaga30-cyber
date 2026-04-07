<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bienvenu DAGA | Data Scientist</title>
    <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Fira Code', 'Courier New', monospace;
            background: linear-gradient(135deg, #0a0e27 0%, #0f1235 25%, #1a1f4e 50%, #0f1235 75%, #0a0e27 100%);
            background-attachment: fixed;
            color: #e4e6eb;
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
        }

        /* Animation de fond avec particules */
        .background-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            overflow: hidden;
        }

        .particle {
            position: absolute;
            background: rgba(144, 202, 249, 0.1);
            border-radius: 50%;
            pointer-events: none;
            animation: floatParticle linear infinite;
        }

        @keyframes floatParticle {
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
                transform: translateY(-100vh) rotate(360deg);
                opacity: 0;
            }
        }

        /* Grid pattern overlay */
        .grid-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                linear-gradient(rgba(144, 202, 249, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(144, 202, 249, 0.03) 1px, transparent 1px);
            background-size: 50px 50px;
            pointer-events: none;
            z-index: 1;
        }

        /* Glow effect */
        .glow {
            position: fixed;
            top: 50%;
            left: 50%;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at center, rgba(88, 166, 255, 0.08) 0%, transparent 70%);
            pointer-events: none;
            z-index: 1;
            animation: pulse 8s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% {
                opacity: 0.3;
                transform: scale(1);
            }
            50% {
                opacity: 0.6;
                transform: scale(1.05);
            }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
            position: relative;
            z-index: 2;
        }

        /* Glassmorphism cards */
        .card {
            background: rgba(13, 17, 23, 0.7);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            border: 1px solid rgba(144, 202, 249, 0.2);
            padding: 2rem;
            margin-bottom: 2rem;
            transition: all 0.3s ease;
        }

        .card:hover {
            transform: translateY(-5px);
            border-color: rgba(144, 202, 249, 0.4);
            box-shadow: 0 10px 40px rgba(88, 166, 255, 0.1);
        }

        /* Typing animation for header */
        .typing-header {
            font-size: 3rem;
            font-weight: 700;
            background: linear-gradient(135deg, #90caf9, #58a6ff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-align: center;
            margin-bottom: 1rem;
            overflow: hidden;
            border-right: 3px solid #90caf9;
            white-space: nowrap;
            width: 0;
            animation: typing 3s steps(30, end) forwards, blink-caret 0.75s step-end infinite;
        }

        @keyframes typing {
            from { width: 0; }
            to { width: 100%; }
        }

        @keyframes blink-caret {
            from, to { border-color: transparent; }
            50% { border-color: #90caf9; }
        }

        /* Subtitle animation */
        .subtitle {
            text-align: center;
            margin: 2rem 0;
        }

        /* Badge styling */
        .badge-container {
            display: flex;
            justify-content: center;
            gap: 1rem;
            flex-wrap: wrap;
            margin: 2rem 0;
        }

        .badge {
            display: inline-flex;
            align-items: center;
            padding: 0.5rem 1rem;
            border-radius: 8px;
            text-decoration: none;
            transition: all 0.3s ease;
            font-weight: 500;
            gap: 0.5rem;
        }

        .badge:hover {
            transform: translateY(-2px);
            filter: brightness(1.1);
        }

        /* Code block styling */
        .code-block {
            background: #0d1117;
            border-radius: 12px;
            padding: 1.5rem;
            border-left: 4px solid #58a6ff;
            overflow-x: auto;
            font-family: 'Fira Code', monospace;
            font-size: 0.9rem;
            line-height: 1.5;
        }

        .code-block pre {
            margin: 0;
            color: #c9d1d9;
        }

        /* Skills grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 1rem;
            margin: 2rem 0;
        }

        .skill-item {
            text-align: center;
            padding: 1rem;
            background: rgba(13, 17, 23, 0.5);
            border-radius: 12px;
            border: 1px solid rgba(144, 202, 249, 0.2);
            transition: all 0.3s ease;
        }

        .skill-item:hover {
            transform: scale(1.05);
            border-color: #58a6ff;
            background: rgba(88, 166, 255, 0.1);
        }

        .skill-icon {
            font-size: 2rem;
            margin-bottom: 0.5rem;
        }

        /* Stats containers */
        .stats-container {
            display: flex;
            justify-content: center;
            gap: 2rem;
            flex-wrap: wrap;
            margin: 2rem 0;
        }

        .stat-card {
            background: rgba(13, 17, 23, 0.5);
            border-radius: 16px;
            padding: 1rem;
            text-align: center;
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            transform: scale(1.02);
        }

        /* Timeline */
        .timeline {
            position: relative;
            padding-left: 2rem;
        }

        .timeline-item {
            position: relative;
            padding: 1rem 0 1rem 2rem;
            border-left: 2px solid #58a6ff;
            margin-left: 1rem;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -0.5rem;
            top: 1.5rem;
            width: 1rem;
            height: 1rem;
            background: #58a6ff;
            border-radius: 50%;
        }

        .timeline-year {
            color: #58a6ff;
            font-weight: bold;
            font-size: 1.2rem;
        }

        /* Quote */
        .quote {
            text-align: center;
            font-style: italic;
            padding: 2rem;
            background: linear-gradient(135deg, rgba(88, 166, 255, 0.1), rgba(144, 202, 249, 0.05));
            border-radius: 16px;
            border: 1px solid rgba(144, 202, 249, 0.3);
        }

        /* Footer wave */
        .footer-wave {
            position: relative;
            bottom: 0;
            left: 0;
            width: 100%;
            overflow: hidden;
            line-height: 0;
            margin-top: 3rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .container {
                padding: 1rem;
            }
            
            .typing-header {
                font-size: 2rem;
                white-space: normal;
                animation: none;
                border-right: none;
                width: 100%;
            }
            
            .card {
                padding: 1rem;
            }
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: #0d1117;
        }

        ::-webkit-scrollbar-thumb {
            background: #58a6ff;
            border-radius: 4px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: #90caf9;
        }

        /* Link styling */
        a {
            color: #90caf9;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        a:hover {
            color: #58a6ff;
        }

        hr {
            border: none;
            height: 1px;
            background: linear-gradient(90deg, transparent, #58a6ff, transparent);
            margin: 2rem 0;
        }
    </style>
</head>
<body>
    <!-- Background animations -->
    <div class="background-animation" id="particles"></div>
    <div class="grid-overlay"></div>
    <div class="glow"></div>

    <div class="container">
        <!-- Header -->
        <div class="card">
            <h1 class="typing-header">Bienvenu DAGA</h1>
            
            <div class="subtitle">
                <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=18&duration=3500&pause=800&color=90CAF9&center=true&vCenter=true&width=700&lines=Data+Scientist+in+Training+%F0%9F%93%88;GCI+%E2%80%94+University+of+Tokyo+2026+%F0%9F%87%AF%F0%9F%87%B5;Bridging+raw+data+and+smart+decisions+%F0%9F%94%8D;Based+in+Cotonou%2C+B%C3%A9nin+%F0%9F%87%A7%F0%9F%87%AF" alt="Typing SVG" />
            </div>

            <div class="badge-container">
                <a href="https://gci2.t.u-tokyo.ac.jp" class="badge" style="background: #8e0c24; color: white;">🎓 GCI 2026 — University of Tokyo</a>
                <a href="https://bienvenudaga.vercel.app/" class="badge" style="background: #000000; color: white;">🌐 Portfolio</a>
                <a href="https://www.linkedin.com/in/kossoba-destin-bienvenu-daga-4496b8396" class="badge" style="background: #0A66C2; color: white;">🔗 LinkedIn</a>
                <a href="mailto:bienvenudaga30@gmail.com" class="badge" style="background: #D14836; color: white;">📧 Gmail</a>
            </div>
        </div>

        <!-- whoami section -->
        <div class="card">
            <h2 style="color: #90caf9; margin-bottom: 1rem;">🚀 whoami</h2>
            <div class="code-block">
                <pre>
class DataScientist:
    def __init__(self):
        self.name = "Bienvenu DAGA"
        self.location = "Cotonou, Bénin 🇧🇯"
        self.education = "Digitalisation & Data Science — Sèmè City Institute (SCITI)"
        self.program = "Global Consumer Intelligence (GCI) — University of Tokyo 🇯🇵"
        self.role = "Data Scientist & Web Enthusiast"
        self.mission = "Bridging the gap between raw data and smart decisions."
        self.philosophy = "Data-driven, human-centered."
    
    def introduce(self):
        return f"👋 {self.name} — {self.mission}"

me = DataScientist()
print(me.introduce())</pre>
            </div>
        </div>

        <!-- tech_stack section -->
        <div class="card">
            <h2 style="color: #90caf9; margin-bottom: 1rem;">🛠️ tech_stack</h2>
            <div class="skills-grid">
                <div class="skill-item">
                    <div class="skill-icon">🐍</div>
                    <div>Python</div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">📊</div>
                    <div>R</div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">🌐</div>
                    <div>HTML5/CSS3</div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">⚡</div>
                    <div>Node.js</div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">🗄️</div>
                    <div>SQL</div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">🔧</div>
                    <div>Git/GitHub</div>
                </div>
            </div>
            
            <div style="margin-top: 1.5rem;">
                <p><strong>Core Skills:</strong> Analyse de données · Machine Learning · Développement Web · Déploiement · Requêtage & Gestion de bases</p>
            </div>
        </div>

        <!-- github_insights section -->
        <div class="card">
            <h2 style="color: #90caf9; margin-bottom: 1rem;">📊 github_insights</h2>
            <div class="stats-container">
                <div class="stat-card">
                    <img src="https://github-readme-stats.vercel.app/api?username=bienvenudaga30-cyber&show_icons=true&hide_border=true&title_color=90caf9&text_color=c9d1d9&bg_color=0d1117&icon_color=58a6ff&count_private=true&include_all_commits=true&hide=contribs&ring_color=90caf9" alt="GitHub Stats" style="max-width: 100%;">
                </div>
                <div class="stat-card">
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=bienvenudaga30-cyber&layout=compact&hide_border=true&title_color=90caf9&text_color=c9d1d9&bg_color=0d1117&langs_count=8" alt="Top Languages" style="max-width: 100%;">
                </div>
            </div>
            
            <div style="text-align: center; margin-top: 1rem;">
                <img src="https://github-readme-streak-stats.herokuapp.com/?user=bienvenudaga30-cyber&theme=github-dark-blue&hide_border=true&stroke=90caf9&ring=90caf9&fire=ff6b6b&currStreakLabel=90caf9" alt="GitHub Streak" style="max-width: 100%;">
            </div>
            
            <div style="margin-top: 1rem;">
                <img src="https://github-readme-activity-graph.vercel.app/graph?username=bienvenudaga30-cyber&bg_color=0d1117&color=90caf9&line=58a6ff&point=ffffff&area=true&hide_border=true&area_color=58a6ff&custom_title=Contribution%20Graph" alt="Contribution Graph" style="max-width: 100%;">
            </div>
            
            <div style="margin-top: 1rem; text-align: center;">
                <img src="https://github-profile-trophy.vercel.app/?username=bienvenudaga30-cyber&theme=darkhub&no-frame=true&column=4&margin-w=15&margin-h=15" alt="GitHub Trophies" style="max-width: 100%;">
            </div>
        </div>

        <!-- git_log section -->
        <div class="card">
            <h2 style="color: #90caf9; margin-bottom: 1rem;">📜 git_log --history</h2>
            <div class="code-block">
                <pre>
$ git log --oneline --decorate

2026  feat(gci):  Selected for GCI (Global Consumer Intelligence)
                  University of Tokyo 🇯🇵
                  [One of the few African students admitted]

2025  feat(sciti): Enrolled at Sèmè City Institute (SCITI)
                   Programme: Digitalisation & Data Science 🎓

2024  feat(bac):   Baccalauréat Série C — Mention: Excellence Scientifique 🏅

$ git tag -l
GCI-2026
SCITI-2025
BAC-2024</pre>
            </div>
        </div>

        <!-- about_africa section -->
        <div class="card">
            <h2 style="color: #90caf9; margin-bottom: 1rem;">🌍 about_africa</h2>
            <div class="quote">
                <p>« Représenter le Bénin sur la scène mondiale de la data science — <br/>
                prouver que l'excellence africaine n'a pas de frontières. »</p>
                <footer style="margin-top: 1rem; color: #90caf9;">— Bienvenu DAGA</footer>
            </div>
        </div>

        <!-- connect section -->
        <div class="card">
            <h2 style="color: #90caf9; margin-bottom: 1rem;">📬 connect_with_me</h2>
            <div class="badge-container">
                <a href="mailto:bienvenudaga30@gmail.com" class="badge" style="background: #D14836; color: white;">📧 Gmail</a>
                <a href="https://www.linkedin.com/in/kossoba-destin-bienvenu-daga-4496b8396" class="badge" style="background: #0A66C2; color: white;">🔗 LinkedIn</a>
                <a href="https://bienvenudaga.vercel.app/" class="badge" style="background: #000000; color: white;">🌐 Portfolio</a>
            </div>
            
            <div style="text-align: center; margin-top: 1rem;">
                <img src="https://komarev.com/ghpvc/?username=bienvenudaga30-cyber&label=Profile%20Views&color=0d1117&style=flat&labelColor=0d1117" alt="Profile views" />
            </div>
        </div>
    </div>

    <div class="footer-wave">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 120">
            <path fill="url(#gradient)" fill-opacity="1" d="M0,64L80,69.3C160,75,320,85,480,80C640,75,800,53,960,48C1120,43,1280,53,1360,58.7L1440,64L1440,120L1360,120C1280,120,1120,120,960,120C800,120,640,120,480,120C320,120,160,120,80,120L0,120Z">
                <animate attributeName="d" dur="10s" repeatCount="indefinite" values="
                    M0,64L80,69.3C160,75,320,85,480,80C640,75,800,53,960,48C1120,43,1280,53,1360,58.7L1440,64L1440,120L1360,120C1280,120,1120,120,960,120C800,120,640,120,480,120C320,120,160,120,80,120L0,120Z;
                    M0,32L80,42.7C160,53,320,75,480,80C640,85,800,75,960,64C1120,53,1280,43,1360,37.3L1440,32L1440,120L1360,120C1280,120,1120,120,960,120C800,120,640,120,480,120C320,120,160,120,80,120L0,120Z;
                    M0,64L80,69.3C160,75,320,85,480,80C640,75,800,53,960,48C1120,43,1280,53,1360,58.7L1440,64L1440,120L1360,120C1280,120,1120,120,960,120C800,120,640,120,480,120C320,120,160,120,80,120L0,120Z" />
            </path>
            <defs>
                <linearGradient id="gradient" x1="0%" y1="0%" x2="100%" y2="0%">
                    <stop offset="0%" style="stop-color:#0a0e27;stop-opacity:1" />
                    <stop offset="50%" style="stop-color:#1a1f4e;stop-opacity:1" />
                    <stop offset="100%" style="stop-color:#0a0e27;stop-opacity:1" />
                </linearGradient>
            </defs>
        </svg>
    </div>

    <script>
        // Particle animation system
        function createParticles() {
            const container = document.getElementById('particles');
            const particleCount = 50;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.classList.add('particle');
                
                // Random size between 2px and 6px
                const size = Math.random() * 4 + 2;
                particle.style.width = size + 'px';
                particle.style.height = size + 'px';
                
                // Random position
                particle.style.left = Math.random() * 100 + '%';
                
                // Random animation duration between 8s and 20s
                const duration = Math.random() * 12 + 8;
                particle.style.animationDuration = duration + 's';
                
                // Random delay
                particle.style.animationDelay = Math.random() * 10 + 's';
                
                // Random opacity
                particle.style.opacity = Math.random() * 0.3 + 0.1;
                
                container.appendChild(particle);
            }
        }
        
        // Add floating numbers effect
        function addFloatingNumbers() {
            const container = document.getElementById('particles');
            const numbers = ['0', '1', '&lt;/&gt;', '{}', '()', 'def', 'class', 'import', 'npm', 'git'];
            
            for (let i = 0; i < 30; i++) {
                const element = document.createElement('div');
                element.classList.add('particle');
                element.textContent = numbers[Math.floor(Math.random() * numbers.length)];
                element.style.fontSize = (Math.random() * 14 + 10) + 'px';
                element.style.fontFamily = 'monospace';
                element.style.color = 'rgba(144, 202, 249, 0.15)';
                element.style.background = 'none';
                element.style.width = 'auto';
                element.style.height = 'auto';
                element.style.left = Math.random() * 100 + '%';
                element.style.animationDuration = (Math.random() * 15 + 10) + 's';
                element.style.animationDelay = Math.random() * 15 + 's';
                container.appendChild(element);
            }
        }
        
        // Initialize animations
        createParticles();
        addFloatingNumbers();
        
        // Smooth scroll for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });
        
        // Add intersection observer for fade-in effect on cards
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);
        
        document.querySelectorAll('.card').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(30px)';
            card.style.transition = 'all 0.6s ease-out';
            observer.observe(card);
        });
    </script>
</body>
</html>
