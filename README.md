<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no,viewport-fit=cover">
<meta name="theme-color" content="#4e8ef7">
<title>С днём рождения! 🥔</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Neucha&family=Nunito:wght@900&display=swap" rel="stylesheet">
<style>
*{box-sizing:border-box;margin:0;padding:0}
[hidden]{display:none!important}
html,body{height:100%;overflow:hidden;background:#4e8ef7}
body{font-family:'Nunito',system-ui,sans-serif;-webkit-user-select:none;user-select:none;-webkit-touch-callout:none;-webkit-tap-highlight-color:transparent;touch-action:manipulation}
.full{position:fixed;top:0;left:0;right:0;bottom:0}

#sky{z-index:0;overflow:hidden;pointer-events:none;background:radial-gradient(ellipse 75% 42% at 50% 50%,rgba(255,255,255,.5),rgba(255,255,255,0) 72%),linear-gradient(180deg,#4e8ef7 0%,#79adff 55%,#a3c7ff 100%)}
.cloud{position:absolute;left:0;animation:drift linear infinite}
.cloud svg{display:block;width:100%;height:100%}
@keyframes drift{from{transform:translateX(-110%)}to{transform:translateX(calc(100vw + 10%))}}

#stage{z-index:2;display:flex;flex-direction:column;align-items:center;touch-action:none;transition:opacity .5s ease,transform .5s ease}
#stage.out{opacity:0;transform:scale(.9);pointer-events:none}
#pots{flex:1;min-height:0;width:100%;display:flex;flex-wrap:wrap;align-content:center;align-items:flex-end;justify-content:center;padding:4vh 2vw 0;padding-top:calc(env(safe-area-inset-top,0px) + 4vh);opacity:0;transform:translateY(24px) scale(.96);transition:opacity .6s ease,transform .7s cubic-bezier(.3,1.4,.5,1)}
#pots.ready{opacity:1;transform:none}
.slot{position:relative;margin:3vh 1.5vw;--d:0s}
.slot::after{content:'';position:absolute;left:18%;right:18%;bottom:-12px;height:16px;border-radius:50%;background:rgba(28,58,140,.28);filter:blur(4px);animation:shade 3.4s ease-in-out infinite;animation-delay:var(--d)}
.pot{position:relative;z-index:1;cursor:pointer;animation:float 3.4s ease-in-out infinite;animation-delay:var(--d)}
.pot-in{transform-origin:50% 100%}
.pot-in.hop{animation:hop .5s cubic-bezier(.25,.9,.35,1)}
.pot img,.pot .fb{display:block;pointer-events:none;filter:drop-shadow(4px 0 0 #fff) drop-shadow(-4px 0 0 #fff) drop-shadow(0 4px 0 #fff) drop-shadow(0 -4px 0 #fff) drop-shadow(0 5px 6px rgba(28,58,140,.22))}
.pot img{max-width:var(--mw);max-height:var(--mh);width:auto;height:auto;border-radius:22px}
.pot .fb{width:var(--fw);height:calc(var(--fw) * 1.2);overflow:visible}
@keyframes float{0%,100%{transform:translateY(0) rotate(-2deg)}50%{transform:translateY(-14px) rotate(2deg)}}
@keyframes shade{0%,100%{transform:scaleX(1);opacity:1}50%{transform:scaleX(.8);opacity:.55}}
@keyframes hop{
  0%{transform:translateY(0) rotate(0deg) scale(1,1)}
  14%{transform:translateY(0) rotate(0deg) scale(1.14,.84)}
  42%{transform:translateY(-16%) rotate(var(--tilt,6deg)) scale(.93,1.09)}
  68%{transform:translateY(0) rotate(0deg) scale(1.06,.95)}
  84%{transform:translateY(0) rotate(0deg) scale(.98,1.02)}
  100%{transform:translateY(0) rotate(0deg) scale(1,1)}}

#cta{flex:none;width:100%;padding:10px 16px 30px;padding-bottom:calc(env(safe-area-inset-bottom,0px) + 30px);font-weight:900;font-size:clamp(28px,8.4vw,46px);line-height:1.1;color:#fff;text-align:center;text-shadow:0 4px 0 #3a6fe0,0 10px 24px rgba(28,58,140,.35);pointer-events:none}
#cta span{display:inline-block;animation:breathe 2.4s ease-in-out infinite}
@keyframes breathe{0%,100%{transform:scale(1)}50%{transform:scale(1.06)}}

#memes{z-index:5;pointer-events:none;overflow:hidden}
.meme{position:absolute;transform:translate(-50%,-50%) rotate(var(--r));animation:memeIn .45s cubic-bezier(.3,1.6,.5,1) both}
.meme img{display:block;box-sizing:content-box;border:5px solid #fff;border-radius:16px;background:#fff;box-shadow:0 16px 34px rgba(20,40,110,.38)}
.meme.bye{animation:memeOut .35s ease-in forwards}
@keyframes memeIn{from{opacity:0;transform:translate(-50%,-50%) rotate(calc(var(--r) - 30deg)) scale(.2)}to{opacity:1;transform:translate(-50%,-50%) rotate(var(--r)) scale(1)}}
@keyframes memeOut{from{opacity:1;transform:translate(-50%,-50%) rotate(var(--r)) scale(1)}to{opacity:0;transform:translate(-50%,-80%) rotate(calc(var(--r) + 12deg)) scale(.7)}}

#env{--ew:min(78vw,340px);position:fixed;left:50%;top:47%;z-index:6;width:var(--ew);height:calc(var(--ew) * .66);transform:translate(-50%,-50%) scale(0) rotate(-14deg);transition:transform .75s cubic-bezier(.3,1.5,.5,1),opacity .5s ease}
#env.in{transform:translate(-50%,-50%) scale(1) rotate(-3deg)}
#env.gone{opacity:0;transform:translate(-50%,-25%) scale(.85) rotate(-3deg)}
#env>div{position:absolute}
.e-back{top:0;left:0;right:0;bottom:0;z-index:0;background:#d7e4ff;border-radius:14px;box-shadow:0 22px 46px rgba(20,40,110,.35)}
.e-paper{left:7%;right:7%;top:5%;height:88%;z-index:2;background:#fffdf7;border-radius:10px;transition:transform .8s cubic-bezier(.3,1.25,.5,1)}
.e-paper::before{content:'';position:absolute;left:14%;right:14%;top:14%;height:42%;background:repeating-linear-gradient(180deg,#dfe6f6 0 3px,transparent 3px 12px)}
#env.peek .e-paper{transform:translateY(-55%)}
.e-front{top:0;left:0;right:0;bottom:0;z-index:3;border-radius:0 0 14px 14px;overflow:hidden}
.e-flap{left:0;top:0;width:100%;height:58%;z-index:4;transform-origin:50% 0;transform:perspective(900px) rotateX(0deg);transition:transform .6s ease-in-out}
#env.open .e-flap{transform:perspective(900px) rotateX(180deg)}
#env.peek .e-flap{z-index:1}
.e-front svg,.e-flap svg{display:block;width:100%;height:100%}
.e-seal{left:50%;top:58%;z-index:5;width:calc(var(--ew) * .16);height:calc(var(--ew) * .16);transform:translate(-50%,-50%);border-radius:50%;background:#ff6b7a;box-shadow:0 3px 0 #d84a5c,0 8px 14px rgba(0,0,0,.18);display:flex;align-items:center;justify-content:center;transition:transform .3s ease,opacity .3s ease}
.e-seal svg{width:50%;height:50%}
#env.open .e-seal{transform:translate(-50%,-50%) scale(0);opacity:0}

#letter{z-index:8;overflow-y:auto;-webkit-overflow-scrolling:touch;padding:6vh 4vw 0;padding-top:calc(env(safe-area-inset-top,0px) + 6vh);background:rgba(24,48,120,.3);opacity:0;transition:opacity .6s ease}
#letter::after{content:'';display:block;height:calc(env(safe-area-inset-bottom,0px) + 8vh)}
#letter.on{opacity:1}
.paper{max-width:580px;margin:0 auto;background:#fffdf7;border-radius:22px;padding:30px 22px 36px;box-shadow:0 26px 60px rgba(20,40,110,.4);color:#26314f;font-family:'Neucha','Nunito',cursive;font-size:clamp(19px,5.2vw,23px);line-height:1.5;transform:translateY(60px) scale(.94);transition:transform .8s cubic-bezier(.3,1.3,.5,1);-webkit-user-select:text;user-select:text}
#letter.on .paper{transform:none}
.paper p{margin-bottom:.9em;opacity:0;transform:translateY(12px);animation:pin .7s ease forwards}
.paper p:last-child{margin-bottom:0}
@keyframes pin{to{opacity:1;transform:none}}
</style>
</head>
<body>
<div id="sky" class="full"></div>

<main id="stage" class="full">
  <div id="pots"></div>
  <div id="cta"><span>потапай картошку</span></div>
</main>

<div id="memes" class="full"></div>

<div id="env" hidden>
  <div class="e-back"></div>
  <div class="e-paper"></div>
  <div class="e-front"><svg viewBox="0 0 100 66" preserveAspectRatio="none"><path d="M0 4L50 38L100 4V66H0Z" fill="#fff"/><path d="M0 66L50 38L100 66" fill="none" stroke="#d3e0fb" stroke-width="1.5" vector-effect="non-scaling-stroke"/></svg></div>
  <div class="e-flap"><svg viewBox="0 0 100 38" preserveAspectRatio="none"><path d="M0 0H100L50 38Z" fill="#f2f6ff" stroke="#d3e0fb" stroke-width="1.5" vector-effect="non-scaling-stroke"/></svg></div>
  <div class="e-seal"><svg viewBox="0 0 24 24"><path d="M12 21C5 16 2 12.5 2 8.5C2 5.5 4.3 3.5 7 3.5C9 3.5 10.8 4.7 12 6.5C13.2 4.7 15 3.5 17 3.5C19.7 3.5 22 5.5 22 8.5C22 12.5 19 16 12 21Z" fill="#fff"/></svg></div>
</div>

<div id="letter" class="full" hidden><div class="paper" id="paper"></div></div>

<script>
/* ===== НАСТРОЙКИ ===== */
const CONFIG = {
  taps: 15,                  // сколько тапов до письма
  potatoFolder: 'potatoes',  // папка с картошками
  memeFolder: 'memes',       // папка с мемами
  // запасной вариант (если папок нет): файлы в корне с такими именами
  potatoes: ['potato1.png', 'potato2.png', 'potato3.png'],
  memes: Array.from({ length: 15 }, (_, i) => 'meme' + (i + 1) + '.jpg'),
};

const LETTER = `потато! я поздравляю вас с вашим днем рождения!! 
я не знаю какими материальными подарками вас можно удивить, но я бы просто хотела в этот день вас немножко порадовать и сказать какой вы крутой. а вы ряльна супер крутой, потата, эта чистая правда! никогда не сомневайтесь в своей крутости, не сомневайтесь в своих способностях и возможностях, продолжайте следовать своей цели и не тильтуйте!!!!!!!! 
я хочу вам искренне пожелать, чтобы вы были счастливы. пусть вас окружают люди, которые будут всегда за вас и с вами, которые будут по-настоящему вас ценить и приносить вам столько же добра и радости, сколько вы даете окружающим
хочу вам также пожелать здоровья, потато. вы зря не слушаити моих коллов конечно, но здоровье это самое ценное что у нас есть, что нельзя будет купить ни за какие деньги в будущем. никакие усилия и работа не стоят вашего здоровья и эта факт. берегите себя и своих близких! 
ну и ,конечно, хочу вам пожелать удачи. я считаю, что  20% любого успеха это удача. с усердной работой и трудом она обязательно придёт. так вот пусть она сопутствует вам на всем жизненном пути, и не только в работе. желаю вам оказаться в нужном месте и в нужное время, потато! пусть все ваши цели осуществятся, желания исполнятся, мечты сбудяца и вы наконец поедете отдыхать, путешествовать, ловить солнышко, любоваться горами и наслаждаться жизнью! 
а вообще потата мой колл вам: не ждите момента чтобы быть счастливым. живити сейчас, кайфуйте от вашей жизни и берите из нее максимум. стакан наполовину полон, понимаити??жизнь слишком коротка чтобы тильтовать. я верю что все у вас получится, потата. все сложится так, как надо, поверьте. доверьтесь процессу 
карочи с днем варенья вас!!! растите большой картофелиной, не будьте пюрешкой🥔🥔🥔🥔🥔🥔🍓🍓🍓🍓🍓`;
/* ===================== */

const $ = s => document.querySelector(s);
const rnd = (a, b) => a + Math.random() * (b - a);
const later = (ms, v) => new Promise(r => setTimeout(() => r(v), ms));
const IMG_RE = /\.(png|jpe?g|gif|webp|avif|heic|heif)$/i;

/* облака */
const CLOUD = '<svg viewBox="0 -8 120 58" preserveAspectRatio="none"><path d="M25 48a17 17 0 0 1 0-34a22 22 0 0 1 40-8a18 18 0 0 1 30 10a16 16 0 0 1 0 32Z" fill="#fff"/></svg>';
[[6, 190, .9, 85, -20], [22, 120, .55, 62, -48], [40, 150, .45, 100, -75], [63, 110, .5, 72, -10], [80, 170, .65, 90, -58]].forEach(([top, w, o, t, d]) => {
  const c = document.createElement('div');
  c.className = 'cloud';
  c.style.cssText = 'top:' + top + '%;width:' + w + 'px;height:' + Math.round(w * .48) + 'px;opacity:' + o + ';animation-duration:' + t + 's;animation-delay:' + d + 's';
  c.innerHTML = CLOUD;
  $('#sky').appendChild(c);
});

/* картинки из папок репозитория (названия любые) */
async function listFolder(folder) {
  const host = location.hostname;
  if (!/\.github\.io$/i.test(host)) return null;
  const owner = host.split('.')[0];
  const seg = location.pathname.split('/').filter(Boolean)[0];
  const repo = seg && seg.indexOf('.') < 0 ? seg : host;
  try {
    const r = await Promise.race([fetch('https://api.github.com/repos/' + owner + '/' + repo + '/contents/' + folder), later(6000, null)]);
    if (!r || !r.ok) return null;
    const list = await r.json();
    if (!Array.isArray(list)) return null;
    return list
      .filter(f => f.type === 'file' && IMG_RE.test(f.name))
      .sort((a, b) => a.name.localeCompare(b.name, undefined, { numeric: true }))
      .map(f => [folder + '/' + encodeURIComponent(f.name), f.download_url]);
  } catch (e) { return null; }
}
function loadImg(srcs) {
  return new Promise(res => {
    const list = srcs.filter(Boolean);
    let i = 0, done = false;
    const end = v => { if (!done) { done = true; res(v); } };
    setTimeout(() => end(null), 12000);
    const next = () => {
      if (i >= list.length) return end(null);
      const src = list[i++], im = new Image();
      im.onload = () => (im.naturalWidth ? end({ src, im, w: im.naturalWidth, h: im.naturalHeight }) : next());
      im.onerror = next;
      im.src = src;
    };
    next();
  });
}

/* запасная картошка, пока нет своих картинок */
const FALLBACK = `<svg class="fb" viewBox="0 0 200 240" xmlns="http://www.w3.org/2000/svg">
<ellipse cx="74" cy="224" rx="18" ry="9" fill="#9a5b26"/><ellipse cx="126" cy="224" rx="18" ry="9" fill="#9a5b26"/>
<path d="M104 46C104 32 108 24 116 16" fill="none" stroke="#3f8f42" stroke-width="5" stroke-linecap="round"/>
<path d="M114 18C124 4 142 6 146 14C136 24 122 24 114 18Z" fill="#7ccf6b" stroke="#3f8f42" stroke-width="3" stroke-linejoin="round"/>
<path d="M110 26C100 14 84 16 82 24C90 32 102 32 110 26Z" fill="#7ccf6b" stroke="#3f8f42" stroke-width="3" stroke-linejoin="round"/>
<path d="M100 40C146 36 176 70 178 116C180 160 166 204 124 216C94 225 56 214 38 182C20 150 22 98 42 70C58 50 78 42 100 40Z" fill="#eab664" stroke="#a5652a" stroke-width="5" stroke-linejoin="round"/>
<path d="M58 84C68 66 86 58 102 57" fill="none" stroke="#fbe2ad" stroke-width="9" stroke-linecap="round"/>
<g fill="#b9783b" opacity=".45"><ellipse cx="148" cy="88" rx="5" ry="3.5"/><ellipse cx="54" cy="156" rx="4.5" ry="3"/><ellipse cx="152" cy="172" rx="5.5" ry="4"/><ellipse cx="98" cy="198" rx="4" ry="2.8"/><ellipse cx="128" cy="62" rx="3" ry="2.2"/></g>
<g fill="#fff" stroke="#5a3415" stroke-width="3"><circle cx="78" cy="118" r="16"/><circle cx="124" cy="118" r="16"/></g>
<circle cx="81" cy="114" r="8" fill="#2a1a0c"/><circle cx="127" cy="114" r="8" fill="#2a1a0c"/>
<circle cx="84" cy="111" r="3" fill="#fff"/><circle cx="130" cy="111" r="3" fill="#fff"/>
<ellipse cx="60" cy="146" rx="11" ry="7" fill="#ff8f8f" opacity=".55"/><ellipse cx="142" cy="146" rx="11" ry="7" fill="#ff8f8f" opacity=".55"/>
<path d="M86 146Q101 168 116 146Z" fill="#7a2a1e" stroke="#5a3415" stroke-width="3" stroke-linejoin="round"/>
<ellipse cx="101" cy="153" rx="5.5" ry="3" fill="#ff8b9c"/>
</svg>`;

/* картошки */
function sizes(n) {
  if (n <= 1) return ['min(76vw,420px)', '50vh'];
  if (n === 2) return ['min(43vw,300px)', '38vh'];
  if (n <= 4) return ['min(43vw,280px)', '26vh'];
  return ['min(29vw,200px)', '19vh'];
}
const EV = window.PointerEvent ? 'pointerdown' : 'touchstart';
function buildPots(list) {
  const box = $('#pots'), sz = sizes(list.length);
  box.style.setProperty('--mw', sz[0]);
  box.style.setProperty('--mh', sz[1]);
  box.style.setProperty('--fw', 'min(58vw,280px,40vh)');
  (list.length ? list : [null]).forEach(item => {
    const slot = document.createElement('div'), pot = document.createElement('div'), inn = document.createElement('div');
    slot.className = 'slot'; pot.className = 'pot'; inn.className = 'pot-in';
    slot.style.setProperty('--d', (-rnd(0, 3.4)).toFixed(2) + 's');
    if (item) { item.im.alt = ''; item.im.draggable = false; inn.appendChild(item.im); }
    else inn.innerHTML = FALLBACK;
    pot.appendChild(inn); slot.appendChild(pot); box.appendChild(slot);
    pot.addEventListener(EV, e => { e.preventDefault(); tap(inn); }, { passive: false });
  });
  requestAnimationFrame(() => requestAnimationFrame(() => box.classList.add('ready')));
}

/* тапы и мемы */
let taps = 0, state = 'play', bag = [], lastMeme = null;
const memes = [], live = [];
function tap(inn) {
  if (state !== 'play') return;
  inn.style.setProperty('--tilt', ((Math.random() < .5 ? -1 : 1) * rnd(5, 10)).toFixed(1) + 'deg');
  inn.classList.remove('hop'); void inn.offsetWidth; inn.classList.add('hop');
  showMeme();
  if (++taps >= CONFIG.taps) finish();
}
function nextMeme() {
  if (!memes.length) return null;
  if (!bag.length) {
    bag = memes.slice();
    for (let i = bag.length - 1; i > 0; i--) { const j = Math.random() * (i + 1) | 0; const t = bag[i]; bag[i] = bag[j]; bag[j] = t; }
    if (bag.length > 1 && bag[bag.length - 1] === lastMeme) bag.unshift(bag.pop());
  }
  return (lastMeme = bag.pop());
}
function showMeme() {
  const m = nextMeme(); if (!m) return;
  while (live.length >= 4) live.shift().remove();
  const W = innerWidth, H = innerHeight;
  const k = Math.min(1, Math.min(W * .62, 340) / m.w, (H * .36) / m.h);
  const w = Math.round(m.w * k), h = Math.round(m.h * k), bw = w + 10, bh = h + 10;
  const el = document.createElement('div'), im = new Image();
  el.className = 'meme';
  im.src = m.src; im.alt = ''; im.draggable = false;
  im.style.width = w + 'px'; im.style.height = h + 'px';
  el.appendChild(im);
  const x0 = bw / 2 + 10, x1 = Math.max(x0, W - bw / 2 - 10);
  const y0 = bh / 2 + 50, y1 = Math.max(y0, H * .74 - bh / 2);
  el.style.left = rnd(x0, x1) + 'px';
  el.style.top = rnd(y0, y1) + 'px';
  el.style.setProperty('--r', rnd(-12, 12).toFixed(1) + 'deg');
  $('#memes').appendChild(el); live.push(el);
  setTimeout(() => el.classList.add('bye'), 1500);
  setTimeout(() => { el.remove(); const i = live.indexOf(el); if (i > -1) live.splice(i, 1); }, 1900);
}

/* письмо */
function finish() {
  state = 'end';
  setTimeout(() => {
    $('#stage').classList.add('out');
    live.forEach(el => el.classList.add('bye'));
    const env = $('#env');
    env.hidden = false; void env.offsetWidth; env.classList.add('in');
    setTimeout(() => env.classList.add('open'), 1000);
    setTimeout(() => env.classList.add('peek'), 1650);
    setTimeout(openLetter, 2700);
  }, 900);
}
function openLetter() {
  const env = $('#env'), L = $('#letter'), paper = $('#paper');
  paper.innerHTML = '';
  LETTER.split('\n').map(s => s.trim()).filter(Boolean).forEach((t, i) => {
    const p = document.createElement('p');
    p.textContent = t;
    p.style.animationDelay = (0.5 + i * 0.3).toFixed(2) + 's';
    paper.appendChild(p);
  });
  env.classList.add('gone');
  L.hidden = false; L.scrollTop = 0; void L.offsetWidth; L.classList.add('on');
  setTimeout(() => { env.hidden = true; }, 700);
}

/* старт */
(async () => {
  const lists = await Promise.all([listFolder(CONFIG.potatoFolder), listFolder(CONFIG.memeFolder)]);
  const potC = lists[0] && lists[0].length ? lists[0] : CONFIG.potatoes.map(s => [s]);
  const memeC = lists[1] && lists[1].length ? lists[1] : CONFIG.memes.map(s => [s]);
  const pots = (await Promise.all(potC.map(loadImg))).filter(Boolean);
  buildPots(pots);
  memeC.forEach(c => loadImg(c).then(m => { if (m) memes.push(m); }));
})();
</script>
</body>
</html>
