<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>شات وألعاب خاصة</title>
  <style>
    :root{
      --bg:#120814; --card:rgba(255,255,255,.11); --text:#fff7fb; --muted:#dcc9d8;
      --pink:#ff5fa2; --purple:#8d5cff; --gold:#ffd166; --green:#67f2bc; --danger:#ff6b6b;
      --shadow:0 22px 70px rgba(0,0,0,.35); --radius:28px;
    }
    *{box-sizing:border-box}
    body{
      margin:0; min-height:100vh; font-family:Tahoma,Arial,sans-serif; color:var(--text);
      background:
        radial-gradient(circle at 8% 10%,rgba(255,95,162,.35),transparent 35%),
        radial-gradient(circle at 92% 18%,rgba(141,92,255,.38),transparent 36%),
        radial-gradient(circle at 50% 100%,rgba(255,209,102,.18),transparent 42%),
        linear-gradient(145deg,#120814,#251038 52%,#120814);
      overflow-x:hidden;
    }
    button,input,select,textarea{font-family:inherit}
    button{
      border:0; cursor:pointer; color:white; border-radius:18px; padding:12px 16px; font-weight:900;
      background:linear-gradient(135deg,var(--pink),var(--purple));
      box-shadow:0 12px 26px rgba(255,95,162,.20); transition:.16s;
    }
    button:hover{transform:translateY(-2px); filter:saturate(1.1)}
    button.secondary{background:rgba(255,255,255,.12); border:1px solid rgba(255,255,255,.16); box-shadow:none}
    button.danger{background:linear-gradient(135deg,#ff6b6b,#d63b72)}
    button.green{background:linear-gradient(135deg,var(--green),#24c6dc); color:#06261f}
    button.gold{background:linear-gradient(135deg,#ffd166,#ff9f68); color:#271406}
    button.small{padding:8px 10px; border-radius:13px; font-size:12px}
    input,select,textarea{
      width:100%; outline:none; border:1px solid rgba(255,255,255,.16); background:rgba(0,0,0,.22);
      color:white; border-radius:18px; padding:13px 14px; font-size:15px;
    }
    textarea{min-height:110px; resize:vertical; line-height:1.8}
    label{display:block; color:#ffe5f1; font-weight:900; line-height:2}
    .wrap{max-width:1280px; margin:auto; padding:18px; position:relative; z-index:1}
    .app{display:grid; grid-template-columns:320px 1fr; gap:16px; align-items:start; min-height:100vh}
    .side,.main-card,.panel,.tile{
      background:linear-gradient(145deg,rgba(255,255,255,.145),rgba(255,255,255,.075));
      border:1px solid rgba(255,255,255,.16); box-shadow:var(--shadow); backdrop-filter:blur(18px); border-radius:var(--radius);
    }
    .side{position:sticky; top:14px; padding:16px; display:grid; gap:12px}
    .logo{
      padding:18px; border-radius:24px;
      background:radial-gradient(circle at 20% 10%,rgba(255,95,162,.35),transparent 42%),rgba(0,0,0,.18);
      border:1px solid rgba(255,255,255,.12);
    }
    .logo h1{
      margin:0; font-size:32px; line-height:1.1;
      background:linear-gradient(90deg,#fff,#ff9eca,#ffd166); -webkit-background-clip:text; background-clip:text; color:transparent;
    }
    .logo p{margin:9px 0 0; color:var(--muted); line-height:1.7; font-size:13px}
    .status{display:flex; justify-content:space-between; align-items:center; gap:10px; padding:12px; border-radius:18px; background:rgba(0,0,0,.2); color:var(--muted); font-size:13px}
    .dot{display:inline-block; width:10px; height:10px; border-radius:50%; background:#777; margin-left:6px}
    .dot.on{background:var(--green); box-shadow:0 0 14px rgba(103,242,188,.6)}
    .profile{display:grid; gap:10px; padding:14px; border-radius:22px; background:rgba(0,0,0,.18); border:1px solid rgba(255,255,255,.11)}
    .players,.list{display:grid; gap:8px}
    .player,.list-item{
      display:flex; justify-content:space-between; align-items:center; gap:10px; padding:11px; border-radius:16px;
      background:rgba(255,255,255,.09); border:1px solid rgba(255,255,255,.09); line-height:1.6
    }
    .score{font-weight:900; color:var(--gold)}
    .small-text{font-size:12px; color:var(--muted)}
    .main-card{padding:14px; min-height:94vh}
    .tabs{
      display:flex; gap:8px; overflow:auto; padding:9px; border-radius:24px; background:rgba(18,8,20,.68);
      border:1px solid rgba(255,255,255,.12); backdrop-filter:blur(16px); position:sticky; top:12px; z-index:10; margin-bottom:12px;
    }
    .tabs button{white-space:nowrap; background:rgba(255,255,255,.1); box-shadow:none; border:1px solid rgba(255,255,255,.12); padding:10px 13px; font-size:13px}
    .tabs button.active{background:linear-gradient(135deg,var(--pink),var(--purple))}
    .hidden{display:none!important}
    .grid{display:grid; grid-template-columns:repeat(12,1fr); gap:12px}
    .panel{padding:18px}
    .span-12{grid-column:span 12}.span-8{grid-column:span 8}.span-6{grid-column:span 6}.span-4{grid-column:span 4}.span-3{grid-column:span 3}
    .tile{padding:18px; min-height:145px; display:flex; flex-direction:column; justify-content:center; cursor:pointer; font-size:34px; transition:.16s}
    .tile:hover{transform:translateY(-3px)}
    .tile b{font-size:18px; margin-top:10px}
    .tile span{font-size:13px; color:var(--muted); margin-top:6px}
    h2,h3{margin-top:0}
    p{color:var(--muted); line-height:1.85}
    .actions{display:flex; flex-wrap:wrap; gap:9px; margin:12px 0}
    .result{
      min-height:92px; border-radius:22px; background:rgba(0,0,0,.20); border:1px dashed rgba(255,255,255,.2);
      padding:16px; color:#fff; line-height:1.9; display:flex; align-items:center; justify-content:center; text-align:center; white-space:pre-wrap; margin:12px 0;
    }
    .result.big{font-size:22px; min-height:132px}
    .chat-card{height:78vh; display:grid; grid-template-rows:auto 1fr auto; gap:10px}
    .chat{overflow:auto; display:flex; flex-direction:column; gap:10px; padding:12px; border-radius:24px; background:rgba(0,0,0,.17); border:1px solid rgba(255,255,255,.09)}
    .empty{margin:auto; text-align:center; color:var(--muted); line-height:1.8; padding:30px}
    .msg{max-width:78%; padding:12px 14px; border-radius:20px; background:rgba(255,255,255,.11); border:1px solid rgba(255,255,255,.10); line-height:1.75; animation:pop .14s ease; word-break:break-word}
    .msg.me{margin-right:auto; background:rgba(255,95,162,.18); border-color:rgba(255,95,162,.25)}
    .msg.other{margin-left:auto; background:rgba(141,92,255,.18); border-color:rgba(141,92,255,.25)}
    .msg-head{display:flex; align-items:center; gap:8px; margin-bottom:5px; font-weight:900; color:#fff; font-size:14px}
    .msg small{display:block; margin-top:5px; color:var(--muted); font-size:12px}
    .composer{display:grid; grid-template-columns:1fr auto; gap:10px}
    .wheel-wrap{text-align:center}
    .pointer{font-size:38px; margin-bottom:-22px; filter:drop-shadow(0 8px 12px rgba(0,0,0,.35))}
    .wheel{
      width:min(320px,76vw); height:min(320px,76vw); border-radius:50%; margin:auto auto 18px;
      background:conic-gradient(#ff5fa2 0 30deg,#8d5cff 30deg 60deg,#ffd166 60deg 90deg,#7cf7c2 90deg 120deg,#ff89c0 120deg 150deg,#b896ff 150deg 180deg,#ff9f68 180deg 210deg,#61f2bd 210deg 240deg,#ff5fa2 240deg 270deg,#8d5cff 270deg 300deg,#ffd166 300deg 330deg,#7cf7c2 330deg 360deg);
      border:10px solid rgba(255,255,255,.18); box-shadow:0 25px 70px rgba(0,0,0,.3),inset 0 0 40px rgba(255,255,255,.15);
      transition:transform 4s cubic-bezier(.13,.78,.19,1); position:relative;
    }
    .wheel:after{content:"💘"; position:absolute; inset:50% auto auto 50%; transform:translate(-50%,-50%); width:86px; height:86px; border-radius:50%; background:rgba(18,8,20,.82); display:grid; place-items:center; font-size:38px; border:1px solid rgba(255,255,255,.22)}
    .xo-board{display:grid; grid-template-columns:repeat(3,1fr); gap:9px; max-width:360px; margin:auto}
    .cell{height:100px; border-radius:22px; background:rgba(255,255,255,.11); border:1px solid rgba(255,255,255,.14); display:grid; place-items:center; font-size:46px; cursor:pointer}
    .memory-board{display:grid; grid-template-columns:repeat(auto-fit,minmax(92px,1fr)); gap:10px; margin-top:14px}
    .memory-card{aspect-ratio:1/1; border-radius:20px; background:rgba(255,255,255,.12); border:1px solid rgba(255,255,255,.14); display:grid; place-items:center; font-size:34px; cursor:pointer; user-select:none}
    .memory-card.matched{background:rgba(103,242,188,.20); border-color:rgba(103,242,188,.40)}
    .options{display:grid; gap:10px; margin:14px 0}
    .option{text-align:right; background:rgba(255,255,255,.11); box-shadow:none; border:1px solid rgba(255,255,255,.12)}
    .option.selected{background:rgba(103,242,188,.22)}
    .progress{height:12px; border-radius:999px; background:rgba(255,255,255,.12); overflow:hidden}
    .progress span{display:block; width:0; height:100%; border-radius:999px; background:linear-gradient(90deg,var(--pink),var(--gold)); transition:.2s}
    .emoji{font-size:54px; letter-spacing:10px}
    .poll-row{display:grid; grid-template-columns:1fr auto; gap:8px; align-items:center; margin:8px 0}
    .bar{height:12px; border-radius:999px; background:rgba(255,255,255,.12); overflow:hidden}
    .bar span{display:block; height:100%; border-radius:999px; background:linear-gradient(90deg,var(--pink),var(--gold)); width:0}
    canvas#drawCanvas{width:100%; height:400px; display:block; border-radius:24px; background:white; touch-action:none}
    .toast{position:fixed; left:20px; bottom:20px; background:rgba(18,8,20,.94); border:1px solid rgba(255,255,255,.16); color:#fff; padding:14px 16px; border-radius:18px; box-shadow:var(--shadow); transform:translateY(140%); transition:.22s; z-index:20; max-width:380px; line-height:1.7}
    .toast.show{transform:translateY(0)}
    .hearts{position:fixed; inset:0; pointer-events:none; overflow:hidden; z-index:0}
    .heart{position:absolute; bottom:-80px; font-size:22px; opacity:.25; animation:floatHeart linear infinite}
    @keyframes floatHeart{0%{transform:translateY(0) rotate(0deg) scale(.8);opacity:0}10%{opacity:.28}100%{transform:translateY(-115vh) rotate(360deg) scale(1.35);opacity:0}}
    @keyframes pop{from{transform:scale(.97);opacity:.5}to{transform:scale(1);opacity:1}}
    @media(max-width:1050px){
      .app{grid-template-columns:1fr}.side{position:static}.span-8,.span-6,.span-4,.span-3{grid-column:span 12}.tile{min-height:120px}.chat-card{height:72vh}
    }
    @media(max-width:650px){
      .wrap{padding:10px}.main-card,.side{padding:10px}.composer{grid-template-columns:1fr}.msg{max-width:92%}.cell{height:82px}.chat-card{height:75vh}
    }
  </style>
</head>
<body>
  <div class="hearts" id="hearts"></div>
  <main class="wrap">
    <div class="app">
      <aside class="side">
        <div class="logo">
          <h1>شاتنا وألعابنا 💞</h1>
          <p>بدون رومات. شات واحد خاص + فعاليات وألعاب كثيرة تتحدث مباشرة عندكم الاثنين.</p>
        </div>

        <div class="status">
          <span><span class="dot" id="statusDot"></span><span id="statusText">جاري الاتصال...</span></span>
          <button class="small secondary" onclick="requestNotify()">إشعارات</button>
        </div>

        <div class="profile">
          <label>اسمك <input id="nameInput" maxlength="30" placeholder="اكتب اسمك"></label>
          <label>رمزك
            <select id="avatarInput">
              <option>💖</option><option>🌙</option><option>✨</option><option>🫶</option><option>🧸</option><option>☕</option><option>🎧</option><option>🍓</option>
            </select>
          </label>
          <button onclick="saveProfile()">حفظ الاسم</button>
        </div>

        <div class="panel">
          <h3>المتصلين والنقاط</h3>
          <div class="players" id="playersList"></div>
        </div>

        <div class="panel">
          <h3>آخر فعالية</h3>
          <div class="small-text" id="lastActivity">جاهز</div>
          <div class="small-text">عدد الفعاليات: <b id="doneCount">0</b></div>
        </div>
      </aside>

      <section class="main-card">
        <nav class="tabs">
          <button class="active" onclick="showTab('homeTab')">الرئيسية</button>
          <button onclick="showTab('chatTab')">الشات</button>
          <button onclick="showTab('cardsTab')">بطاقات</button>
          <button onclick="showTab('wheelTab')">العجلة</button>
          <button onclick="showTab('xoTab')">إكس أو</button>
          <button onclick="showTab('memoryTab')">الذاكرة</button>
          <button onclick="showTab('quizTab')">التوافق</button>
          <button onclick="showTab('emojiTab')">إيموجي</button>
          <button onclick="showTab('pollTab')">تصويت</button>
          <button onclick="showTab('dateTab')">مواعيد</button>
          <button onclick="showTab('drawTab')">رسم</button>
          <button onclick="showTab('notesTab')">وعود</button>
        </nav>

        <section class="tab" id="homeTab">
          <div class="grid">
            <div class="panel span-8">
              <h2>جاهز للفعاليات؟ ✨</h2>
              <p>كل زر تضغطه يتغير عند الطرف الثاني مباشرة. تقدرون تشاتون وتلعبون بنفس الوقت بدون رومات.</p>
              <div class="actions">
                <button onclick="randomActivity()">فعالية عشوائية</button>
                <button class="green" onclick="completeActivity('فعالية عشوائية',10)">خلصناها +10</button>
                <button class="gold" onclick="loveLetter()">رسالة حب</button>
              </div>
              <div class="result big" id="homeResult">اضغط فعالية عشوائية أو رسالة حب.</div>
            </div>
            <div class="panel span-4">
              <h3>إنجازاتك</h3>
              <div class="list" id="achievements"></div>
            </div>
            <div class="tile span-3" onclick="showTab('chatTab')">💬<b>شات</b><span>رسائل وتنبيهات</span></div>
            <div class="tile span-3" onclick="showTab('cardsTab')">💌<b>بطاقات</b><span>أسئلة وتحديات</span></div>
            <div class="tile span-3" onclick="showTab('wheelTab')">🎡<b>عجلة</b><span>حظ وفعاليات</span></div>
            <div class="tile span-3" onclick="showTab('xoTab')">❌<b>إكس أو</b><span>لعب مباشر</span></div>
            <div class="tile span-3" onclick="showTab('memoryTab')">🃏<b>ذاكرة</b><span>تطابق كروت</span></div>
            <div class="tile span-3" onclick="showTab('quizTab')">🧠<b>توافق</b><span>اختبار مشترك</span></div>
            <div class="tile span-3" onclick="showTab('emojiTab')">🎭<b>إيموجي</b><span>خمن اللغز</span></div>
            <div class="tile span-3" onclick="showTab('drawTab')">🎨<b>رسم</b><span>لوحة مشتركة</span></div>
          </div>
        </section>

        <section class="tab hidden" id="chatTab">
          <div class="panel chat-card">
            <div><h2>الشات الخاص</h2><p>رسالة توصل للطرف الثاني مع إشعار.</p></div>
            <div class="chat" id="chatBox"><div class="empty" id="emptyText">لا توجد رسائل بعد.<br>اكتب أول رسالة.</div></div>
            <div class="composer">
              <input id="messageInput" placeholder="اكتب رسالتك..." maxlength="500" onkeydown="if(event.key==='Enter') sendMessage()">
              <button onclick="sendMessage()">إرسال</button>
            </div>
          </div>
        </section>

        <section class="tab hidden" id="cardsTab">
          <div class="panel">
            <h2>بطاقات أسئلة وتحديات</h2>
            <p>اسحب بطاقة وتظهر للطرف الثاني فورًا.</p>
            <div class="actions">
              <button onclick="drawCard('question')">سؤال 💬</button>
              <button onclick="drawCard('dare')">تحدي 🔥</button>
              <button onclick="drawCard('sweet')">كلام حلو 🍯</button>
              <button onclick="drawCard('deep')">عميق 🌙</button>
              <button onclick="drawCard('fast')">سريع ⚡</button>
            </div>
            <div class="result big" id="cardResult">اسحب بطاقة.</div>
            <button class="green" onclick="completeActivity('بطاقة',10)">تم تنفيذها +10</button>
          </div>
        </section>

        <section class="tab hidden" id="wheelTab">
          <div class="panel wheel-wrap">
            <h2>عجلة الحظ</h2>
            <div class="pointer">⬇️</div>
            <div class="wheel" id="wheel"></div>
            <button onclick="spinWheel()">لف العجلة</button>
            <div class="result big" id="wheelResult">النتيجة تظهر هنا.</div>
            <button class="green" onclick="completeActivity('عجلة الحظ',10)">تم +10</button>
          </div>
        </section>

        <section class="tab hidden" id="xoTab">
          <div class="panel" style="text-align:center">
            <h2>إكس أو قلوب</h2>
            <h3 id="xoStatus">دور 💖</h3>
            <div class="xo-board" id="xoBoard"></div>
            <div class="actions" style="justify-content:center"><button onclick="resetXO()">إعادة</button></div>
          </div>
        </section>

        <section class="tab hidden" id="memoryTab">
          <div class="panel">
            <h2>لعبة الذاكرة</h2>
            <p>طابقوا الرموز. كل تطابق يزيد النقاط.</p>
            <button onclick="resetMemory()">خلط جديد</button>
            <div class="memory-board" id="memoryBoard"></div>
          </div>
        </section>

        <section class="tab hidden" id="quizTab">
          <div class="panel">
            <h2>اختبار التوافق</h2>
            <div class="progress"><span id="quizProgress"></span></div>
            <h3 id="quizQuestion">ابدؤوا الاختبار</h3>
            <div class="options" id="quizOptions"></div>
            <div class="actions">
              <button onclick="startQuiz()">ابدأ من جديد</button>
              <button class="secondary" onclick="nextQuiz()">السؤال التالي</button>
            </div>
            <div class="result" id="quizResult">النتيجة تظهر هنا.</div>
          </div>
        </section>

        <section class="tab hidden" id="emojiTab">
          <div class="panel">
            <h2>خمن الإيموجي</h2>
            <button onclick="newEmoji()">لغز جديد</button>
            <div class="result emoji" id="emojiPuzzle">---</div>
            <label>الإجابة <input id="emojiAnswer" placeholder="اكتب الإجابة"></label>
            <button onclick="answerEmoji()">تحقق</button>
            <div class="result" id="emojiResult">جاهز؟</div>
          </div>
        </section>

        <section class="tab hidden" id="pollTab">
          <div class="panel">
            <h2>تصويت سريع</h2>
            <p>اختاروا بين خيارين وشوفوا النتيجة مباشرة.</p>
            <div class="grid">
              <div class="span-6"><label>الخيار الأول <input id="pollAInput" placeholder="مثال: فيلم"></label></div>
              <div class="span-6"><label>الخيار الثاني <input id="pollBInput" placeholder="مثال: لعبة"></label></div>
            </div>
            <div class="actions">
              <button onclick="createPoll()">إنشاء التصويت</button>
              <button class="secondary" onclick="votePoll('a')">أصوت للأول</button>
              <button class="secondary" onclick="votePoll('b')">أصوت للثاني</button>
            </div>
            <div id="pollResult" class="result">لا يوجد تصويت الآن.</div>
          </div>
        </section>

        <section class="tab hidden" id="dateTab">
          <div class="grid">
            <div class="panel span-6">
              <h2>مولد موعد</h2>
              <p>أفكار مواعيد لطيفة وسريعة.</p>
              <button onclick="dateIdea()">اقترح موعد</button>
              <div class="result" id="dateResult">الفكرة تظهر هنا.</div>
              <button class="green" onclick="completeActivity('موعد لطيف',20)">نفذناه +20</button>
            </div>
            <div class="panel span-6">
              <h2>مولد رسالة حب</h2>
              <button onclick="loveLetter()">رسالة جديدة</button>
              <div class="result" id="letterResult">الرسالة تظهر هنا.</div>
              <button class="secondary" onclick="copyText('letterResult')">نسخ</button>
            </div>
          </div>
        </section>

        <section class="tab hidden" id="drawTab">
          <div class="panel">
            <h2>لوحة رسم مشتركة</h2>
            <div class="actions">
              <button onclick="setDrawColor('#ff5fa2')">وردي</button>
              <button onclick="setDrawColor('#8d5cff')">بنفسجي</button>
              <button onclick="setDrawColor('#111111')">أسود</button>
              <button onclick="setDrawColor('#ffd166')">ذهبي</button>
              <button class="danger" onclick="clearDraw()">مسح</button>
            </div>
            <canvas id="drawCanvas" width="1200" height="600"></canvas>
          </div>
        </section>

        <section class="tab hidden" id="notesTab">
          <div class="grid">
            <div class="panel span-8">
              <h2>صندوق الوعود والذكريات</h2>
              <label>اكتب وعد أو ذكرى أو فكرة <textarea id="noteInput" placeholder="مثال: نوعد بعض نسمع لبعض بدون مقاطعة..."></textarea></label>
              <button onclick="addNote()">إضافة</button>
            </div>
            <div class="panel span-4">
              <h3>القائمة المشتركة</h3>
              <div class="list" id="notesList"></div>
            </div>
          </div>
        </section>
      </section>
    </div>
  </main>

  <div class="toast" id="toast"></div>

  <script type="module">
    import { initializeApp } from "https://www.gstatic.com/firebasejs/12.13.0/firebase-app.js";
    import {
      getDatabase, ref, set, update, get, push, remove, onValue, onChildAdded,
      query, limitToLast, serverTimestamp, onDisconnect, runTransaction
    } from "https://www.gstatic.com/firebasejs/12.13.0/firebase-database.js";

    const firebaseConfig = {
      apiKey: "AIzaSyADMXsQoY1Y8hTv4UTnE-oAtuAcoRjqQgM",
      authDomain: "adsdasd-6672f.firebaseapp.com",
      databaseURL: "https://adsdasd-6672f-default-rtdb.firebaseio.com",
      projectId: "adsdasd-6672f",
      storageBucket: "adsdasd-6672f.firebasestorage.app",
      messagingSenderId: "743897028959",
      appId: "1:743897028959:web:e67a22d97b938324783eea",
      measurementId: "G-PXEFSCJ6EZ"
    };

    const ROOT = "loveChatAndGamesGlobal";
    const $ = id => document.getElementById(id);
    const clientId = localStorage.getItem("loveClientId") || crypto.randomUUID();
    localStorage.setItem("loveClientId", clientId);

    let db, currentData = {}, wheelDeg = 0, ignoreOldMessages = true;
    let drawing=false, lastPoint=null, drawColor="#ff5fa2";

    const questions = [
      "وش أكثر شيء تحبه في علاقتنا؟","وش ذكرى بيننا تحب ترجع لها؟","لو نسافر الآن وين نروح؟","وش أكثر كلمة تحب تسمعها؟",
      "وش الشيء الصغير اللي يسعدك؟","وش عادة فيني تعجبك؟","وش ودك نجرب سوا؟","وش الشيء اللي يخليك تحس بالأمان؟",
      "لو علاقتنا فيلم وش اسمه؟","وش أكثر أكلة نطلبها سوا؟","وش هدية بسيطة تفرحك؟","وش أكثر موقف ضحك بيننا؟",
      "وش صفة تتمنى نزيدها؟","وش روتين أسبوعي نبدأ فيه؟","وش أغنية تذكرك فيني؟","وش أكثر شيء يخليك تشتاق؟"
    ];
    const dares = [
      "مدح الطرف الثاني 30 ثانية بدون توقف.","تحدي نظرات 20 ثانية، اللي يضحك يخسر.","اكتب رسالة حب قصيرة في الشات.",
      "اختار لقب لطيف للطرف الثاني ليوم كامل.","قول ثلاث أشياء تحبها في الطرف الثاني.","ارسم قلب في اللوحة خلال 15 ثانية.",
      "اختاروا أغنية تكون أغنية اليوم.","كل واحد يكتب وعد بسيط.","جواب سريع خلال 5 ثواني.",
      "الخاسر في اللعبة الجاية يرسل كلام حلو.","كل واحد يقول ذكرى يحبها.","سووا تصويت على موعد الليلة."
    ];
    const sweets = [
      "وجودك يجعل اليوم العادي يصير ذكرى.","أحب تفاصيلك الصغيرة قبل الكبيرة.","ضحكتك تختصر نص التعب.","أنت أجمل مكان أرجع له.",
      "كل مرة أكلمك أحس الدنيا أخف.","قربك راحة ما تنوصف.","أنت أجمل جزء في يومي.","أحب إننا نخلق لحظاتنا حتى من أبسط الأشياء."
    ];
    const deep = [
      "وش تحتاج وقت زعلك عشان أحسسك بالأمان؟","وش أكثر شيء يخوفك في العلاقات؟","كيف أقدر أكون أقرب لك؟",
      "وش طريقة الاعتذار اللي تريحك؟","وش حدود تحب أحترمها؟","متى تحس إننا فريق واحد؟","وش حلم تبغاني أكون جزء منه؟",
      "وش شيء لو تغير يخلي علاقتنا أجمل؟"
    ];
    const fast = [
      "قهوة ولا شاي؟","فيلم ولا مسلسل؟","طلعة ولا بيت؟","حلو ولا مالح؟","ليل ولا نهار؟","رسالة ولا مكالمة؟",
      "ورد ولا شوكولاتة؟","بحر ولا بر؟","ضحك ولا هدوء؟","مفاجأة ولا تخطيط؟"
    ];
    const wheelItems = ["سؤال عميق 🌙","تحدي ضحك 😂","رسالة حب 💌","موعد قهوة ☕","مدح 30 ثانية ✨","إكس أو ❌","ذاكرة 🃏","وعد صغير 🤝","رسم قلب 🎨","تصويت سريع 📊","لغز إيموجي 🎭","فعالية عشوائية 🎲"];
    const activities = [
      "كل واحد يكتب 5 أشياء يحبها في الثاني.","اختاروا موعد بسيط تسوونه هذا الأسبوع.","تحدي نظرات 20 ثانية.",
      "ارسموا بعض في لوحة الرسم خلال دقيقة.","اكتبوا وعد واحد سهل التنفيذ اليوم.","اختاروا أغنية تمثلكم.",
      "قولوا ذكرى حلوة بينكم وليه تحبونها.","اسحبوا بطاقة عميقة وجاوبوا بصدق.","العبوا إكس أو والخاسر يمدح الفائز.",
      "سووا لغز إيموجي، والخاسر يرسل رسالة حب.","كل واحد يرسل رسالة تبدأ بـ: أحب فيك...","قرروا شيء لطيف تسوونه الليلة.",
      "كل واحد يختار صورة أو ذكرى ويحكي قصتها.","اكتبوا 3 أهداف صغيرة لعلاقتكم.","سووا تصويت: فيلم أو لعبة أو سوالف."
    ];
    const dateIdeas = [
      "ليلة فيلم + فشار + كل واحد يختار مشهد يحبه.","طبخة مشتركة: واحد يختار الطبق والثاني يختار الحلى.",
      "جلسة أسئلة عميقة مع إضاءة هادئة.","بطولة ألعاب: إكس أو ثم ذاكرة ثم سؤال نهائي.","قهوة ومشي مع تصوير ذكرى بسيطة.",
      "مكان جديد قريب وتقييمه من 10.","عشاء خفيف ثم جولة بالسيارة مع أغانيكم.","جلسة امتنان: كل واحد يقول 3 أشياء ممتن لها.",
      "رسم حر على اللوحة ثم اختيار أجمل رسمة.","مسابقة ضحك ونكت، اللي يضحك أول يخسر.","موعد بدون جوال لمدة ساعة.",
      "رسائل مستقبلية: كل واحد يكتب رسالة تقرأونها بعد شهر."
    ];
    const emojiPuzzles = [
      {p:"🍕🎬🏠",a:["ليلة فيلم","فيلم","فلم","موعد بيت"]},{p:"☕🚶‍♂️🌙",a:["قهوة ومشي","مشي وقهوة","قهوه ومشي"]},
      {p:"💌📱❤️",a:["رسالة حب","رساله حب"]},{p:"🎧🚗🌃",a:["جولة بالسيارة","طلعة سيارة","سيارة"]},
      {p:"🎨💖🖼️",a:["رسم قلب","رسم","لوحة"]},{p:"🍿😂🎞️",a:["فيلم كوميدي","فلم كوميدي","كوميديا"]},
      {p:"🧸🌙💬",a:["سوالف ليلية","سوالف","حديث"]},{p:"🍓🍫💝",a:["حلى","هدية حلى","شوكولاته"]}
    ];
    const quizQuestions = [
      {q:"أفضل موعد؟",options:["فيلم وبيت","قهوة ومشي","مطعم","ألعاب وتحديات"]},
      {q:"أفضل اهتمام؟",options:["كلام حلو","وقت طويل","هدايا بسيطة","مساعدة وقت الزعل"]},
      {q:"مزاجكم غالبًا؟",options:["هادئ","حماسي","رومانسي","عشوائي"]},
      {q:"أجمل هدية معنوية؟",options:["رسالة","صورة ذكرى","وعد","دعاء وكلام طيب"]},
      {q:"وقت الخلاف الأفضل؟",options:["نهدأ ثم نتكلم","نتكلم فورًا","نكتب لبعض","نمزح ونخفف"]}
    ];

    function esc(v){return String(v||"").replaceAll("&","&amp;").replaceAll("<","&lt;").replaceAll(">","&gt;").replaceAll('"',"&quot;").replaceAll("'","&#039;")}
    function clean(v,f=""){return String(v||f).replace(/[<>]/g,"").replace(/\s+/g," ").trim()}
    function pick(a){return a[Math.floor(Math.random()*a.length)]}
    function toast(m){const e=$("toast");e.textContent=m;e.classList.add("show");clearTimeout(window.__t);window.__t=setTimeout(()=>e.classList.remove("show"),3000)}
    function time(){return new Date().toLocaleTimeString("ar-SA",{hour:"2-digit",minute:"2-digit"})}
    function profile(){
      const name=clean($("nameInput").value,localStorage.getItem("loveName")||"ضيف").slice(0,30)||"ضيف";
      const avatar=clean($("avatarInput").value,localStorage.getItem("loveAvatar")||"💖").slice(0,4)||"💖";
      localStorage.setItem("loveName",name);localStorage.setItem("loveAvatar",avatar);return {name,avatar}
    }
    function beep(freq=660,duration=.07){try{const A=window.AudioContext||window.webkitAudioContext,ac=new A(),o=ac.createOscillator(),g=ac.createGain();o.frequency.value=freq;g.gain.value=.035;o.connect(g);g.connect(ac.destination);o.start();o.stop(ac.currentTime+duration);setTimeout(()=>ac.close(),250)}catch(e){}}
    function status(ok,t){$("statusDot").classList.toggle("on",ok);$("statusText").textContent=t}

    function saveProfile(){const p=profile(); update(ref(db,`${ROOT}/players/${clientId}`),{id:clientId,name:p.name,avatar:p.avatar,online:true,lastSeen:Date.now()}); toast("تم حفظ الاسم")}
    async function requestNotify(){if(!("Notification" in window))return toast("متصفحك لا يدعم إشعارات المتصفح"); const r=await Notification.requestPermission(); toast(r==="granted"?"تم تفعيل الإشعارات 🔔":"لم يتم السماح بالإشعارات")}
    function notifyMsg(m){toast(`رسالة من ${m.name||"الطرف الثاني"}: ${m.text||""}`); beep(760,.08); if("Notification" in window&&Notification.permission==="granted"){new Notification(`رسالة من ${m.name||"الطرف الثاني"}`,{body:m.text||"",tag:"love-chat-games"})}}

    async function sendMessage(){
      const input=$("messageInput"), text=clean(input.value).slice(0,500); if(!text)return;
      const p=profile();
      try{
        await push(ref(db,`${ROOT}/messages`),{senderId:clientId,name:p.name,avatar:p.avatar,text,time:time(),createdAt:Date.now(),serverTime:serverTimestamp()});
        input.value=""; toast("تم إرسال الرسالة ✅"); beep(540,.05)
      }catch(e){console.error(e); toast("ما انرسلت. فعّل Realtime Database Test mode.")}
    }
    function addMsg(m){
      $("emptyText")?.remove();
      const me=m.senderId===clientId, d=document.createElement("div");
      d.className=`msg ${me?"me":"other"}`;
      d.innerHTML=`<div class="msg-head">${esc(m.avatar||"💬")} ${esc(m.name||"ضيف")}</div><div>${esc(m.text||"")}</div><small>${esc(m.time||time())}</small>`;
      $("chatBox").appendChild(d); $("chatBox").scrollTop=$("chatBox").scrollHeight;
      if(!ignoreOldMessages&&!me) notifyMsg(m)
    }

    function showTab(id){
      document.querySelectorAll(".tab").forEach(t=>t.classList.add("hidden")); $(id).classList.remove("hidden");
      document.querySelectorAll(".tabs button").forEach(b=>b.classList.remove("active"));
      const btn=[...document.querySelectorAll(".tabs button")].find(b=>b.getAttribute("onclick")?.includes(id)); if(btn)btn.classList.add("active")
    }
    async function completeActivity(label,pts=10){
      await runTransaction(ref(db,`${ROOT}/players/${clientId}/score`),v=>(v||0)+pts);
      await runTransaction(ref(db,`${ROOT}/meta/done`),v=>(v||0)+1);
      await update(ref(db,`${ROOT}/meta`),{lastActivity:label}); burstHearts(12); toast(`تم احتساب +${pts}`)
    }
    async function randomActivity(){const text=pick(activities); $("homeResult").textContent=text; await update(ref(db,`${ROOT}/games/home`),{text,at:Date.now()})}
    async function loveLetter(){
      const s=pick(["يا أجمل صدفة صارت لي،","أحب أقول لك اليوم،","من بين كل الأشياء الحلوة،","كل مرة أفكر فيك،","يا نور أيامي،"]);
      const m=pick(["وجودك يخليني أحس إن الدنيا أخف وألطف.","تفاصيلك الصغيرة تسوي فرق كبير في قلبي.","أنت سبب ابتسامة ما تنشرح بالكلام.","معك حتى الوقت العادي يصير ذكرى."]);
      const e=pick(["الله لا يحرمني منك 💗","دائمًا أنت اختياري الحلو.","خلينا نكمل ونصنع ذكريات أكثر.","أحبك بطريقة هادئة وكبيرة."]);
      const text=`${s}\n${m}\n${e}`;
      $("letterResult").textContent=text; $("homeResult").textContent=text; await update(ref(db,`${ROOT}/games/letter`),{text,at:Date.now()})
    }
    async function drawCard(type){
      const decks={question:questions,dare:dares,sweet:sweets,deep:deep,fast:fast};
      const labels={question:"سؤال",dare:"تحدي",sweet:"كلام حلو",deep:"عميق",fast:"سريع"};
      const text=pick(decks[type]||questions), label=labels[type]||"بطاقة";
      await set(ref(db,`${ROOT}/games/card`),{label,text,type,at:Date.now()}); await update(ref(db,`${ROOT}/meta`),{lastActivity:label}); showTab("cardsTab")
    }
    async function spinWheel(){
      const index=Math.floor(Math.random()*wheelItems.length), result=wheelItems[index]; wheelDeg+=1440+index*30+Math.floor(Math.random()*24);
      await set(ref(db,`${ROOT}/games/wheel`),{result,deg:wheelDeg,at:Date.now()}); await update(ref(db,`${ROOT}/meta`),{lastActivity:result}); showTab("wheelTab")
    }

    function checkWin(b){for(const w of [[0,1,2],[3,4,5],[6,7,8],[0,3,6],[1,4,7],[2,5,8],[0,4,8],[2,4,6]]){const[a,c,d]=w;if(b[a]&&b[a]===b[c]&&b[a]===b[d])return b[a]} return b.every(Boolean)?"تعادل":""}
    async function playXO(i){
      const xo=currentData.games?.xo||{board:["","","","","","","","",""],turn:"💖",winner:""}, b=[...(xo.board||["","","","","","","","",""])];
      if(xo.winner||b[i])return; b[i]=xo.turn||"💖"; const winner=checkWin(b), next=(xo.turn||"💖")==="💖"?"🌙":"💖";
      await set(ref(db,`${ROOT}/games/xo`),{board:b,turn:winner?xo.turn:next,winner});
      if(winner&&winner!=="تعادل") await completeActivity("فوز في إكس أو",15)
    }
    async function resetXO(){await set(ref(db,`${ROOT}/games/xo`),{board:["","","","","","","","",""],turn:"💖",winner:""})}
    function renderXO(xo={}){
      const b=xo.board||["","","","","","","","",""];
      $("xoStatus").textContent=xo.winner?(xo.winner==="تعادل"?"تعادل 🤝":`الفائز ${xo.winner} 🎉`):`دور ${xo.turn||"💖"}`;
      $("xoBoard").innerHTML=b.map((v,i)=>`<div class="cell" onclick="playXO(${i})">${esc(v)}</div>`).join("")
    }

    function makeCards(){const icons=["💖","🌙","✨","🍓","🧸","💌","☕","🎧","🌹","🍫"];return [...icons,...icons].map((icon,i)=>({id:`${Date.now()}-${i}-${Math.random()}`,icon,open:false,matched:false})).sort(()=>Math.random()-.5)}
    async function resetMemory(){await set(ref(db,`${ROOT}/games/memory`),{cards:makeCards(),lock:false})}
    async function flipMemory(id){
      const mem=currentData.games?.memory||{cards:[]}; if(mem.lock)return;
      const cards=JSON.parse(JSON.stringify(mem.cards||[])), card=cards.find(c=>c.id===id); if(!card||card.open||card.matched)return;
      const open=cards.filter(c=>c.open&&!c.matched); card.open=true;
      if(!open.length){await set(ref(db,`${ROOT}/games/memory`),{cards,lock:false});return}
      const first=cards.find(c=>c.id===open[0].id);
      if(first&&first.icon===card.icon){first.matched=card.matched=true; await set(ref(db,`${ROOT}/games/memory`),{cards,lock:false}); await completeActivity("تطابق في الذاكرة",5); if(cards.every(c=>c.matched)) await completeActivity("إنهاء الذاكرة",20)}
      else{await set(ref(db,`${ROOT}/games/memory`),{cards,lock:true}); setTimeout(async()=>{cards.forEach(c=>{if(!c.matched)c.open=false}); await set(ref(db,`${ROOT}/games/memory`),{cards,lock:false})},850)}
    }
    function renderMemory(mem={cards:[]}){$("memoryBoard").innerHTML=(mem.cards||[]).map(c=>`<div class="memory-card ${c.matched?"matched":""}" onclick="flipMemory('${c.id}')">${c.open||c.matched?c.icon:"?"}</div>`).join("")}

    async function startQuiz(){await set(ref(db,`${ROOT}/games/quiz`),{index:0,finished:false,score:0,answers:{}})}
    async function answerQuiz(i){const idx=currentData.games?.quiz?.index||0; await set(ref(db,`${ROOT}/games/quiz/answers/${clientId}/${idx}`),i); document.querySelectorAll("#quizOptions .option").forEach((b,n)=>b.classList.toggle("selected",n===i))}
    async function nextQuiz(){
      const q=currentData.games?.quiz||{index:0,answers:{}}; const idx=q.index||0;
      if(idx<quizQuestions.length-1) await update(ref(db,`${ROOT}/games/quiz`),{index:idx+1});
      else{const vals=[]; Object.values(q.answers||{}).forEach(a=>Object.values(a||{}).forEach(v=>Number.isInteger(v)&&vals.push(v))); const score=Math.min(99,76+new Set(vals).size*4+Math.floor(Math.random()*8)); await update(ref(db,`${ROOT}/games/quiz`),{finished:true,score}); await completeActivity("اختبار التوافق",20)}
    }
    function renderQuiz(q={index:0}){
      const idx=q.index||0, item=quizQuestions[idx]; $("quizProgress").style.width=`${q.finished?100:Math.round(idx/quizQuestions.length*100)}%`;
      if(q.finished){$("quizQuestion").textContent="انتهى الاختبار";$("quizOptions").innerHTML="";$("quizResult").textContent=`نسبة التوافق: ${q.score||90}% 💞`;return}
      $("quizQuestion").textContent=`سؤال ${idx+1}: ${item.q}`; $("quizOptions").innerHTML=item.options.map((o,i)=>`<button class="option" onclick="answerQuiz(${i})">${esc(o)}</button>`).join("")
    }

    async function newEmoji(){const e=pick(emojiPuzzles); await set(ref(db,`${ROOT}/games/emoji`),{puzzle:e.p,answers:e.a,at:Date.now()}); showTab("emojiTab")}
    async function answerEmoji(){
      const ans=clean($("emojiAnswer").value).toLowerCase(); if(!ans)return;
      const answers=currentData.games?.emoji?.answers||[]; const ok=answers.some(x=>ans.includes(String(x).toLowerCase())||String(x).toLowerCase()===ans);
      if(ok){$("emojiResult").textContent="صح عليك! ✅"; $("emojiAnswer").value=""; await completeActivity("حل لغز إيموجي",10)} else $("emojiResult").textContent="غلط، جرب ثاني 😄"
    }
    async function dateIdea(){const text=pick(dateIdeas); await set(ref(db,`${ROOT}/games/date`),{text,at:Date.now()}); await push(ref(db,`${ROOT}/notes`),{text:`فكرة موعد: ${text}`,by:clientId,byName:profile().name,createdAt:Date.now()})}
    async function createPoll(){const a=clean($("pollAInput").value,"الخيار الأول"), b=clean($("pollBInput").value,"الخيار الثاني"); await set(ref(db,`${ROOT}/games/poll`),{a,b,votes:{},at:Date.now()})}
    async function votePoll(choice){await set(ref(db,`${ROOT}/games/poll/votes/${clientId}`),choice)}
    async function addNote(){const text=clean($("noteInput").value).slice(0,280); if(!text)return; await push(ref(db,`${ROOT}/notes`),{text,by:clientId,byName:profile().name,createdAt:Date.now()}); $("noteInput").value=""; toast("تمت الإضافة")}
    async function removeNote(id){await remove(ref(db,`${ROOT}/notes/${id}`))}
    function copyText(id){navigator.clipboard.writeText($(id).textContent).then(()=>toast("تم النسخ"))}

    const canvas=$("drawCanvas"), ctx=canvas.getContext("2d"); ctx.lineWidth=7; ctx.lineCap="round"; ctx.lineJoin="round";
    function setDrawColor(c){drawColor=c}
    function pos(e){const r=canvas.getBoundingClientRect(),t=e.touches?e.touches[0]:e;return{x:(t.clientX-r.left)*(canvas.width/r.width),y:(t.clientY-r.top)*(canvas.height/r.height)}}
    function drawLine(a,b,c,emit=false){if(!a||!b)return; ctx.strokeStyle=c||drawColor; ctx.beginPath(); ctx.moveTo(a.x,a.y); ctx.lineTo(b.x,b.y); ctx.stroke(); if(emit)push(ref(db,`${ROOT}/draw`),{senderId:clientId,from:a,to:b,color:drawColor,at:Date.now()})}
    function startDraw(e){drawing=true; lastPoint=pos(e)}
    function moveDraw(e){if(!drawing)return; e.preventDefault(); const p=pos(e); drawLine(lastPoint,p,drawColor,true); lastPoint=p}
    function endDraw(){drawing=false; lastPoint=null}
    async function clearDraw(){ctx.clearRect(0,0,canvas.width,canvas.height); await push(ref(db,`${ROOT}/draw`),{clear:true,senderId:clientId,at:Date.now()})}
    canvas.addEventListener("mousedown",startDraw); canvas.addEventListener("mousemove",moveDraw); window.addEventListener("mouseup",endDraw);
    canvas.addEventListener("touchstart",startDraw,{passive:false}); canvas.addEventListener("touchmove",moveDraw,{passive:false}); canvas.addEventListener("touchend",endDraw);

    function renderAll(d){
      currentData=d||{}; const meta=d.meta||{}, games=d.games||{}, players=Object.values(d.players||{}).sort((a,b)=>(b.online===true)-(a.online===true));
      $("lastActivity").textContent=meta.lastActivity||"جاهز"; $("doneCount").textContent=meta.done||0;
      $("playersList").innerHTML=players.length?players.map(p=>`<div class="player"><div><b><span class="dot ${p.online?"on":""}"></span>${esc(p.avatar)} ${esc(p.name)} ${p.id===clientId?"أنت":""}</b><div class="small-text">${p.online?"متصل":"غير متصل"}</div></div><div class="score">${p.score||0}</div></div>`).join(""):"<div class='small-text'>لا يوجد لاعبين</div>";
      const me=players.find(p=>p.id===clientId), score=me?.score||0;
      $("achievements").innerHTML=[["بداية الحب",10,"🌱"],["ثنائي نشيط",50,"⚡"],["قلوب محترفة",100,"💖"],["أبطال الفعاليات",200,"🏆"],["أسطورة الشات",500,"👑"]].map(a=>`<div class="list-item"><span>${a[2]} ${a[0]}</span><b>${score>=a[1]?"مفتوح":a[1]+" نقطة"}</b></div>`).join("");
      if(games.home?.text)$("homeResult").textContent=games.home.text;
      if(games.card)$("cardResult").textContent=`${games.card.label||"بطاقة"}\n\n${games.card.text||""}`;
      if(games.wheel){$("wheelResult").textContent=games.wheel.result||"النتيجة تظهر هنا."; if(Number(games.wheel.deg||0)!==wheelDeg){wheelDeg=Number(games.wheel.deg||0); $("wheel").style.transform=`rotate(${wheelDeg}deg)`}}
      renderXO(games.xo||{}); renderMemory(games.memory||{cards:[]}); renderQuiz(games.quiz||{index:0});
      if(games.emoji)$("emojiPuzzle").textContent=games.emoji.puzzle||"---";
      if(games.date?.text)$("dateResult").textContent=games.date.text;
      if(games.letter?.text)$("letterResult").textContent=games.letter.text;
      if(games.poll){const votes=Object.values(games.poll.votes||{}), av=votes.filter(v=>v==="a").length,bv=votes.filter(v=>v==="b").length,total=Math.max(1,av+bv);$("pollResult").innerHTML=`<div style="width:100%"><b>${esc(games.poll.a)}</b><div class="poll-row"><div class="bar"><span style="width:${av/total*100}%"></span></div><b>${av}</b></div><b>${esc(games.poll.b)}</b><div class="poll-row"><div class="bar"><span style="width:${bv/total*100}%"></span></div><b>${bv}</b></div></div>`}
    }
    function makeHearts(){const box=$("hearts"); for(let i=0;i<24;i++){const h=document.createElement("span");h.className="heart";h.textContent=["💗","💖","💘","💕"][i%4];h.style.left=Math.random()*100+"%";h.style.animationDuration=7+Math.random()*11+"s";h.style.animationDelay=-Math.random()*12+"s";h.style.fontSize=16+Math.random()*24+"px";box.appendChild(h)}}
    function burstHearts(n){for(let i=0;i<n;i++){const h=document.createElement("div");h.textContent="💖";h.style.position="fixed";h.style.zIndex="99";h.style.left=45+Math.random()*10+"%";h.style.top="58%";h.style.fontSize=22+Math.random()*22+"px";h.style.pointerEvents="none";h.style.transition="1.1s ease";document.body.appendChild(h);requestAnimationFrame(()=>{h.style.transform=`translate(${(Math.random()-.5)*260}px,${-180-Math.random()*180}px) rotate(${Math.random()*260}deg)`;h.style.opacity="0"});setTimeout(()=>h.remove(),1200)}}

    async function init(){
      $("nameInput").value=localStorage.getItem("loveName")||""; $("avatarInput").value=localStorage.getItem("loveAvatar")||"💖"; makeHearts();
      try{
        const app=initializeApp(firebaseConfig); db=getDatabase(app); status(true,"متصل");
        const p=profile(); await update(ref(db,`${ROOT}/players/${clientId}`),{id:clientId,name:p.name,avatar:p.avatar,online:true,lastSeen:Date.now()});
        onDisconnect(ref(db,`${ROOT}/players/${clientId}`)).update({online:false,lastSeen:Date.now()});
        const rootSnap=await get(ref(db,`${ROOT}/games/memory/cards`)); if(!rootSnap.exists()) await resetMemory();
        onValue(ref(db,ROOT),snap=>renderAll(snap.val()||{}));
        onChildAdded(query(ref(db,`${ROOT}/messages`),limitToLast(80)),snap=>addMsg(snap.val()));
        setTimeout(()=>ignoreOldMessages=false,1400);
        onValue(ref(db,`${ROOT}/notes`),snap=>{const notes=snap.val()||{}; const arr=Object.entries(notes).map(([id,n])=>({id,...n})).sort((a,b)=>(b.createdAt||0)-(a.createdAt||0)); $("notesList").innerHTML=arr.length?arr.map(n=>`<div class="list-item"><span>${esc(n.text)}<div class="small-text">${esc(n.byName||"")}</div></span><button class="small danger" onclick="removeNote('${n.id}')">حذف</button></div>`).join(""):"<div class='small-text'>مافي شيء محفوظ</div>"});
        onChildAdded(ref(db,`${ROOT}/draw`),snap=>{const l=snap.val(); if(!l)return; if(l.clear){ctx.clearRect(0,0,canvas.width,canvas.height);return} if(l.senderId!==clientId)drawLine(l.from,l.to,l.color,false)});
      }catch(e){console.error(e); status(false,"غير متصل"); toast("تعذر الاتصال. فعّل Realtime Database Test mode.")}
    }

    Object.assign(window,{saveProfile,requestNotify,sendMessage,showTab,completeActivity,randomActivity,loveLetter,drawCard,spinWheel,playXO,resetXO,resetMemory,flipMemory,startQuiz,answerQuiz,nextQuiz,newEmoji,answerEmoji,dateIdea,createPoll,votePoll,addNote,removeNote,copyText,setDrawColor,clearDraw});
    init();
  </script>
</body>
</html>
