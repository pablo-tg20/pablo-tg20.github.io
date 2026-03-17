<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Simulación de Vaciado de Tanque</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap');

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0f1117;
    --surface: #1a1d27;
    --surface2: #1f2335;
    --border: rgba(255,255,255,0.08);
    --border2: rgba(255,255,255,0.14);
    --blue: #4f9eff;
    --blue-dim: rgba(79,158,255,0.15);
    --cyan: #56cfb2;
    --cyan-dim: rgba(86,207,178,0.12);
    --text: #e2e8f0;
    --muted: #64748b;
    --muted2: #94a3b8;
    --wave: rgba(79,158,255,0.08);
  }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Inter', sans-serif;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  /* Animated background grid */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(var(--border) 1px, transparent 1px),
      linear-gradient(90deg, var(--border) 1px, transparent 1px);
    background-size: 48px 48px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    position: relative;
    z-index: 1;
    width: 100%;
    max-width: 960px;
    padding: 2.5rem 1.5rem 4rem;
  }

  /* Header */
  .header {
    text-align: center;
    margin-bottom: 3rem;
  }
  .header-tag {
    display: inline-block;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.7rem;
    letter-spacing: 0.14em;
    color: var(--cyan);
    background: var(--cyan-dim);
    border: 1px solid rgba(86,207,178,0.2);
    border-radius: 100px;
    padding: 0.3rem 0.9rem;
    margin-bottom: 1rem;
    text-transform: uppercase;
  }
  .header h1 {
    font-size: clamp(1.8rem, 4vw, 2.8rem);
    font-weight: 600;
    letter-spacing: -0.03em;
    color: #fff;
    margin-bottom: 0.6rem;
    line-height: 1.15;
  }
  .header-sub {
    font-size: 0.85rem;
    color: var(--muted2);
    letter-spacing: 0.04em;
  }
  .header-sub span {
    color: var(--blue);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.8rem;
  }

  /* Stat cards row */
  .stats {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1rem;
    margin-bottom: 1.5rem;
  }
  @media (max-width: 600px) { .stats { grid-template-columns: 1fr 1fr; } }

  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border2);
    border-radius: 14px;
    padding: 1.1rem 1.2rem;
    position: relative;
    overflow: hidden;
    transition: border-color 0.2s;
  }
  .stat-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--blue), var(--cyan));
    opacity: 0.5;
    border-radius: 14px 14px 0 0;
  }
  .stat-label {
    font-size: 0.68rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 0.5rem;
  }
  .stat-val {
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.45rem;
    font-weight: 500;
    color: #fff;
    line-height: 1;
  }
  .stat-val.accent { color: var(--cyan); }
  .stat-val.blue { color: var(--blue); }
  .stat-sub {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.65rem;
    color: var(--muted);
    margin-top: 0.3rem;
  }

  /* Main layout */
  .main-grid {
    display: grid;
    grid-template-columns: 1fr 280px;
    gap: 1.5rem;
    margin-bottom: 1.5rem;
  }
  @media (max-width: 700px) { .main-grid { grid-template-columns: 1fr; } }

  /* Chart card */
  .card {
    background: var(--surface);
    border: 1px solid var(--border2);
    border-radius: 16px;
    padding: 1.4rem;
  }
  .card-title {
    font-size: 0.7rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 1.2rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
  }
  .card-title::before {
    content: '';
    display: inline-block;
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--cyan);
  }
  .chart-wrap {
    position: relative;
    width: 100%;
    height: 240px;
  }

  /* Tank visual card */
  .tank-card {
    background: var(--surface);
    border: 1px solid var(--border2);
    border-radius: 16px;
    padding: 1.4rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1.2rem;
  }

  .tank-scene {
    position: relative;
    width: 140px;
    height: 280px;
    margin: 0 auto;
  }

  /* Tank glass effect */
  .tank-outer {
    position: absolute;
    inset: 0 10px 20px 10px;
    border: 1.5px solid rgba(255,255,255,0.15);
    border-radius: 8px 8px 4px 4px;
    overflow: hidden;
    background: rgba(0,0,0,0.4);
  }
  .tank-water {
    position: absolute;
    bottom: 0; left: 0; right: 0;
    background: linear-gradient(180deg, rgba(79,158,255,0.6) 0%, rgba(56,130,220,0.85) 100%);
    transition: height 0.06s linear;
    border-radius: 0 0 2px 2px;
  }
  /* Water surface shimmer */
  .tank-water::after {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: rgba(150,210,255,0.7);
    border-radius: 2px;
    animation: shimmer 2s ease-in-out infinite;
  }
  @keyframes shimmer {
    0%,100% { opacity: 0.7; }
    50% { opacity: 0.3; }
  }
  .tank-pct-label {
    position: absolute;
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    font-family: 'JetBrains Mono', monospace;
    font-size: 1.1rem;
    font-weight: 500;
    color: rgba(255,255,255,0.9);
    text-shadow: 0 1px 6px rgba(0,0,0,0.6);
    pointer-events: none;
    z-index: 2;
  }
  /* Tick marks */
  .tick {
    position: absolute;
    right: -16px;
    width: 8px;
    height: 1px;
    background: var(--muted);
  }
  .tick-label {
    position: absolute;
    right: -38px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.55rem;
    color: var(--muted);
    transform: translateY(-50%);
  }
  /* Pipe/orifice */
  .pipe {
    position: absolute;
    bottom: 0; left: 50%;
    transform: translateX(-50%);
    width: 14px; height: 22px;
    background: var(--surface2);
    border: 1.5px solid rgba(255,255,255,0.1);
    border-top: none;
    border-radius: 0 0 4px 4px;
  }
  /* Water jet */
  .jet-wrap {
    position: absolute;
    bottom: -50px; left: 50%;
    transform: translateX(-50%);
    width: 8px;
    overflow: hidden;
  }
  .jet-stream {
    width: 100%;
    height: 0;
    background: linear-gradient(180deg, rgba(79,158,255,0.8), rgba(79,158,255,0));
    border-radius: 0 0 4px 4px;
    transition: height 0.1s;
  }

  /* h label */
  .h-arrow {
    position: absolute;
    left: -32px;
    top: 0; bottom: 20px;
    display: flex;
    align-items: center;
  }
  .h-line {
    position: absolute;
    left: 8px; top: 0; bottom: 0;
    width: 1px;
    background: var(--blue);
    opacity: 0.5;
  }
  .h-text {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.6rem;
    color: var(--blue);
    writing-mode: vertical-rl;
    transform: rotate(180deg);
    white-space: nowrap;
  }

  /* Formula display in tank card */
  .formula-strip {
    width: 100%;
    background: rgba(0,0,0,0.3);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 0.7rem 0.9rem;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.65rem;
    color: var(--muted2);
    line-height: 1.9;
  }
  .formula-strip .eq { color: var(--cyan); }

  /* Controls card */
  .controls-card {
    background: var(--surface);
    border: 1px solid var(--border2);
    border-radius: 16px;
    padding: 1.4rem;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 1.2rem;
    align-items: end;
  }
  @media (max-width: 600px) { .controls-card { grid-template-columns: 1fr; } }

  .ctrl { }
  .ctrl-head { display: flex; justify-content: space-between; margin-bottom: 0.5rem; }
  .ctrl-name { font-size: 0.7rem; color: var(--muted2); }
  .ctrl-num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.7rem;
    color: var(--cyan);
    font-weight: 500;
  }
  input[type=range] {
    -webkit-appearance: none;
    width: 100%; height: 4px;
    border-radius: 2px;
    background: var(--surface2);
    outline: none;
    cursor: pointer;
  }
  input[type=range]::-webkit-slider-thumb {
    -webkit-appearance: none;
    width: 16px; height: 16px;
    border-radius: 50%;
    background: var(--blue);
    border: 2px solid rgba(255,255,255,0.2);
    cursor: pointer;
    transition: transform 0.1s;
  }
  input[type=range]::-webkit-slider-thumb:hover { transform: scale(1.2); }

  /* Buttons */
  .btn-group {
    background: var(--surface);
    border: 1px solid var(--border2);
    border-radius: 16px;
    padding: 1.2rem 1.4rem;
    display: flex;
    align-items: center;
    gap: 0.75rem;
    flex-wrap: wrap;
    margin-bottom: 1.5rem;
  }
  .btn {
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    padding: 0.6rem 1.4rem;
    border-radius: 9px;
    border: 1px solid var(--border2);
    background: transparent;
    color: var(--text);
    font-family: 'Inter', sans-serif;
    font-size: 0.82rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.15s;
    letter-spacing: 0.01em;
    white-space: nowrap;
  }
  .btn:hover { background: rgba(255,255,255,0.06); border-color: rgba(255,255,255,0.2); }
  .btn.start { background: var(--blue-dim); border-color: rgba(79,158,255,0.4); color: var(--blue); }
  .btn.start:hover { background: rgba(79,158,255,0.25); }
  .btn.pause { background: rgba(245,158,11,0.12); border-color: rgba(245,158,11,0.3); color: #f59e0b; }
  .btn.reset { }
  .speed-wrap { display: flex; align-items: center; gap: 0.6rem; margin-left: auto; }
  .speed-label { font-size: 0.72rem; color: var(--muted); white-space: nowrap; }
  .speed-select {
    background: var(--surface2);
    border: 1px solid var(--border2);
    border-radius: 7px;
    color: var(--text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.75rem;
    padding: 0.35rem 0.6rem;
    cursor: pointer;
    outline: none;
  }

  /* Progress bar */
  .progress-track {
    width: 100%;
    height: 5px;
    background: var(--surface2);
    border-radius: 3px;
    overflow: hidden;
    flex: 1;
  }
  .progress-fill {
    height: 100%;
    background: linear-gradient(90deg, var(--blue), var(--cyan));
    border-radius: 3px;
    width: 0%;
    transition: width 0.06s linear;
  }
  .time-mono {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.75rem;
    color: var(--muted2);
    white-space: nowrap;
  }

  /* Footer */
  footer {
    text-align: center;
    font-size: 0.7rem;
    color: var(--muted);
    letter-spacing: 0.06em;
    margin-top: 1rem;
  }
  footer span { color: var(--blue); font-family: 'JetBrains Mono', monospace; }
</style>
</head>
<body>
<div class="container">

  <!-- Header -->
  <div class="header">
    <div class="header-tag">Ecuaciones Diferenciales · Ley de Torricelli</div>
    <h1>Simulación de Vaciado de Tanque</h1>
    <div class="header-sub">
      h₀ = <span>2.9 m</span> &nbsp;·&nbsp; R = <span>46 cm</span> &nbsp;·&nbsp; r = <span>3.7 cm</span> &nbsp;·&nbsp; t = <span id="hdrT">119.02 s</span>
    </div>
  </div>

  <!-- Stats -->
  <div class="stats">
    <div class="stat-card">
      <div class="stat-label">Altura actual</div>
      <div class="stat-val accent" id="sH">2.900 m</div>
    </div>
    <div class="stat-card">
      <div class="stat-label">Tiempo</div>
      <div class="stat-val blue" id="sT">0.00 s</div>
    </div>
    <div class="stat-card">
      <div class="stat-label">Vaciado</div>
      <div class="stat-val" id="sPct">0%</div>
    </div>
    <div class="stat-card">
      <div class="stat-label">Tiempo total</div>
      <div class="stat-val" id="sTv">119.02 s</div>
      <div class="stat-sub" id="sTvMin">1 min 59.02 s</div>
    </div>
  </div>

  <!-- Button row -->
  <div class="btn-group">
    <button class="btn start" id="btnStart">▶ Iniciar</button>
    <button class="btn pause" id="btnPause" disabled>⏸ Pausar</button>
    <button class="btn reset" id="btnReset">↺ Reiniciar</button>
    <div style="display:flex;align-items:center;gap:0.5rem;flex:1;">
      <div class="progress-track"><div class="progress-fill" id="pgBar"></div></div>
      <span class="time-mono" id="pgTime">0.00 s</span>
    </div>
    <div class="speed-wrap">
      <span class="speed-label">Velocidad:</span>
      <select class="speed-select" id="speedSel">
        <option value="1">1×</option>
        <option value="5">5×</option>
        <option value="10" selected>10×</option>
        <option value="25">25×</option>
        <option value="50">50×</option>
      </select>
    </div>
  </div>

  <!-- Main grid -->
  <div class="main-grid">
    <!-- Chart -->
    <div class="card">
      <div class="card-title">Altura h(t) — curva de vaciado</div>
      <div class="chart-wrap"><canvas id="myChart"></canvas></div>
    </div>

    <!-- Tank -->
    <div class="tank-card">
      <div class="card-title" style="align-self:flex-start">Nivel del tanque</div>

      <div class="tank-scene">
        <!-- h arrow -->
        <div class="h-arrow" style="left:-28px;">
          <div class="h-line"></div>
          <span class="h-text" id="hArrowTxt">h = 2.90 m</span>
        </div>

        <!-- Tick marks -->
        <div class="tick" style="bottom:calc(20px + 100%*0.75);"></div>
        <span class="tick-label" style="bottom:calc(20px + 100%*0.75 - 4px);">75%</span>
        <div class="tick" style="bottom:calc(20px + 100%*0.5);"></div>
        <span class="tick-label" style="bottom:calc(20px + 100%*0.5 - 4px);">50%</span>
        <div class="tick" style="bottom:calc(20px + 100%*0.25);"></div>
        <span class="tick-label" style="bottom:calc(20px + 100%*0.25 - 4px);">25%</span>

        <div class="tank-outer">
          <div class="tank-water" id="tankWater" style="height:100%;">
          </div>
          <div class="tank-pct-label" id="tankPctLbl">100%</div>
        </div>
        <div class="pipe"></div>
        <div class="jet-wrap">
          <div class="jet-stream" id="jetStream" style="height:40px;"></div>
        </div>
      </div>

      <div class="formula-strip">
        <div><span class="eq">dh/dt</span> = −(r/R)²·√(2gh)</div>
        <div><span class="eq">h(t)</span> = [√h₀ − k·t ]²</div>
        <div><span class="eq">k</span> = (r/R)²·√(2g)/2</div>
        <div><span class="eq">t_vac</span> = 2√h₀ / [(r/R)²·√(2g)]</div>
      </div>
    </div>
  </div>

  <!-- Controls -->
  <div class="controls-card">
    <div class="ctrl">
      <div class="ctrl-head">
        <span class="ctrl-name">Radio tanque R (cm)</span>
        <span class="ctrl-num" id="lR">46.0 cm</span>
      </div>
      <input type="range" id="slR" min="10" max="120" step="0.5" value="46">
    </div>
    <div class="ctrl">
      <div class="ctrl-head">
        <span class="ctrl-name">Radio orificio r (cm)</span>
        <span class="ctrl-num" id="lr">3.7 cm</span>
      </div>
      <input type="range" id="slr" min="0.5" max="15" step="0.1" value="3.7">
    </div>
    <div class="ctrl">
      <div class="ctrl-head">
        <span class="ctrl-name">Altura inicial h₀ (m)</span>
        <span class="ctrl-num" id="lH">2.9 m</span>
      </div>
      <input type="range" id="slH" min="0.5" max="6" step="0.1" value="2.9">
    </div>
  </div>

  <footer style="margin-top:2rem;">
    Simulación basada en la Ley de Torricelli &nbsp;·&nbsp; <span>dh/dt = −(r²/R²)√(2gh)</span>
  </footer>

</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js"></script>
<script>
const G = 9.81;
let chart = null, sim = null, idx = 0, running = false, rafId = null, lastTs = null;

function getP() {
  return {
    R: parseFloat(document.getElementById('slR').value) / 100,
    r: parseFloat(document.getElementById('slr').value) / 100,
    h0: parseFloat(document.getElementById('slH').value),
    speed: parseFloat(document.getElementById('speedSel').value)
  };
}

function compute(h0, R, r) {
  const ratio = (r / R) ** 2;
  const k = ratio * Math.sqrt(2 * G) / 2;
  const tv = Math.sqrt(h0) / k;
  const STEPS = 600;
  const dt = tv / STEPS;
  const T = [], H = [], V = [];
  for (let i = 0; i <= STEPS; i++) {
    const t = i * dt;
    const sq = Math.max(0, Math.sqrt(h0) - k * t);
    T.push(+(t.toFixed(3)));
    H.push(+(sq * sq).toFixed(5));
    V.push(+(Math.sqrt(2 * G * sq * sq)).toFixed(4));
  }
  return { T, H, V, tv, k };
}

function toMinSec(s) {
  const m = Math.floor(s / 60);
  const sec = (s - m * 60).toFixed(2);
  return m > 0 ? `${m} min ${sec} s` : `${sec} s`;
}

function buildChart() {
  if (chart) { chart.destroy(); chart = null; }
  const ctx = document.getElementById('myChart').getContext('2d');
  chart = new Chart(ctx, {
    type: 'line',
    data: {
      labels: [],
      datasets: [{
        data: [],
        borderColor: '#4f9eff',
        backgroundColor: 'rgba(79,158,255,0.07)',
        borderWidth: 2, pointRadius: 0, fill: true, tension: 0.35
      }]
    },
    options: {
      responsive: true, maintainAspectRatio: false, animation: false,
      plugins: { legend: { display: false }, tooltip: {
        callbacks: { label: ctx => ` h = ${ctx.parsed.y.toFixed(3)} m` },
        bodyFont: { family: 'JetBrains Mono' }, titleFont: { family: 'JetBrains Mono' }
      }},
      scales: {
        x: {
          grid: { color: 'rgba(255,255,255,0.04)' },
          ticks: { color: '#64748b', font: { family: 'JetBrains Mono', size: 10 }, maxTicksLimit: 8, autoSkip: true },
          title: { display: true, text: 'Tiempo (s)', color: '#64748b', font: { family: 'JetBrains Mono', size: 10 } }
        },
        y: {
          grid: { color: 'rgba(255,255,255,0.04)' },
          ticks: { color: '#64748b', font: { family: 'JetBrains Mono', size: 10 } },
          min: 0,
          title: { display: true, text: 'h (m)', color: '#64748b', font: { family: 'JetBrains Mono', size: 10 } }
        }
      }
    }
  });
}

function updateUI(i) {
  if (!sim) return;
  const h = sim.H[i], t = sim.T[i], h0 = getP().h0;
  const pct = Math.max(0, Math.min(1, h / h0));

  document.getElementById('sH').textContent = h.toFixed(3) + ' m';
  document.getElementById('sT').textContent = t.toFixed(2) + ' s';
  document.getElementById('sPct').textContent = (pct * 100).toFixed(1) + '%';
  document.getElementById('pgTime').textContent = t.toFixed(2) + ' s';
  document.getElementById('pgBar').style.width = ((t / sim.tv) * 100).toFixed(2) + '%';

  // tank
  document.getElementById('tankWater').style.height = (pct * 100).toFixed(2) + '%';
  document.getElementById('tankPctLbl').textContent = Math.round(pct * 100) + '%';
  document.getElementById('hArrowTxt').textContent = 'h = ' + h.toFixed(2) + ' m';
  document.getElementById('jetStream').style.height = Math.round(pct * 45) + 'px';

  // chart
  if (chart) {
    chart.data.labels = sim.T.slice(0, i + 1);
    chart.data.datasets[0].data = sim.H.slice(0, i + 1);
    chart.update('none');
  }
}

function startAnim() {
  if (running) return;
  if (!sim) {
    buildSim();
  }
  running = true;
  lastTs = null;
  document.getElementById('btnStart').disabled = true;
  document.getElementById('btnPause').disabled = false;

  function tick(ts) {
    if (!running) return;
    if (lastTs === null) lastTs = ts;
    const elapsed = (ts - lastTs) / 1000;
    lastTs = ts;

    const { speed } = getP();
    const simElapsed = elapsed * speed;
    const dt = sim.tv / sim.H.length;
    const steps = Math.max(1, Math.round(simElapsed / dt));
    idx = Math.min(idx + steps, sim.H.length - 1);
    updateUI(idx);

    if (idx >= sim.H.length - 1) {
      running = false;
      document.getElementById('btnStart').disabled = false;
      document.getElementById('btnPause').disabled = true;
      return;
    }
    rafId = requestAnimationFrame(tick);
  }
  rafId = requestAnimationFrame(tick);
}

function pauseAnim() {
  running = false;
  if (rafId) cancelAnimationFrame(rafId);
  document.getElementById('btnStart').disabled = false;
  document.getElementById('btnPause').disabled = true;
}

function resetSim() {
  running = false;
  if (rafId) cancelAnimationFrame(rafId);
  idx = 0;
  sim = null;
  buildSim();
  updateUI(0);
  document.getElementById('btnStart').disabled = false;
  document.getElementById('btnPause').disabled = true;
  if (chart) { chart.data.labels = []; chart.data.datasets[0].data = []; chart.update('none'); }
}

function buildSim() {
  const { R, r, h0 } = getP();
  sim = compute(h0, R, r);
  idx = 0;
  const tvStr = sim.tv.toFixed(2) + ' s';
  document.getElementById('sTv').textContent = tvStr;
  document.getElementById('sTvMin').textContent = toMinSec(sim.tv);
  document.getElementById('hdrT').textContent = tvStr;
  document.getElementById('sH').textContent = h0.toFixed(3) + ' m';
  document.getElementById('sT').textContent = '0.00 s';
  document.getElementById('sPct').textContent = '0%';
  document.getElementById('pgTime').textContent = '0.00 s';
  document.getElementById('pgBar').style.width = '0%';
  document.getElementById('tankWater').style.height = '100%';
  document.getElementById('tankPctLbl').textContent = '100%';
  document.getElementById('hArrowTxt').textContent = 'h = ' + h0.toFixed(2) + ' m';
  document.getElementById('jetStream').style.height = '45px';
  if (!chart) buildChart();
}

function updateLabels() {
  const R = parseFloat(document.getElementById('slR').value);
  const r = parseFloat(document.getElementById('slr').value);
  const h0 = parseFloat(document.getElementById('slH').value);
  document.getElementById('lR').textContent = R.toFixed(1) + ' cm';
  document.getElementById('lr').textContent = r.toFixed(1) + ' cm';
  document.getElementById('lH').textContent = h0.toFixed(1) + ' m';
  resetSim();
}

document.getElementById('btnStart').addEventListener('click', startAnim);
document.getElementById('btnPause').addEventListener('click', pauseAnim);
document.getElementById('btnReset').addEventListener('click', resetSim);
['slR', 'slr', 'slH'].forEach(id => document.getElementById(id).addEventListener('input', updateLabels));

buildChart();
buildSim();
</script>
</body>
</html>
