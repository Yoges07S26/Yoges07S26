<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Developer Ecosystem Matrix - Portfolio</title>
    <style>
        :root {
            --bg-color: #16120f;
            --card-bg: rgba(26, 21, 18, 0.88);
            --card-border: #42352e;
            --text-main: #dfd2c6;
            --text-muted: #9e8e82;
            --accent-gold: #cfa86b;
            --shadow-glow: rgba(207, 168, 107, 0.12);
            --hdr-gradient: rgba(18, 15, 13, 0.85);
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(rgba(22, 18, 15, 0.85), rgba(22, 18, 15, 0.92)), 
                        url('https://unsplash.com') no-repeat center center fixed;
            background-size: cover;
            color: var(--text-main);
            margin: 0;
            padding: 40px 20px;
            display: flex;
            justify-content: center;
        }

        .container {
            max-width: 1200px;
            width: 100%;
        }

        /* Header Styles */
        header {
            text-align: center;
            margin-bottom: 40px;
            background: rgba(0, 0, 0, 0.2);
            padding: 30px;
            border-radius: 12px;
            border: 1px solid rgba(207, 168, 107, 0.1);
        }

        .logo-placeholder {
            font-size: 2.2rem;
            font-weight: bold;
            letter-spacing: 3px;
            text-transform: uppercase;
            color: #ffffff;
            display: inline-flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 15px;
        }

        .logo-placeholder span {
            color: var(--accent-gold);
        }

        header p {
            color: var(--text-muted);
            font-size: 1.1rem;
            max-width: 750px;
            margin: 0 auto;
            line-height: 1.6;
        }

        hr {
            border: 0;
            height: 1px;
            background: linear-gradient(to right, transparent, var(--card-border), transparent);
            margin: 40px 0;
        }

        h2 {
            text-align: center;
            font-size: 1.8rem;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            margin-bottom: 30px;
            color: #ffffff;
            text-shadow: 0 2px 4px rgba(0,0,0,0.5);
        }

        /* Featured Projects Grid */
        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 24px;
            margin-bottom: 40px;
        }

        .project-card {
            background: var(--card-bg);
            border: 1px solid var(--card-border);
            border-radius: 8px;
            padding: 24px;
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.5), inset 0 0 20px var(--shadow-glow);
            transition: transform 0.25s ease, border-color 0.25s ease, box-shadow 0.25s ease;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .project-card:hover {
            transform: translateY(-4px);
            border-color: var(--accent-gold);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.6), 0 0 15px rgba(207, 168, 107, 0.2);
        }

        .project-card h3 {
            margin-top: 0;
            font-size: 1.35rem;
            color: var(--accent-gold);
            display: flex;
            align-items: center;
            gap: 10px;
            letter-spacing: 0.5px;
        }

        .project-card p {
            font-size: 0.95rem;
            line-height: 1.6;
            color: var(--text-main);
            margin-bottom: 12px;
        }

        .project-card ul {
            padding-left: 20px;
            margin: 0 0 16px 0;
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        .project-card li {
            margin-bottom: 6px;
            line-height: 1.4;
        }

        .tech-stack {
            margin-top: auto;
            font-size: 0.9rem;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            padding-top: 12px;
            margin-bottom: 12px;
        }

        .tech-stack strong {
            color: var(--text-muted);
        }

        .focus-areas {
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
        }

        .badge {
            background: rgba(207, 168, 107, 0.08);
            border: 1px solid rgba(207, 168, 107, 0.25);
            color: var(--accent-gold);
            padding: 3px 10px;
            border-radius: 4px;
            font-weight: 500;
            font-size: 0.8rem;
            letter-spacing: 0.3px;
        }

        /* Ecosystem Matrix Section */
        .ecosystem-container {
            max-width: 700px;
            margin: 0 auto 40px auto;
        }

        .ecosystem-list {
            list-style: none;
            padding: 0;
            display: flex;
            flex-direction: column;
            gap: 14px;
            background: var(--card-bg);
            border: 1px solid var(--card-border);
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.5);
        }

        .ecosystem-list li {
            font-size: 1rem;
            line-height: 1.5;
            display: flex;
            align-items: baseline;
        }

        .ecosystem-list li strong {
            color: var(--accent-gold);
            min-width: 180px;
            display: inline-block;
            letter-spacing: 0.5px;
        }

        .ecosystem-list li span {
            color: var(--text-main);
        }

        /* Accordion Architecture Sections */
        .architecture-section {
            max-width: 850px;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            gap: 16px;
        }

        details {
            background: var(--card-bg);
            border: 1px solid var(--card-border);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.4);
            transition: border-color 0.2s ease;
        }

        details[open] {
            border-color: var(--accent-gold);
        }

        summary {
            padding: 18px 24px;
            font-weight: 600;
            font-size: 1.05rem;
            cursor: pointer;
            user-select: none;
            background: rgba(255, 255, 255, 0.01);
            outline: none;
            transition: background 0.2s ease, color 0.2s ease;
            display: flex;
            align-items: center;
            gap: 12px;
            letter-spacing: 0.5px;
        }

        summary:hover {
            background: rgba(207, 168, 107, 0.04);
            color: var(--accent-gold);
        }

        /* Smooth reveal layout */
        .details-content {
            padding: 24px;
            border-top: 1px solid var(--card-border);
            background: rgba(0, 0, 0, 0.15);
            font-size: 0.95rem;
            line-height: 1.6;
        }

        .details-content ul {
            margin: 0;
            padding-left: 20px;
        }

        .details-content li {
            margin-bottom: 10px;
        }

        .details-content li:last-child {
            margin-bottom: 0;
        }

        .details-content strong {
            color: var(--accent-gold);
        }

        /* Footer */
        footer {
            text-align: center;
            margin-top: 60px;
            color: var(--text-muted);
            font-size: 0.9rem;
            letter-spacing: 0.5px;
        }
    </style>
</head>
<body>

<div class="container">

    <!-- Header Block -->
    <header>
        <div class="logo-placeholder">▲ vercel</div>
        <p>A comprehensive showcase of foundational software applications, optimized database query models, custom architectural deep dives, and data structures.</p>
    </header>

    <hr>

    <!-- Featured Projects Grid Layout -->
    <h2>🚀 Featured Projects</h2>
    <div class="project-grid">

        <!-- Card 1 -->
        <div class="project-card">
            <div>
                <h3>🧠 ProblemSolving</h3>
                <p>A modular collection of algorithmic computational puzzles and foundational logical program execution flows.</p>
            </div>
            <div>
                <div class="tech-stack"><strong>Technologies:</strong> C, C++, Java, Python</div>
                <div class="focus-areas">
                    <span class="badge">DSA</span>
                    <span class="badge">Algorithms</span>
                    <span class="badge">Logic</span>
                </div>
            </div>
        </div>

        <!-- Card 2 -->
        <div class="project-card">
            <div>
                <h3>🎮 GameDesign</h3>
                <p>Game design architecture experiments focused on core rendering principles, frame execution blocks, and standalone object states.</p>
            </div>
            <div>
                <div class="tech-stack"><strong>Technologies:</strong> Java</div>
                <div class="focus-areas">
                    <span class="badge">Game Dev</span>
                    <span class="badge">Java</span>
                    <span class="badge">Design</span>
                </div>
            </div>
        </div>

        <!-- Card 3 -->
        <div class="project-card">
            <div>
                <h3>🗄️ Basic-Sql</h3>
                <p>Production-safe structured query assets built to investigate index management strategies and entity relationships.</p>
            </div>
            <div>
                <div class="tech-stack"><strong>Technologies:</strong> MySQL</div>
                <div class="focus-areas">
        <!-- Card 8 (HackerEarth) Closing Block Wrapper -->
        </div>
    </div>

    <!-- Developer Ecosystem Matrix Segment -->
    <h2>🛠️ Developer Ecosystem Matrix</h2>
    <div class="ecosystem-container">
        <ul class="ecosystem-list">
            <li><strong>Languages:</strong> <span>C, C++, Java, Python</span></li>
            <li><strong>Databases:</strong> <span>MySQL</span></li>
            <li><strong>DevOps & Workflows:</strong> <span>Git, GitHub, GitHub Actions</span></li>
            <li><strong>Environments:</strong> <span>VS Code, IntelliJ IDEA</span></li>
        </ul>
    </div>

    <!-- System Architecture Accordion Expansion Blocks -->
    <h2>⚙️ System Architecture Deep-Dives</h2>
    <div class="architecture-section">

        <details class="arch-accordion">
            <summary>🔍 System Layout: Criminal Management System</summary>
            <div class="details-content">
                <ul>
                    <li><strong>Structural Framework:</strong> Designed with completely normalized tables ensuring strict relational integrity constraints across active incident tables.</li>
                    <li><strong>Data Integrity:</strong> Engineered parameterized statements throughout execution flows to securely isolate operational inputs from structural query mutations.</li>
                </ul>
            </div>
        </details>

        <details class="arch-accordion">
            <summary>🏋️ Target Module Execution: Fitness Application</summary>
            <div class="details-content">
                <ul>
                    <li><strong>Algorithmic Matrix:</strong> Real-time asynchronous math computations comparing custom biometric metrics against active calorie targets.</li>
                    <li><strong>Session Maintenance:</strong> Implements thread-isolated transactional rules keeping state parameters consistent during sudden disconnects.</li>
                </ul>
            </div>
        </details>

    </div>

    <!-- Global Layout Footer -->
    <footer>
        <p>© 2026 Yoges07S26 • Built with automated vector styling components</p>
    </footer>

</div>

<!-- Interactive Accordion Handler Script -->
<script>
    // Ensures only one deep-dive panel stays expanded at a single time
    const accordions = document.querySelectorAll('.arch-accordion');
    accordions.forEach((acc) => {
        acc.addEventListener('toggle', () => {
            if (acc.open) {
                accordions.forEach((otherAcc) => {
                    if (otherAcc !== acc) {
                        otherAcc.open = false;
                    }
                });
            }
        });
    });
</script>

</body>
</html>
