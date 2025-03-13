<!-- README.md -->
<div align="center">
  <div class="profile-container">
    <h1 class="animated-gradient">Ayoub Ameur</h1>
    <div class="tagline">🚀 Software Engineer | AI Explorer | Creative Developer</div>
    
    <div class="card" id="profile-card">
      <div class="glow"></div>
      <div class="content">
        <div class="section">
          <h2 class="animated-header"><span>👋 About Me</span></h2>
          <p class="animated-text">Software Engineering & AI student passionate about merging technical expertise with creative design. Currently diving deep into full-stack development and mobile ecosystems!</p>
        </div>

        <div class="section">
          <h2 class="animated-header"><span>🛠 Tech Stack</span></h2>
          <div class="skills">
            <span class="skill">Frontend</span>
            <span class="skill">Backend</span>
            <span class="skill">Mobile</span>
            <span class="skill">AI/ML</span>
            <span class="skill">Graphic Design</span>
          </div>
        </div>

        <div class="section">
          <h2 class="animated-header"><span>🌟 Collaboration</span></h2>
          <p class="animated-text">Looking to team up on innovative projects that blend development with creative solutions!</p>
          <div class="cta-buttons">
            <a href="mailto:ayoubyameury@gmail.com" class="cta-button">✉️ Email Me</a>
            <a href="https://www.linkedin.com/in/yourprofile" target="_blank" class="cta-button">💼 LinkedIn</a>
          </div>
        </div>
      </div>
    </div>

    <div class="fun-fact" id="funFact">
      ⚡ Balancing engineering with filmmaking & global adventures!
    </div>
  </div>
</div>

<style>
  @keyframes gradient {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }

  .profile-container {
    max-width: 800px;
    margin: 2rem auto;
    padding: 2rem;
    position: relative;
  }

  .animated-gradient {
    background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
    background-size: 400% 400%;
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
    animation: gradient 15s ease infinite;
    font-size: 2.5rem;
    margin-bottom: 1rem;
  }

  .card {
    background: rgba(255, 255, 255, 0.1);
    border-radius: 15px;
    padding: 2rem;
    position: relative;
    overflow: hidden;
    transition: transform 0.3s ease;
    backdrop-filter: blur(10px);
  }

  .card:hover {
    transform: translateY(-5px);
  }

  .glow {
    position: absolute;
    width: 200%;
    height: 200%;
    background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0) 70%);
    animation: rotate 20s linear infinite;
    pointer-events: none;
  }

  .skill {
    display: inline-block;
    padding: 0.5rem 1rem;
    margin: 0.3rem;
    background: rgba(255,255,255,0.1);
    border-radius: 20px;
    transition: all 0.3s ease;
    cursor: default;
  }

  .skill:hover {
    transform: scale(1.05);
    background: rgba(255,255,255,0.2);
  }

  .cta-button {
    display: inline-block;
    padding: 0.8rem 1.5rem;
    margin: 0.5rem;
    border-radius: 25px;
    background: linear-gradient(45deg, #23a6d5, #23d5ab);
    color: white;
    text-decoration: none;
    transition: transform 0.3s ease;
  }

  .cta-button:hover {
    transform: translateY(-2px);
    box-shadow: 0 5px 15px rgba(0,0,0,0.2);
  }

  @keyframes rotate {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }

  .fun-fact {
    margin-top: 2rem;
    padding: 1rem;
    border-left: 3px solid #23d5ab;
    opacity: 0;
    transform: translateY(20px);
    animation: slideUp 0.5s ease forwards;
    animation-delay: 0.5s;
  }

  @keyframes slideUp {
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
</style>

<script>
  document.addEventListener('DOMContentLoaded', () => {
    // Animate elements on scroll
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.style.opacity = 1;
          entry.target.style.transform = 'translateY(0)';
        }
      });
    });

    document.querySelectorAll('.animated-text, .animated-header').forEach(el => {
      el.style.opacity = 0;
      el.style.transform = 'translateY(20px)';
      observer.observe(el);
    });

    // Parallax effect
    document.addEventListener('mousemove', (e) => {
      const card = document.getElementById('profile-card');
      const xAxis = (window.innerWidth / 2 - e.pageX) / 25;
      const yAxis = (window.innerHeight / 2 - e.pageY) / 25;
      card.style.transform = `rotateY(${xAxis}deg) rotateX(${yAxis}deg)`;
    });

    // Fun facts rotation
    const facts = [
      "⚡ Currently learning: Neural Networks architecture",
      "🌍 Visited 15+ countries and counting!",
      "🎥 Directed short films about tech innovations",
      "🏀 Former basketball team captain"
    ];
    
    let factIndex = 0;
    const factElement = document.getElementById('funFact');
    
    setInterval(() => {
      factElement.style.opacity = 0;
      setTimeout(() => {
        factElement.textContent = facts[factIndex];
        factElement.style.opacity = 1;
        factIndex = (factIndex + 1) % facts.length;
      }, 500);
    }, 5000);
  });
</script>
