# levelup.github.io[levelup_1.html](https://github.com/user-attachments/files/26428743/levelup_1.html)
<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
<meta charset="UTF-8"/>
<title>LEVELUP</title>
<meta name="viewport" content="width=device-width,initial-scale=1.0"/>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow:wght@400;600;700;800&display=swap" rel="stylesheet"/>
<style>
:root[data-theme="dark"]{
  --red:#e50914;--yellow:#ffcc00;--green:#1db954;--blue:#1e90ff;
  --bg:#0a0a0a;--card:#111;--card2:#181818;
  --muted:#777;--text:#fff;--border:#222;--input-bg:#0d0d0d;--sub:#161616;
}
:root[data-theme="light"]{
  --red:#c0000c;--yellow:#d4a000;--green:#15a045;--blue:#1070dd;
  --bg:#f0f0f0;--card:#fff;--card2:#fafafa;
  --muted:#666;--text:#111;--border:#ddd;--input-bg:#f5f5f5;--sub:#eee;
}
*{box-sizing:border-box;margin:0;padding:0}
body{background:var(--bg);color:var(--text);font-family:'Barlow',sans-serif;font-size:15px;transition:background .3s,color .3s}

/* GREETING BANNER */
#greetBanner{
  background:linear-gradient(90deg,#0d0000,#1a0000,#0d0000);
  border-bottom:1px solid rgba(229,9,20,.4);
  padding:9px 24px;display:flex;align-items:center;gap:12px;font-size:14px;
}
[data-theme="light"] #greetBanner{background:linear-gradient(90deg,#fff0f0,#ffe5e5,#fff0f0);border-bottom-color:rgba(192,0,12,.3)}
#greetText{font-weight:800;flex:1}
#greetQuote{color:var(--muted);font-style:italic;font-size:12px;display:none}
@media(min-width:600px){#greetQuote{display:block}}
.pulse-dot{width:8px;height:8px;border-radius:50%;background:var(--green);box-shadow:0 0 6px var(--green);animation:pulse 1.5s infinite;flex-shrink:0}
@keyframes pulse{0%,100%{opacity:1;transform:scale(1)}50%{opacity:.4;transform:scale(.7)}}

/* HEADER */
header{
  display:flex;align-items:center;justify-content:space-between;
  padding:12px 24px;border-bottom:2px solid var(--red);
  background:var(--card);position:sticky;top:0;z-index:100;
  box-shadow:0 2px 20px rgba(229,9,20,.1);
}
.logo{font-family:'Bebas Neue',sans-serif;font-size:30px;color:var(--red);letter-spacing:3px}
.header-right{display:flex;gap:7px;align-items:center;flex-wrap:wrap}
.hbtn{
  background:none;border:1px solid var(--border);border-radius:999px;
  color:var(--text);padding:6px 13px;cursor:pointer;font-family:'Barlow',sans-serif;
  font-weight:700;font-size:12px;white-space:nowrap;transition:all .2s;width:auto;margin-top:0;
}
.hbtn:hover{border-color:var(--red);color:var(--red);filter:none}
.hbtn.on{border-color:var(--green);color:var(--green);box-shadow:0 0 10px rgba(29,185,84,.35)}

/* TABS */
.tabs{display:flex;border-bottom:2px solid var(--border);background:var(--card);overflow-x:auto}
.tab{padding:11px 18px;cursor:pointer;font-weight:700;font-size:13px;border-bottom:3px solid transparent;white-space:nowrap;color:var(--muted);transition:color .2s}
.tab:hover{color:var(--text)}
.tab.active{color:var(--red);border-bottom-color:var(--red)}

.page{display:none;padding:20px 24px;max-width:1300px;margin:auto;animation:fadeIn .3s ease}
.page.active{display:block}
@keyframes fadeIn{from{opacity:0;transform:translateY(6px)}to{opacity:1;transform:none}}

/* CARDS */
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(230px,1fr));gap:14px}
.card{background:var(--card);border:1px solid var(--border);border-radius:14px;padding:16px;transition:border-color .3s}
.card h3{font-family:'Bebas Neue',sans-serif;font-size:19px;color:var(--red);margin-bottom:10px;letter-spacing:1px}
.kpi{font-size:28px;font-weight:800}
.muted{color:var(--muted);font-size:13px;margin-top:4px}

/* FORMS */
input,select,textarea{
  width:100%;padding:10px 12px;border-radius:10px;
  border:1px solid var(--border);background:var(--input-bg);
  color:var(--text);margin-top:8px;font-family:'Barlow',sans-serif;font-size:14px;outline:none;transition:border-color .2s;
}
input:focus,select:focus,textarea:focus{border-color:var(--red)}
textarea{resize:vertical;min-height:65px}
button{
  width:100%;padding:11px;border-radius:10px;border:none;
  background:var(--red);color:#fff;font-family:'Bebas Neue',sans-serif;
  font-size:17px;letter-spacing:1px;cursor:pointer;margin-top:10px;transition:filter .2s;
}
button:hover{filter:brightness(1.2)}
button.sec{background:var(--sub);border:1px solid var(--border);color:var(--text);font-family:'Barlow',sans-serif;font-size:13px;font-weight:700;letter-spacing:0}

/* BADGES */
.badge{display:inline-block;background:var(--yellow);color:#000;padding:3px 10px;border-radius:999px;font-weight:800;font-size:12px}
.badge.green{background:var(--green);color:#fff}
.badge.red{background:var(--red);color:#fff}
.badge.blue{background:var(--blue);color:#fff}

/* CALENDAR */
.cal-nav{display:flex;justify-content:space-between;align-items:center;margin-bottom:10px}
.cal-nav span{font-weight:800;font-size:15px}
.cal-nav-btns{display:flex;gap:6px}
.cal-nav-btns button{width:auto;padding:5px 14px;margin-top:0;font-size:13px;letter-spacing:0}
.cal-header{display:grid;grid-template-columns:repeat(7,1fr);gap:4px;margin-bottom:6px}
.cal-header span{text-align:center;font-size:11px;color:var(--muted);font-weight:700}
.calendar{display:grid;grid-template-columns:repeat(7,1fr);gap:5px}
.day{
  padding:8px 2px;border:1px solid var(--border);border-radius:8px;
  text-align:center;font-size:11px;font-weight:700;cursor:default;transition:all .3s;position:relative;min-height:44px;display:flex;flex-direction:column;align-items:center;justify-content:center;
}
.day.done{
  background:#1a0000;border-color:var(--red);color:var(--red);
  box-shadow:0 0 10px rgba(229,9,20,.5),inset 0 0 8px rgba(229,9,20,.1);
  animation:glow 2.5s ease-in-out infinite alternate;
}
.day.done::after{content:'🔥';position:absolute;top:-7px;right:-5px;font-size:10px}
.day.today{border-color:var(--yellow)!important;color:var(--yellow)!important;box-shadow:0 0 10px rgba(255,204,0,.4)!important}
.day.future{opacity:.25}
.day .d-sets{font-size:9px;color:inherit;opacity:.8;margin-top:1px}
@keyframes glow{from{box-shadow:0 0 6px rgba(229,9,20,.3)}to{box-shadow:0 0 18px rgba(229,9,20,.8)}}
.cal-legend{display:flex;gap:14px;margin-top:10px;flex-wrap:wrap}
.cal-legend span{font-size:12px;display:flex;align-items:center;gap:5px}
.leg-dot{width:12px;height:12px;border-radius:3px;display:inline-block}

/* DATA CHAIN */
.chain-scroll{display:flex;gap:0;overflow-x:auto;padding-bottom:8px;align-items:center}
.chain-day{
  border-radius:10px;border:1px solid var(--border);padding:10px 12px;
  min-width:110px;font-size:12px;cursor:pointer;transition:all .25s;flex-shrink:0;
}
.chain-day.has-data{border-color:var(--red);background:#140000}
.chain-day.chain-today{border-color:var(--yellow);background:#141000}
.chain-day:hover{transform:translateY(-3px);box-shadow:0 6px 16px rgba(0,0,0,.5)}
.chain-day .cd-date{font-weight:800;color:var(--red);font-size:10px;margin-bottom:2px}
.chain-day .cd-label{font-weight:800;font-size:12px}
.chain-day .cd-items{color:var(--muted);font-size:10px;margin-top:2px}
.chain-arrow{color:var(--red);font-size:16px;padding:0 4px;opacity:.5;flex-shrink:0;align-self:center}

/* PROGRESS */
.prog-bar{background:var(--sub);border-radius:999px;height:10px;margin-top:8px;overflow:hidden}
.prog-fill{height:100%;border-radius:999px;background:var(--red);transition:width .6s cubic-bezier(.4,0,.2,1)}
.prog-fill.green{background:var(--green)}
.prog-fill.yellow{background:var(--yellow)}
.prog-fill.blue{background:var(--blue)}

/* WATER */
.water-grid{display:flex;flex-wrap:wrap;gap:8px;margin-top:12px}
.cup{
  width:46px;height:46px;border-radius:10px;border:2px solid var(--border);
  background:var(--sub);cursor:pointer;display:flex;align-items:center;justify-content:center;
  font-size:22px;transition:all .25s;
}
.cup.filled{background:#001833;border-color:var(--blue);box-shadow:0 0 8px rgba(30,144,255,.35)}
.cup:hover{transform:scale(1.12)}

/* PR TABLE */
.pr-table{width:100%;border-collapse:collapse;margin-top:10px}
.pr-table th{background:var(--red);color:#fff;padding:8px 12px;text-align:left;font-size:13px}
.pr-table td{padding:8px 12px;border-bottom:1px solid var(--border);font-size:13px}
.pr-table tr:hover td{background:var(--sub)}
.pr-new{color:var(--yellow);font-weight:800}

/* AI CHAT */
.chat-wrap{background:var(--sub);border-radius:14px;border:1px solid var(--border);overflow:hidden}
.chat-box{height:370px;overflow-y:auto;padding:14px;display:flex;flex-direction:column;gap:10px}
.msg{max-width:82%;padding:10px 14px;border-radius:14px;font-size:14px;line-height:1.55;word-break:break-word}
.msg.user{background:var(--red);color:#fff;align-self:flex-end;border-bottom-right-radius:3px}
.msg.ai{background:var(--card2);color:var(--text);align-self:flex-start;border-bottom-left-radius:3px;border:1px solid var(--border)}
.chat-footer{padding:10px;border-top:1px solid var(--border);display:flex;gap:8px;align-items:center;background:var(--card)}
.chat-footer input{margin-top:0;flex:1}
.chat-footer button{width:auto;padding:10px 16px;margin-top:0;font-size:13px;letter-spacing:.3px;flex-shrink:0}
.mic-btn{
  width:42px!important;height:42px;border-radius:50%!important;
  background:var(--sub)!important;border:2px solid var(--border)!important;
  font-size:18px;padding:0!important;display:flex;align-items:center;justify-content:center;flex-shrink:0;
  transition:all .2s;
}
.mic-btn.rec{background:#1a0000!important;border-color:var(--red)!important;animation:recPulse 1s infinite}
@keyframes recPulse{0%,100%{box-shadow:0 0 6px rgba(229,9,20,.4)}50%{box-shadow:0 0 18px rgba(229,9,20,.9)}}
.typing{color:var(--muted);font-size:13px;font-style:italic}

/* NOTES */
.note-item{background:var(--sub);border-radius:10px;padding:12px;border-left:3px solid var(--red);margin-top:10px}
.note-item .note-meta{font-size:12px;color:var(--muted);margin-bottom:4px}
.note-item .note-muscle{font-weight:700;color:var(--yellow)}

/* TOAST */
#toast{
  position:fixed;bottom:24px;right:24px;
  background:var(--red);color:#fff;
  padding:14px 20px;border-radius:14px;font-weight:700;font-size:14px;
  z-index:9999;display:none;animation:slideUp .4s ease;
  box-shadow:0 4px 24px rgba(229,9,20,.5);max-width:300px;line-height:1.4;
}
@keyframes slideUp{from{transform:translateY(20px);opacity:0}to{transform:none;opacity:1}}
#toast .close-toast{float:right;cursor:pointer;margin-left:10px;opacity:.8}

/* NAME MODAL */
#nameModal{position:fixed;inset:0;background:rgba(0,0,0,.9);z-index:9999;display:flex;align-items:center;justify-content:center}
.modal-box{background:var(--card);border:2px solid var(--red);border-radius:20px;padding:36px;max-width:380px;width:90%;text-align:center;box-shadow:0 0 40px rgba(229,9,20,.3)}
.modal-box .ico{font-size:56px;margin-bottom:8px}
.modal-box h2{font-family:'Bebas Neue',sans-serif;font-size:32px;color:var(--red);letter-spacing:2px}
.modal-box p{color:var(--muted);margin:6px 0 16px;font-size:14px}

canvas{border-radius:10px;width:100%!important}
.section-title{font-family:'Bebas Neue',sans-serif;font-size:21px;color:var(--red);letter-spacing:1px;margin:18px 0 10px}
footer{padding:16px;text-align:center;color:var(--muted);font-size:12px;border-top:1px solid var(--border);margin-top:20px}
@media(max-width:600px){.page{padding:12px}.logo{font-size:24px}.tab{padding:10px 12px;font-size:12px}}

/* ── WORKOUT PLANNER ── */
.split-day{
  background:var(--sub);border:1px solid var(--border);border-radius:12px;
  margin-bottom:12px;overflow:hidden;transition:border-color .2s;
}
.split-day:hover{border-color:var(--red)}
.split-day-header{
  display:flex;align-items:center;justify-content:space-between;
  padding:12px 16px;background:var(--card2);cursor:pointer;
  border-bottom:1px solid var(--border);
}
.split-day-header .day-name{font-family:'Bebas Neue',sans-serif;font-size:18px;letter-spacing:1px;color:var(--red)}
.split-day-header .day-focus{color:var(--yellow);font-weight:700;font-size:13px}
.split-day-header .day-badge{font-size:11px;padding:3px 10px;border-radius:999px}
.exercise-table{width:100%;border-collapse:collapse;font-size:13px}
.exercise-table th{background:rgba(229,9,20,.12);color:var(--red);padding:8px 12px;text-align:left;font-size:12px;font-weight:700}
.exercise-table td{padding:9px 12px;border-bottom:1px solid var(--border);vertical-align:middle}
.exercise-table tr:last-child td{border-bottom:none}
.exercise-table tr:hover td{background:rgba(255,255,255,.03)}
.intensity-pill{
  display:inline-block;padding:2px 10px;border-radius:999px;font-size:11px;font-weight:800;
}
.intensity-pill.beginner{background:#003300;color:#1db954}
.intensity-pill.intermediate{background:#2a1a00;color:#ffcc00}
.intensity-pill.advanced{background:#1a0000;color:#e50914}
.planner-profile{display:grid;grid-template-columns:repeat(auto-fit,minmax(160px,1fr));gap:10px;margin-bottom:16px}
.plan-stat{background:var(--sub);border:1px solid var(--border);border-radius:10px;padding:12px;text-align:center}
.plan-stat .ps-val{font-size:20px;font-weight:800;color:var(--red)}
.plan-stat .ps-label{font-size:11px;color:var(--muted);margin-top:3px}
.split-input-area{background:var(--sub);border:1px solid var(--border);border-radius:12px;padding:16px;margin-bottom:14px}
.split-input-area h4{font-family:'Bebas Neue',sans-serif;font-size:16px;color:var(--yellow);margin-bottom:8px;letter-spacing:.5px}
.rest-badge{color:var(--muted);font-style:italic;font-size:13px}
.profile-form-row{display:grid;grid-template-columns:1fr 1fr;gap:10px}
@media(max-width:480px){.profile-form-row{grid-template-columns:1fr}}

/* ── HOME WORKOUT ── */
.hw-gender-tabs{display:flex;gap:10px;margin-bottom:18px}
.hw-gtab{
  flex:1;padding:14px;border-radius:12px;border:2px solid var(--border);
  text-align:center;cursor:pointer;font-weight:800;font-size:15px;transition:all .25s;
}
.hw-gtab.male.active{border-color:#1e90ff;background:#001833;color:#1e90ff;box-shadow:0 0 14px rgba(30,144,255,.3)}
.hw-gtab.female.active{border-color:#ff69b4;background:#1a0010;color:#ff69b4;box-shadow:0 0 14px rgba(255,105,180,.3)}
.hw-gtab:not(.active){color:var(--muted)}
.hw-week{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:14px;margin-top:16px}
.hw-day-card{
  background:var(--card);border:1px solid var(--border);border-radius:14px;overflow:hidden;transition:border-color .2s;
}
.hw-day-card:hover{border-color:var(--red)}
.hw-day-header{
  padding:12px 16px;display:flex;justify-content:space-between;align-items:center;
  cursor:pointer;border-bottom:1px solid var(--border);
}
.hw-day-header.rest-hdr{background:var(--sub)}
.hw-day-title{font-family:'Bebas Neue',sans-serif;font-size:17px;letter-spacing:1px}
.hw-day-focus{font-size:12px;font-weight:700}
.hw-ex-list{padding:0}
.hw-ex{display:flex;align-items:center;gap:10px;padding:10px 14px;border-bottom:1px solid var(--border);font-size:13px}
.hw-ex:last-child{border-bottom:none}
.hw-ex-num{width:22px;height:22px;border-radius:50%;background:var(--red);color:#fff;font-size:10px;font-weight:800;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.hw-ex-num.female{background:#ff69b4}
.hw-ex-info{flex:1}
.hw-ex-name{font-weight:700}
.hw-ex-detail{font-size:11px;color:var(--muted);margin-top:2px}
.hw-ex-sets{font-size:12px;font-weight:800;color:var(--yellow);text-align:right;flex-shrink:0}
.hw-tip{background:var(--sub);border-left:3px solid var(--green);padding:10px 14px;font-size:12px;color:var(--muted);line-height:1.6}
.hw-tip b{color:var(--green)}
.level-tabs{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:14px}
.level-tab{
  padding:7px 16px;border-radius:999px;border:1px solid var(--border);
  cursor:pointer;font-size:13px;font-weight:700;color:var(--muted);transition:all .2s;
}
.level-tab.active{background:var(--red);border-color:var(--red);color:#fff}
.goal-tabs{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:16px}
.goal-tab{
  padding:7px 18px;border-radius:999px;border:1px solid var(--border);
  cursor:pointer;font-size:13px;font-weight:700;color:var(--muted);transition:all .2s;
}
.goal-tab.active{background:var(--yellow);border-color:var(--yellow);color:#000}
.hw-hero{
  background:linear-gradient(135deg,#0d0000,#1a0000);
  border:1px solid var(--red);border-radius:14px;padding:20px;margin-bottom:18px;
  display:flex;align-items:center;gap:16px;flex-wrap:wrap;
}
.hw-hero-icon{font-size:48px}
.hw-hero-text h2{font-family:'Bebas Neue',sans-serif;font-size:26px;color:var(--red);letter-spacing:2px}
.hw-hero-text p{color:var(--muted);font-size:13px;margin-top:4px}
[data-theme="light"] .hw-hero{background:linear-gradient(135deg,#fff0f0,#ffe5e5)}
</style>
</head>
<body>

<!-- NAME MODAL -->
<div id="nameModal">
  <div class="modal-box">
    <div class="ico">⚡</div>
    <h2>Welcome to LEVELUP</h2>
    <p>Your personal fitness JARVIS — AI Coach, Tracker & Motivator</p>
    <input id="nameInput" type="text" placeholder="What's your name, Champion?" style="text-align:center;font-size:16px;font-weight:700"/>
    <button onclick="saveName()">LET'S GO 🚀</button>
  </div>
</div>

<!-- GREETING BANNER -->
<div id="greetBanner">
  <div class="pulse-dot"></div>
  <div id="greetText" style="font-weight:800">Welcome, Champion</div>
  <div id="greetQuote" style="margin-left:auto">"The pain you feel today is the strength you feel tomorrow."</div>
</div>

<!-- HEADER -->
<header>
  <div class="logo">⚡ LEVELUP</div>
  <div class="header-right">
    <button class="hbtn" id="voiceBtn" onclick="toggleVoice()">🎙️ Voice Off</button>
    <button class="hbtn" onclick="requestReminder()">🔔 Reminders</button>
    <button class="hbtn" onclick="toggleTheme()">🌓 Theme</button>
  </div>
</header>

<!-- TABS -->
<div class="tabs">
  <div class="tab active" onclick="showTab('dashboard',this)">📊 Dashboard</div>
  <div class="tab" onclick="showTab('log',this)">🏋️ Log</div>
  <div class="tab" onclick="showTab('chain',this)">🔗 Chain</div>
  <div class="tab" onclick="showTab('ai',this)">🤖 AI Coach</div>
  <div class="tab" onclick="showTab('water',this)">💧 Water</div>
  <div class="tab" onclick="showTab('prs',this)">🏆 PRs</div>
  <div class="tab" onclick="showTab('body',this)">🧮 Body</div>
  <div class="tab" onclick="showTab('charts',this)">📈 Progress</div>
  <div class="tab" onclick="showTab('planner',this)">📋 Planner</div>
  <div class="tab" onclick="showTab('home',this)">🏠 Home Workout</div>
</div>

<!-- DASHBOARD -->
<div id="tab-dashboard" class="page active">
  <div class="grid">
    <div class="card"><h3>🔥 Streak</h3><div id="streak" class="kpi">0 days</div><div class="muted">Consecutive gym days</div></div>
    <div class="card"><h3>📅 Weekly</h3><div id="weekly" class="kpi">0 / 4</div><div class="muted">Workouts this week</div></div>
    <div class="card"><h3>✅ Today</h3><div id="todayStatus" class="kpi">Not logged</div><div class="muted">Today's workout status</div></div>
    <div class="card"><h3>💧 Water</h3><div id="waterKpi" class="kpi">0 / 8</div><div class="muted">Glasses today</div></div>
  </div>
  <div class="section-title">📆 Gym Calendar</div>
  <div class="card">
    <div class="cal-nav">
      <span id="calMonthLabel"></span>
      <div class="cal-nav-btns">
        <button class="sec" onclick="changeCalMonth(-1)">◀ Prev</button>
        <button class="sec" onclick="changeCalMonth(0)">Today</button>
        <button class="sec" onclick="changeCalMonth(1)">Next ▶</button>
      </div>
    </div>
    <div class="cal-header"><span>Sun</span><span>Mon</span><span>Tue</span><span>Wed</span><span>Thu</span><span>Fri</span><span>Sat</span></div>
    <div id="calendar" class="calendar"></div>
    <div class="cal-legend">
      <span><span class="leg-dot" style="background:var(--red)"></span>Workout done 🔥</span>
      <span><span class="leg-dot" style="border:2px solid var(--yellow)"></span>Today</span>
      <span><span class="leg-dot" style="border:1px solid var(--border);opacity:.4"></span>Future</span>
    </div>
  </div>
</div>

<!-- LOG -->
<div id="tab-log" class="page">
  <div class="grid">
    <div class="card">
      <h3>Log Workout</h3>
      <select id="muscle"><option>Chest</option><option>Back</option><option>Legs</option><option>Arms</option><option>Shoulder</option></select>
      <input id="weight" type="number" placeholder="Top set weight (kg)"/>
      <input id="reps" type="number" placeholder="Reps"/>
      <input id="sets" type="number" placeholder="Sets"/>
      <textarea id="wNotes" placeholder="Workout notes (optional)…"></textarea>
      <button onclick="logWorkout()">SAVE WORKOUT</button>
      <div id="logMsg" style="margin-top:8px"></div>
    </div>
    <div class="card"><h3>Today's Log</h3><div id="todayLog"></div></div>
  </div>
  <div class="section-title">📝 Notes History</div>
  <div id="notesHistory"></div>
</div>

<!-- DATA CHAIN -->
<div id="tab-chain" class="page">
  <div class="card">
    <h3>🔗 Live Data Chain</h3>
    <div class="muted" style="margin-bottom:14px">Every day you save builds a permanent link in your chain — growing day by day, forever! Click any day to see details.</div>
    <div class="chain-scroll" id="chainContainer"></div>
  </div>
  <div class="grid" style="margin-top:14px" id="chainStats"></div>
  <div class="section-title" id="dayDetailTitle" style="display:none">📋 Day Detail</div>
  <div class="card" id="dayDetail" style="display:none"></div>
</div>

<!-- AI COACH -->
<div id="tab-ai" class="page">
  <div style="max-width:820px;margin:auto">
    <div class="card" style="margin-bottom:12px">
      <h3>🤖 LEVELUP AI Coach</h3>
      <div class="muted">Your personal Indian Fitness JARVIS — food tracker, workout planner & daily motivator!</div>
    </div>
    <div class="chat-wrap">
      <div class="chat-box" id="chatBox"></div>
      <div class="chat-footer">
        <button class="mic-btn" id="micBtn" onclick="toggleVoiceChat()" title="Voice Input">🎙️</button>
        <input id="chatInput" type="text" placeholder="Ask anything… or tap 🎙️ to speak" onkeydown="if(event.key==='Enter')sendChat()"/>
        <button onclick="sendChat()">SEND ➤</button>
      </div>
    </div>
    <div id="voiceStatus" style="font-size:12px;color:var(--muted);margin-top:6px;min-height:18px;padding:0 2px"></div>
  </div>
</div>

<!-- WATER -->
<div id="tab-water" class="page">
  <div class="grid">
    <div class="card">
      <h3>💧 Water Tracker</h3>
      <div class="kpi" id="waterCount">0 / 8</div>
      <div class="muted">Goal: 8 glasses (2L) — aim 3–4L on workout days</div>
      <div class="prog-bar"><div class="prog-fill blue" id="waterBar" style="width:0%"></div></div>
      <div class="water-grid" id="waterGrid"></div>
      <button class="sec" onclick="resetWater()" style="margin-top:14px">↺ Reset Today</button>
    </div>
    <div class="card"><h3>📊 7-Day Hydration</h3><canvas id="waterChart"></canvas></div>
  </div>
</div>

<!-- PRs -->
<div id="tab-prs" class="page">
  <div class="grid">
    <div class="card">
      <h3>🏆 Personal Records</h3>
      <table class="pr-table"><thead><tr><th>Muscle</th><th>PR (kg)</th><th>Reps</th><th>Date</th></tr></thead><tbody id="prBody"></tbody></table>
    </div>
    <div class="card">
      <h3>Set New PR</h3>
      <select id="prMuscle"><option>Chest</option><option>Back</option><option>Legs</option><option>Arms</option><option>Shoulder</option></select>
      <input id="prWeight" type="number" placeholder="Weight (kg)"/>
      <input id="prReps" type="number" placeholder="Reps"/>
      <button onclick="savePR()">SAVE PR</button>
      <div id="prMsg" style="margin-top:8px"></div>
    </div>
  </div>
</div>

<!-- BODY -->
<div id="tab-body" class="page">
  <div class="grid">
    <div class="card">
      <h3>🧮 BMI Calculator</h3>
      <input id="heightCm" type="number" placeholder="Height (cm)"/>
      <input id="bodyWeightKg" type="number" placeholder="Weight (kg)"/>
      <select id="goalType"><option value="loss">Weight Loss</option><option value="maintain">Maintain</option><option value="gain">Weight Gain</option></select>
      <button onclick="calcBMI()">CALCULATE</button>
      <div id="bmiResult" class="muted" style="margin-top:12px;font-size:14px;line-height:2"></div>
    </div>
    <div class="card">
      <h3>🥗 Daily Targets</h3>
      <div id="proteinNeed" class="kpi">—</div><div class="muted">Protein / day</div>
      <div id="carbNeed" class="kpi" style="margin-top:12px">—</div><div class="muted">Carbs / day</div>
      <div id="calNeed" class="kpi" style="margin-top:12px">—</div><div class="muted">Calories / day</div>
      <div id="calorieHint" class="muted" style="margin-top:12px;font-size:14px"></div>
    </div>
  </div>
</div>

<!-- CHARTS -->
<div id="tab-charts" class="page">
  <div class="grid">
    <div class="card"><h3>Chest</h3><canvas id="chestChart"></canvas></div>
    <div class="card"><h3>Back</h3><canvas id="backChart"></canvas></div>
    <div class="card"><h3>Legs</h3><canvas id="legsChart"></canvas></div>
    <div class="card"><h3>Arms</h3><canvas id="armsChart"></canvas></div>
    <div class="card"><h3>Shoulder</h3><canvas id="shoulderChart"></canvas></div>
  </div>
</div>

<!-- HOME WORKOUT -->
<div id="tab-home" class="page">

  <div class="hw-hero">
    <div class="hw-hero-icon">🏠</div>
    <div class="hw-hero-text">
      <h2>Home Workout Plans</h2>
      <p>Zero equipment needed — full bodyweight plans for Male & Female · Beginner to Advanced · All goals</p>
    </div>
  </div>

  <!-- Gender Select -->
  <div class="hw-gender-tabs">
    <div class="hw-gtab male active" id="hw-male-tab" onclick="switchHWGender('male')">♂ Male Plans</div>
    <div class="hw-gtab female" id="hw-female-tab" onclick="switchHWGender('female')">♀ Female Plans</div>
  </div>

  <!-- Level Tabs -->
  <div class="level-tabs">
    <div class="level-tab active" onclick="switchHWLevel('beginner',this)">🟢 Beginner</div>
    <div class="level-tab" onclick="switchHWLevel('intermediate',this)">🟡 Intermediate</div>
    <div class="level-tab" onclick="switchHWLevel('advanced',this)">🔴 Advanced</div>
  </div>

  <!-- Goal Tabs -->
  <div class="goal-tabs">
    <div class="goal-tab active" onclick="switchHWGoal('loss',this)">🔥 Fat Loss</div>
    <div class="goal-tab" onclick="switchHWGoal('muscle',this)">💪 Muscle Gain</div>
    <div class="goal-tab" onclick="switchHWGoal('gain',this)">⚖️ Weight Gain</div>
  </div>

  <!-- Plan Output -->
  <div id="hwPlanContainer"></div>

</div>

<!-- WORKOUT PLANNER -->
<div id="tab-planner" class="page">

  <!-- Profile Setup -->
  <div class="card" id="plannerSetupCard">
    <h3>📋 Workout Planner — Setup Your Profile</h3>
    <div class="muted" style="margin-bottom:14px">Enter your details so the AI can build a fully personalised plan with correct protein targets, sets, reps & intensity based on your age and gender.</div>
    <div class="profile-form-row">
      <div>
        <label style="font-size:12px;color:var(--muted);font-weight:700">AGE</label>
        <input id="planAge" type="number" placeholder="e.g. 24" min="10" max="80"/>
      </div>
      <div>
        <label style="font-size:12px;color:var(--muted);font-weight:700">GENDER</label>
        <select id="planGender">
          <option value="male">Male</option>
          <option value="female">Female</option>
        </select>
      </div>
      <div>
        <label style="font-size:12px;color:var(--muted);font-weight:700">WEIGHT (kg)</label>
        <input id="planWeight" type="number" placeholder="e.g. 70"/>
      </div>
      <div>
        <label style="font-size:12px;color:var(--muted);font-weight:700">GOAL</label>
        <select id="planGoal">
          <option value="loss">Fat Loss</option>
          <option value="muscle">Muscle Gain</option>
          <option value="gain">Weight Gain</option>
        </select>
      </div>
      <div>
        <label style="font-size:12px;color:var(--muted);font-weight:700">EXPERIENCE LEVEL</label>
        <select id="planLevel">
          <option value="beginner">Beginner (0–1 yr)</option>
          <option value="intermediate">Intermediate (1–3 yrs)</option>
          <option value="advanced">Advanced (3+ yrs)</option>
        </select>
      </div>
      <div>
        <label style="font-size:12px;color:var(--muted);font-weight:700">WORKOUT DAYS / WEEK</label>
        <select id="planDays">
          <option value="3">3 days</option>
          <option value="4">4 days</option>
          <option value="5">5 days</option>
          <option value="6">6 days</option>
        </select>
      </div>
    </div>

    <div class="split-input-area" style="margin-top:14px">
      <h4>✍️ YOUR WEEKLY SPLIT (Optional — or let AI generate)</h4>
      <div class="muted" style="margin-bottom:8px">Type your own split below, or leave blank and press Generate for an AI plan.</div>
      <textarea id="planSplitInput" style="min-height:110px" placeholder="Example:&#10;Monday – Chest&#10;Tuesday – Back&#10;Wednesday – Legs&#10;Thursday – Shoulders&#10;Friday – Arms&#10;Saturday – Full Body&#10;Sunday – Rest"></textarea>
    </div>

    <div style="display:flex;gap:10px;flex-wrap:wrap">
      <button onclick="generatePlan()" style="flex:1">⚡ GENERATE MY PLAN</button>
      <button onclick="clearPlan()" class="sec" style="flex:0 0 auto;padding:11px 20px">↺ Reset</button>
    </div>
    <div id="planMsg" style="margin-top:8px"></div>
  </div>

  <!-- Plan Output -->
  <div id="planOutput" style="display:none;margin-top:16px">

    <!-- Stats Row -->
    <div id="plannerStats" class="planner-profile"></div>

    <!-- Split Cards -->
    <div class="section-title">🗓️ YOUR PERSONALISED WEEKLY SPLIT</div>
    <div id="splitCards"></div>

    <!-- Protein Guide -->
    <div class="section-title">🥗 PROTEIN & NUTRITION GUIDE</div>
    <div id="nutritionGuide" class="card"></div>

    <button onclick="window.print()" class="sec" style="margin-top:14px;max-width:200px">🖨️ Print / Save Plan</button>
  </div>
</div>

<!-- TOAST -->
<div id="toast"><span id="toastMsg">Time to train!</span> <span class="close-toast" onclick="closeToast()">✕</span></div>

<footer>LEVELUP ⚡ Your data is permanent • Every day adds a new link to your chain</footer>

<script>
// ════════════════════════════════
// STATE
// ════════════════════════════════
let data     = JSON.parse(localStorage.getItem('lvData'))    || {};
let profile  = JSON.parse(localStorage.getItem('lvProfile')) || {};
let prs      = JSON.parse(localStorage.getItem('lvPRs'))     || {};
let water    = JSON.parse(localStorage.getItem('lvWater'))   || {};
let chatHist = JSON.parse(localStorage.getItem('lvChat'))    || [];
let userName = localStorage.getItem('lvName') || '';
const today  = new Date().toISOString().slice(0,10);
let calOffset = 0;
let voiceOn   = false;
let isRecording = false;
let recog = null;

// ════════════════════════════════
// NAME & GREETING
// ════════════════════════════════
const QUOTES = [
  '"The pain you feel today is the strength you feel tomorrow." 💪',
  '"Success starts with self-discipline." 🔥',
  '"No excuses. No shortcuts. Just results." ⚡',
  '"Every rep counts. Every day matters." 🏋️',
  '"Champions are made when no one is watching." 🏆',
  '"Your body can do it. Convince your mind." 🧠',
  '"Be stronger than your strongest excuse." 💯',
  '"Train insane or remain the same." 🚀',
  '"Small daily improvements lead to stunning results." 📈',
];

function saveName(){
  const n = document.getElementById('nameInput').value.trim();
  if(!n){ alert('Please enter your name!'); return; }
  userName = n;
  localStorage.setItem('lvName', n);
  document.getElementById('nameModal').style.display = 'none';
  setGreeting();
}

function setGreeting(){
  if(!userName) return;
  const h = new Date().getHours();
  const g = h<12 ? 'Good morning ☀️' : h<17 ? 'Good afternoon 🌤️' : 'Good evening 🌙';
  document.getElementById('greetText').textContent = `${g}, ${userName}! Let's crush it today.`;
  document.getElementById('greetQuote').textContent = QUOTES[Math.floor(Math.random()*QUOTES.length)];
}

if(!userName){
  document.getElementById('nameModal').style.display = 'flex';
} else {
  document.getElementById('nameModal').style.display = 'none';
  setGreeting();
}

// ════════════════════════════════
// THEME
// ════════════════════════════════
function toggleTheme(){
  const html = document.documentElement;
  html.dataset.theme = html.dataset.theme === 'dark' ? 'light' : 'dark';
  localStorage.setItem('lvTheme', html.dataset.theme);
}
const savedTheme = localStorage.getItem('lvTheme');
if(savedTheme) document.documentElement.dataset.theme = savedTheme;

// ════════════════════════════════
// TABS
// ════════════════════════════════
function showTab(t, el){
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.tab').forEach(b => b.classList.remove('active'));
  document.getElementById('tab-'+t).classList.add('active');
  if(el) el.classList.add('active');
  if(t === 'charts') renderAllCharts();
  if(t === 'water')  renderWaterChart();
  if(t === 'chain')  renderChain();
  if(t === 'home')   renderHWPlan();
}

// ════════════════════════════════
// WORKOUT LOG
// ════════════════════════════════
function logWorkout(){
  const muscle = document.getElementById('muscle').value;
  const wt     = +document.getElementById('weight').value;
  const reps   = +document.getElementById('reps').value || 0;
  const sets   = +document.getElementById('sets').value || 0;
  const notes  = document.getElementById('wNotes').value.trim();
  if(!wt){ alert('Enter weight'); return; }
  if(!data[today]) data[today] = [];
  data[today].push({ muscle, weight:wt, reps, sets, notes, time: new Date().toLocaleTimeString() });
  let prBadge = '';
  if(!prs[muscle] || wt > prs[muscle].weight){
    prBadge = prs[muscle] ? ' 🏆 NEW PR!' : '';
    prs[muscle] = { weight:wt, reps, date:today };
    localStorage.setItem('lvPRs', JSON.stringify(prs));
  }
  localStorage.setItem('lvData', JSON.stringify(data));
  document.getElementById('weight').value = '';
  document.getElementById('reps').value   = '';
  document.getElementById('sets').value   = '';
  document.getElementById('wNotes').value = '';
  document.getElementById('logMsg').innerHTML = `<span class="badge green">Saved ✔${prBadge}</span>`;
  if(voiceOn) speak(`${muscle} workout saved. Great job ${userName}!`);
  renderAll();
}

// ════════════════════════════════
// CALENDAR
// ════════════════════════════════
const MONTHS = ['January','February','March','April','May','June','July','August','September','October','November','December'];

function changeCalMonth(dir){
  if(dir === 0) calOffset = 0;
  else calOffset += dir;
  renderCalendar();
}

function renderCalendar(){
  const cal = document.getElementById('calendar');
  cal.innerHTML = '';
  const now  = new Date();
  const base = new Date(now.getFullYear(), now.getMonth() + calOffset, 1);
  const y = base.getFullYear(), m = base.getMonth();
  document.getElementById('calMonthLabel').textContent = MONTHS[m] + ' ' + y;
  const firstDay = new Date(y, m, 1).getDay();
  const daysInMonth = new Date(y, m+1, 0).getDate();
  const todayFull   = new Date().toISOString().slice(0,10);

  // blank slots
  for(let i = 0; i < firstDay; i++){
    const blank = document.createElement('div');
    blank.className = 'day';
    blank.style.visibility = 'hidden';
    cal.appendChild(blank);
  }

  for(let i = 1; i <= daysInMonth; i++){
    const d    = new Date(y, m, i).toISOString().slice(0,10);
    const done = !!data[d];
    const isT  = d === todayFull;
    const isFut = d > todayFull;
    const div  = document.createElement('div');
    let cls    = 'day';
    if(done)  cls += ' done';
    if(isT)   cls += ' today';
    if(isFut && !done) cls += ' future';
    div.className = cls;
    const setsCount = done ? data[d].length : 0;
    div.innerHTML   = `<div>${i}</div>${done ? `<div class="d-sets">${setsCount}x</div>` : ''}`;
    if(done) div.title = data[d].map(e => e.muscle).join(', ');
    cal.appendChild(div);
  }
}

// ════════════════════════════════
// DATA CHAIN
// ════════════════════════════════
function renderChain(){
  const container = document.getElementById('chainContainer');
  const statsEl   = document.getElementById('chainStats');
  container.innerHTML = '';
  statsEl.innerHTML   = '';

  const allDays = Object.keys(data).sort();
  if(!allDays.length){
    container.innerHTML = '<div class="muted" style="padding:10px">No workouts logged yet. Save your first session and it will appear here as Link 1!</div>';
    return;
  }

  allDays.forEach((d, i) => {
    if(i > 0){
      const arr = document.createElement('div');
      arr.className = 'chain-arrow';
      arr.textContent = '→';
      container.appendChild(arr);
    }
    const entries  = data[d];
    const muscles  = [...new Set(entries.map(e => e.muscle))];
    const isToday  = d === today;
    const div      = document.createElement('div');
    div.className  = 'chain-day' + (isToday ? ' chain-today' : ' has-data');
    div.innerHTML  = `
      <div class="cd-date">${d.slice(5)}</div>
      <div class="cd-label" style="color:${isToday?'var(--yellow)':'var(--red)'}">
        ${isToday ? '⚡ TODAY' : 'Link '+(i+1)}
      </div>
      <div class="cd-items">${muscles.join(', ')}</div>
      <div style="font-size:10px;color:var(--muted);margin-top:3px">${entries.length} set${entries.length>1?'s':''}</div>`;
    div.onclick = () => showDayDetail(d);
    container.appendChild(div);
  });

  // Stats cards
  const total = allDays.length;
  const muscleCounts = {};
  allDays.forEach(d => data[d].forEach(e => { muscleCounts[e.muscle] = (muscleCounts[e.muscle]||0)+1; }));
  const topMuscle = Object.entries(muscleCounts).sort((a,b) => b[1]-a[1])[0];
  const lastDay   = allDays[allDays.length-1];
  statsEl.innerHTML = `
    <div class="card"><h3>🗓️ Total Days</h3><div class="kpi">${total}</div><div class="muted">All-time workout days logged</div></div>
    <div class="card"><h3>🏋️ Favourite</h3><div class="kpi">${topMuscle?topMuscle[0]:'—'}</div><div class="muted">${topMuscle?topMuscle[1]+' sessions':''}</div></div>
    <div class="card"><h3>🔗 Chain Length</h3><div class="kpi">${total} links</div><div class="muted">Last: ${lastDay}</div></div>`;
}

function showDayDetail(d){
  const el    = document.getElementById('dayDetail');
  const title = document.getElementById('dayDetailTitle');
  el.style.display    = 'block';
  title.style.display = 'block';
  const entries = data[d];
  el.innerHTML = `
    <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:12px">
      <h3 style="color:var(--yellow)">${d} — ${entries.length} set${entries.length>1?'s':''}</h3>
      <button class="sec hbtn" onclick="document.getElementById('dayDetail').style.display='none';document.getElementById('dayDetailTitle').style.display='none'">✕ Close</button>
    </div>
    ${entries.map(e => `
      <div style="padding:10px;border-bottom:1px solid var(--border);display:flex;flex-wrap:wrap;gap:10px;align-items:center">
        <span style="color:var(--red);font-weight:800;min-width:80px">${e.muscle}</span>
        <span style="color:var(--yellow);font-weight:700">${e.weight}kg</span>
        ${e.reps ? `<span class="muted">× ${e.reps} reps</span>` : ''}
        ${e.sets ? `<span class="muted">× ${e.sets} sets</span>` : ''}
        ${e.notes ? `<span class="muted">💬 ${e.notes}</span>` : ''}
        <span class="muted" style="margin-left:auto">${e.time||''}</span>
      </div>`).join('')}`;
  el.scrollIntoView({ behavior:'smooth', block:'nearest' });
}

// ════════════════════════════════
// STREAK / WEEKLY
// ════════════════════════════════
function calcStreak(){
  let s = 0;
  for(let i = 0; i < 365; i++){
    const d = new Date(); d.setDate(d.getDate()-i);
    if(data[d.toISOString().slice(0,10)]) s++; else break;
  }
  document.getElementById('streak').textContent = s + ' days';
}
function calcWeekly(){
  let c = 0;
  Object.keys(data).forEach(d => { if((new Date()-new Date(d))/86400000 <= 7) c++; });
  document.getElementById('weekly').textContent = c + ' / 4';
}

// ════════════════════════════════
// TODAY LOG & NOTES
// ════════════════════════════════
function renderTodayLog(){
  const el      = document.getElementById('todayLog');
  const entries = data[today] || [];
  if(!entries.length){ el.innerHTML = '<div class="muted">No workouts yet today.</div>'; return; }
  el.innerHTML  = entries.map(e => `
    <div style="padding:10px;border-bottom:1px solid var(--border)">
      <b style="color:var(--red)">${e.muscle}</b>
      <span style="color:var(--yellow);margin-left:8px">${e.weight}kg</span>
      ${e.reps ? ` × ${e.reps} reps` : ''}
      ${e.sets ? ` × ${e.sets} sets` : ''}
      <span style="float:right;color:var(--muted);font-size:12px">${e.time||''}</span>
      ${e.notes ? `<div style="font-size:12px;color:var(--muted);margin-top:3px">💬 ${e.notes}</div>` : ''}
    </div>`).join('');
}

function renderNotesHistory(){
  const el   = document.getElementById('notesHistory');
  const all  = [];
  Object.keys(data).sort().reverse().forEach(d => data[d].forEach(e => { if(e.notes) all.push({date:d,...e}); }));
  if(!all.length){ el.innerHTML = '<div class="muted">No notes yet. Add notes when logging workouts.</div>'; return; }
  el.innerHTML = all.slice(0,25).map(n => `
    <div class="note-item">
      <div class="note-meta">${n.date} · <span class="note-muscle">${n.muscle}</span> · ${n.weight}kg ${n.reps ? '× '+n.reps+' reps' : ''}</div>
      <div style="font-size:14px">💬 ${n.notes}</div>
    </div>`).join('');
}

// ════════════════════════════════
// WATER
// ════════════════════════════════
const WGOAL = 8;
function initWater(){ if(!water[today]) water[today] = 0; renderWater(); }
function renderWater(){
  const cups = water[today] || 0;
  document.getElementById('waterKpi').textContent  = cups + ' / ' + WGOAL;
  document.getElementById('waterCount').textContent = cups + ' / ' + WGOAL + ' glasses';
  const pct = Math.min(100, (cups/WGOAL)*100);
  document.getElementById('waterBar').style.width = pct + '%';
  const grid = document.getElementById('waterGrid');
  if(!grid) return;
  grid.innerHTML = '';
  for(let i = 0; i < WGOAL; i++){
    const cup = document.createElement('div');
    cup.className = 'cup' + (i < cups ? ' filled' : '');
    cup.textContent = '🥛';
    cup.onclick = () => {
      water[today] = (i < cups) ? i : i+1;
      localStorage.setItem('lvWater', JSON.stringify(water));
      renderWater(); renderWaterChart();
    };
    grid.appendChild(cup);
  }
}
function resetWater(){ water[today] = 0; localStorage.setItem('lvWater', JSON.stringify(water)); renderWater(); }

let wChart = null;
function renderWaterChart(){
  const labels = [], vals = [];
  for(let i = 6; i >= 0; i--){
    const d = new Date(); d.setDate(d.getDate()-i);
    const k = d.toISOString().slice(0,10);
    labels.push(d.toLocaleDateString('en',{weekday:'short'}));
    vals.push(water[k] || 0);
  }
  if(wChart) wChart.destroy();
  const el   = document.getElementById('waterChart'); if(!el) return;
  const dark = document.documentElement.dataset.theme === 'dark';
  const tc   = dark ? '#555' : '#555';
  wChart = new Chart(el, {
    type:'bar',
    data:{ labels, datasets:[{ data:vals, backgroundColor:'#1e90ff', borderRadius:7 }]},
    options:{ plugins:{legend:{display:false}}, scales:{ x:{ticks:{color:tc}}, y:{ticks:{color:tc},max:10} }}
  });
}

// ════════════════════════════════
// PRs
// ════════════════════════════════
function renderPRs(){
  const tbody = document.getElementById('prBody');
  tbody.innerHTML = '';
  ['Chest','Back','Legs','Arms','Shoulder'].forEach(m => {
    const p = prs[m];
    tbody.innerHTML += `<tr>
      <td>${m}</td>
      <td class="${p?'pr-new':''}">${p ? p.weight+'kg' : '—'}</td>
      <td>${p ? (p.reps||'—') : '—'}</td>
      <td class="muted">${p ? p.date : '—'}</td>
    </tr>`;
  });
}

function savePR(){
  const muscle = document.getElementById('prMuscle').value;
  const wt     = +document.getElementById('prWeight').value;
  const reps   = +document.getElementById('prReps').value || 0;
  if(!wt){ alert('Enter weight'); return; }
  const prev = prs[muscle];
  prs[muscle] = { weight:wt, reps, date:today };
  localStorage.setItem('lvPRs', JSON.stringify(prs));
  document.getElementById('prMsg').innerHTML = (prev && wt > prev.weight)
    ? `<span class="badge">🏆 NEW PR! Was ${prev.weight}kg</span>`
    : '<span class="badge green">Saved ✔</span>';
  document.getElementById('prWeight').value = '';
  document.getElementById('prReps').value   = '';
  renderPRs();
}

// ════════════════════════════════
// BMI
// ════════════════════════════════
function calcBMI(){
  const h    = +document.getElementById('heightCm').value;
  const w    = +document.getElementById('bodyWeightKg').value;
  const goal = document.getElementById('goalType').value;
  if(!h||!w){ alert('Enter height & weight'); return; }
  const bmi  = (w / ((h/100)**2)).toFixed(1);
  let status = bmi<18.5 ? 'Underweight ⚠️' : bmi<25 ? 'Normal ✅' : bmi<30 ? 'Overweight ⚠️' : 'Obese 🔴';
  const bmr  = (10*w) + (6.25*h) - (5*25) + 5;
  const tdee = bmr * 1.55;
  const cal  = goal==='loss' ? tdee-400 : goal==='gain' ? tdee+500 : tdee;
  const prot = w * 1.9;
  const carbs = goal==='loss' ? w*2.5 : goal==='gain' ? w*5 : w*3.5;
  document.getElementById('bmiResult').innerHTML =
    `BMI: <b>${bmi}</b> — ${status}<br>
     ${goal==='loss'?'Target: Lose ~'+Math.round(w*0.1)+'kg':goal==='gain'?'Target: Gain ~'+Math.round(w*0.08)+'kg':'Target: Maintain weight'}`;
  document.getElementById('proteinNeed').textContent = Math.round(prot) + 'g';
  document.getElementById('carbNeed').textContent    = Math.round(carbs) + 'g';
  document.getElementById('calNeed').textContent     = Math.round(cal) + ' kcal';
  document.getElementById('calorieHint').textContent =
    goal==='loss' ? '🔻 Eat in a calorie deficit' : goal==='gain' ? '🔺 Eat in a calorie surplus' : '⚖️ Maintain calories';
  profile = { h, w, goal };
  localStorage.setItem('lvProfile', JSON.stringify(profile));
}

// ════════════════════════════════
// CHARTS
// ════════════════════════════════
let charts = {};
function renderChart(muscle, id){
  const labels = [], vals = [];
  Object.keys(data).sort().forEach(d =>
    data[d].forEach(w => { if(w.muscle === muscle){ labels.push(d.slice(5)); vals.push(w.weight); }})
  );
  const el = document.getElementById(id); if(!el) return;
  if(charts[id]) charts[id].destroy();
  const dark = document.documentElement.dataset.theme === 'dark';
  const tc   = dark ? '#555' : '#555';
  charts[id] = new Chart(el, {
    type:'line',
    data:{ labels, datasets:[{ data:vals, borderColor:'#e50914', fill:true, backgroundColor:'rgba(229,9,20,.07)', tension:.4, pointBackgroundColor:'#e50914', pointRadius:4 }]},
    options:{ plugins:{legend:{display:false}}, scales:{ x:{ticks:{color:tc}}, y:{ticks:{color:tc}} }}
  });
}
function renderAllCharts(){
  ['Chest','Back','Legs','Arms','Shoulder'].forEach(m => renderChart(m, m.toLowerCase()+'Chart'));
}

// ════════════════════════════════
// HOME WORKOUT PLANS
// ════════════════════════════════

let hwGender = 'male';
let hwLevel  = 'beginner';
let hwGoal   = 'loss';

// ── MALE HOME WORKOUT DATABASE ──
const HW_MALE = {
  beginner:{
    loss:{
      name:'Fat Burn Starter — Male',
      tip:'Focus on full range of motion. Rest 45–60s between sets. Do cardio finisher after each session.',
      days:[
        { day:'Monday', focus:'Upper Body Burn', color:'#e50914', exercises:[
          {name:'Push-Ups',sets:'3',reps:'12–15',tip:'Keep core tight, full range'},
          {name:'Wide Push-Ups',sets:'3',reps:'10–12',tip:'Wider grip hits chest more'},
          {name:'Diamond Push-Ups',sets:'2',reps:'10',tip:'Targets triceps'},
          {name:'Pike Push-Ups',sets:'3',reps:'10–12',tip:'Shoulder builder'},
          {name:'Plank Hold',sets:'3',reps:'30–45s',tip:'Don\'t let hips drop'},
          {name:'Mountain Climbers',sets:'3',reps:'20/side',tip:'Cardio + core combo'},
        ]},
        { day:'Tuesday', focus:'Lower Body Burn', color:'#ffcc00', exercises:[
          {name:'Bodyweight Squat',sets:'4',reps:'20',tip:'Sit back, chest up'},
          {name:'Reverse Lunges',sets:'3',reps:'12/leg',tip:'Step back, knee to floor'},
          {name:'Glute Bridges',sets:'3',reps:'20',tip:'Squeeze glutes at top'},
          {name:'Wall Sit',sets:'3',reps:'45s',tip:'90° angle, back flat'},
          {name:'Calf Raises',sets:'3',reps:'25',tip:'Full stretch at bottom'},
          {name:'Jump Jacks',sets:'3',reps:'30',tip:'Cardio finisher'},
        ]},
        { day:'Wednesday', focus:'Active Recovery', rest:true, tip:'Light walk 20–30 min. Stretch all major muscles. Sleep 7–8 hrs.' },
        { day:'Thursday', focus:'Core + Cardio', color:'#1e90ff', exercises:[
          {name:'Crunches',sets:'3',reps:'20',tip:'Don\'t pull your neck'},
          {name:'Leg Raises',sets:'3',reps:'15',tip:'Lower back flat on floor'},
          {name:'Bicycle Crunches',sets:'3',reps:'20/side',tip:'Slow & controlled'},
          {name:'Plank',sets:'3',reps:'45s',tip:'Breathe steadily'},
          {name:'Burpees',sets:'3',reps:'10',tip:'Full body fat burner'},
          {name:'High Knees',sets:'3',reps:'30s',tip:'Drive knees up fast'},
        ]},
        { day:'Friday', focus:'Full Body Circuit', color:'#1db954', exercises:[
          {name:'Push-Ups',sets:'3',reps:'15',tip:'Explosive on push'},
          {name:'Squat Jumps',sets:'3',reps:'15',tip:'Land softly'},
          {name:'Mountain Climbers',sets:'3',reps:'20/side',tip:'Keep hips level'},
          {name:'Glute Bridge',sets:'3',reps:'20',tip:'Hold 2s at top'},
          {name:'Plank to Push-Up',sets:'3',reps:'10',tip:'Core stable throughout'},
          {name:'Burpees',sets:'3',reps:'10',tip:'Max effort'},
        ]},
        { day:'Saturday', focus:'Stretch & Walk', rest:true, tip:'30 min brisk walk outdoors. Foam roll legs & back.' },
        { day:'Sunday', focus:'Full Rest', rest:true, tip:'Complete rest. Eat clean. Hydrate well. Prepare for next week!' },
      ]
    },
    muscle:{
      name:'Muscle Builder Starter — Male',
      tip:'Progressive overload at home: increase reps each week. Protein is key — aim 2g/kg bodyweight.',
      days:[
        { day:'Monday', focus:'Push (Chest + Shoulders + Triceps)', color:'#e50914', exercises:[
          {name:'Standard Push-Ups',sets:'4',reps:'15–20',tip:'Warm up movement'},
          {name:'Wide Push-Ups',sets:'3',reps:'12–15',tip:'Chest focus'},
          {name:'Decline Push-Ups',sets:'3',reps:'12',tip:'Upper chest, feet elevated'},
          {name:'Pike Push-Ups',sets:'3',reps:'12',tip:'Shoulder press alternative'},
          {name:'Diamond Push-Ups',sets:'3',reps:'12',tip:'Tricep isolation'},
          {name:'Dips (Chair)',sets:'3',reps:'15',tip:'Use sturdy chair'},
        ]},
        { day:'Tuesday', focus:'Pull (Back + Biceps)', color:'#ffcc00', exercises:[
          {name:'Doorframe Rows',sets:'4',reps:'12–15',tip:'Use doorframe or table'},
          {name:'Superman Hold',sets:'3',reps:'15',tip:'Back extension, hold 2s'},
          {name:'Towel Bicep Curl',sets:'3',reps:'12',tip:'Use heavy backpack'},
          {name:'Reverse Snow Angels',sets:'3',reps:'15',tip:'Rear delt, lie face down'},
          {name:'Plank Row (Backpack)',sets:'3',reps:'10/side',tip:'Core + back combo'},
        ]},
        { day:'Wednesday', focus:'Legs', color:'#1db954', exercises:[
          {name:'Bodyweight Squat',sets:'4',reps:'20–25',tip:'Deep squat'},
          {name:'Bulgarian Split Squat',sets:'3',reps:'12/leg',tip:'Rear foot on chair'},
          {name:'Romanian DL (Single Leg)',sets:'3',reps:'12/leg',tip:'Hamstring stretch'},
          {name:'Glute Bridge',sets:'4',reps:'20',tip:'Single leg variant for harder'},
          {name:'Calf Raises',sets:'4',reps:'25',tip:'On step for full range'},
          {name:'Wall Sit',sets:'3',reps:'60s',tip:'Burn those quads!'},
        ]},
        { day:'Thursday', focus:'Active Recovery', rest:true, tip:'Light yoga or walking. Eat high protein meal.' },
        { day:'Friday', focus:'Full Body Strength', color:'#1e90ff', exercises:[
          {name:'Explosive Push-Ups',sets:'4',reps:'10',tip:'Power push, clap if able'},
          {name:'Squat Jumps',sets:'4',reps:'15',tip:'Max height'},
          {name:'Pike Push-Up',sets:'3',reps:'12',tip:'Controlled descent'},
          {name:'Single Leg Glute Bridge',sets:'3',reps:'15/leg',tip:'Full hip extension'},
          {name:'Dips (Chair)',sets:'3',reps:'15',tip:'Chest up'},
          {name:'Plank',sets:'3',reps:'60s',tip:'Abs rock solid'},
        ]},
        { day:'Saturday', focus:'Core & Arms', color:'#ff69b4', exercises:[
          {name:'Hanging Knee Raises (Door)',sets:'3',reps:'15',tip:'Or floor leg raises'},
          {name:'Plank',sets:'3',reps:'60s',tip:''},
          {name:'Bicycle Crunches',sets:'3',reps:'20/side',tip:''},
          {name:'Towel Curl',sets:'3',reps:'15',tip:'Backpack for resistance'},
          {name:'Diamond Push-Ups',sets:'3',reps:'12',tip:'Tricep finisher'},
        ]},
        { day:'Sunday', focus:'Full Rest', rest:true, tip:'Complete rest. High protein meals. Sleep 8 hrs.' },
      ]
    },
    gain:{
      name:'Weight Gain Home Plan — Male',
      tip:'Eat in calorie surplus. High carbs. Train 3–4x/week. Focus on compound movements.',
      days:[
        { day:'Monday', focus:'Full Body Compound', color:'#e50914', exercises:[
          {name:'Squat',sets:'4',reps:'20',tip:'Deep, controlled'},
          {name:'Push-Ups',sets:'4',reps:'20',tip:'Chest to floor'},
          {name:'Glute Bridge',sets:'3',reps:'20',tip:'Posterior chain'},
          {name:'Pike Push-Up',sets:'3',reps:'15',tip:'Shoulder builder'},
          {name:'Plank',sets:'3',reps:'45s',tip:'Core stability'},
        ]},
        { day:'Tuesday', focus:'Rest', rest:true, tip:'Eat 3 big meals. Get 8 hrs sleep.' },
        { day:'Wednesday', focus:'Upper Body Volume', color:'#ffcc00', exercises:[
          {name:'Wide Push-Ups',sets:'5',reps:'20',tip:'High volume chest'},
          {name:'Diamond Push-Ups',sets:'4',reps:'15',tip:'Tricep volume'},
          {name:'Pike Push-Ups',sets:'4',reps:'15',tip:'Shoulder press'},
          {name:'Dips (Chair)',sets:'4',reps:'15',tip:'Weighted with backpack'},
          {name:'Superman',sets:'3',reps:'15',tip:'Back development'},
        ]},
        { day:'Thursday', focus:'Rest', rest:true, tip:'Eat calorie surplus. Protein shake if available.' },
        { day:'Friday', focus:'Lower Body Volume', color:'#1db954', exercises:[
          {name:'Squat',sets:'5',reps:'25',tip:'High volume'},
          {name:'Reverse Lunge',sets:'4',reps:'15/leg',tip:'Leg mass builder'},
          {name:'Single Leg Glute Bridge',sets:'4',reps:'15/leg',tip:''},
          {name:'Calf Raises',sets:'5',reps:'30',tip:'Full range'},
          {name:'Wall Sit',sets:'3',reps:'60s',tip:''},
        ]},
        { day:'Saturday', focus:'Rest or Light Walk', rest:true, tip:'Active rest day.' },
        { day:'Sunday', focus:'Full Rest', rest:true, tip:'Meal prep for the week. Hydrate.' },
      ]
    }
  },
  intermediate:{
    loss:{
      name:'Fat Shredder — Male Intermediate',
      tip:'Superset exercises where marked. Rest 30–45s. Add a 10-min HIIT finisher daily.',
      days:[
        { day:'Monday', focus:'HIIT Upper Body', color:'#e50914', exercises:[
          {name:'Explosive Push-Ups',sets:'4',reps:'15',tip:'Fast concentric'},
          {name:'Pike Push-Ups',sets:'4',reps:'12',tip:'Superset with next'},
          {name:'Tricep Dips (Chair)',sets:'4',reps:'15',tip:''},
          {name:'Plank to Push-Up',sets:'3',reps:'12',tip:'Core fire'},
          {name:'Burpee Push-Ups',sets:'3',reps:'10',tip:'Full fat burner'},
          {name:'Mountain Climbers',sets:'3',reps:'30s',tip:'Sprint pace'},
        ]},
        { day:'Tuesday', focus:'HIIT Lower Body', color:'#ffcc00', exercises:[
          {name:'Squat Jumps',sets:'4',reps:'20',tip:'Land softly, explode up'},
          {name:'Alternating Lunges',sets:'4',reps:'15/leg',tip:''},
          {name:'Single Leg Glute Bridge',sets:'3',reps:'15/leg',tip:''},
          {name:'Sumo Squat',sets:'4',reps:'20',tip:'Wide stance, inner thigh'},
          {name:'Box Jumps (Chair)',sets:'3',reps:'12',tip:'Explosive power'},
          {name:'High Knees',sets:'3',reps:'40s',tip:'Max speed'},
        ]},
        { day:'Wednesday', focus:'Active Recovery', rest:true, tip:'30 min jog or yoga. Stretch 15 min.' },
        { day:'Thursday', focus:'Core + Cardio Circuit', color:'#1e90ff', exercises:[
          {name:'V-Ups',sets:'4',reps:'15',tip:'Touch toes at top'},
          {name:'Bicycle Crunches',sets:'4',reps:'25/side',tip:'Slow & controlled'},
          {name:'Plank',sets:'3',reps:'60s',tip:''},
          {name:'Side Plank',sets:'3',reps:'45s/side',tip:''},
          {name:'Burpees',sets:'4',reps:'15',tip:'No rest between sets'},
          {name:'Jump Rope (Imaginary)',sets:'4',reps:'60s',tip:'Or actual jump rope'},
        ]},
        { day:'Friday', focus:'Full Body HIIT', color:'#1db954', exercises:[
          {name:'Burpees',sets:'4',reps:'15',tip:''},
          {name:'Push-Ups',sets:'4',reps:'20',tip:''},
          {name:'Squat Jumps',sets:'4',reps:'20',tip:''},
          {name:'Mountain Climbers',sets:'4',reps:'30s',tip:''},
          {name:'Dips',sets:'3',reps:'15',tip:''},
          {name:'High Knees',sets:'3',reps:'40s',tip:'Sprint finish'},
        ]},
        { day:'Saturday', focus:'Long Walk / Jog', rest:true, tip:'45 min steady state cardio outdoors.' },
        { day:'Sunday', focus:'Full Rest', rest:true, tip:'Rest. Meal prep. Hydrate 3–4L.' },
      ]
    },
    muscle:{
      name:'Home Hypertrophy — Male Intermediate',
      tip:'Time under tension is your friend. Slow negatives (3 seconds down). Use backpack for added resistance.',
      days:[
        { day:'Monday', focus:'Chest + Triceps', color:'#e50914', exercises:[
          {name:'Decline Push-Ups',sets:'4',reps:'15–20',tip:'Upper chest focus'},
          {name:'Wide Push-Ups',sets:'4',reps:'15',tip:''},
          {name:'Archer Push-Ups',sets:'3',reps:'10/side',tip:'Unilateral chest'},
          {name:'Diamond Push-Ups',sets:'4',reps:'15',tip:'Tricep pump'},
          {name:'Dips (Chair)',sets:'4',reps:'15',tip:'Lean forward for chest'},
          {name:'Push-Up Hold (Bottom)',sets:'3',reps:'30s',tip:'Isometric tension'},
        ]},
        { day:'Tuesday', focus:'Back + Biceps', color:'#ffcc00', exercises:[
          {name:'Table Rows',sets:'4',reps:'15',tip:'Lie under table, pull up'},
          {name:'Superman',sets:'4',reps:'15',tip:'Hold 3s at top'},
          {name:'Reverse Snow Angels',sets:'3',reps:'20',tip:'Rear delts & upper back'},
          {name:'Backpack Curl',sets:'4',reps:'12',tip:'Fill bag for weight'},
          {name:'Hammer Curl (Backpack)',sets:'3',reps:'12',tip:''},
          {name:'Good Mornings (BW)',sets:'3',reps:'15',tip:'Lower back & hamstrings'},
        ]},
        { day:'Wednesday', focus:'Legs', color:'#1db954', exercises:[
          {name:'Bulgarian Split Squat',sets:'4',reps:'15/leg',tip:'Chair for rear foot'},
          {name:'Pistol Squat (Assisted)',sets:'3',reps:'8/leg',tip:'Hold wall if needed'},
          {name:'Single Leg RDL',sets:'4',reps:'12/leg',tip:'Hamstring stretch'},
          {name:'Jump Squats',sets:'3',reps:'20',tip:'Plyometric power'},
          {name:'Step-Ups (Chair)',sets:'4',reps:'15/leg',tip:''},
          {name:'Calf Raises (Single Leg)',sets:'4',reps:'20/leg',tip:''},
        ]},
        { day:'Thursday', focus:'Rest', rest:true, tip:'Protein meal. Stretch. 8 hrs sleep.' },
        { day:'Friday', focus:'Shoulders + Abs', color:'#1e90ff', exercises:[
          {name:'Pike Push-Ups',sets:'5',reps:'15',tip:''},
          {name:'Wall Handstand Hold',sets:'3',reps:'20s',tip:'Build shoulder strength'},
          {name:'Lateral Raise (Bottles)',sets:'4',reps:'15',tip:'Use water bottles'},
          {name:'Front Raise (Bottles)',sets:'3',reps:'15',tip:''},
          {name:'Ab Wheel (or Towel)',sets:'4',reps:'12',tip:'Towel on floor works'},
          {name:'Hanging Leg Raise',sets:'4',reps:'15',tip:''},
        ]},
        { day:'Saturday', focus:'Arms + Core', color:'#ff69b4', exercises:[
          {name:'Backpack Curl',sets:'4',reps:'15',tip:''},
          {name:'Hammer Curl',sets:'3',reps:'12',tip:''},
          {name:'Diamond Push-Ups',sets:'4',reps:'15',tip:''},
          {name:'Dips',sets:'4',reps:'15',tip:''},
          {name:'Plank',sets:'3',reps:'60s',tip:''},
          {name:'V-Ups',sets:'3',reps:'15',tip:''},
        ]},
        { day:'Sunday', focus:'Full Rest', rest:true, tip:'Active recovery walk. Prep meals.' },
      ]
    },
    gain:{
      name:'Home Bulk — Male Intermediate',
      tip:'Eat big, train big. High volume. Rest 90s between sets. Focus on progressive overload.',
      days:[
        { day:'Monday', focus:'Push Volume', color:'#e50914', exercises:[
          {name:'Push-Ups (Weighted)',sets:'5',reps:'20',tip:'Backpack on back'},
          {name:'Decline Push-Ups',sets:'4',reps:'15',tip:''},
          {name:'Pike Push-Ups',sets:'4',reps:'15',tip:''},
          {name:'Dips',sets:'5',reps:'20',tip:''},
          {name:'Diamond Push-Ups',sets:'4',reps:'15',tip:''},
        ]},
        { day:'Tuesday', focus:'Pull Volume', color:'#ffcc00', exercises:[
          {name:'Table Rows',sets:'5',reps:'15',tip:''},
          {name:'Backpack Curl',sets:'4',reps:'15',tip:''},
          {name:'Superman',sets:'4',reps:'20',tip:''},
          {name:'Doorframe Pull (Isometric)',sets:'3',reps:'30s',tip:''},
          {name:'Reverse Snow Angels',sets:'3',reps:'20',tip:''},
        ]},
        { day:'Wednesday', focus:'Rest', rest:true, tip:'Eat 3 full meals + snacks. Sleep.' },
        { day:'Thursday', focus:'Leg Volume', color:'#1db954', exercises:[
          {name:'Squat (Weighted)',sets:'5',reps:'25',tip:'Backpack for resistance'},
          {name:'Bulgarian Split Squat',sets:'4',reps:'15/leg',tip:''},
          {name:'Step-Ups',sets:'4',reps:'15/leg',tip:''},
          {name:'Calf Raises',sets:'5',reps:'30',tip:''},
          {name:'Wall Sit',sets:'3',reps:'90s',tip:''},
        ]},
        { day:'Friday', focus:'Full Body + Core', color:'#1e90ff', exercises:[
          {name:'Explosive Push-Ups',sets:'4',reps:'15',tip:''},
          {name:'Squat Jumps',sets:'4',reps:'20',tip:''},
          {name:'Table Row',sets:'4',reps:'15',tip:''},
          {name:'Plank',sets:'3',reps:'60s',tip:''},
          {name:'V-Ups',sets:'3',reps:'15',tip:''},
        ]},
        { day:'Saturday', focus:'Rest', rest:true, tip:'Meal prep. High carb day.' },
        { day:'Sunday', focus:'Full Rest', rest:true, tip:'Sleep 9 hrs. Hydrate.' },
      ]
    }
  },
  advanced:{
    loss:{
      name:'Elite Fat Shred — Male Advanced',
      tip:'Minimal rest (20–30s). Superset everything. Add 15-min HIIT after every session.',
      days:[
        { day:'Monday', focus:'Upper HIIT Superset', color:'#e50914', exercises:[
          {name:'Clap Push-Ups',sets:'5',reps:'15',tip:'Explosive power'},
          {name:'Archer Push-Ups',sets:'4',reps:'12/side',tip:'Superset with dips'},
          {name:'Tricep Dips',sets:'4',reps:'20',tip:''},
          {name:'Handstand Push-Ups (Wall)',sets:'4',reps:'8',tip:''},
          {name:'Burpee Push-Ups',sets:'4',reps:'15',tip:''},
          {name:'Mountain Climbers',sets:'4',reps:'45s',tip:'Sprint pace'},
        ]},
        { day:'Tuesday', focus:'Lower HIIT Superset', color:'#ffcc00', exercises:[
          {name:'Pistol Squats',sets:'4',reps:'10/leg',tip:'Full range'},
          {name:'Jump Lunges',sets:'4',reps:'15/leg',tip:'Explosive'},
          {name:'Nordic Hamstring Curl',sets:'3',reps:'8',tip:'Partner or sofa'},
          {name:'Box Jumps',sets:'4',reps:'15',tip:'Max height'},
          {name:'Single Leg Box Jump',sets:'3',reps:'10/leg',tip:''},
          {name:'Sprint (in place)',sets:'5',reps:'30s',tip:'Max speed'},
        ]},
        { day:'Wednesday', focus:'Active Recovery + Mobility', rest:true, tip:'30 min yoga. Foam roll. Ice bath if possible.' },
        { day:'Thursday', focus:'Core + Cardio Beast', color:'#1e90ff', exercises:[
          {name:'Dragon Flag',sets:'4',reps:'10',tip:'Control the negative'},
          {name:'Ab Wheel Rollout',sets:'4',reps:'15',tip:'Full extension'},
          {name:'Hanging L-Sit (Door)',sets:'3',reps:'20s',tip:''},
          {name:'Burpees',sets:'5',reps:'20',tip:''},
          {name:'V-Ups',sets:'4',reps:'20',tip:''},
          {name:'Planche Lean',sets:'3',reps:'30s',tip:'Lean forward on push-up position'},
        ]},
        { day:'Friday', focus:'Full Body Elite Circuit', color:'#1db954', exercises:[
          {name:'Clap Push-Ups',sets:'5',reps:'15',tip:''},
          {name:'Pistol Squats',sets:'4',reps:'10/leg',tip:''},
          {name:'Jump Lunges',sets:'4',reps:'15/leg',tip:''},
          {name:'Handstand Hold',sets:'3',reps:'30s',tip:''},
          {name:'Burpee Box Jumps',sets:'4',reps:'12',tip:''},
          {name:'Sprint Finisher',sets:'1',reps:'5 min AMRAP',tip:'All out effort'},
        ]},
        { day:'Saturday', focus:'5K Run or 45 min Cardio', rest:true, tip:'Outdoor run or cycling. Active fat burn.' },
        { day:'Sunday', focus:'Full Rest', rest:true, tip:'Complete rest. Prep nutrition for week.' },
      ]
    },
    muscle:{
      name:'Calisthenics Hypertrophy — Male Advanced',
      tip:'Slow negatives 4 seconds. Pause at bottom. Weighted vest/backpack for progression.',
      days:[
        { day:'Monday', focus:'Chest + Triceps (Heavy)', color:'#e50914', exercises:[
          {name:'Weighted Push-Ups',sets:'5',reps:'20',tip:'Heavy backpack'},
          {name:'Archer Push-Ups',sets:'4',reps:'12/side',tip:'Unilateral overload'},
          {name:'Pseudo Planche Push-Ups',sets:'4',reps:'10',tip:'Lean forward'},
          {name:'Ring Dips / Chair Dips',sets:'5',reps:'20',tip:'Weighted'},
          {name:'Handstand Push-Ups',sets:'4',reps:'8',tip:'Wall supported'},
          {name:'One-Arm Push-Up (Assisted)',sets:'3',reps:'5/side',tip:''},
        ]},
        { day:'Tuesday', focus:'Back + Biceps (Heavy)', color:'#ffcc00', exercises:[
          {name:'Weighted Table Row',sets:'5',reps:'15',tip:'Heavy backpack on chest'},
          {name:'Towel Pull-Up (Door)',sets:'4',reps:'10',tip:''},
          {name:'Single Arm Table Row',sets:'4',reps:'12/side',tip:''},
          {name:'Backpack Curl (Heavy)',sets:'5',reps:'12',tip:''},
          {name:'Reverse Curl',sets:'3',reps:'15',tip:'Brachialis focus'},
          {name:'Superman (Weighted)',sets:'4',reps:'15',tip:''},
        ]},
        { day:'Wednesday', focus:'Legs (Heavy)', color:'#1db954', exercises:[
          {name:'Pistol Squats',sets:'5',reps:'12/leg',tip:'Full depth'},
          {name:'Nordic Curl',sets:'4',reps:'8',tip:'Slow negative, 5s'},
          {name:'Bulgarian Split Squat (Weighted)',sets:'4',reps:'15/leg',tip:''},
          {name:'Single Leg Box Jump',sets:'4',reps:'10/leg',tip:''},
          {name:'Sissy Squat',sets:'3',reps:'15',tip:'Quad isolation'},
          {name:'Single Leg Calf Raise',sets:'5',reps:'25/leg',tip:''},
        ]},
        { day:'Thursday', focus:'Rest', rest:true, tip:'8 hrs sleep. 2.2g protein/kg. Stretch.' },
        { day:'Friday', focus:'Shoulders + Abs (Heavy)', color:'#1e90ff', exercises:[
          {name:'Handstand Push-Ups',sets:'5',reps:'10',tip:''},
          {name:'Pike Push-Ups (Weighted)',sets:'4',reps:'15',tip:''},
          {name:'Lateral Raise (Heavy Bottles)',sets:'4',reps:'15',tip:''},
          {name:'Dragon Flag',sets:'4',reps:'12',tip:''},
          {name:'Ab Wheel Rollout',sets:'4',reps:'15',tip:''},
          {name:'L-Sit Hold',sets:'3',reps:'20s',tip:''},
        ]},
        { day:'Saturday', focus:'Arms + Full Body', color:'#ff69b4', exercises:[
          {name:'Backpack Curl (Max Weight)',sets:'5',reps:'10',tip:''},
          {name:'One-Arm Dip (Assisted)',sets:'3',reps:'8/side',tip:''},
          {name:'Explosive Push-Ups',sets:'4',reps:'15',tip:''},
          {name:'Squat Jumps (Weighted)',sets:'4',reps:'20',tip:''},
          {name:'Plank (Weighted)',sets:'3',reps:'90s',tip:''},
        ]},
        { day:'Sunday', focus:'Full Rest', rest:true, tip:'Active stretch. Meal prep. 9 hrs sleep.' },
      ]
    },
    gain:{
      name:'Advanced Home Bulk — Male',
      tip:'Maximum volume. Calorie surplus 500kcal. Train 5–6 days. Sleep is growth.',
      days:[
        { day:'Monday', focus:'Max Push Volume', color:'#e50914', exercises:[
          {name:'Weighted Push-Ups',sets:'6',reps:'20',tip:''},
          {name:'Handstand Push-Ups',sets:'5',reps:'10',tip:''},
          {name:'Archer Push-Ups',sets:'4',reps:'12/side',tip:''},
          {name:'Dips (Heavy)',sets:'5',reps:'20',tip:''},
          {name:'Diamond Push-Ups',sets:'4',reps:'20',tip:''},
        ]},
        { day:'Tuesday', focus:'Max Pull Volume', color:'#ffcc00', exercises:[
          {name:'Table Rows (Heavy)',sets:'6',reps:'15',tip:''},
          {name:'Backpack Curl',sets:'5',reps:'15',tip:''},
          {name:'Single Arm Row',sets:'4',reps:'12/side',tip:''},
          {name:'Superman (Weighted)',sets:'4',reps:'20',tip:''},
          {name:'Reverse Curl',sets:'3',reps:'15',tip:''},
        ]},
        { day:'Wednesday', focus:'Max Leg Volume', color:'#1db954', exercises:[
          {name:'Pistol Squat',sets:'5',reps:'15/leg',tip:''},
          {name:'Bulgarian Split Squat',sets:'5',reps:'20/leg',tip:''},
          {name:'Nordic Curl',sets:'4',reps:'10',tip:''},
          {name:'Calf Raise (Single Leg)',sets:'5',reps:'30/leg',tip:''},
          {name:'Wall Sit',sets:'3',reps:'120s',tip:''},
        ]},
        { day:'Thursday', focus:'Rest', rest:true, tip:'2 high-calorie meals. Sleep 9 hrs.' },
        { day:'Friday', focus:'Shoulders + Core', color:'#1e90ff', exercises:[
          {name:'Handstand Push-Ups',sets:'5',reps:'12',tip:''},
          {name:'Pike Push-Ups',sets:'4',reps:'20',tip:''},
          {name:'Dragon Flag',sets:'4',reps:'12',tip:''},
          {name:'Ab Wheel',sets:'4',reps:'15',tip:''},
          {name:'L-Sit',sets:'3',reps:'25s',tip:''},
        ]},
        { day:'Saturday', focus:'Full Body Power', color:'#ff69b4', exercises:[
          {name:'Clap Push-Ups',sets:'4',reps:'20',tip:''},
          {name:'Pistol Squat',sets:'4',reps:'12/leg',tip:''},
          {name:'Burpees',sets:'4',reps:'20',tip:''},
          {name:'Box Jumps',sets:'4',reps:'15',tip:''},
          {name:'Plank',sets:'3',reps:'90s',tip:''},
        ]},
        { day:'Sunday', focus:'Full Rest', rest:true, tip:'Maximum recovery. Eat big. Sleep big.' },
      ]
    }
  }
};

// ── FEMALE HOME WORKOUT DATABASE ──
const HW_FEMALE = {
  beginner:{
    loss:{
      name:'Slim & Tone Starter — Female',
      tip:'Focus on form over speed. Rest 45–60s. Add 20 min walk after each session for extra fat burn.',
      days:[
        { day:'Monday', focus:'Lower Body Tone', color:'#ff69b4', exercises:[
          {name:'Bodyweight Squat',sets:'3',reps:'20',tip:'Sit back, knees over toes'},
          {name:'Glute Bridge',sets:'4',reps:'20',tip:'Squeeze glutes at top, hold 2s'},
          {name:'Reverse Lunges',sets:'3',reps:'12/leg',tip:'Core tight, step back'},
          {name:'Sumo Squat',sets:'3',reps:'15',tip:'Wide stance, inner thigh'},
          {name:'Donkey Kicks',sets:'3',reps:'15/leg',tip:'Glute activation'},
          {name:'Calf Raises',sets:'3',reps:'25',tip:'Full stretch'},
        ]},
        { day:'Tuesday', focus:'Upper Body Tone', color:'#e50914', exercises:[
          {name:'Knee Push-Ups',sets:'3',reps:'12–15',tip:'Build up to full push-ups'},
          {name:'Shoulder Tap Plank',sets:'3',reps:'10/side',tip:'Core + shoulder'},
          {name:'Lateral Raise (Bottles)',sets:'3',reps:'15',tip:'Use water bottles'},
          {name:'Tricep Dip (Chair)',sets:'3',reps:'12',tip:'Arms close to body'},
          {name:'Plank Hold',sets:'3',reps:'30s',tip:'Don\'t let hips sag'},
        ]},
        { day:'Wednesday', focus:'Active Recovery', rest:true, tip:'20–30 min light walk. Hip flexor stretches. Breathe.' },
        { day:'Thursday', focus:'Core + Cardio', color:'#ffcc00', exercises:[
          {name:'Crunches',sets:'3',reps:'20',tip:'Don\'t pull neck'},
          {name:'Leg Raises',sets:'3',reps:'15',tip:'Lower back stays flat'},
          {name:'Bicycle Crunches',sets:'3',reps:'15/side',tip:'Slow rotation'},
          {name:'Plank',sets:'3',reps:'30s',tip:''},
          {name:'Jump Jacks',sets:'3',reps:'30',tip:'Light cardio'},
          {name:'March in Place',sets:'3',reps:'60s',tip:'Drive knees high'},
        ]},
        { day:'Friday', focus:'Full Body Tone Circuit', color:'#1db954', exercises:[
          {name:'Squat',sets:'3',reps:'15',tip:''},
          {name:'Glute Bridge',sets:'3',reps:'20',tip:''},
          {name:'Knee Push-Up',sets:'3',reps:'12',tip:''},
          {name:'Mountain Climbers',sets:'3',reps:'20/side',tip:''},
          {name:'Side Lying Leg Raise',sets:'3',reps:'15/side',tip:'Hip abductor'},
          {name:'Plank',sets:'3',reps:'30s',tip:''},
        ]},
        { day:'Saturday', focus:'Walk or Dance', rest:true, tip:'30 min brisk walk or dance cardio. Fun counts!' },
        { day:'Sunday', focus:'Full Rest', rest:true, tip:'Rest. Eat clean. Hydrate 2.5–3L.' },
      ]
    },
    muscle:{
      name:'Lean Muscle Starter — Female',
      tip:'Don\'t fear muscle — it boosts metabolism! Aim 1.8g protein/kg. Slow reps = more tone.',
      days:[
        { day:'Monday', focus:'Glutes + Legs', color:'#ff69b4', exercises:[
          {name:'Squat',sets:'4',reps:'20',tip:'Deep squat'},
          {name:'Hip Thrust (Floor)',sets:'4',reps:'20',tip:'Back on sofa edge'},
          {name:'Bulgarian Split Squat',sets:'3',reps:'12/leg',tip:'Chair for rear foot'},
          {name:'Fire Hydrant',sets:'3',reps:'15/side',tip:'Hip abductor'},
          {name:'Donkey Kicks',sets:'3',reps:'15/leg',tip:'Glute squeeze at top'},
          {name:'Calf Raises',sets:'3',reps:'25',tip:''},
        ]},
        { day:'Tuesday', focus:'Upper Body & Core', color:'#e50914', exercises:[
          {name:'Knee Push-Ups',sets:'4',reps:'15',tip:'Progress to full push-ups'},
          {name:'Lateral Raise (Bottles)',sets:'3',reps:'15',tip:''},
          {name:'Tricep Dip',sets:'3',reps:'15',tip:''},
          {name:'Plank',sets:'3',reps:'45s',tip:''},
          {name:'Superman',sets:'3',reps:'15',tip:'Back strength'},
          {name:'Bicycle Crunches',sets:'3',reps:'20/side',tip:''},
        ]},
        { day:'Wednesday', focus:'Rest', rest:true, tip:'Eat protein. Stretch hips and glutes.' },
        { day:'Thursday', focus:'Legs + Glutes Volume', color:'#ffcc00', exercises:[
          {name:'Sumo Squat',sets:'4',reps:'20',tip:'Inner thigh tone'},
          {name:'Glute Bridge',sets:'4',reps:'25',tip:'Single leg for harder'},
          {name:'Curtsy Lunge',sets:'3',reps:'12/leg',tip:'Cross behind, great for glutes'},
          {name:'Side Leg Raise',sets:'3',reps:'20/side',tip:''},
          {name:'Step-Ups (Chair)',sets:'3',reps:'15/leg',tip:''},
          {name:'Wall Sit',sets:'3',reps:'45s',tip:''},
        ]},
        { day:'Friday', focus:'Full Body Tone', color:'#1db954', exercises:[
          {name:'Full Push-Ups (or Knee)',sets:'4',reps:'12',tip:''},
          {name:'Hip Thrust',sets:'4',reps:'20',tip:''},
          {name:'Pike Push-Ups',sets:'3',reps:'10',tip:'Shoulder tone'},
          {name:'Plank',sets:'3',reps:'45s',tip:''},
          {name:'V-Ups',sets:'3',reps:'12',tip:''},
        ]},
        { day:'Saturday', focus:'Core + Stretch', color:'#1e90ff', exercises:[
          {name:'Plank',sets:'3',reps:'60s',tip:''},
          {name:'Side Plank',sets:'3',reps:'30s/side',tip:''},
          {name:'Leg Raises',sets:'3',reps:'15',tip:''},
          {name:'Cat-Cow',sets:'3',reps:'10',tip:'Spinal mobility'},
          {name:'Hip Flexor Stretch',sets:'3',reps:'30s/side',tip:''},
        ]},
        { day:'Sunday', focus:'Full Rest', rest:true, tip:'Rest. High protein day. Sleep 8 hrs.' },
      ]
    },
    gain:{
      name:'Healthy Weight Gain — Female Beginner',
      tip:'Eat 300–400 calorie surplus. Healthy carbs & protein. Train 3x/week. No need to overtrain.',
      days:[
        { day:'Monday', focus:'Full Body', color:'#ff69b4', exercises:[
          {name:'Squat',sets:'3',reps:'15',tip:''},
          {name:'Push-Up (Knee)',sets:'3',reps:'12',tip:''},
          {name:'Glute Bridge',sets:'3',reps:'20',tip:''},
          {name:'Superman',sets:'3',reps:'15',tip:''},
          {name:'Plank',sets:'3',reps:'30s',tip:''},
        ]},
        { day:'Tuesday', focus:'Rest', rest:true, tip:'Eat 3 meals + 2 snacks. Paneer, dal, milk.' },
        { day:'Wednesday', focus:'Lower Body', color:'#ffcc00', exercises:[
          {name:'Squat',sets:'4',reps:'20',tip:''},
          {name:'Hip Thrust',sets:'4',reps:'20',tip:''},
          {name:'Reverse Lunge',sets:'3',reps:'12/leg',tip:''},
          {name:'Calf Raises',sets:'3',reps:'25',tip:''},
          {name:'Wall Sit',sets:'3',reps:'45s',tip:''},
        ]},
        { day:'Thursday', focus:'Rest', rest:true, tip:'Protein shake or milk + banana.' },
        { day:'Friday', focus:'Upper Body', color:'#e50914', exercises:[
          {name:'Push-Up (Knee or Full)',sets:'3',reps:'15',tip:''},
          {name:'Lateral Raise',sets:'3',reps:'15',tip:''},
          {name:'Tricep Dip',sets:'3',reps:'12',tip:''},
          {name:'Superman',sets:'3',reps:'15',tip:''},
          {name:'Plank',sets:'3',reps:'45s',tip:''},
        ]},
        { day:'Saturday', focus:'Light Walk', rest:true, tip:'Light 20 min walk. No intense cardio.' },
        { day:'Sunday', focus:'Full Rest', rest:true, tip:'Rest. Eat well. Sleep 8+ hrs.' },
      ]
    }
  },
  intermediate:{
    loss:{
      name:'Body Sculpt — Female Intermediate',
      tip:'Superset glutes with upper body for max calorie burn. Rest 30–40s. Keep intensity high.',
      days:[
        { day:'Monday', focus:'Glute + Core Superset', color:'#ff69b4', exercises:[
          {name:'Hip Thrust',sets:'4',reps:'25',tip:'Single leg variant'},
          {name:'Sumo Squat Jump',sets:'4',reps:'15',tip:'Explosive lower body'},
          {name:'Donkey Kicks (Elevated)',sets:'4',reps:'20/leg',tip:'Foot on wall'},
          {name:'Plank Hip Dip',sets:'3',reps:'20/side',tip:'Oblique sculpt'},
          {name:'Mountain Climbers',sets:'4',reps:'30s',tip:'Core fire'},
          {name:'Curtsy Lunge Jump',sets:'3',reps:'12/leg',tip:''},
        ]},
        { day:'Tuesday', focus:'Upper Body + Cardio', color:'#e50914', exercises:[
          {name:'Full Push-Ups',sets:'4',reps:'15',tip:''},
          {name:'Tricep Dip',sets:'4',reps:'15',tip:''},
          {name:'Pike Push-Up',sets:'3',reps:'12',tip:'Shoulder tone'},
          {name:'Lateral Raise (Bottles)',sets:'4',reps:'15',tip:''},
          {name:'Burpees',sets:'4',reps:'12',tip:''},
          {name:'Jump Jacks',sets:'3',reps:'45s',tip:''},
        ]},
        { day:'Wednesday', focus:'Active Recovery', rest:true, tip:'Yoga flow 30 min. Hip opener stretches.' },
        { day:'Thursday', focus:'Legs + HIIT', color:'#ffcc00', exercises:[
          {name:'Bulgarian Split Squat',sets:'4',reps:'15/leg',tip:''},
          {name:'Jump Squats',sets:'4',reps:'20',tip:''},
          {name:'Side Lunge',sets:'3',reps:'15/leg',tip:'Inner thigh'},
          {name:'Glute Kickback',sets:'4',reps:'20/leg',tip:''},
          {name:'High Knees',sets:'4',reps:'40s',tip:'Max speed'},
          {name:'Box Step Jump (Chair)',sets:'3',reps:'12',tip:''},
        ]},
        { day:'Friday', focus:'Full Body Sculpt', color:'#1db954', exercises:[
          {name:'Push-Ups',sets:'4',reps:'15',tip:''},
          {name:'Hip Thrust',sets:'4',reps:'20',tip:''},
          {name:'Burpees',sets:'4',reps:'12',tip:''},
          {name:'Plank',sets:'3',reps:'60s',tip:''},
          {name:'V-Ups',sets:'3',reps:'15',tip:''},
          {name:'Mountain Climbers',sets:'3',reps:'30s',tip:''},
        ]},
        { day:'Saturday', focus:'Long Walk / Jog', rest:true, tip:'45 min outdoor cardio. Flat belly finisher!' },
        { day:'Sunday', focus:'Full Rest', rest:true, tip:'Rest. Eat clean. Hydrate 3L.' },
      ]
    },
    muscle:{
      name:'Curves & Strength — Female Intermediate',
      tip:'Build curves with progressive overload. Add backpack weight to squats and hip thrusts.',
      days:[
        { day:'Monday', focus:'Glutes + Hamstrings (Heavy)', color:'#ff69b4', exercises:[
          {name:'Hip Thrust (Weighted)',sets:'5',reps:'20',tip:'Backpack on hips'},
          {name:'Bulgarian Split Squat',sets:'4',reps:'15/leg',tip:''},
          {name:'Romanian DL (Single Leg)',sets:'4',reps:'12/leg',tip:''},
          {name:'Donkey Kicks (Elevated)',sets:'4',reps:'20/leg',tip:''},
          {name:'Nordic Curl',sets:'3',reps:'8',tip:'Hamstring builder'},
          {name:'Fire Hydrant',sets:'3',reps:'20/side',tip:''},
        ]},
        { day:'Tuesday', focus:'Upper Body + Shoulders', color:'#e50914', exercises:[
          {name:'Full Push-Ups',sets:'4',reps:'15',tip:''},
          {name:'Archer Push-Up',sets:'3',reps:'10/side',tip:'Chest shape'},
          {name:'Pike Push-Up',sets:'4',reps:'15',tip:''},
          {name:'Lateral Raise (Bottles)',sets:'4',reps:'15',tip:''},
          {name:'Tricep Dip (Heavy)',sets:'4',reps:'15',tip:'Legs extended'},
          {name:'Superman (Weighted)',sets:'3',reps:'15',tip:'Back strength'},
        ]},
        { day:'Wednesday', focus:'Quads + Calves', color:'#ffcc00', exercises:[
          {name:'Squat (Weighted Backpack)',sets:'5',reps:'20',tip:''},
          {name:'Sumo Squat (Weighted)',sets:'4',reps:'20',tip:''},
          {name:'Step-Ups (Weighted)',sets:'4',reps:'15/leg',tip:''},
          {name:'Sissy Squat',sets:'3',reps:'15',tip:''},
          {name:'Single Leg Calf Raise',sets:'4',reps:'25/leg',tip:''},
        ]},
        { day:'Thursday', focus:'Rest', rest:true, tip:'2g protein/kg. 8 hrs sleep. Stretch glutes.' },
        { day:'Friday', focus:'Core + Arms', color:'#1e90ff', exercises:[
          {name:'V-Ups',sets:'4',reps:'15',tip:''},
          {name:'Bicycle Crunches',sets:'4',reps:'25/side',tip:''},
          {name:'Ab Wheel (Towel)',sets:'4',reps:'12',tip:''},
          {name:'Backpack Curl',sets:'4',reps:'15',tip:''},
          {name:'Hammer Curl',sets:'3',reps:'12',tip:''},
          {name:'Side Plank',sets:'3',reps:'45s/side',tip:''},
        ]},
        { day:'Saturday', focus:'Glute Finisher', color:'#ff69b4', exercises:[
          {name:'Hip Thrust (Max Weight)',sets:'5',reps:'20',tip:''},
          {name:'Curtsy Lunge',sets:'4',reps:'15/leg',tip:''},
          {name:'Donkey Kicks',sets:'4',reps:'20/leg',tip:''},
          {name:'Side Lying Clam',sets:'3',reps:'20/side',tip:'Hip abductor'},
          {name:'Glute Squeeze Hold',sets:'3',reps:'30s',tip:''},
        ]},
        { day:'Sunday', focus:'Full Rest', rest:true, tip:'Active stretch. Protein meal. 8 hrs sleep.' },
      ]
    },
    gain:{
      name:'Healthy Curves Gain — Female Intermediate',
      tip:'Calorie surplus 300–400kcal. Focus on lower body volume for shape. Eat good carbs.',
      days:[
        { day:'Monday', focus:'Lower Body Volume', color:'#ff69b4', exercises:[
          {name:'Squat (Weighted)',sets:'5',reps:'25',tip:''},
          {name:'Hip Thrust (Weighted)',sets:'5',reps:'20',tip:''},
          {name:'Romanian DL',sets:'4',reps:'15',tip:''},
          {name:'Calf Raises',sets:'4',reps:'30',tip:''},
          {name:'Wall Sit',sets:'3',reps:'60s',tip:''},
        ]},
        { day:'Tuesday', focus:'Upper Volume', color:'#e50914', exercises:[
          {name:'Push-Ups',sets:'5',reps:'20',tip:''},
          {name:'Pike Push-Ups',sets:'4',reps:'15',tip:''},
          {name:'Tricep Dips',sets:'4',reps:'15',tip:''},
          {name:'Lateral Raise',sets:'4',reps:'15',tip:''},
          {name:'Superman',sets:'4',reps:'20',tip:''},
        ]},
        { day:'Wednesday', focus:'Rest', rest:true, tip:'3 meals + 2 snacks. High carb day.' },
        { day:'Thursday', focus:'Glute Volume', color:'#ffcc00', exercises:[
          {name:'Hip Thrust (Heavy)',sets:'5',reps:'20',tip:''},
          {name:'Donkey Kicks',sets:'4',reps:'20/leg',tip:''},
          {name:'Fire Hydrant',sets:'4',reps:'20/side',tip:''},
          {name:'Glute Bridge (Single)',sets:'4',reps:'15/leg',tip:''},
          {name:'Curtsy Lunge',sets:'3',reps:'15/leg',tip:''},
        ]},
        { day:'Friday', focus:'Full Body', color:'#1db954', exercises:[
          {name:'Squat',sets:'4',reps:'20',tip:''},
          {name:'Push-Ups',sets:'4',reps:'15',tip:''},
          {name:'Hip Thrust',sets:'4',reps:'20',tip:''},
          {name:'Plank',sets:'3',reps:'60s',tip:''},
          {name:'V-Ups',sets:'3',reps:'15',tip:''},
        ]},
        { day:'Saturday', focus:'Rest', rest:true, tip:'Meal prep. Eat dal, paneer, rice.' },
        { day:'Sunday', focus:'Full Rest', rest:true, tip:'Sleep 9 hrs. Hydrate.' },
      ]
    }
  },
  advanced:{
    loss:{
      name:'Elite Shred — Female Advanced',
      tip:'Minimal rest. Superset everything. Add 15 min HIIT finisher. Track calories strictly.',
      days:[
        { day:'Monday', focus:'Lower HIIT + Glutes', color:'#ff69b4', exercises:[
          {name:'Pistol Squat',sets:'4',reps:'10/leg',tip:'Full depth'},
          {name:'Jump Lunges',sets:'5',reps:'15/leg',tip:''},
          {name:'Hip Thrust (Weighted Max)',sets:'5',reps:'20',tip:''},
          {name:'Nordic Curl',sets:'4',reps:'8',tip:''},
          {name:'Box Jump',sets:'4',reps:'15',tip:''},
          {name:'Sprint Finisher',sets:'1',reps:'5 min AMRAP',tip:''},
        ]},
        { day:'Tuesday', focus:'Upper HIIT', color:'#e50914', exercises:[
          {name:'Clap Push-Ups',sets:'4',reps:'12',tip:''},
          {name:'Archer Push-Up',sets:'4',reps:'12/side',tip:''},
          {name:'Handstand Hold (Wall)',sets:'3',reps:'20s',tip:''},
          {name:'Burpee Push-Ups',sets:'4',reps:'12',tip:''},
          {name:'Tricep Dip (Legs Extended)',sets:'4',reps:'20',tip:''},
          {name:'Mountain Climbers',sets:'4',reps:'45s',tip:''},
        ]},
        { day:'Wednesday', focus:'Yoga + Mobility', rest:true, tip:'45 min yoga. Deep stretches. Recovery.' },
        { day:'Thursday', focus:'Core Beast', color:'#ffcc00', exercises:[
          {name:'Dragon Flag',sets:'4',reps:'10',tip:''},
          {name:'Ab Wheel',sets:'4',reps:'15',tip:''},
          {name:'Hanging L-Sit',sets:'3',reps:'20s',tip:''},
          {name:'V-Ups',sets:'4',reps:'20',tip:''},
          {name:'Burpees',sets:'5',reps:'15',tip:''},
          {name:'High Knees',sets:'4',reps:'45s',tip:''},
        ]},
        { day:'Friday', focus:'Glute + Legs Heavy', color:'#1db954', exercises:[
          {name:'Hip Thrust (Max Weighted)',sets:'5',reps:'20',tip:''},
          {name:'Pistol Squat',sets:'5',reps:'12/leg',tip:''},
          {name:'Jump Squat (Weighted)',sets:'4',reps:'20',tip:''},
          {name:'Single Leg Nordic',sets:'3',reps:'6/leg',tip:''},
          {name:'Donkey Kick Pulse',sets:'4',reps:'30/leg',tip:''},
        ]},
        { day:'Saturday', focus:'5K Run / Long Cardio', rest:true, tip:'45–60 min outdoor run. Active fat burn.' },
        { day:'Sunday', focus:'Full Rest', rest:true, tip:'Recovery day. High protein meals.' },
      ]
    },
    muscle:{
      name:'Calisthenics Curves — Female Advanced',
      tip:'Progressive overload via weighted backpack & slower tempo. Build feminine muscle definition.',
      days:[
        { day:'Monday', focus:'Glutes & Hamstrings Max', color:'#ff69b4', exercises:[
          {name:'Weighted Hip Thrust',sets:'6',reps:'20',tip:'Maximum weight'},
          {name:'Pistol Squat',sets:'4',reps:'12/leg',tip:''},
          {name:'Nordic Curl',sets:'4',reps:'10',tip:'3s negative'},
          {name:'Elevated Single Leg Glute Bridge',sets:'4',reps:'20/leg',tip:''},
          {name:'Donkey Kick (Weighted Ankle)',sets:'5',reps:'20/leg',tip:''},
          {name:'Fire Hydrant Circles',sets:'3',reps:'15/side',tip:''},
        ]},
        { day:'Tuesday', focus:'Upper Body & Shoulders Heavy', color:'#e50914', exercises:[
          {name:'Archer Push-Ups',sets:'5',reps:'12/side',tip:''},
          {name:'Handstand Push-Ups',sets:'4',reps:'8',tip:''},
          {name:'Weighted Tricep Dip',sets:'5',reps:'20',tip:''},
          {name:'Lateral Raise (Heavy)',sets:'5',reps:'15',tip:''},
          {name:'Single Arm Push-Up (Assisted)',sets:'3',reps:'6/side',tip:''},
        ]},
        { day:'Wednesday', focus:'Quads + Calves Heavy', color:'#ffcc00', exercises:[
          {name:'Weighted Squat',sets:'5',reps:'25',tip:''},
          {name:'Bulgarian Split Squat (Heavy)',sets:'5',reps:'15/leg',tip:''},
          {name:'Sissy Squat',sets:'4',reps:'15',tip:''},
          {name:'Jump Squat',sets:'4',reps:'20',tip:''},
          {name:'Single Leg Calf Raise',sets:'5',reps:'30/leg',tip:''},
        ]},
        { day:'Thursday', focus:'Rest', rest:true, tip:'2g protein/kg. Glute stretches. Sleep 9 hrs.' },
        { day:'Friday', focus:'Core + Arms Heavy', color:'#1e90ff', exercises:[
          {name:'Dragon Flag',sets:'4',reps:'12',tip:''},
          {name:'Ab Wheel Rollout',sets:'4',reps:'15',tip:''},
          {name:'Hanging L-Sit',sets:'3',reps:'25s',tip:''},
          {name:'Heavy Backpack Curl',sets:'5',reps:'12',tip:''},
          {name:'One-Arm Dip (Assisted)',sets:'3',reps:'8/side',tip:''},
        ]},
        { day:'Saturday', focus:'Glute Hypertrophy Finisher', color:'#ff69b4', exercises:[
          {name:'Hip Thrust (Max)',sets:'6',reps:'20',tip:''},
          {name:'Curtsy Lunge (Weighted)',sets:'4',reps:'15/leg',tip:''},
          {name:'Pulse Squats',sets:'4',reps:'30',tip:'Quarter range, fast'},
          {name:'Side Lying Hip Raise',sets:'3',reps:'20/side',tip:''},
          {name:'Glute Squeeze Isometric',sets:'3',reps:'45s',tip:''},
        ]},
        { day:'Sunday', focus:'Full Rest', rest:true, tip:'Maximum recovery. 9 hrs sleep. Eat big.' },
      ]
    },
    gain:{
      name:'Advanced Healthy Gain — Female',
      tip:'High volume + calorie surplus 400kcal. Focus on lower body shape and upper body tone.',
      days:[
        { day:'Monday', focus:'Lower Body Max Volume', color:'#ff69b4', exercises:[
          {name:'Squat (Max Weighted)',sets:'6',reps:'25',tip:''},
          {name:'Hip Thrust (Max)',sets:'6',reps:'20',tip:''},
          {name:'Nordic Curl',sets:'4',reps:'10',tip:''},
          {name:'Calf Raises',sets:'5',reps:'30',tip:''},
          {name:'Wall Sit',sets:'3',reps:'120s',tip:''},
        ]},
        { day:'Tuesday', focus:'Upper Body Max Volume', color:'#e50914', exercises:[
          {name:'Weighted Push-Ups',sets:'5',reps:'20',tip:''},
          {name:'Handstand Push-Ups',sets:'4',reps:'10',tip:''},
          {name:'Archer Push-Ups',sets:'4',reps:'12/side',tip:''},
          {name:'Tricep Dip (Heavy)',sets:'5',reps:'20',tip:''},
          {name:'Superman (Weighted)',sets:'4',reps:'20',tip:''},
        ]},
        { day:'Wednesday', focus:'Glute Volume', color:'#ffcc00', exercises:[
          {name:'Hip Thrust (Heavy)',sets:'6',reps:'20',tip:''},
          {name:'Donkey Kicks',sets:'5',reps:'25/leg',tip:''},
          {name:'Curtsy Lunge',sets:'4',reps:'15/leg',tip:''},
          {name:'Fire Hydrant',sets:'4',reps:'20/side',tip:''},
          {name:'Pulse Squat',sets:'3',reps:'30',tip:''},
        ]},
        { day:'Thursday', focus:'Rest', rest:true, tip:'High calorie meals. 3L water. Sleep.' },
        { day:'Friday', focus:'Full Body Power', color:'#1db954', exercises:[
          {name:'Pistol Squat',sets:'4',reps:'12/leg',tip:''},
          {name:'Clap Push-Ups',sets:'4',reps:'12',tip:''},
          {name:'Jump Squats',sets:'4',reps:'20',tip:''},
          {name:'Ab Wheel',sets:'4',reps:'15',tip:''},
          {name:'Dragon Flag',sets:'3',reps:'10',tip:''},
        ]},
        { day:'Saturday', focus:'Core + Stretch', color:'#1e90ff', exercises:[
          {name:'Dragon Flag',sets:'3',reps:'10',tip:''},
          {name:'L-Sit Hold',sets:'3',reps:'25s',tip:''},
          {name:'V-Ups',sets:'4',reps:'20',tip:''},
          {name:'Side Plank',sets:'3',reps:'60s/side',tip:''},
          {name:'Full Body Stretch',sets:'1',reps:'15 min',tip:''},
        ]},
        { day:'Sunday', focus:'Full Rest', rest:true, tip:'Sleep 9 hrs. Maximum nutrition.' },
      ]
    }
  }
};

function switchHWGender(g){
  hwGender = g;
  document.getElementById('hw-male-tab').className   = 'hw-gtab male'   + (g==='male'?' active':'');
  document.getElementById('hw-female-tab').className = 'hw-gtab female' + (g==='female'?' active':'');
  renderHWPlan();
}

function switchHWLevel(l, el){
  hwLevel = l;
  document.querySelectorAll('.level-tab').forEach(t => t.classList.remove('active'));
  el.classList.add('active');
  renderHWPlan();
}

function switchHWGoal(g, el){
  hwGoal = g;
  document.querySelectorAll('.goal-tab').forEach(t => t.classList.remove('active'));
  el.classList.add('active');
  renderHWPlan();
}

function renderHWPlan(){
  const db   = hwGender === 'male' ? HW_MALE : HW_FEMALE;
  const plan = db[hwLevel]?.[hwGoal];
  if(!plan){ document.getElementById('hwPlanContainer').innerHTML = '<div class="muted">Plan coming soon!</div>'; return; }

  const isFemale = hwGender === 'female';
  const numColor = isFemale ? 'female' : '';
  const accentColor = isFemale ? '#ff69b4' : '#e50914';

  let html = `
    <div style="background:var(--sub);border:1px solid ${accentColor};border-radius:12px;padding:14px;margin-bottom:16px;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:10px">
      <div>
        <div style="font-family:'Bebas Neue',sans-serif;font-size:20px;color:${accentColor};letter-spacing:1px">${plan.name}</div>
        <div style="font-size:12px;color:var(--muted);margin-top:4px">💡 ${plan.tip}</div>
      </div>
      <div style="display:flex;gap:8px;flex-wrap:wrap">
        <span class="badge" style="background:${accentColor};color:#fff">${hwGender==='male'?'♂ Male':'♀ Female'}</span>
        <span class="badge" style="background:var(--sub);border:1px solid var(--border);color:var(--text)">${hwLevel.charAt(0).toUpperCase()+hwLevel.slice(1)}</span>
        <span class="badge green">${hwGoal==='loss'?'🔥 Fat Loss':hwGoal==='muscle'?'💪 Muscle':'⚖️ Weight Gain'}</span>
      </div>
    </div>
    <div class="hw-week">`;

  plan.days.forEach(d => {
    if(d.rest){
      html += `
        <div class="hw-day-card">
          <div class="hw-day-header rest-hdr">
            <div>
              <div class="hw-day-title" style="color:var(--muted)">${d.day}</div>
              <div class="hw-day-focus" style="color:var(--muted)">${d.focus}</div>
            </div>
            <span class="badge" style="background:var(--sub);color:var(--muted);border:1px solid var(--border)">REST 😴</span>
          </div>
          <div class="hw-tip"><b>Recovery tip:</b> ${d.tip}</div>
        </div>`;
    } else {
      const exHTML = d.exercises.map((ex, i) => `
        <div class="hw-ex">
          <div class="hw-ex-num ${numColor}">${i+1}</div>
          <div class="hw-ex-info">
            <div class="hw-ex-name">${ex.name}</div>
            ${ex.tip ? `<div class="hw-ex-detail">💡 ${ex.tip}</div>` : ''}
          </div>
          <div class="hw-ex-sets">${ex.sets}×${ex.reps}</div>
        </div>`).join('');
      html += `
        <div class="hw-day-card">
          <div class="hw-day-header" style="border-left:4px solid ${d.color||accentColor}">
            <div>
              <div class="hw-day-title" style="color:${d.color||accentColor}">${d.day}</div>
              <div class="hw-day-focus" style="color:${d.color||accentColor}">${d.focus}</div>
            </div>
            <span class="badge" style="background:${d.color||accentColor};color:#fff;font-size:11px">${d.exercises.length} exercises</span>
          </div>
          <div class="hw-ex-list">${exHTML}</div>
        </div>`;
    }
  });

  html += `</div>`;
  document.getElementById('hwPlanContainer').innerHTML = html;
}

// ════════════════════════════════
// WORKOUT PLANNER
// ════════════════════════════════

// Exercise library per muscle group
const EXERCISE_LIB = {
  Chest:{
    beginner:    [{name:'Push-Ups',sets:'3',reps:'10–15',rest:'60s'},{name:'Dumbbell Bench Press',sets:'3',reps:'10–12',rest:'60s'},{name:'Incline DB Press',sets:'3',reps:'10–12',rest:'60s'},{name:'Cable Flyes',sets:'2',reps:'12–15',rest:'45s'}],
    intermediate:[{name:'Barbell Bench Press',sets:'4',reps:'8–10',rest:'90s'},{name:'Incline DB Press',sets:'3',reps:'10–12',rest:'75s'},{name:'Cable Flyes',sets:'3',reps:'12–15',rest:'60s'},{name:'Dips (Weighted)',sets:'3',reps:'8–10',rest:'75s'},{name:'Pec Deck Machine',sets:'2',reps:'15',rest:'45s'}],
    advanced:    [{name:'Barbell Bench Press (Heavy)',sets:'5',reps:'5–6',rest:'2–3min'},{name:'Incline BB Press',sets:'4',reps:'6–8',rest:'2min'},{name:'DB Flyes',sets:'3',reps:'10–12',rest:'75s'},{name:'Weighted Dips',sets:'4',reps:'8–10',rest:'90s'},{name:'Cable Crossover',sets:'3',reps:'12–15',rest:'60s'}]
  },
  Back:{
    beginner:    [{name:'Lat Pulldown',sets:'3',reps:'10–12',rest:'60s'},{name:'Seated Cable Row',sets:'3',reps:'10–12',rest:'60s'},{name:'Dumbbell Row',sets:'3',reps:'10–12',rest:'60s'},{name:'Face Pulls',sets:'2',reps:'15',rest:'45s'}],
    intermediate:[{name:'Pull-Ups / Chin-Ups',sets:'4',reps:'6–10',rest:'90s'},{name:'Barbell Row',sets:'4',reps:'8–10',rest:'90s'},{name:'Seated Cable Row',sets:'3',reps:'10–12',rest:'75s'},{name:'Lat Pulldown (Wide)',sets:'3',reps:'10–12',rest:'60s'},{name:'Face Pulls',sets:'3',reps:'15',rest:'45s'}],
    advanced:    [{name:'Weighted Pull-Ups',sets:'5',reps:'5–8',rest:'2min'},{name:'Deadlift',sets:'4',reps:'5–6',rest:'3min'},{name:'Barbell Row',sets:'4',reps:'6–8',rest:'2min'},{name:'T-Bar Row',sets:'3',reps:'8–10',rest:'90s'},{name:'Straight Arm Pulldown',sets:'3',reps:'12–15',rest:'60s'}]
  },
  Legs:{
    beginner:    [{name:'Bodyweight Squat',sets:'3',reps:'15–20',rest:'60s'},{name:'Leg Press',sets:'3',reps:'12–15',rest:'75s'},{name:'Lunges',sets:'3',reps:'10/leg',rest:'60s'},{name:'Leg Curl',sets:'3',reps:'12–15',rest:'60s'}],
    intermediate:[{name:'Barbell Squat',sets:'4',reps:'8–10',rest:'2min'},{name:'Romanian Deadlift',sets:'4',reps:'10–12',rest:'90s'},{name:'Leg Press',sets:'3',reps:'12–15',rest:'75s'},{name:'Walking Lunges',sets:'3',reps:'12/leg',rest:'75s'},{name:'Leg Curl',sets:'3',reps:'12–15',rest:'60s'},{name:'Calf Raises',sets:'4',reps:'15–20',rest:'45s'}],
    advanced:    [{name:'Barbell Back Squat (Heavy)',sets:'5',reps:'5–6',rest:'3min'},{name:'Romanian Deadlift',sets:'4',reps:'8–10',rest:'2min'},{name:'Bulgarian Split Squat',sets:'4',reps:'8/leg',rest:'90s'},{name:'Leg Press',sets:'3',reps:'10–12',rest:'90s'},{name:'Leg Curl',sets:'4',reps:'10–12',rest:'75s'},{name:'Weighted Calf Raises',sets:'5',reps:'15–20',rest:'45s'}]
  },
  Shoulder:{
    beginner:    [{name:'DB Shoulder Press',sets:'3',reps:'10–12',rest:'60s'},{name:'Lateral Raises',sets:'3',reps:'12–15',rest:'45s'},{name:'Front Raises',sets:'2',reps:'12',rest:'45s'},{name:'Face Pulls',sets:'2',reps:'15',rest:'45s'}],
    intermediate:[{name:'Barbell Overhead Press',sets:'4',reps:'8–10',rest:'90s'},{name:'DB Lateral Raises',sets:'4',reps:'12–15',rest:'60s'},{name:'Arnold Press',sets:'3',reps:'10–12',rest:'75s'},{name:'Rear Delt Flyes',sets:'3',reps:'15',rest:'45s'},{name:'Upright Row',sets:'3',reps:'10–12',rest:'60s'}],
    advanced:    [{name:'Barbell OHP (Heavy)',sets:'5',reps:'5–6',rest:'2–3min'},{name:'DB Lateral Raises (Drop Set)',sets:'4',reps:'12–15',rest:'60s'},{name:'Arnold Press',sets:'4',reps:'8–10',rest:'90s'},{name:'Rear Delt Cable Flyes',sets:'4',reps:'15',rest:'60s'},{name:'Upright Row',sets:'3',reps:'10–12',rest:'75s'}]
  },
  Arms:{
    beginner:    [{name:'Barbell Curl',sets:'3',reps:'10–12',rest:'60s'},{name:'Hammer Curl',sets:'3',reps:'10–12',rest:'60s'},{name:'Tricep Pushdown',sets:'3',reps:'12–15',rest:'60s'},{name:'Overhead Tricep Ext.',sets:'2',reps:'12',rest:'60s'}],
    intermediate:[{name:'Barbell Curl',sets:'4',reps:'8–10',rest:'75s'},{name:'Incline DB Curl',sets:'3',reps:'10–12',rest:'60s'},{name:'Hammer Curl',sets:'3',reps:'10–12',rest:'60s'},{name:'Tricep Pushdown',sets:'4',reps:'10–12',rest:'75s'},{name:'Skull Crushers',sets:'3',reps:'10–12',rest:'75s'},{name:'Overhead Tricep Ext.',sets:'3',reps:'12',rest:'60s'}],
    advanced:    [{name:'Barbell Curl (Heavy)',sets:'4',reps:'6–8',rest:'90s'},{name:'Incline DB Curl',sets:'4',reps:'8–10',rest:'75s'},{name:'Concentration Curl',sets:'3',reps:'10–12',rest:'60s'},{name:'Skull Crushers',sets:'4',reps:'8–10',rest:'90s'},{name:'Close-Grip Bench',sets:'4',reps:'8–10',rest:'90s'},{name:'Tricep Dips (Weighted)',sets:'3',reps:'8–10',rest:'75s'}]
  },
  Abs:{
    beginner:    [{name:'Plank',sets:'3',reps:'30–45s',rest:'45s'},{name:'Crunches',sets:'3',reps:'15–20',rest:'45s'},{name:'Leg Raises',sets:'3',reps:'12–15',rest:'45s'}],
    intermediate:[{name:'Hanging Knee Raises',sets:'4',reps:'15',rest:'45s'},{name:'Cable Crunches',sets:'3',reps:'15–20',rest:'45s'},{name:'Plank (Weighted)',sets:'3',reps:'45–60s',rest:'45s'},{name:'Bicycle Crunches',sets:'3',reps:'20',rest:'45s'}],
    advanced:    [{name:'Hanging Leg Raises',sets:'4',reps:'15–20',rest:'60s'},{name:'Ab Wheel Rollout',sets:'4',reps:'12–15',rest:'60s'},{name:'Cable Crunches',sets:'4',reps:'20',rest:'45s'},{name:'Dragon Flag',sets:'3',reps:'8–10',rest:'75s'}]
  },
  Cardio:{
    beginner:    [{name:'Brisk Walk',sets:'1',reps:'20 min',rest:'—'},{name:'Stationary Bike',sets:'1',reps:'15 min',rest:'—'}],
    intermediate:[{name:'Treadmill Jog',sets:'1',reps:'25 min',rest:'—'},{name:'Jump Rope',sets:'5',reps:'1 min on / 30s off',rest:'30s'}],
    advanced:    [{name:'HIIT Sprints',sets:'8',reps:'30s sprint / 30s rest',rest:'—'},{name:'Stairmaster',sets:'1',reps:'20 min',rest:'—'}]
  },
  'Full Body':{
    beginner:    [{name:'Squat',sets:'3',reps:'12–15',rest:'60s'},{name:'Push-Up',sets:'3',reps:'10–15',rest:'60s'},{name:'DB Row',sets:'3',reps:'10–12',rest:'60s'},{name:'Plank',sets:'3',reps:'30s',rest:'45s'},{name:'Lunges',sets:'3',reps:'10/leg',rest:'60s'}],
    intermediate:[{name:'Barbell Squat',sets:'4',reps:'8–10',rest:'90s'},{name:'Bench Press',sets:'4',reps:'8–10',rest:'90s'},{name:'Pull-Ups',sets:'4',reps:'6–10',rest:'90s'},{name:'OHP',sets:'3',reps:'10–12',rest:'75s'},{name:'Romanian DL',sets:'3',reps:'10–12',rest:'90s'},{name:'Plank',sets:'3',reps:'45s',rest:'45s'}],
    advanced:    [{name:'Deadlift',sets:'4',reps:'5–6',rest:'3min'},{name:'Squat',sets:'4',reps:'5–6',rest:'3min'},{name:'Bench Press',sets:'4',reps:'6–8',rest:'2min'},{name:'Weighted Pull-Ups',sets:'4',reps:'6–8',rest:'2min'},{name:'OHP',sets:'3',reps:'8–10',rest:'90s'}]
  }
};

// Parse muscle from day text (e.g. "Monday – Chest" → "Chest")
function parseMuscle(text){
  const t = text.toLowerCase();
  if(t.includes('chest'))       return 'Chest';
  if(t.includes('back'))        return 'Back';
  if(t.includes('leg'))         return 'Legs';
  if(t.includes('shoulder'))    return 'Shoulder';
  if(t.includes('arm') || t.includes('bicep') || t.includes('tricep')) return 'Arms';
  if(t.includes('abs') || t.includes('core')) return 'Abs';
  if(t.includes('cardio') || t.includes('hiit')) return 'Cardio';
  if(t.includes('full') || t.includes('total')) return 'Full Body';
  if(t.includes('rest'))        return 'REST';
  return null;
}

// Detect day name from line
function parseDayLabel(text){
  const days = ['monday','tuesday','wednesday','thursday','friday','saturday','sunday'];
  const t    = text.toLowerCase();
  const found = days.find(d => t.includes(d));
  if(found) return found.charAt(0).toUpperCase()+found.slice(1);
  return text.split(/[–\-:]/)[0].trim();
}

// Default splits by goal + days
function defaultSplit(goal, days){
  const splits = {
    loss:{
      3:['Monday – Full Body','Wednesday – Full Body','Friday – Full Body'],
      4:['Monday – Full Body','Tuesday – Cardio','Thursday – Full Body','Saturday – Cardio'],
      5:['Monday – Chest','Tuesday – Back','Wednesday – Legs','Thursday – Shoulder','Friday – Arms'],
      6:['Monday – Chest','Tuesday – Back','Wednesday – Legs','Thursday – Shoulder','Friday – Arms','Saturday – Cardio'],
    },
    muscle:{
      3:['Monday – Chest','Wednesday – Back','Friday – Legs'],
      4:['Monday – Chest','Tuesday – Back','Thursday – Legs','Friday – Shoulder'],
      5:['Monday – Chest','Tuesday – Back','Wednesday – Legs','Thursday – Shoulder','Friday – Arms'],
      6:['Monday – Chest','Tuesday – Back','Wednesday – Legs','Thursday – Shoulder','Friday – Arms','Saturday – Full Body'],
    },
    gain:{
      3:['Monday – Full Body','Wednesday – Full Body','Friday – Full Body'],
      4:['Monday – Chest','Tuesday – Back','Thursday – Legs','Friday – Full Body'],
      5:['Monday – Chest','Tuesday – Back','Wednesday – Legs','Thursday – Shoulder','Friday – Arms'],
      6:['Monday – Chest','Tuesday – Back','Wednesday – Legs','Thursday – Shoulder','Friday – Arms','Saturday – Full Body'],
    }
  };
  return splits[goal][days] || splits[goal][4];
}

// Protein targets by goal + gender + age
function calcProtein(weight, goal, gender, age){
  let base;
  if(goal === 'loss')   base = gender==='male' ? 2.0   : 1.8;
  if(goal === 'muscle') base = gender==='male' ? 2.2   : 2.0;
  if(goal === 'gain')   base = gender==='male' ? 2.0   : 1.8;
  // Age adjustment: seniors need slightly more, teens slightly less
  if(age >= 50) base += 0.1;
  if(age < 18)  base -= 0.1;
  return { min: Math.round(weight*(base-0.2)), max: Math.round(weight*base), per100: Math.round(base*100)/100 };
}

function getIntensityLabel(level){
  if(level==='beginner')    return '<span class="intensity-pill beginner">🟢 Beginner</span>';
  if(level==='intermediate') return '<span class="intensity-pill intermediate">🟡 Intermediate</span>';
  return '<span class="intensity-pill advanced">🔴 Advanced</span>';
}

function generatePlan(){
  const age    = +document.getElementById('planAge').value;
  const gender = document.getElementById('planGender').value;
  const weight = +document.getElementById('planWeight').value;
  const goal   = document.getElementById('planGoal').value;
  const level  = document.getElementById('planLevel').value;
  const days   = +document.getElementById('planDays').value;
  const custom = document.getElementById('planSplitInput').value.trim();

  if(!age || !weight){ 
    document.getElementById('planMsg').innerHTML = '<span class="badge red">⚠️ Please fill Age and Weight</span>';
    return;
  }

  // Parse split lines
  let lines;
  if(custom){
    lines = custom.split('\n').map(l=>l.trim()).filter(l=>l);
  } else {
    lines = defaultSplit(goal, days);
  }

  const protein = calcProtein(weight, goal, gender, age);
  const goalLabel = goal==='loss'?'Fat Loss':goal==='muscle'?'Muscle Gain':'Weight Gain';

  // BMR / calorie estimate
  const bmr  = gender==='male'
    ? (10*weight) + (6.25*170) - (5*age) + 5
    : (10*weight) + (6.25*160) - (5*age) - 161;
  const tdee = Math.round(bmr * 1.55);
  const calTarget = goal==='loss' ? tdee-400 : goal==='gain'||goal==='muscle' ? tdee+400 : tdee;
  const carbs = goal==='loss' ? Math.round(weight*2.5) : goal==='muscle' ? Math.round(weight*4.5) : Math.round(weight*4);

  // Save to profile
  profile = { ...profile, age, gender, planGoal:goal, level };
  localStorage.setItem('lvProfile', JSON.stringify(profile));

  // Stat cards
  document.getElementById('plannerStats').innerHTML = `
    <div class="plan-stat"><div class="ps-val">${age}</div><div class="ps-label">Age</div></div>
    <div class="plan-stat"><div class="ps-val">${gender==='male'?'♂ Male':'♀ Female'}</div><div class="ps-label">Gender</div></div>
    <div class="plan-stat"><div class="ps-val">${weight}kg</div><div class="ps-label">Body Weight</div></div>
    <div class="plan-stat"><div class="ps-val">${goalLabel}</div><div class="ps-label">Goal</div></div>
    <div class="plan-stat"><div class="ps-val">${level.charAt(0).toUpperCase()+level.slice(1)}</div><div class="ps-label">Level</div></div>
    <div class="plan-stat"><div class="ps-val">${days} days</div><div class="ps-label">Per Week</div></div>
  `;

  // Build split day cards
  const splitEl = document.getElementById('splitCards');
  splitEl.innerHTML = '';
  lines.forEach((line, i) => {
    const dayLabel = parseDayLabel(line);
    const muscle   = parseMuscle(line);

    if(!muscle || muscle === 'REST'){
      splitEl.innerHTML += `
        <div class="split-day">
          <div class="split-day-header">
            <span class="day-name">${dayLabel}</span>
            <span class="day-focus">😴 Rest & Recovery</span>
            <span class="day-badge badge" style="background:var(--sub);color:var(--muted);border:1px solid var(--border)">REST DAY</span>
          </div>
          <div style="padding:14px 16px;color:var(--muted);font-size:13px">
            Active recovery: light walk, stretching, foam rolling. Aim for 7–8 hours of sleep. Drink 2–3L water. 💤
          </div>
        </div>`;
      return;
    }

    const exList = (EXERCISE_LIB[muscle] || EXERCISE_LIB['Full Body'])[level] || [];
    const rows   = exList.map((ex,j) => `
      <tr>
        <td style="color:var(--muted);font-size:11px;width:28px">${j+1}</td>
        <td style="font-weight:700">${ex.name}</td>
        <td style="color:var(--yellow);font-weight:700;text-align:center">${ex.sets}</td>
        <td style="text-align:center">${ex.reps}</td>
        <td style="text-align:center;color:var(--muted)">${ex.rest}</td>
        <td>${getIntensityLabel(level)}</td>
      </tr>`).join('');

    splitEl.innerHTML += `
      <div class="split-day">
        <div class="split-day-header" onclick="this.nextElementSibling.style.display=this.nextElementSibling.style.display==='none'?'block':'none'">
          <span class="day-name">${dayLabel}</span>
          <span class="day-focus">🏋️ ${muscle}</span>
          <span class="day-badge badge green">${exList.length} exercises</span>
        </div>
        <div style="overflow-x:auto">
          <table class="exercise-table">
            <thead><tr><th>#</th><th>Exercise</th><th>Sets</th><th>Reps</th><th>Rest</th><th>Intensity</th></tr></thead>
            <tbody>${rows}</tbody>
          </table>
        </div>
      </div>`;
  });

  // Nutrition guide
  const genderNote = gender==='male'
    ? 'As a <b>Male</b>, aim for the <b>upper range</b> of protein to maximise muscle protein synthesis.'
    : 'As a <b>Female</b>, the <b>mid range</b> of protein is ideal — your hormonal profile still benefits greatly from adequate protein.';
  const ageNote = age < 18
    ? '⚡ <b>Teen tip:</b> Your body is still growing — prioritise compound movements, sleep 8–9hrs & avoid max-effort lifts.'
    : age >= 50
    ? '⚡ <b>50+ tip:</b> Prioritise joint health, add mobility work. Slightly higher protein (2.0–2.2g/kg) helps combat age-related muscle loss.'
    : '';

  document.getElementById('nutritionGuide').innerHTML = `
    <h3>🥗 Personalised Nutrition — ${userName||'Champion'} (${gender==='male'?'Male':'Female'}, Age ${age})</h3>
    <div class="grid" style="margin:14px 0">
      <div style="background:var(--sub);border-radius:10px;padding:14px;border:1px solid var(--border)">
        <div style="font-size:11px;color:var(--muted);font-weight:700">PROTEIN TARGET</div>
        <div style="font-size:24px;font-weight:800;color:var(--red);margin-top:4px">${protein.min}–${protein.max}g<span style="font-size:14px;color:var(--muted)">/day</span></div>
        <div style="font-size:12px;color:var(--muted);margin-top:3px">${protein.per100}g per kg bodyweight</div>
      </div>
      <div style="background:var(--sub);border-radius:10px;padding:14px;border:1px solid var(--border)">
        <div style="font-size:11px;color:var(--muted);font-weight:700">CARBS TARGET</div>
        <div style="font-size:24px;font-weight:800;color:var(--yellow);margin-top:4px">${carbs}g<span style="font-size:14px;color:var(--muted)">/day</span></div>
        <div style="font-size:12px;color:var(--muted);margin-top:3px">Primary energy source</div>
      </div>
      <div style="background:var(--sub);border-radius:10px;padding:14px;border:1px solid var(--border)">
        <div style="font-size:11px;color:var(--muted);font-weight:700">CALORIES TARGET</div>
        <div style="font-size:24px;font-weight:800;color:var(--green);margin-top:4px">${calTarget}<span style="font-size:14px;color:var(--muted)">kcal</span></div>
        <div style="font-size:12px;color:var(--muted);margin-top:3px">${goal==='loss'?'Deficit -400 kcal':goal==='gain'||goal==='muscle'?'Surplus +400 kcal':'Maintenance'}</div>
      </div>
      <div style="background:var(--sub);border-radius:10px;padding:14px;border:1px solid var(--border)">
        <div style="font-size:11px;color:var(--muted);font-weight:700">WATER GOAL</div>
        <div style="font-size:24px;font-weight:800;color:var(--blue);margin-top:4px">3–4L<span style="font-size:14px;color:var(--muted)">/day</span></div>
        <div style="font-size:12px;color:var(--muted);margin-top:3px">More on workout days</div>
      </div>
    </div>
    <div style="font-size:13px;line-height:1.8;color:var(--muted)">
      ${genderNote}<br>
      ${ageNote ? ageNote+'<br>' : ''}
      <b style="color:var(--text)">Goal:</b> ${goalLabel} &nbsp;|&nbsp; 
      <b style="color:var(--text)">Level:</b> ${level} &nbsp;|&nbsp; 
      <b style="color:var(--text)">Frequency:</b> ${days}x / week<br>
      <b style="color:var(--text)">Tip:</b> Spread your protein across 4–5 meals. Include Indian sources like paneer, dal, eggs, chicken & soya chunks for best results. 💪
    </div>`;

  document.getElementById('planOutput').style.display = 'block';
  document.getElementById('planMsg').innerHTML = '<span class="badge green">✔ Plan Generated!</span>';
  document.getElementById('planOutput').scrollIntoView({ behavior:'smooth' });
}

function clearPlan(){
  document.getElementById('planSplitInput').value = '';
  document.getElementById('planOutput').style.display = 'none';
  document.getElementById('planMsg').innerHTML = '';
}

// ════════════════════════════════
// UPGRADE AI SYSTEM PROMPT (inline in sendChat)
// ════════════════════════════════
// (handled inside sendChat below — replace the sys string)
function addMsg(text, role){
  const box = document.getElementById('chatBox');
  const div = document.createElement('div');
  div.className = 'msg ' + role;
  div.innerHTML = text.replace(/\n/g,'<br>');
  box.appendChild(div);
  box.scrollTop = box.scrollHeight;
}
function addTyping(){
  const box = document.getElementById('chatBox');
  const div = document.createElement('div');
  div.className = 'msg ai typing'; div.id = 'typingMsg';
  div.textContent = 'Coach is thinking…';
  box.appendChild(div); box.scrollTop = box.scrollHeight;
}
function removeTyping(){ const t = document.getElementById('typingMsg'); if(t) t.remove(); }

async function sendChat(){
  const inp = document.getElementById('chatInput');
  const msg = inp.value.trim(); if(!msg) return;
  inp.value = '';
  addMsg(msg, 'user');
  chatHist.push({ role:'user', content:msg });

  const age    = profile.age    || '?';
  const gender = profile.gender || '?';
  const level  = profile.level  || 'beginner';
  const pCtx   = profile.w
    ? `User: Name=${userName||'Champion'}, Age=${age}, Gender=${gender}, Weight=${profile.w}kg, Height=${profile.h}cm, Goal=${profile.goal}, Level=${level}.`
    : `User name: ${userName||'Champion'}.`;

  const sys = `You are LEVELUP – an elite Indian Fitness Coach AI. You coach like a knowledgeable, motivating personal trainer from India.
${pCtx}

════ YOUR CORE ROLE ════
1. Track Indian food & calculate Protein/Carbs/Calories
2. Compare with personalised daily targets
3. Build detailed weekly workout splits
4. Adjust ALL recommendations by AGE + GENDER + GOAL + EXPERIENCE LEVEL
5. Motivate daily — use the user's name every response

════ STEP 1 — USER PROFILE ════
If you don't have full details, ask:
• Age | Gender | Height (cm) | Weight (kg) | Goal (Fat Loss / Muscle Gain / Weight Gain) | Experience Level (Beginner/Intermediate/Advanced) | Workout Days Per Week

After getting details, calculate:
• BMI = weight/(height_m²)
• BMR (Mifflin-St Jeor): Male = 10W+6.25H-5A+5 | Female = 10W+6.25H-5A-161
• TDEE = BMR × 1.55

════ STEP 2 — PROTEIN BY GENDER + AGE ════
Fat Loss:    Male = 2.0g/kg (upper), Female = 1.8g/kg (mid)
Muscle Gain: Male = 2.2g/kg (upper), Female = 2.0g/kg (mid)
Weight Gain: Male = 2.0g/kg (upper), Female = 1.8g/kg (mid)
Age adjustments:
• Under 18: reduce by 0.1g/kg (still developing)
• 50+: increase by 0.1g/kg (combats muscle loss)
Always show: Daily Calories | Protein (g) | Carbs (g) | Water (L)

Calories:
• Fat Loss: TDEE – 400 kcal
• Muscle Gain: TDEE + 400 kcal
• Weight Gain: TDEE + 500 kcal

════ STEP 3 — WORKOUT SPLIT BUILDER ════
When user types their weekly split (e.g. "Monday – Chest, Tuesday – Back"), generate:
• Proper exercise ORDER for that muscle
• Sets & Reps based on level:
  - Beginner: 3 sets × 12–15 reps, 60s rest, compound first
  - Intermediate: 4 sets × 8–12 reps, 75–90s rest
  - Advanced: 5 sets × 5–8 reps, 2–3min rest, periodised
• Intensity level label (Beginner/Intermediate/Advanced)
• Rest time between sets
• Show as structured table: Exercise | Sets | Reps | Rest | Intensity

Sample exercises per muscle:
CHEST: Bench Press → Incline Press → Dips → Cable Flyes → Pec Deck
BACK: Pull-Ups → Barbell Row → Seated Row → Lat Pulldown → Face Pulls
LEGS: Squat → Romanian DL → Leg Press → Lunges → Leg Curl → Calf Raises
SHOULDERS: OHP → Lateral Raises → Arnold Press → Rear Delt Flyes
ARMS: Barbell Curl → Incline DB Curl → Hammer Curl → Skull Crushers → Tricep Pushdown
ABS: Hanging Leg Raises → Cable Crunch → Plank → Ab Wheel

Default splits by goal:
• Fat Loss 4-day: Full Body → Cardio/Upper → Full Body → Cardio/Lower
• Muscle Gain 5-day: Chest+Tri → Back+Bi → Legs → Shoulders → Arms+Abs
• Weight Gain 3-day: Full Body → Full Body → Full Body
• Beginners: Always compound movements first, lower volume

Age-specific notes:
• Teens (<18): Avoid max-effort lifts, prioritise form & compound movements
• 50+: Add mobility work, joint-friendly exercises, longer rest

════ STEP 4 — INDIAN FOOD TRACKER ════
South Indian: Idli(1)=2g P,14g C | Dosa(1)=3g,18g | Upma(1cup)=5g,32g | Sambar(1cup)=7g,18g | Curd Rice(1cup)=6g,38g | Pongal(1cup)=6g,35g
North Indian: Chapati(1)=3g,15g | Paratha(1)=4g,30g | Brown Rice(1cup)=5g,45g | Dal(1cup)=11g,30g | Rajma(1cup)=14g,40g | Paneer(100g)=20g,6g | Chole(1cup)=15g,45g
Veg Proteins: Soya Chunks(50g)=26g | Sprouts(1cup)=14g | Curd(1cup)=8g | Milk(1glass)=8g | Greek Yogurt(1cup)=15g | Almonds(10)=6g | Tofu(100g)=10g | PB(1tbsp)=4g
Non-Veg: Egg(1)=6g | Chicken Breast(100g)=31g | Fish(100g)=22g | Tuna(100g)=30g | Prawns(100g)=24g | Mutton(100g)=26g

When user says "Today I ate…":
Show table: Food Item | Qty | Protein | Carbs
Then: TOTAL | — | Xg | Xg
Compare: "You hit X% of your protein goal."
If <70% protein: suggest paneer, eggs, soya chunks, sprouts
If carbs too high (fat loss): suggest brown rice, reduce paratha

════ RESPONSE STYLE ════
• Always use ${userName||'Champion'}'s name
• Friendly, energetic Indian trainer tone
• Tables for food/workout data
• Clear numbers always
• Suggest both veg & non-veg options
• Always remind hydration (3–4L water)
• End every reply with a personalised motivational line! 💪🔥`;

  addTyping();
  try{
    const res = await fetch('https://api.anthropic.com/v1/messages', {
      method:'POST',
      headers:{'Content-Type':'application/json'},
      body: JSON.stringify({ model:'claude-sonnet-4-20250514', max_tokens:1000, system:sys, messages:chatHist.slice(-12) })
    });
    const d     = await res.json();
    const reply = d.content?.map(c => c.text||'').join('\n') || 'Sorry, please try again.';
    removeTyping();
    addMsg(reply, 'ai');
    chatHist.push({ role:'assistant', content:reply });
    localStorage.setItem('lvChat', JSON.stringify(chatHist.slice(-30)));
    if(voiceOn) speak(reply.replace(/<[^>]+>/g,'').replace(/[*_#|]/g,'').slice(0, 280));
  } catch(e){
    removeTyping();
    addMsg('⚠️ Network error. Please try again.', 'ai');
  }
}

// ════════════════════════════════
// VOICE
// ════════════════════════════════
function toggleVoice(){
  voiceOn = !voiceOn;
  const btn = document.getElementById('voiceBtn');
  btn.textContent = voiceOn ? '🔊 Voice ON' : '🎙️ Voice Off';
  btn.className   = voiceOn ? 'hbtn on' : 'hbtn';
  if(voiceOn) speak('Voice mode activated. Ready to help you, ' + userName + '!');
}

function speak(text){
  if(!voiceOn || !window.speechSynthesis) return;
  window.speechSynthesis.cancel();
  const utt   = new SpeechSynthesisUtterance(text);
  utt.rate    = 1.05; utt.pitch = 1.05; utt.volume = 1;
  const voices = window.speechSynthesis.getVoices();
  const pref  = voices.find(v => v.lang.startsWith('en') && /male/i.test(v.name))
             || voices.find(v => v.lang.startsWith('en'))
             || voices[0];
  if(pref) utt.voice = pref;
  window.speechSynthesis.speak(utt);
}

function toggleVoiceChat(){
  const SR = window.SpeechRecognition || window.webkitSpeechRecognition;
  if(!SR){ alert('Voice not supported in this browser. Try Chrome!'); return; }
  const btn    = document.getElementById('micBtn');
  const status = document.getElementById('voiceStatus');
  if(isRecording){ if(recog) recog.stop(); return; }
  recog = new SR();
  recog.lang = 'en-IN';
  recog.continuous = false;
  recog.interimResults = true;
  isRecording = true;
  btn.classList.add('rec');
  status.textContent = '🎙️ Listening… speak now';
  recog.onresult = e => {
    const t = Array.from(e.results).map(r => r[0].transcript).join('');
    document.getElementById('chatInput').value = t;
    if(e.results[e.results.length-1].isFinal) status.textContent = '✅ Got it!';
  };
  recog.onend = () => {
    isRecording = false;
    btn.classList.remove('rec');
    setTimeout(() => status.textContent = '', 2000);
    const val = document.getElementById('chatInput').value.trim();
    if(val) sendChat();
  };
  recog.onerror = e => {
    isRecording = false;
    btn.classList.remove('rec');
    status.textContent = '❌ ' + e.error;
  };
  recog.start();
}

// ════════════════════════════════
// REMINDERS
// ════════════════════════════════
function showToast(msg, duration=5000){
  const t = document.getElementById('toast');
  document.getElementById('toastMsg').textContent = msg;
  t.style.display = 'block';
  clearTimeout(t._timer);
  t._timer = setTimeout(closeToast, duration);
  if(voiceOn) speak(msg);
}
function closeToast(){ document.getElementById('toast').style.display = 'none'; }

function requestReminder(){
  if(!('Notification' in window)){ alert('Notifications not supported. The in-app reminders will still work!'); scheduleInAppReminders(); return; }
  Notification.requestPermission().then(perm => {
    if(perm === 'granted'){
      scheduleReminders();
      alert('✅ Reminders enabled!\nYou will get gym reminders at 7 AM, 12 PM and 6 PM daily.');
    } else {
      scheduleInAppReminders();
      alert('Browser notifications denied. In-app toast reminders are still active!');
    }
  });
}

const REMINDER_MSGS = [
  () => `Time to hit the gym, ${userName}! 💪 Don't break your streak!`,
  () => `${userName}, your muscles are calling! 🏋️ Go train!`,
  () => `Hey ${userName}! 🔥 Champions don't skip. Log your workout!`,
  () => `${userName}, every rep counts! ⚡ Let's go!`,
];

function fireReminder(){
  const msg = REMINDER_MSGS[Math.floor(Math.random()*REMINDER_MSGS.length)]();
  if(typeof Notification !== 'undefined' && Notification.permission === 'granted'){
    new Notification('⚡ LEVELUP', { body: msg });
  }
  showToast(msg);
}

function scheduleReminders(){
  const now   = new Date();
  const times = [{h:7,m:0},{h:12,m:0},{h:18,m:0}];
  times.forEach(t => {
    const rem = new Date(now.getFullYear(), now.getMonth(), now.getDate(), t.h, t.m, 0);
    if(rem > now) setTimeout(fireReminder, rem - now);
    // schedule for tomorrow too
    const tom = new Date(now.getFullYear(), now.getMonth(), now.getDate()+1, t.h, t.m, 0);
    setTimeout(fireReminder, tom - now);
  });
}

function scheduleInAppReminders(){
  // Fire every 4 hours if page is open
  setInterval(fireReminder, 4 * 3600 * 1000);
}

// Show welcome toast if not logged today
window.addEventListener('load', () => {
  setTimeout(() => {
    if(!data[today] && userName){
      showToast(`⚡ Welcome back ${userName}! You haven't logged today yet 💪`, 4500);
    }
  }, 2500);
});

// ════════════════════════════════
// RENDER ALL
// ════════════════════════════════
function renderAll(){
  document.getElementById('todayStatus').textContent = data[today] ? 'Logged ✔' : 'Not logged';
  renderCalendar(); calcStreak(); calcWeekly();
  renderWater(); renderTodayLog(); renderNotesHistory(); renderPRs();
}

// ════════════════════════════════
// INIT
// ════════════════════════════════
if(profile.h){
  document.getElementById('heightCm').value    = profile.h;
  document.getElementById('bodyWeightKg').value = profile.w;
  document.getElementById('goalType').value     = profile.goal;
  calcBMI();
}
initWater();
renderAll();

// Load voices for speech
window.speechSynthesis.onvoiceschanged = () => window.speechSynthesis.getVoices();

// Chat init
if(chatHist.length){
  chatHist.forEach(m => addMsg(m.content, m.role==='user'?'user':'ai'));
} else {
  addMsg(`Namaste${userName?' '+userName:''}! 🙏 I'm your LEVELUP AI Coach.\n\nI'm here to:\n✅ Track your Indian food & calculate protein/carbs\n✅ Build a personalized workout plan\n✅ Motivate you every single day!\n\nTell me your Age, Weight, Height & Goal to get started — or just say what you ate today! 💪🔥`, 'ai');
}
</script>
</body>
</html>
