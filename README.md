<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Saksham - Coder Animation</title>

  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;700;900&display=swap" rel="stylesheet">

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      min-height: 100vh;
      background: radial-gradient(circle at top, #111827, #020617 70%);
      overflow-x: hidden;
      font-family: 'Orbitron', sans-serif;
      position: relative;
      padding: 40px 20px;
    }

    .bg-grid {
      position: fixed;
      width: 200%;
      height: 200%;
      background-image:
        linear-gradient(rgba(255,255,255,0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,0.03) 1px, transparent 1px);
      background-size: 40px 40px;
      transform: rotate(10deg);
      animation: moveGrid 20s linear infinite;
      z-index: 0;
    }

    @keyframes moveGrid {
      from {
        transform: translateY(0) rotate(10deg);
      }
      to {
        transform: translateY(-100px) rotate(10deg);
      }
    }

    .content {
      position: relative;
      z-index: 2;
      max-width: 900px;
      margin: 0 auto;
    }

    .container {
      position: relative;
      text-align: center;
      padding: 40px;
      border-radius: 30px;
      background: rgba(255,255,255,0.03);
      backdrop-filter: blur(10px);
      border: 1px solid rgba(255,255,255,0.08);
      box-shadow: 0 0 40px rgba(0,255,170,0.15);
      margin-bottom: 30px;
    }

    .coder {
      font-size: 22px;
      color: #00ffcc;
      letter-spacing: 6px;
      margin-bottom: 15px;
      animation: blink 1.5s infinite;
    }

    @keyframes blink {
      50% {
        opacity: 0.5;
      }
    }

    h1 {
      font-size: 90px;
      font-weight: 900;
      letter-spacing: 10px;
      background: linear-gradient(90deg, #00f5ff, #00ff95, #00f5ff);
      background-size: 300%;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      animation: shine 5s linear infinite;
      text-shadow: 0 0 25px rgba(0,255,200,0.4);
    }

    @keyframes shine {
      0% {
        background-position: 0%;
      }
      100% {
        background-position: 300%;
      }
    }

    .typing {
      color: #94a3b8;
      margin-top: 18px;
      font-size: 20px;
      white-space: nowrap;
      overflow: hidden;
      border-right: 3px solid #00ffcc;
      width: 0;
      animation: typing 5s steps(40) infinite alternate,
                 cursor 0.8s infinite;
    }

    @keyframes typing {
      from {
        width: 0;
      }
      to {
        width: 100%;
      }
    }

    @keyframes cursor {
      50% {
        border-color: transparent;
      }
    }

    .grid {
      margin-top: 40px;
      display: grid;
      grid-template-columns: repeat(25, 14px);
      gap: 6px;
      justify-content: center;
    }

    .box {
      width: 14px;
      height: 14px;
      border-radius: 4px;
      background: #0f172a;
      animation: pulse 3s infinite ease-in-out;
      box-shadow: 0 0 5px rgba(0,255,150,0.2);
    }

    .box:nth-child(odd) {
      animation-delay: 0.3s;
    }

    .box:nth-child(3n) {
      animation-delay: 0.8s;
    }

    .box:nth-child(5n) {
      animation-delay: 1.2s;
    }

    @keyframes pulse {
      0% {
        transform: scale(1);
        background: #0f172a;
      }
      50% {
        transform: scale(1.5) rotate(180deg);
        background: #00ff99;
        box-shadow: 0 0 15px #00ff99;
      }
      100% {
        transform: scale(1);
        background: #2563eb;
      }
    }

    .floating {
      position: fixed;
      color: rgba(0,255,200,0.2);
      font-size: 20px;
      animation: float 10s linear infinite;
      user-select: none;
      z-index: 1;
    }

    @keyframes float {
      from {
        transform: translateY(100vh) rotate(0deg);
      }
      to {
        transform: translateY(-120vh) rotate(360deg);
      }
    }

    .footer {
      margin-top: 35px;
      color: #00ffcc;
      font-size: 16px;
      letter-spacing: 3px;
      text-transform: uppercase;
      opacity: 0.8;
    }

    h2 {
      color: #00ffcc;
      font-size: 28px;
      letter-spacing: 4px;
      margin: 30px 0 20px 0;
      border-bottom: 2px solid rgba(0,255,150,0.3);
      padding-bottom: 10px;
    }

    .section-container {
      background: rgba(255,255,255,0.02);
      border-radius: 15px;
      padding: 25px;
      margin: 20px 0;
      border: 1px solid rgba(0,255,200,0.1);
    }

    .about-text {
      color: #cbd5e1;
      font-size: 16px;
      line-height: 1.8;
      text-align: left;
      margin: 15px 0;
    }

    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
      gap: 12px;
      margin: 20px 0;
    }

    .skill-badge {
      background: linear-gradient(135deg, rgba(0,255,150,0.1), rgba(0,255,200,0.1));
      border: 1px solid rgba(0,255,200,0.3);
      color: #00ffcc;
      padding: 10px;
      border-radius: 8px;
      font-size: 13px;
      transition: all 0.3s ease;
    }

    .skill-badge:hover {
      background: linear-gradient(135deg, rgba(0,255,150,0.2), rgba(0,255,200,0.2));
      box-shadow: 0 0 15px rgba(0,255,200,0.3);
      transform: translateY(-2px);
    }

    .interests-list {
      color: #cbd5e1;
      text-align: left;
      font-size: 15px;
      line-height: 1.8;
    }

    .interests-list li {
      margin: 8px 0;
      margin-left: 20px;
      color: #94a3b8;
    }

    .interests-list li::marker {
      color: #00ffcc;
    }

    .stats {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 15px;
      margin: 20px 0;
    }

    .stat-box {
      background: rgba(0,255,200,0.05);
      border: 1px solid rgba(0,255,200,0.2);
      padding: 15px;
      border-radius: 10px;
      text-align: center;
    }

    .stat-number {
      color: #00ffcc;
      font-size: 24px;
      font-weight: bold;
      margin-bottom: 5px;
    }

    .stat-label {
      color: #94a3b8;
      font-size: 12px;
      text-transform: uppercase;
      letter-spacing: 2px;
    }

    .contact-links {
      display: flex;
      justify-content: center;
      gap: 20px;
      flex-wrap: wrap;
      margin: 20px 0;
    }

    .contact-link {
      color: #00ffcc;
      text-decoration: none;
      padding: 10px 15px;
      border: 1px solid rgba(0,255,200,0.3);
      border-radius: 8px;
      transition: all 0.3s ease;
      font-size: 14px;
    }

    .contact-link:hover {
      background: rgba(0,255,200,0.1);
      box-shadow: 0 0 15px rgba(0,255,200,0.3);
      transform: translateY(-2px);
    }

    @media (max-width: 768px) {
      h1 {
        font-size: 50px;
        letter-spacing: 5px;
      }

      .coder {
        font-size: 16px;
        letter-spacing: 3px;
      }

      .typing {
        font-size: 14px;
      }

      .container {
        padding: 25px;
      }

      .skills-grid {
        grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
      }
    }
  </style>
</head>
<body>

  <div class="bg-grid"></div>

  <div class="floating" style="left:10%; animation-duration:12s;">&lt;/&gt;</div>
  <div class="floating" style="left:25%; animation-duration:16s;">{ }</div>
  <div class="floating" style="left:40%; animation-duration:10s;">console.log()</div>
  <div class="floating" style="left:60%; animation-duration:14s;">#include</div>
  <div class="floating" style="left:80%; animation-duration:18s;">function()</div>

  <div class="content">
    <div class="container">
      <div class="coder">FULL STACK CODER</div>
      <h1>SAKSHAM</h1>
      <div class="typing">
        Passionate Developer • Creative Programmer • Future Software Engineer
      </div>
      <div class="grid" id="grid"></div>
      <div class="footer">
        Building The Future With Code ⚡
      </div>
    </div>

    <!-- About Me Section -->
    <div class="section-container">
      <h2>👋 About Me</h2>
      <div class="about-text">
        <p>Hi! I'm a passionate full-stack developer and tech enthusiast. I love building innovative solutions at the intersection of web development and artificial intelligence. Always eager to learn, collaborate, and contribute to the open-source community.</p>
      </div>
    </div>

    <!-- Interests Section -->
    <div class="section-container">
      <h2>👀 My Interests</h2>
      <ul class="interests-list">
        <li><strong>Artificial Intelligence & Machine Learning</strong> - TensorFlow, PyTorch, NLP</li>
        <li><strong>Web Development</strong> - React, Angular, Vue.js, Node.js</li>
        <li><strong>Cybersecurity & Networking</strong> - System security, network protocols</li>
        <li><strong>Data Science & Analytics</strong> - Data visualization, statistical analysis</li>
        <li><strong>Open-source Contributions</strong> - Community involvement and collaborative projects</li>
      </ul>
    </div>

    <!-- Technical Skills Section -->
    <div class="section-container">
      <h2>🛠️ Technical Skills</h2>
      <div class="skills-grid">
        <div class="skill-badge">Python</div>
        <div class="skill-badge">JavaScript</div>
        <div class="skill-badge">React</div>
        <div class="skill-badge">Node.js</div>
        <div class="skill-badge">TensorFlow</div>
        <div class="skill-badge">PyTorch</div>
        <div class="skill-badge">SQL</div>
        <div class="skill-badge">MongoDB</div>
        <div class="skill-badge">HTML/CSS</div>
        <div class="skill-badge">Git</div>
        <div class="skill-badge">Docker</div>
        <div class="skill-badge">REST APIs</div>
      </div>
    </div>

    <!-- Currently Learning -->
    <div class="section-container">
      <h2>🌱 Currently Learning</h2>
      <div class="about-text">
        📚 Data Structures & Algorithms (DSA)<br>
        🤖 Advanced Machine Learning Techniques<br>
        ☁️ Cloud Computing (AWS, GCP)
      </div>
    </div>

    <!-- Collaboration Section -->
    <div class="section-container">
      <h2>💞️ Looking to Collaborate On</h2>
      <ul class="interests-list">
        <li>Web development projects (React, Angular, Vue.js)</li>
        <li>Machine Learning & AI projects (TensorFlow, PyTorch)</li>
        <li>Cybersecurity research and projects</li>
        <li>Open-source projects & community contributions</li>
        <li>Collaborative coding challenges & hackathons</li>
        <li>CS research papers & academic projects</li>
      </ul>
    </div>

    <!-- Contact Section -->
    <div class="section-container">
      <h2>📫 Get In Touch</h2>
      <div class="contact-links">
        <a href="https://www.linkedin.com/in/saksham-jha-141623275" class="contact-link" target="_blank">💼 LinkedIn</a>
        <a href="https://github.com/Saksham9934" class="contact-link" target="_blank">🐙 GitHub</a>
        <a href="mailto:your-email@example.com" class="contact-link">📧 Email</a>
      </div>
    </div>

    <!-- Stats Section -->
    <div class="section-container">
      <h2>📊 Stats & Achievements</h2>
      <div class="stats">
        <div class="stat-box">
          <div class="stat-number">🚀</div>
          <div class="stat-label">Active Developer</div>
        </div>
        <div class="stat-box">
          <div class="stat-number">💡</div>
          <div class="stat-label">Problem Solver</div>
        </div>
        <div class="stat-box">
          <div class="stat-number">🎯</div>
          <div class="stat-label">Goal Oriented</div>
        </div>
        <div class="stat-box">
          <div class="stat-number">🤝</div>
          <div class="stat-label">Team Player</div>
        </div>
      </div>
    </div>
  </div>

  <script>
    const grid = document.getElementById('grid');

    for (let i = 0; i < 375; i++) {
      const box = document.createElement('div');
      box.classList.add('box');
      grid.appendChild(box);
    }
  </script>

</body>
</html>