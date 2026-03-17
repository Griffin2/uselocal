<script>
  let hoveredTool = $state(null);

  const tools = [
    {
      name: "QR Generator",
      desc: "Generate QR codes without your data touching a server.",
      url: "https://localqr.dev",
      accent: "#F2714D",
      icon: "⬡",
    },
    {
      name: "Prompt Sanitizer",
      desc: "Strip personal data before pasting into AI.",
      url: "https://localclean.dev",
      accent: "#F2714D",
      icon: "🧹",
    },
    {
      name: "EXIF Stripper",
      desc: "Remove GPS & camera data from your photos.",
      url: "https://localexif.dev",
      accent: "#E8628A",
      icon: "📷",
    },
    {
      name: "Password Generator",
      desc: "Crypto-random passwords from your browser.",
      url: "https://localpass.dev",
      accent: "#6BAF8D",
      icon: "🔑",
    },
    {
      name: "Fake Identity",
      desc: "Generate test data without using real people.",
      url: "https://localid.dev",
      accent: "#F59E6C",
      icon: "🎭",
    },
    {
      name: "Screenshot Redactor",
      desc: "Black out sensitive info in screenshots.",
      url: "https://localredact.dev",
      accent: "#E8A830",
      icon: "🖼️",
    },
    {
      name: "Link Cleaner",
      desc: "Strip tracking params from URLs.",
      url: "https://localurl.dev",
      accent: "#9B8FDE",
      icon: "🔗",
    },
    {
      name: "JSON Formatter",
      desc: "Paste messy JSON, get it clean.",
      url: "https://localjson.dev",
      accent: "#F2714D",
      icon: "{ }",
    },
    {
      name: "Base64 Codec",
      desc: "Encode and decode Base64 privately.",
      url: "https://localbase64.dev",
      accent: "#9B8FDE",
      icon: "⟴",
    },
    {
      name: "Text Diff",
      desc: "Compare two texts side by side.",
      url: "https://localcompare.dev",
      accent: "#E8A830",
      icon: "⇄",
    },
  ];

  const posts = [
    {
      title: "What happens when you paste an API key into ChatGPT",
      slug: "/blog/api-key-chatgpt",
      date: "Coming soon",
    },
    {
      title: "Your photos are broadcasting your home address",
      slug: "/blog/exif-gps-danger",
      date: "Coming soon",
    },
    {
      title: "Every link you share is tracking you — here's how to stop it",
      slug: "/blog/url-tracking-params",
      date: "Coming soon",
    },
  ];
</script>

<div class="page">
  <!-- ===== HERO ===== -->
  <section class="hero">
    <div class="hero-glow"></div>
    <div class="hero-content">
      <img src="/logo.png" alt="Run Local" class="hero-logo" />
      <h1 class="hero-title">
        use<span class="hero-title-accent">local</span>
      </h1>
      <p class="hero-sub">Tools that never see your data.</p>
      <p class="hero-desc">
        Every tool runs 100% in your browser. Nothing uploaded. Nothing tracked.
        Nothing stored.
        <br />Open source. Security audited. Free forever.
      </p>
      <a href="#tools" class="hero-cta">See the tools ↓</a>
    </div>
    <div class="hero-fade"></div>
  </section>

  <!-- ===== TRUST STRIP ===== -->
  <section class="trust-strip">
    <div class="trust-inner">
      <div class="trust-item">
        <span class="trust-dot"></span>
        <span>Client-side only</span>
      </div>
      <div class="trust-divider"></div>
      <div class="trust-item">
        <span class="trust-dot"></span>
        <span>Zero network requests</span>
      </div>
      <div class="trust-divider"></div>
      <div class="trust-item">
        <span class="trust-dot"></span>
        <span>Open source</span>
      </div>
      <div class="trust-divider"></div>
      <div class="trust-item">
        <span class="trust-dot"></span>
        <span>Security audited</span>
      </div>
    </div>
  </section>

  <!-- ===== TOOLS ===== -->
  <section class="tools" id="tools">
    <div class="section-inner">
      <h2 class="section-title">The Suite</h2>
      <p class="section-sub">10 privacy tools. Zero servers. One standard.</p>

      <div class="tool-grid">
        {#each tools as tool, i}
          <a
            href={tool.url}
            class="tool-card"
            target="_blank"
            rel="noopener"
            onmouseenter={() => (hoveredTool = i)}
            onmouseleave={() => (hoveredTool = null)}
            style="--card-accent: {tool.accent}; animation-delay: {i * 50}ms;"
          >
            <div class="tool-icon">{tool.icon}</div>
            <div class="tool-info">
              <h3 class="tool-name">{tool.name}</h3>
              <p class="tool-desc">{tool.desc}</p>
            </div>
            <span class="tool-arrow">→</span>
          </a>
        {/each}
      </div>
    </div>
  </section>

  <!-- ===== HOW IT WORKS ===== -->
  <section class="how">
    <div class="section-inner">
      <h2 class="section-title">How is this possible?</h2>
      <div class="how-grid">
        <div class="how-card">
          <div class="how-num">1</div>
          <h3 class="how-heading">You open the tool</h3>
          <p class="how-text">
            A static page loads in your browser. No server processes your
            request — because there is no server.
          </p>
        </div>
        <div class="how-card">
          <div class="how-num">2</div>
          <h3 class="how-heading">Your browser does the work</h3>
          <p class="how-text">
            JavaScript runs on your machine. Your files, text, and images never
            leave your device. We literally can't see them.
          </p>
        </div>
        <div class="how-card">
          <div class="how-num">3</div>
          <h3 class="how-heading">You verify it yourself</h3>
          <p class="how-text">
            Open DevTools → Network tab. Use any tool. Zero requests. Every tool
            links to its source code so you can read exactly what runs.
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- ===== BLOG ===== -->
  <section class="blog" id="blog">
    <div class="section-inner">
      <h2 class="section-title">From the blog</h2>
      <p class="section-sub">
        Why privacy-first tools matter — and what your data is doing without
        you.
      </p>

      <div class="blog-grid">
        {#each posts as post}
          <div class="blog-card">
            <span class="blog-date">{post.date}</span>
            <h3 class="blog-title">{post.title}</h3>
          </div>
        {/each}
      </div>
    </div>
  </section>

  <!-- ===== FOOTER ===== -->
  <footer class="footer">
    <div class="footer-inner">
      <div class="footer-brand">
        <span class="footer-logo"
          >use<span class="footer-logo-accent">local</span></span
        >
        <span class="footer-tagline">Tools that never see your data.</span>
      </div>
      <div class="footer-links">
        <a href="https://github.com/Griffin2" target="_blank" rel="noopener"
          >GitHub</a
        >
        <a href="#tools">Tools</a>
        <a href="#blog">Blog</a>
      </div>
      <div class="footer-bottom">
        <span>runs locally · no server · open source</span>
      </div>
    </div>
  </footer>
</div>

<style>
  @import url("https://fonts.googleapis.com/css2?family=General+Sans:wght@400;500;600;700&display=swap");
  @import url("https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600&display=swap");

  :global(body) {
    margin: 0;
    padding: 0;
    background: #fffbf7;
    -webkit-font-smoothing: antialiased;
  }

  .page {
    font-family:
      "General Sans",
      -apple-system,
      sans-serif;
    color: #2a2a2a;
  }

  /* ===== HERO ===== */
  .hero {
    position: relative;
    background: #0a0a0a;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    min-height: 90vh;
    overflow: hidden;
  }

  .hero-glow {
    position: absolute;
    width: 500px;
    height: 500px;
    background: radial-gradient(
      circle,
      rgba(100, 180, 255, 0.12) 0%,
      transparent 70%
    );
    top: 50%;
    left: 50%;
    transform: translate(-50%, -55%);
    pointer-events: none;
  }

  .hero-content {
    position: relative;
    z-index: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    padding: 0 24px;
  }

  .hero-logo {
    width: 160px;
    height: auto;
    margin-bottom: 24px;
    filter: drop-shadow(0 0 40px rgba(100, 180, 255, 0.3));
    animation: float 6s ease-in-out infinite;
  }

  @keyframes float {
    0%,
    100% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(-8px);
    }
  }

  .hero-title {
    font-family: "JetBrains Mono", monospace;
    font-size: 48px;
    font-weight: 700;
    color: #ffffff;
    margin: 0 0 12px 0;
    letter-spacing: -1px;
  }

  .hero-title-accent {
    color: #7cb8ff;
  }

  .hero-sub {
    font-size: 20px;
    color: rgba(255, 255, 255, 0.9);
    margin: 0 0 16px 0;
    font-weight: 500;
  }

  .hero-desc {
    font-size: 14px;
    color: rgba(255, 255, 255, 0.45);
    margin: 0 0 32px 0;
    line-height: 1.7;
    max-width: 420px;
  }

  .hero-cta {
    font-family: "JetBrains Mono", monospace;
    font-size: 13px;
    color: #7cb8ff;
    text-decoration: none;
    padding: 10px 24px;
    border: 1px solid rgba(124, 184, 255, 0.3);
    border-radius: 999px;
    transition: all 0.2s;
  }

  .hero-cta:hover {
    background: rgba(124, 184, 255, 0.1);
    border-color: rgba(124, 184, 255, 0.6);
  }

  .hero-fade {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 120px;
    background: linear-gradient(to bottom, transparent, #fffbf7);
    pointer-events: none;
  }

  /* ===== TRUST STRIP ===== */
  .trust-strip {
    background: #fffbf7;
    padding: 24px 0;
    border-bottom: 1px solid #f0ebe4;
  }

  .trust-inner {
    max-width: 720px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 20px;
    flex-wrap: wrap;
    padding: 0 24px;
  }

  .trust-item {
    display: flex;
    align-items: center;
    gap: 6px;
    font-family: "JetBrains Mono", monospace;
    font-size: 11px;
    color: #3d8c5c;
    font-weight: 500;
    letter-spacing: 0.3px;
  }

  .trust-dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: #3d8c5c;
    flex-shrink: 0;
  }

  .trust-divider {
    width: 1px;
    height: 14px;
    background: #e0dbd4;
  }

  /* ===== SECTIONS ===== */
  .section-inner {
    max-width: 720px;
    margin: 0 auto;
    padding: 0 24px;
  }

  .section-title {
    font-family: "General Sans", sans-serif;
    font-size: 28px;
    font-weight: 700;
    color: #1a1a1a;
    margin: 0 0 6px 0;
  }

  .section-sub {
    font-size: 15px;
    color: #888;
    margin: 0 0 32px 0;
  }

  /* ===== TOOLS ===== */
  .tools {
    background: #fffbf7;
    padding: 64px 0;
  }

  .tool-grid {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  .tool-card {
    display: flex;
    align-items: center;
    gap: 16px;
    padding: 16px 20px;
    background: #ffffff;
    border: 1px solid #f0ebe4;
    border-radius: 12px;
    text-decoration: none;
    color: inherit;
    transition: all 0.15s;
    animation: fadeUp 0.4s ease both;
  }

  @keyframes fadeUp {
    from {
      opacity: 0;
      transform: translateY(12px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  .tool-card:hover {
    border-color: var(--card-accent);
    box-shadow: 0 2px 12px rgba(0, 0, 0, 0.04);
    transform: translateX(4px);
  }

  .tool-icon {
    width: 40px;
    height: 40px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 10px;
    background: color-mix(in srgb, var(--card-accent) 10%, white);
    font-size: 18px;
    flex-shrink: 0;
    font-family: "JetBrains Mono", monospace;
  }

  .tool-info {
    flex: 1;
    min-width: 0;
  }

  .tool-name {
    font-family: "JetBrains Mono", monospace;
    font-size: 14px;
    font-weight: 600;
    margin: 0 0 2px 0;
    color: #1a1a1a;
  }

  .tool-desc {
    font-size: 13px;
    color: #888;
    margin: 0;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }

  .tool-arrow {
    font-size: 16px;
    color: #ccc;
    flex-shrink: 0;
    transition: all 0.15s;
  }

  .tool-card:hover .tool-arrow {
    color: var(--card-accent);
    transform: translateX(3px);
  }

  /* ===== HOW ===== */
  .how {
    background: #f9f5f0;
    padding: 64px 0;
  }

  .how-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
  }

  .how-card {
    padding: 24px;
    background: #ffffff;
    border: 1px solid #f0ebe4;
    border-radius: 12px;
  }

  .how-num {
    font-family: "JetBrains Mono", monospace;
    font-size: 11px;
    font-weight: 700;
    color: #7cb8ff;
    background: rgba(124, 184, 255, 0.1);
    width: 28px;
    height: 28px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 8px;
    margin-bottom: 14px;
  }

  .how-heading {
    font-size: 15px;
    font-weight: 600;
    margin: 0 0 8px 0;
    color: #1a1a1a;
  }

  .how-text {
    font-size: 13px;
    color: #888;
    line-height: 1.6;
    margin: 0;
  }

  /* ===== BLOG ===== */
  .blog {
    background: #fffbf7;
    padding: 64px 0;
  }

  .blog-grid {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  .blog-card {
    padding: 20px 24px;
    background: #ffffff;
    border: 1px solid #f0ebe4;
    border-radius: 12px;
    cursor: default;
    transition: border-color 0.15s;
  }

  .blog-card:hover {
    border-color: #d0cbc4;
  }

  .blog-date {
    font-family: "JetBrains Mono", monospace;
    font-size: 11px;
    color: #bbb;
    letter-spacing: 0.3px;
  }

  .blog-title {
    font-size: 15px;
    font-weight: 600;
    color: #1a1a1a;
    margin: 6px 0 0 0;
  }

  /* ===== FOOTER ===== */
  .footer {
    background: #0a0a0a;
    padding: 48px 0 32px;
  }

  .footer-inner {
    max-width: 720px;
    margin: 0 auto;
    padding: 0 24px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
  }

  .footer-brand {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 6px;
  }

  .footer-logo {
    font-family: "JetBrains Mono", monospace;
    font-size: 20px;
    font-weight: 700;
    color: #ffffff;
  }

  .footer-logo-accent {
    color: #7cb8ff;
  }

  .footer-tagline {
    font-size: 13px;
    color: rgba(255, 255, 255, 0.35);
  }

  .footer-links {
    display: flex;
    gap: 24px;
  }

  .footer-links a {
    font-family: "JetBrains Mono", monospace;
    font-size: 12px;
    color: rgba(255, 255, 255, 0.4);
    text-decoration: none;
    transition: color 0.15s;
  }

  .footer-links a:hover {
    color: #7cb8ff;
  }

  .footer-bottom {
    padding-top: 20px;
    border-top: 1px solid rgba(255, 255, 255, 0.06);
    width: 100%;
    text-align: center;
  }

  .footer-bottom span {
    font-family: "JetBrains Mono", monospace;
    font-size: 11px;
    color: rgba(255, 255, 255, 0.2);
    letter-spacing: 0.5px;
  }

  /* ===== RESPONSIVE ===== */
  @media (max-width: 640px) {
    .hero-title {
      font-size: 36px;
    }

    .hero-logo {
      width: 120px;
    }

    .how-grid {
      grid-template-columns: 1fr;
    }

    .trust-divider {
      display: none;
    }

    .trust-inner {
      flex-direction: column;
      gap: 8px;
    }

    .tool-desc {
      display: none;
    }
  }
</style>
