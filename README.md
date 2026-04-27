<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ryan | Engineering Portfolio</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background: #030303;
      color: #f5f5f7;
      line-height: 1.6;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    .navbar {
      position: fixed;
      top: 0;
      width: 100%;
      z-index: 1000;
      backdrop-filter: blur(20px);
      background: rgba(10, 10, 10, 0.72);
      border-bottom: 1px solid rgba(255, 255, 255, 0.08);
    }

    .nav-content {
      max-width: 1120px;
      margin: auto;
      padding: 14px 24px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .logo {
      font-weight: 700;
      letter-spacing: -0.03em;
      font-size: 18px;
    }

    nav a {
      margin-left: 24px;
      color: #c7c7cc;
      font-size: 14px;
      transition: color 0.2s ease;
    }

    nav a:hover {
      color: #ffffff;
    }

    .hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 120px 24px 80px;
      text-align: center;
      background:
        radial-gradient(circle at top, rgba(41, 121, 255, 0.25), transparent 32%),
        radial-gradient(circle at bottom right, rgba(120, 119, 198, 0.16), transparent 28%),
        #030303;
    }

    .hero-content {
      max-width: 900px;
    }

    .eyebrow {
      color: #8ab4ff;
      font-size: 15px;
      font-weight: 600;
      margin-bottom: 14px;
      letter-spacing: 0.02em;
    }

    .hero h1 {
      font-size: clamp(48px, 9vw, 96px);
      line-height: 0.95;
      letter-spacing: -0.075em;
      margin-bottom: 24px;
    }

    .hero p {
      max-width: 720px;
      margin: 0 auto 34px;
      color: #c7c7cc;
      font-size: clamp(18px, 2vw, 24px);
      letter-spacing: -0.025em;
    }

    .hero-actions {
      display: flex;
      gap: 14px;
      justify-content: center;
      flex-wrap: wrap;
    }

    .button {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      min-width: 150px;
      padding: 13px 22px;
      border-radius: 999px;
      font-size: 15px;
      font-weight: 600;
      transition: transform 0.2s ease, background 0.2s ease, border 0.2s ease;
    }

    .button:hover {
      transform: translateY(-2px);
    }

    .primary {
      background: #0071e3;
      color: white;
    }

    .primary:hover {
      background: #147ce5;
    }

    .secondary {
      border: 1px solid rgba(255, 255, 255, 0.22);
      color: #f5f5f7;
      background: rgba(255, 255, 255, 0.04);
    }

    section {
      max-width: 1120px;
      margin: auto;
      padding: 90px 24px;
    }

    .section-header {
      margin-bottom: 34px;
    }

    .section-header h2 {
      font-size: clamp(34px, 5vw, 56px);
      letter-spacing: -0.055em;
      line-height: 1;
      margin-bottom: 12px;
    }

    .section-header p {
      color: #a1a1aa;
      font-size: 18px;
      max-width: 720px;
    }

    .about-grid {
      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      gap: 22px;
    }

    .panel {
      background: linear-gradient(145deg, rgba(255, 255, 255, 0.09), rgba(255, 255, 255, 0.035));
      border: 1px solid rgba(255, 255, 255, 0.1);
      border-radius: 28px;
      padding: 32px;
      box-shadow: 0 24px 80px rgba(0, 0, 0, 0.35);
    }

    .panel p {
      color: #d1d1d6;
      font-size: 17px;
      margin-bottom: 16px;
    }

    .stat {
      margin-bottom: 22px;
    }

    .stat strong {
      display: block;
      font-size: 34px;
      letter-spacing: -0.05em;
    }

    .stat span {
      color: #a1a1aa;
    }

    .cards {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 22px;
    }

    .card {
      min-height: 280px;
      background: #111113;
      border: 1px solid rgba(255, 255, 255, 0.09);
      border-radius: 30px;
      padding: 28px;
      transition: transform 0.25s ease, border 0.25s ease, background 0.25s ease;
    }

    .card:hover {
      transform: translateY(-6px);
      border-color: rgba(0, 113, 227, 0.65);
      background: #16161a;
    }

    .card h3 {
      font-size: 24px;
      letter-spacing: -0.04em;
      margin-bottom: 12px;
    }

    .card p {
      color: #b7b7bd;
      margin-bottom: 18px;
    }

    .tag-list {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 18px;
    }

    .tag {
      font-size: 12px;
      padding: 6px 10px;
      border-radius: 999px;
      background: rgba(255, 255, 255, 0.08);
      color: #d1d1d6;
    }

    .timeline {
      display: grid;
      gap: 16px;
    }

    .timeline-item {
      display: grid;
      grid-template-columns: 180px 1fr;
      gap: 22px;
      padding: 24px;
      border-radius: 24px;
      background: rgba(255, 255, 255, 0.055);
      border: 1px solid rgba(255, 255, 255, 0.08);
    }

    .timeline-date {
      color: #8ab4ff;
      font-weight: 700;
    }

    .timeline-item h3 {
      font-size: 21px;
      margin-bottom: 8px;
      letter-spacing: -0.035em;
    }

    .timeline-item p {
      color: #c7c7cc;
    }

    .skills {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 14px;
    }

    .skill {
      padding: 18px;
      background: rgba(255, 255, 255, 0.06);
      border: 1px solid rgba(255, 255, 255, 0.08);
      border-radius: 18px;
      text-align: center;
      color: #e5e5ea;
      font-weight: 600;
    }

    .contact-panel {
      text-align: center;
      background:
        radial-gradient(circle at top left, rgba(0, 113, 227, 0.25), transparent 32%),
        linear-gradient(145deg, rgba(255, 255, 255, 0.09), rgba(255, 255, 255, 0.035));
      border: 1px solid rgba(255, 255, 255, 0.1);
      border-radius: 34px;
      padding: 54px 30px;
    }

    .contact-panel h2 {
      font-size: clamp(36px, 5vw, 58px);
      letter-spacing: -0.055em;
      margin-bottom: 12px;
    }

    .contact-panel p {
      color: #c7c7cc;
      font-size: 18px;
      margin-bottom: 24px;
    }

    footer {
      padding: 34px 24px;
      text-align: center;
      color: #77777f;
      border-top: 1px solid rgba(255, 255, 255, 0.08);
    }

    @media (max-width: 850px) {
      nav {
        display: none;
      }

      .about-grid,
      .cards,
      .skills {
        grid-template-columns: 1fr;
      }

      .timeline-item {
        grid-template-columns: 1fr;
      }

      section {
        padding: 70px 20px;
      }
    }
  </style>
</head>
<body>
  <header class="navbar">
    <div class="nav-content">
      <a href="#top" class="logo">Ryan</a>
      <nav>
        <a href="#about">About</a>
        <a href="#projects">Projects</a>
        <a href="#experience">Experience</a>
        <a href="#skills">Skills</a>
        <a href="#contact">Contact</a>
      </nav>
    </div>
  </header>

  <main id="top">
    <section class="hero">
      <div class="hero-content">
        <div class="eyebrow">Engineering Portfolio</div>
        <h1>Designing practical systems with purpose.</h1>
        <p>
          I am Ryan, a mechatronics engineering student building hands-on experience in automation,
          mechanical design, manufacturing systems, controls, and data-driven engineering tools.
        </p>
        <div class="hero-actions">
          <a class="button primary" href="#projects">View Projects</a>
          <a class="button secondary" href="https://github.com/rta74" target="_blank">GitHub</a>
        </div>
      </div>
    </section>

    <section id="about">
      <div class="section-header">
        <h2>About</h2>
        <p>A clean snapshot of who I am, what I build, and what I can bring to an engineering team.</p>
      </div>

      <div class="about-grid">
        <div class="panel">
          <p>
            I am interested in engineering roles where I can combine mechanical design, automation,
            technical problem-solving, and real-world implementation. My experience includes hands-on
            project work, manufacturing support, data organization, CAD, testing, and system-level thinking.
          </p>
          <p>
            I enjoy turning messy or unclear problems into organized systems, whether that means improving
            a physical design, documenting a workflow, analyzing technical data, or building tools that make
            engineering work easier to understand and maintain.
          </p>
        </div>

        <div class="panel">
          <div class="stat">
            <strong>Mechatronics</strong>
            <span>Engineering background</span>
          </div>
          <div class="stat">
            <strong>Hands-on</strong>
            <span>Design, testing, and implementation</span>
          </div>
          <div class="stat">
            <strong>Career Goal</strong>
            <span>Engineering co-op / internship roles</span>
          </div>
        </div>
      </div>
    </section>

    <section id="projects">
      <div class="section-header">
        <h2>Selected Projects</h2>
        <p>Project cards can be linked to GitHub, reports, images, or live demos once they are ready.</p>
      </div>

      <div class="cards">
        <article class="card">
          <h3>SCADA & Asset Management</h3>
          <p>
            Organized equipment data, asset hierarchy, preventative maintenance details, and workflow
            information to support a more structured manufacturing maintenance system.
          </p>
          <div class="tag-list">
            <span class="tag">SCADA</span>
            <span class="tag">Data Management</span>
            <span class="tag">Manufacturing</span>
          </div>
        </article>

        <article class="card">
          <h3>Assistive Fetch Machine</h3>
          <p>
            Designed and prototyped an assistive fetch machine to help individuals with disabilities engage
            with their pets through a more accessible play experience.
          </p>
          <div class="tag-list">
            <span class="tag">Mechanical Design</span>
            <span class="tag">Prototyping</span>
            <span class="tag">Assistive Tech</span>
          </div>
        </article>

        <article class="card">
          <h3>Air Filtration Retrofit</h3>
          <p>
            Worked on a ventilation retrofit concept for factory air barriers, including design iteration,
            filter fit improvement, and airflow leakage considerations.
          </p>
          <div class="tag-list">
            <span class="tag">CAD</span>
            <span class="tag">HVAC</span>
            <span class="tag">Design Testing</span>
          </div>
        </article>
      </div>
    </section>

    <section id="experience">
      <div class="section-header">
        <h2>Experience</h2>
        <p>Use this section to show engineering employers what you have actually done.</p>
      </div>

      <div class="timeline">
        <div class="timeline-item">
          <div class="timeline-date">Recent</div>
          <div>
            <h3>Engineering / Manufacturing Experience</h3>
            <p>
              Supported manufacturing systems through asset organization, maintenance documentation,
              technical data cleanup, and practical workflow improvements.
            </p>
          </div>
        </div>

        <div class="timeline-item">
          <div class="timeline-date">Projects</div>
          <div>
            <h3>Mechanical and Mechatronics Design</h3>
            <p>
              Built experience with CAD, prototyping, controls concepts, design iteration, testing,
              and engineering communication through academic and personal projects.
            </p>
          </div>
        </div>
      </div>
    </section>

    <section id="skills">
      <div class="section-header">
        <h2>Skills</h2>
        <p>Keep this section clean and job-focused. Add or remove skills based on each application.</p>
      </div>

      <div class="skills">
        <div class="skill">CAD</div>
        <div class="skill">Manufacturing</div>
        <div class="skill">Automation</div>
        <div class="skill">SCADA</div>
        <div class="skill">Data Analysis</div>
        <div class="skill">Prototyping</div>
        <div class="skill">Controls</div>
        <div class="skill">Technical Writing</div>
      </div>
    </section>

    <section id="contact">
      <div class="contact-panel">
        <h2>Let’s build something useful.</h2>
        <p>
          I am currently looking for engineering internship and co-op opportunities where I can contribute,
          learn quickly, and support practical technical work.
        </p>
        <div class="hero-actions">
          <a class="button primary" href="mailto:your.email@example.com">Email Me</a>
          <a class="button secondary" href="https://github.com/rta74" target="_blank">View GitHub</a>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <p>© 2026 Ryan. Designed and built as a personal engineering portfolio.</p>
  </footer>
</body>
</html>
