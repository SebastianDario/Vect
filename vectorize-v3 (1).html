<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vectorize Pro — Alta Fidelidad</title>
<!-- ImageTracer.js official CDN -->
<script src="https://cdn.jsdelivr.net/npm/imagetracerjs@1.2.6/imagetracer_v1.2.6.min.js"></script>
<!-- OpenCV.js -->
<script async src="https://docs.opencv.org/4.x/opencv.js" onload="window._cvReady=true;log('OpenCV.js listo','ok')" onerror="window._cvReady=false;log('OpenCV.js no disponible — usando fallback','warn')"></script>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#0d1117;--bg2:#161b22;--bg3:#21262d;
  --border:#30363d;--border2:#484f58;
  --txt:#e6edf3;--txt2:#8b949e;--txt3:#484f58;
  --hi:#d2ff47;--ok:#3fb950;--err:#f85149;--warn:#e3b341;--info:#58a6ff;
}
html{-webkit-font-smoothing:antialiased}
body{font-family:'Segoe UI',system-ui,sans-serif;background:var(--bg);color:var(--txt);min-height:100vh;padding:20px 24px 48px}

/* HEADER */
.hdr{display:flex;align-items:center;gap:12px;margin-bottom:20px;padding-bottom:16px;border-bottom:1px solid var(--border)}
.logo{width:32px;height:32px;background:var(--hi);border-radius:8px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.logo svg{width:16px;height:16px}
.hdr-t{font-size:18px;font-weight:700;letter-spacing:-.02em}
.hdr-sub{font-size:12px;color:var(--txt2);margin-left:auto}
.cv-status{font-size:10px;padding:3px 8px;border-radius:100px;font-weight:600;background:var(--bg3);border:1px solid var(--border);color:var(--txt2);font-family:monospace}
.cv-status.ok{border-color:rgba(63,185,80,.3);color:var(--ok);background:rgba(63,185,80,.08)}
.cv-status.warn{border-color:rgba(227,179,65,.3);color:var(--warn);background:rgba(227,179,65,.08)}

/* DROP */
.drop{border:2px dashed var(--border);border-radius:10px;padding:28px;text-align:center;cursor:pointer;transition:all .2s;position:relative;margin-bottom:14px}
.drop:hover,.drop.over{border-color:var(--hi);background:rgba(210,255,71,.02)}
.drop.has-file{border-color:rgba(210,255,71,.3);border-style:solid}
.drop input{position:absolute;inset:0;opacity:0;cursor:pointer;width:100%}
.drop-txt{font-size:14px;color:var(--txt2)}
.drop-txt strong{color:var(--txt)}

/* GRID CONTROLS */
.ctrls{display:grid;grid-template-columns:repeat(auto-fill,minmax(200px,1fr));gap:12px;margin-bottom:14px}
.ctrl{display:flex;flex-direction:column;gap:5px;background:var(--bg2);border:1px solid var(--border);border-radius:8px;padding:10px 12px}
.ctrl-hdr{display:flex;justify-content:space-between;align-items:center}
.ctrl-lbl{font-size:10px;font-weight:700;color:var(--txt2);text-transform:uppercase;letter-spacing:.06em}
.ctrl-val{font-size:11px;color:var(--hi);font-family:monospace;font-weight:700}
input[type=range]{width:100%;accent-color:var(--hi);height:4px;margin-top:2px}
select,input[type=number]{background:var(--bg3);border:1px solid var(--border);color:var(--txt);padding:4px 8px;border-radius:6px;font-size:12px;width:100%}

/* MODE TABS */
.modes{display:flex;gap:6px;margin-bottom:14px;flex-wrap:wrap}
.mode-btn{padding:6px 14px;border-radius:6px;border:1px solid var(--border);background:var(--bg2);color:var(--txt2);font-size:12px;font-weight:600;cursor:pointer;transition:all .15s}
.mode-btn:hover{border-color:var(--border2);color:var(--txt)}
.mode-btn.active{border-color:var(--hi);color:var(--hi);background:rgba(210,255,71,.06)}

/* BTNS */
.btns{display:flex;gap:8px;margin-bottom:16px;flex-wrap:wrap}
.btn{padding:8px 18px;border-radius:7px;border:none;font-size:13px;font-weight:700;cursor:pointer;transition:all .15s;display:flex;align-items:center;gap:6px;white-space:nowrap}
.btn-hi{background:var(--hi);color:var(--bg)}
.btn-hi:hover{background:#bcef20;transform:translateY(-1px)}
.btn-hi:disabled{opacity:.35;cursor:not-allowed;transform:none}
.btn-sec{background:var(--bg2);color:var(--txt);border:1px solid var(--border)}
.btn-sec:hover{background:var(--bg3);border-color:var(--border2)}
.btn-sec:disabled{opacity:.35;cursor:not-allowed}
.spin{display:inline-block;width:13px;height:13px;border:2px solid transparent;border-top-color:var(--bg);border-radius:50%;animation:sp .6s linear infinite}
@keyframes sp{to{transform:rotate(360deg)}}

/* PROGRESS */
.prow{display:flex;align-items:center;gap:10px;margin-bottom:12px}
.pbar-w{flex:1;height:4px;background:var(--bg3);border-radius:2px;overflow:hidden}
.pbar{height:100%;background:linear-gradient(90deg,var(--hi),#47d2ff);border-radius:2px;width:0;transition:width .28s cubic-bezier(.4,0,.2,1)}
.pstep{font-family:monospace;font-size:11px;color:var(--txt2);min-width:260px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}

/* PANELS */
.panels{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:14px}
@media(max-width:680px){.panels{grid-template-columns:1fr}}
.panel{background:var(--bg2);border:1px solid var(--border);border-radius:10px;overflow:hidden}
.panel-hdr{padding:8px 13px;background:var(--bg);border-bottom:1px solid var(--border);font-size:10px;font-weight:700;color:var(--txt2);text-transform:uppercase;letter-spacing:.07em;display:flex;justify-content:space-between;align-items:center;gap:8px}
.pbadge{font-family:monospace;font-size:10px;padding:2px 7px;border-radius:100px;background:var(--bg3);border:1px solid var(--border);color:var(--txt2)}
.pbadge.ok{border-color:rgba(63,185,80,.3);color:var(--ok);background:rgba(63,185,80,.06)}
.pbadge.err{border-color:rgba(248,81,73,.3);color:var(--err);background:rgba(248,81,73,.06)}
.panel-body{min-height:300px;display:flex;align-items:center;justify-content:center;padding:10px;background:repeating-conic-gradient(var(--bg2) 0% 25%,var(--bg) 0% 50%) 0 0/18px 18px;position:relative}
.panel-body img,.panel-body svg{max-width:100%;max-height:340px;object-fit:contain;display:block}
.ph{color:var(--txt3);font-size:12px;text-align:center}

/* STATS */
.stats{display:flex;flex-wrap:wrap;gap:10px;padding:10px 13px;background:var(--bg2);border:1px solid var(--border);border-radius:8px;margin-bottom:14px}
.stat{display:flex;flex-direction:column;gap:1px}
.stat-l{font-size:9px;color:var(--txt3);text-transform:uppercase;letter-spacing:.06em;font-weight:700}
.stat-v{font-family:monospace;font-size:12px;color:var(--txt);font-weight:700}
.stat-v.ok{color:var(--ok)}.stat-v.err{color:var(--err)}

/* LOG */
.log{background:var(--bg);border:1px solid var(--border);border-radius:8px;padding:10px 13px;font-family:'JetBrains Mono','Courier New',monospace;font-size:11px;max-height:180px;overflow-y:auto;display:flex;flex-direction:column;gap:2px}
.log:empty::before{content:'// pipeline log';color:var(--txt3)}
.ll{display:flex;gap:7px;line-height:1.5}
.ll .ts{color:var(--txt3);flex-shrink:0;min-width:42px}
.ll .msg{color:var(--txt2)}
.ll.ok .msg{color:var(--ok)}.ll.err .msg{color:var(--err)}.ll.warn .msg{color:var(--warn)}.ll.info .msg{color:var(--hi)}

/* DEBUG STAGES */
.dbg{background:var(--bg2);border:1px solid var(--border);border-radius:8px;margin-top:12px;overflow:hidden}
.dbg-hdr{padding:8px 13px;display:flex;align-items:center;justify-content:space-between;cursor:pointer}
.dbg-hdr:hover{background:var(--bg3)}
.dbg-title{font-size:10px;font-weight:700;color:var(--txt3);text-transform:uppercase;letter-spacing:.07em;display:flex;align-items:center;gap:6px}
.dbg-dot{width:6px;height:6px;border-radius:50%;background:var(--txt3)}
.dbg-dot.on{background:var(--hi);box-shadow:0 0 5px rgba(210,255,71,.5)}
.dbg-body{display:none;padding:10px;display:none}
.dbg-body.open{display:grid;grid-template-columns:repeat(auto-fill,minmax(140px,1fr));gap:8px}
.dbg-stage{display:flex;flex-direction:column;gap:4px}
.dbg-lbl{font-size:9px;color:var(--txt3);font-family:monospace;text-transform:uppercase;letter-spacing:.05em}
.dbg-canvas{width:100%;aspect-ratio:1;border-radius:5px;background:var(--bg3);border:1px solid var(--border);display:flex;align-items:center;justify-content:center;overflow:hidden}
.dbg-canvas canvas,.dbg-canvas img{max-width:100%;max-height:100%;object-fit:contain}
.dbg-empty{font-size:9px;color:var(--txt3);font-family:monospace}
</style>
</head>
<body>

<div class="hdr">
  <div class="logo"><svg viewBox="0 0 16 16" fill="none"><polygon points="8,1 15,14 1,14" fill="#0d1117"/><line x1="4.5" y1="11" x2="11.5" y2="11" stroke="#0d1117" stroke-width="1.5" stroke-linecap="round"/></svg></div>
  <div><div class="hdr-t">Vectorize Pro</div></div>
  <div class="hdr-sub">Alta fidelidad · ImageTracer.js oficial · OpenCV.js</div>
  <div class="cv-status" id="cvStatus">OpenCV cargando…</div>
</div>

<!-- DROP -->
<div class="drop" id="drop">
  <input type="file" id="fileIn" accept="image/jpeg,image/png,image/webp,image/bmp">
  <div class="drop-txt" id="dropTxt"><strong>Arrastra tu imagen aquí</strong><br>JPG · PNG · WEBP — sin límites</div>
</div>

<!-- MODES -->
<div class="modes" id="modeRow">
  <button class="mode-btn active" data-mode="logo" onclick="setMode(this)">🎯 Logo</button>
  <button class="mode-btn" data-mode="tshirt" onclick="setMode(this)">👕 Camiseta</button>
  <button class="mode-btn" data-mode="tattoo" onclick="setMode(this)">🖤 Tatuaje</button>
  <button class="mode-btn" data-mode="lineart" onclick="setMode(this)">✏️ Line Art</button>
  <button class="mode-btn" data-mode="botanical" onclick="setMode(this)">🌿 Botánico</button>
  <button class="mode-btn" data-mode="multi" onclick="setMode(this)">🎨 Multicolor</button>
</div>

<!-- CONTROLS -->
<div class="ctrls" id="ctrlGrid">
  <div class="ctrl">
    <div class="ctrl-hdr"><span class="ctrl-lbl">Threshold</span><span class="ctrl-val" id="vThr">128</span></div>
    <input type="range" id="sThr" min="1" max="254" value="128" oninput="sv('Thr',this.value)">
  </div>
  <div class="ctrl">
    <div class="ctrl-hdr"><span class="ctrl-lbl">Tolerancia Bézier</span><span class="ctrl-val" id="vTol">1</span></div>
    <input type="range" id="sTol" min="1" max="30" value="1" oninput="sv('Tol',this.value)">
  </div>
  <div class="ctrl">
    <div class="ctrl-hdr"><span class="ctrl-lbl">Path mínimo (px)</span><span class="ctrl-val" id="vMin">4</span></div>
    <input type="range" id="sMin" min="1" max="40" value="4" oninput="sv('Min',this.value)">
  </div>
  <div class="ctrl">
    <div class="ctrl-hdr"><span class="ctrl-lbl">Blur denoising</span><span class="ctrl-val" id="vBlur">1</span></div>
    <input type="range" id="sBlur" min="0" max="5" value="1" oninput="sv('Blur',this.value)">
  </div>
  <div class="ctrl" id="ccCtrl" style="display:none">
    <div class="ctrl-hdr"><span class="ctrl-lbl">Colores</span><span class="ctrl-val" id="vCC">8</span></div>
    <input type="range" id="sCC" min="2" max="32" value="8" oninput="sv('CC',this.value)">
  </div>
  <div class="ctrl">
    <div class="ctrl-hdr"><span class="ctrl-lbl">Escala salida</span><span class="ctrl-val" id="vScl">1.0x</span></div>
    <input type="range" id="sScl" min="5" max="30" value="10" oninput="sv('Scl',(this.value/10).toFixed(1)+'x')">
  </div>
</div>

<!-- BTNS -->
<div class="btns">
  <button class="btn btn-hi" id="btnRun" disabled><span id="btnIco">⚡</span> Vectorizar</button>
  <button class="btn btn-sec" id="btnSVG" disabled>↓ SVG</button>
  <button class="btn btn-sec" id="btnPNG" disabled>↓ PNG</button>
  <button class="btn btn-sec" id="btnCopy" disabled>⎘ Copiar SVG</button>
</div>

<!-- PROGRESS -->
<div class="prow"><div class="pstep" id="pstep">idle</div><div class="pbar-w"><div class="pbar" id="pbar"></div></div></div>

<!-- STATS -->
<div class="stats" id="statsBar">
  <div class="stat"><div class="stat-l">Engine</div><div class="stat-v" id="stEng">—</div></div>
  <div class="stat"><div class="stat-l">Paths</div><div class="stat-v" id="stP">—</div></div>
  <div class="stat"><div class="stat-l">Nodos</div><div class="stat-v" id="stN">—</div></div>
  <div class="stat"><div class="stat-l">Tamaño</div><div class="stat-v" id="stSz">—</div></div>
  <div class="stat"><div class="stat-l">Dimensiones</div><div class="stat-v" id="stDm">—</div></div>
  <div class="stat"><div class="stat-l">Tiempo</div><div class="stat-v" id="stTm">—</div></div>
</div>

<!-- PANELS -->
<div class="panels">
  <div class="panel">
    <div class="panel-hdr">Original <span class="pbadge" id="bdOrig">sin imagen</span></div>
    <div class="panel-body" id="pOrig"><div class="ph">Sube una imagen</div></div>
  </div>
  <div class="panel">
    <div class="panel-hdr">SVG Vectorizado <span class="pbadge" id="bdSVG">pendiente</span></div>
    <div class="panel-body" id="pSVG" style="background:#fff"><div class="ph">Resultado aquí</div></div>
  </div>
</div>

<!-- LOG -->
<div class="log" id="logEl"></div>

<!-- DEBUG -->
<div class="dbg" id="dbgPanel">
  <div class="dbg-hdr" onclick="toggleDbg()">
    <div class="dbg-title"><div class="dbg-dot" id="dbgDot"></div>Debug Pipeline</div>
    <span style="font-size:10px;color:var(--txt3)" id="dbgToggle">▼ abrir</span>
  </div>
  <div class="dbg-body" id="dbgBody">
    <div class="dbg-stage"><div class="dbg-lbl">01 · Original</div><div class="dbg-canvas" id="d1"><div class="dbg-empty">—</div></div></div>
    <div class="dbg-stage"><div class="dbg-lbl">02 · Blur</div><div class="dbg-canvas" id="d2"><div class="dbg-empty">—</div></div></div>
    <div class="dbg-stage"><div class="dbg-lbl">03 · Contraste</div><div class="dbg-canvas" id="d3"><div class="dbg-empty">—</div></div></div>
    <div class="dbg-stage"><div class="dbg-lbl">04 · Edges</div><div class="dbg-canvas" id="d4"><div class="dbg-empty">—</div></div></div>
    <div class="dbg-stage"><div class="dbg-lbl">05 · Threshold</div><div class="dbg-canvas" id="d5"><div class="dbg-empty">—</div></div></div>
    <div class="dbg-stage"><div class="dbg-lbl">06 · SVG final</div><div class="dbg-canvas" id="d6"><div class="dbg-empty">—</div></div></div>
  </div>
</div>

<script>
'use strict';
// ═══════════════════════════════════════════════════════════
//  STATE
// ═══════════════════════════════════════════════════════════
var APP = {
  file: null, dataURL: null, origCanvas: null,
  svg: null, mode: 'logo', busy: false, t0: 0
};

// ═══════════════════════════════════════════════════════════
//  LOG
// ═══════════════════════════════════════════════════════════
function log(msg, type) {
  type = type || 'info';
  var el = document.getElementById('logEl');
  var ll = document.createElement('div');
  ll.className = 'll ' + type;
  var ts = APP.t0 ? ((Date.now()-APP.t0)/1000).toFixed(2)+'s' : '0.00s';
  ll.innerHTML = '<span class="ts">'+ts+'</span><span class="msg">'+msg+'</span>';
  el.appendChild(ll);
  el.scrollTop = el.scrollHeight;
  console.log('[VEC] '+msg);
}
function logClear(){ document.getElementById('logEl').innerHTML=''; APP.t0=Date.now(); }

// ═══════════════════════════════════════════════════════════
//  PROGRESS
// ═══════════════════════════════════════════════════════════
function progress(pct, msg) {
  document.getElementById('pbar').style.width = Math.max(0,pct)+'%';
  if (msg) document.getElementById('pstep').textContent = msg;
}

// ═══════════════════════════════════════════════════════════
//  CV STATUS
// ═══════════════════════════════════════════════════════════
function checkCV() {
  var el = document.getElementById('cvStatus');
  if (window.cv && window.cv.Mat) {
    el.textContent = 'OpenCV listo'; el.className = 'cv-status ok';
  } else if (window._cvReady === false) {
    el.textContent = 'Sin OpenCV (fallback JS)'; el.className = 'cv-status warn';
  } else {
    el.textContent = 'OpenCV cargando…';
    setTimeout(checkCV, 500);
  }
}
setTimeout(checkCV, 800);

// ═══════════════════════════════════════════════════════════
//  FILE UPLOAD
// ═══════════════════════════════════════════════════════════
var drop = document.getElementById('drop');
document.getElementById('fileIn').addEventListener('change', function(e){ if(e.target.files[0]) loadFile(e.target.files[0]); });
drop.addEventListener('dragover', function(e){ e.preventDefault(); drop.classList.add('over'); });
drop.addEventListener('dragleave', function(){ drop.classList.remove('over'); });
drop.addEventListener('drop', function(e){ e.preventDefault(); drop.classList.remove('over'); if(e.dataTransfer.files[0]) loadFile(e.dataTransfer.files[0]); });

function loadFile(f) {
  var ok = ['image/jpeg','image/png','image/webp','image/bmp'];
  if (!ok.includes(f.type)) { log('Formato no soportado: '+f.type,'err'); return; }
  logClear();
  log('Cargando: '+f.name+' ('+fmtB(f.size)+')');
  var url = URL.createObjectURL(f);
  var img = new Image();
  img.onload = function() {
    var MAX = 1200, w = img.naturalWidth, h = img.naturalHeight;
    if (w>MAX||h>MAX){ var r=Math.min(MAX/w,MAX/h); w=Math.round(w*r); h=Math.round(h*r); }
    var c = document.createElement('canvas'); c.width=w; c.height=h;
    var ctx = c.getContext('2d');
    ctx.fillStyle='#ffffff'; ctx.fillRect(0,0,w,h);
    ctx.drawImage(img,0,0,w,h);
    URL.revokeObjectURL(url);
    APP.origCanvas = c; APP.dataURL = c.toDataURL('image/png'); APP.svg = null;
    // Show original
    var po = document.getElementById('pOrig'); po.innerHTML='';
    var timg = document.createElement('img');
    timg.src = c.toDataURL('image/jpeg',0.85);
    timg.style.cssText='max-width:100%;max-height:340px;object-fit:contain;display:block';
    po.appendChild(timg);
    document.getElementById('bdOrig').textContent=w+'×'+h; document.getElementById('bdOrig').className='pbadge ok';
    document.getElementById('dropTxt').innerHTML='<strong>'+f.name+'</strong> · '+w+'×'+h;
    drop.classList.add('has-file');
    document.getElementById('btnRun').disabled=false;
    ['btnSVG','btnPNG','btnCopy'].forEach(function(id){document.getElementById(id).disabled=true;});
    document.getElementById('pSVG').innerHTML='<div class="ph">Haz clic en Vectorizar</div>';
    document.getElementById('pSVG').style.background='';
    document.getElementById('bdSVG').textContent='pendiente'; document.getElementById('bdSVG').className='pbadge';
    dbgSet('d1',c);
    log('Imagen lista: '+w+'×'+h,'ok');
    progress(5,'Listo para vectorizar');
  };
  img.onerror=function(){ log('Error al cargar','err'); URL.revokeObjectURL(url); };
  img.src=url;
}

// ═══════════════════════════════════════════════════════════
//  MODE
// ═══════════════════════════════════════════════════════════
var MODES = {
  logo:      { thr:160, tol:2,  min:4,  blur:1, cc:4,  scl:10, desc:'Bordes nítidos, pocos nodos, curvas limpias' },
  tshirt:    { thr:140, tol:3,  min:3,  blur:1, cc:8,  scl:10, desc:'Preserva detalle, limpia ruido textil' },
  tattoo:    { thr:200, tol:1,  min:2,  blur:2, cc:2,  scl:10, desc:'Alto contraste, negro puro, stencil' },
  lineart:   { thr:180, tol:1,  min:2,  blur:0, cc:2,  scl:10, desc:'Líneas finas, máxima fidelidad' },
  botanical: { thr:150, tol:1,  min:1,  blur:0, cc:4,  scl:10, desc:'Grabado botánico, máximo detalle' },
  multi:     { thr:128, tol:4,  min:5,  blur:1, cc:16, scl:10, desc:'Cuantización de color, imágenes complejas' }
};
function setMode(el) {
  document.querySelectorAll('.mode-btn').forEach(function(b){b.classList.remove('active');});
  el.classList.add('active'); APP.mode = el.dataset.mode;
  var m = MODES[APP.mode];
  document.getElementById('sThr').value=m.thr; sv('Thr',m.thr);
  document.getElementById('sTol').value=m.tol; sv('Tol',m.tol);
  document.getElementById('sMin').value=m.min; sv('Min',m.min);
  document.getElementById('sBlur').value=m.blur; sv('Blur',m.blur);
  document.getElementById('sCC').value=m.cc; sv('CC',m.cc);
  document.getElementById('sScl').value=m.scl; sv('Scl',(m.scl/10).toFixed(1)+'x');
  document.getElementById('ccCtrl').style.display = APP.mode==='multi'?'':'none';
}
function sv(k,v){ var el=document.getElementById('v'+k); if(el) el.textContent=v; }

// ═══════════════════════════════════════════════════════════
//  VECTORIZE ENTRY
// ═══════════════════════════════════════════════════════════
document.getElementById('btnRun').onclick = function(){ if(!APP.busy && APP.origCanvas) startVectorize(); };

function startVectorize() {
  APP.busy=true; logClear();
  document.getElementById('btnRun').disabled=true;
  document.getElementById('btnRun').innerHTML='<span class="spin"></span> Procesando…';
  ['btnSVG','btnPNG','btnCopy'].forEach(function(id){document.getElementById(id).disabled=true;});
  progress(0,'Iniciando…');
  setTimeout(runPipeline, 20);
}

// ═══════════════════════════════════════════════════════════
//  MAIN PIPELINE
// ═══════════════════════════════════════════════════════════
function runPipeline() {
  var t0 = Date.now();
  var thr  = parseInt(document.getElementById('sThr').value);
  var tol  = parseFloat(document.getElementById('sTol').value);
  var minPx= parseInt(document.getElementById('sMin').value);
  var blurR= parseInt(document.getElementById('sBlur').value);
  var nc   = parseInt(document.getElementById('sCC').value);
  var scl  = parseFloat(document.getElementById('sScl').value)/10;
  var mode = APP.mode;

  log('Pipeline · mode='+mode+' thr='+thr+' tol='+tol+' min='+minPx+' blur='+blurR+' nc='+nc+' scl='+scl);

  try {
    // ── STEP 1: Preprocess ──────────────────────────────────
    progress(10,'Preprocesando imagen…');
    log('Step 1/5 · Preprocessing');
    var prepCanvas = preprocess(APP.origCanvas, mode, blurR, thr);
    dbgSet('d2', prepCanvas);

    // ── STEP 2: Contrast + Edge ─────────────────────────────
    progress(22,'Mejora de contraste + bordes…');
    log('Step 2/5 · Contraste + edges');
    var contrastCanvas = enhanceContrast(prepCanvas);
    dbgSet('d3', contrastCanvas);
    var edgeCanvas = detectEdges(prepCanvas);
    dbgSet('d4', edgeCanvas);

    // ── STEP 3: Threshold / Quant ──────────────────────────
    progress(38,'Threshold / cuantización…');
    log('Step 3/5 · Threshold (thr='+thr+')');
    var thrCanvas;
    if (mode === 'multi') {
      thrCanvas = contrastCanvas; // keep color for multicolor
    } else {
      thrCanvas = applyThreshold(contrastCanvas, mode, thr);
    }
    dbgSet('d5', thrCanvas);

    // ── STEP 4: ImageTracer.js official ───────────────────
    progress(55,'Vectorizando con ImageTracer.js oficial…');
    log('Step 4/5 · ImageTracer.js oficial CDN');
    var svgStr = traceWithImageTracer(thrCanvas, mode, tol, minPx, nc, scl);

    // Validate
    var pathCount = (svgStr.match(/<path/g)||[]).length;
    log('ImageTracer result: paths='+pathCount+' size='+fmtB(new Blob([svgStr]).size));

    // Recovery if too few paths
    if (pathCount < 3) {
      log('Pocos paths ('+pathCount+'). Reintentando con parámetros alternativos…','warn');
      svgStr = traceRetry(APP.origCanvas, thr, tol, minPx, nc, scl);
      pathCount = (svgStr.match(/<path/g)||[]).length;
      log('Retry result: paths='+pathCount,'warn');
    }

    // ── STEP 5: Finalize ───────────────────────────────────
    progress(85,'Finalizando SVG…');
    log('Step 5/5 · Finalizando');
    var finalSVG = finalizeSVG(svgStr);

    var finalPaths = (finalSVG.match(/<path/g)||[]).length;
    var finalNodes = (finalSVG.match(/[MLQZmlqz]/g)||[]).length;
    var svgSz = new Blob([finalSVG]).size;
    var elapsed = Date.now()-t0;

    log('✓ Completo · paths='+finalPaths+' nodes='+finalNodes+' size='+fmtB(svgSz)+' time='+elapsed+'ms','ok');
    progress(100,'Completo');

    document.getElementById('stEng').textContent = 'ImageTracer.js';
    document.getElementById('stP').textContent=finalPaths; document.getElementById('stP').className='stat-v '+(finalPaths>0?'ok':'err');
    document.getElementById('stN').textContent=finalNodes;
    document.getElementById('stSz').textContent=fmtB(svgSz);
    document.getElementById('stDm').textContent=APP.origCanvas.width+'×'+APP.origCanvas.height;
    document.getElementById('stTm').textContent=elapsed+'ms';

    APP.svg = finalSVG;
    dbgSet('d6', null, finalSVG);
    renderResult(finalSVG);

  } catch(e) {
    log('ERROR en pipeline: '+e.message,'err');
    console.error(e);
    resetBtn();
    progress(-1,'Error');
    document.getElementById('bdSVG').textContent='error'; document.getElementById('bdSVG').className='pbadge err';
  }
}

// ═══════════════════════════════════════════════════════════
//  PREPROCESSING
// ═══════════════════════════════════════════════════════════
function preprocess(srcCanvas, mode, blurR, thr) {
  var w=srcCanvas.width, h=srcCanvas.height;
  var c=document.createElement('canvas'); c.width=w; c.height=h;
  var ctx=c.getContext('2d');
  ctx.drawImage(srcCanvas,0,0);

  if (blurR > 0) {
    var imgd = ctx.getImageData(0,0,w,h);
    var blurred = gaussBlur(imgd, blurR);
    ctx.putImageData(blurred,0,0);
  }
  return c;
}

function enhanceContrast(srcCanvas) {
  var w=srcCanvas.width, h=srcCanvas.height;
  var c=document.createElement('canvas'); c.width=w; c.height=h;
  var ctx=c.getContext('2d');
  ctx.drawImage(srcCanvas,0,0);
  var imgd=ctx.getImageData(0,0,w,h), d=imgd.data;

  // Find min/max luminance
  var mn=255, mx=0;
  for (var i=0;i<d.length;i+=4){
    var l=0.299*d[i]+0.587*d[i+1]+0.114*d[i+2];
    if(l<mn)mn=l; if(l>mx)mx=l;
  }
  var rng=Math.max(mx-mn,1);
  for (var i2=0;i2<d.length;i2+=4){
    d[i2]  =Math.min(255,Math.round((d[i2]  -mn)/rng*255));
    d[i2+1]=Math.min(255,Math.round((d[i2+1]-mn)/rng*255));
    d[i2+2]=Math.min(255,Math.round((d[i2+2]-mn)/rng*255));
  }
  ctx.putImageData(imgd,0,0);
  return c;
}

function detectEdges(srcCanvas) {
  var w=srcCanvas.width, h=srcCanvas.height;
  var c=document.createElement('canvas'); c.width=w; c.height=h;
  var ctx=c.getContext('2d');
  var src=srcCanvas.getContext('2d').getImageData(0,0,w,h);
  var d=src.data, out=new Uint8ClampedArray(d.length);
  function gray(x,y){ var xi=Math.min(Math.max(x,0),w-1),yi=Math.min(Math.max(y,0),h-1); var i=(yi*w+xi)*4; return 0.299*d[i]+0.587*d[i+1]+0.114*d[i+2]; }
  for (var y=0;y<h;y++) for (var x=0;x<w;x++){
    var gx=-gray(x-1,y-1)-2*gray(x-1,y)-gray(x-1,y+1)+gray(x+1,y-1)+2*gray(x+1,y)+gray(x+1,y+1);
    var gy=-gray(x-1,y-1)-2*gray(x,y-1)-gray(x+1,y-1)+gray(x-1,y+1)+2*gray(x,y+1)+gray(x+1,y+1);
    var mag=Math.min(255,Math.sqrt(gx*gx+gy*gy));
    var oi=(y*w+x)*4; out[oi]=out[oi+1]=out[oi+2]=Math.round(mag); out[oi+3]=255;
  }
  ctx.putImageData(new ImageData(out,w,h),0,0);
  return c;
}

function applyThreshold(srcCanvas, mode, thr) {
  var w=srcCanvas.width, h=srcCanvas.height;
  var c=document.createElement('canvas'); c.width=w; c.height=h;
  var ctx=c.getContext('2d');
  var imgd=srcCanvas.getContext('2d').getImageData(0,0,w,h), d=new Uint8ClampedArray(imgd.data);

  if (mode==='tattoo'||mode==='lineart'||mode==='botanical') {
    // Adaptive local threshold for detail preservation
    var half=15;
    for (var y=0;y<h;y++) for (var x=0;x<w;x++){
      var sum=0,cnt=0;
      for (var ky=-half;ky<=half;ky+=3) for (var kx=-half;kx<=half;kx+=3){
        var xi=Math.min(Math.max(x+kx,0),w-1), yi=Math.min(Math.max(y+ky,0),h-1);
        var ii=(yi*w+xi)*4; sum+=0.299*d[ii]+0.587*d[ii+1]+0.114*d[ii+2]; cnt++;
      }
      var mean=sum/cnt;
      var i=(y*w+x)*4;
      var lum=0.299*d[i]+0.587*d[i+1]+0.114*d[i+2];
      var v=lum < (mean-8) ? 0 : 255;
      d[i]=d[i+1]=d[i+2]=v;
    }
  } else {
    // Standard threshold
    for (var i2=0;i2<d.length;i2+=4){
      var l=0.299*d[i2]+0.587*d[i2+1]+0.114*d[i2+2];
      var v2=l<thr?0:255; d[i2]=d[i2+1]=d[i2+2]=v2;
    }
  }
  ctx.putImageData(new ImageData(d,w,h),0,0);
  return c;
}

// ═══════════════════════════════════════════════════════════
//  IMAGETRACER.JS OFFICIAL — uses the CDN library directly
// ═══════════════════════════════════════════════════════════
function traceWithImageTracer(canvas, mode, tol, minPx, nc, scl) {
  // Check if official ImageTracer CDN library loaded
  if (typeof ImageTracer === 'undefined') {
    log('ImageTracer CDN no disponible — usando engine interno','warn');
    return traceInternal(canvas, mode, tol, minPx, nc, scl);
  }

  var imgd = canvas.getContext('2d').getImageData(0, 0, canvas.width, canvas.height);

  // Official ImageTracer.js options — tuned per mode
  // ltres/qtres: lower = more detail, higher = more smoothing
  // pathomit: minimum path length in px
  var opts;
  if (mode === 'botanical' || mode === 'lineart') {
    opts = {
      ltres: 0.1, qtres: 0.1,        // maximum detail
      pathomit: Math.max(1, minPx),
      rightangleenhance: true,
      colorsampling: 2,
      numberofcolors: 2,
      mincolorratio: 0,
      colorquantcycles: 3,
      layering: 0,
      strokewidth: 0,
      linefilter: false,
      scale: scl,
      roundcoords: 2,
      blurradius: 0,
      blurdelta: 20
    };
  } else if (mode === 'tattoo') {
    opts = {
      ltres: 0.2, qtres: 0.2,
      pathomit: Math.max(1, minPx),
      rightangleenhance: true,
      colorsampling: 2,
      numberofcolors: 2,
      mincolorratio: 0,
      colorquantcycles: 3,
      layering: 0,
      strokewidth: 0,
      linefilter: false,
      scale: scl,
      roundcoords: 2,
      blurradius: 0
    };
  } else if (mode === 'multi') {
    opts = {
      ltres: tol * 0.5, qtres: tol * 0.5,
      pathomit: Math.max(2, minPx),
      rightangleenhance: false,
      colorsampling: 2,
      numberofcolors: nc,
      mincolorratio: 0,
      colorquantcycles: 5,
      layering: 0,
      strokewidth: 0,
      linefilter: false,
      scale: scl,
      roundcoords: 1,
      blurradius: 0
    };
  } else {
    opts = {
      ltres: tol * 0.3, qtres: tol * 0.3,
      pathomit: Math.max(2, minPx),
      rightangleenhance: false,
      colorsampling: 2,
      numberofcolors: (mode==='logo'||mode==='tshirt') ? Math.max(4, nc) : 8,
      mincolorratio: 0,
      colorquantcycles: 3,
      layering: 0,
      strokewidth: 0,
      linefilter: false,
      scale: scl,
      roundcoords: 1,
      blurradius: 0
    };
  }

  log('ImageTracer opts: ltres='+opts.ltres+' nc='+opts.numberofcolors+' pathomit='+opts.pathomit);
  var svg = ImageTracer.imagedataToSVG(imgd, opts);
  return svg || '';
}

function traceRetry(canvas, thr, tol, minPx, nc, scl) {
  // Fallback: try with lower threshold contrast inversion
  var c2=document.createElement('canvas'); c2.width=canvas.width; c2.height=canvas.height;
  var ctx2=c2.getContext('2d');
  ctx2.fillStyle='#ffffff'; ctx2.fillRect(0,0,c2.width,c2.height);
  ctx2.drawImage(canvas,0,0);
  var imgd=ctx2.getImageData(0,0,c2.width,c2.height);
  var d=imgd.data;

  // Auto-threshold: use Otsu's method
  var histogram=new Array(256).fill(0);
  for (var i=0;i<d.length;i+=4){
    var l=Math.round(0.299*d[i]+0.587*d[i+1]+0.114*d[i+2]);
    histogram[l]++;
  }
  var total=canvas.width*canvas.height;
  var sum=0; for(var i2=0;i2<256;i2++) sum+=i2*histogram[i2];
  var sumB=0,wB=0,max=0,thr2=128;
  for(var t=0;t<256;t++){
    wB+=histogram[t]; if(wB===0)continue;
    var wF=total-wB; if(wF===0)break;
    sumB+=t*histogram[t];
    var mB=sumB/wB, mF=(sum-sumB)/wF;
    var between=wB*wF*(mB-mF)*(mB-mF);
    if(between>max){max=between;thr2=t;}
  }
  log('Otsu threshold='+thr2,'warn');

  // Re-threshold with Otsu
  for(var i3=0;i3<d.length;i3+=4){
    var lum=0.299*d[i3]+0.587*d[i3+1]+0.114*d[i3+2];
    var v=lum<thr2?0:255; d[i3]=d[i3+1]=d[i3+2]=v;
  }
  ctx2.putImageData(imgd,0,0);

  if (typeof ImageTracer !== 'undefined') {
    var imgd2=ctx2.getImageData(0,0,c2.width,c2.height);
    return ImageTracer.imagedataToSVG(imgd2, {
      ltres:0.5, qtres:0.5, pathomit:Math.max(1,minPx-2),
      numberofcolors:2, scale:scl, roundcoords:1,
      colorsampling:2, colorquantcycles:3
    }) || '';
  }
  return traceInternal(c2, APP.mode, tol, minPx, nc, scl);
}

// ═══════════════════════════════════════════════════════════
//  INTERNAL ENGINE FALLBACK (when CDN fails)
// ═══════════════════════════════════════════════════════════
function traceInternal(canvas, mode, tol, minPx, nc, scl) {
  log('Usando engine interno de contornos','warn');
  var imgd = canvas.getContext('2d').getImageData(0,0,canvas.width,canvas.height);
  var W=imgd.width, H=imgd.height, d=imgd.data;
  var thr2 = parseInt(document.getElementById('sThr').value);

  // Grayscale + threshold
  var bitmap=new Uint8Array(W*H);
  for(var i=0;i<W*H;i++){
    var l=0.299*d[i*4]+0.587*d[i*4+1]+0.114*d[i*4+2];
    bitmap[i]=l<thr2?1:0;
  }
  var blackPx=bitmap.reduce(function(s,v){return s+v;},0);
  if(blackPx===0){ for(var i2=0;i2<bitmap.length;i2++) bitmap[i2]=1-bitmap[i2]; log('Invertido (sin píxeles negros)','warn'); }

  var visited=new Uint8Array(W*H), paths=[];
  for(var y=0;y<H;y++) for(var x=0;x<W;x++){
    var idx=y*W+x;
    if(bitmap[idx]!==1||visited[idx]) continue;
    var hasEdge=false;
    var nx2=[x-1,x+1,x,x], ny2=[y,y,y-1,y+1];
    for(var ni=0;ni<4;ni++){ var ex=nx2[ni],ey=ny2[ni]; if(ex<0||ex>=W||ey<0||ey>=H||bitmap[ey*W+ex]===0){hasEdge=true;break;} }
    if(!hasEdge) continue;
    var path=mooreTrace(bitmap,visited,W,H,x,y);
    if(path&&path.length>=minPx) paths.push(path);
  }
  log('Engine interno: '+paths.length+' contornos');

  var W2=Math.round(W*scl), H2=Math.round(H*scl);
  var svg='<svg xmlns="http://www.w3.org/2000/svg" width="'+W2+'" height="'+H2+'" viewBox="0 0 '+W2+' '+H2+'">';
  var tf=function(v){return(v*scl).toFixed(1);};
  for(var pi=0;pi<paths.length;pi++){
    var pts=paths[pi]; if(pts.length<2) continue;
    var dd='M '+tf(pts[0].x)+' '+tf(pts[0].y);
    for(var si=1;si<pts.length;si++) dd+=' L '+tf(pts[si].x)+' '+tf(pts[si].y);
    dd+=' Z';
    svg+='<path fill="#000000" d="'+dd+'"/>';
  }
  svg+='</svg>';
  return svg;
}

function mooreTrace(bitmap,visited,W,H,sx,sy){
  var path=[],x=sx,y=sy,px=sx-1,py=sy;
  var MN=[[-1,0],[-1,-1],[0,-1],[1,-1],[1,0],[1,1],[0,1],[-1,1]];
  var MAX=W*H, steps=0;
  do {
    if(x<0||x>=W||y<0||y>=H) break;
    path.push({x:x,y:y}); visited[y*W+x]=1;
    var dx=x-px,dy=y-py;
    var bd=-1;
    for(var di=0;di<8;di++){ if(MN[di][0]===-dx&&MN[di][1]===-dy){bd=di;break;} }
    if(bd===-1) bd=0;
    var found=false;
    for(var k=1;k<=8;k++){
      var dd=(bd+k)%8,cx=x+MN[dd][0],cy=y+MN[dd][1];
      if(cx>=0&&cx<W&&cy>=0&&cy<H&&bitmap[cy*W+cx]===1){px=x;py=y;x=cx;y=cy;found=true;break;}
    }
    if(!found) break;
    steps++;
  } while((x!==sx||y!==sy)&&steps<MAX);
  return path;
}

// ═══════════════════════════════════════════════════════════
//  SVG FINALIZE — skip background, fix viewBox, validate
// ═══════════════════════════════════════════════════════════
function finalizeSVG(svg) {
  if (!svg || svg.length < 50) return svg;

  // Parse with DOMParser for clean manipulation
  var parser = new DOMParser();
  var doc = parser.parseFromString(svg, 'image/svg+xml');
  var svgEl = doc.querySelector('svg');
  if (!svgEl) return svg;

  // Ensure viewBox
  var w = svgEl.getAttribute('width'), h = svgEl.getAttribute('height');
  var vb = svgEl.getAttribute('viewBox');
  if (!vb && w && h) {
    svgEl.setAttribute('viewBox', '0 0 ' + parseFloat(w) + ' ' + parseFloat(h));
  }

  // Find and remove near-white background path (luminance > 230)
  // This is the white composite background we added — not part of the design
  var paths = svgEl.querySelectorAll('path');
  var removedBg = 0;
  paths.forEach(function(p) {
    var fill = p.getAttribute('fill') || '';
    var m = fill.match(/rgb\((\d+),(\d+),(\d+)\)/);
    if (m) {
      var lum = 0.299*parseInt(m[1]) + 0.587*parseInt(m[2]) + 0.114*parseInt(m[3]);
      // Check if this path covers most of the canvas (background rectangle)
      var d = p.getAttribute('d') || '';
      // If it's a very light color AND has few nodes (likely background rect)
      var nodeCount = (d.match(/[MLQ]/g)||[]).length;
      if (lum > 235 && nodeCount <= 6) {
        p.parentNode.removeChild(p);
        removedBg++;
      }
    }
  });
  if (removedBg > 0) log('Fondo blanco eliminado ('+removedBg+' path)');

  var finalPaths = svgEl.querySelectorAll('path').length;
  if (finalPaths === 0) {
    log('ADVERTENCIA: finalizeSVG eliminó todos los paths — restaurando original','warn');
    return svg; // return unmodified
  }

  return svgEl.outerHTML || new XMLSerializer().serializeToString(svgEl);
}

// ═══════════════════════════════════════════════════════════
//  RENDER RESULT
// ═══════════════════════════════════════════════════════════
function renderResult(svg) {
  var pathCount = (svg.match(/<path/g)||[]).length;

  if (pathCount === 0) {
    document.getElementById('pSVG').innerHTML='<div class="ph" style="color:var(--err)">SVG vacío — ajusta parámetros</div>';
    document.getElementById('bdSVG').textContent='0 paths'; document.getElementById('bdSVG').className='pbadge err';
    resetBtn(); return;
  }

  // Use blob URL + <img> — most reliable cross-browser SVG render
  var blob = new Blob([svg], {type:'image/svg+xml;charset=utf-8'});
  var url = URL.createObjectURL(blob);
  var panel = document.getElementById('pSVG');
  panel.innerHTML='';

  // Detect dominant color for background
  var lightBg = hasDarkColors(svg);
  panel.style.background = lightBg ? '#f8f8f8' : '';

  var imgEl = document.createElement('img');
  imgEl.src = url;
  imgEl.style.cssText='max-width:100%;max-height:340px;object-fit:contain;display:block;margin:auto';
  imgEl.alt='SVG vectorizado';
  imgEl.onload = function(){
    URL.revokeObjectURL(url);
    log('SVG renderizado: '+pathCount+' paths','ok');
    document.getElementById('bdSVG').textContent=pathCount+' paths'; document.getElementById('bdSVG').className='pbadge ok';
    resetBtn();
    document.getElementById('btnSVG').disabled=false;
    document.getElementById('btnPNG').disabled=false;
    document.getElementById('btnCopy').disabled=false;
    document.getElementById('dbgDot').classList.add('on');
  };
  imgEl.onerror = function(){
    URL.revokeObjectURL(url);
    log('img src falló — usando DOM injection','warn');
    try {
      var parser=new DOMParser();
      var doc=parser.parseFromString(svg,'image/svg+xml');
      var svgEl=doc.querySelector('svg');
      if(svgEl){
        svgEl.removeAttribute('width'); svgEl.removeAttribute('height');
        svgEl.style.cssText='max-width:100%;max-height:340px;display:block;margin:auto';
        svgEl.setAttribute('preserveAspectRatio','xMidYMid meet');
        panel.appendChild(document.adoptNode(svgEl));
        log('SVG montado vía DOM','ok');
      }
    } catch(e2){ log('DOM inject falló: '+e2.message,'err'); }
    resetBtn();
    document.getElementById('btnSVG').disabled=false;
  };
  panel.appendChild(imgEl);
}

function hasDarkColors(svg) {
  var m = svg.match(/fill="rgb\((\d+),(\d+),(\d+)\)"/g)||[];
  if (!m.length) {
    // Check hex fills
    return svg.includes('fill="#000') || svg.includes('fill="#1') || svg.includes('fill="#2');
  }
  var dark=0;
  m.forEach(function(fill){
    var c=fill.match(/(\d+),(\d+),(\d+)/);
    if(c){ var l=0.299*parseInt(c[1])+0.587*parseInt(c[2])+0.114*parseInt(c[3]); if(l<100)dark++; }
  });
  return dark > m.length*0.25;
}

function resetBtn(){
  APP.busy=false;
  document.getElementById('btnRun').disabled=false;
  document.getElementById('btnRun').innerHTML='<span>⚡</span> Vectorizar';
}

// ═══════════════════════════════════════════════════════════
//  EXPORT
// ═══════════════════════════════════════════════════════════
document.getElementById('btnSVG').onclick = function(){
  if (!APP.svg) return;
  var n = (APP.svg.match(/<path/g)||[]).length;
  if (n===0){ log('SVG vacío — no se puede descargar','err'); return; }
  var b=new Blob([APP.svg],{type:'image/svg+xml;charset=utf-8'});
  dlFile(URL.createObjectURL(b),'vectorize.svg');
  log('SVG descargado · '+n+' paths','ok');
};

document.getElementById('btnPNG').onclick = function(){
  if (!APP.svg) return;
  var parser=new DOMParser();
  var doc=parser.parseFromString(APP.svg,'image/svg+xml');
  var svgEl=doc.querySelector('svg');
  if(!svgEl){ log('SVG inválido','err'); return; }
  var vb=(svgEl.getAttribute('viewBox')||'').split(/\s+/);
  var W=parseFloat(svgEl.getAttribute('width'))||parseFloat(vb[2])||APP.origCanvas.width;
  var H=parseFloat(svgEl.getAttribute('height'))||parseFloat(vb[3])||APP.origCanvas.height;
  var sc=2, cw=Math.round(W*sc), ch=Math.round(H*sc);
  var c=document.createElement('canvas'); c.width=cw; c.height=ch;
  var ctx=c.getContext('2d');
  if (hasDarkColors(APP.svg)){ ctx.fillStyle='#ffffff'; ctx.fillRect(0,0,cw,ch); }
  var svgR=APP.svg.replace(/(<svg[^>]*)width="[^"]*"/,'$1width="'+cw+'"').replace(/(<svg[^>]*)height="[^"]*"/,'$1height="'+ch+'"');
  if(!svgR.includes('viewBox') && W&&H) svgR=svgR.replace('<svg','<svg viewBox="0 0 '+W+' '+H+'"');
  var blob=new Blob([svgR],{type:'image/svg+xml;charset=utf-8'});
  var url=URL.createObjectURL(blob);
  var img=new Image();
  img.onload=function(){
    try{
      ctx.drawImage(img,0,0,cw,ch);
      c.toBlob(function(b2){
        if(!b2){log('Canvas toBlob falló','err');dlFile(URL.createObjectURL(new Blob([APP.svg],{type:'image/svg+xml'})),'vectorize.svg');return;}
        dlFile(URL.createObjectURL(b2),'vectorize.png');
        log('PNG descargado '+cw+'×'+ch,'ok'); URL.revokeObjectURL(url);
      },'image/png');
    }catch(e){URL.revokeObjectURL(url);document.getElementById('btnSVG').click();log('PNG bloqueado → SVG descargado','warn');}
  };
  img.onerror=function(){URL.revokeObjectURL(url);document.getElementById('btnSVG').click();};
  img.src=url;
};

document.getElementById('btnCopy').onclick = function(){
  if(!APP.svg){ log('Sin SVG','err'); return; }
  if(navigator.clipboard&&navigator.clipboard.writeText){
    navigator.clipboard.writeText(APP.svg).then(function(){log('SVG copiado','ok');}).catch(copyFallback);
  } else { copyFallback(); }
};
function copyFallback(){
  try{
    var ta=document.createElement('textarea'); ta.value=APP.svg;
    ta.style.cssText='position:fixed;left:-9999px;opacity:0';
    document.body.appendChild(ta); ta.select();
    document.execCommand('copy'); document.body.removeChild(ta);
    log('SVG copiado (fallback)','ok');
  }catch(e){log('Clipboard bloqueado — usa Descargar SVG','warn');}
}

// ═══════════════════════════════════════════════════════════
//  IMAGE PROCESSING UTILITIES
// ═══════════════════════════════════════════════════════════
function gaussBlur(imgd, r) {
  var w=imgd.width, h=imgd.height, d=imgd.data;
  var sigma=Math.max(r/2,.5), sz=r*2+1;
  var k=new Float32Array(sz), ks=0;
  for(var i=0;i<sz;i++){ var x=i-r; k[i]=Math.exp(-(x*x)/(2*sigma*sigma)); ks+=k[i]; }
  for(var i2=0;i2<sz;i2++) k[i2]/=ks;
  var tmp=new Float32Array(w*h*4), out=new Uint8ClampedArray(w*h*4);
  for(var y=0;y<h;y++) for(var x=0;x<w;x++){
    var R=0,G=0,B=0,A=0;
    for(var ki=0;ki<sz;ki++){
      var xi=Math.min(Math.max(x+ki-r,0),w-1);
      var idx=(y*w+xi)*4;
      R+=d[idx]*k[ki];G+=d[idx+1]*k[ki];B+=d[idx+2]*k[ki];A+=d[idx+3]*k[ki];
    }
    var di=(y*w+x)*4; tmp[di]=R;tmp[di+1]=G;tmp[di+2]=B;tmp[di+3]=A;
  }
  for(var y2=0;y2<h;y2++) for(var x2=0;x2<w;x2++){
    var R2=0,G2=0,B2=0,A2=0;
    for(var ki2=0;ki2<sz;ki2++){
      var yi=Math.min(Math.max(y2+ki2-r,0),h-1);
      var idx2=(yi*w+x2)*4;
      R2+=tmp[idx2]*k[ki2];G2+=tmp[idx2+1]*k[ki2];B2+=tmp[idx2+2]*k[ki2];A2+=tmp[idx2+3]*k[ki2];
    }
    var di2=(y2*w+x2)*4; out[di2]=R2;out[di2+1]=G2;out[di2+2]=B2;out[di2+3]=A2;
  }
  return new ImageData(out,w,h);
}

// ═══════════════════════════════════════════════════════════
//  DEBUG PANEL
// ═══════════════════════════════════════════════════════════
function toggleDbg(){
  var b=document.getElementById('dbgBody'), t=document.getElementById('dbgToggle');
  b.classList.toggle('open');
  t.textContent=b.classList.contains('open')?'▲ cerrar':'▼ abrir';
}
function dbgSet(id, canvas, svgStr){
  var el=document.getElementById(id); if(!el) return;
  el.innerHTML='';
  if(svgStr){
    var blob=new Blob([svgStr],{type:'image/svg+xml'}), url=URL.createObjectURL(blob);
    var img=document.createElement('img'); img.src=url; img.style.cssText='max-width:100%;max-height:100%;object-fit:contain';
    img.onload=function(){URL.revokeObjectURL(url);}; el.appendChild(img);
  } else if(canvas){
    var thumb=document.createElement('canvas'), MAX=120;
    var r=Math.min(MAX/canvas.width,MAX/canvas.height);
    thumb.width=Math.max(1,Math.round(canvas.width*r)); thumb.height=Math.max(1,Math.round(canvas.height*r));
    thumb.getContext('2d').drawImage(canvas,0,0,thumb.width,thumb.height);
    el.appendChild(thumb);
  }
}

// ═══════════════════════════════════════════════════════════
//  UTILITIES
// ═══════════════════════════════════════════════════════════
function fmtB(b){ if(b<1024)return b+'B'; if(b<1048576)return(b/1024).toFixed(1)+'KB'; return(b/1048576).toFixed(1)+'MB'; }
function dlFile(url,name){ var a=document.createElement('a'); a.href=url; a.download=name; document.body.appendChild(a); a.click(); setTimeout(function(){document.body.removeChild(a);},150); }

// Init mode
setMode(document.querySelector('.mode-btn.active'));
</script>
</body>
</html>
