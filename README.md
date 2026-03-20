<!DOCTYPE html>
<html lang="en">
<head>
<script async src="https://www.googletagmanager.com/gtag/js?id=G-GHJQT4PQZB"></script>
<script>window.dataLayer=window.dataLayer||[];function gtag(){dataLayer.push(arguments)}gtag('js',new Date());gtag('config','G-GHJQT4PQZB');</script>

<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Conditional Access Policy Simulator — jasperbernaers.com</title>
<meta name="description" content="Simulate Entra ID Conditional Access policy logic. Test User, Location, and Device variables against Zero Trust policies."/>
<link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png"/>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700&display=swap" rel="stylesheet"/>

<style>
/* ════════════════════════════════════════════════════
   CSS VARIABLES & BASE (FROM TEMPLATE)
════════════════════════════════════════════════════ */
:root{
  --bg:#0a0e0f;--bg2:#0f1517;--bg3:#131b1e;--border:#1e2d2f;
  --green:#00ff88;--cyan:#00d4ff;--yellow:#ffd700;--red:#ff4444;
  --white:#e8f4f8;--dim:#4a7080;--dim2:#1a2a30;--font:'JetBrains Mono',monospace;
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html,body{width:100%;min-height:100vh;font-family:var(--font);font-size:14px;background:var(--bg);color:var(--white);display:flex;flex-direction:column;overflow-x:hidden}

/* CRT EFFECTS */
body::before{content:'';position:fixed;inset:0;background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,0,0,.06) 2px,rgba(0,0,0,.06) 4px);pointer-events:none;z-index:9999}
body::after{content:'';position:fixed;inset:0;background:radial-gradient(ellipse at center,transparent 60%,rgba(0,0,0,.45) 100%);pointer-events:none;z-index:9998}
@keyframes scanline{0%{transform:translateY(-100%)}100%{transform:translateY(100vh)}}
.scanline{position:fixed;left:0;width:100%;height:2px;background:rgba(0,255,136,.04);z-index:9997;animation:scanline 6s linear infinite;pointer-events:none}

/* UI COMPONENTS */
#topbar{background:var(--bg2);border-bottom:1px solid var(--border);padding:.4rem 1.2rem;display:flex;align-items:center;gap:1rem;font-size:.72rem;position:sticky;top:0;z-index:100}
.tb-logo{color:var(--green);font-weight:700;text-decoration:none}.tb-path{color:var(--cyan)}
.tb-right{margin-left:auto;display:flex;gap:1.5rem}
.tb-right a{color:var(--dim);text-decoration:none}
main{flex:1;max-width:900px;width:100%;margin:0 auto;padding:1.5rem 1.2rem 2rem}
.hero-title{font-size:1.1rem;font-weight:700;margin-bottom:.3rem}.hero-title span{color:var(--green)}
.hero-sub{color:var(--dim);font-size:.72rem}.hero-sub span{color:var(--cyan)}
.panel{background:var(--bg2);border:1px solid var(--border);border-radius:4px;margin-bottom:1rem;overflow:hidden}
.panel-header{background:var(--bg3);border-bottom:1px solid var(--border);padding:.55rem 1rem;font-size:.65rem;color:var(--dim);display:flex;justify-content:space-between;text-transform:uppercase}
.panel-body{padding:.9rem 1rem}
.section-title{font-size:.65rem;font-weight:700;color:var(--cyan);text-transform:uppercase;margin-bottom:.75rem;display:flex;align-items:center;gap:.5rem}
.section-title::before{content:'▸';color:var(--green)}
.card-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:.75rem;margin:.75rem 0}
.card{background:var(--bg2);border:1px solid var(--border);padding:.75rem;border-radius:4px}
.card-label{font-size:.65rem;color:var(--cyan);text-transform:uppercase;margin-bottom:.3rem}
.card-value{font-size:.82rem;font-weight:700}
select, input{background:var(--bg);border:1px solid var(--border);color:var(--white);font-family:var(--font);padding:.4rem;width:100%;border-radius:3px;outline:none}
select:focus{border-color:var(--cyan)}
label{font-size:.65rem;color:var(--dim);display:block;margin-bottom:.3rem;margin-top:.8rem}
.row{display:flex;align-items:center;padding:.45rem .75rem;border-left:2px solid transparent;font-size:.82rem;transition:0.12s}
.row.match{background:var(--dim2);border-left-color:var(--green)}
.row.no-match{opacity:0.4}
.prompt{font-size:.82rem;color:var(--dim);display:flex;gap:4px;margin-bottom:0.5rem}
.p-user{color:var(--green)}.p-cmd{color:var(--white)}
.line{line-height:1.6;font-size:.8rem}
#footer{background:var(--bg2);border-top:1px solid var(--border);padding:.4rem 1.2rem;font-size:.6rem;color:var(--dim);display:flex;justify-content:space-between}
#footer a{color:var(--dim);text-decoration:none}
</style>
</head>
<body>

<div class="scanline"></div>

<div id="topbar">
  <a href="https://jasperbernaers.com" class="tb-logo">JasperBernaers.com</a>
  <span class="tb-path">~/ca-policy-simulator</span>
  <span class="tb-right">
    <a href="https://jasperbernaers.com/apps/">apps</a>
    <a href="https://jasperbernaers.com">← terminal</a>
  </span>
</div>

<main>
  <div style="margin-bottom:1.5rem">
    <div class="hero-title">CA Policy <span>Simulator</span></div>
    <div class="hero-sub">Logic-tree visualizer · <span>Zero Trust</span> · Entra ID Testing</div>
  </div>

  <div style="display:grid; grid-template-columns: 1fr 1.5fr; gap: 1rem;">
    <div class="panel">
      <div class="panel-header"><span>▸ Assignment Variables</span></div>
      <div class="panel-body">
        <label>User Type</label>
        <select id="userType" onchange="runSimulation()">
          <option value="standard">Standard User</option>
          <option value="admin">Global Administrator</option>
          <option value="guest">Guest / External</option>
        </select>

        <label>Location</label>
        <select id="location" onchange="runSimulation()">
          <option value="trusted">Trusted IP (Office)</option>
          <option value="untrusted">Untrusted (Home/Coffee Shop)</option>
          <option value="blocked">Blocked Country (High Risk)</option>
        </select>

        <label>Device State</label>
        <select id="deviceState" onchange="runSimulation()">
          <option value="compliant">Compliant (Intune)</option>
          <option value="hybrid">Hybrid Joined</option>
          <option value="unmanaged">Unmanaged (BYOD)</option>
        </select>

        <label>Client App</label>
        <select id="clientApp" onchange="runSimulation()">
          <option value="modern">Browser / Modern Auth</option>
          <option value="legacy">Legacy (POP/IMAP/SMTP)</option>
        </select>
      </div>
    </div>

    <div class="panel">
      <div class="panel-header"><span>▸ Evaluation Log</span></div>
      <div class="panel-body" id="terminal-output" style="height: 280px; overflow-y: auto;">
        <div class="prompt"><span class="p-user">admin</span>@entra-id:~$ <span class="p-cmd">test-policy --verbose</span></div>
        <div id="log-lines"></div>
      </div>
    </div>
  </div>

  <div class="section-title">Final Access Decision</div>
  <div class="card-grid">
    <div class="card" id="card-result">
      <div class="card-label">Result</div>
      <div class="card-value" id="res-decision">---</div>
    </div>
    <div class="card">
      <div class="card-label">Controls Applied</div>
      <div class="card-value" id="res-controls" style="color:var(--yellow)">---</div>
    </div>
    <div class="card">
      <div class="card-label">Matching Policies</div>
      <div class="card-value" id="res-matches" style="color:var(--cyan)">0</div>
    </div>
  </div>

  <div class="section-title" style="margin-top:1.2rem">Policy Evaluation Tree</div>
  <div class="panel" id="policy-list" style="padding:0">
    </div>
</main>

<div id="footer">
  <span>jasperbernaers.com/ca-simulator &nbsp;·&nbsp; <a href="/apps/">all tools</a></span>
  <a href="https://jasperbernaers.com">← back to jasper-os</a>
</div>

<script>
const policies = [
  { id: 1, name: "Global: Block Legacy Auth", trigger: (v) => v.clientApp === 'legacy', action: 'BLOCK', control: 'None' },
  { id: 2, name: "Admin: Require MFA Always", trigger: (v) => v.userType === 'admin', action: 'ALLOW', control: 'MFA Required' },
  { id: 3, name: "Guest: Block Untrusted Loc", trigger: (v) => v.userType === 'guest' && v.location !== 'trusted', action: 'BLOCK', control: 'None' },
  { id: 4, name: "All: Require Compliant Device", trigger: (v) => v.deviceState === 'unmanaged' && v.userType !== 'guest', action: 'ALLOW', control: 'MFA + Compliance' },
  { id: 5, name: "Location: Block High Risk", trigger: (v) => v.location === 'blocked', action: 'BLOCK', control: 'None' }
];

function runSimulation() {
  const vars = {
    userType: document.getElementById('userType').value,
    location: document.getElementById('location').value,
    deviceState: document.getElementById('deviceState').value,
    clientApp: document.getElementById('clientApp').value
  };

  const log = document.getElementById('log-lines');
  const list = document.getElementById('policy-list');
  log.innerHTML = "";
  list.innerHTML = `<div class="stats-bar" style="padding:.5rem 1rem; border-bottom:1px solid var(--border); font-size:.65rem; color:var(--dim)">Total Policies: <span>${policies.length}</span></div>`;

  let matchingCount = 0;
  let finalDecision = "ALLOW";
  let controls = ["None"];
  let blockPolicy = null;

  policies.forEach(p => {
    const isMatch = p.trigger(vars);
    const row = document.createElement('div');
    row.className = `row ${isMatch ? 'match' : 'no-match'}`;
    row.innerHTML = `
      <span style="width:20px">${isMatch ? '✅' : '⚪'}</span>
      <span style="color:${isMatch ? 'var(--green)' : 'var(--dim)'}; font-weight:700; width:220px">${p.name}</span>
      <span style="flex:1; font-size:.7rem; color:var(--dim)">Target: ${p.action}</span>
      <span style="font-size:.6rem; border:1px solid var(--border); padding:1px 4px">${p.control}</span>
    `;
    list.appendChild(row);

    if (isMatch) {
      matchingCount++;
      addLog(`Policy matched: ${p.name}`, 'info');
      if (p.action === 'BLOCK') {
        finalDecision = "BLOCK";
        blockPolicy = p.name;
      }
      if (p.control !== 'None') controls.push(p.control);
    }
  });

  // Final logic
  const resCard = document.getElementById('card-result');
  const resDec = document.getElementById('res-decision');
  
  if (finalDecision === "BLOCK") {
    resDec.innerText = "ACCESS DENIED";
    resDec.style.color = "var(--red)";
    resCard.style.borderColor = "var(--red)";
    addLog(`Critical: Access blocked by ${blockPolicy}`, 'err');
  } else {
    resDec.innerText = "ACCESS GRANTED";
    resDec.style.color = "var(--green)";
    resCard.style.borderColor = "var(--green)";
    addLog(`Success: User cleared all block policies.`, 'out');
  }

  document.getElementById('res-controls').innerText = [...new Set(controls)].filter(c => c !== 'None').join(", ") || "None";
  document.getElementById('res-matches').innerText = matchingCount;
}

function addLog(msg, type) {
  const line = document.createElement('div');
  line.className = `line l-${type}`;
  line.innerText = `> ${msg}`;
  document.getElementById('log-lines').appendChild(line);
}

// Initial Run
runSimulation();
</script>
</body>
</html>
