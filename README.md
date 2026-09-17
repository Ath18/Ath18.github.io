<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Atharv // Digital Lab</title>

    <style>

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            background: #050505;
            color: white;
            font-family: Arial, sans-serif;
            overflow-x: hidden;
        }

        /* BACKGROUND */

        body::before {
            content: "";
            position: fixed;
            inset: 0;
            background-image:
                linear-gradient(rgba(0,255,200,.035) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0,255,200,.035) 1px, transparent 1px);
            background-size: 50px 50px;
            pointer-events: none;
            z-index: -2;
        }

        .glow {
            position: fixed;
            width: 400px;
            height: 400px;
            border-radius: 50%;
            background: #00ffc3;
            filter: blur(180px);
            opacity: .08;
            top: 20%;
            left: 40%;
            pointer-events: none;
            z-index: -1;
        }

        /* NAVBAR */

        nav {
            height: 75px;
            width: 100%;
            position: fixed;
            top: 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 7%;
            background: rgba(5,5,5,.7);
            backdrop-filter: blur(15px);
            border-bottom: 1px solid #151515;
            z-index: 100;
        }

        .logo {
            font-size: 22px;
            font-weight: bold;
            letter-spacing: 3px;
        }

        .logo span {
            color: #00ffc3;
        }

        nav ul {
            display: flex;
            gap: 30px;
            list-style: none;
        }

        nav a {
            color: #888;
            text-decoration: none;
            font-size: 13px;
            transition: .3s;
        }

        nav a:hover {
            color: #00ffc3;
        }

        .status {
            font-size: 11px;
            color: #00ffc3;
            border: 1px solid #00ffc355;
            padding: 8px 13px;
            border-radius: 20px;
        }

        .dot {
            display: inline-block;
            width: 7px;
            height: 7px;
            background: #00ffc3;
            border-radius: 50%;
            margin-right: 6px;
            box-shadow: 0 0 10px #00ffc3;
        }

        /* HERO */

        .hero {
            min-height: 100vh;
            padding: 150px 8% 80px;
            display: flex;
            align-items: center;
        }

        .hero-left {
            width: 65%;
        }

        .terminal {
            color: #00ffc3;
            font-family: monospace;
            font-size: 14px;
            margin-bottom: 20px;
        }

        .terminal span {
            color: #555;
        }

        h1 {
            font-size: clamp(55px, 9vw, 120px);
            line-height: .9;
            letter-spacing: -5px;
        }

        h1 .green {
            color: #00ffc3;
            text-shadow: 0 0 35px rgba(0,255,195,.25);
        }

        .hero-description {
            max-width: 650px;
            color: #777;
            margin-top: 30px;
            font-size: 17px;
            line-height: 1.8;
        }

        .buttons {
            display: flex;
            gap: 15px;
            margin-top: 35px;
        }

        .btn {
            padding: 14px 24px;
            border-radius: 4px;
            text-decoration: none;
            font-size: 13px;
            transition: .3s;
        }

        .primary {
            background: #00ffc3;
            color: #00110d;
            font-weight: bold;
            box-shadow: 0 0 25px rgba(0,255,195,.2);
        }

        .primary:hover {
            transform: translateY(-4px);
            box-shadow: 0 0 40px rgba(0,255,195,.5);
        }

        .outline {
            border: 1px solid #333;
            color: #aaa;
        }

        .outline:hover {
            border-color: #00ffc3;
            color: #00ffc3;
        }

        /* RIGHT SIDE */

        .hero-right {
            width: 35%;
            display: flex;
            justify-content: center;
        }

        .orb {
            width: 300px;
            height: 300px;
            border: 1px solid #00ffc344;
            border-radius: 50%;
            position: relative;
            animation: rotate 15s linear infinite;
        }

        .orb::before {
            content: "";
            position: absolute;
            inset: 35px;
            border: 1px solid #00ffc333;
            border-radius: 50%;
        }

        .orb::after {
            content: "A";
            position: absolute;
            inset: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 130px;
            font-weight: bold;
            color: #00ffc3;
            text-shadow: 0 0 50px #00ffc3;
            animation: counter 15s linear infinite;
        }

        .orb-dot {
            position: absolute;
            width: 15px;
            height: 15px;
            background: #00ffc3;
            border-radius: 50%;
            top: 10px;
            left: 50%;
            box-shadow: 0 0 30px #00ffc3;
        }

        @keyframes rotate {
            from {
                transform: rotate(0);
            }
            to {
                transform: rotate(360deg);
            }
        }

        @keyframes counter {
            from {
                transform: rotate(0);
            }
            to {
                transform: rotate(-360deg);
            }
        }

        /* STATS */

        .stats {
            border-top: 1px solid #181818;
            border-bottom: 1px solid #181818;
            display: grid;
            grid-template-columns: repeat(4,1fr);
        }

        .stat {
            padding: 30px 7%;
            border-right: 1px solid #181818;
        }

        .stat-number {
            font-size: 30px;
            color: #00ffc3;
        }

        .stat p {
            color: #666;
            margin-top: 5px;
            font-size: 12px;
        }

        /* SECTIONS */

        section {
            padding: 120px 8%;
        }

        .label {
            color: #00ffc3;
            font-family: monospace;
            font-size: 12px;
            margin-bottom: 15px;
        }

        .title {
            font-size: 45px;
            margin-bottom: 50px;
        }

        .title span {
            color: #00ffc3;
        }

        /* ABOUT */

        .about {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 80px;
        }

        .about p {
            color: #777;
            line-height: 2;
            font-size: 16px;
        }

        .code-box {
            background: #090909;
            border: 1px solid #202020;
            border-radius: 8px;
            padding: 25px;
            font-family: monospace;
            color: #777;
            box-shadow: 0 0 40px rgba(0,255,195,.04);
        }

        .code-box .green-text {
            color: #00ffc3;
        }

        .code-box .purple {
            color: #b47cff;
        }

        .code-box .yellow {
            color: #ffd166;
        }

        /* SKILLS */

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }

        .skill {
            padding: 15px 22px;
            border: 1px solid #222;
            background: #090909;
            color: #999;
            transition: .3s;
        }

        .skill:hover {
            border-color: #00ffc3;
            color: #00ffc3;
            transform: translateY(-4px);
            box-shadow: 0 10px 30px rgba(0,255,195,.08);
        }

        /* PROJECTS */

        .projects {
            display: grid;
            grid-template-columns: repeat(3,1fr);
            gap: 20px;
        }

        .project {
            min-height: 320px;
            padding: 30px;
            border: 1px solid #1d1d1d;
            background:
                linear-gradient(145deg,#0c0c0c,#070707);
            position: relative;
            overflow: hidden;
            transition: .4s;
        }

        .project:hover {
            transform: translateY(-8px);
            border-color: #00ffc355;
        }

        .project-number {
            font-family: monospace;
            color: #333;
            font-size: 13px;
        }

        .project-icon {
            font-size: 50px;
            margin: 35px 0 20px;
        }

        .project h3 {
            font-size: 22px;
            margin-bottom: 12px;
        }

        .project p {
            color: #666;
            font-size: 13px;
            line-height: 1.7;
        }

        .project-tags {
            position: absolute;
            bottom: 25px;
            left: 30px;
            color: #00ffc3;
            font-size: 10px;
            font-family: monospace;
        }

        /* GOALS */

        .goals {
            border-top: 1px solid #181818;
            border-bottom: 1px solid #181818;
        }

        .goal-grid {
            display: grid;
            grid-template-columns: repeat(3,1fr);
            gap: 20px;
        }

        .goal {
            padding: 35px;
            background: #080808;
            border-left: 2px solid #00ffc3;
        }

        .goal h3 {
            margin-bottom: 15px;
        }

        .goal p {
            color: #666;
            line-height: 1.7;
            font-size: 14px;
        }

        /* CONTACT */

        .contact {
            min-height: 70vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
        }

        .contact h2 {
            font-size: clamp(45px,7vw,90px);
            line-height: 1;
        }

        .contact h2 span {
            color: #00ffc3;
        }

        .contact p {
            color: #666;
            margin: 25px 0;
        }

        /* FOOTER */

        footer {
            border-top: 1px solid #181818;
            padding: 25px 8%;
            display: flex;
            justify-content: space-between;
            color: #444;
            font-size: 11px;
            font-family: monospace;
        }

        /* MOBILE */

        @media(max-width:900px) {

            nav ul {
                display: none;
            }

            .status {
                display: none;
            }

            .hero {
                display: block;
                padding-top: 140px;
            }

            .hero-left {
                width: 100%;
            }

            .hero-right {
                width: 100%;
                margin-top: 70px;
            }

            .orb {
                width: 220px;
                height: 220px;
            }

            .orb::after {
                font-size: 90px;
            }

            .stats {
                grid-template-columns: repeat(2,1fr);
            }

            .about {
                grid-template-columns: 1fr;
            }

            .projects {
                grid-template-columns: 1fr;
            }

            .goal-grid {
                grid-template-columns: 1fr;
            }
        }

        @media(max-width:500px) {

            h1 {
                font-size: 55px;
            }

            .stats {
                grid-template-columns: 1fr;
            }

            .buttons {
                flex-direction: column;
            }

            .btn {
                text-align: center;
            }

            footer {
                flex-direction: column;
                gap: 10px;
            }
        }

    </style>
</head>


<body>

    <div class="glow"></div>


    <!-- NAVIGATION -->

    <nav>

        <div class="logo">
            ATHARV<span>.</span>
        </div>

        <ul>
            <li><a href="#about">ABOUT</a></li>
            <li><a href="#skills">STACK</a></li>
            <li><a href="#projects">PROJECTS</a></li>
            <li><a href="#goals">VISION</a></li>
        </ul>

        <div class="status">
            <span class="dot"></span>
            BUILDING
        </div>

    </nav>


    <!-- HERO -->

    <section class="hero">

        <div class="hero-left">

            <div class="terminal">
                atharv@digital-lab:~$ whoami
            </div>

            <h1>
                BUILD.
                <br>
                <span class="green">BREAK.</span>
                <br>
                REBUILD.
            </h1>

            <p class="hero-description">

                Computer Science student exploring the intersection of
                software, artificial intelligence, robotics, physics and
                real-world engineering.

                <br><br>

                I don't just want to use technology.
                I want to understand what is happening underneath it —
                and eventually build systems of my own.

            </p>

            <div class="buttons">

                <a href="#projects" class="btn primary">
                    ENTER MY LAB →
                </a>

                <a href="#contact" class="btn outline">
                    CONTACT
                </a>

            </div>

        </div>


        <div class="hero-right">

            <div class="orb">

                <div class="orb-dot"></div>

            </div>

        </div>

    </section>


    <!-- STATS -->

    <div class="stats">

        <div class="stat">
            <div class="stat-number">CSE</div>
            <p>ENGINEERING</p>
        </div>

        <div class="stat">
            <div class="stat-number">C++</div>
            <p>PRIMARY LANGUAGE</p>
        </div>

        <div class="stat">
            <div class="stat-number">AI</div>
            <p>EXPLORING</p>
        </div>

        <div class="stat">
            <div class="stat-number">∞</div>
            <p>CURIOSITY</p>
        </div>

    </div>


    <!-- ABOUT -->

    <section id="about">

        <div class="label">
            01 // ABOUT
        </div>

        <h2 class="title">
            The person behind
            <span>the code.</span>
        </h2>

        <div class="about">

            <div>

                <p>

                    I'm Atharv, a Computer Science Engineering student
                    interested in understanding technology from the
                    software layer all the way down to the physical world.

                    <br><br>

                    My current journey revolves around C++, Data Structures
                    & Algorithms, Python, AI/ML and robotics.

                    <br><br>

                    But the curiosity doesn't stop at software.

                    CPUs, GPUs, MOSFETs, autonomous robots, rockets,
                    spacecraft and quantum systems are all things I want
                    to understand.

                    <br><br>

                    The long-term goal is simple:

                    <strong style="color:white">
                        learn deeply → build aggressively → solve real problems.
                    </strong>

                </p>

            </div>


            <div class="code-box">

                <p>
                    <span class="purple">class</span>
                    <span class="yellow">Atharv</span>
                    {
                </p>

                <br>

                <p>
                    &nbsp;&nbsp;
                    <span class="green-text">interest</span>
                    = [
                </p>

                <p>
                    &nbsp;&nbsp;&nbsp;&nbsp;"AI",
                </p>

                <p>
                    &nbsp;&nbsp;&nbsp;&nbsp;"Robotics",
                </p>

                <p>
                    &nbsp;&nbsp;&nbsp;&nbsp;"Physics",
                </p>

                <p>
                    &nbsp;&nbsp;&nbsp;&nbsp;"Quantum",
                </p>

                <p>
                    &nbsp;&nbsp;&nbsp;&nbsp;"Space"
                </p>

                <p>
                    &nbsp;&nbsp;];
                </p>

                <br>

                <p>
                    &nbsp;&nbsp;
                    <span class="green-text">mission</span>
                    =
                    "Build something meaningful";
                </p>

                <br>

                <p>
                    &nbsp;&nbsp;
                    <span class="green-text">status</span>
                    = "Learning...";
                </p>

                <p>
                    }
                </p>

            </div>

        </div>

    </section>


    <!-- SKILLS -->

    <section id="skills">

        <div class="label">
            02 // TECH STACK
        </div>

        <h2 class="title">
            Things I'm
            <span>learning.</span>
        </h2>

        <div class="skills">

            <div class="skill">C++</div>
            <div class="skill">Python</div>
            <div class="skill">DSA</div>
            <div class="skill">Algorithms</div>
            <div class="skill">AI / ML</div>
            <div class="skill">Computer Vision</div>
            <div class="skill">Robotics</div>
            <div class="skill">IoT</div>
            <div class="skill">Electronics</div>
            <div class="skill">Mathematics</div>
            <div class="skill">Quantum Physics</div>
            <div class="skill">Space Technology</div>

        </div>

    </section>


    <!-- PROJECTS -->

    <section id="projects">

        <div class="label">
            03 // PROJECTS
        </div>

        <h2 class="title">
            Ideas becoming
            <span>systems.</span>
        </h2>

        <div class="projects">


            <div class="project">

                <div class="project-number">
                    PROJECT_001
                </div>

                <div class="project-icon">
                    🤖
                </div>

                <h3>RoboDog</h3>

                <p>
                    Autonomous robotic platform exploring navigation,
                    perception, interaction and real-world assistance.
                </p>

                <div class="project-tags">
                    ROBOTICS // AI // HARDWARE
                </div>

            </div>


            <div class="project">

                <div class="project-number">
                    PROJECT_002
                </div>

                <div class="project-icon">
                    🎧
                </div>

                <h3>JARVIS</h3>

                <p>
                    A wearable AI assistant concept focused on natural
                    interaction, voice intelligence and personalized
                    assistance.
                </p>

                <div class="project-tags">
                    AI // IOT // VOICE
                </div>

            </div>


            <div class="project">

                <div class="project-number">
                    PROJECT_003
                </div>

                <div class="project-icon">
                    ⚡
                </div>

                <h3>ATECH</h3>

                <p>
                    A technology initiative exploring intelligent products,
                    engineering systems and futuristic applications.
                </p>

                <div class="project-tags">
                    SYSTEMS // AI // INNOVATION
                </div>

            </div>


        </div>

    </section>


    <!-- VISION -->

    <section id="goals" class="goals">

        <div class="label">
            04 // VISION
        </div>

        <h2 class="title">
            What's
            <span>next?</span>
        </h2>

        <div class="goal-grid">

            <div class="goal">

                <h3>ROBOTICS</h3>

                <p>
                    Build physical machines instead of only writing
                    simulations. Learn sensors, control systems,
                    embedded systems and autonomous navigation.
                </p>

            </div>


            <div class="goal">

                <h3>AI</h3>

                <p>
                    Move from using AI tools toward understanding and
                    building intelligent systems, agents and machine
                    learning models.
                </p>

            </div>


            <div class="goal">

                <h3>QUANTUM</h3>

                <p>
                    Develop the mathematics and physics required to
                    understand quantum mechanics and eventually
                    quantum computing.
                </p>

            </div>

        </div>

    </section>


    <!-- CONTACT -->

    <section id="contact" class="contact">

        <div>

            <div class="label">
                05 // CONNECTION
            </div>

            <h2>
                LET'S BUILD
                <br>
                <span>SOMETHING.</span>
            </h2>

            <p>
                Open to technology, engineering and interesting projects.
            </p>

            <a href="mailto:your@email.com" class="btn primary">
                SEND MESSAGE →
            </a>

        </div>

    </section>


    <!-- FOOTER -->

    <footer>

        <div>
            ATHARV // DIGITAL LAB
        </div>

        <div>
            © 2026
        </div>

    </footer>


</body>
</html>
