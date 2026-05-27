
<style>
@import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Orbitron:wght@400;700;900&display=swap');
*{box-sizing:border-box;margin:0;padding:0}
.hud{background:#03040a;min-height:700px;padding:18px;font-family:'Share Tech Mono',monospace;position:relative;overflow:hidden;border-radius:12px}
.scanline{position:absolute;inset:0;background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,255,255,0.012) 2px,rgba(0,255,255,0.012) 4px);pointer-events:none;z-index:1}
.particles{position:absolute;inset:0;pointer-events:none;z-index:0}
.glow-text{text-shadow:0 0 8px currentColor,0 0 16px currentColor}
.panel{border-radius:8px;position:relative}
.c-border{border:1px solid rgba(0,255,255,0.3)}
.c-border-v{border:1px solid rgba(168,85,247,0.3)}
.c-border-p{border:1px solid rgba(236,72,153,0.3)}

.header{text-align:center;padding:16px 12px 14px;border:1px solid rgba(0,255,255,0.4);border-radius:8px;background:rgba(0,255,255,0.03);margin-bottom:14px;position:relative;z-index:2}
.holo-badge{display:inline-block;border:1px solid rgba(0,255,255,0.6);padding:3px 18px;border-radius:2px;font-size:11px;color:#00ffff;letter-spacing:3px;margin-bottom:8px;animation:pulse-c 2s ease-in-out infinite}
.username{font-family:'Orbitron',monospace;font-size:22px;font-weight:900;color:#00ffff;letter-spacing:4px;line-height:1.1}
.fullname{font-size:12px;color:#c084fc;letter-spacing:2px;margin:4px 0}
.subtitle-tag{font-size:10px;color:#f472b6;letter-spacing:1.5px;margin-top:4px;opacity:0.9}
.avatar-wrap{display:inline-block;margin:10px 0 6px;position:relative}
.avatar-hex{width:60px;height:60px;position:relative}
.avatar-hex svg{width:60px;height:60px}

.grid-main{display:grid;grid-template-columns:1fr 1.6fr 1fr;gap:10px;position:relative;z-index:2}
.panel-title{font-family:'Orbitron',monospace;font-size:9px;letter-spacing:2px;font-weight:700;padding:8px 10px 6px;border-bottom:1px solid rgba(0,255,255,0.15)}

.tech-panel{background:rgba(0,255,255,0.03);border:1px solid rgba(0,255,255,0.3);border-radius:8px}
.tech-panel .panel-title{color:#00ffff}
.tech-item{display:flex;align-items:center;gap:10px;padding:10px 10px;border-bottom:1px solid rgba(0,255,255,0.08);position:relative}
.tech-item:last-child{border-bottom:none}
.tech-icon{width:32px;height:32px;border-radius:6px;display:flex;align-items:center;justify-content:center;font-size:13px;font-weight:700;flex-shrink:0;border:1px solid}
.tech-label{font-size:11px;letter-spacing:1px}
.energy-line{position:absolute;right:0;top:50%;height:1px;width:0;animation:grow-line 1.5s ease forwards}
.tech-item:nth-child(1) .energy-line{background:rgba(0,255,255,0.5);animation-delay:0.2s}
.tech-item:nth-child(2) .energy-line{background:rgba(168,85,247,0.5);animation-delay:0.5s}
.tech-item:nth-child(3) .energy-line{background:rgba(0,255,255,0.5);animation-delay:0.8s}
.tech-item:nth-child(4) .energy-line{background:rgba(236,72,153,0.5);animation-delay:1.1s}

.projects-panel{background:rgba(168,85,247,0.03);border:1px solid rgba(168,85,247,0.3);border-radius:8px}
.projects-panel .panel-title{color:#c084fc}
.proj-card{margin:8px;border-radius:6px;background:rgba(168,85,247,0.06);border:1px solid rgba(168,85,247,0.2);padding:8px 10px;position:relative;overflow:hidden}
.proj-name{font-family:'Orbitron',monospace;font-size:10px;font-weight:700;color:#c084fc;letter-spacing:1.5px;margin-bottom:6px}
.proj-graph{height:36px;position:relative;margin-bottom:8px}
.proj-graph canvas{width:100%;height:36px}
.live-btn{display:inline-block;border:1px solid rgba(236,72,153,0.7);color:#f472b6;font-size:9px;letter-spacing:1.5px;padding:3px 10px;border-radius:2px;cursor:pointer;animation:pulse-p 2s ease-in-out infinite;font-family:'Share Tech Mono',monospace;background:transparent}
.live-dot{display:inline-block;width:5px;height:5px;border-radius:50%;background:#f472b6;margin-right:4px;animation:blink 1s ease-in-out infinite;vertical-align:middle}
.proj-card:nth-child(2){animation-delay:0.3s}
.proj-card:nth-child(3){animation-delay:0.6s}

.stats-panel{background:rgba(236,72,153,0.03);border:1px solid rgba(236,72,153,0.3);border-radius:8px}
.stats-panel .panel-title{color:#f472b6}
.stat-graph{padding:8px 10px;height:160px;position:relative}
.stat-legend{display:flex;flex-direction:column;gap:5px;padding:0 10px 8px}
.leg-item{display:flex;align-items:center;gap:6px;font-size:9px;letter-spacing:1px}
.leg-dot{width:8px;height:8px;border-radius:50%;flex-shrink:0}

.bottom-row{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-top:10px;position:relative;z-index:2}
.sys-panel{background:rgba(0,255,255,0.02);border:1px solid rgba(0,255,255,0.2);border-radius:8px;padding:10px}
.sys-title{font-family:'Orbitron',monospace;font-size:9px;letter-spacing:2px;color:#00ffff;margin-bottom:8px}
.sys-bar-row{display:flex;align-items:center;gap:8px;margin-bottom:6px;font-size:9px;letter-spacing:1px;color:rgba(0,255,255,0.7)}
.sys-bar-bg{flex:1;height:4px;background:rgba(0,255,255,0.1);border-radius:2px;overflow:hidden}
.sys-bar-fill{height:100%;border-radius:2px;animation:fill-bar 1.5s ease forwards;width:0}
.sys-val{min-width:28px;text-align:right;color:#00ffff;font-size:9px}

.connect-panel{background:rgba(236,72,153,0.02);border:1px solid rgba(236,72,153,0.25);border-radius:8px;padding:10px}
.connect-title{font-family:'Orbitron',monospace;font-size:9px;letter-spacing:2px;color:#f472b6;margin-bottom:10px}
.connect-btns{display:flex;gap:12px;align-items:center}
.conn-btn{display:flex;flex-direction:column;align-items:center;gap:5px;cursor:pointer;text-decoration:none}
.conn-circle{width:44px;height:44px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:16px;font-weight:700;border:1.5px solid;animation:pulse-orbit 2.5s ease-in-out infinite;position:relative}
.conn-circle::after{content:'';position:absolute;inset:-4px;border-radius:50%;border:1px solid;opacity:0.3;animation:pulse-orbit 2.5s ease-in-out infinite reverse}
.conn-label{font-size:8px;letter-spacing:1px;animation:blink 2s ease-in-out infinite}
.conn-li .conn-circle{color:#00ffff;border-color:rgba(0,255,255,0.6);background:rgba(0,255,255,0.06)}
.conn-li .conn-circle::after{border-color:#00ffff}
.conn-li .conn-label{color:#00ffff}
.conn-em .conn-circle{color:#f472b6;border-color:rgba(236,72,153,0.6);background:rgba(236,72,153,0.06)}
.conn-em .conn-circle::after{border-color:#f472b6}
.conn-em .conn-label{color:#f472b6}

@keyframes pulse-c{0%,100%{box-shadow:0 0 6px rgba(0,255,255,0.4)}50%{box-shadow:0 0 14px rgba(0,255,255,0.8)}}
@keyframes pulse-p{0%,100%{box-shadow:0 0 4px rgba(236,72,153,0.3)}50%{box-shadow:0 0 10px rgba(236,72,153,0.7)}}
@keyframes pulse-orbit{0%,100%{opacity:0.7}50%{opacity:1}}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0.4}}
@keyframes grow-line{0%{width:0}100%{width:100%}}
@keyframes fill-bar{0%{width:0}100%{width:var(--fill)}}
@keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-4px)}}
@keyframes spin-slow{0%{transform:rotate(0deg)}100%{transform:rotate(360deg)}}
.avatar-wrap{animation:float 3s ease-in-out infinite}
</style>

<h2 class="sr-only">Futuristic GitHub profile dashboard for THANUJAYA448, showing tech stack, recent projects, performance stats, and contact info.</h2>

<div class="hud">
<div class="scanline"></div>
<canvas class="particles" id="particles" style="position:absolute;inset:0;width:100%;height:100%;z-index:0"></canvas>

<div class="header">
  <div class="holo-badge">◈ GITHUB PROFILE INTERFACE v4.8 ◈</div>
  <div class="avatar-wrap">
    <div class="avatar-hex">
      <svg viewBox="0 0 60 60" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <clipPath id="hex"><polygon points="30,2 56,16 56,44 30,58 4,44 4,16"/></clipPath>
        </defs>
        <polygon points="30,2 56,16 56,44 30,58 4,44 4,16" fill="rgba(0,255,255,0.08)" stroke="rgba(0,255,255,0.7)" stroke-width="1.5"/>
        <polygon points="30,8 50,19 50,41 30,52 10,41 10,19" fill="rgba(168,85,247,0.12)" stroke="rgba(168,85,247,0.5)" stroke-width="1"/>
        <line x1="30" y1="2" x2="30" y2="58" stroke="rgba(0,255,255,0.2)" stroke-width="0.5"/>
        <line x1="4" y1="16" x2="56" y2="44" stroke="rgba(0,255,255,0.2)" stroke-width="0.5"/>
        <line x1="56" y1="16" x2="4" y2="44" stroke="rgba(0,255,255,0.2)" stroke-width="0.5"/>
        <circle cx="30" cy="30" r="10" fill="rgba(0,255,255,0.1)" stroke="rgba(0,255,255,0.6)" stroke-width="1"/>
        <circle cx="30" cy="30" r="5" fill="rgba(168,85,247,0.3)" stroke="rgba(168,85,247,0.8)" stroke-width="1"/>
        <circle cx="30" cy="30" r="2" fill="#00ffff"/>
      </svg>
    </div>
  </div>
  <div class="username glow-text">THANUJAYA448</div>
  <div class="fullname">THANUJAYA HASARANGA PERERA</div>
  <div class="subtitle-tag">◆ FUTURISTIC DEVELOPER &amp; DIGITAL ARCHITECT ◆</div>
</div>

<div class="grid-main">
  <div class="tech-panel panel">
    <div class="panel-title">◈ TECH STACK</div>
    <div class="tech-item">
      <div class="tech-icon" style="color:#61dafb;border-color:rgba(97,218,251,0.5);background:rgba(97,218,251,0.08)">Re</div>
      <div>
        <div class="tech-label" style="color:#61dafb">React</div>
        <div style="font-size:8px;color:rgba(97,218,251,0.5);letter-spacing:1px">UI ENGINE</div>
      </div>
      <div class="energy-line"></div>
    </div>
    <div class="tech-item">
      <div class="tech-icon" style="color:#fbbf24;border-color:rgba(251,191,36,0.5);background:rgba(251,191,36,0.08)">Py</div>
      <div>
        <div class="tech-label" style="color:#fbbf24">Python</div>
        <div style="font-size:8px;color:rgba(251,191,36,0.5);letter-spacing:1px">CORE LANG</div>
      </div>
      <div class="energy-line"></div>
    </div>
    <div class="tech-item">
      <div class="tech-icon" style="color:#00ffff;border-color:rgba(0,255,255,0.5);background:rgba(0,255,255,0.08)">GH</div>
      <div>
        <div class="tech-label" style="color:#00ffff">GitHub</div>
        <div style="font-size:8px;color:rgba(0,255,255,0.5);letter-spacing:1px">VERSION CTRL</div>
      </div>
      <div class="energy-line"></div>
    </div>
    <div class="tech-item">
      <div class="tech-icon" style="color:#f472b6;border-color:rgba(244,114,182,0.5);background:rgba(244,114,182,0.08)">Fi</div>
      <div>
        <div class="tech-label" style="color:#f472b6">Figma</div>
        <div style="font-size:8px;color:rgba(244,114,182,0.5);letter-spacing:1px">DESIGN SYS</div>
      </div>
      <div class="energy-line"></div>
    </div>
  </div>

  <div class="projects-panel panel">
    <div class="panel-title">◈ RECENT PROJECTS</div>
    <div class="proj-card">
      <div class="proj-name">CYBERNETIC UI</div>
      <div class="proj-graph"><canvas id="g1" width="200" height="36"></canvas></div>
      <span class="live-btn"><span class="live-dot"></span>LIVE DEMO</span>
    </div>
    <div class="proj-card">
      <div class="proj-name">DATA SPHERE</div>
      <div class="proj-graph"><canvas id="g2" width="200" height="36"></canvas></div>
      <span class="live-btn"><span class="live-dot"></span>LIVE DEMO</span>
    </div>
    <div class="proj-card">
      <div class="proj-name">AETHERNET</div>
      <div class="proj-graph"><canvas id="g3" width="200" height="36"></canvas></div>
      <span class="live-btn"><span class="live-dot"></span>LIVE DEMO</span>
    </div>
  </div>

  <div class="stats-panel panel">
    <div class="panel-title">◈ PERFORMANCE STATS</div>
    <div class="stat-graph"><canvas id="stats-chart" width="180" height="150"></canvas></div>
    <div class="stat-legend">
      <div class="leg-item"><div class="leg-dot" style="background:#00ffff"></div><span style="color:rgba(0,255,255,0.8)">COMMITS</span></div>
      <div class="leg-item"><div class="leg-dot" style="background:#f472b6"></div><span style="color:rgba(244,114,182,0.8)">STARS</span></div>
      <div class="leg-item"><div class="leg-dot" style="background:#c084fc"></div><span style="color:rgba(192,132,252,0.8)">PULL REQUESTS</span></div>
    </div>
  </div>
</div>

<div class="bottom-row">
  <div class="sys-panel">
    <div class="sys-title">◈ SYSTEM STATUS</div>
    <div class="sys-bar-row">
      <span style="min-width:52px">ACTIVITY</span>
      <div class="sys-bar-bg"><div class="sys-bar-fill" style="background:#00ffff;--fill:87%"></div></div>
      <span class="sys-val">87%</span>
    </div>
    <div class="sys-bar-row">
      <span style="min-width:52px">REPOS</span>
      <div class="sys-bar-bg"><div class="sys-bar-fill" style="background:#c084fc;--fill:64%;animation-delay:0.2s"></div></div>
      <span class="sys-val">64%</span>
    </div>
    <div class="sys-bar-row">
      <span style="min-width:52px">COLLAB</span>
      <div class="sys-bar-bg"><div class="sys-bar-fill" style="background:#f472b6;--fill:73%;animation-delay:0.4s"></div></div>
      <span class="sys-val">73%</span>
    </div>
    <div class="sys-bar-row">
      <span style="min-width:52px">UPTIME</span>
      <div class="sys-bar-bg"><div class="sys-bar-fill" style="background:#00ffff;--fill:99%;animation-delay:0.6s"></div></div>
      <span class="sys-val">99%</span>
    </div>
    <div style="margin-top:8px;font-size:8px;color:rgba(0,255,255,0.4);letter-spacing:1px;animation:blink 3s ease-in-out infinite">● ALL SYSTEMS NOMINAL</div>
  </div>

  <div class="connect-panel">
    <div class="connect-title">◈ CONNECT WITH ME</div>
    <div class="connect-btns">
      <a class="conn-btn conn-li" href="https://linkedin.com" target="_blank" title="LinkedIn">
        <div class="conn-circle">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
        </div>
        <span class="conn-label">CLICK TO OPEN</span>
      </a>
      <a class="conn-btn conn-em" href="mailto:thanujaya@email.com" title="Email">
        <div class="conn-circle">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="M22 7l-10 7L2 7"/></svg>
        </div>
        <span class="conn-label">CLICK TO OPEN</span>
      </a>
      <div style="margin-left:auto;font-size:8px;color:rgba(0,255,255,0.35);letter-spacing:1px;text-align:right;line-height:1.8">
        <div style="animation:blink 2s ease-in-out infinite">◈ SECURE LINK</div>
        <div style="animation:blink 2.5s ease-in-out infinite">◈ ENCRYPTED</div>
        <div style="animation:blink 3s ease-in-out infinite">◈ VERIFIED</div>
      </div>
    </div>
  </div>
</div>

</div>

<script>
(function(){
const pal=['#00ffff','#f472b6','#c084fc','#38bdf8','#a78bfa'];

function miniGraph(id,color,offset){
  const c=document.getElementById(id);if(!c)return;
  const ctx=c.getContext('2d');const w=c.offsetWidth||c.parentElement.offsetWidth||200;c.width=w;c.height=36;
  const pts=Array.from({length:12},(_,i)=>10+Math.sin(i*0.8+offset)*12+Math.random()*8);
  const grad=ctx.createLinearGradient(0,0,0,36);
  grad.addColorStop(0,color.replace(')',',0.25)').replace('rgb','rgba'));
  grad.addColorStop(1,'transparent');
  ctx.beginPath();ctx.moveTo(0,36);
  pts.forEach((p,i)=>{const x=i/(pts.length-1)*w;ctx.lineTo(x,36-p)});
  ctx.lineTo(w,36);ctx.closePath();
  const fr=parseInt(color.slice(1,3),16),fg=parseInt(color.slice(3,5),16),fb=parseInt(color.slice(5,7),16);
  const g2=ctx.createLinearGradient(0,0,0,36);
  g2.addColorStop(0,`rgba(${fr},${fg},${fb},0.25)`);g2.addColorStop(1,'transparent');
  ctx.fillStyle=g2;ctx.fill();
  ctx.beginPath();pts.forEach((p,i)=>{const x=i/(pts.length-1)*w;i===0?ctx.moveTo(x,36-p):ctx.lineTo(x,36-p)});
  ctx.strokeStyle=color;ctx.lineWidth=1.5;ctx.stroke();
  pts.forEach((p,i)=>{const x=i/(pts.length-1)*w;ctx.beginPath();ctx.arc(x,36-p,2,0,Math.PI*2);ctx.fillStyle=color;ctx.fill()});
}
miniGraph('g1','#c084fc',0);
miniGraph('g2','#00ffff',1);
miniGraph('g3','#f472b6',2);

const sc=document.getElementById('stats-chart');
if(sc){
  const ctx=sc.getContext('2d');const w=sc.offsetWidth||sc.parentElement.offsetWidth||180;sc.width=w;sc.height=150;
  const labels=[0,5,10,15,20,25,30];const n=7;const pad=24;const bh=sc.height-pad*2;const bw=sc.width-pad*2;
  ctx.strokeStyle='rgba(0,255,255,0.1)';ctx.lineWidth=0.5;
  labels.forEach((v,i)=>{const y=pad+bh*(1-i/6);ctx.beginPath();ctx.moveTo(pad,y);ctx.lineTo(w-8,y);ctx.stroke();ctx.fillStyle='rgba(0,255,255,0.35)';ctx.font='8px monospace';ctx.textAlign='right';ctx.fillText(v,pad-3,y+3)});
  const datasets=[
    {color:'#00ffff',data:[3,8,14,20,18,25,28]},
    {color:'#f472b6',data:[1,4,9,12,16,22,26]},
    {color:'#c084fc',data:[2,6,10,8,14,18,24]}
  ];
  datasets.forEach(ds=>{
    ctx.beginPath();
    ds.data.forEach((v,i)=>{const x=pad+i/6*bw;const y=pad+bh*(1-v/30);i===0?ctx.moveTo(x,y):ctx.lineTo(x,y)});
    ctx.strokeStyle=ds.color;ctx.lineWidth=1.5;ctx.stroke();
    ds.data.forEach((v,i)=>{const x=pad+i/6*bw;const y=pad+bh*(1-v/30);ctx.beginPath();ctx.arc(x,y,2.5,0,Math.PI*2);ctx.fillStyle=ds.color;ctx.fill()});
  });
}

const pc=document.getElementById('particles');
if(pc){
  const ctx=pc.getContext('2d');const pw=pc.offsetWidth||680;const ph=pc.offsetHeight||700;pc.width=pw;pc.height=ph;
  const particles=Array.from({length:40},()=>({x:Math.random()*pw,y:Math.random()*ph,vx:(Math.random()-0.5)*0.4,vy:(Math.random()-0.5)*0.4,r:Math.random()*1.5+0.5,c:pal[Math.floor(Math.random()*pal.length)]}));
  function drawP(){
    ctx.clearRect(0,0,pw,ph);
    particles.forEach(p=>{
      p.x+=p.vx;p.y+=p.vy;
      if(p.x<0)p.x=pw;if(p.x>pw)p.x=0;if(p.y<0)p.y=ph;if(p.y>ph)p.y=0;
      const cr=parseInt(p.c.slice(1,3),16),cg=parseInt(p.c.slice(3,5),16),cb=parseInt(p.c.slice(5,7),16);
      ctx.beginPath();ctx.arc(p.x,p.y,p.r,0,Math.PI*2);
      ctx.fillStyle=`rgba(${cr},${cg},${cb},0.5)`;ctx.fill();
    });
    requestAnimationFrame(drawP);
  }
  drawP();
}
})();
</script>
