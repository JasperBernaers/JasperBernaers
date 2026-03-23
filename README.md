<!DOCTYPE html>
<html lang="en">
<head>
<script async src="https://www.googletagmanager.com/gtag/js?id=G-GHJQT4PQZB"></script>
<script>window.dataLayer=window.dataLayer||[];function gtag(){dataLayer.push(arguments)}gtag('js',new Date());gtag('config','G-GHJQT4PQZB');</script>

<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Jasper Bernaers — Cloud &amp; AI Strategist · IBM Consulting</title>
<meta name="description" content="Jasper Bernaers — Cloud &amp; AI Strategist at IBM Consulting. Co-founder of MC2MC. Free tools, articles and community for Microsoft 365 &amp; Azure professionals."/>
<meta property="og:title" content="Jasper Bernaers — Cloud &amp; AI Strategist"/>
<meta property="og:description" content="Cloud &amp; AI Strategist at IBM Consulting. Co-founder of MC2MC. Free tools &amp; articles for Microsoft 365 and Azure."/>
<meta property="og:type" content="profile"/>
<link rel="canonical" href="https://jasperbernaers.com/about-me/"/>

<link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png"/>
<link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png"/>
<link rel="apple-touch-icon" href="/apple-touch-icon.png"/>

<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700&display=swap" rel="stylesheet"/>
<link rel="stylesheet" href="/theme.css"/>
<script src="/theme.js"></script>

<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#0a0e0f;--bg2:#0f1517;--bg3:#131b1e;
  --border:#1e2d2f;--border2:#2a3f44;
  --green:#00ff88;--cyan:#00d4ff;--yellow:#ffd700;
  --red:#ff4444;--purple:#b388ff;
  --white:#e8f4f8;--dim:#4a7080;--dim2:#1a2a30;
  --font:'JetBrains Mono',monospace;
}
html,body{width:100%;min-height:100%;background:#000}
body{font-family:var(--font);font-size:14px;color:var(--white);background:var(--bg);display:flex;flex-direction:column;min-height:100vh;overflow-x:hidden}
body::before{content:'';position:fixed;inset:0;background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,0,0,.06) 2px,rgba(0,0,0,.06) 4px);pointer-events:none;z-index:9999}
body::after{content:'';position:fixed;inset:0;background:radial-gradient(ellipse at center,transparent 60%,rgba(0,0,0,.45) 100%);pointer-events:none;z-index:9998}
@keyframes scanline{0%{transform:translateY(-100%)}100%{transform:translateY(100vh)}}
.scanline{position:fixed;left:0;width:100%;height:2px;background:rgba(0,255,136,.04);z-index:9997;animation:scanline 6s linear infinite;pointer-events:none}

/* TOPBAR */
#topbar{flex-shrink:0;background:var(--bg2);border-bottom:1px solid var(--border);padding:.4rem 1.2rem;display:flex;align-items:center;gap:1rem;font-size:.72rem;color:var(--dim);position:sticky;top:0;z-index:100}
.tb-dot{display:inline-block;width:10px;height:10px;border-radius:50%;margin-right:2px}
.dot-r{background:#ff5f57}.dot-y{background:#ffbd2e}.dot-g{background:#28c840}
#topbar .tb-logo{color:var(--green);font-weight:700;margin-left:.5rem;text-decoration:none}
#topbar .tb-logo:hover{color:var(--cyan)}
#topbar .tb-path{color:var(--cyan)}
#topbar .tb-right{margin-left:auto;display:flex;gap:1.5rem;align-items:center}
#topbar .tb-right a{color:var(--dim);font-size:.68rem;text-decoration:none;transition:color .15s}
#topbar .tb-right a:hover{color:var(--green)}

/* FOOTER */
#footer{background:var(--bg2);border-top:1px solid var(--border);padding:.4rem 1.2rem;font-size:.6rem;color:var(--dim);display:flex;justify-content:space-between;align-items:center;flex-shrink:0;flex-wrap:wrap;gap:.5rem}
#footer a{color:var(--dim);text-decoration:none}
#footer a:hover{color:var(--green)}

/* MAIN */
main{flex:1;max-width:900px;width:100%;margin:0 auto;padding:2rem 1.2rem 3rem}

/* SECTION LABEL */
.sec-label{font-size:.62rem;font-weight:700;color:var(--cyan);letter-spacing:.1em;text-transform:uppercase;margin-bottom:.9rem;display:flex;align-items:center;gap:.5rem}
.sec-label::before{content:'▸';color:var(--green)}
.sec-label::after{content:'';flex:1;height:1px;background:var(--border)}

/* HERO */
.hero{margin-bottom:2.5rem}
.hero-name{font-size:1.5rem;font-weight:700;color:var(--white);line-height:1.2;margin-bottom:.35rem}
.hero-name span{color:var(--green)}
.hero-role{font-size:.82rem;color:var(--cyan);margin-bottom:.5rem}
.hero-quote{font-size:.78rem;color:var(--dim);border-left:2px solid var(--border2);padding-left:.75rem;line-height:1.6;font-style:italic}

/* BIO LIST */
.bio-list{list-style:none;display:flex;flex-direction:column;gap:.55rem;margin-bottom:2rem}
.bio-list li{font-size:.82rem;color:var(--white);line-height:1.6;display:flex;gap:.7rem;align-items:baseline}
.bio-list .icon{flex-shrink:0;width:1.5rem;text-align:center}
.bio-list a{color:var(--cyan);text-decoration:none}
.bio-list a:hover{color:var(--green)}

/* AWARD CHIPS */
.award-row{display:inline-flex;gap:.4rem;flex-wrap:wrap;margin-left:.3rem}
.award{font-size:.62rem;padding:.2rem .55rem;border:1px solid var(--border2);color:var(--dim);border-radius:2px}

/* EBOOK CALLOUT */
.callout{background:var(--bg2);border:1px solid var(--border);border-left:3px solid var(--green);border-radius:4px;padding:.8rem 1rem;margin-bottom:2.5rem;display:flex;align-items:center;justify-content:space-between;gap:1rem;flex-wrap:wrap}
.callout-text{font-size:.78rem;color:var(--white)}
.callout-text span{color:var(--dim);font-size:.7rem;display:block;margin-top:.2rem}
.callout-btn{display:inline-flex;align-items:center;gap:.4rem;border:1px solid var(--green);color:var(--green);padding:.35rem .8rem;border-radius:3px;font-size:.72rem;font-family:var(--font);text-decoration:none;white-space:nowrap;transition:background .15s}
.callout-btn:hover{background:rgba(0,255,136,.08)}

/* TOOLS TABLE */
.tools-table{width:100%;border-collapse:collapse;margin-bottom:.75rem;font-size:.78rem}
.tools-table th{text-align:left;padding:.45rem .7rem;font-size:.62rem;color:var(--dim);text-transform:uppercase;letter-spacing:.07em;border-bottom:1px solid var(--border);font-weight:400}
.tools-table td{padding:.55rem .7rem;border-bottom:1px solid var(--border);vertical-align:top;line-height:1.5}
.tools-table tr:last-child td{border-bottom:none}
.tools-table tr:hover td{background:var(--dim2)}
.tools-table td:first-child{white-space:nowrap}
.tools-table td:first-child a{color:var(--green);text-decoration:none;font-weight:500}
.tools-table td:first-child a:hover{color:var(--cyan)}
.tools-table td:last-child{color:var(--dim)}
.tools-all{font-size:.72rem;color:var(--dim);margin-bottom:2.5rem}
.tools-all a{color:var(--cyan);text-decoration:none}
.tools-all a:hover{color:var(--green)}

/* ARTICLES */
.article-list{list-style:none;display:flex;flex-direction:column;gap:.45rem;margin-bottom:2.5rem}
.article-list li{display:flex;align-items:baseline;gap:.6rem}
.article-list li::before{content:'//';color:var(--dim);font-size:.62rem;flex-shrink:0}
.article-list a{font-size:.8rem;color:var(--white);text-decoration:none;transition:color .15s;line-height:1.5}
.article-list a:hover{color:var(--green)}

/* EVENTS */
.event-list{list-style:none;display:flex;flex-direction:column;gap:.45rem;margin-bottom:2.5rem}
.event-list li{display:flex;gap:.8rem;align-items:baseline;font-size:.78rem}
.event-date{color:var(--dim);flex-shrink:0;font-size:.7rem;min-width:7rem}
.event-list a{color:var(--white);text-decoration:none}
.event-list a:hover{color:var(--green)}

/* CONTACT BADGES */
.badge-row{display:flex;flex-wrap:wrap;gap:.5rem;margin-bottom:2.5rem}
.badge{display:inline-flex;align-items:center;gap:.5rem;padding:.4rem .8rem;border:1px solid var(--border);border-radius:3px;font-size:.72rem;color:var(--dim);text-decoration:none;transition:border-color .15s,color .15s}
.badge:hover{border-color:var(--green);color:var(--green)}

/* RESPONSIVE */
@media(max-width:600px){
  .tools-table td:last-child{display:none}
  .hero-name{font-size:1.1rem}
  #topbar .tb-path{display:none}
  .callout{flex-direction:column;align-items:flex-start}
}
</style>
</head>
<body>
<div class="scanline"></div>

<div id="topbar">
  <span class="tb-dot dot-r"></span>
  <span class="tb-dot dot-y"></span>
  <span class="tb-dot dot-g"></span>
  <a href="https://jasperbernaers.com" class="tb-logo">JasperBernaers.com</a>
  <span class="tb-path">~/about-me</span>
  <span class="tb-right">
    <a href="https://jasperbernaers.com/apps/">apps</a>
    <a href="https://jasperbernaers.com">← terminal</a>
  </span>
</div>

<main>

  <!-- HERO -->
  <div class="hero">
    <div class="hero-name">Jasper Bernaers <span>🌍</span></div>
    <div class="hero-role">Cloud &amp; AI Strategist · IBM Consulting · Belgium 🇧🇪</div>
    <div class="hero-quote">Helping organisations navigate hybrid cloud, AI, and secure modern workplaces — one implementation at a time.</div>
  </div>

  <!-- ABOUT -->
  <div class="sec-label">about</div>
  <ul class="bio-list">
    <li>
      <span class="icon">🏢</span>
      Managing Consultant Cloud &amp; AI at <strong>IBM Consulting</strong>
    </li>
    <li>
      <span class="icon">🛡️</span>
      Co-founder of <a href="https://mc2mc.be">MC2MC</a> — Microsoft Cloud &amp; Client Management Community
    </li>
    <li>
      <span class="icon">✍️</span>
      Writing about Azure, Microsoft 365 &amp; security at <a href="https://jasperbernaers.com">jasperbernaers.com</a>
    </li>
    <li>
      <span class="icon">🏅</span>
      <span>Community Hero #229 · Content Hero #106
        <span class="award-row">
          <span class="award">Community Hero #229</span>
          <span class="award">Content Hero #106</span>
        </span>
      </span>
    </li>
  </ul>

  <!-- EBOOK -->
  <div class="callout">
    <div class="callout-text">
      Free eBook — How a Modern &amp; Secure Workplace Can Help Your Organisation Become Relevant
      <span>Written by Jasper Bernaers · PDF · Free download</span>
    </div>
    <a class="callout-btn" href="https://jasperbernaers.com/Ebook-Jasper-Bernaers.pdf" target="_blank">↓ Download free</a>
  </div>

  <!-- TOOLS -->
  <div class="sec-label">free tools I built</div>
  <table class="tools-table">
    <thead>
      <tr>
        <th>tool</th>
        <th>what it does</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><a href="https://jasperbernaers.com/conditional-access-policy-simulator/" target="_blank">Conditional Access Simulator</a></td>
        <td>Test Entra ID CA policies — user, app, location &amp; device conditions</td>
      </tr>
      <tr>
        <td><a href="https://jasperbernaers.com/KQL-example-generator/" target="_blank">KQL Query Generator</a></td>
        <td>Generate Microsoft Sentinel KQL queries — no login, 100% private</td>
      </tr>
      <tr>
        <td><a href="https://jasperbernaers.com/header-analyzer/" target="_blank">Email Header Analyzer</a></td>
        <td>Trace email delivery path · SPF · DKIM · DMARC · hop delays</td>
      </tr>
      <tr>
        <td><a href="https://jasperbernaers.com/azurenamingconvention/" target="_blank">Azure Naming Convention</a></td>
        <td>Generate Azure resource names following CAF standards</td>
      </tr>
      <tr>
        <td><a href="https://jasperbernaers.com/ASCII-generator/" target="_blank">ASCII Art Generator</a></td>
        <td>Convert any image or text to ASCII art — webcam, glitch &amp; history</td>
      </tr>
    </tbody>
  </table>
  <p class="tools-all">→ <a href="https://jasperbernaers.com/apps/">Browse all 60+ free tools</a></p>

  <!-- ARTICLES -->
  <div class="sec-label">articles</div>
  <ul class="article-list">
    <li><a href="https://jasperbernaers.com/how-to-build-your-zero-trust-modern-workplace-with-microsoft-365/" target="_blank">How to build your Zero Trust Modern Workplace with Microsoft 365</a></li>
    <li><a href="https://jasperbernaers.com/automated-security-operations-delivered-by-microsoft-m365e5-secops/" target="_blank">Automated Security Operations delivered by Microsoft M365 E5</a></li>
    <li><a href="https://jasperbernaers.com/technical-high-level-modern-workplace-implementation-with-m365-e3-e5/" target="_blank">Technical high-level Modern Workplace implementation with M365 E3/E5</a></li>
    <li><a href="https://jasperbernaers.com/actionable-steps-to-decrease-security-risk/" target="_blank">Actionable steps to decrease security risk</a></li>
    <li><a href="https://jasperbernaers.com/the-multi-factor-authentication-struggle-and-the-solution/" target="_blank">The MFA struggle — and the solution</a></li>
    <li><a href="https://jasperbernaers.com/copilot-prompts-for-it-admins/" target="_blank">Copilot prompts for IT admins</a></li>
  </ul>

  <!-- MC2MC -->
  <div class="sec-label">MC2MC community 🧑‍🤝‍🧑</div>
  <ul class="event-list">
    <li><span class="event-date">05/02/2026</span><a href="https://connect.mc2mc.be/" target="_blank">MC2MC Connect</a></li>
    <li><span class="event-date">18/12/2025</span><a href="https://mc2mc.be/mc2mc-live-the-martian-codebase/" target="_blank">MC2MC Live: The Martian Codebase</a></li>
    <li><span class="event-date">13/11/2025</span><a href="https://mc2mc.be/mc2mc-live-transformers-of-the-digital-age/" target="_blank">MC2MC Live: Transformers of the Digital Age</a></li>
    <li><span class="event-date">16/10/2025</span><a href="https://mc2mc.be/mc2mc-live-a-space-odyssey-in-nnovation-16-10-2025/" target="_blank">MC2MC Live: A Space Odyssey in Innovation</a></li>
    <li><span class="event-date">11/09/2025</span><a href="https://mc2mc.be/mc2mc-live-guardians-of-the-digital-realm-11-09-2025/" target="_blank">MC2MC Live: Guardians of the Digital Realm</a></li>
  </ul>

  <!-- CONTACT -->
  <div class="sec-label">contact 📬</div>
  <div class="badge-row">
    <a class="badge" href="https://www.linkedin.com/in/jasperbernaers" target="_blank">💼 linkedin.com/in/jasperbernaers</a>
    <a class="badge" href="https://twitter.com/Jasper_be" target="_blank">𝕏 @Jasper_be</a>
    <a class="badge" href="mailto:jasper@bernaers.be">✉ jasper@bernaers.be</a>
    <a class="badge" href="https://jasperbernaers.com">🌐 jasperbernaers.com</a>
  </div>

</main>

<div id="footer">
  <span>jasperbernaers.com/about-me &nbsp;·&nbsp; <a href="https://jasperbernaers.com/apps/">apps</a> &nbsp;·&nbsp; <a href="https://jasperbernaers.com/notepad/">notepad</a> &nbsp;·&nbsp; <a href="https://jasperbernaers.com/password/">password</a> &nbsp;·&nbsp; <a href="https://jasperbernaers.com/QR/">QR</a> &nbsp;·&nbsp; <a href="https://mc2mc.be">mc2mc.be</a></span>
  <a href="https://jasperbernaers.com">← terminal</a>
</div>

</body>
</html>
