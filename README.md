# github.io-FiveCrowns
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>The Five Crowns — Find Your Reward</title>
<meta name="theme-color" content="#3A2142">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="mobile-web-app-capable" content="yes">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@500;600;700&family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;1,400;1,500&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --parchment:#F1E6CC;
    --parchment-dark:#E4D3A8;
    --parchment-line: rgba(36,27,46,0.16);
    --ink:#241B2E;
    --ink-soft:#584D64;
    --royal:#3A2142;
    --royal-light:#6B3F73;
    --gold:#A9812E;
    --gold-light:#D4AF61;
    --burgundy:#7A2938;
    --cream:#FBF6E9;
    --shadow: 0 10px 30px rgba(36,27,46,0.18);
    --radius: 14px;
  }
  *,*::before,*::after{box-sizing:border-box;}
  html,body{margin:0;padding:0;}
  body{
    background:#d8c9a3;
    font-family:'Inter',sans-serif;
    color:var(--ink);
    -webkit-font-smoothing:antialiased;
    min-height:100vh;
  }
  @media (prefers-reduced-motion: reduce){
    *{animation:none!important;transition:none!important;}
  }
  .app-shell{
    max-width:480px;
    margin:0 auto;
    min-height:100vh;
    background:
      radial-gradient(ellipse at top, rgba(255,255,255,0.35), transparent 60%),
      var(--parchment);
    position:relative;
    display:flex;
    flex-direction:column;
    overflow-x:hidden;
  }
  @media (min-width:600px){
    body{padding:24px 0;}
    .app-shell{min-height:calc(100vh - 48px); box-shadow: var(--shadow); border-radius:28px; overflow:hidden;}
  }

  /* ---------- header ---------- */
  .topbar{
    display:flex;
    align-items:center;
    justify-content:space-between;
    padding:16px 20px;
    background:var(--royal);
    color:var(--cream);
    position:sticky;
    top:0;
    z-index:20;
  }
  .topbar .brand{
    font-family:'Cinzel',serif;
    font-size:14px;
    letter-spacing:1.5px;
    text-transform:uppercase;
    color:var(--gold-light);
  }
  .icon-btn{
    background:none;
    border:1px solid rgba(212,175,97,0.5);
    color:var(--gold-light);
    width:34px;height:34px;
    border-radius:50%;
    display:flex;align-items:center;justify-content:center;
    cursor:pointer;
    font-family:'Cinzel',serif;
    font-size:13px;
  }
  .icon-btn:focus-visible, button:focus-visible, .opt-btn:focus-visible, textarea:focus-visible{
    outline:2px solid var(--gold);
    outline-offset:2px;
  }

  /* ---------- screens ---------- */
  .screen{
    display:none;
    flex:1;
    flex-direction:column;
    padding:28px 22px 40px;
    animation:fadeIn .35s ease;
  }
  .screen.active{display:flex;}
  @keyframes fadeIn{ from{opacity:0; transform:translateY(6px);} to{opacity:1; transform:translateY(0);} }

  .ornament{
    text-align:center;
    color:var(--gold);
    font-size:22px;
    letter-spacing:8px;
    margin-bottom:6px;
  }
  h1.display{
    font-family:'Cinzel',serif;
    font-weight:700;
    font-size:30px;
    letter-spacing:1px;
    text-align:center;
    color:var(--royal);
    margin:0 0 4px;
    line-height:1.25;
  }
  .subtitle{
    font-family:'Cormorant Garamond',serif;
    font-style:italic;
    font-size:19px;
    text-align:center;
    color:var(--ink-soft);
    margin:0 0 28px;
  }
  .lede{
    font-family:'Cormorant Garamond',serif;
    font-size:19px;
    line-height:1.55;
    color:var(--ink);
    text-align:center;
    margin:0 0 30px;
  }

  .btn{
    display:block;
    width:100%;
    text-align:center;
    font-family:'Inter',sans-serif;
    font-weight:600;
    font-size:16px;
    padding:15px 18px;
    border-radius:999px;
    border:none;
    cursor:pointer;
    transition:transform .15s ease, box-shadow .15s ease;
  }
  .btn-primary{
    background:linear-gradient(135deg, var(--gold-light), var(--gold));
    color:var(--royal);
    box-shadow:0 8px 18px rgba(169,129,46,0.35);
  }
  .btn-primary:active{transform:scale(0.98);}
  .btn-ghost{
    background:transparent;
    color:var(--royal);
    border:1.5px solid var(--royal);
    margin-top:12px;
  }
  .btn-text{
    background:none;border:none;
    color:var(--ink-soft);
    font-family:'Inter',sans-serif;
    text-decoration:underline;
    font-size:14px;
    cursor:pointer;
    padding:8px;
  }

  .home-crown{
    display:flex;justify-content:center;margin:8px 0 22px;
  }
  .home-crown svg{width:120px;height:100px;color:var(--gold);}

  .home-actions{margin-top:auto;padding-top:20px;}

  .tip{
    font-size:12.5px;
    color:var(--ink-soft);
    text-align:center;
    margin-top:18px;
    line-height:1.5;
  }

  /* ---------- crown info cards ---------- */
  .crown-card{
    background:var(--cream);
    border:1px solid var(--parchment-line);
    border-radius:var(--radius);
    padding:18px;
    margin-bottom:14px;
    box-shadow:0 4px 14px rgba(36,27,46,0.08);
  }
  .crown-card-head{display:flex;align-items:center;gap:14px;margin-bottom:8px;}
  .crown-card-head svg{width:44px;height:38px;flex-shrink:0;}
  .crown-card-name{font-family:'Cinzel',serif;font-size:16px;color:var(--royal);margin:0;}
  .crown-card-ref{font-family:'Inter',sans-serif;font-size:11px;letter-spacing:0.5px;text-transform:uppercase;color:var(--burgundy);margin-top:2px;}
  .crown-card-verse{
    font-family:'Cormorant Garamond',serif;
    font-style:italic;
    font-size:16.5px;
    line-height:1.5;
    color:var(--ink);
    border-left:2px solid var(--gold);
    padding-left:12px;
    margin:10px 0;
  }
  .crown-card-summary{font-size:14px;color:var(--ink-soft);line-height:1.5;}

  /* ---------- progress ---------- */
  .progress-wrap{margin-bottom:24px;}
  .progress-label{
    font-size:12px;color:var(--ink-soft);text-transform:uppercase;letter-spacing:1px;
    display:flex;justify-content:space-between;margin-bottom:8px;
  }
  .progress-track{
    position:relative;height:6px;background:var(--parchment-dark);border-radius:4px;overflow:visible;
  }
  .progress-fill{
    position:absolute;left:0;top:0;height:100%;background:linear-gradient(90deg,var(--gold-light),var(--gold));
    border-radius:4px;transition:width .35s ease;
  }
  .progress-glyph{
    position:absolute;top:50%;width:20px;height:20px;transform:translate(-50%,-50%);color:var(--royal);
    transition:left .35s ease;
  }

  /* ---------- question ---------- */
  .q-card{flex:1;display:flex;flex-direction:column;}
  .q-text{
    font-family:'Cormorant Garamond',serif;
    font-size:23px;
    line-height:1.4;
    color:var(--royal);
    margin:0 0 20px;
  }
  .opt-list{display:flex;flex-direction:column;gap:10px;margin-bottom:20px;}
  .opt-btn{
    text-align:left;
    background:var(--cream);
    border:1.5px solid var(--parchment-line);
    border-radius:12px;
    padding:14px 16px;
    font-family:'Inter',sans-serif;
    font-size:14.5px;
    line-height:1.45;
    color:var(--ink);
    cursor:pointer;
    transition:all .15s ease;
  }
  .opt-btn:hover{border-color:var(--gold);}
  .opt-btn.selected{
    background:linear-gradient(135deg, rgba(212,175,97,0.25), rgba(169,129,46,0.12));
    border-color:var(--gold);
    box-shadow:0 3px 10px rgba(169,129,46,0.2);
  }
  .gift-grid{display:flex;flex-wrap:wrap;gap:10px;margin-bottom:20px;}
  .gift-pill{
    background:var(--cream);
    border:1.5px solid var(--parchment-line);
    border-radius:999px;
    padding:10px 16px;
    font-size:13.5px;
    font-family:'Inter',sans-serif;
    color:var(--ink);
    cursor:pointer;
    transition:all .15s ease;
  }
  .gift-pill.selected{
    background:var(--royal);
    border-color:var(--royal);
    color:var(--cream);
  }
  .field-label{
    font-family:'Cormorant Garamond',serif;
    font-size:19px;
    color:var(--royal);
    margin:0 0 8px;
  }
  .field-hint{font-size:12.5px;color:var(--ink-soft);margin:0 0 8px;}
  textarea{
    width:100%;
    min-height:86px;
    border:1.5px dashed var(--ink-soft);
    background:rgba(255,255,255,0.4);
    border-radius:10px;
    padding:12px 14px;
    font-family:'Inter',sans-serif;
    font-size:14.5px;
    color:var(--ink);
    resize:vertical;
    margin-bottom:22px;
  }
  .nav-row{display:flex;gap:10px;margin-top:auto;padding-top:8px;}
  .nav-row .btn{flex:1;}

  /* ---------- results ---------- */
  .result-crown-wrap{display:flex;justify-content:center;margin:6px 0 14px;}
  .result-crown-wrap svg{width:150px;height:125px;}
  .crown-path{
    fill:none;stroke:currentColor;stroke-width:4;stroke-linejoin:round;stroke-linecap:round;
    stroke-dasharray:460; stroke-dashoffset:460;
  }
  .active .crown-path{animation:draw 1.1s ease forwards;}
  @keyframes draw{ to{stroke-dashoffset:0;} }
  .crown-jewel{fill:currentColor; opacity:0; animation:pop .3s ease forwards; animation-delay:1.05s;}
  @keyframes pop{ to{opacity:1;} }
  .result-name{
    font-family:'Cinzel',serif;
    font-size:24px;
    text-align:center;
    color:var(--royal);
    margin:0 0 4px;
  }
  .result-ref{
    text-align:center;
    font-size:11.5px;
    letter-spacing:1px;
    text-transform:uppercase;
    color:var(--burgundy);
    margin-bottom:16px;
  }
  .result-verse{
    font-family:'Cormorant Garamond',serif;
    font-style:italic;
    font-size:18px;
    line-height:1.55;
    text-align:center;
    color:var(--ink);
    padding:0 6px;
    margin-bottom:8px;
  }
  .result-verseref{text-align:center;font-size:12.5px;color:var(--ink-soft);margin-bottom:22px;}
  .section-block{
    background:var(--cream);
    border:1px solid var(--parchment-line);
    border-radius:var(--radius);
    padding:18px;
    margin-bottom:16px;
  }
  .section-title{
    font-family:'Cinzel',serif;
    font-size:13px;
    letter-spacing:1.2px;
    text-transform:uppercase;
    color:var(--royal);
    margin:0 0 10px;
  }
  .section-body{font-size:14.5px;line-height:1.6;color:var(--ink);}
  .quote-back{font-style:italic;color:var(--ink-soft);}
  .steps-list{list-style:none;margin:0;padding:0;}
  .steps-list li{
    position:relative;
    padding-left:22px;
    margin-bottom:10px;
    font-size:14.5px;
    line-height:1.5;
    color:var(--ink);
  }
  .steps-list li::before{
    content:"✦";
    position:absolute;left:0;top:1px;
    color:var(--gold);
    font-size:13px;
  }
  .secondary-note{
    display:flex;align-items:flex-start;gap:12px;
  }
  .secondary-note svg{width:34px;height:29px;flex-shrink:0;margin-top:2px;}
  .about-note{
    font-size:12px;
    line-height:1.6;
    color:var(--ink-soft);
    border-top:1px solid var(--parchment-line);
    padding-top:14px;
    margin-top:6px;
  }

  /* ---------- modal ---------- */
  .modal-overlay{
    position:fixed;inset:0;background:rgba(36,27,46,0.55);
    display:none;align-items:flex-end;justify-content:center;z-index:50;
  }
  .modal-overlay.active{display:flex;}
  .modal-sheet{
    background:var(--parchment);
    width:100%;max-width:480px;
    max-height:82vh;
    overflow-y:auto;
    border-radius:20px 20px 0 0;
    padding:20px 20px 30px;
    animation:slideUp .3s ease;
  }
  @keyframes slideUp{from{transform:translateY(24px);opacity:0;} to{transform:translateY(0);opacity:1;}}
  .modal-head{display:flex;justify-content:space-between;align-items:center;margin-bottom:14px;}
  .modal-head h2{font-family:'Cinzel',serif;font-size:17px;color:var(--royal);margin:0;}
  .close-x{background:none;border:none;font-size:20px;color:var(--ink-soft);cursor:pointer;}
</style>
</head>
<body>
<div class="app-shell">

  <div class="topbar">
    <span class="brand">The Five Crowns</span>
    <button class="icon-btn" id="infoBtn" aria-label="View the five crowns">i</button>
  </div>

  <!-- WELCOME -->
  <section class="screen active" id="screen-welcome">
    <div class="ornament">❦</div>
    <div class="home-crown" id="homeCrownIcon"></div>
    <h1 class="display">Find Your Crown</h1>
    <p class="subtitle">A scripture-rooted journey of self-discovery</p>
    <p class="lede">Scripture describes several crowns believers may receive as rewards for a life of faithfulness. Answer honestly about who you are, and discover which crown your life is most shaped to pursue.</p>
    <div class="home-actions">
      <button class="btn btn-primary" id="startBtn">Begin the Journey</button>
      <button class="btn btn-ghost" id="learnBtn">Explore the Five Crowns First</button>
      <p class="tip">Tip: add this page to your Home Screen (Share → Add to Home Screen) to use it like an app.</p>
    </div>
  </section>

  <!-- CROWNS INFO (as its own screen when reached via "Explore") -->
  <section class="screen" id="screen-crowns">
    <h1 class="display" style="font-size:24px;margin-bottom:4px;">The Five Crowns</h1>
    <p class="subtitle" style="margin-bottom:22px;">Rewards Scripture promises the faithful</p>
    <div id="crownsList"></div>
    <button class="btn btn-primary" id="toQuizFromInfo" style="margin-top:8px;">Begin the Journey</button>
    <button class="btn btn-text" id="backHomeFromInfo">Back</button>
  </section>

  <!-- QUIZ -->
  <section class="screen" id="screen-quiz">
    <div class="progress-wrap">
      <div class="progress-label"><span id="progressText">Question 1 of 9</span><span>Personality &amp; Calling</span></div>
      <div class="progress-track">
        <div class="progress-fill" id="progressFill"></div>
      </div>
    </div>
    <div class="q-card">
      <p class="q-text" id="qText"></p>
      <div class="opt-list" id="qOptions"></div>
      <div class="nav-row">
        <button class="btn btn-ghost" id="qBack">Back</button>
        <button class="btn btn-primary" id="qNext" disabled>Next</button>
      </div>
    </div>
  </section>

  <!-- GIFTS -->
  <section class="screen" id="screen-gifts">
    <p class="field-label">Which of these describe a gift or ability you carry?</p>
    <p class="field-hint">Select as many as genuinely fit — there's no "right" number.</p>
    <div class="gift-grid" id="giftGrid"></div>
    <div class="nav-row">
      <button class="btn btn-ghost" id="giftsBack">Back</button>
      <button class="btn btn-primary" id="giftsNext">Next</button>
    </div>
  </section>

  <!-- TEXT REFLECTIONS -->
  <section class="screen" id="screen-texts">
    <p class="field-label">A few things in your own words</p>
    <p class="field-hint">Optional, but it helps sharpen your result.</p>

    <p class="field-label" style="font-size:16px;">Your goals in your walk with God</p>
    <textarea id="txtGoals" placeholder="e.g. I want to finish my life faithfully and help others grow..."></textarea>

    <p class="field-label" style="font-size:16px;">A weakness you're working through</p>
    <textarea id="txtWeak" placeholder="e.g. I struggle with consistency in prayer..."></textarea>

    <p class="field-label" style="font-size:16px;">A strength others notice in you</p>
    <textarea id="txtStrength" placeholder="e.g. People say I'm patient and steady under pressure..."></textarea>

    <div class="nav-row">
      <button class="btn btn-ghost" id="textsBack">Back</button>
      <button class="btn btn-primary" id="textsNext">See My Crown</button>
    </div>
  </section>

  <!-- RESULTS -->
  <section class="screen" id="screen-results">
    <div class="result-crown-wrap" id="resultCrownIcon"></div>
    <h2 class="result-name" id="resName"></h2>
    <p class="result-ref" id="resRef"></p>
    <p class="result-verse" id="resVerse"></p>
    <p class="result-verseref" id="resVerseRef"></p>

    <div class="section-block">
      <p class="section-title">What This Crown Is</p>
      <p class="section-body" id="resSummary"></p>
    </div>

    <div class="section-block">
      <p class="section-title">Your Encouragement</p>
      <p class="section-body" id="resEncouragement"></p>
    </div>

    <div class="section-block">
      <p class="section-title">Actions to Pursue This Crown</p>
      <ul class="steps-list" id="resSteps"></ul>
    </div>

    <div class="section-block" id="secondaryBlock" style="display:none;">
      <p class="section-title">Also Worth Noticing</p>
      <div class="secondary-note">
        <div id="secIcon"></div>
        <p class="section-body" id="secText"></p>
      </div>
    </div>

    <p class="about-note">A note on crowns: Scripture speaks of several distinct rewards for faithfulness, and Revelation 4:10 reminds us that every crown believers receive is ultimately laid before Christ's throne in worship, not kept as a personal trophy. This assessment follows one common way — especially within Protestant teaching — of naming those rewards; other Christian traditions describe heavenly reward differently. Treat your result as a mirror for reflection, not a prophecy.</p>

    <button class="btn btn-ghost" id="restartBtn" style="margin-top:18px;">Take the Journey Again</button>
  </section>

</div>

<!-- MODAL: crowns quick reference, reachable any time -->
<div class="modal-overlay" id="modalOverlay">
  <div class="modal-sheet">
    <div class="modal-head">
      <h2>The Five Crowns</h2>
      <button class="close-x" id="modalClose" aria-label="Close">✕</button>
    </div>
    <div id="modalCrownsList"></div>
  </div>
</div>

<script>
(function(){
  "use strict";

  /* ============ CROWN ICON MARKUP ============ */
  // shared base crown silhouette; ornament + jewel color varies per crown
  function crownSVG(key, opts){
    opts = opts || {};
    var animated = !!opts.animated;
    var jewelDelayBase = 1.05;
    var ornaments = {
      life: '<path d="M55,27 C55,17 60,13 60,5 C60,13 65,17 65,27 C65,22 60,20 60,20 C60,20 55,22 55,27 Z" fill="currentColor"/>',
      righteousness:
        '<g stroke="currentColor" stroke-width="2.5" stroke-linecap="round">' +
        '<line x1="60" y1="34" x2="60" y2="16"/>' +
        '<line x1="45" y1="38" x2="34" y2="24"/>' +
        '<line x1="75" y1="38" x2="86" y2="24"/>' +
        '<line x1="36" y1="48" x2="20" y2="42"/>' +
        '<line x1="84" y1="48" x2="100" y2="42"/>' +
        '</g>',
      glory:
        '<path d="M16,96 L78,22" stroke="currentColor" stroke-width="4" stroke-linecap="round" fill="none"/>' +
        '<path d="M78,22 C90,14 92,28 80,29" stroke="currentColor" stroke-width="4" stroke-linecap="round" fill="none"/>',
      incorruptible:
        '<g fill="currentColor" opacity="0.9">' +
        '<ellipse cx="11" cy="88" rx="5" ry="2.4" transform="rotate(-35 11 88)"/>' +
        '<ellipse cx="8" cy="76" rx="5" ry="2.4" transform="rotate(-55 8 76)"/>' +
        '<ellipse cx="10" cy="64" rx="5" ry="2.4" transform="rotate(-75 10 64)"/>' +
        '<ellipse cx="109" cy="88" rx="5" ry="2.4" transform="rotate(35 109 88)"/>' +
        '<ellipse cx="112" cy="76" rx="5" ry="2.4" transform="rotate(55 112 76)"/>' +
        '<ellipse cx="110" cy="64" rx="5" ry="2.4" transform="rotate(75 110 64)"/>' +
        '</g>',
      rejoicing:
        '<g fill="currentColor">' +
        star(20,28,4) + star(100,28,4) + star(60,10,4.5) +
        '</g>'
    };
    function star(cx,cy,s){
      var pts = [
        [cx, cy-s],[cx+s*0.32, cy-s*0.32],[cx+s, cy],[cx+s*0.32, cy+s*0.32],
        [cx, cy+s],[cx-s*0.32, cy+s*0.32],[cx-s, cy],[cx-s*0.32, cy-s*0.32]
      ];
      var d = "M" + pts.map(function(p){return p[0].toFixed(1)+","+p[1].toFixed(1);}).join(" L") + " Z";
      return '<path d="'+d+'"/>';
    }
    var crownPathClass = animated ? 'crown-path' : '';
    var crownPath = '<path class="'+crownPathClass+'" d="M18,92 L18,78 L34,42 L50,78 L60,30 L70,78 L86,42 L102,78 L102,92 Z"/>';
    var jewelClass = animated ? 'crown-jewel' : '';
    var jewelStyle1 = animated ? ' style="animation-delay:'+jewelDelayBase+'s"' : '';
    var jewelStyle2 = animated ? ' style="animation-delay:'+(jewelDelayBase+0.12)+'s"' : '';
    var jewelStyle3 = animated ? ' style="animation-delay:'+(jewelDelayBase+0.24)+'s"' : '';
    var jewels =
      '<circle class="'+jewelClass+'" cx="34" cy="42" r="4"'+jewelStyle1+'/>' +
      '<circle class="'+jewelClass+'" cx="60" cy="30" r="5"'+jewelStyle2+'/>' +
      '<circle class="'+jewelClass+'" cx="86" cy="42" r="4"'+jewelStyle3+'/>';

    var behind = (key === 'righteousness') ? ornaments[key] : '';
    var front = (key === 'righteousness') ? '' : (ornaments[key] || '');

    return '<svg viewBox="0 0 120 100" xmlns="http://www.w3.org/2000/svg">' +
      behind + crownPath + jewels + front + '</svg>';
  }

  /* ============ DATA ============ */
  var CROWNS = {
    life: {
      key:'life',
      name:'Crown of Life',
      ref:'James 1:12 · Revelation 2:10',
      verse:'"Blessed is the man that endureth temptation: for when he is tried, he shall receive the crown of life, which the Lord hath promised to them that love him."',
      verseRef:'James 1:12, KJV',
      accent:'var(--burgundy)',
      summary:'Given to those who love God steadfastly through trial, temptation, and suffering — faith that keeps holding on when holding on is hard.',
      encouragement:'You may not always feel strong, but you keep showing up faithfully, even when a season is genuinely hard — and that kind of quiet endurance is exactly what heaven notices. You are not being tested because God is far from you; you are being tested because He trusts what your faith can carry. Keep loving Him through it.',
      steps:[
        'Keep a short "faithfulness log" of how God has met you in hard seasons, so you can reread it before the next one.',
        'Memorize James 1:12 and Romans 5:3-5 now, before hardship hits — not in the middle of it.',
        'Sit with one person walking through suffering this week. Presence matters more than advice.',
        'When you feel like quitting something hard, pray Psalm 27 out loud before you decide anything.'
      ],
      keywords:['trial','suffer','pain','endur','persever','patien','tempt','difficult','hardship','faithful','loyal','steadfast','trust','illness','loss','grief','struggl','hard time']
    },
    righteousness: {
      key:'righteousness',
      name:'Crown of Righteousness',
      ref:'2 Timothy 4:8',
      verse:'"Henceforth there is laid up for me a crown of righteousness, which the Lord, the righteous judge, shall give me at that day: and not to me only, but unto all them also that love his appearing."',
      verseRef:'2 Timothy 4:8, KJV',
      accent:'var(--gold)',
      summary:'For those who finish the race, keep the faith, and live with a holy longing for Christ\'s return — integrity that holds up under no supervision but His.',
      encouragement:"You are the kind of person who does the right thing when no one is watching, and who keeps one eye on eternity even while living an ordinary Tuesday. That's rarer than it sounds, and it's exactly the character this crown is promised to. Keep finishing well — one faithful, unremarkable day at a time.",
      steps:[
        'Name one area of personal integrity to guard fiercely this month — a habit, a boundary, an unseen choice.',
        'Read a passage on Christ\'s return (Titus 2:11-14 or 2 Peter 3) monthly to refresh your "finish line" perspective.',
        'Ask a trusted friend to check in on one specific, named area of your life — not just "how are you."',
        'At the start of each week, ask: "what would it look like to finish this week well?"'
      ],
      keywords:['holy','holiness','righteous','integrity','purity','discipline','future','return of christ','second coming','obedien','truth','justice','principle','standard','finish the race','complete','honest']
    },
    glory: {
      key:'glory',
      name:'Crown of Glory',
      ref:'1 Peter 5:2-4',
      verse:'"Feed the flock of God which is among you, taking the oversight thereof... And when the chief Shepherd shall appear, ye shall receive a crown of glory that fadeth not away."',
      verseRef:'1 Peter 5:2,4, KJV',
      accent:'var(--royal)',
      summary:'For those who shepherd others — leading, teaching, mentoring — not for profit or control, but willingly, gently, and by example.',
      encouragement:"People grow because you show up for them — you teach, you mentor, you carry other people's questions and struggles as if they were your own. That's shepherd's work, and it's easy to underestimate how much it costs you. Keep tending the people God has actually put in front of you; that is the ministry this crown is for.",
      steps:[
        'Identify one specific person you could intentionally mentor or disciple this season, and reach out this week.',
        'Prepare to teach or lead something small — a group, a lesson, a conversation — this month.',
        'Ask an older mentor how they shepherded others, and borrow one practice from them.',
        'Serve someone in your care in a way that costs you time, not just advice.'
      ],
      keywords:['lead','mentor','shepherd','teach','guide','pastor','disciple','nurture','train others','oversee','manage','help others grow','care for people','hospitality']
    },
    incorruptible: {
      key:'incorruptible',
      name:'Incorruptible Crown',
      ref:'1 Corinthians 9:24-25',
      verse:'"Every man that striveth for the mastery is temperate in all things. Now they do it to obtain a corruptible crown; but we an incorruptible."',
      verseRef:'1 Corinthians 9:25, KJV',
      accent:'var(--ink)',
      summary:'For those who train like an athlete — disciplined, focused, running to win rather than running aimlessly.',
      encouragement:"You already know that feelings are unreliable and habits are not — so you build the habit. That discipline isn't legalism; it's how you actually keep your word to God when motivation runs out. Keep training. The self-control nobody applauds is exactly what this crown rewards.",
      steps:[
        'Pick one spiritual discipline — prayer, fasting, Scripture memory — and commit to a specific, measurable practice for 30 days.',
        'Name your most undisciplined area honestly, and build one concrete daily habit to address it.',
        'Track your progress like training: a short weekly check-in with yourself or an accountability partner.',
        'Remove one specific distraction that keeps quietly derailing your discipline.'
      ],
      keywords:['self-control','self control','discipline','habit','training','focus','goal','exercise','diet','consist','practice','master','routine','willpower','fasting']
    },
    rejoicing: {
      key:'rejoicing',
      name:'Crown of Rejoicing',
      ref:'1 Thessalonians 2:19 · Philippians 4:1',
      verse:'"For what is our hope, or joy, or crown of rejoicing? Are not even ye in the presence of our Lord Jesus Christ at his coming?"',
      verseRef:'1 Thessalonians 2:19, KJV',
      accent:'var(--royal-light)',
      summary:'For those whose deepest joy is watching someone else come to know Christ — the fruit of a faithful witness.',
      encouragement:"You come alive talking about Jesus with someone who doesn't know Him yet, and you genuinely rejoice over other people's spiritual breakthroughs. That joy is not incidental — it's the exact reward Paul says will meet you at Christ's coming. Keep telling people. It matters more than you can currently measure.",
      steps:[
        'Write your testimony in under two minutes and practice saying it out loud this week.',
        'Pray by name for three specific people who don\'t yet know Christ.',
        'Invite someone to church, a Bible study, or an honest gospel conversation this month.',
        'Follow up with someone you\'ve already shared the gospel with — discipleship matters as much as the first conversation.'
      ],
      keywords:['evangel','gospel','witness','soul','convert','mission','outreach','tell others','preach','invite','bring people to','win souls','testimony','share my faith','share the gospel']
    }
  };
  var ORDER = ['life','righteousness','glory','incorruptible','rejoicing'];

  var QUESTIONS = [
    {text:"When life gets hard, which of these feels most like you?", options:[
      {label:"I dig in and hold on to God, no matter how long the trial lasts.", crown:'life'},
      {label:"I keep my eyes on eternity and try to live it right, one day at a time.", crown:'righteousness'},
      {label:"I look for someone nearby I can help carry the load.", crown:'glory'},
      {label:"I tighten my discipline — prayer, habits, focus — until I'm through it.", crown:'incorruptible'},
      {label:"I look for someone I can point to the gospel, even in my own hardship.", crown:'rejoicing'}
    ]},
    {text:"Which ability do people most often notice in you?", options:[
      {label:"Endurance — I don't quit, even when things drag on.", crown:'life'},
      {label:"Integrity — I do the right thing even when no one's watching.", crown:'righteousness'},
      {label:"Care — I notice when someone needs support and I step in.", crown:'glory'},
      {label:"Discipline — I stick to habits and follow through.", crown:'incorruptible'},
      {label:"Persuasion — I can explain my faith in a way that makes people think.", crown:'rejoicing'}
    ]},
    {text:"In church or ministry, where do you naturally gravitate?", options:[
      {label:"Praying for and sitting with people who are suffering.", crown:'life'},
      {label:"Studying Scripture and applying it faithfully to daily choices.", crown:'righteousness'},
      {label:"Teaching, leading a group, or mentoring someone younger in faith.", crown:'glory'},
      {label:"Personal disciplines — fasting, early prayer, Scripture memory.", crown:'incorruptible'},
      {label:"Sharing the gospel with someone who doesn't know Jesus.", crown:'rejoicing'}
    ]},
    {text:"Picture your life in ten years. What matters most to you?", options:[
      {label:"That I stayed faithful to God through whatever came.", crown:'life'},
      {label:"That I lived with integrity and finished well.", crown:'righteousness'},
      {label:"That the people I led or mentored grew because of me.", crown:'glory'},
      {label:"That I mastered my flesh and grew in godly discipline.", crown:'incorruptible'},
      {label:"That I led as many people to Christ as I could.", crown:'rejoicing'}
    ]},
    {text:"What's your instinct when you notice a weakness in yourself?", options:[
      {label:"I ask God for strength to endure it rather than escape it.", crown:'life'},
      {label:"I hold myself to Scripture's standard and course-correct.", crown:'righteousness'},
      {label:"I ask a mentor, or someone I disciple, to keep me accountable.", crown:'glory'},
      {label:"I build a new habit or routine to train it out.", crown:'incorruptible'},
      {label:"I use my own struggle to relate to people I'm trying to reach.", crown:'rejoicing'}
    ]},
    {text:"What motivates you most in your walk with God?", options:[
      {label:"Knowing He's faithful even when life isn't easy.", crown:'life'},
      {label:"Longing for the day Christ returns and all is made right.", crown:'righteousness'},
      {label:"Watching someone I've poured into grow spiritually.", crown:'glory'},
      {label:"The quiet satisfaction of a disciplined, self-controlled life.", crown:'incorruptible'},
      {label:"The joy of seeing someone come to faith.", crown:'rejoicing'}
    ]},
    {text:"Given a free Saturday to serve, what would you choose?", options:[
      {label:"Sit with someone going through a hard season.", crown:'life'},
      {label:"Spend it in personal study, prayer, and reflection.", crown:'righteousness'},
      {label:"Lead or teach a group of younger believers.", crown:'glory'},
      {label:"Train — physically, mentally, spiritually — toward a goal.", crown:'incorruptible'},
      {label:"Share your testimony with a stranger or go serve outreach.", crown:'rejoicing'}
    ]},
    {text:"When you fail at something spiritually, what's true of you?", options:[
      {label:"I don't give up — I keep trusting and trying.", crown:'life'},
      {label:"I repent quickly and realign with what's right.", crown:'righteousness'},
      {label:"I let it make me more compassionate toward those I lead.", crown:'glory'},
      {label:"I analyze what habit broke down and rebuild it.", crown:'incorruptible'},
      {label:"I'm quick to tell others what God taught me through it.", crown:'rejoicing'}
    ]},
    {text:"Which phrase feels most like you?", options:[
      {label:"Steadfast", crown:'life'},
      {label:"Faithful to the end", crown:'righteousness'},
      {label:"A shepherd at heart", crown:'glory'},
      {label:"Disciplined", crown:'incorruptible'},
      {label:"A gospel messenger", crown:'rejoicing'}
    ]}
  ];

  var GIFTS = [
    {label:"Faith & perseverance under trial", crown:'life'},
    {label:"Intercession for the suffering", crown:'life'},
    {label:"Mercy toward the hurting", crown:'life'},
    {label:"Discernment of truth", crown:'righteousness'},
    {label:"Generosity & stewardship", crown:'righteousness'},
    {label:"Personal holiness & self-examination", crown:'righteousness'},
    {label:"Teaching", crown:'glory'},
    {label:"Leadership", crown:'glory'},
    {label:"Pastoring / shepherding", crown:'glory'},
    {label:"Hospitality", crown:'glory'},
    {label:"Self-control & fasting", crown:'incorruptible'},
    {label:"Wisdom applied to growth", crown:'incorruptible'},
    {label:"Diligence & consistency", crown:'incorruptible'},
    {label:"Evangelism", crown:'rejoicing'},
    {label:"Missions & outreach", crown:'rejoicing'},
    {label:"Encouragement (exhortation)", crown:'rejoicing'}
  ];

  /* ============ STATE ============ */
  var state = {
    answers:{},         // qIndex -> crownKey
    gifts:{},           // crownKey.label -> true (using label as key for simplicity we track selected labels)
    selectedGifts:[],   // array of crownKey
    texts:{goals:'', weak:'', strength:''}
  };
  var currentQ = 0;

  /* ============ RENDER: CROWN LISTS ============ */
  function renderCrownList(container){
    container.innerHTML = '';
    ORDER.forEach(function(key){
      var c = CROWNS[key];
      var card = document.createElement('div');
      card.className = 'crown-card';
      card.innerHTML =
        '<div class="crown-card-head">' +
          '<div style="color:'+c.accent+'">'+crownSVG(key)+'</div>' +
          '<div><p class="crown-card-name">'+c.name+'</p><p class="crown-card-ref">'+c.ref+'</p></div>' +
        '</div>' +
        '<p class="crown-card-verse">'+c.verse+'</p>' +
        '<p class="crown-card-summary">'+c.summary+'</p>';
      container.appendChild(card);
    });
  }

  /* ============ NAVIGATION ============ */
  function showScreen(id){
    document.querySelectorAll('.screen').forEach(function(s){ s.classList.remove('active'); });
    document.getElementById(id).classList.add('active');
    window.scrollTo(0,0);
  }

  /* ============ QUIZ RENDER ============ */
  function renderQuestion(){
    var q = QUESTIONS[currentQ];
    document.getElementById('progressText').textContent = 'Question ' + (currentQ+1) + ' of ' + QUESTIONS.length;
    document.getElementById('progressFill').style.width = (((currentQ)/(QUESTIONS.length-1))*100) + '%';
    document.getElementById('qText').textContent = q.text;
    var optWrap = document.getElementById('qOptions');
    optWrap.innerHTML = '';
    q.options.forEach(function(opt, i){
      var btn = document.createElement('button');
      btn.className = 'opt-btn' + (state.answers[currentQ] === opt.crown ? ' selected' : '');
      btn.textContent = opt.label;
      btn.addEventListener('click', function(){
        state.answers[currentQ] = opt.crown;
        renderQuestion();
      });
      optWrap.appendChild(btn);
    });
    document.getElementById('qNext').disabled = !state.answers.hasOwnProperty(currentQ);
    document.getElementById('qBack').style.visibility = currentQ === 0 ? 'hidden' : 'visible';
  }

  document.getElementById('qNext').addEventListener('click', function(){
    if(currentQ < QUESTIONS.length - 1){
      currentQ++;
      renderQuestion();
    } else {
      renderGifts();
      showScreen('screen-gifts');
    }
  });
  document.getElementById('qBack').addEventListener('click', function(){
    if(currentQ > 0){
      currentQ--;
      renderQuestion();
    } else {
      showScreen('screen-welcome');
    }
  });

  /* ============ GIFTS RENDER ============ */
  function renderGifts(){
    var grid = document.getElementById('giftGrid');
    grid.innerHTML = '';
    GIFTS.forEach(function(g, i){
      var pill = document.createElement('button');
      var isSel = state.selectedGifts.indexOf(i) !== -1;
      pill.className = 'gift-pill' + (isSel ? ' selected' : '');
      pill.textContent = g.label;
      pill.addEventListener('click', function(){
        var idx = state.selectedGifts.indexOf(i);
        if(idx === -1){ state.selectedGifts.push(i); } else { state.selectedGifts.splice(idx,1); }
        renderGifts();
      });
      grid.appendChild(pill);
    });
  }
  document.getElementById('giftsNext').addEventListener('click', function(){
    showScreen('screen-texts');
  });
  document.getElementById('giftsBack').addEventListener('click', function(){
    currentQ = QUESTIONS.length - 1;
    renderQuestion();
    showScreen('screen-quiz');
  });

  /* ============ TEXTS ============ */
  document.getElementById('textsBack').addEventListener('click', function(){
    showScreen('screen-gifts');
  });
  document.getElementById('textsNext').addEventListener('click', function(){
    state.texts.goals = document.getElementById('txtGoals').value.trim();
    state.texts.weak = document.getElementById('txtWeak').value.trim();
    state.texts.strength = document.getElementById('txtStrength').value.trim();
    computeAndShowResults();
  });

  /* ============ SCORING ============ */
  function countKeywordHits(text, crownKey){
    if(!text) return 0;
    var lower = text.toLowerCase();
    var hits = 0;
    CROWNS[crownKey].keywords.forEach(function(kw){
      if(lower.indexOf(kw) !== -1) hits++;
    });
    return Math.min(hits, 5);
  }

  function computeScores(){
    var scores = {life:0, righteousness:0, glory:0, incorruptible:0, rejoicing:0};
    Object.keys(state.answers).forEach(function(qi){
      scores[state.answers[qi]] += 3;
    });
    state.selectedGifts.forEach(function(i){
      scores[GIFTS[i].crown] += 2;
    });
    ['goals','weak','strength'].forEach(function(field){
      ORDER.forEach(function(key){
        scores[key] += countKeywordHits(state.texts[field], key);
      });
    });
    return scores;
  }

  function computeAndShowResults(){
    var scores = computeScores();
    var ranked = ORDER.slice().sort(function(a,b){ return scores[b]-scores[a]; });
    var top = ranked[0];
    var second = ranked[1];
    var topScore = scores[top] || 1;
    var isCloseSecond = scores[second] >= topScore * 0.8 && scores[second] > 0;

    var c = CROWNS[top];
    document.getElementById('resultCrownIcon').innerHTML = crownSVG(top, {animated:true});
    document.getElementById('resultCrownIcon').style.color = c.accent;
    document.getElementById('resName').textContent = c.name;
    document.getElementById('resRef').textContent = c.ref;
    document.getElementById('resVerse').textContent = c.verse;
    document.getElementById('resVerseRef').textContent = '— ' + c.verseRef;
    document.getElementById('resSummary').textContent = c.summary;

    var enc = c.encouragement;
    var reflectionSource = state.texts.strength || state.texts.goals || '';
    if(reflectionSource){
      var trimmed = reflectionSource.length > 90 ? reflectionSource.slice(0,90) + '…' : reflectionSource;
      enc = 'You wrote, "' + trimmed + '" — that isn\'t a coincidence. ' + enc;
    }
    document.getElementById('resEncouragement').textContent = enc;

    var stepsWrap = document.getElementById('resSteps');
    stepsWrap.innerHTML = '';
    c.steps.forEach(function(s){
      var li = document.createElement('li');
      li.textContent = s;
      stepsWrap.appendChild(li);
    });

    var secBlock = document.getElementById('secondaryBlock');
    if(isCloseSecond){
      var c2 = CROWNS[second];
      document.getElementById('secIcon').innerHTML = crownSVG(second);
      document.getElementById('secIcon').style.color = c2.accent;
      document.getElementById('secText').textContent =
        'Your answers also show real alignment with the ' + c2.name + ' (' + c2.ref + '). ' + c2.summary;
      secBlock.style.display = 'block';
    } else {
      secBlock.style.display = 'none';
    }

    showScreen('screen-results');
  }

  document.getElementById('restartBtn').addEventListener('click', function(){
    state = {answers:{}, gifts:{}, selectedGifts:[], texts:{goals:'',weak:'',strength:''}};
    currentQ = 0;
    document.getElementById('txtGoals').value = '';
    document.getElementById('txtWeak').value = '';
    document.getElementById('txtStrength').value = '';
    showScreen('screen-welcome');
  });

  /* ============ WELCOME / INFO NAV ============ */
  document.getElementById('startBtn').addEventListener('click', function(){
    currentQ = 0;
    renderQuestion();
    showScreen('screen-quiz');
  });
  document.getElementById('learnBtn').addEventListener('click', function(){
    renderCrownList(document.getElementById('crownsList'));
    showScreen('screen-crowns');
  });
  document.getElementById('toQuizFromInfo').addEventListener('click', function(){
    currentQ = 0;
    renderQuestion();
    showScreen('screen-quiz');
  });
  document.getElementById('backHomeFromInfo').addEventListener('click', function(){
    showScreen('screen-welcome');
  });

  document.getElementById('infoBtn').addEventListener('click', function(){
    renderCrownList(document.getElementById('modalCrownsList'));
    document.getElementById('modalOverlay').classList.add('active');
  });
  document.getElementById('modalClose').addEventListener('click', function(){
    document.getElementById('modalOverlay').classList.remove('active');
  });
  document.getElementById('modalOverlay').addEventListener('click', function(e){
    if(e.target === this) this.classList.remove('active');
  });

  /* ============ INIT ============ */
  document.getElementById('homeCrownIcon').innerHTML = crownSVG('rejoicing');
  renderQuestion();

})();
</script>
</body>
</html>
