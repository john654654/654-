# 654-
无限可能
<!doctype html>
<html lang="zh-CN">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Fashion Color Lab Pro — SaaS 原型</title>
<style>
:root{
  --bg:#07111a; --panel:#0d161b; --muted:#97a6ae; --accent1:#ff8a65; --accent2:#6b9cff;
  --glass: rgba(255,255,255,0.03); --glass-2: rgba(255,255,255,0.02);
  --card-grad: linear-gradient(180deg, rgba(255,255,255,0.015), rgba(255,255,255,0.01));
}
*{box-sizing:border-box;font-family:Inter, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif}
html,body{height:100%;margin:0;background:
 radial-gradient(900px 420px at 10% 12%, rgba(255,138,101,0.03), transparent 8%),
 radial-gradient(800px 380px at 88% 88%, rgba(81,150,255,0.02), transparent 10%),
 var(--bg); color:#e6eef3; -webkit-font-smoothing:antialiased;}
header{display:flex;align-items:center;gap:14px;padding:18px 22px;border-bottom:1px solid rgba(255,255,255,0.03)}
.logo{display:flex;align-items:center;gap:12px}
.logo .mark{width:48px;height:48px;border-radius:10px;background:linear-gradient(135deg,var(--accent1),#ffd166);box-shadow:0 12px 36px rgba(255,138,101,0.12);display:flex;align-items:center;justify-content:center;color:#081217;font-weight:800;font-size:18px}
h1{font-size:16px;margin:0}
.top-actions{margin-left:auto;display:flex;gap:10px;align-items:center}
.btn{background:transparent;border:1px solid rgba(255,255,255,0.04);padding:8px 12px;border-radius:10px;color:var(--muted);cursor:pointer;transition:all .18s;backdrop-filter: blur(4px)}
.btn:hover{transform:translateY(-2px);box-shadow:0 8px 30px rgba(2,6,8,0.6)}
.btn.primary{background:linear-gradient(90deg,var(--accent1),#ff6bcb);color:#081217;border:none;box-shadow:0 10px 32px rgba(255,107,203,0.12)}
.container{display:grid;grid-template-columns:360px 8px 1fr 360px;grid-template-rows:calc(100vh - 78px);gap:14px;padding:18px}
.splitter{width:8px;border-radius:6px;background:linear-gradient(180deg,rgba(255,255,255,0.02),rgba(255,255,255,0.01));cursor:col-resize}
.panel{background:var(--card-grad);border-radius:12px;padding:16px;box-shadow:0 10px 40px rgba(6,10,12,0.6);border:1px solid rgba(255,255,255,0.03);overflow:auto}
.panel h2{margin:0 0 8px 0;font-size:13px;color:#fff}
.muted{color:var(--muted);font-size:13px}
.small{font-size:12px;color:var(--muted)}
.palette{display:flex;gap:10px;align-items:center;margin-bottom:10px;flex-wrap:wrap}
.swatch{width:48px;height:48px;border-radius:10px;box-shadow:inset 0 -10px 24px rgba(0,0,0,0.2);border:1px solid rgba(255,255,255,0.02)}
.swatch.small{width:34px;height:34px;border-radius:8px}
.row{display:flex;gap:10px;align-items:center}
.preview-wrap{display:flex;flex-direction:column;height:100%}
.preview-top{display:flex;gap:16px;align-items:flex-start;margin-bottom:14px}
.main-color{flex:0 0 340px;border-radius:14px;padding:20px;background:linear-gradient(135deg,#0f1724,#131a23);border:1px solid rgba(255,255,255,0.03);position:relative;overflow:hidden}
.main-color .circle{width:120px;height:120px;border-radius:999px;border:6px solid rgba(255,255,255,0.06);display:flex;align-items:center;justify-content:center;font-weight:800;box-shadow:0 26px 60px rgba(0,0,0,0.6)}
.breathe{animation:breath 3.4s ease-in-out infinite}
@keyframes breath{0%{box-shadow:0 0 0 0 rgba(255,138,101,0)}50%{box-shadow:0 0 80px 18px rgba(255,138,101,0.06)}100%{box-shadow:0 0 0 0 rgba(255,138,101,0)}}
.controls{display:flex;flex-direction:column;gap:10px}
.control{margin-bottom:6px}
input[type=range]{width:100%}
label{font-size:12px;color:var(--muted);display:block;margin-bottom:6px}
.variant-row{display:flex;gap:8px;margin-top:8px;align-items:center}
.wall{display:grid;grid-template-columns:repeat(auto-fit,minmax(120px,1fr));gap:10px}
.card{background:linear-gradient(180deg, rgba(255,255,255,0.015), rgba(255,255,255,0.01));padding:10px;border-radius:10px;border:1px solid rgba(255,255,255,0.02);cursor:pointer;transition:transform .12s}
.card:hover{transform:translateY(-6px)}
.chart{height:110px;border-radius:10px;padding:8px;background:linear-gradient(180deg, rgba(255,255,255,0.01), transparent)}
.brand-header{display:flex;gap:12px;align-items:center}
input[type=text],select{width:100%;padding:10px;border-radius:10px;background:transparent;border:1px solid rgba(255,255,255,0.04);color:#e6eef3}
.tag{display:inline-block;padding:6px 10px;border-radius:999px;background:rgba(255,255,255,0.02);font-size:12px;color:var(--muted)}
.bottom-nav{position:fixed;left:0;right:0;bottom:0;height:68px;background:linear-gradient(180deg,rgba(2,6,8,0.6),rgba(2,6,8,0.9));display:none;border-top:1px solid rgba(255,255,255,0.03);align-items:center;justify-content:center}
.bottom-nav .nav{display:flex;gap:24px}
@media(max-width:960px){ .container{grid-template-columns:1fr;grid-template-rows:1fr 8px 420px;gap:12px;padding-bottom:90px} .splitter{display:none} .bottom-nav{display:flex} .main-color{flex:1;width:100%} }
.footer{padding:12px 22px;color:var(--muted);font-size:12px;text-align:center}
.tools-row{display:flex;gap:8px;align-items:center;flex-wrap:wrap}
.pill{padding:6px 10px;border-radius:999px;background:rgba(255,255,255,0.02);font-size:12px;color:var(--muted);cursor:pointer;border:1px solid rgba(255,255,255,0.02)}
.kv{font-size:12px;color:var(--muted);display:flex;gap:8px;align-items:center}
.inline-btn{padding:6px 8px;border-radius:8px;background:transparent;border:1px solid rgba(255,255,255,0.03);color:var(--muted)}
</style>
</head>
<body>
<header>
  <div class="logo">
    <div class="mark">F</div>
    <div>
      <h1>Fashion Color Lab Pro</h1>
      <div class="muted small">高级配色 · 面料渲染 · 设计交付</div>
    </div>
  </div>
  <div class="top-actions">
    <div class="tag" id="user-status">Free</div>
    <button class="btn" id="toggle-pro">切换 Pro</button>
    <button class="btn" id="copy-css">复制 CSS</button>
    <button class="btn primary" id="save-palette">保存配色</button>
  </div>
</header>

<div class="container">
  <!-- left -->
  <aside class="panel" id="left-panel">
    <h2>灵感采集</h2>
    <div class="control">
      <label>上传图片提取主色（自动量化并取 5 色）</label>
      <input type="file" id="img-input" accept="image/*" />
    </div>
    <div class="control">
      <label>检测到的主色（点击设为主色）</label>
      <div id="detected" class="palette"></div>
    </div>

    <h2>情绪词汇（内置映射）</h2>
    <div id="mood-list" class="muted small"></div>

    <h2>流行趋势色板</h2>
    <div id="trend-palettes"></div>

    <h2>AI Palette Predictor（惊喜）</h2>
    <div class="muted small">语义化建议并可直接应用</div>
    <div id="smart-suggestions" style="margin-top:8px"></div>

    <h2 style="margin-top:12px">趋势仪表盘（惊喜）</h2>
    <div class="chart panel" id="trend-dashboard" style="padding:8px">
      <canvas id="trendChart" width="320" height="110"></canvas>
    </div>
  </aside>

  <div class="splitter"></div>

  <!-- center -->
  <main class="panel preview-wrap" id="center-panel">
    <div class="preview-top">
      <div class="main-color breathe" id="mainColorBlock">
        <div style="position:absolute;inset:0;mix-blend-mode:overlay;opacity:0.06;background:radial-gradient(circle at 30% 20%, white, transparent 12%)"></div>
        <div style="display:flex;flex-direction:column;align-items:center;gap:10px">
          <div class="circle" id="mainColorCircle" style="background:#FF8A65;color:#081217">#FF8A65</div>
          <div class="muted small">主色 · 动态呼吸光晕</div>
        </div>
      </div>

      <div style="flex:1">
        <div style="display:flex;gap:12px;align-items:center">
          <div style="flex:1">
            <label>主色权重（60 / 30 / 10 模拟）</label>
            <div style="display:flex;gap:8px;align-items:center">
              <input id="w1" type="range" min="10" max="80" value="60" />
              <input id="w2" type="range" min="10" max="80" value="30" />
              <input id="w3" type="range" min="0" max="40" value="10" />
            </div>
            <div class="muted small" id="weight-values">60% · 30% · 10%</div>
          </div>
          <div style="width:140px">
            <label>WCAG 对比检测</label>
            <div id="contrast-status" class="muted small">-</div>
            <div id="contrast-bar" style="height:8px;border-radius:6px;background:rgba(255,255,255,0.03);margin-top:6px"></div>
          </div>
        </div>

        <div style="margin-top:12px" class="controls">
          <label>色彩变体轮（色相 / 饱和 / 亮度）</label>
          <div style="display:flex;gap:8px;align-items:center">
            <input id="hue" type="range" min="-180" max="180" value="0" />
            <input id="sat" type="range" min="-100" max="100" value="0" />
            <input id="lum" type="range" min="-100" max="100" value="0" />
          </div>
          <div id="variant-row" class="variant-row"></div>
          <div style="display:flex;gap:8px;margin-top:8px;align-items:center">
            <button class="btn inline-btn" id="gen-harmony">生成配色和谐（惊喜）</button>
            <select id="harmony-type" style="width:160px">
              <option value="analogous">相邻（Analogous）</option>
              <option value="triadic">三分法（Triadic）</option>
              <option value="complement">互补（Complementary）</option>
            </select>
            <button class="btn" id="copy-permalink">生成分享链接</button>
          </div>
        </div>
      </div>
    </div>

    <div style="flex:1;display:flex;gap:12px;align-items:stretch">
      <div style="flex:1" class="panel" id="fabric-panel">
        <h2>面料与材质渲染</h2>
        <div style="display:flex;gap:8px;align-items:center;margin-bottom:8px">
          <select id="fabric-select">
            <option value="cotton">棉麻（纯色）</option>
            <option value="silk">真丝（强光泽渐变）</option>
            <option value="leather">皮革（噪点纹理）</option>
            <option value="tweed">粗花呢（彩色颗粒）</option>
            <option value="dyed" id="adv-fabric" style="display:none">高级：活性染色（Pro）</option>
          </select>
          <select id="env-select">
            <option value="day">日光</option>
            <option value="warm">暖灯</option>
            <option value="cool">冷灯</option>
          </select>
          <div style="width:140px"><label>透明度</label><input id="alpha" type="range" min="0" max="1" step="0.01" value="1"></div>
          <div style="width:140px"><label>光泽度</label><input id="gloss" type="range" min="0" max="1" step="0.01" value="0.4"></div>
        </div>
        <canvas id="garment" width="720" height="380" style="width:100%;border-radius:10px;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.00));"></canvas>
      </div>
    </div>
  </main>

  <!-- right -->
  <aside class="panel" id="right-panel">
    <div class="brand-header">
      <div style="flex:1">
        <h2>品牌工具箱</h2>
        <input id="brand-name" type="text" placeholder="输入品牌名（例：Aurora）" />
      </div>
      <div style="width:120px">
        <button class="btn" id="gen-brand">生成品牌色卡</button>
      </div>
    </div>

    <div style="margin-top:10px">
      <div class="muted small">使用比例指南（60 / 30 / 10）</div>
      <div id="brand-swatches" style="display:flex;gap:8px;margin-top:8px"></div>
      <div style="margin-top:8px;display:flex;gap:8px">
        <button class="btn" id="export-png">导出 PNG</button>
        <button class="btn" id="export-highres">高清导出（Pro）</button>
      </div>
    </div>

    <h2 style="margin-top:12px">灵感墙 · 历史与社区</h2>
    <div style="display:flex;gap:8px;align-items:center;margin-bottom:8px">
      <input id="share-title" type="text" placeholder="配色标题（可选）" />
      <button class="btn" id="publish">发布</button>
    </div>
    <div class="wall" id="inspiration-wall"></div>

    <h2 style="margin-top:12px">多品牌管理（惊喜）</h2>
    <div style="display:flex;gap:8px;margin-bottom:8px">
      <input id="new-brand-name" type="text" placeholder="新建品牌名" />
      <button class="btn" id="create-brand">创建</button>
    </div>
    <div id="brand-list" style="display:flex;flex-direction:column;gap:8px"></div>
  </aside>
</div>

<div class="bottom-nav">
  <div class="nav">
    <div class="kv">工具</div>
    <div class="kv">渲染</div>
    <div class="kv">灵感墙</div>
    <div class="kv">导出</div>
  </div>
</div>

<footer class="footer">© Fashion Color Lab Pro · Demo</footer>

<script>
/* ========== 商业开关 ========== */
let isProUser = false; // 切换到 true 解锁 Pro 功能
document.getElementById('user-status').textContent = isProUser ? 'Pro' : 'Free';

/* ========== 内置数据 ========= */
const moodMap = {
  "自然:清新":"#7bd389","自然:大地":"#a67c52","情绪:优雅":"#caa0ff","情绪:热情":"#ff6b6b","情绪:沉稳":"#2b6b6b",
  "自然:晨曦":"#ffd36b","自然:海洋":"#2eb7d5","情绪:浪漫":"#ff8abf","情绪:冷静":"#6fb3ff","自然:森林":"#2f8b57",
  "自然:沙漠":"#d4a373","情绪:活力":"#ffb84d","情绪:高级":"#1f2937","自然:雪地":"#e6f2ff","情绪:神秘":"#5a3d7c",
  "自然:岩石":"#7a6f64","情绪:纯净":"#f7fbff","自然:黄昏":"#ffa66d","情绪:复古":"#c48b67","自然:雨季":"#7aa3c7","情绪:极简":"#111827"
};

const trendPalettes = [
  ['#FF6B6B','#FFD166','#6BCB77','#4D96FF','#6B6BFF'],
  ['#1F2937','#3B82F6','#60A5FA','#93C5FD','#E0F2FE'],
  ['#FF8A65','#FFD166','#FFEFB2','#C6F6D5','#D4E157'],
  ['#D7263D','#F46036','#2E294E','#1B998B','#C5D86D'],
  ['#2D313A','#69717A','#9BA7B3','#E6EEF3','#FFF1E6'],
  ['#7BD389','#2EB7D5','#7AA3C7','#bc8fce','#ffb6b9'],
  ['#0F1724','#1e293b','#3b4250','#ff8a65','#ffd166'],
  ['#8B5CF6','#06B6D4','#06D6A0','#FFD166','#FF6B6B']
];

/* ========== DOM refs ========== */
const detected = document.getElementById('detected');
const moodList = document.getElementById('mood-list');
const trendContainer = document.getElementById('trend-palettes');
const mainColorCircle = document.getElementById('mainColorCircle');
const mainColorBlock = document.getElementById('mainColorBlock');
const variantRow = document.getElementById('variant-row');
const weightValues = document.getElementById('weight-values');
const contrastStatus = document.getElementById('contrast-status');
const contrastBar = document.getElementById('contrast-bar');
const brandSwatches = document.getElementById('brand-swatches');

/* ========== 初始化 UI ========== */
moodList.innerHTML = Object.entries(moodMap).map(([k,v])=>`<span style="display:inline-block;margin:4px;padding:6px 8px;border-radius:999px;background:${v};color:#07111a;font-weight:600;font-size:12px">${k.split(':')[1]}</span>`).join('');
trendPalettes.forEach((pal,i)=>{
  const el = document.createElement('div'); el.style.display='flex'; el.style.gap='6px'; el.style.marginBottom='8px'; el.style.alignItems='center';
  pal.slice(0,5).forEach(c=>{ const s=document.createElement('div'); s.className='swatch'; s.style.background=c; el.appendChild(s); });
  const btn = document.createElement('button'); btn.className='btn'; btn.textContent='应用'; btn.onclick=()=>applyPalette(pal);
  el.appendChild(btn); trendContainer.appendChild(el);
});

/* ========= 全局状态 ========= */
let currentPalette = ['#FF8A65','#6BCB77','#4D96FF','#FFD166','#6B6BFF'];
function applyPalette(pal){ currentPalette = pal.slice(0,5); updateUIFromPalette(); saveTempSession(); }
function selectMainColor(hex){ currentPalette[0]=hex; updateUIFromPalette(); saveTempSession(); }

/* ========= 图像主色提取 ========= */
const imgInput = document.getElementById('img-input');
imgInput.addEventListener('change', (e)=>{ const f=e.target.files[0]; if(!f) return; const img=new Image(); img.onload=()=>extractColors(img); img.src=URL.createObjectURL(f); });

function extractColors(img){
  const canvas = document.createElement('canvas'); const w=Math.min(360,img.width), h=Math.min(240,img.height); canvas.width=w; canvas.height=h;
  const ctx = canvas.getContext('2d'); ctx.drawImage(img,0,0,w,h);
  const data = ctx.getImageData(0,0,w,h).data;
  const freq={};
  for(let i=0;i<data.length;i+=4){
    const r=data[i], g=data[i+1], b=data[i+2], a=data[i+3];
    if(a<128) continue;
    const q=[Math.round(r/12)*12,Math.round(g/12)*12,Math.round(b/12)*12];
    const key=q.join(',');
    freq[key]=(freq[key]||0)+1;
  }
  const sorted = Object.entries(freq).sort((a,b)=>b[1]-a[1]).slice(0,30);
  const picked=[]; for(const [k,v] of sorted){ const hex = rgbToHex(k.split(',').map(n=>+n)); if(picked.some(p=>colorDistance(p,hex)<18)) continue; picked.push(hex); if(picked.length>=5) break; }
  renderDetected(picked);
  generateSmartSuggestions(picked);
}

/* ========= 小工具：颜色转换/距离 ========= */
function rgbToHex([r,g,b]){ return "#"+[r,g,b].map(x=>x.toString(16).padStart(2,'0')).join('').toUpperCase(); }
function hexToRgb(hex){ const h=hex.replace('#',''); return [parseInt(h.slice(0,2),16),parseInt(h.slice(2,4),16),parseInt(h.slice(4,6),16)]; }
function colorDistance(a,b){ const A=hexToRgb(a), B=hexToRgb(b); return Math.sqrt((A[0]-B[0])**2+(A[1]-B[1])**2+(A[2]-B[2])**2); }
function shade(hex,percent){ const [r,g,b]=hexToRgb(hex); const t=(p)=>Math.max(0,Math.min(255,Math.round(p))); if(percent<0) return `rgb(${t(r*(1+percent/100))},${t(g*(1+percent/100))},${t(b*(1+percent/100))})`; else return `rgb(${t(r+(255-r)*(percent/100))},${t(g+(255-g)*(percent/100))},${t(b+(255-b)*(percent/100))})`; }

/* ========= 渲染检测结果 ========= */
function renderDetected(colors){
  detected.innerHTML='';
  colors.forEach(c=>{
    const el=document.createElement('div'); el.style.display='flex'; el.style.flexDirection='column'; el.style.alignItems='center'; el.style.gap='6px';
    const s=document.createElement('div'); s.className='swatch'; s.style.background=c; s.style.cursor='pointer'; s.onclick=()=>selectMainColor(c);
    const t=document.createElement('div'); t.className='muted small'; t.textContent=c;
    el.appendChild(s); el.appendChild(t); detected.appendChild(el);
  });
  if(colors[0]) selectMainColor(colors[0]);
}

/* ========= 主色 UI / 变体 / 权重 / 对比 ========== */
function updateUIFromPalette(){
  const main = currentPalette[0] || '#FF8A65';
  mainColorCircle.style.background = main; mainColorCircle.textContent = main.toUpperCase();
  mainColorBlock.style.background = `linear-gradient(135deg, ${shade(main,-16)}, ${shade(main,8)})`;
  renderVariants();
  renderBrandSwatches();
  updateContrastStatus();
}
document.getElementById('hue').addEventListener('input', renderVariants);
document.getElementById('sat').addEventListener('input', renderVariants);
document.getElementById('lum').addEventListener('input', renderVariants);
['w1','w2','w3'].forEach(id=>document.getElementById(id).addEventListener('input', updateWeights));
function renderVariants(){
  variantRow.innerHTML=''; const base=currentPalette[0]||'#FF8A65';
  const hAdj=+document.getElementById('hue').value, sAdj=+document.getElementById('sat').value, lAdj=+document.getElementById('lum').value;
  for(let i=-3;i<=3;i++){
    const v=hslAdjust(base, hAdj+i*8, sAdj+i*5, lAdj+i*6);
    const d=document.createElement('div'); d.className='swatch small'; d.style.background=v; d.onclick=()=>selectMainColor(v);
    variantRow.appendChild(d);
  }
}
function hslAdjust(hex,dh,ds,dl){
  const [r,g,b]=hexToRgb(hex); const hsl=rgbToHsl(r,g,b);
  let h=(hsl[0]*360+dh+360)%360; let s=Math.min(1,Math.max(0,hsl[1]+ds/100)); let l=Math.min(1,Math.max(0,hsl[2]+dl/100));
  const rgb=hslToRgb(h/360,s,l); return rgbToHex(rgb.map(v=>Math.round(v)));
}
function rgbToHsl(r,g,b){ r/=255;g/=255;b/=255; const max=Math.max(r,g,b),min=Math.min(r,g,b); let h=0,s=0,l=(max+min)/2; if(max!==min){ const d=max-min; s=l>0.5? d/(2-max-min): d/(max+min); switch(max){case r:h=(g-b)/d+(g<b?6:0);break;case g:h=(b-r)/d+2;break;case b:h=(r-g)/d+4;break;} h/=6;} return [h,s,l]; }
function hslToRgb(h,s,l){ let r,g,b; if(s===0){ r=g=b=l; } else{ const hue2rgb=(p,q,t)=>{ if(t<0)t+=1;if(t>1)t-=1;if(t<1/6) return p+(q-p)*6*t; if(t<1/2) return q; if(t<2/3) return p+(q-p)*(2/3-t)*6; return p;}; const q=l<0.5? l*(1+s): l+s-l*s; const p=2*l-q; r=hue2rgb(p,q,h+1/3); g=hue2rgb(p,q,h); b=hue2rgb(p,q,h-1/3);} return [r*255,g*255,b*255]; }

/* 权重显示 */
function updateWeights(){ const w1=+document.getElementById('w1').value, w2=+document.getElementById('w2').value, w3=+document.getElementById('w3').value; weightValues.textContent=`${w1}% · ${w2}% · ${w3}%`; }

/* WCAG 对比检测 */
function luminance(rgb){ const srgb=rgb.map(v=>v/255).map(c=>c<=0.03928? c/12.92 : Math.pow((c+0.055)/1.055,2.4)); return 0.2126*srgb[0]+0.7152*srgb[1]+0.0722*srgb[2]; }
function contrastRatio(hex1,hex2){ const L1=luminance(hexToRgb(hex1)), L2=luminance(hexToRgb(hex2)); const lighter=Math.max(L1,L2), darker=Math.min(L1,L2); return (lighter+0.05)/(darker+0.05); }
function updateContrastStatus(){
  const fg = '#FFFFFF', bg = currentPalette[0] || '#FF8A65';
  const ratio = contrastRatio(fg,bg); const passAA = ratio>=4.5, passAAA = ratio>=7;
  contrastStatus.innerHTML = `对比 ${ratio.toFixed(2)} — ${passAAA? 'AAA' : passAA? 'AA' : '<span style="color:#ff7a7a">不达标</span>'}`;
  const pct = Math.min(100, (ratio/8)*100);
  contrastBar.style.background = `linear-gradient(90deg, #6bffb4 ${pct}%, rgba(255,255,255,0.03) ${pct}%)`;
}
updateUIFromPalette();

/* ========= 面料渲染（Canvas） ========= */
const garment = document.getElementById('garment'); const gctx = garment.getContext('2d');
function renderGarment(){
  const dpr = devicePixelRatio||1; const cw=Math.max(480,Math.floor(garment.clientWidth*dpr)), ch=Math.max(320,Math.floor(garment.clientHeight*dpr));
  garment.width=cw; garment.height=ch; garment.style.width='100%'; garment.style.height='';
  const ctx=gctx; ctx.clearRect(0,0,cw,ch);
  ctx.fillStyle='#07111a'; ctx.fillRect(0,0,cw,ch);
  ctx.save(); ctx.translate(cw/2,ch/2+20);
  const scale = Math.min(cw,ch)/1200;
  ctx.beginPath(); ctx.moveTo(-260*scale,-120*scale); ctx.bezierCurveTo(-300*scale,-140*scale,-320*scale,-40*scale,-260*scale,20*scale); ctx.lineTo(-140*scale,140*scale); ctx.bezierCurveTo(-90*scale,190*scale,90*scale,190*scale,140*scale,140*scale); ctx.lineTo(260*scale,20*scale); ctx.bezierCurveTo(320*scale,-40*scale,300*scale,-140*scale,260*scale,-120*scale); ctx.closePath();
  const fabric=document.getElementById('fabric-select').value; const env=document.getElementById('env-select').value; const base=currentPalette[0]||'#FF8A65';
  const alpha=+document.getElementById('alpha').value, gloss=+document.getElementById('gloss').value;
  const envTint = env==='day'? 'rgba(255,255,240,0.04)' : env==='warm'? 'rgba(255,220,180,0.04)' : 'rgba(180,220,255,0.03)';
  if(fabric==='cotton'){ ctx.fillStyle=base; ctx.globalAlpha=alpha; ctx.fill(); ctx.globalAlpha=0.06; ctx.fillStyle='#000'; ctx.fill(); ctx.globalAlpha=1; ctx.strokeStyle='rgba(255,255,255,0.02)'; ctx.lineWidth=2; ctx.stroke(); }
  else if(fabric==='silk'){ const g=ctx.createLinearGradient(-260*scale,-120*scale,260*scale,140*scale); g.addColorStop(0, shade(base,12)); g.addColorStop(0.5, base); g.addColorStop(1, shade(base,-10)); ctx.fillStyle=g; ctx.globalAlpha=alpha; ctx.fill(); const glow=ctx.createLinearGradient(-260*scale,-220*scale,260*scale,220*scale); glow.addColorStop(0, `rgba(255,255,255,${0.15*gloss})`); glow.addColorStop(0.4,'rgba(255,255,255,0)'); glow.addColorStop(1,`rgba(255,255,255,${0.06*gloss})`); ctx.fillStyle=glow; ctx.fill(); ctx.globalAlpha=1; }
  else if(fabric==='leather'){ ctx.fillStyle=base; ctx.globalAlpha=alpha; ctx.fill(); const imgData=ctx.getImageData(-260*scale,-120*scale,520*scale,260*scale); for(let i=0;i<imgData.data.length;i+=4){ const v=(Math.random()*40-20)*gloss; imgData.data[i]+=v; imgData.data[i+1]+=v; imgData.data[i+2]+=v; } ctx.putImageData(imgData,-260*scale,-120*scale); ctx.globalAlpha=0.06; ctx.strokeStyle='rgba(0,0,0,0.6)'; ctx.lineWidth=1; for(let i=0;i<8;i++){ ctx.beginPath(); ctx.moveTo(-180*scale+Math.random()*360*scale,-80*scale+Math.random()*180*scale); ctx.lineTo(-170*scale+Math.random()*340*scale,-70*scale+Math.random()*160*scale); ctx.stroke(); } ctx.globalAlpha=1; }
  else if(fabric==='tweed'){ ctx.fillStyle=shade(base,-6); ctx.globalAlpha=alpha; ctx.fill(); for(let i=0;i<2200;i++){ const x=-240*scale+Math.random()*480*scale; const y=-100*scale+Math.random()*200*scale; const r=Math.random()*2*scale; const c=trendPalettes[Math.floor(Math.random()*trendPalettes.length)][Math.floor(Math.random()*5)]; ctx.fillStyle=c; ctx.globalAlpha=0.18; ctx.beginPath(); ctx.arc(x,y,r,0,Math.PI*2); ctx.fill(); } ctx.globalAlpha=1; }
  ctx.globalCompositeOperation='overlay'; ctx.fillStyle=envTint; ctx.fill(); ctx.globalCompositeOperation='source-over';
  ctx.restore();
  if(!isProUser){ ctx.save(); ctx.globalAlpha=0.08; ctx.fillStyle='#FFF'; ctx.font = `${14*dpr}px Inter`; ctx.fillText('Fashion Color Lab · Free', 20*dpr, ch-20*dpr); ctx.restore(); }
}
['fabric-select','env-select','alpha','gloss'].forEach(id=>document.getElementById(id).addEventListener('input', renderGarment));
window.addEventListener('resize', ()=>{ setTimeout(renderGarment,120); });
renderGarment();

/* ========= 品牌工具箱与导出 ========= */
function renderBrandSwatches(){
  brandSwatches.innerHTML=''; const p=currentPalette.slice(0,3);
  p.forEach((c,i)=>{ const el=document.createElement('div'); el.style.flex='1'; el.style.padding='12px'; el.style.borderRadius='10px'; el.style.textAlign='center'; el.style.background=`linear-gradient(180deg, ${shade(c,6)}, ${shade(c,-8)})`; el.style.boxShadow='inset 0 -8px 28px rgba(0,0,0,0.28)'; el.innerHTML=`<div style="font-weight:700">${c.toUpperCase()}</div><div class="muted small">${i===0? '60%': i===1? '30%':'10%'}</div>`; brandSwatches.appendChild(el); });
}
document.getElementById('gen-brand').addEventListener('click', ()=>{ const name=document.getElementById('brand-name').value.trim()||'Brand'; saveBrand(name,currentPalette.slice(0,3)); renderBrandList(); });

document.getElementById('export-png').addEventListener('click', ()=>exportBrand(false));
document.getElementById('export-highres').addEventListener('click', ()=>exportBrand(true));

function exportBrand(highres){
  const name=document.getElementById('brand-name').value.trim()||'Brand';
  if(highres && !isProUser){ alert('高清导出为 Pro 功能，解锁专业版以获得高分辨率与无水印导出。'); return; }
  const scale=highres?3:1; const cw=1200*scale, ch=800*scale;
  const cn=document.createElement('canvas'); cn.width=cw; cn.height=ch; const c=cn.getContext('2d');
  c.fillStyle='#07111a'; c.fillRect(0,0,cw,ch); c.fillStyle='#fff'; c.font=`${36*scale}px Inter`; c.fillText(name,40*scale,80*scale);
  const items=currentPalette.slice(0,3);
  items.forEach((col,i)=>{ c.fillStyle=col; c.fillRect(40*scale,120*scale + i*200*scale,1100*scale,160*scale); c.fillStyle='#fff'; c.font=`${28*scale}px Inter`; c.fillText(`${i===0? '60%': i===1? '30%':'10%'}`, 60*scale,200*scale + i*200*scale); });
  if(!isProUser){ c.globalAlpha=0.08; c.fillStyle='#fff'; c.font=`${24*scale}px Inter`; c.fillText('Fashion Color Lab · Free', 40*scale, ch-40*scale); }
  const a=document.createElement('a'); a.download=`${name}_palette${highres? '_hires':''}.png`; a.href=cn.toDataURL('image/png'); a.click();
}

/* ========= 历史与灵感墙（LocalStorage） ========= */
function loadWall(){ const raw=localStorage.getItem('fcl_wall'); return raw? JSON.parse(raw): []; }
function saveWall(arr){ localStorage.setItem('fcl_wall', JSON.stringify(arr)); }
function publish(){
  const title=document.getElementById('share-title').value.trim()||'Untitled';
  const pal=currentPalette.slice(0,5);
  const wall=loadWall();
  const entry={id:Date.now(),title,palette:pal,time:new Date().toISOString()};
  wall.unshift(entry);
  // enforce per-user caps
  if(!isProUser && wall.length>50) wall.length=50;
  saveWall(wall); renderWall(); renderTrendChart();
}
document.getElementById('publish').addEventListener('click', publish);

function renderWall(){
  const wall=loadWall(); const container=document.getElementById('inspiration-wall'); container.innerHTML='';
  wall.forEach(e=>{
    const card=document.createElement('div'); card.className='card';
    const swDiv=document.createElement('div'); swDiv.style.display='flex'; swDiv.style.gap='6px'; swDiv.style.marginBottom='8px';
    e.palette.slice(0,5).forEach(c=>{ const s=document.createElement('div'); s.className='swatch small'; s.style.background=c; swDiv.appendChild(s); });
    const meta=document.createElement('div'); meta.className='kv'; meta.style.justifyContent='space-between';
    const left=document.createElement('div'); left.innerHTML=`<div style="font-weight:600">${e.title}</div><div class="muted small">${new Date(e.time).toLocaleString()}</div>`;
    const right=document.createElement('div'); right.innerHTML=`<button class="btn" style="padding:6px 8px">回滚</button> <button class="btn" style="padding:6px 8px">分享</button>`;
    right.querySelectorAll('button')[0].onclick=()=>{ currentPalette=e.palette.slice(0,5); updateUIFromPalette(); };
    right.querySelectorAll('button')[1].onclick=()=>{ const url=makePermalink(e.palette); prompt('复制并分享此链接：',url); };
    meta.appendChild(left); meta.appendChild(right);
    card.appendChild(swDiv); card.appendChild(meta); container.appendChild(card);
  });
}
renderWall();

/* ========= 多品牌管理 ========= */
function loadBrands(){ const raw=localStorage.getItem('fcl_brands'); return raw? JSON.parse(raw): []; }
function saveBrands(b){ localStorage.setItem('fcl_brands', JSON.stringify(b)); }
function saveBrand(name, palette){ const brands=loadBrands(); const existing=brands.find(x=>x.name===name); if(existing){ existing.palette=palette; } else { brands.push({name,palette,id:Date.now()}); } saveBrands(brands); }
function renderBrandList(){ const cont=document.getElementById('brand-list'); cont.innerHTML=''; loadBrands().forEach(b=>{ const el=document.createElement('div'); el.className='row'; el.style.justifyContent='space-between'; const left=document.createElement('div'); left.style.display='flex'; left.style.alignItems='center'; left.style.gap='8px'; const name=document.createElement('div'); name.textContent=b.name; const sw=document.createElement('div'); sw.style.display='flex'; sw.style.gap='6px'; b.palette.slice(0,3).forEach(c=>{ const s=document.createElement('div'); s.className='swatch small'; s.style.background=c; sw.appendChild(s); }); left.appendChild(name); left.appendChild(sw); const right=document.createElement('div'); const loadBtn=document.createElement('button'); loadBtn.className='btn'; loadBtn.textContent='载入'; loadBtn.onclick=()=>{ currentPalette=b.palette.concat(currentPalette).slice(0,5); updateUIFromPalette(); }; const delBtn=document.createElement('button'); delBtn.className='btn'; delBtn.textContent='删除'; delBtn.onclick=()=>{ const arr=loadBrands().filter(x=>x.id!==b.id); saveBrands(arr); renderBrandList(); }; right.appendChild(loadBtn); right.appendChild(delBtn); el.appendChild(left); el.appendChild(right); cont.appendChild(el); }); }
document.getElementById('create-brand').addEventListener('click', ()=>{ const name=document.getElementById('new-brand-name').value.trim(); if(!name) return alert('请填写品牌名'); saveBrand(name,currentPalette.slice(0,3)); renderBrandList(); });
renderBrandList();

/* ========= 智能配色建议（模拟 AI） ========= */
function generateSmartSuggestions(picked){
  const box=document.getElementById('smart-suggestions'); box.innerHTML='';
  if(!picked||picked.length===0) return;
  const base=picked[0];
  const suggestions = [
    {name:'Minimal', pal:[base, shade(base,-28), shade(base,-58), '#FFFFFF', '#0B0F12']},
    {name:'Vibrant', pal:[base, hslAdjust(base,24,30,8), hslAdjust(base,-36,10,2), '#FFD166', '#FF6B6B']},
    {name:'Monochrome', pal:[base, hslAdjust(base,0,0,-10), hslAdjust(base,0,0,10), hslAdjust(base,0,0,-30), hslAdjust(base,0,0,30)]},
    {name:'Business', pal:[ '#0F1724', shade(base, -8), shade(base, -36), '#D1D5DB', '#111827' ]}
  ];
  suggestions.forEach(s=>{
    const card=document.createElement('div'); card.className='card'; card.style.display='flex'; card.style.alignItems='center'; card.style.justifyContent='space-between';
    const left=document.createElement('div'); left.style.display='flex'; left.style.gap='6px';
    s.pal.slice(0,5).forEach(c=>{ const sw=document.createElement('div'); sw.className='swatch small'; sw.style.background=c; sw.onclick=()=>{ currentPalette=s.pal.slice(0,5); updateUIFromPalette(); }; left.appendChild(sw); });
    const right=document.createElement('div'); right.style.display='flex'; right.style.flexDirection='column'; right.style.gap='6px';
    const t=document.createElement('div'); t.style.fontWeight='700'; t.textContent=s.name;
    const btn=document.createElement('button'); btn.className='btn'; btn.textContent='应用'; btn.onclick=()=>{ currentPalette=s.pal.slice(0,5); updateUIFromPalette(); };
    right.appendChild(t); right.appendChild(btn); card.appendChild(left); card.appendChild(right); box.appendChild(card);
  });
}

/* ========= 色彩和谐生成（惊喜） ========= */
document.getElementById('gen-harmony').addEventListener('click', ()=>{
  const type=document.getElementById('harmony-type').value; const base=currentPalette[0]||'#FF8A65';
  const pal = generateHarmony(base,type); currentPalette = pal.slice(0,5); updateUIFromPalette();
});
function generateHarmony(hex,type){
  const [r,g,b]=hexToRgb(hex); const hsl=rgbToHsl(r,g,b); const h = hsl[0]*360;
  let pals=[hex];
  if(type==='analogous'){ pals.push(hslAdjust(hex,30,10,6)); pals.push(hslAdjust(hex,-30,8,-6)); pals.push(shade(hex,-12)); pals.push(shade(hex,10)); }
  else if(type==='triadic'){ pals.push(hslAdjust(hex,120,0,0)); pals.push(hslAdjust(hex,-120,0,0)); pals.push(shade(hex,-10)); pals.push(shade(hex,20)); }
  else { pals.push(hslAdjust(hex,180,0,-6)); pals.push(hslAdjust(hex,180,0,6)); pals.push(shade(hex,-18)); pals.push(shade(hex,12)); }
  return pals;
}

/* ========= 分享链接 / CSS 导出（惊喜） ========= */
function makePermalink(palette){
  const payload = {palette, t:Date.now()};
  const str = btoa(encodeURIComponent(JSON.stringify(payload)));
  const url = location.origin + location.pathname + '#p=' + str;
  return url;
}
document.getElementById('copy-permalink').addEventListener('click', ()=>{ const url=makePermalink(currentPalette); navigator.clipboard.writeText(url).then(()=>alert('分享链接已复制')); });

document.getElementById('copy-css').addEventListener('click', ()=>{
  const css = generateCSSVars(currentPalette);
  navigator.clipboard.writeText(css).then(()=>alert('CSS 变量已复制到剪贴板'));
});
function generateCSSVars(pal){
  const [a,b,c,d,e]=pal.concat(['','','','','']).slice(0,5);
  return `:root{\n  --brand-1: ${a}; /* 60% */\n  --brand-2: ${b}; /* 30% */\n  --brand-3: ${c}; /* 10% */\n  --accent-1: ${d};\n  --accent-2: ${e};\n}\n/* Usage example */\n.header{ background: linear-gradient(90deg,var(--brand-1),var(--brand-2)); }`;
}

/* ========= 趋势图（基于灵感墙） ========= */
function renderTrendChart(){
  const wall = loadWall(); const buckets = new Array(12).fill(0);
  wall.forEach(e=> e.palette.forEach(c=>{ const h=rgbToHsl(...hexToRgb(c))[0]*360; const idx=Math.floor(h/30)%12; buckets[idx]+=1; }));
  const canvas=document.getElementById('trendChart'); const ctx=canvas.getContext('2d'); const w=canvas.width, h=canvas.height; ctx.clearRect(0,0,w,h);
  const max=Math.max(1,...buckets);
  for(let i=0;i<12;i++){ const bw=(w/12)-6; const x=i*(w/12)+3; const hh=(buckets[i]/max)*(h-20); const grad=ctx.createLinearGradient(0,h-10,0,h-10-hh); grad.addColorStop(0,'#243447'); grad.addColorStop(1,'#FF8A65'); ctx.fillStyle=grad; ctx.fillRect(x,h-10-hh,bw,hh); }
}
function renderTrendDashboard(){ renderTrendChart(); }
renderTrendDashboard();

/* ========= 拖拽分栏 ========= */
(function(){ const splitter=document.querySelector('.splitter'); const left=document.getElementById('left-panel'); let dragging=false,startX=0,startW=0; splitter.addEventListener('mousedown', (e)=>{ dragging=true; startX=e.clientX; startW=left.offsetWidth; document.body.style.cursor='col-resize'; }); window.addEventListener('mousemove', (e)=>{ if(!dragging) return; const dx=e.clientX-startX; let nw=startW+dx; nw=Math.max(260,Math.min(560,nw)); left.style.width=nw+'px'; }); window.addEventListener('mouseup', ()=>{ if(dragging){ dragging=false; document.body.style.cursor='default'; } }); })();

/* ========= 新手引导（首次） ========= */
(function(){ if(!localStorage.getItem('fcl_seen_tour')){ const overlay=document.createElement('div'); overlay.style.position='fixed'; overlay.style.inset=0; overlay.style.background='rgba(2,6,8,0.78)'; overlay.style.zIndex=9999; overlay.style.display='flex'; overlay.style.alignItems='center'; overlay.style.justifyContent='center'; const box=document.createElement('div'); box.style.width='780px'; box.style.background='#07111a'; box.style.padding='22px'; box.style.borderRadius='12px'; box.style.border='1px solid rgba(255,255,255,0.04)'; box.style.color='#e6eef3'; let step=0; const steps=[{t:'上传图片提取主色',d:'左侧上传图片，自动识别主色并映射情绪词汇。'},{t:'调整与渲染',d:'中间面板调节色相/饱和/亮度并实时预览面料质感。'},{t:'保存与导出',d:'右侧生成品牌色卡并导出 PNG / CSS / 分享链接（Pro 解锁高清）。'}]; const title=document.createElement('h2'); const desc=document.createElement('div'); desc.className='muted small'; const nav=document.createElement('div'); nav.style.display='flex'; nav.style.justifyContent='flex-end'; nav.style.marginTop='14px'; const skip=document.createElement('button'); skip.className='btn'; skip.textContent='跳过'; skip.onclick=closeOverlay; const next=document.createElement('button'); next.className='btn primary'; next.textContent='下一步'; next.onclick=()=>{ step++; if(step>=steps.length) closeOverlay(); else update(); }; nav.appendChild(skip); nav.appendChild(next); box.appendChild(title); box.appendChild(desc); box.appendChild(nav); overlay.appendChild(box); document.body.appendChild(overlay); function update(){ title.textContent=steps[step].t; desc.textContent=steps[step].d; if(step===steps.length-1) next.textContent='完成'; } function closeOverlay(){ localStorage.setItem('fcl_seen_tour','1'); document.body.removeChild(overlay); } update(); } })();

/* ========= 保存配色 ========== */
document.getElementById('save-palette').addEventListener('click', ()=>{
  const wall = loadWall(); wall.unshift({id:Date.now(), title:'Quick Save', palette:currentPalette.slice(0,5), time:new Date().toISOString()});
  if(!isProUser && wall.length>50) wall.length=50;
  saveWall(wall); renderWall(); renderTrendDashboard(); alert('配色已保存到灵感墙');
});

/* ========= 切换 Pro 模拟 ========= */
document.getElementById('toggle-pro').addEventListener('click', ()=>{ isProUser=!isProUser; document.getElementById('user-status').textContent=isProUser? 'Pro' : 'Free'; document.getElementById('adv-fabric').style.display=isProUser?'block':'none'; alert('已切换：'+(isProUser? '专业版 (Pro)':'免费版 (Free)')+'（仅本地模拟）'); });

/* ========= 辅助：保存临时会话 ========= */
function saveTempSession(){ localStorage.setItem('fcl_session', JSON.stringify({palette:currentPalette,ts:Date.now()})); }
(function(){ const s=localStorage.getItem('fcl_session'); if(s){ try{ const obj=JSON.parse(s); if(obj.palette) currentPalette=obj.palette; }catch(e){} } updateUIFromPalette(); })();

/* ========= 分享 / permalink 解析 ========= */
(function(){ if(location.hash && location.hash.startsWith('#p=')){ try{ const encoded = location.hash.slice(3); const raw = decodeURIComponent(atob(encoded)); const obj=JSON.parse(raw); if(obj.palette){ currentPalette=obj.palette; updateUIFromPalette(); alert('已应用来自分享链接的配色'); } }catch(e){} } })();

/* ========= 保存与渲染尾声 ========= */
updateUIFromPalette();

/* ========= 生成/复制 CSS（按钮）已绑定上方 ========== */

/* ========= Trend updates after any wall change ========= */
function renderTrendChart(){ renderTrendDashboard(); }

/* ========== 结束 ========== */
</script>
</body>
</html>
