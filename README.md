<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Atharv | Engineer & Builder</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        :root {
            --bg: #03060c;
            --card: #080d16;
            --border: #172333;
            --blue: #38bdf8;
            --cyan: #00e5ff;
            --purple: #9b6cff;
            --text: #f5f7fa;
            --muted: #8b96a8;
        }

        body {
            background: var(--bg);
            color: var(--text);
            font-family: Arial, Helvetica, sans-serif;
            overflow-x: hidden;
        }

        body::before {
            content: "";
            position: fixed;
            width: 500px;
            height: 500px;
            background: #006eff;
            filter: blur(180px);
            opacity: 0.08;
            top: 20%;
            left: -200px;
            pointer-events: none;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        /* NAVBAR */

        nav {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 70px;
            padding: 0 5%;
            display: flex;
            align-items: center;
            justify-content: space-between;
            background: rgba(3, 6, 12, 0.75);
            backdrop-filter: blur(18px);
            border-bottom: 1px solid rgba(255,255,255,0.05);
            z-index: 1000;
        }

        .logo {
            font-size: 22px;
            font-weight: bold;
            letter-spacing: 7px;
        }

        .logo span {
            color: var(--blue);
        }

        .nav-links {
            display: flex;
            gap: 30px;
            list-style: none;
        }

        .nav-links a {
            color: #aeb7c5;
            font-size: 14px;
            transition: 0.3s;
        }

        .nav-links a:hover {
            color: white;
        }

        .nav-button {
            border: 1px solid var(--blue);
            padding: 11px 20px;
            border-radius: 30px;
            color: var(--blue);
            box-shadow: 0 0 15px rgba(56,189,248,0.15);
            transition: 0.3s;
        }

        .nav-button:hover {
            background: var(--blue);
            color: #001018;
            box-shadow: 0 0 30px rgba(56,189,248,0.5);
        }

        /* HERO */

        .hero {
            min-height: 100vh;
            padding: 120px 6% 50px;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
        }

        .hero::after {
            content: "";
            position: absolute;
            inset: 0;
            background:
                radial-gradient(circle at 75% 50%, rgba(40,130,255,0.18), transparent 35%),
                linear-gradient(90deg, #03060c 10%, transparent 65%);
            pointer-events: none;
        }

        .hero-content {
            width: 55%;
            position: relative;
            z-index: 2;
        }

        .eyebrow {
            color: var(--blue);
            font-size: 12px;
            letter-spacing: 5px;
            font-weight: bold;
            margin-bottom: 20px;
        }

        .hero h1 {
            font-size: clamp(45px, 6vw, 78px);
            line-height: 1.05;
            margin-bottom: 25px;
        }

        .gradient-text {
            background: linear-gradient(90deg, #fff, #4cc9ff, #9270ff);
            -webkit-background-clip: text;
            color: transparent;
        }

        .hero-description {
            color: var(--muted);
            max-width: 600px;
            font-size: 17px;
            line-height: 1.8;
        }

        .hero-buttons {
            display: flex;
            gap: 15px;
            margin-top: 35px;
        }

        .primary-btn,
        .secondary-btn {
            padding: 14px 24px;
            border-radius: 7px;
            font-size: 14px;
            transition: 0.3s;
        }

        .primary-btn {
            color: #001018;
            background: linear-gradient(100deg, #dffaff, var(--blue));
            box-shadow: 0 0 25px rgba(56,189,248,0.3);
        }

        .primary-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 0 40px rgba(56,189,248,0.6);
        }

        .secondary-btn {
            border: 1px solid #28506a;
            color: #d8e4ee;
        }

        .secondary-btn:hover {
            border-color: var(--blue);
            color: var(--blue);
        }

        .socials {
            display: flex;
            gap: 20px;
            margin-top: 30px;
        }

        .socials a {
            width: 35px;
            height: 35px;
            border: 1px solid #26384c;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #9aa8ba;
            transition: 0.3s;
        }

        .socials a:hover {
            color: var(--blue);
            border-color: var(--blue);
            box-shadow: 0 0 15px rgba(56,189,248,0.4);
        }

        /* SPACE IMAGE */

        .space {
            position: absolute;
            right: -5%;
            top: 12%;
            width: 60%;
            height: 80%;
            background:
                radial-gradient(circle at 50% 75%, #1c5d9c 0%, #07152a 25%, transparent 55%),
                radial-gradient(circle at 70% 25%, #7770ff 0%, transparent 15%),
                linear-gradient(120deg, transparent 30%, rgba(0,180,255,0.1));
            border-radius: 50%;
            opacity: 0.9;
        }

        .space::before {
            content: "";
            position: absolute;
            width: 100%;
            height: 50%;
            bottom: 0;
            border-radius: 50% 50% 0 0;
            background:
                radial-gradient(circle, rgba(255,255,255,0.8) 1px, transparent 1px);
            background-size: 45px 45px;
            opacity: 0.5;
            transform: perspective(400px) rotateX(55deg);
        }

        .astronaut {
            position: absolute;
            right: 20%;
            top: 25%;
            font-size: 120px;
            filter: drop-shadow(0 0 30px rgba(80,180,255,0.5));
            animation: float 5s ease-in-out infinite;
        }

        @keyframes float {
            0%,100% {
                transform: translateY(0);
            }

            50% {
                transform: translateY(-15px);
            }
        }

        /* STATS */

        .stats {
            display: grid;
            grid-template-columns: repeat(4,1fr);
            border-top: 1px solid var(--border);
            border-bottom: 1px solid var(--border);
            padding: 25px 6%;
            background: #040811;
        }

        .stat {
            padding: 10px 30px;
            border-right: 1px solid var(--border);
        }

        .stat:last-child {
            border: none;
        }

        .stat-number {
            font-size: 25px;
            font-weight: bold;
            color: var(--blue);
        }

        .stat-title {
            font-size: 13px;
            color: white;
            margin-top: 4px;
        }

        .stat-description {
            color: var(--muted);
            font-size: 12px;
        }

        /* GENERAL */

        section {
            padding: 100px 6%;
        }

        .section-label {
            color: var(--blue);
            font-size: 11px;
            letter-spacing: 4px;
            font-weight: bold;
            margin-bottom: 12px;
        }

        .section-title {
            font-size: 38px;
            margin-bottom: 20px;
        }

        .section-title span {
            color: var(--blue);
        }

        /* ABOUT */

        .about-grid {
            display: grid;
            grid-template-columns: 1.5fr 1fr;
            gap: 60px;
        }

        .about-text {
            color: var(--muted);
            font-size: 16px;
            line-height: 1.9;
        }

        .about-card {
            background: linear-gradient(145deg,#09111d,#050912);
            border: 1px solid var(--border);
            border-radius: 15px;
            padding: 30px;
        }

        .timeline {
            position: relative;
            padding-left: 25px;
            border-left: 1px solid #315271;
        }

        .timeline-item {
            margin-bottom: 28px;
            position: relative;
        }

        .timeline-item::before {
            content: "";
            position: absolute;
            left: -31px;
            top: 5px;
            width: 10px;
            height: 10px;
            background: var(--blue);
            border-radius: 50%;
            box-shadow: 0 0 12px var(--blue);
        }

        .timeline-year {
            color: var(--blue);
            font-size: 13px;
            font-weight: bold;
        }

        .timeline-item p {
            color: var(--muted);
            font-size: 13px;
            margin-top: 5px;
        }

        /* SKILLS */

        .skills-section {
            border-top: 1px solid var(--border);
            border-bottom: 1px solid var(--border);
        }

        .skills-grid {
            display: grid;
            grid-template-columns: 1.1fr 1fr;
            gap: 70px;
        }

        .skill-list {
            display: grid;
            grid-template-columns: repeat(2,1fr);
            gap: 10px;
        }

        .skill {
            padding: 18px;
            background: #080e18;
            border: 1px solid var(--border);
            border-radius: 7px;
            transition: 0.3s;
        }

        .skill:hover {
            border-color: var(--blue);
            transform: translateY(-3px);
        }

        .skill-name {
            font-size: 14px;
        }

        .exploring {
            border-left: 1px solid #294c68;
            padding-left: 35px;
        }

        .exploring li {
            color: var(--muted);
            margin: 13px 0;
            font-size: 14px;
        }

        .exploring li::marker {
            color: var(--blue);
        }

        /* PROJECTS */

        .projects-header {
            display: flex;
            justify-content: space-between;
            align-items: end;
            margin-bottom: 35px;
        }

        .projects {
            display: grid;
            grid-template-columns: repeat(4,1fr);
            gap: 18px;
        }

        .project {
            min-height: 300px;
            border: 1px solid var(--border);
            border-radius: 10px;
            overflow: hidden;
            background: #080e17;
            transition: 0.4s;
        }

        .project:hover {
            transform: translateY(-8px);
            border-color: var(--blue);
            box-shadow: 0 10px 40px rgba(0,150,255,0.12);
        }

        .project-image {
            height: 145px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 55px;
            background:
                radial-gradient(circle, rgba(50,170,255,0.3), transparent 50%),
                #050a12;
        }

        .project-content {
            padding: 20px;
        }

        .project h3 {
            margin-bottom: 8px;
        }

        .project p {
            color: var(--muted);
            font-size: 13px;
            line-height: 1.6;
        }

        .tags {
            margin-top: 15px;
        }

        .tag {
            display: inline-block;
            padding: 4px 9px;
            margin-right: 4px;
            margin-bottom: 4px;
            border-radius: 20px;
            background: #101c2b;
            border: 1px solid #20364c;
            color: #8fb5d0;
            font-size: 10px;
        }

        /* QUOTE */

        .quote {
            text-align: center;
            padding: 80px 15%;
            border-top: 1px solid var(--border);
        }

        .quote p {
            font-size: 28px;
            font-style: italic;
            color: #dce5ef;
        }

        .quote span {
            display: block;
            color: var(--blue);
            font-size: 12px;
            margin-top: 20px;
            letter-spacing: 3px;
        }

        /* CONTACT */

        .contact {
            text-align: center;
            background:
                radial-gradient(circle at center, rgba(0,120,255,0.12), transparent 45%);
        }

        .contact h2 {
            font-size: 45px;
            margin-bottom: 15px;
        }

        .contact p {
            color: var(--muted);
            margin-bottom: 30px;
        }

        /* FOOTER */

        footer {
            padding: 25px 6%;
            border-top: 1px solid var(--border);
            display: flex;
            justify-content: space-between;
            color: #687386;
            font-size: 12px;
        }

        /* ANIMATION */

        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: 0.8s;
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* MOBILE */

        @media(max-width: 900px) {

            .nav-links {
                display: none;
            }

            .hero-content {
                width: 100%;
            }

            .space {
                opacity: 0.25;
                width: 100%;
                right: -30%;
            }

            .stats {
                grid-template-columns: repeat(2,1fr);
            }

            .stat {
                margin-bottom: 15px;
            }

            .about-grid,
            .skills-grid {
                grid-template-columns: 1fr;
            }

            .projects {
                grid-template-columns: repeat(2,1fr);
            }
        }

        @media(max-width: 600px) {

            .logo {
                font-size: 18px;
            }

            .nav-button {
                display: none;
            }

            section {
                padding: 70px 6%;
            }

            .hero {
                padding-top: 110px;
            }

            .hero h1 {
                font-size: 46px;
            }

            .hero-buttons {
                flex-direction: column;
            }

            .stats {
                grid-template-columns: 1fr 1fr;
            }

            .stat {
                padding: 10px;
            }

            .projects {
                grid-template-columns: 1fr;
            }

            .skill-list {
                grid-template-columns: 1fr;
            }

            .quote {
                padding: 60px 8%;
            }

            .quote p {
                font-size: 21px;
            }

            .contact h2 {
                font-size: 34px;
            }

            footer {
                flex-direction: column;
                gap: 10px;
                text-align: center;
            }
        }
    </style>
</head>


<body>

    <!-- NAVBAR -->

    <nav>

        <div class="logo">
            A<span>THARV</span>
        </div>

        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#skills">Skills</a></li>
            <li><a href="#projects">Projects</a></li>
            <li><a href="#goals">Goals</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>

        <a href="#contact" class="nav-button">
            Let's Connect →
        </a>

    </nav>


    <!-- HERO -->

    <section class="hero" id="home">

        <div class="hero-content">

            <div class="eyebrow">
                ENGINEER × BUILDER × PROBLEM SOLVER
            </div>

            <h1>
                Turning Ideas into
                <br>
                <span class="gradient-text">
                    Real-World Impact.
                </span>
            </h1>

            <p class="hero-description">
                I'm Atharv — a Computer Science engineering student driven
                by curiosity, technology and the desire to understand how
                things actually work.
                I build, experiment and explore at the intersection of
                AI, robotics, physics and engineering.
            </p>

            <div class="hero-buttons">

                <a href="#projects" class="primary-btn">
                    View My Work →
                </a>

                <a href="#" class="secondary-btn">
                    Download Resume ↓
                </a>

            </div>

            <div class="socials">

                <a href="#">GH</a>
                <a href="#">in</a>
                <a href="#">✉</a>
                <a href="#">◎</a>

            </div>

        </div>


        <div class="space">

            <div class="astronaut">
                👨‍🚀
            </div>

        </div>

    </section>


    <!-- STATS -->

    <div class="stats">

        <div class="stat">

            <div class="stat-number">CSE</div>
            <div class="stat-title">Engineering Student</div>
            <div class="stat-description">VIT-AP</div>

        </div>

        <div class="stat">

            <div class="stat-number">1000+</div>
            <div class="stat-title">Hours of Learning</div>
            <div class="stat-description">Coding & Engineering</div>

        </div>

        <div class="stat">

            <div class="stat-number">10+</div>
            <div class="stat-title">Ideas & Projects</div>
            <div class="stat-description">Exploring & Building</div>

        </div>

        <div class="stat">

            <div class="stat-number">∞</div>
            <div class="stat-title">Curiosity</div>
            <div class="stat-description">Always What's Next</div>

        </div>

    </div>


    <!-- ABOUT -->

    <section id="about" class="reveal">

        <div class="about-grid">

            <div>

                <div class="section-label">
                    ABOUT ME
                </div>

                <h2 class="section-title">
                    More Than a <span>Student.</span>
                    <br>
                    A Builder of <span>Possibilities.</span>
                </h2>

                <p class="about-text">

                    I'm Atharv — a Computer Science Engineering student
                    with a strong interest in technology and science.

                    <br><br>

                    I'm currently strengthening my foundations in C++,
                    Data Structures & Algorithms and Python while exploring
                    artificial intelligence, robotics and computer hardware.

                    <br><br>

                    My curiosity goes beyond software. I want to understand
                    the engineering behind robots, spacecraft, CPUs,
                    autonomous systems and complex machines.

                    <br><br>

                    Long term, I'm particularly interested in quantum
                    physics, advanced mathematics and the technologies that
                    could shape the next generation of engineering.

                </p>

            </div>


            <div class="about-card">

                <div class="section-label">
                    MY JOURNEY
                </div>

                <div class="timeline">

                    <div class="timeline-item">

                        <div class="timeline-year">
                            2023
                        </div>

                        <p>
                            Completed Class 12 and began exploring
                            different paths in technology.
                        </p>

                    </div>


                    <div class="timeline-item">

                        <div class="timeline-year">
                            2025
                        </div>

                        <p>
                            Started Computer Science Engineering
                            at VIT-AP.
                        </p>

                    </div>


                    <div class="timeline-item">

                        <div class="timeline-year">
                            2025+
                        </div>

                        <p>
                            Building projects, learning C++,
                            DSA, AI and robotics.
                        </p>

                    </div>


                    <div class="timeline-item">

                        <div class="timeline-year">
                            FUTURE
                        </div>

                        <p>
                            Work on advanced technology,
                            robotics, space systems and
                            quantum science.
                        </p>

                    </div>

                </div>

            </div>

        </div>

    </section>


    <!-- SKILLS -->

    <section id="skills" class="skills-section reveal">

        <div class="skills-grid">

            <div>

                <div class="section-label">
                    SKILLS & INTERESTS
                </div>

                <h2 class="section-title">
                    Tools I use.
                    <span>Technologies I love.</span>
                </h2>

                <div class="skill-list">

                    <div class="skill">
                        C++ / Programming
                    </div>

                    <div class="skill">
                        Python
                    </div>

                    <div class="skill">
                        Data Structures
                    </div>

                    <div class="skill">
                        Algorithms
                    </div>

                    <div class="skill">
                        AI / ML
                    </div>

                    <div class="skill">
                        Robotics
                    </div>

                    <div class="skill">
                        Computer Vision
                    </div>

                    <div class="skill">
                        Electronics
                    </div>

                    <div class="skill">
                        IoT
                    </div>

                    <div class="skill">
                        Mathematics
                    </div>

                    <div class="skill">
                        Quantum Physics
                    </div>

                    <div class="skill">
                        Space Technology
                    </div>

                </div>

            </div>


            <div class="exploring" id="goals">

                <div class="section-label">
                    CURRENTLY EXPLORING
                </div>

                <ul>

                    <li>
                        Advanced DSA & System Design
                    </li>

                    <li>
                        Robotics & Autonomous Systems
                    </li>

                    <li>
                        AI Agents & LLMs
                    </li>

                    <li>
                        Computer Hardware — CPUs, GPUs & MOSFETs
                    </li>

                    <li>
                        Space & Rocket Engineering
                    </li>

                    <li>
                        Quantum Computing
                    </li>

                    <li>
                        Real-world Product Development
                    </li>

                </ul>

            </div>

        </div>

    </section>


    <!-- PROJECTS -->

    <section id="projects" class="reveal">

        <div class="projects-header">

            <div>

                <div class="section-label">
                    FEATURED PROJECTS
                </div>

                <h2 class="section-title">
                    Ideas I'm <span>Building.</span>
                </h2>

            </div>

            <a href="#" class="secondary-btn">
                View All Projects →
            </a>

        </div>


        <div class="projects">


            <!-- PROJECT 1 -->

            <div class="project">

                <div class="project-image">
                    🤖
                </div>

                <div class="project-content">

                    <h3>RoboDog</h3>

                    <p>
                        An autonomous robotic platform concept designed
                        for real-world assistance, environmental interaction
                        and intelligent navigation.
                    </p>

                    <div class="tags">
                        <span class="tag">Robotics</span>
                        <span class="tag">AI</span>
                        <span class="tag">Hardware</span>
                    </div>

                </div>

            </div>


            <!-- PROJECT 2 -->

            <div class="project">

                <div class="project-image">
                    🎧
                </div>

                <div class="project-content">

                    <h3>JARVIS</h3>

                    <p>
                        A wearable AI assistant concept focused on
                        personalized interaction, intelligent assistance
                        and seamless human-computer interaction.
                    </p>

                    <div class="tags">
                        <span class="tag">AI</span>
                        <span class="tag">IoT</span>
                        <span class="tag">Voice</span>
                    </div>

                </div>

            </div>


            <!-- PROJECT 3 -->

            <div class="project">

                <div class="project-image">
                    🌐
                </div>

                <div class="project-content">

                    <h3>ATECH</h3>

                    <p>
                        A technology initiative exploring intelligent
                        systems, futuristic products and engineering
                        solutions for real-world problems.
                    </p>

                    <div class="tags">
                        <span class="tag">Innovation</span>
                        <span class="tag">AI</span>
                        <span class="tag">Systems</span>
                    </div>

                </div>

            </div>


            <!-- PROJECT 4 -->

            <div class="project">

                <div class="project-image">
                    🚀
                </div>

                <div class="project-content">

                    <h3>Engineering Lab</h3>

                    <p>
                        Exploring the systems behind rockets, computers,
                        robots, electronics and other complex engineering
                        machines.
                    </p>

                    <div class="tags">
                        <span class="tag">Physics</span>
                        <span class="tag">Hardware</span>
                        <span class="tag">Research</span>
                    </div>

                </div>

            </div>

        </div>

    </section>


    <!-- QUOTE -->

    <div class="quote reveal">

        <p>
            "The goal isn't just to learn technology.
            It's to understand it well enough to build something new."
        </p>

        <span>
            — ATHARV
        </span>

    </div>


    <!-- CONTACT -->

    <section id="contact" class="contact reveal">

        <div class="section-label">
            LET'S BUILD
        </div>

        <h2>
            Let's Build a
            <span class="gradient-text">
                Better Tomorrow.
            </span>
        </h2>

        <p>
            Open to interesting projects, collaborations
            and opportunities.
        </p>

        <a href="mailto:your@email.com" class="primary-btn">
            Get In Touch →
        </a>

    </section>


    <!-- FOOTER -->

    <footer>

        <div>
            © 2026 Atharv
        </div>

        <div>
            Engineer × Builder × Learner
        </div>

    </footer>


    <!-- JAVASCRIPT -->

    <script>

        const sections = document.querySelectorAll(".reveal");

        function revealSections() {

            sections.forEach(section => {

                const position =
                    section.getBoundingClientRect().top;

                if (position < window.innerHeight - 100) {
                    section.classList.add("active");
                }

            });

        }

        window.addEventListener("scroll", revealSections);

        revealSections();

    </script>

</body>
</html>
