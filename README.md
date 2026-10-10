<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Alvis Pressley</title>
    <style>
      :root {
        --bg-1: #070b1a;
        --bg-2: #0f172a;
        --panel: rgba(16, 24, 40, 0.7);
        --panel-strong: rgba(20, 28, 48, 0.9);
        --text: #ecf3ff;
        --muted: #9cb0d4;
        --primary: #84ccff;
        --secondary: #8b5cf6;
        --accent: #22d3ee;
        --glow: rgba(132, 204, 255, 0.35);
        background-color: black;
      }

      * {
        box-sizing: border-box;
      }

      html {
        scroll-behavior: smooth;
      }

      body {
        margin: 0;
        min-height: 100vh;
        font-family: Arial, sans-serif;
        color: var(--text);
        background:
          radial-gradient(circle at top left, rgba(139, 92, 246, 0.45), transparent 28%),
          radial-gradient(circle at bottom right, rgba(34, 211, 238, 0.25), transparent 30%),
          linear-gradient(135deg, var(--bg-1), var(--bg-2) 48%, #111827);
        overflow-x: hidden;
      }

      body::before,
      body::after {
        content: "";
        position: fixed;
        inset: auto;
        width: 420px;
        height: 420px;
        border-radius: 50%;
        filter: blur(80px);
        opacity: 0.5;
        z-index: 0;
      }

      body::before {
        top: -90px;
        left: -80px;
        background: rgba(107, 70, 193, 0.7);
      }

      body::after {
        bottom: -120px;
        right: -60px;
        background: rgba(34, 211, 238, 0.6);
      }

      a {
        color: inherit;
        text-decoration: none;
      }

      .shell {
        position: relative;
        z-index: 1;
      }

      .topbar {
        position: sticky;
        top: 0;
        z-index: 20;
        backdrop-filter: blur(18px);
        background: rgba(9, 12, 22, 0.44);
        border-bottom: 1px solid rgba(255, 255, 255, 0.08);
      }

      .nav {
        max-width: 1200px;
        margin: 0 auto;
        padding: 18px 30px;
        display: flex;
        justify-content: space-between;
        align-items: center;
      }

      .brand {
        display: flex;
        align-items: center;
        gap: 12px;
        font-weight: 700;
        letter-spacing: 0.08em;
        text-transform: uppercase;
      }

      .logo {
        width: 36px;
        height: 36px;
        border-radius: 12px;
        display: grid;
        place-items: center;
        background: linear-gradient(135deg, var(--primary), var(--secondary));
        box-shadow: 0 10px 24px rgba(139, 92, 246, 0.55);
      }

      .nav-links {
        display: flex;
        align-items: center;
        list-style: none;
        gap: 30px;
        margin: 0;
        padding: 0;
        font-size: 0.96rem;
        color: var(--muted);
      }

      .nav-links a {
        transition: color 0.2s ease;
      }

      .nav-links a:hover {
        color: var(--text);
      }

      .cta {
        padding: 12px 22px;
        border-radius: 999px;
        color: #081120;
        background: linear-gradient(135deg, #d9f3ff, #8bd8ff 40%, #b8a4ff);
        font-weight: 700;
        box-shadow: 0 12px 35px rgba(167, 214, 255, 0.45);
      }

      .hero {
        max-width: 1200px;
        margin: 0 auto;
        padding: 90px 30px 60px;
        display: grid;
        grid-template-columns: 1.15fr 0.85fr;
        gap: 30px;
        align-items: center;
      }

      .eyebrow {
        display: inline-flex;
        padding: 8px 14px;
        border: 1px solid rgba(255, 255, 255, 0.12);
        border-radius: 999px;
        color: var(--primary);
        background: rgba(132, 204, 255, 0.08);
        font-size: 0.75rem;
        letter-spacing: 0.14em;
        text-transform: uppercase;
      }

      h1 {
        margin: 18px 0 18px;
        font-size: clamp(3rem, 6vw, 6rem);
        line-height: 0.96;
        letter-spacing: -0.05em;
      }

      .gradient-text {
        background: linear-gradient(135deg, #dff7ff, #91d0ff 35%, #d8c6ff 100%);
        -webkit-background-clip: text;
        background-clip: text;
        color: transparent;
      }

      .hero-copy {
        font-size: 1.1rem;
        line-height: 1.8;
        color: var(--muted);
        max-width: 620px;
      }

      .hero-actions {
        display: flex;
        gap: 16px;
        margin-top: 28px;
        flex-wrap: wrap;
      }

      .button-primary,
      .button-secondary {
        display: inline-flex;
        justify-content: center;
        align-items: center;
        min-height: 52px;
        padding: 0 22px;
        border-radius: 16px;
        font-weight: 700;
        transition: transform 0.2s ease, box-shadow 0.2s ease;
      }

      .button-primary {
        background: linear-gradient(135deg, var(--primary), var(--secondary));
        color: #0a1021;
        box-shadow: 0 15px 35px rgba(139, 92, 246, 0.4);
      }

      .button-secondary {
        border: 1px solid rgba(255, 255, 255, 0.12);
        background: rgba(255, 255, 255, 0.03);
        color: var(--text);
      }

      .button-primary:hover,
      .button-secondary:hover,
      .cta:hover {
        transform: translateY(-2px);
      }

      .stats {
        margin-top: 30px;
        display: flex;
        gap: 28px;
        flex-wrap: wrap;
      }

      .stat {
        min-width: 120px;
      }

      .stat strong {
        display: block;
        font-size: 1.7rem;
      }

      .stat span {
        color: var(--muted);
        font-size: 0.9rem;
      }

      .visual-wrap {
        display: flex;
        justify-content: center;
        align-items: center;
        position: relative;
        min-height: 460px;
      }

      .orb {
        position: absolute;
        border-radius: 50%;
        filter: blur(16px);
        opacity: 0.8;
      }

      .orb.one {
        width: 180px;
        height: 180px;
        background: rgba(96, 165, 250, 0.5);
        top: 30px;
        right: 70px;
      }

      .orb.two {
        width: 220px;
        height: 220px;
        background: rgba(167, 139, 250, 0.5);
        bottom: 40px;
        left: 70px;
      }

      .device {
        position: relative;
        width: min(100%, 450px);
        min-height: 420px;
        border-radius: 32px;
        padding: 22px;
        background: linear-gradient(180deg, rgba(15, 23, 42, 0.78), rgba(15, 23, 42, 0.9));
        border: 1px solid rgba(255, 255, 255, 0.11);
        box-shadow: 0 25px 80px rgba(3, 7, 18, 0.75);
      }

      .device::before {
        content: "";
        position: absolute;
        inset: 10px;
        border-radius: 26px;
        border: 1px solid rgba(255, 255, 255, 0.06);
        background: linear-gradient(135deg, rgba(255, 255, 255, 0.04), rgba(255, 255, 255, 0.01));
      }

      .screen {
        position: relative;
        z-index: 1;
        display: grid;
        gap: 16px;
        height: 100%;
      }

      .top-row,
      .mini-row,
      .chart,
      .bottom-row {
        display: grid;
        gap: 14px;
      }

      .top-row {
        grid-template-columns: repeat(3, 1fr);
      }

      .panel {
        padding: 16px 14px;
        border: 1px solid rgba(255, 255, 255, 0.08);
        background: rgba(15, 25, 40, 0.7);
        border-radius: 18px;
        backdrop-filter: blur(10px);
      }

      .vertical {
        min-height: 130px;
      }

      .mini-row {
        grid-template-columns: 1.2fr 0.8fr;
      }

      .chart {
        padding: 20px 18px 14px;
      }

      .bars {
        display: flex;
        align-items: end;
        gap: 10px;
        height: 110px;
        margin-top: 12px;
      }

      .bars span {
        flex: 1;
        border-radius: 12px 12px 0 0;
        background: linear-gradient(180deg, #9fe4ff, #5d8cf6 55%, #7c5ef7);
        box-shadow: 0 14px 25px rgba(96, 165, 250, 0.35);
      }

      .bars span:nth-child(1) { height: 42%; }
      .bars span:nth-child(2) { height: 62%; }
      .bars span:nth-child(3) { height: 88%; }
      .bars span:nth-child(4) { height: 72%; }
      .bars span:nth-child(5) { height: 100%; }
      .bars span:nth-child(6) { height: 82%; }

      .metric {
        display: flex;
        justify-content: space-between;
        align-items: center;
        color: var(--muted);
        font-size: 0.78rem;
      }

      .metric strong {
        color: var(--text);
        font-size: 1.2rem;
      }

      .circle {
        width: 90px;
        height: 90px;
        border-radius: 50%;
        margin: 14px auto 0;
        display: grid;
        place-items: center;
        background: conic-gradient(var(--primary) 0 74%, rgba(255,255,255,0.08) 74% 100%);
        position: relative;
      }

      .circle::before {
        content: "74%";
        position: absolute;
        width: 62px;
        height: 62px;
        display: grid;
        place-items: center;
        border-radius: 50%;
        background: rgba(10, 16, 29, 0.9);
        font-weight: 700;
      }

      .bottom-row {
        grid-template-columns: 1.1fr 0.9fr;
      }

      .list {
        display: grid;
        gap: 10px;
      }

      .list-item {
        display: flex;
        justify-content: space-between;
        align-items: center;
        color: var(--muted);
        font-size: 0.76rem;
      }

      .dot {
        width: 10px;
        height: 10px;
        border-radius: 50%;
        display: inline-block;
      }

      .dot.purple { background: #8b5cf6; }
      .dot.blue { background: #60a5fa; }
      .dot.cyan { background: #2dd4bf; }

      .section {
        max-width: 1200px;
        margin: 0 auto;
        padding: 30px 30px 12px;
      }

      .section-header {
        display: flex;
        justify-content: space-between;
        align-items: end;
        gap: 20px;
        margin-bottom: 30px;
      }

      .section-header h2 {
        margin: 0;
        font-size: clamp(2rem, 3vw, 3rem);
        letter-spacing: -0.04em;
      }

      .section-header p {
        margin: 0;
        max-width: 560px;
        color: var(--muted);
        line-height: 1.7;
      }

      .cards {
        display: grid;
        grid-template-columns: repeat(3, minmax(0, 1fr));
        gap: 24px;
      }

      .card {
        position: relative;
        padding: 26px 22px;
        border-radius: 24px;
        background: rgba(10, 17, 29, 0.72);
        border: 1px solid rgba(255, 255, 255, 0.08);
        box-shadow: inset 0 1px 0 rgba(255,255,255,0.04);
        overflow: hidden;
      }

      .card::before {
        content: "";
        position: absolute;
        inset: 0 auto auto 0;
        width: 100%;
        height: 1px;
        background: linear-gradient(90deg, transparent, rgba(255,255,255,0.5), transparent);
      }

      .icon {
        width: 54px;
        height: 54px;
        border-radius: 16px;
        display: grid;
        place-items: center;
        font-size: 1.35rem;
        margin-bottom: 18px;
        background: linear-gradient(135deg, rgba(96,165,250,0.2), rgba(139,92,246,0.2));
        border: 1px solid rgba(255,255,255,0.06);
      }

      .card h3 {
        margin: 0 0 10px;
        font-size: 1.4rem;
      }

      .card p {
        margin: 0;
        color: var(--muted);
        line-height: 1.75;
      }

      .feature-band {
        max-width: 1200px;
        margin: 50px auto 20px;
        padding: 28px 30px;
        border-radius: 30px;
        background: linear-gradient(135deg, rgba(99, 102, 241, 0.2), rgba(34, 211, 238, 0.12));
        border: 1px solid rgba(255,255,255,0.1);
        display: flex;
        justify-content: space-between;
        align-items: center;
        gap: 24px;
      }

      .feature-band h3 {
        margin: 0;
        font-size: clamp(1.5rem, 2vw, 2.5rem);
      }

      .feature-band span {
        color: var(--muted);
      }

      footer {
        max-width: 1200px;
        margin: 0 auto;
        padding: 24px 30px 55px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        color: var(--muted);
      }

      @media (max-width: 920px) {
        .hero {
          grid-template-columns: 1fr;
          padding-top: 60px;
        }

        .cards {
          grid-template-columns: 1fr;
        }

        .feature-band,
        .section-header,
        footer {
          flex-direction: column;
          align-items: flex-start;
        }
      }

      @media (max-width: 620px) {
        .nav {
          flex-wrap: wrap;
          gap: 15px;
        }

        .nav-links {
          gap: 14px;
          flex-wrap: wrap;
        }

        .hero {
          padding-left: 18px;
          padding-right: 18px;
        }

        .section,
        .feature-band,
        footer {
          padding-left: 18px;
          padding-right: 18px;
        }
      }
    </style>
  </head>
  <body>
    <div class="shell">
      <header class="topbar">
        <nav class="nav">
          <a href="#" class="brand">
            <span class="logo">N</span>
            <span>Nova</span>
          </a>

          <ul class="nav-links">
            <li><a href="#about">About</a></li>
            <li><a href="#studio">Studio</a></li>
            <li><a href="#solutions">Solutions</a></li>
            <li><a href="#insights">Insights</a></li>
          </ul>

          <a href="#contact" class="cta">Book a demo</a>
        </nav>
      </header>

      <main>
        <section class="hero">
          <div>
            <span class="eyebrow">Design the future</span>
            <h1>
              Build bold<br />
              <span class="gradient-text">immersive</span><br />
              digital brands.
            </h1>
            <p class="hero-copy">
              We turn raw ideas into cinematic experiences that help brands stand out,
              move faster, and leave lasting impressions in the minds of the people who matter.
            </p>

            <div class="hero-actions">
              <a href="#solutions" class="button-primary">Get started</a>
              <a href="#about" class="button-secondary">See how it works</a>
            </div>

            <div class="stats">
              <div class="stat">
                <strong>120+</strong>
                <span>launches</span>
              </div>
              <div class="stat">
                <strong>4.9/5</strong>
                <span>client rating</span>
              </div>
              <div class="stat">
                <strong>18k</strong>
                <span>users reached</span>
              </div>
            </div>
          </div>

          <div class="visual-wrap" aria-label="Analytics dashboard preview">
            <div class="orb one"></div>
            <div class="orb two"></div>

            <div class="device">
              <div class="screen">
                <div class="top-row panel">
                  <div class="vertical">
                    <div class="metric"><span>Traffic</span><strong>+26%</strong></div>
                  </div>
                  <div class="vertical">
                    <div class="metric"><span>Reach</span><strong>87k</strong></div>
                  </div>
                  <div class="vertical">
                    <div class="metric"><span>ROI</span><strong>3.2x</strong></div>
                  </div>
                </div>

                <div class="mini-row">
                  <div class="panel chart">
                    <div class="metric"><span>Engagement</span><strong>76%</strong></div>
                    <div class="bars" aria-label="bar chart">
                      <span></span>
                      <span></span>
                      <span></span>
                      <span></span>
                      <span></span>
                      <span></span>
                    </div>
                  </div>

                  <div class="panel">
                    <div class="metric"><span>Progress</span><strong>74%</strong></div>
                    <div class="circle" aria-label="progress circle"></div>
                  </div>
                </div>

                <div class="bottom-row">
                  <div class="panel list">
                    <div class="list-item"><span><span class="dot purple"></span> Creative</span><strong>42%</strong></div>
                    <div class="list-item"><span><span class="dot blue"></span> Growth</span><strong>31%</strong></div>
                    <div class="list-item"><span><span class="dot cyan"></span> Product</span><strong>27%</strong></div>
                  </div>

                  <div class="panel">
                    <div class="metric"><span>Revenue</span><strong>$182k</strong></div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>

        <section class="section" id="about">
          <div class="section-header">
            <h2>Craft experiences that move people.</h2>
            <p>
              We blend strategy, creativity, and design systems to build story-led digital products that feel premium from the first click to the final conversion.
            </p>
          </div>

          <div class="cards">
            <article class="card">
              <div class="icon">✦</div>
              <h3>Brand systems</h3>
              <p>
                Visual identities, messaging, and digital direction that make your brand recognizable, memorable, and unmistakably premium.
              </p>
            </article>

            <article class="card">
              <div class="icon">◎</div>
              <h3>Immersive design</h3>
              <p>
                High-impact interfaces, atmospheric motion, and layered storytelling that pull attention into the experience and keep it there.
              </p>
            </article>

            <article class="card">
              <div class="icon">▣</div>
              <h3>Conversion strategy</h3>
              <p>
                Thoughtful journeys and measurable UX decisions that help audiences connect, trust, and act without friction.
              </p>
            </article>
          </div>
        </section>

        <section class="feature-band" id="solutions">
          <div>
            <h3>Launch smarter, faster, and with more impact.</h3>
          </div>
          <a href="#contact" class="button-primary">Start your project</a>
        </section>
      </main>

      <footer id="contact">
        <div>© 2026 Nova Studio</div>
        <div>hello@novastudio.design</div>
      </footer>
    </div>
  </body>
</html>
