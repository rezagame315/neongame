<!doctype html>
<html lang="fa" dir="rtl">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no,viewport-fit=cover">
<meta name="theme-color" content="#080b19">
<title>Neon Flappy | پرنده نئونی</title>
<script src="https://developer.eitaa.com/eitaa-web-app.js"></script>
<style>

:root{--banner-h:56px;--cyan:#38f5ff;--pink:#ff3ec9;--violet:#8c62ff;--ink:#080b19}*{box-sizing:border-box}html,body{margin:0;width:100%;height:100%;overflow:hidden;background:var(--ink);color:#f4f7ff;font-family:Tahoma,"Segoe UI",sans-serif;touch-action:none;-webkit-tap-highlight-color:transparent;user-select:none}body{display:flex;flex-direction:column;height:100vh;height:100dvh;min-height:0;background:radial-gradient(ellipse at 50% 30%,#151c3d 0%,#0b1025 42%,#050711 100%)}#stage{flex:1 1 auto;min-height:0;display:grid;place-items:center;width:100%;overflow:hidden}#game{position:relative;width:min(100vw,58vh);height:min(100%,177.78vw);max-width:520px;max-height:calc(100dvh - var(--banner-h,56px) - 2px);overflow:hidden;background:#0b1025;isolation:isolate;box-shadow:0 0 60px #05d9ff18,0 0 120px #843dff12}canvas{display:block;width:100%;height:100%;touch-action:none}.topline{position:absolute;top:max(16px,env(safe-area-inset-top));right:18px;left:18px;display:flex;align-items:center;justify-content:space-between;pointer-events:none}.brand{font-size:12px;letter-spacing:2px;color:#8ba0c8;font-weight:700;direction:ltr}.brand b{color:var(--cyan);text-shadow:0 0 12px #38f5ff}.sound{pointer-events:auto;border:1px solid #ffffff20;background:#111a32cc;color:#d9edff;border-radius:50%;width:38px;height:38px;font-size:17px;cursor:pointer;backdrop-filter:blur(10px)}.hud{position:absolute;top:69px;left:0;right:0;display:flex;justify-content:center;gap:10px;pointer-events:none;transition:opacity .2s}.pill{min-width:94px;text-align:center;padding:8px 14px;border-radius:14px;background:#0b1229bd;border:1px solid #8c9ec522;box-shadow:0 4px 20px #0003;backdrop-filter:blur(8px)}.pill small{display:block;color:#8d9cbe;font-size:10px;margin-bottom:3px}.pill strong{font-size:20px;line-height:1;color:#fff;text-shadow:0 0 14px #38f5ff88;direction:ltr;display:block}.overlay{position:absolute;inset:0;display:grid;place-items:center;padding:24px;background:linear-gradient(180deg,#080b1930,#080b1955);transition:opacity .25s,visibility .25s}.overlay.hidden{opacity:0;visibility:hidden;pointer-events:none}.card{width:min(100%,350px);padding:30px 24px 25px;text-align:center;border:1px solid #a8c6ff25;border-radius:25px;background:linear-gradient(145deg,#141d38ed,#0d1329ed);box-shadow:0 24px 80px #0008,0 0 40px #692bff20;backdrop-filter:blur(18px);animation:rise .45s ease both}.logo-mark{width:64px;height:64px;margin:0 auto 14px;display:grid;place-items:center;border-radius:20px;transform:rotate(-8deg);border:1px solid #38f5ff66;background:linear-gradient(140deg,#38f5ff25,#ff3ec91c);box-shadow:0 0 25px #38f5ff25,inset 0 0 20px #38f5ff12;font-size:32px}.eyebrow{font-size:11px;color:var(--cyan);letter-spacing:3px;direction:ltr;margin:0 0 6px;text-shadow:0 0 12px #38f5ff88}.card h1{font-size:27px;margin:0 0 7px;font-weight:800}.card h1 span{color:var(--cyan);text-shadow:0 0 16px #38f5ff70}.sub{color:#a9b5d0;font-size:13px;line-height:1.9;margin:0 0 20px}.scores{display:flex;gap:10px;margin:20px 0}.scorebox{flex:1;padding:12px 8px;background:#080d1fc9;border:1px solid #ffffff12;border-radius:14px}.scorebox small{display:block;color:#929fbd;font-size:11px;margin-bottom:6px}.scorebox strong{font-size:23px;direction:ltr;display:block;color:#fff}.scorebox.current strong{color:var(--cyan);text-shadow:0 0 12px #38f5ff60}.button{width:100%;border:0;border-radius:14px;padding:14px 18px;color:#06101b;background:linear-gradient(100deg,#38f5ff,#61dfff 48%,#9f7cff);font:700 15px Tahoma,sans-serif;box-shadow:0 8px 25px #24dcff33;cursor:pointer;transition:transform .15s,filter .15s}.button:active{transform:scale(.97);filter:brightness(1.1)}.hint{font-size:11px;color:#7786a6;margin:15px 0 0}.hint kbd{font:inherit;color:#c5d4f1;border:1px solid #5a698544;background:#ffffff09;border-radius:5px;padding:2px 6px}.toast{position:absolute;bottom:max(28px,env(safe-area-inset-bottom));left:0;right:0;text-align:center;color:#a8b8d6;font-size:12px;text-shadow:0 1px 8px #000;pointer-events:none;opacity:.86}.hiddenHud{opacity:0}.newbest{color:#ffdf74!important;text-shadow:0 0 16px #ffbe33!important}@keyframes rise{from{transform:translateY(12px) scale(.97);opacity:0}to{transform:none;opacity:1}}@media(min-width:700px){#game{border:1px solid #ffffff10;border-radius:20px}}@media(max-height:580px){.card{padding:20px}.logo-mark{width:48px;height:48px;font-size:25px;margin-bottom:8px}.scores{margin:12px 0}.card h1{font-size:23px}}

.gameover-actions{display:flex;flex-direction:column;gap:9px;margin-top:18px}
.btn{border:0;border-radius:14px;padding:13px 16px;font:700 15px Tahoma,sans-serif;cursor:pointer;display:flex;align-items:center;justify-content:center;gap:8px;transition:transform .15s,filter .15s;width:100%}
.btn:active{transform:scale(.97);filter:brightness(1.08)}
.btn-retry{color:#06101b;background:linear-gradient(100deg,#38f5ff,#61dfff 48%,#9f7cff);box-shadow:0 8px 25px #24dcff33}
.btn-home{color:#d7e4ff;background:#ffffff10;border:1px solid #a8c6ff33;box-shadow:none}
.btn-ad{color:#ffe9fb;background:linear-gradient(100deg,#ff3ec9,#b04cff);box-shadow:0 8px 25px #ff3ec933;font-size:14px}
.btn .ic{font-size:16px}
.btn:disabled{opacity:.55;cursor:default}
@media(max-height:620px){.btn{padding:11px 14px;font-size:14px}.gameover-actions{gap:7px;margin-top:12px}}

/* ---------- rewarded video hook (برای این بازی) ---------- */
#rewarded-video-hook{display:none}

/* ---------- بنر تبلیغاتی پایین صفحه ---------- */
#adly-banner-bottom{flex:0 0 auto;width:100%;min-height:56px;display:flex;align-items:center;justify-content:center;padding:4px 10px calc(4px + env(safe-area-inset-bottom));background:linear-gradient(180deg,#0a1022f2,#06090f);border-top:1px solid #38f5ff2e;box-shadow:0 -8px 26px #0006,0 -1px 0 #ff3ec920;position:relative;z-index:5;touch-action:manipulation}
#adly-banner-bottom::before{content:"تبلیغ";position:absolute;top:-9px;right:8px;font:700 9px Tahoma,sans-serif;letter-spacing:1px;color:#8ba0c8;background:#0a1022;border:1px solid #38f5ff33;border-radius:6px;padding:1px 6px;line-height:1.4}
#adly-banner-bottom .banner-slot{width:100%;max-width:360px;height:50px;display:flex;align-items:center;justify-content:center;border-radius:10px;border:1px dashed #38f5ff33;background:repeating-linear-gradient(135deg,#0e1730,#0e1730 8px,#111c3a 8px,#111c3a 16px);color:#7f93b8;font:700 11px Tahoma,sans-serif;overflow:hidden;transition:border-color .2s,background .2s}
#adly-banner-bottom .banner-slot.loaded{border-style:solid;border-color:#ff3ec955;background:#080d1f}
#adly-banner-bottom .banner-slot img,#adly-banner-bottom .banner-slot canvas,#adly-banner-bottom .banner-slot iframe{max-width:100%;max-height:50px;display:block;border:0}
@media(max-width:380px){#adly-banner-bottom .banner-slot{height:44px}#adly-banner-bottom .banner-slot img{max-height:44px}}
@media(max-height:600px){#adly-banner-bottom{min-height:48px}#adly-banner-bottom .banner-slot{height:42px}}
</style></head>
<body><div id="stage"><main id="game" aria-label="بازی پرنده نئونی">
<canvas id="canvas"></canvas>
<div class="topline"><div class="brand">NEON <b>FLAPPY</b></div><button class="sound" id="soundBtn" type="button" aria-label="قطع یا وصل صدا">♫</button></div>
<div class="hud hiddenHud" id="hud"><div class="pill"><small>امتیاز</small><strong id="score">0</strong></div><div class="pill"><small>رکورد</small><strong id="bestHud">0</strong></div></div>
<section class="overlay" id="overlay"><div class="card" id="card"></div></section>
<div class="toast" id="toast">برای پرواز لمس کن یا Space بزن</div>
</main></div>
<!-- ===== بنر تبلیغاتی پایین (فقط یک کد بنر در slot قرار دهید) ===== -->
<div id="adly-banner-bottom" role="complementary" aria-label="تبلیغات">
  <div class="banner-slot" id="banner-slot" data-banner-ready="false">
  <div id="adly-container"></div>
  <script src="https://myadino.ir/widget/adly-widget.js"></script>
  <script>
    AdlyWidget.init({
      apiKey: 'secret-abe2eabd',
      containerId: 'adly-container',
      barnamk: 'neon_game_app',
      appRef: 175
    });
  </script>
</div>
</div>

<script>
(()=>{'use strict';
const canvas=document.getElementById('canvas'),ctx=canvas.getContext('2d'),game=document.getElementById('game'),stage=document.getElementById('stage'),banner=document.getElementById('adly-banner-bottom'),bannerSlot=document.getElementById('banner-slot'),overlay=document.getElementById('overlay'),card=document.getElementById('card'),hud=document.getElementById('hud'),scoreEl=document.getElementById('score'),bestHud=document.getElementById('bestHud'),toast=document.getElementById('toast'),soundBtn=document.getElementById('soundBtn');
let W=360,H=640,dpr=1,last=0,mode='ready',score=0,best=0,muted=false,audio=null,world=0,shake=0,flash=0,adBusy=false;const pipes=[],particles=[];
try{best=+(localStorage.getItem('neonFlappyBest')||0)||0}catch(e){}
const bird={x:0,y:0,vy:0,r:14,rot:0};

/* ---------- Eitaa WebApp ---------- */
const wa=window.Eitaa&&window.Eitaa.WebApp?window.Eitaa.WebApp:null;
const backBtn=wa&&wa.BackButton?wa.BackButton:null;
function tg(fn){try{fn()}catch(e){console.warn('Eitaa:',e)}}
if(wa){
  tg(()=>wa.ready());
  tg(()=>wa.expand());
  tg(()=>wa.disableVerticalSwipes&&wa.disableVerticalSwipes());
  tg(()=>wa.setHeaderColor&&wa.setHeaderColor('#080b19'));
  tg(()=>wa.setBackgroundColor&&wa.setBackgroundColor('#080b19'));
  tg(()=>wa.onEvent&&wa.onEvent('themeChanged',()=>{}));
}
function syncBack(){
  if(!backBtn)return;
  tg(()=>{
    if(mode==='ready'){ backBtn.hide ? backBtn.hide() : backBtn.offClick(backHandler); }
    else { backBtn.show && backBtn.show(); backBtn.onClick(backHandler); }
  });
}
function backHandler(){
  if(mode==='ready'){ // let Eitaa close the mini-app
    tg(()=>wa.close&&wa.close());
    return;
  }
  goHome();
}

/* ---------- audio ---------- */
function sound(type){if(muted)return;try{audio ||= new(window.AudioContext||window.webkitAudioContext)();if(audio.state==='suspended')audio.resume();const now=audio.currentTime,o=audio.createOscillator(),g=audio.createGain();o.connect(g);g.connect(audio.destination);let f=520,d=.12,w='sine';if(type==='jump'){f=520;o.frequency.setValueAtTime(520,now);o.frequency.exponentialRampToValueAtTime(760,now+.08);w='triangle';d=.1;g.gain.setValueAtTime(.09,now)}else if(type==='score'){f=760;o.frequency.setValueAtTime(760,now);o.frequency.exponentialRampToValueAtTime(1180,now+.12);w='sine';d=.16;g.gain.setValueAtTime(.08,now)}else if(type==='hit'){f=180;o.frequency.setValueAtTime(190,now);o.frequency.exponentialRampToValueAtTime(65,now+.28);w='sawtooth';d=.3;g.gain.setValueAtTime(.11,now)}else{f=330;o.frequency.setValueAtTime(330,now);o.frequency.exponentialRampToValueAtTime(110,now+.35);w='triangle';d=.38;g.gain.setValueAtTime(.08,now)}o.type=w;g.gain.exponentialRampToValueAtTime(.001,now+d);o.start(now);o.stop(now+d)}catch(e){}}
soundBtn.addEventListener('click',e=>{e.stopPropagation();muted=!muted;soundBtn.textContent=muted?'♩':'♫';soundBtn.style.opacity=muted?'.5':'1';if(!muted)sound('score')});

/* ---------- layout ---------- */
function resize(){const r=game.getBoundingClientRect();if(!r.width||!r.height)return;W=r.width;H=r.height;dpr=Math.min(window.devicePixelRatio||1,2);canvas.width=Math.round(W*dpr);canvas.height=Math.round(H*dpr);ctx.setTransform(dpr,0,0,dpr,0,0);bird.x=W*.29;if(mode==='ready')bird.y=H*.43;else bird.y=Math.min(Math.max(bird.y,bird.r+2),H-bird.r-56);}
if(window.ResizeObserver){const ro=new ResizeObserver(()=>resize());ro.observe(stage);ro.observe(game);ro.observe(banner);}
window.addEventListener('resize',resize);window.addEventListener('orientationchange',()=>setTimeout(resize,220));
/* بنر: فضا را از canvas می‌گیرد نه این‌که روی بازی بیفتد؛ اندازه‌ها با تغییر ارتفاع بنر هم‌گام می‌شوند */
function syncBannerSpace(){
  const h=banner?banner.offsetHeight:0;
  document.documentElement.style.setProperty('--banner-h',h+'px');
  game.style.maxHeight='calc(100dvh - '+(h+2)+'px)';
  resize();
}
if(window.ResizeObserver&&banner){new ResizeObserver(()=>syncBannerSpace()).observe(banner);}
syncBannerSpace();
resize();bestHud.textContent=best;

/* ---------- screens ---------- */
function showReady(){
  mode='ready';particles.length=0;pipes.length=0;score=0;shake=0;flash=0;
  hud.classList.add('hiddenHud');toast.textContent='برای پرواز لمس کن یا Space بزن';
  overlay.classList.remove('hidden');
  card.innerHTML='<div class="logo-mark">✦</div><p class="eyebrow">NEON FLAPPY</p><h1>پرنده <span>نئونی</span></h1><p class="sub">در شهر نئون پرواز کن، از دروازه‌ها بگذر و رکوردت را بشکن!</p><button class="button" id="startBtn" type="button">شروع بازی <span style="font-size:18px">←</span></button><p class="hint">لمس صفحه یا <kbd>Space</kbd> برای پرواز</p>';
  document.getElementById('startBtn').addEventListener('click',e=>{e.stopPropagation();start()});
  bestHud.textContent=best;
  syncBack();
}
function showDead(){
  const isNew=score>=best&&score>0;
  card.innerHTML='<div class="logo-mark">✧</div><p class="eyebrow">FLIGHT ENDED</p><h1>پایان <span>پرواز</span></h1>'+
  '<div class="scores"><div class="scorebox current"><small>امتیاز این بازی</small><strong>'+score+'</strong></div><div class="scorebox"><small>بهترین رکورد</small><strong class="'+(isNew?'newbest':'')+'">'+best+(isNew?' ✦':'')+'</strong></div></div>'+
  '<div class="gameover-actions">'+
    '<button class="btn btn-retry" id="retryBtn" type="button"><span class="ic">↻</span>تلاش دوباره</button>'+
    '<button class="btn btn-home" id="homeBtn" type="button"><span class="ic">⌂</span>صفحه اول / خانه</button>'+
    '<button class="btn btn-ad" id="adBtn" type="button"><span class="ic">▶</span>تماشای ویدیو و ادامه بازی</button>'+
  '</div>';
  document.getElementById('retryBtn').addEventListener('click',e=>{e.stopPropagation();start()});
  document.getElementById('homeBtn').addEventListener('click',e=>{e.stopPropagation();goHome()});
  document.getElementById('adBtn').addEventListener('click',e=>{e.stopPropagation();watchAd()});
  overlay.classList.remove('hidden');
  syncBack();
}
function goHome(){if(mode==='playing'||mode==='dead')showReady();}

/* ---------- game flow ---------- */
function start(){if(mode==='playing')return;mode='playing';score=0;pipes.length=0;particles.length=0;bird.y=H*.43;bird.vy=0;bird.rot=0;world=0;shake=0;flash=0;hud.classList.remove('hiddenHud');overlay.classList.add('hidden');toast.textContent='';scoreEl.textContent='0';bestHud.textContent=best;flap();syncBack()}
function resume(){if(mode!=='dead')return;mode='playing';pipes.length=0;particles.length=0;bird.vy=0;bird.y=Math.min(Math.max(bird.y,H*.2),H*.6);hud.classList.remove('hiddenHud');overlay.classList.add('hidden');toast.textContent='دوباره پرواز!';syncBack()}
function flap(){if(mode==='ready'){start();return}if(mode!=='playing')return;bird.vy=-H*.58;sound('jump');for(let i=0;i<5;i++)particles.push({x:bird.x-bird.r*.6,y:bird.y+(Math.random()-.5)*10,vx:-35-Math.random()*90,vy:(Math.random()-.5)*90,life:.24+Math.random()*.2,size:1.5+Math.random()*2,color:i%2?'#38f5ff':'#ff3ec9'})}
function die(){if(mode!=='playing')return;mode='dead';sound('hit');setTimeout(()=>sound('over'),125);shake=10;flash=.22;hud.classList.add('hiddenHud');toast.textContent='';for(let i=0;i<34;i++){let a=Math.random()*Math.PI*2,s=50+Math.random()*240;particles.push({x:bird.x,y:bird.y,vx:Math.cos(a)*s,vy:Math.sin(a)*s,life:.45+Math.random()*.65,size:2+Math.random()*4,color:['#38f5ff','#ff3ec9','#ffe36e','#a879ff'][i%4]})}if(score>best){best=score;try{localStorage.setItem('neonFlappyBest',best)}catch(e){}}setTimeout(()=>{if(mode==='dead')showDead()},520);syncBack()}

/* ---------- بنر تبلیغاتی پایین: API ساده برای تزریق کد بنر ---------- */
function mountBanner(html){
  if(!bannerSlot)return;
  bannerSlot.innerHTML=html;              // فقط یک کد بنر اینجا قرار می‌گیرد
  bannerSlot.classList.add('loaded');
  bannerSlot.dataset.bannerReady='true';
  syncBannerSpace();                      // اگر ارتفاع بنر عوض شد، بازی خودش را تنظیم می‌کند
}
function clearBanner(){if(!bannerSlot)return;bannerSlot.innerHTML='slider banner 320x50';bannerSlot.classList.remove('loaded');bannerSlot.dataset.bannerReady='false';syncBannerSpace();}
window.NeonFlappyAds={mountBanner:mountBanner,clearBanner:clearBanner};

/* ---------- rewarded ad hook (Adly) ---------- */
function watchAd(){
  if(adBusy)return;adBusy=true;
  const btn=document.getElementById('adBtn');if(btn){btn.disabled=true;btn.textContent='در حال دریافت ویدیو…';}
  const onReward=()=>{adBusy=false;resume()};
  const onFail=()=>{adBusy=false;if(mode==='dead')showDead();};
  try{
    const A=window.Adly||(window.Eitaa&&window.Eitaa.Ad)||null;
    if(A&&typeof A.showRewarded==='function'){
      A.showRewarded({placement:'flappy_revive',onReward:onReward,onError:onFail,onClose:onFail});
    }else if(A&&A.loaded&&typeof A.showRewardedAd==='function'){
      A.showRewardedAd({onReward:onReward,onError:onFail});
    }else{
      // Test fallback
      setTimeout(()=>{
        adBusy=false;
        try{alert('ویدیو تبلیغاتی (نسخه آزمایشی) — جایزه دریافت شد');}catch(e){}
        onReward();
      },700);
    }
  }catch(e){console.warn(e);onFail();}
}


/* ---------- physics ---------- */
function update(dt){world+=dt;if(mode==='playing'){bird.vy+=H*1.45*dt;bird.y+=bird.vy*dt;bird.rot=Math.max(-.45,Math.min(1.15,bird.vy/(H*.8)));let speed=W*.50*difficulty().speed;for(const p of pipes){p.x-=speed*dt;if(!p.passed&&p.x+p.w<bird.x){p.passed=true;score++;scoreEl.textContent=score;sound('score');if(score%5===0)toast.textContent='عالیه! همین‌طور ادامه بده ✦'}}while(pipes.length&&pipes[0].x+pipes[0].w<-10)pipes.shift();if(pipes.length===0||pipes[pipes.length-1].x<W*.42)addPipe();const hit=bird.r-5;if(bird.y-hit<0||bird.y+hit>H-54)die();for(const p of pipes){if(bird.x+hit>p.x&&bird.x-hit<p.x+p.w&&(bird.y-hit<p.top||bird.y+hit>p.top+p.gap))die()}}else if(mode==='ready'){bird.y=H*.43+Math.sin(world*3)*8;bird.rot=Math.sin(world*2)*.06}for(let i=particles.length-1;i>=0;i--){let p=particles[i];p.x+=p.vx*dt;p.y+=p.vy*dt;p.vy+=90*dt;p.life-=dt;if(p.life<=0)particles.splice(i,1)}shake=Math.max(0,shake-dt*30);flash=Math.max(0,flash-dt)}

/* ---------- render ---------- */
function rr(x,y,w,h,r){ctx.beginPath();ctx.roundRect(x,y,w,h,r)}
function drawBg(){let g=ctx.createLinearGradient(0,0,0,H);g.addColorStop(0,'#0b1028');g.addColorStop(.58,'#111533');g.addColorStop(1,'#11152b');ctx.fillStyle=g;ctx.fillRect(0,0,W,H);let glow=ctx.createRadialGradient(W*.72,H*.28,5,W*.72,H*.28,W*.7);glow.addColorStop(0,'#52328a30');glow.addColorStop(1,'#15112a00');ctx.fillStyle=glow;ctx.fillRect(0,0,W,H);ctx.save();for(let i=0;i<56;i++){let x=((i*83+23)%W),y=((i*131+11)%H),tw=.4+((i*7)%8)/10;ctx.globalAlpha=.25+.25*Math.sin(world*2+i);ctx.fillStyle=i%5===0?'#ff6be1':'#a9dcff';ctx.fillRect(x,y,tw,tw)}ctx.globalAlpha=1;for(let layer=0;layer<2;layer++){let base=H-53,step=46+layer*18,off=(world*(layer?17:30))%step;ctx.beginPath();ctx.moveTo(-step,base);for(let x=-step;x<W+step;x+=step){let yy=base-((x/step*19+layer*13)%5+2)*(layer?15:22);ctx.lineTo(x-off,yy);ctx.lineTo(x+step*.5-off,base)}ctx.lineTo(W,H);ctx.lineTo(0,H);ctx.closePath();ctx.fillStyle=layer?'#121a38':'#151934';ctx.fill()}ctx.strokeStyle='#253359';ctx.globalAlpha=.45;ctx.lineWidth=1;for(let i=1;i<5;i++){let y=H-53+i*i*13;ctx.beginPath();ctx.moveTo(0,y);ctx.lineTo(W,y);ctx.stroke()}ctx.restore();ctx.fillStyle='#12162c';ctx.fillRect(0,H-54,W,54);ctx.fillStyle='#38f5ff';ctx.globalAlpha=.8;ctx.fillRect(0,H-54,W,2);ctx.globalAlpha=1;for(let x=-20;x<W+30;x+=34){ctx.fillStyle='#ff3ec9';ctx.globalAlpha=.25;ctx.fillRect(x-(world*42%34),H-17,12,2)}ctx.globalAlpha=1}
function drawPipe(p){let cap=13;ctx.save();ctx.shadowBlur=19;ctx.shadowColor='#38f5ff';let grad=ctx.createLinearGradient(p.x,0,p.x+p.w,0);grad.addColorStop(0,'#12344c');grad.addColorStop(.45,'#17556a');grad.addColorStop(1,'#10263e');ctx.fillStyle=grad;ctx.strokeStyle='#38f5ff';ctx.lineWidth=2;let pieces=[[p.x,0,p.w,p.top],[p.x,p.top-cap,p.w,cap],[p.x,p.top+p.gap,p.w,H-(p.top+p.gap)-54],[p.x,p.top+p.gap,p.w,cap]];for(const [x,y,w,h] of pieces){rr(x,y,w,h,5);ctx.fill();ctx.stroke()}ctx.shadowBlur=0;ctx.fillStyle='#8effff';ctx.globalAlpha=.55;ctx.fillRect(p.x+8,12,2,Math.max(0,p.top-24));ctx.fillRect(p.x+8,p.top+p.gap+18,2,Math.max(0,H-p.top-p.gap-80));ctx.restore()}
function drawBird(){ctx.save();ctx.translate(bird.x,bird.y);ctx.rotate(bird.rot);ctx.shadowBlur=24;ctx.shadowColor='#38f5ff';let g=ctx.createLinearGradient(-bird.r,-bird.r,bird.r,bird.r);g.addColorStop(0,'#fff276');g.addColorStop(.38,'#38f5ff');g.addColorStop(1,'#7375ff');ctx.fillStyle=g;ctx.beginPath();ctx.ellipse(0,0,bird.r+2,bird.r*.8,0,0,Math.PI*2);ctx.fill();ctx.shadowBlur=12;ctx.shadowColor='#ff3ec9';ctx.fillStyle='#ff3ec9';ctx.beginPath();ctx.ellipse(-5,4,8,5,-.4,0,Math.PI*2);ctx.fill();ctx.fillStyle='#ffb14d';ctx.beginPath();ctx.moveTo(bird.r-1,-2);ctx.lineTo(bird.r+11,2);ctx.lineTo(bird.r-1,6);ctx.closePath();ctx.fill();ctx.shadowBlur=0;ctx.fillStyle='#071025';ctx.beginPath();ctx.arc(5,-5,3.4,0,Math.PI*2);ctx.fill();ctx.fillStyle='#fff';ctx.beginPath();ctx.arc(6,-6,1.2,0,Math.PI*2);ctx.fill();ctx.restore()}
function difficulty(){const steps=Math.floor(score/5);return{gap:Math.max(135,Math.min(200,H*.30)-steps*5),speed:Math.min(1.4,1+steps*.04)}}
function addPipe(){let gap=difficulty().gap,margin=100,center=margin+Math.random()*(H-gap-170);pipes.push({x:W+30,w:Math.max(58,W*.17),gap,top:center,passed:false})}

function render(){ctx.save();if(shake>0)ctx.translate((Math.random()-.5)*shake,(Math.random()-.5)*shake);drawBg();for(const p of pipes)drawPipe(p);for(const p of particles){ctx.globalAlpha=Math.max(0,Math.min(1,p.life*2));ctx.shadowBlur=10;ctx.shadowColor=p.color;ctx.fillStyle=p.color;ctx.beginPath();ctx.arc(p.x,p.y,p.size*Math.min(1,p.life*2),0,Math.PI*2);ctx.fill()}ctx.globalAlpha=1;ctx.shadowBlur=0;if(mode!=='dead'||particles.length<10)drawBird();if(mode==='ready'){ctx.fillStyle='#dbeaff';ctx.globalAlpha=.75;ctx.font='13px Tahoma';ctx.textAlign='center';ctx.fillText('برای شروع، لمس کن',W/2,H*.61);ctx.globalAlpha=1}if(flash>0){ctx.fillStyle='#ff3ec9';ctx.globalAlpha=flash*1.7;ctx.fillRect(0,0,W,H)}ctx.restore()}
function frame(t){let dt=Math.min((t-last)/1000||0,0.034);last=t;update(dt);render();requestAnimationFrame(frame)}requestAnimationFrame(frame);

/* ---------- input ---------- */
function input(e){if(e)e.preventDefault();if(mode==='dead')return;flap()}
game.addEventListener('pointerdown',e=>{if(e.target.closest('.card')||e.target.closest('#soundBtn'))return;input(e)},{passive:false});
window.addEventListener('keydown',e=>{if(['Space','ArrowUp','KeyW'].includes(e.code)){e.preventDefault();if(!e.repeat)input(e)}if(e.code==='Enter'&&mode==='ready')start()});
window.addEventListener('contextmenu',e=>e.preventDefault());
document.addEventListener('visibilitychange',()=>{last=performance.now();});

showReady();
})();
</script></body></html>
