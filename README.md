<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Anant Yadav | Game Developer</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
  <style>
    :root {
      --bg-hero: radial-gradient(circle at center, #7a0000 0%, #1a0000 70%, #000000 100%);
      --bg-dark: #000000;
      --card-bg: rgba(15, 23, 42, 0.7);
      --accent-cyan: #00f2ff;
      --accent-red: #ff3c3c;
      --text-main: #f8fafc;
      --text-dim: #94a3b8;
    }

    html {
      scroll-behavior: smooth;
      scroll-padding-top: 80px; 
    }

    body {
      margin: 0;
      font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
      background: var(--bg-hero); 
      background-attachment: fixed;
      color: var(--text-main);
    }

    /* Translucent Navigation Bar */
    nav {
      display: flex;
      justify-content: flex-end;
      padding: 20px 10%;
      background: rgba(0, 0, 0, 0.6); 
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      position: sticky;
      top: 0;
      z-index: 1000;
      border-bottom: 1px solid rgba(255, 60, 60, 0.15);
    }

    nav a {
      color: var(--text-dim);
      text-decoration: none;
      margin-left: 30px;
      font-size: 16px;
      transition: 0.3s;
      font-weight: 500;
    }

    nav a:hover { color: var(--accent-cyan); }

    /* Landing Section */
    #home {
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: flex-start;
      padding: 0 10%;
      position: relative;
    }

    .hero-top-nav {
      position: absolute;
      top: 40px;
      left: 10%;
      right: 10%;
      display: flex;
      justify-content: space-between;
      text-transform: uppercase;
      letter-spacing: 2px;
      font-size: 0.9rem;
    }

    .hero-content {
      max-width: 700px;
      z-index: 2;
    }

    h1 {
      font-size: clamp(3rem, 8vw, 5rem);
      margin: 0;
      text-transform: uppercase;
      letter-spacing: 4px;
      line-height: 1;
    }

    .hero-role {
      font-size: 1.5rem;
      color: var(--accent-red);
      font-weight: bold;
      margin: 10px 0 30px;
      letter-spacing: 3px;
      text-transform: uppercase;
    }

    .hero-about {
      font-size: 1.1rem;
      line-height: 1.8;
      color: var(--text-dim);
      margin-bottom: 40px;
    }

    /* Content Layout */
    .container {
      max-width: 1100px;
      margin: 0 auto;
      padding: 60px 20px;
    }

    .section-title {
      font-size: 2.5rem;
      margin-bottom: 30px;
      display: inline-block;
      position: relative;
    }

    .section-title::after {
      content: '';
      display: block;
      width: 60%;
      height: 4px;
      background: var(--accent-cyan);
      margin-top: 10px;
    }

    /* Project Cards */
    .card {
      background: var(--card-bg);
      padding: 25px;
      border-radius: 12px;
      margin-bottom: 30px;
      border: 1px solid rgba(255, 60, 60, 0.1);
      backdrop-filter: blur(4px);
    }

    .priority-tag {
      background: var(--accent-red);
      color: white;
      padding: 4px 12px;
      border-radius: 4px;
      font-size: 0.8rem;
      font-weight: bold;
      text-transform: uppercase;
      margin-bottom: 10px;
      display: inline-block;
    }

    ul { list-style: none; padding: 0; }
    li { margin-bottom: 10px; color: var(--text-dim); display: flex; align-items: flex-start; }
    li::before { content: '▹'; color: var(--accent-cyan); margin-right: 10px; }

    /* CIRCULAR SKILLS STYLES */
    .skills-circular-container {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 40px 0;
      position: relative;
    }

    .skills-label-side {
      width: 25%;
      display: flex;
      flex-direction: column;
      gap: 15px;
    }

    .side-skills-header {
      font-size: 1rem;
      text-transform: uppercase;
      color: var(--accent-cyan);
      margin-bottom: 10px;
      letter-spacing: 1px;
    }

    .side-skill-item {
      color: var(--text-dim);
      font-size: 0.9rem;
      border-left: 2px solid var(--accent-red);
      padding-left: 10px;
    }

    .hub-wrapper {
      width: 30%;
      display: flex;
      justify-content: center;
      position: relative;
    }

    .skills-hub {
      width: 160px;
      height: 160px;
      background: white;
      border-radius: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      color: #300000;
      font-weight: bold;
      font-size: 1.1rem;
      box-shadow: 0 0 40px rgba(255, 255, 255, 0.2);
      z-index: 5;
    }

    .hub-ring {
      position: absolute;
      width: 200px;
      height: 200px;
      border: 4px solid rgba(255, 255, 255, 0.1);
      border-radius: 50%;
      border-left-color: var(--accent-cyan);
      animation: spin 8s linear infinite;
    }

    @keyframes spin { to { transform: rotate(360deg); } }

    .skills-branches {
      width: 45%;
      display: flex;
      flex-direction: column;
      gap: 20px;
    }

    .branch-item {
      display: flex;
      align-items: center;
      height: 45px;
      position: relative;
      color: white;
      font-weight: bold;
      text-transform: uppercase;
      font-size: 0.85rem;
      clip-path: polygon(0% 0%, 90% 0%, 100% 50%, 90% 100%, 0% 100%);
      padding: 0 40px 0 20px;
      transition: transform 0.3s;
    }

    .branch-item:hover { transform: translateX(10px); }

    .branch-text {
      width: 100%;
      letter-spacing: 1px;
    }

    .orange { background: linear-gradient(90deg, #ff8c00, #ffb347); }
    .purple { background: linear-gradient(90deg, #800080, #bf00bf); }
    .cyan { background: linear-gradient(90deg, #00ced1, #00f2ff); }
    .green { background: linear-gradient(90deg, #2e8b57, #3cb371); }

    /* Footer / Footer Contact Section */
    footer {
      text-align: center;
      padding: 60px 20px;
      color: var(--text-dim);
      border-top: 1px solid rgba(255, 60, 60, 0.2);
      margin-top: 50px;
    }

    .footer-contact {
      display: flex;
      justify-content: center;
      gap: 40px;
      margin-bottom: 25px;
      flex-wrap: wrap;
    }

    .footer-contact a {
      color: var(--text-main);
      font-size: 1rem;
      transition: color 0.3s, transform 0.3s;
      text-decoration: none;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .footer-contact a:hover {
      color: var(--accent-cyan);
      transform: translateY(-3px);
    }

    .footer-contact i {
      font-size: 1.3rem;
    }

    @media (max-width: 900px) {
      .skills-circular-container { flex-direction: column; gap: 50px; }
      .skills-label-side, .hub-wrapper, .skills-branches { width: 100%; align-items: center; text-align: center; }
      .skills-branches { padding-left: 20px; }
      h1 { font-size: 3rem; }
      nav { justify-content: center; }
      nav a { margin: 0 10px; font-size: 14px; }
      .footer-contact { flex-direction: column; gap: 15px; }
    }
  </style>
</head>
<body>

<section id="home">
  <div class="hero-top-nav">
    <span>ANANT YADAV — GAME DEVELOPER</span>
    <i class="fas fa-bars"></i>
  </div>

  <div class="hero-content">
    <h1>ANANT YADAV</h1>
    <div class="hero-role">Game Developer</div>
    <p class="hero-about">
      Dedicated and highly motivated Computer Science student with a deep passion for game architecture and immersive storytelling. 
      Currently developing a high-fidelity AAA prototype <b>"AINCRAD"</b> with a long-term vision of establishing India's premier AAA game development studio.
    </p>
  </div>
</section>

<nav>
  <a href="#projects">Projects</a>
  <a href="#education">Education</a>
  <a href="#skills">Skills</a>
</nav>

<div class="container">
  
  <!-- Projects Section -->
  <section id="projects">
    <h2 class="section-title">Major Projects</h2>
    
    <div class="card">
      <span class="priority-tag">Primary Focus</span>
      <h3>Software & AAA Game Development</h3>
      <ul>
        <li><b>Lead Developer - AINCRAD</b>: Architecting a large-scale AAA game prototype.</li>
        <li><b>Gameplay Programmer</b>: Engineered a high-fidelity FPS movement system in Unreal Engine.</li>
        <li><b>Independent Developer</b>: Created a custom 2D project using the Unity engine.</li>
      </ul>
    </div>

    <h3 style="margin-top: 40px; color: var(--text-dim); text-transform: uppercase; letter-spacing: 1px;">College Projects</h3>
    <div class="card">
      <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 15px;">
        <h3 style="margin: 0;">Driver Safety Alarm (ICT Project)</h3>
        <span style="color: var(--accent-cyan); font-size: 0.9rem;">Arduino Uno</span>
      </div>
      <p style="color: var(--text-dim); margin-bottom: 10px;">Developed a real-time <b>Driver Drowsiness Detection System</b> using eye-blink sensor technology.</p>
      <ul>
        <li>Implemented as an efficient safety solution to reduce road accidents.</li>
        <li>Uses advanced eye-blink sensors to trigger alerts instantly.</li>
        <li>Integrated triple-alert system: <b>Buzzer, LED, and Relay System</b>.</li>
      </ul>
    </div>
  </section>

  <!-- Circular Skills Section -->
  <section id="skills">
    <h2 class="section-title">Skills</h2>
    
    <div class="skills-circular-container">
      
      <!-- Left Side: Core Identity (Game Dev & DSA) -->
      <div class="skills-label-side">
        <h3 class="side-skills-header">Core Game Development</h3>
        <div class="side-skill-item">C++ & C# (Game Engines)</div>
        <div class="side-skill-item">Data Structures & Algorithms</div>
        <div class="side-skill-item">Game Architecture</div>
        <div class="side-skill-item">Real-time Optimization</div>
      </div>

      <!-- Center Hub -->
      <div class="hub-wrapper">
        <div class="skills-hub">
          <span>Game<br>Developer</span>
          <div class="hub-ring"></div>
        </div>
      </div>

      <!-- Right Side Branches -->
      <div class="skills-branches">
        <div class="branch-item orange">
          <span class="branch-text">Self-Learned: Java & C</span>
        </div>
        <div class="branch-item purple">
          <span class="branch-text">Embedded Systems (College)</span>
        </div>
        <div class="branch-item cyan">
          <span class="branch-text">OOP Fundamentals</span>
        </div>
        <div class="branch-item green">
          <span class="branch-text">Debugging & Performance Logic</span>
        </div>
      </div>
    </div>
  </section>

  <!-- Education Section -->
  <section id="education" style="margin-top: 40px;">
    <h2 class="section-title">Education</h2>
    <div class="card">
      <h3>Gautam Buddha University</h3>
      <p><b>B.Tech in Computer Science and Engineering</b> | 2025 - 2029</p>
      <p>Class XII: 72% | Class X: 75%</p>
    </div>
  </section>

</div>

<footer>
  <div class="footer-contact">
    <a href="mailto:yadavanant389@gmail.com" title="Email">
      <i class="far fa-envelope"></i> yadavanant389@gmail.com
    </a>
    <a href="tel:+916388102646" title="Call">
      <i class="fas fa-phone"></i> +91 63881 02646
    </a>
    <a href="#" title="LinkedIn">
      <i class="fab fa-linkedin-in"></i> LinkedIn
    </a>
  </div>
  <p style="letter-spacing: 2px; font-size: 14px;">Designed and Developed by <b style="color: var(--accent-cyan);">ANANT YADAV</b></p>
</footer>

</body>
</html>


