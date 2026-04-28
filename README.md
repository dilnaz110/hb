<!DOCTYPE html>

<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>С Днём Рождения, Папа! ❤️</title>

<style>

  :root {
    -forest: #1a3a2a;
    -moss: #2d5a3d;
    -sage: #4a7c59;
    -fern: #6fa876;
    -mint: #a8d5b5;
    -cream: #f5f0e8;
    -warm: #ede4d3;
    -bark: #6b4c2a;
    -wood: #8b6340;
    -honey: #c49a4a;
    -light-wood: #d4b896;
  }

* { margin: 0; padding: 0; box-sizing: border-box; }

 html { scroll-behavior: smooth; }

 body {
 font-family: ‘Nunito’, sans-serif;
 background: var(–cream);
 color: var(–forest);
 overflow-x: hidden;
}

/* ── HERO ── */
#hero {
 min-height: 100vh;
 display: flex;
 flex-direction: column;
 align-items: center;
 justify-content: center;
 position: relative;
 overflow: hidden;
 background: linear-gradient(160deg, var(–forest) 0%, var(–moss) 40%, var(–sage) 75%, var(–fern) 100%);
}

.hero-leaves {
 position: absolute; inset: 0;
 pointer-events: none;
 overflow: hidden;
}

.leaf {
 position: absolute;
 opacity: 0.12;
 animation: leafDrift linear infinite;
}

.leaf svg { fill: var(–mint); }

@keyframes leafDrift {
 0%   { transform: translateY(-120px) rotate(0deg); opacity: 0; }
 10%  { opacity: 0.12; }
 90%  { opacity: 0.12; }
 100% { transform: translateY(110vh) rotate(360deg); opacity: 0; }
}

.hero-content {
 text-align: center;
 z-index: 1;
 padding: 2rem;
 opacity: 0;
 transform: translateY(30px);
 animation: fadeUp 1.2s ease forwards 0.4s;
}

@keyframes fadeUp {
 to { opacity: 1; transform: translateY(0); }
}

.hero-badge {
 display: inline-block;
 background: rgba(255,255,255,0.12);
 border: 1px solid rgba(255,255,255,0.3);
 color: var(–mint);
 font-family: ‘Nunito’, sans-serif;
 font-weight: 300;
 letter-spacing: 0.25em;
 text-transform: uppercase;
 font-size: 0.75rem;
 padding: 0.45rem 1.4rem;
 border-radius: 50px;
 margin-bottom: 2rem;
 opacity: 0;
 animation: fadeUp 1s ease forwards 0.9s;
}

.hero-title {
font-family: ‘Cormorant Garamond’, serif;
font-size: clamp(3rem, 8vw, 6.5rem);
font-weight: 300;
color: #fff;
line-height: 1.1;
letter-spacing: -0.01em;
margin-bottom: 1.2rem;
opacity: 0;
animation: fadeUp 1.2s ease forwards 0.6s;
}

.hero-title .heart {
color: #e88080;
display: inline-block;
animation: heartbeat 1.8s ease-in-out infinite 2s;
}

@keyframes heartbeat {
0%, 100% { transform: scale(1); }
50% { transform: scale(1.2); }
}

.hero-sub {
font-family: ‘Cormorant Garamond’, serif;
font-style: italic;
font-size: clamp(1.1rem, 2.5vw, 1.6rem);
color: rgba(255,255,255,0.75);
letter-spacing: 0.03em;
opacity: 0;
animation: fadeUp 1.2s ease forwards 1.1s;
}

.hero-scroll {
position: absolute;
bottom: 2.5rem;
left: 50%;
transform: translateX(-50%);
display: flex;
flex-direction: column;
align-items: center;
gap: 0.5rem;
color: rgba(255,255,255,0.4);
font-size: 0.7rem;
letter-spacing: 0.2em;
text-transform: uppercase;
animation: fadeUp 1s ease forwards 2s, bobble 2s ease-in-out infinite 3s;
opacity: 0;
}

.hero-scroll .arrow { font-size: 1.2rem; }

@keyframes bobble {
0%, 100% { transform: translateX(-50%) translateY(0); }
50% { transform: translateX(-50%) translateY(6px); }
}

/* ── SECTIONS COMMON ── */
section { padding: 6rem 1.5rem; }

.section-label {
display: inline-block;
font-size: 0.7rem;
letter-spacing: 0.3em;
text-transform: uppercase;
color: var(–sage);
font-weight: 600;
margin-bottom: 1rem;
}

.section-title {
font-family: ‘Cormorant Garamond’, serif;
font-size: clamp(2rem, 5vw, 3.5rem);
font-weight: 400;
color: var(–forest);
line-height: 1.2;
margin-bottom: 1rem;
}

.section-divider {
width: 60px;
height: 2px;
background: linear-gradient(to right, var(–sage), var(–honey));
margin: 1.5rem auto;
border-radius: 2px;
}

.container {
max-width: 1100px;
margin: 0 auto;
}

.text-center { text-align: center; }

/* ── REVEAL ANIMATION ── */
.reveal {
opacity: 0;
transform: translateY(28px);
transition: opacity 0.8s ease, transform 0.8s ease;
}
.reveal.visible {
opacity: 1;
transform: translateY(0);
}

/* ── CALENDAR ── */
#calendar-section {
background: var(–warm);
}

.calendar-wrap {
background: #fff;
border-radius: 20px;
padding: 2rem;
box-shadow: 0 8px 40px rgba(45,90,61,0.1);
max-width: 420px;
margin: 0 auto;
}

.cal-header {
display: flex;
justify-content: space-between;
align-items: center;
margin-bottom: 1.5rem;
}

.cal-month {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.5rem;
font-weight: 600;
color: var(–forest);
}

.cal-nav {
background: none;
border: none;
color: var(–sage);
font-size: 1.4rem;
cursor: pointer;
padding: 0.3rem 0.6rem;
border-radius: 8px;
transition: background 0.2s;
}
.cal-nav:hover { background: var(–warm); }

.cal-grid {
display: grid;
grid-template-columns: repeat(7, 1fr);
gap: 4px;
}

.cal-day-name {
text-align: center;
font-size: 0.7rem;
font-weight: 600;
letter-spacing: 0.1em;
color: var(–wood);
text-transform: uppercase;
padding: 0.4rem 0;
}

.cal-day {
text-align: center;
padding: 0.55rem 0;
border-radius: 10px;
font-size: 0.9rem;
cursor: default;
color: var(–forest);
transition: background 0.2s, transform 0.2s;
position: relative;
}

.cal-day.empty { color: transparent; pointer-events: none; }

.cal-day.birthday {
background: linear-gradient(135deg, var(–moss), var(–sage));
color: #fff;
font-weight: 700;
cursor: pointer;
box-shadow: 0 4px 14px rgba(45,90,61,0.35);
animation: pulse 2.5s ease-in-out infinite;
}

@keyframes pulse {
0%, 100% { box-shadow: 0 4px 14px rgba(45,90,61,0.35); }
50% { box-shadow: 0 4px 24px rgba(45,90,61,0.6); }
}

.cal-day.birthday:hover {
transform: scale(1.15);
}

.cal-tooltip {
display: none;
position: fixed;
left: 50%;
top: 50%;
transform: translate(-50%, -50%) scale(0.9);
background: var(–forest);
color: #fff;
padding: 1.5rem 2rem;
border-radius: 16px;
font-family: ‘Cormorant Garamond’, serif;
font-style: italic;
font-size: 1.15rem;
text-align: center;
max-width: 320px;
z-index: 1000;
box-shadow: 0 20px 60px rgba(0,0,0,0.3);
transition: transform 0.3s ease, opacity 0.3s ease;
opacity: 0;
}

.cal-tooltip.show {
display: block;
transform: translate(-50%, -50%) scale(1);
opacity: 1;
animation: popIn 0.3s ease forwards;
}

@keyframes popIn {
from { transform: translate(-50%, -50%) scale(0.85); opacity: 0; }
to   { transform: translate(-50%, -50%) scale(1); opacity: 1; }
}

.cal-tooltip-close {
display: block;
margin: 1rem auto 0;
background: rgba(255,255,255,0.15);
border: 1px solid rgba(255,255,255,0.3);
color: #fff;
padding: 0.4rem 1.2rem;
border-radius: 50px;
cursor: pointer;
font-family: ‘Nunito’, sans-serif;
font-size: 0.8rem;
transition: background 0.2s;
}

.cal-tooltip-close:hover { background: rgba(255,255,255,0.25); }

.cal-overlay {
display: none;
position: fixed; inset: 0;
background: rgba(0,0,0,0.4);
z-index: 999;
backdrop-filter: blur(3px);
}
.cal-overlay.show { display: block; }

/* ── GALLERY ── */
#gallery {
background: var(–cream);
}

.gallery-grid {
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 1.2rem;
margin-top: 3rem;
}

@media (max-width: 700px) {
.gallery-grid { grid-template-columns: repeat(2, 1fr); }
}

.gallery-item {
position: relative;
border-radius: 16px;
overflow: hidden;
aspect-ratio: 4/3;
cursor: pointer;
box-shadow: 0 4px 20px rgba(45,90,61,0.12);
transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.gallery-item:nth-child(2) { grid-row: span 2; aspect-ratio: auto; }

.gallery-item:hover {
transform: translateY(-4px);
box-shadow: 0 12px 40px rgba(45,90,61,0.22);
}

.gallery-item img {
width: 100%;
height: 100%;
object-fit: cover;
display: block;
transition: transform 0.5s ease;
}

.gallery-item:hover img { transform: scale(1.06); }

.gallery-caption {
position: absolute;
inset: 0;
background: linear-gradient(to top, rgba(26,58,42,0.85) 0%, transparent 55%);
display: flex;
align-items: flex-end;
padding: 1.2rem;
opacity: 0;
transition: opacity 0.3s ease;
}

.gallery-item:hover .gallery-caption { opacity: 1; }

.gallery-caption span {
font-family: ‘Cormorant Garamond’, serif;
font-style: italic;
color: #fff;
font-size: 1rem;
line-height: 1.3;
}

/* SVG placeholder photos */
.photo-placeholder {
width: 100%;
height: 100%;
object-fit: cover;
}

/* ── CARDS ── */
#wishes {
background: linear-gradient(170deg, var(–forest) 0%, var(–moss) 100%);
position: relative;
overflow: hidden;
}

#wishes::before {
content: ‘’;
position: absolute;
top: -50%;
right: -20%;
width: 600px; height: 600px;
border-radius: 50%;
background: radial-gradient(circle, rgba(168,213,181,0.07) 0%, transparent 70%);
pointer-events: none;
}

#wishes .section-title { color: #fff; }
#wishes .section-label { color: var(–mint); }

.cards-grid {
display: grid;
grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
gap: 1.5rem;
margin-top: 3rem;
}

.flip-card {
perspective: 1000px;
height: 220px;
cursor: pointer;
}

.flip-card-inner {
position: relative;
width: 100%; height: 100%;
transform-style: preserve-3d;
transition: transform 0.7s cubic-bezier(0.4, 0, 0.2, 1);
}

.flip-card:hover .flip-card-inner,
.flip-card.flipped .flip-card-inner {
transform: rotateY(180deg);
}

.flip-front, .flip-back {
position: absolute; inset: 0;
border-radius: 18px;
backface-visibility: hidden;
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
padding: 1.8rem;
text-align: center;
}

.flip-front {
background: rgba(255,255,255,0.08);
border: 1px solid rgba(255,255,255,0.15);
backdrop-filter: blur(10px);
}

.flip-front .card-name {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.5rem;
font-weight: 600;
color: #fff;
margin-bottom: 0.4rem;
}

.flip-front .card-emoji {
font-size: 2.5rem;
margin-bottom: 0.8rem;
}

.flip-front .card-hint {
font-size: 0.7rem;
color: rgba(255,255,255,0.4);
letter-spacing: 0.15em;
text-transform: uppercase;
}

.flip-back {
background: linear-gradient(135deg, var(–honey), var(–bark));
transform: rotateY(180deg);
}

.flip-back .card-text {
font-family: ‘Cormorant Garamond’, serif;
font-style: italic;
font-size: 1.05rem;
color: #fff;
line-height: 1.6;
}

.flip-back .card-from {
margin-top: 1rem;
font-family: ‘Nunito’, sans-serif;
font-size: 0.75rem;
color: rgba(255,255,255,0.7);
letter-spacing: 0.1em;
}

/* ── PLAYLIST ── */
#playlist {
background: var(–warm);
}

.playlist-list {
max-width: 640px;
margin: 3rem auto 0;
display: flex;
flex-direction: column;
gap: 0.8rem;
}

.track {
display: flex;
align-items: center;
gap: 1.2rem;
background: #fff;
border-radius: 14px;
padding: 1rem 1.4rem;
box-shadow: 0 2px 12px rgba(45,90,61,0.07);
transition: transform 0.25s ease, box-shadow 0.25s ease;
cursor: pointer;
text-decoration: none;
color: inherit;
}

.track:hover {
transform: translateX(6px);
box-shadow: 0 6px 24px rgba(45,90,61,0.14);
}

.track-num {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.4rem;
font-weight: 300;
color: var(–mint);
min-width: 28px;
text-align: center;
}

.track-icon {
width: 42px; height: 42px;
border-radius: 10px;
background: linear-gradient(135deg, var(–moss), var(–fern));
display: flex;
align-items: center;
justify-content: center;
color: #fff;
font-size: 1.1rem;
flex-shrink: 0;
transition: transform 0.2s;
}

.track:hover .track-icon { transform: scale(1.1); }

.track-info { flex: 1; }

.track-title {
font-weight: 600;
font-size: 0.95rem;
color: var(–forest);
margin-bottom: 0.15rem;
}

.track-artist {
font-size: 0.8rem;
color: var(–wood);
}

.track-arrow {
color: var(–sage);
font-size: 1rem;
opacity: 0.6;
}

/* ── FINAL ── */
#final {
min-height: 60vh;
display: flex;
align-items: center;
justify-content: center;
background: linear-gradient(160deg, var(–forest), var(–moss) 60%, var(–sage));
position: relative;
overflow: hidden;
text-align: center;
}

#final::before {
content: ‘’;
position: absolute; inset: 0;
background: radial-gradient(ellipse at 50% 100%, rgba(168,213,181,0.15) 0%, transparent 65%);
}

.final-content {
z-index: 1;
padding: 3rem 2rem;
}

.final-title {
font-family: ‘Cormorant Garamond’, serif;
font-size: clamp(2.2rem, 6vw, 4.5rem);
font-weight: 300;
color: #fff;
line-height: 1.2;
margin-bottom: 1rem;
opacity: 0;
transform: translateY(24px);
transition: opacity 0.9s ease, transform 0.9s ease;
}

.final-title.visible { opacity: 1; transform: translateY(0); }

.final-heart {
font-size: 2rem;
animation: heartbeat 2s ease-in-out infinite;
display: inline-block;
margin: 0 0.4rem;
}

.final-from {
font-family: ‘Nunito’, sans-serif;
font-size: 0.85rem;
color: rgba(255,255,255,0.5);
letter-spacing: 0.25em;
text-transform: uppercase;
margin-top: 1.5rem;
opacity: 0;
transition: opacity 0.9s ease 0.5s;
}

.final-from.visible { opacity: 1; }

.final-ornament {
display: flex;
align-items: center;
justify-content: center;
gap: 1rem;
margin-top: 2.5rem;
opacity: 0;
transition: opacity 0.9s ease 0.8s;
}

.final-ornament.visible { opacity: 1; }

.ornament-line {
width: 60px; height: 1px;
background: rgba(255,255,255,0.25);
}

.ornament-leaf { color: var(–mint); font-size: 1.2rem; }

/* Nav dots */
.nav-dots {
position: fixed;
right: 1.5rem;
top: 50%;
transform: translateY(-50%);
display: flex;
flex-direction: column;
gap: 0.6rem;
z-index: 500;
}

.nav-dot {
width: 8px; height: 8px;
border-radius: 50%;
background: rgba(255,255,255,0.4);
border: 1px solid rgba(255,255,255,0.6);
cursor: pointer;
transition: background 0.3s, transform 0.3s;
}

.nav-dot.active {
background: #fff;
transform: scale(1.4);
}

.nav-dot.dark {
background: rgba(45,90,61,0.3);
border-color: rgba(45,90,61,0.5);
}

.nav-dot.dark.active { background: var(–moss); }
</style>

</head>
<body>

<!-- Navigation dots -->

<nav class="nav-dots" id="navDots">
  <div class="nav-dot active" data-target="hero"></div>
  <div class="nav-dot dark" data-target="calendar-section"></div>
  <div class="nav-dot dark" data-target="gallery"></div>
  <div class="nav-dot" data-target="wishes"></div>
  <div class="nav-dot dark" data-target="playlist"></div>
  <div class="nav-dot" data-target="final"></div>
</nav>

<!-- ── HERO ── -->

<section id="hero">
  <div class="hero-leaves" id="heroLeaves"></div>
  <div class="hero-content">
    <div class="hero-badge">9 мая · особенный день</div>
    <h1 class="hero-title">С Днём Рождения,<br>Папа! <span class="heart">❤️</span></h1>
    <p class="hero-sub">Спасибо за всё, что ты для нас делаешь</p>
  </div>
  <div class="hero-scroll">
    <span>листать</span>
    <span class="arrow">↓</span>
  </div>
</section>

<!-- ── CALENDAR ── -->

<section id="calendar-section">
  <div class="container">
    <div class="text-center reveal">
      <span class="section-label">Особая дата</span>
      <h2 class="section-title">9 мая — твой день</h2>
      <div class="section-divider"></div>
    </div>
    <div class="reveal" style="transition-delay:0.2s">
      <div class="calendar-wrap">
        <div class="cal-header">
          <button class="cal-nav" id="prevMonth">‹</button>
          <span class="cal-month" id="calTitle"></span>
          <button class="cal-nav" id="nextMonth">›</button>
        </div>
        <div class="cal-grid" id="calGrid"></div>
      </div>
    </div>
  </div>
</section>

<!-- Tooltip overlay -->

<div class="cal-overlay" id="calOverlay"></div>
<div class="cal-tooltip" id="calTooltip">
  🌿 Самый важный день — день, когда родился наш папа
  <button class="cal-tooltip-close" id="calClose">Закрыть</button>
</div>

<section id="gallery">
  <div class="container">
    <div class="text-center reveal">
      <span class="section-label">Воспоминания</span>
      <h2 class="section-title">Семейная галерея</h2>
      <div class="section-divider"></div>
    </div>

    <div class="gallery-grid reveal" style="transition-delay:0.2s">

      <div class="gallery-item">
        <img src="family1.jpg" alt="Наша семья" class="gallery-photo">
        <div class="gallery-caption"><span>Наши лучшие моменты</span></div>
      </div>

      <div class="gallery-item">
        <img src="family2.jpg" alt="Гордость нашей семьи" class="gallery-photo">
        <div class="gallery-caption"><span>Гордость нашей семьи ❤️</span></div>
      </div>

      <div class="gallery-item">
        <img src="family3.jpg" alt="Папин дом" class="gallery-photo">
        <div class="gallery-caption"><span>Там, где живёт уют</span></div>
      </div>

      <div class="gallery-item">
        <img src="family4.jpg" alt="Вместе навсегда" class="gallery-photo">
        <div class="gallery-caption"><span>Вместе навсегда</span></div>
      </div>

      <div class="gallery-item">
        <img src="family5.jpg" alt="Счастье рядом" class="gallery-photo">
        <div class="gallery-caption"><span>Счастье — это рядом с тобой</span></div>
      </div>

    </div>
  </div>
</section>

<!-- ── WISHES ── -->

<section id="wishes">
  <div class="container">
    <div class="text-center reveal">
      <span class="section-label">От всей семьи</span>
      <h2 class="section-title">Поздравления</h2>
      <div class="section-divider"></div>
      <p style="color:rgba(255,255,255,0.5);font-size:0.8rem;margin-top:-0.5rem;">Наведи на карточку, чтобы прочитать</p>
    </div>
    <div class="cards-grid reveal" style="transition-delay:0.2s">

```
  <div class="flip-card">
    <div class="flip-card-inner">
      <div class="flip-front">
        <div class="card-emoji">🌻</div>
        <div class="card-name">Мама</div>
        <div class="card-hint">нажми на карточку</div>
      </div>
      <div class="flip-back">
        <p class="card-text">«Ты — опора нашей семьи, наш тихий герой. С каждым годом я люблю тебя всё сильнее.»</p>
        <span class="card-from">— С любовью, твоя жена</span>
      </div>
    </div>
  </div>

  <div class="flip-card">
    <div class="flip-card-inner">
      <div class="flip-front">
        <div class="card-emoji">🍀</div>
        <div class="card-name">Сын</div>
        <div class="card-hint">нажми на карточку</div>
      </div>
      <div class="flip-back">
        <p class="card-text">«Пап, ты научил меня быть сильным и добрым. Хочу быть таким же, как ты.»</p>
        <span class="card-from">— Твой сын</span>
      </div>
    </div>
  </div>

  <div class="flip-card">
    <div class="flip-card-inner">
      <div class="flip-front">
        <div class="card-emoji">🌸</div>
        <div class="card-name">Дочка</div>
        <div class="card-hint">нажми на карточку</div>
      </div>
      <div class="flip-back">
        <p class="card-text">«Ты — мой первый и лучший герой. Спасибо за все обнимашки и за то, что всегда рядом.»</p>
        <span class="card-from">— Твоя дочка</span>
      </div>
    </div>
  </div>

  <div class="flip-card">
    <div class="flip-card-inner">
      <div class="flip-front">
        <div class="card-emoji">🌿</div>
        <div class="card-name">Вся семья</div>
        <div class="card-hint">нажми на карточку</div>
      </div>
      <div class="flip-back">
        <p class="card-text">«Желаем здоровья, тепла и бесконечно хороших дней. Мы так тебя любим!»</p>
        <span class="card-from">— Вся наша семья</span>
      </div>
    </div>
  </div>

</div>
```

  </div>
</section>

<!-- ── PLAYLIST ── -->

<section id="playlist">
  <div class="container">
    <div class="text-center reveal">
      <span class="section-label">Музыка</span>
      <h2 class="section-title">Плейлист для папы</h2>
      <div class="section-divider"></div>
    </div>
    <div class="playlist-list reveal" style="transition-delay:0.2s">

```
  <a class="track" href="https://music.yandex.ru/search?text=Юрий+Антонов+Крыша+дома+твоего" target="_blank" rel="noopener">
    <span class="track-num">01</span>
    <div class="track-icon">♪</div>
    <div class="track-info">
      <div class="track-title">Крыша дома твоего</div>
      <div class="track-artist">Юрий Антонов</div>
    </div>
    <span class="track-arrow">→</span>
  </a>

  <a class="track" href="https://music.yandex.ru/search?text=Михаил+Боярский+Папа" target="_blank" rel="noopener">
    <span class="track-num">02</span>
    <div class="track-icon">♪</div>
    <div class="track-info">
      <div class="track-title">Папа</div>
      <div class="track-artist">Михаил Боярский</div>
    </div>
    <span class="track-arrow">→</span>
  </a>

  <a class="track" href="https://music.yandex.ru/search?text=Игорь+Николаев+Папа" target="_blank" rel="noopener">
    <span class="track-num">03</span>
    <div class="track-icon">♪</div>
    <div class="track-info">
      <div class="track-title">Папа</div>
      <div class="track-artist">Игорь Николаев</div>
    </div>
    <span class="track-arrow">→</span>
  </a>

  <a class="track" href="https://music.yandex.ru/search?text=Алексей+Глызин+Папа" target="_blank" rel="noopener">
    <span class="track-num">04</span>
    <div class="track-icon">♪</div>
    <div class="track-info">
      <div class="track-title">Папа, слышишь?</div>
      <div class="track-artist">Алексей Глызин</div>
    </div>
    <span class="track-arrow">→</span>
  </a>

  <a class="track" href="https://music.yandex.ru/search?text=Дочь+папина+песня" target="_blank" rel="noopener">
    <span class="track-num">05</span>
    <div class="track-icon">♪</div>
    <div class="track-info">
      <div class="track-title">Папина дочка</div>
      <div class="track-artist">Анжелика Варум</div>
    </div>
    <span class="track-arrow">→</span>
  </a>

</div>
```

  </div>
</section>

<!-- ── FINAL ── -->

<section id="final">
  <div class="final-content">
    <h2 class="final-title reveal-final">
      Мы тебя очень любим<span class="final-heart">❤️</span>
    </h2>
    <p class="final-from reveal-final-sub">Твоя семья</p>
    <div class="final-ornament reveal-final-ornament">
      <div class="ornament-line"></div>
      <span class="ornament-leaf">🌿</span>
      <div class="ornament-line"></div>
    </div>
  </div>
</section>

<script>
// ── Falling leaves ──
(function() {
  const container = document.getElementById('heroLeaves');
  const leafPaths = [
    'M12,2 C14,6 18,8 18,12 C18,16 15,20 12,22 C9,20 6,16 6,12 C6,8 10,6 12,2Z',
    'M12,1 C16,5 20,9 18,14 C16,19 8,21 5,17 C2,13 4,6 8,3 C10,2 11,1 12,1Z',
    'M10,2 C14,3 19,8 18,13 C17,18 11,22 7,20 C3,18 1,12 3,7 C5,2 8,1 10,2Z'
  ];
  for (let i = 0; i < 12; i++) {
    const el = document.createElement('div');
    el.className = 'leaf';
    const size = 20 + Math.random() * 30;
    el.style.cssText = `left:${Math.random()*100}%;width:${size}px;height:${size}px;animation-duration:${8+Math.random()*10}s;animation-delay:${-Math.random()*15}s`;
    el.innerHTML = `<svg viewBox="0 0 24 24" width="${size}" height="${size}"><path d="${leafPaths[i%3]}"/></svg>`;
    container.appendChild(el);
  }
})();

// ── Calendar ──
(function() {
  let year = 2026, month = 4; // May 2025
  const months = ['Январь','Февраль','Март','Апрель','Май','Июнь','Июль','Август','Сентябрь','Октябрь','Ноябрь','Декабрь'];
  const days = ['Пн','Вт','Ср','Чт','Пт','Сб','Вс'];

  function render() {
    document.getElementById('calTitle').textContent = months[month] + ' ' + year;
    const grid = document.getElementById('calGrid');
    grid.innerHTML = '';
    days.forEach(d => {
      const el = document.createElement('div');
      el.className = 'cal-day-name';
      el.textContent = d;
      grid.appendChild(el);
    });
    const first = new Date(year, month, 1).getDay();
    const offset = first === 0 ? 6 : first - 1;
    for (let i = 0; i < offset; i++) {
      const el = document.createElement('div');
      el.className = 'cal-day empty'; el.textContent = '-';
      grid.appendChild(el);
    }
    const total = new Date(year, month+1, 0).getDate();
    for (let d = 1; d <= total; d++) {
      const el = document.createElement('div');
      el.className = 'cal-day' + (d === 9 && month === 4 ? ' birthday' : '');
      el.textContent = d;
      if (d === 9 && month === 4) {
        el.addEventListener('click', showTooltip);
      }
      grid.appendChild(el);
    }
  }

  function showTooltip() {
    document.getElementById('calOverlay').classList.add('show');
    document.getElementById('calTooltip').classList.add('show');
  }

  document.getElementById('calClose').addEventListener('click', () => {
    document.getElementById('calOverlay').classList.remove('show');
    document.getElementById('calTooltip').classList.remove('show');
  });
  document.getElementById('calOverlay').addEventListener('click', () => {
    document.getElementById('calOverlay').classList.remove('show');
    document.getElementById('calTooltip').classList.remove('show');
  });

  document.getElementById('prevMonth').addEventListener('click', () => {
    month--; if (month < 0) { month = 11; year--; } render();
  });
  document.getElementById('nextMonth').addEventListener('click', () => {
    month++; if (month > 11) { month = 0; year++; } render();
  });

  render();
})();

// ── Flip cards on mobile ──
document.querySelectorAll('.flip-card').forEach(card => {
  card.addEventListener('click', () => card.classList.toggle('flipped'));
});

// ── Scroll reveal ──
const revealEls = document.querySelectorAll('.reveal');
const io = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); io.unobserve(e.target); } });
}, { threshold: 0.15 });
revealEls.forEach(el => io.observe(el));

// Final block reveal
const finalTitle = document.querySelector('.reveal-final');
const finalSub = document.querySelector('.reveal-final-sub');
const finalOrn = document.querySelector('.reveal-final-ornament');
const ioFinal = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      finalTitle && finalTitle.classList.add('visible');
      finalSub && finalSub.classList.add('visible');
      finalOrn && finalOrn.classList.add('visible');
    }
  });
}, { threshold: 0.3 });
const finalSection = document.getElementById('final');
if (finalSection) ioFinal.observe(finalSection);

// ── Nav dots ──
const sections = ['hero','calendar-section','gallery','wishes','playlist','final'];
const dots = document.querySelectorAll('.nav-dot');

function updateDots() {
  const scrollY = window.scrollY + window.innerHeight / 2;
  sections.forEach((id, i) => {
    const el = document.getElementById(id);
    if (!el) return;
    const top = el.offsetTop, bot = top + el.offsetHeight;
    if (scrollY >= top && scrollY < bot) {
      dots.forEach(d => d.classList.remove('active'));
      dots[i].classList.add('active');
    }
  });
}

window.addEventListener('scroll', updateDots, { passive: true });

dots.forEach((dot, i) => {
  dot.addEventListener('click', () => {
    document.getElementById(sections[i])?.scrollIntoView({ behavior: 'smooth' });
  });
});
</script>

</body>
</html>
