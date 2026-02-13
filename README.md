<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>💌 For Madhu</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Dancing+Script:wght@500;700&family=Lato:wght@300;400&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --rose: #e8405a;
      --blush: #f9c4ce;
      --cream: #fff8f5;
      --gold: #d4a853;
      --dark: #2a1520;
      --petal: #fce4ec;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      background: var(--cream);
      font-family: 'Lato', sans-serif;
      color: var(--dark);
      min-height: 100vh;
      overflow-x: hidden;
    }

    /* Floating petals */
    .petal {
      position: fixed;
      top: -40px;
      font-size: 1.2rem;
      animation: fall linear infinite;
      pointer-events: none;
      z-index: 0;
      opacity: 0.6;
    }
    @keyframes fall {
      to { transform: translateY(110vh) rotate(720deg); opacity: 0; }
    }

    /* Screens */
    .screen {
      display: none;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      padding: 2rem;
      position: relative;
      z-index: 1;
      animation: fadeIn 0.8s ease;
    }
    .screen.active { display: flex; }
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* ===== INTRO SCREEN ===== */
    #screen-intro {
      background: radial-gradient(ellipse at 60% 40%, #fce4ec 0%, #fff8f5 70%);
      text-align: center;
    }
    .heart-big {
      font-size: 6rem;
      animation: heartbeat 1.4s ease-in-out infinite;
      display: block;
      margin-bottom: 1rem;
    }
    @keyframes heartbeat {
      0%,100% { transform: scale(1); }
      14% { transform: scale(1.15); }
      28% { transform: scale(1); }
      42% { transform: scale(1.1); }
      56% { transform: scale(1); }
    }
    .intro-title {
      font-family: 'Dancing Script', cursive;
      font-size: clamp(2.5rem, 8vw, 4.5rem);
      color: var(--rose);
      line-height: 1.2;
      margin-bottom: 0.5rem;
    }
    .intro-sub {
      font-family: 'Lato', sans-serif;
      font-size: 1rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: #b06070;
      margin-bottom: 2.5rem;
    }
    .btn-start {
      background: var(--rose);
      color: #fff;
      border: none;
      padding: 1rem 2.5rem;
      border-radius: 50px;
      font-family: 'Dancing Script', cursive;
      font-size: 1.4rem;
      cursor: pointer;
      box-shadow: 0 8px 30px rgba(232,64,90,0.35);
      transition: transform 0.2s, box-shadow 0.2s;
    }
    .btn-start:hover {
      transform: translateY(-3px) scale(1.04);
      box-shadow: 0 12px 40px rgba(232,64,90,0.5);
    }

    /* ===== QUESTION SCREENS ===== */
    .q-screen {
      background: var(--cream);
    }
    .progress-bar-wrap {
      width: min(380px, 90vw);
      background: var(--blush);
      border-radius: 20px;
      height: 8px;
      margin-bottom: 2.5rem;
      overflow: hidden;
    }
    .progress-bar {
      height: 100%;
      background: linear-gradient(90deg, var(--rose), #ff8fa3);
      border-radius: 20px;
      transition: width 0.5s ease;
    }
    .q-card {
      background: #fff;
      border-radius: 24px;
      padding: 2.5rem 2rem;
      width: min(420px, 92vw);
      box-shadow: 0 10px 50px rgba(232,64,90,0.12), 0 2px 10px rgba(0,0,0,0.05);
      border: 1.5px solid rgba(232,64,90,0.08);
      position: relative;
      overflow: hidden;
    }
    .q-card::before {
      content: '';
      position: absolute;
      top: -40px; right: -40px;
      width: 140px; height: 140px;
      background: radial-gradient(circle, rgba(232,64,90,0.07) 0%, transparent 70%);
      border-radius: 50%;
    }
    .q-emoji { font-size: 2.4rem; margin-bottom: 0.8rem; display: block; }
    .q-num {
      font-size: 0.7rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--rose);
      margin-bottom: 0.4rem;
      font-weight: 400;
    }
    .q-text {
      font-family: 'Playfair Display', serif;
      font-size: clamp(1.1rem, 4vw, 1.45rem);
      color: var(--dark);
      line-height: 1.55;
      margin-bottom: 2rem;
    }
    .q-options {
      display: flex;
      flex-direction: column;
      gap: 0.8rem;
    }
    .q-btn {
      background: var(--petal);
      color: var(--dark);
      border: 2px solid transparent;
      padding: 0.85rem 1.2rem;
      border-radius: 14px;
      font-family: 'Lato', sans-serif;
      font-size: 0.95rem;
      cursor: pointer;
      text-align: left;
      transition: all 0.25s;
      display: flex;
      align-items: center;
      gap: 0.6rem;
    }
    .q-btn:hover {
      background: var(--blush);
      border-color: var(--rose);
      transform: translateX(5px);
    }
    .q-btn .opt-label {
      background: var(--rose);
      color: #fff;
      width: 24px; height: 24px;
      border-radius: 50%;
      display: flex; align-items: center; justify-content: center;
      font-size: 0.75rem;
      font-weight: 700;
      flex-shrink: 0;
    }

    /* ===== VALENTINE ASK SCREEN ===== */
    #screen-ask {
      background: radial-gradient(ellipse at 40% 60%, #fce4ec, #fff8f5 70%);
      text-align: center;
    }
    .ask-title {
      font-family: 'Dancing Script', cursive;
      font-size: clamp(1.8rem, 7vw, 3rem);
      color: var(--dark);
      margin-bottom: 0.5rem;
    }
    .ask-name {
      font-family: 'Dancing Script', cursive;
      font-size: clamp(3rem, 10vw, 5.5rem);
      color: var(--rose);
      line-height: 1;
      margin-bottom: 0.3rem;
    }
    .ask-question {
      font-family: 'Playfair Display', serif;
      font-size: clamp(1.2rem, 4vw, 2rem);
      color: var(--dark);
      margin-bottom: 2.5rem;
    }
    .btn-yes {
      background: var(--rose);
      color: #fff;
      border: none;
      padding: 1rem 2.5rem;
      border-radius: 50px;
      font-family: 'Dancing Script', cursive;
      font-size: 1.5rem;
      cursor: pointer;
      box-shadow: 0 8px 30px rgba(232,64,90,0.4);
      transition: all 0.2s;
      margin: 0 0.5rem;
      position: relative;
    }
    .btn-yes:hover { transform: scale(1.1); box-shadow: 0 14px 40px rgba(232,64,90,0.55); }

    .btn-no {
      background: #fff;
      color: var(--rose);
      border: 2px solid var(--blush);
      padding: 0.9rem 2rem;
      border-radius: 50px;
      font-family: 'Dancing Script', cursive;
      font-size: 1.3rem;
      cursor: pointer;
      transition: all 0.2s;
      margin: 0 0.5rem;
    }

    .ask-btns { display: flex; flex-wrap: wrap; justify-content: center; gap: 1rem; }

    /* ===== FINAL YES SCREEN ===== */
    #screen-yes {
      background: radial-gradient(ellipse at 50% 50%, #ffe0e8, #fff8f5 70%);
      text-align: center;
    }
    .confetti-hearts {
      font-size: 2rem;
      letter-spacing: 0.3em;
      margin-bottom: 1.5rem;
      animation: bounce2 1s ease infinite alternate;
    }
    @keyframes bounce2 {
      from { transform: scale(0.95); }
      to { transform: scale(1.05); }
    }
    .yes-title {
      font-family: 'Dancing Script', cursive;
      font-size: clamp(2.5rem, 9vw, 5rem);
      color: var(--rose);
      margin-bottom: 1rem;
    }
    .yes-msg {
      font-family: 'Playfair Display', serif;
      font-size: clamp(1rem, 3.5vw, 1.4rem);
      color: #6b3040;
      max-width: 380px;
      line-height: 1.7;
      margin-bottom: 2rem;
    }
    .yes-badge {
      background: var(--rose);
      color: #fff;
      padding: 0.8rem 2rem;
      border-radius: 50px;
      font-family: 'Dancing Script', cursive;
      font-size: 1.4rem;
      letter-spacing: 0.05em;
      box-shadow: 0 6px 25px rgba(232,64,90,0.35);
    }
    .hearts-burst {
      position: fixed; inset: 0;
      pointer-events: none;
      z-index: 9999;
    }
    .burst-heart {
      position: absolute;
      font-size: 2rem;
      animation: burst 1.5s ease-out forwards;
      opacity: 0;
    }
    @keyframes burst {
      0% { transform: translate(0,0) scale(0.5); opacity: 1; }
      100% { transform: translate(var(--tx), var(--ty)) scale(1.2); opacity: 0; }
    }

    /* DIVIDER */
    .divider {
      width: 60px; height: 2px;
      background: linear-gradient(90deg, transparent, var(--rose), transparent);
      margin: 1.2rem auto;
      border-radius: 2px;
    }

    /* score ribbon */
    .score-ribbon {
      background: linear-gradient(135deg, var(--rose), #ff8fa3);
      color: #fff;
      padding: 0.5rem 1.4rem;
      border-radius: 30px;
      font-family: 'Dancing Script', cursive;
      font-size: 1.1rem;
      margin-bottom: 1.5rem;
      display: inline-block;
    }

  </style>
</head>
<body>

<!-- Floating petals -->
<div id="petals"></div>

<!-- ======== SCREEN 1: INTRO ======== -->
<div class="screen active" id="screen-intro">
  <span class="heart-big">💖</span>
  <h1 class="intro-title">Hey, Madhu…</h1>
  <p class="intro-sub">A little something for you</p>
  <div class="divider"></div>
  <p style="font-family:'Playfair Display',serif;font-style:italic;color:#8a4555;margin-bottom:2rem;text-align:center;max-width:300px;font-size:1.05rem;">
    "Before I ask you something very important, I have a few questions…"
  </p>
  <button class="btn-start" onclick="goTo('screen-q1')">Let's begin 💌</button>
</div>

<!-- ======== QUESTION 1 ======== -->
<div class="screen q-screen" id="screen-q1">
  <div class="progress-bar-wrap"><div class="progress-bar" style="width:20%"></div></div>
  <div class="q-card">
    <span class="q-emoji">🌸</span>
    <p class="q-num">Question 1 of 5</p>
    <p class="q-text">If someone made you smile without even trying… what does that say about them?</p>
    <div class="q-options">
      <button class="q-btn" onclick="nextQ('screen-q2')">
        <span class="opt-label">A</span> They're probably magic ✨
      </button>
      <button class="q-btn" onclick="nextQ('screen-q2')">
        <span class="opt-label">B</span> They just get me 🥺
      </button>
      <button class="q-btn" onclick="nextQ('screen-q2')">
        <span class="opt-label">C</span> They're worth keeping 💛
      </button>
    </div>
  </div>
</div>

<!-- ======== QUESTION 2 ======== -->
<div class="screen q-screen" id="screen-q2">
  <div class="progress-bar-wrap"><div class="progress-bar" style="width:40%"></div></div>
  <div class="q-card">
    <span class="q-emoji">🍫</span>
    <p class="q-num">Question 2 of 5</p>
    <p class="q-text">What's the most romantic thing imaginable on Valentine's Day?</p>
    <div class="q-options">
      <button class="q-btn" onclick="nextQ('screen-q3')">
        <span class="opt-label">A</span> Candles, roses & chocolate 🌹
      </button>
      <button class="q-btn" onclick="nextQ('screen-q3')">
        <span class="opt-label">B</span> A long walk under the stars 🌙
      </button>
      <button class="q-btn" onclick="nextQ('screen-q3')">
        <span class="opt-label">C</span> Someone who just shows up 💕
      </button>
    </div>
  </div>
</div>

<!-- ======== QUESTION 3 ======== -->
<div class="screen q-screen" id="screen-q3">
  <div class="progress-bar-wrap"><div class="progress-bar" style="width:60%"></div></div>
  <div class="q-card">
    <span class="q-emoji">💭</span>
    <p class="q-num">Question 3 of 5</p>
    <p class="q-text">Hypothetically… if someone had a massive crush on you, what would be the best way to tell you?</p>
    <div class="q-options">
      <button class="q-btn" onclick="nextQ('screen-q4')">
        <span class="opt-label">A</span> A sweet handwritten note 📝
      </button>
      <button class="q-btn" onclick="nextQ('screen-q4')">
        <span class="opt-label">B</span> Just say it — be brave! 😤
      </button>
      <button class="q-btn" onclick="nextQ('screen-q4')">
        <span class="opt-label">C</span> A cute little webpage like this 😏
      </button>
    </div>
  </div>
</div>

<!-- ======== QUESTION 4 ======== -->
<div class="screen q-screen" id="screen-q4">
  <div class="progress-bar-wrap"><div class="progress-bar" style="width:80%"></div></div>
  <div class="q-card">
    <span class="q-emoji">🌹</span>
    <p class="q-num">Question 4 of 5</p>
    <p class="q-text">Which would you pick: a thousand roses OR one person who thinks you're worth a thousand roses?</p>
    <div class="q-options">
      <button class="q-btn" onclick="nextQ('screen-q5')">
        <span class="opt-label">A</span> The thousand roses, obviously 💐
      </button>
      <button class="q-btn" onclick="nextQ('screen-q5')">
        <span class="opt-label">B</span> The person, every single time 🥰
      </button>
      <button class="q-btn" onclick="nextQ('screen-q5')">
        <span class="opt-label">C</span> Both — I'm not settling 😄
      </button>
    </div>
  </div>
</div>

<!-- ======== QUESTION 5 ======== -->
<div class="screen q-screen" id="screen-q5">
  <div class="progress-bar-wrap"><div class="progress-bar" style="width:100%"></div></div>
  <div class="q-card">
    <span class="q-emoji">🎯</span>
    <p class="q-num">Question 5 of 5 — The Final One!</p>
    <p class="q-text">Be honest… did you enjoy these questions a little? 👀</p>
    <div class="q-options">
      <button class="q-btn" onclick="nextQ('screen-ask')">
        <span class="opt-label">A</span> Yes, they were cute 😊
      </button>
      <button class="q-btn" onclick="nextQ('screen-ask')">
        <span class="opt-label">B</span> Okay, I'm a little curious what comes next…
      </button>
      <button class="q-btn" onclick="nextQ('screen-ask')">
        <span class="opt-label">C</span> Just get to the point already! 😂
      </button>
    </div>
  </div>
</div>

<!-- ======== ASK SCREEN ======== -->
<div class="screen" id="screen-ask">
  <span class="score-ribbon">✨ 5/5 Questions Answered ✨</span>
  <p class="ask-title">Now, the real question…</p>
  <p class="ask-name">Madhu,</p>
  <div class="divider"></div>
  <p class="ask-question" id="ask-q-text">Will you be my Valentine? 💝</p>
  <div class="ask-btns">
    <button class="btn-yes" onclick="sayYes()">Yes! 💖</button>
    <button class="btn-no" id="btn-no" onmouseover="runAway(this)" onclick="runAway(this)">Nooo 🙈</button>
  </div>
  <p id="no-counter-msg" style="margin-top:1.2rem;font-family:'Playfair Display',serif;font-style:italic;color:#c4607a;font-size:0.95rem;min-height:1.5em;"></p>
</div>

<!-- ======== YES SCREEN ======== -->
<div class="screen" id="screen-yes">
  <div class="confetti-hearts">💖 💕 🌹 💗 🌸</div>
  <h1 class="yes-title">Yaaay! 🎉</h1>
  <div class="divider"></div>
  <p class="yes-msg">
    You just made my heart do a happy dance, Madhu.<br><br>
    This Valentine's Day is going to be extra special — because of <em>you</em>. 🌹
  </p>
  <div class="yes-badge">Happy Valentine's Day 💌</div>
  <div class="hearts-burst" id="hearts-burst"></div>
</div>

<script>
  // ---- Floating petals ----
  const petalEl = document.getElementById('petals');
  const emojis = ['🌸','🌺','💮','🌷','❤️','💕','✨'];
  for(let i = 0; i < 18; i++) {
    const p = document.createElement('div');
    p.className = 'petal';
    p.textContent = emojis[Math.floor(Math.random()*emojis.length)];
    p.style.left = Math.random()*100 + 'vw';
    p.style.animationDuration = (5 + Math.random()*8) + 's';
    p.style.animationDelay = (-Math.random()*10) + 's';
    p.style.fontSize = (0.8 + Math.random()*1.2) + 'rem';
    petalEl.appendChild(p);
  }

  // ---- Navigation ----
  function goTo(id) {
    document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
    document.getElementById(id).classList.add('active');
    window.scrollTo(0,0);
  }
  function nextQ(id) { goTo(id); }

  // ---- No button run away ----
  let noCount = 0;
  const noPhrases = [
    "Are you sureeee? 🥺",
    "Think again, Madhu… 👀",
    "That can't be right! 💔",
    "Last chance… 🌹",
    "Okay, okay… just press YES! 😄"
  ];
  function runAway(btn) {
    noCount++;
    const vw = window.innerWidth;
    const vh = window.innerHeight;
    const x = Math.random()*(vw-100);
    const y = Math.random()*(vh-50);
    btn.style.position = 'fixed';
    btn.style.left = x + 'px';
    btn.style.top = y + 'px';
    btn.style.zIndex = 9999;
    const msg = document.getElementById('no-counter-msg');
    msg.textContent = noPhrases[Math.min(noCount-1, noPhrases.length-1)];
    if(noCount >= 5) {
      btn.style.display = 'none';
      msg.textContent = "The 'No' button gave up! Looks like destiny has decided 😉";
    }
  }

  // ---- Say Yes ----
  function sayYes() {
    goTo('screen-yes');
    burstHearts();
  }

  function burstHearts() {
    const container = document.getElementById('hearts-burst');
    const cx = window.innerWidth / 2;
    const cy = window.innerHeight / 2;
    for(let i = 0; i < 30; i++) {
      const h = document.createElement('div');
      h.className = 'burst-heart';
      h.textContent = ['💖','💕','🌹','💗','✨','💝','🌸'][Math.floor(Math.random()*7)];
      const angle = Math.random()*360;
      const dist = 100 + Math.random()*200;
      h.style.left = cx + 'px';
      h.style.top = cy + 'px';
      h.style.setProperty('--tx', Math.cos(angle*Math.PI/180)*dist + 'px');
      h.style.setProperty('--ty', Math.sin(angle*Math.PI/180)*dist + 'px');
      h.style.animationDelay = Math.random()*0.5 + 's';
      container.appendChild(h);
    }
    setTimeout(() => container.innerHTML = '', 2500);
    setTimeout(burstHearts, 2600);
  }
</script>
</body>
</html>
