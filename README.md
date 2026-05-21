<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>روم ألعابنا كتابة | Online</title>
  <style>
    :root{
      --bg:#120814;
      --card:rgba(255,255,255,.105);
      --card2:rgba(255,255,255,.15);
      --text:#fff7fb;
      --muted:#dcc9d8;
      --pink:#ff5fa2;
      --pink2:#ff93c6;
      --purple:#8d5cff;
      --gold:#ffd166;
      --green:#67f2bc;
      --danger:#ff6b6b;
      --shadow:0 22px 70px rgba(0,0,0,.35);
      --radius:28px;
    }
    *{box-sizing:border-box}
    html{scroll-behavior:smooth}
    body{
      margin:0;
      min-height:100vh;
      font-family:Tahoma,Arial,sans-serif;
      color:var(--text);
      background:
        radial-gradient(circle at 10% 10%,rgba(255,95,162,.32),transparent 35%),
        radial-gradient(circle at 90% 20%,rgba(141,92,255,.35),transparent 35%),
        radial-gradient(circle at 45% 90%,rgba(255,209,102,.16),transparent 38%),
        linear-gradient(145deg,#120814,#251038 52%,#120814);
      overflow-x:hidden;
    }
    button,input,select,textarea{font-family:inherit}
    button{
      border:0;
      cursor:pointer;
      color:white;
      border-radius:18px;
      padding:13px 18px;
      font-weight:900;
      background:linear-gradient(135deg,var(--pink),var(--purple));
      box-shadow:0 12px 26px rgba(255,95,162,.20);
      transition:.16s;
    }
    button:hover{transform:translateY(-2px);filter:saturate(1.08)}
    button.secondary{background:rgba(255,255,255,.12);border:1px solid rgba(255,255,255,.16);box-shadow:none}
    button.green{background:linear-gradient(135deg,var(--green),#24c6dc);color:#06261f}
    button.danger{background:linear-gradient(135deg,#ff6b6b,#d63b72)}
    button.small-btn{padding:9px 12px;border-radius:14px;font-size:13px}
    button:disabled{opacity:.55;cursor:not-allowed;transform:none}
    input,select,textarea{
      width:100%;
      outline:none;
      border:1px solid rgba(255,255,255,.16);
      background:rgba(0,0,0,.22);
      color:white;
      border-radius:18px;
      padding:13px 14px;
      font-size:15px;
    }
    textarea{min-height:120px;resize:vertical;line-height:1.8}
    label{display:block;color:#ffe5f1;font-weight:900;line-height:2}
    .wrap{max-width:1280px;margin:auto;padding:22px;position:relative;z-index:1}
    .hidden{display:none!important}
    .hero{
      min-height:94vh;
      display:grid;
      grid-template-columns:1.1fr .9fr;
      align-items:center;
      gap:24px;
    }
    .hero-card,.preview-card,.room-card,.card,.game-tile,.setup-card{
      background:linear-gradient(145deg,rgba(255,255,255,.145),rgba(255,255,255,.075));
      border:1px solid rgba(255,255,255,.16);
      box-shadow:var(--shadow);
      backdrop-filter:blur(18px);
      border-radius:var(--radius);
    }
    .hero-card{padding:34px;overflow:hidden;position:relative}
    .hero-card:before{
      content:"";
      position:absolute;
      inset:-2px;
      background:radial-gradient(circle at top left,rgba(255,255,255,.22),transparent 36%);
      pointer-events:none;
    }
    .hero-card>*{position:relative;z-index:1}
    .badge{
      display:inline-flex;
      padding:10px 14px;
      border-radius:999px;
      background:rgba(255,95,162,.16);
      color:#ffd9eb;
      border:1px solid rgba(255,95,162,.28);
      font-size:14px;
    }
    h1{font-size:clamp(38px,6vw,76px);line-height:1.04;margin:18px 0 14px;letter-spacing:-1.3px}
    h1 span,.gradient{
      background:linear-gradient(90deg,#fff,#ff9eca,#ffd166,#fff);
      -webkit-background-clip:text;
      background-clip:text;
      color:transparent;
    }
    p{color:var(--muted);line-height:1.9}
    .form-grid{display:grid;grid-template-columns:1fr 150px;gap:14px;margin-top:22px}
    .actions{display:flex;flex-wrap:wrap;gap:10px;margin:16px 0}
    .join-box{margin-top:24px;padding:18px;border-radius:24px;background:rgba(0,0,0,.18);border:1px solid rgba(255,255,255,.11)}
    .note{color:var(--muted);font-size:13px;line-height:1.8;margin-top:12px}
    .setup-card{padding:18px;margin-top:18px;background:rgba(255,209,102,.08);border-color:rgba(255,209,102,.22)}
    .setup-card textarea{font-family:Consolas,monospace;direction:ltr;text-align:left;min-height:150px}
    .preview-card{padding:18px}
    .mock-window{
      min-height:580px;
      border-radius:34px;
      background:
        radial-gradient(circle at 50% 15%,rgba(255,95,162,.35),transparent 32%),
        linear-gradient(145deg,#351848,#17091c);
      border:1px solid rgba(255,255,255,.14);
      overflow:hidden;
    }
    .mock-top{display:flex;gap:8px;padding:18px;background:rgba(0,0,0,.18)}
    .mock-top span{width:12px;height:12px;border-radius:999px;background:rgba(255,255,255,.35)}
    .mock-body{padding:50px 22px;text-align:center}
    .mock-avatar{font-size:92px;filter:drop-shadow(0 18px 25px rgba(0,0,0,.35))}
    .mini-stats{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-top:28px}
    .mini-stats b{padding:16px;border-radius:20px;background:rgba(255,255,255,.1)}
    .app{display:grid;grid-template-columns:310px 1fr;gap:18px;align-items:start}
    .sidebar{position:sticky;top:14px;display:grid;gap:14px}
    .room-card{padding:18px}
    .small{color:var(--muted);font-size:13px}
    #roomCodeLabel{font-size:38px;letter-spacing:4px;margin:6px 0;direction:ltr}
    .copy-row{display:flex;gap:8px;flex-wrap:wrap}
    .players{display:grid;gap:8px;margin-top:10px}
    .player{
      display:flex;
      justify-content:space-between;
      align-items:center;
      gap:10px;
      padding:12px;
      border-radius:18px;
      background:rgba(255,255,255,.1);
      border:1px solid rgba(255,255,255,.1);
    }
    .player strong{display:block}
    .player .score{color:var(--gold);font-weight:900}
    .status-dot{display:inline-block;width:9px;height:9px;border-radius:50%;background:#777;margin-left:5px}
    .status-dot.on{background:var(--green);box-shadow:0 0 12px rgba(103,242,188,.55)}
    .tabs{
      display:flex;
      gap:8px;
      overflow:auto;
      padding:10px;
      border-radius:999px;
      background:rgba(18,8,20,.68);
      border:1px solid rgba(255,255,255,.12);
      backdrop-filter:blur(16px);
      position:sticky;
      top:12px;
      z-index:5;
      margin-bottom:14px;
    }
    .tabs button{
      white-space:nowrap;
      background:rgba(255,255,255,.1);
      border:1px solid rgba(255,255,255,.12);
      box-shadow:none;
      padding:10px 14px;
      font-size:13px;
    }
    .tabs button.active{background:linear-gradient(135deg,var(--pink),var(--purple))}
    .grid{display:grid;grid-template-columns:repeat(12,1fr);gap:14px}
    .card{padding:22px}
    .span-8{grid-column:span 8}
    .span-4{grid-column:span 4}
    .game-tile{
      grid-column:span 3;
      min-height:160px;
      padding:18px;
      display:flex;
      flex-direction:column;
      justify-content:center;
      cursor:pointer;
      font-size:36px;
    }
    .game-tile b{font-size:19px;margin-top:10px}
    .game-tile span{color:var(--muted);font-size:13px;margin-top:6px}
    .result{
      min-height:90px;
      border-radius:22px;
      background:rgba(0,0,0,.20);
      border:1px dashed rgba(255,255,255,.2);
      padding:18px;
      color:#fff;
      line-height:1.9;
      display:flex;
      align-items:center;
      justify-content:center;
      text-align:center;
      white-space:pre-wrap;
      margin:14px 0;
    }
    .result.big{font-size:22px;min-height:130px}
    .result.emoji{font-size:54px;letter-spacing:10px}
    .center{text-align:center}
    .center-actions{justify-content:center}
    .pointer{font-size:38px;margin-bottom:-22px;filter:drop-shadow(0 8px 12px rgba(0,0,0,.35))}
    .wheel{
      width:min(340px,78vw);
      height:min(340px,78vw);
      border-radius:50%;
      margin:auto auto 18px;
      background:conic-gradient(#ff5fa2 0 45deg,#8d5cff 45deg 90deg,#ffd166 90deg 135deg,#7cf7c2 135deg 180deg,#ff89c0 180deg 225deg,#b896ff 225deg 270deg,#ff9f68 270deg 315deg,#61f2bd 315deg 360deg);
      border:10px solid rgba(255,255,255,.18);
      box-shadow:0 25px 70px rgba(0,0,0,.3),inset 0 0 40px rgba(255,255,255,.15);
      transition:transform 4s cubic-bezier(.13,.78,.19,1);
      position:relative;
    }
    .wheel:after{
      content:"💘";
      position:absolute;
      inset:50% auto auto 50%;
      transform:translate(-50%,-50%);
      width:90px;
      height:90px;
      border-radius:50%;
      background:rgba(18,8,20,.82);
      display:grid;
      place-items:center;
      font-size:40px;
      border:1px solid rgba(255,255,255,.22);
    }
    .xo-board{
      display:grid;
      grid-template-columns:repeat(3,1fr);
      gap:9px;
      max-width:370px;
      margin:auto;
    }
    .cell{
      height:105px;
      border-radius:22px;
      background:rgba(255,255,255,.11);
      border:1px solid rgba(255,255,255,.14);
      display:grid;
      place-items:center;
      font-size:48px;
      cursor:pointer;
    }
    .memory-board{
      display:grid;
      grid-template-columns:repeat(auto-fit,minmax(112px,1fr));
      gap:10px;
      margin-top:16px;
    }
    .memory-card{
      aspect-ratio:1/1;
      border-radius:22px;
      background:rgba(255,255,255,.12);
      border:1px solid rgba(255,255,255,.14);
      display:grid;
      place-items:center;
      font-size:38px;
      cursor:pointer;
      user-select:none;
    }
    .memory-card.matched{background:rgba(103,242,188,.20);border-color:rgba(103,242,188,.40)}
    .progress{height:12px;border-radius:999px;background:rgba(255,255,255,.12);overflow:hidden}
    .progress span{display:block;width:0;height:100%;border-radius:999px;background:linear-gradient(90deg,var(--pink),var(--gold));transition:.2s}
    .options{display:grid;gap:10px;margin:14px 0}
    .option{text-align:right;justify-content:flex-start;background:rgba(255,255,255,.11);box-shadow:none;border:1px solid rgba(255,255,255,.12)}
    .option.selected{background:rgba(103,242,188,.22)}
    .chat-card{min-height:72vh;display:flex;flex-direction:column}
    .chat{flex:1;overflow:auto;display:grid;gap:10px;padding:8px;border-radius:20px;background:rgba(0,0,0,.16);max-height:56vh}
    .message{padding:12px;border-radius:18px;background:rgba(255,255,255,.10);line-height:1.7}
    .message.me{background:rgba(255,95,162,.16);border:1px solid rgba(255,95,162,.2)}
    .message.system{color:var(--muted);text-align:center;background:rgba(255,209,102,.09)}
    .message b{color:#fff}
    .message small{color:var(--muted);display:block;margin-top:4px}
    .chat-input{display:grid;grid-template-columns:1fr auto;gap:10px;margin-top:12px}
    .achievements{display:grid;gap:10px}
    .achievement{display:flex;justify-content:space-between;padding:12px;border-radius:16px;background:rgba(255,255,255,.09);color:var(--muted)}
    .achievement.open{color:#fff;border:1px solid rgba(103,242,188,.25)}
    canvas#drawCanvas{
      width:100%;
      height:420px;
      display:block;
      border-radius:24px;
      background:white;
      touch-action:none;
    }
    .toast{
      position:fixed;
      left:20px;
      bottom:20px;
      background:rgba(18,8,20,.94);
      border:1px solid rgba(255,255,255,.16);
      color:#fff;
      padding:14px 16px;
      border-radius:18px;
      box-shadow:var(--shadow);
      transform:translateY(140%);
      transition:.22s;
      z-index:20;
      max-width:380px;
      line-height:1.7;
    }
    .toast.show{transform:translateY(0)}
    .hearts{position:fixed;inset:0;pointer-events:none;overflow:hidden;z-index:0}
    .heart{position:absolute;bottom:-80px;font-size:22px;opacity:.25;animation:floatHeart linear infinite}
    @keyframes floatHeart{
      0%{transform:translateY(0) rotate(0deg) scale(.8);opacity:0}
      10%{opacity:.28}
      100%{transform:translateY(-115vh) rotate(360deg) scale(1.35);opacity:0}
    }
    @media(max-width:1000px){
      .hero{grid-template-columns:1fr;min-height:auto;padding-top:28px}
      .app{grid-template-columns:1fr}
      .sidebar{position:static}
      .span-8,.span-4,.game-tile{grid-column:span 12}
      .game-tile{min-height:120px}
    }
    @media(max-width:650px){
      .wrap{padding:13px}
      .hero-card{padding:22px}
      .form-grid{grid-template-columns:1fr}
      .tabs{border-radius:22px}
      .cell{height:88px}
      .chat-input{grid-template-columns:1fr}
    }
  </style>
</head>
<body>
  <div class="hearts" id="hearts"></div>

  <main class="wrap">
    <section class="hero" id="loginView">
      <div class="hero-card">
        <span class="badge">💬 ملف واحد HTML - روم كتابة وألعاب مباشرة</span>
        <h1>روم ألعاب <span>أنا وحبيبتي</span></h1>
        <p>
          بدون روم صوتي وبدون Node. الملف كله صفحة HTML واحدة: شات، إشعارات رسائل،
          كود روم، وألعاب تتزامن بينكم بنفس الوقت باستخدام Firebase.
        </p>

        <div class="setup-card" id="setupBox">
          <h3>Firebase مركّب داخل الملف ✅</h3>
          <p>
            الإعدادات مركّبة داخل الكود. إذا ما اشتغل إنشاء الروم، فعّل Realtime Database من لوحة Firebase. تقدر أيضًا تعدل الإعدادات يدويًا من هنا في أي وقت.
            <b>FIREBASE_CONFIG</b>. بعد الحفظ يشتغل إنشاء ودخول الرومات.
          </p>
          <label>الصق firebaseConfig كامل هنا</label>
          <textarea id="firebaseConfigInput" placeholder='{
  "apiKey": "...",
  "authDomain": "...firebaseapp.com",
  "databaseURL": "https://...firebaseio.com",
  "projectId": "...",
  "storageBucket": "...",
  "messagingSenderId": "...",
  "appId": "..."
}'></textarea>
          <div class="actions">
            <button onclick="saveFirebaseConfig()">حفظ إعدادات Firebase</button>
            <button class="secondary" onclick="clearFirebaseConfig()">مسح الإعدادات</button>
          </div>
          <div class="note">
            بعد حفظ الإعدادات: أنشئ روم، انسخ الرابط، وأرسله لها.
          </div>
        </div>

        <div class="form-grid">
          <label>
            اسمك
            <input id="nameInput" placeholder="مثال: سهم" maxlength="30" />
          </label>

          <label>
            رمزك
            <select id="avatarInput">
              <option>💖</option>
              <option>🌙</option>
              <option>✨</option>
              <option>🫶</option>
              <option>🧸</option>
              <option>☕</option>
              <option>🎧</option>
              <option>🍓</option>
            </select>
          </label>
        </div>

        <div class="actions">
          <button onclick="createRoom()">إنشاء روم خاص</button>
          <button class="secondary" onclick="requestNotify()">تفعيل إشعارات الرسائل</button>
        </div>

        <div class="join-box">
          <label>
            دخول بكود الروم
            <input id="roomCodeInput" placeholder="مثال: A7K2Q" maxlength="8" />
          </label>
          <button onclick="joinRoom()">دخول الروم</button>
        </div>

        <div class="note">
          لو الإشعارات ما ظهرت، اضغط “تفعيل إشعارات الرسائل” واسمح للمتصفح.
        </div>
      </div>

      <div class="preview-card">
        <div class="mock-window">
          <div class="mock-top">
            <span></span><span></span><span></span>
          </div>
          <div class="mock-body">
            <div class="mock-avatar">💘</div>
            <h2>Private Text Room</h2>
            <p>Chat + Games + Notifications</p>
            <div class="mini-stats">
              <b>💬 شات</b>
              <b>🔔 إشعارات</b>
              <b>🎡 عجلة</b>
              <b>🃏 ألعاب</b>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="app hidden" id="appView">
      <aside class="sidebar">
        <div class="room-card">
          <div class="small">كود الروم</div>
          <h2 id="roomCodeLabel">-----</h2>
          <div class="copy-row">
            <button class="small-btn" onclick="copyInvite()">نسخ الرابط</button>
            <button class="small-btn secondary" onclick="leaveRoom()">خروج</button>
          </div>
        </div>

        <div class="room-card">
          <div class="small">الإشعارات</div>
          <h3 id="notifyStatus">غير مفعّلة</h3>
          <div class="copy-row">
            <button class="small-btn green" onclick="requestNotify()">تفعيل</button>
            <button class="small-btn secondary" onclick="testNotify()">تجربة</button>
          </div>
        </div>

        <div class="room-card">
          <div class="small">اللاعبين</div>
          <div class="players" id="playersList"></div>
        </div>

        <div class="room-card">
          <div class="small">آخر فعالية</div>
          <h3 id="lastActivity">الروم جاهز</h3>
          <div class="small">عدد الفعاليات: <b id="doneCount">0</b></div>
        </div>
      </aside>

      <section class="content">
        <nav class="tabs">
          <button onclick="showTab('tabHome')" class="active">الرئيسية</button>
          <button onclick="showTab('tabChat')">الشات</button>
          <button onclick="showTab('tabCards')">بطاقات</button>
          <button onclick="showTab('tabWheel')">العجلة</button>
          <button onclick="showTab('tabXO')">إكس أو</button>
          <button onclick="showTab('tabMemory')">ذاكرة</button>
          <button onclick="showTab('tabQuiz')">توافق</button>
          <button onclick="showTab('tabEmoji')">إيموجي</button>
          <button onclick="showTab('tabDraw')">رسم</button>
          <button onclick="showTab('tabNotes')">وعود</button>
        </nav>

        <section class="tab" id="tabHome">
          <div class="grid">
            <div class="card span-8">
              <h2>مرحبًا في الروم الخاص 💞</h2>
              <p>
                أرسل الرابط لها، تدخل بنفس الكود، وبعدها الشات والألعاب تتحدث مباشرة عند الطرفين.
                لما ترسل رسالة يظهر لك تأكيد، وهي يظهر لها تنبيه داخل الموقع وإشعار متصفح إذا مفعّل.
              </p>
              <div class="actions">
                <button onclick="randomActivity()">اقترح فعالية</button>
                <button class="green" onclick="completeActivity('فعالية عشوائية',10)">خلصناها +10</button>
              </div>
              <div class="result" id="homeResult">اضغط “اقترح فعالية”.</div>
            </div>

            <div class="card span-4">
              <h3>إنجازاتك</h3>
              <div class="achievements" id="achievements"></div>
            </div>

            <div class="game-tile" onclick="showTab('tabChat')">💬<b>شات الروم</b><span>رسائل وتنبيهات</span></div>
            <div class="game-tile" onclick="showTab('tabCards')">💬<b>أسئلة وتحديات</b><span>بطاقات مشتركة</span></div>
            <div class="game-tile" onclick="showTab('tabWheel')">🎡<b>عجلة الحظ</b><span>نتيجة للجميع</span></div>
            <div class="game-tile" onclick="showTab('tabXO')">❌<b>إكس أو</b><span>لعب مباشر</span></div>
            <div class="game-tile" onclick="showTab('tabMemory')">🃏<b>الذاكرة</b><span>تطابق مشترك</span></div>
            <div class="game-tile" onclick="showTab('tabQuiz')">🧠<b>اختبار توافق</b><span>أسئلة مشتركة</span></div>
            <div class="game-tile" onclick="showTab('tabEmoji')">🎭<b>خمن الإيموجي</b><span>لغز سريع</span></div>
            <div class="game-tile" onclick="showTab('tabDraw')">🎨<b>لوحة رسم</b><span>رسم مباشر</span></div>
          </div>
        </section>

        <section class="tab hidden" id="tabChat">
          <div class="card chat-card">
            <h2>شات الروم</h2>
            <p>اكتبوا هنا. كل رسالة توصل للطرف الثاني مع تنبيه.</p>
            <div class="chat" id="chatMessages"></div>
            <div class="chat-input">
              <input id="chatInput" placeholder="اكتب رسالة..." onkeydown="if(event.key==='Enter') sendChat()" />
              <button onclick="sendChat()">إرسال</button>
            </div>
          </div>
        </section>

        <section class="tab hidden" id="tabCards">
          <div class="card">
            <h2>بطاقات الروم</h2>
            <p>أي بطاقة تسحبها تظهر للجميع في نفس الوقت.</p>
            <div class="actions">
              <button onclick="drawCard('question')">سؤال 💬</button>
              <button onclick="drawCard('dare')">تحدي 🔥</button>
              <button onclick="drawCard('sweet')">كلام حلو 🍯</button>
              <button onclick="drawCard('deep')">عميق 🌙</button>
            </div>
            <div class="result big" id="cardResult">اسحب بطاقة.</div>
            <button class="green" onclick="completeActivity('بطاقة سؤال/تحدي',10)">تم تنفيذها +10</button>
          </div>
        </section>

        <section class="tab hidden" id="tabWheel">
          <div class="card center">
            <h2>عجلة الحظ</h2>
            <div class="pointer">⬇️</div>
            <div class="wheel" id="wheel"></div>
            <button onclick="spinWheel()">لف العجلة للجميع</button>
            <div class="result big" id="wheelResult">النتيجة تظهر هنا.</div>
            <button class="green" onclick="completeActivity('عجلة الحظ',10)">تم +10</button>
          </div>
        </section>

        <section class="tab hidden" id="tabXO">
          <div class="card center">
            <h2>إكس أو قلوب</h2>
            <h3 id="xoStatus">دور 💖</h3>
            <div class="xo-board" id="xoBoard"></div>
            <div class="actions center-actions">
              <button onclick="resetXO()">إعادة اللعبة</button>
            </div>
          </div>
        </section>

        <section class="tab hidden" id="tabMemory">
          <div class="card">
            <h2>لعبة الذاكرة</h2>
            <p>اقلبوا الكروت، إذا صار تطابق تزيد النقاط.</p>
            <button onclick="resetMemory()">خلط جديد</button>
            <div class="memory-board" id="memoryBoard"></div>
          </div>
        </section>

        <section class="tab hidden" id="tabQuiz">
          <div class="card">
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

        <section class="tab hidden" id="tabEmoji">
          <div class="card">
            <h2>خمن الإيموجي</h2>
            <button onclick="newEmoji()">لغز جديد للجميع</button>
            <div class="result emoji" id="emojiPuzzle">---</div>
            <label>
              الإجابة
              <input id="emojiAnswer" placeholder="اكتب الإجابة" />
            </label>
            <button onclick="answerEmoji()">تحقق</button>
            <div class="result" id="emojiResult">جاهز؟</div>
          </div>
        </section>

        <section class="tab hidden" id="tabDraw">
          <div class="card">
            <h2>لوحة رسم مشتركة</h2>
            <p>ارسم أنت وهي على نفس اللوحة. الخطوط تظهر عند الطرف الثاني مباشرة.</p>
            <div class="actions">
              <button onclick="setDrawColor('#ff5fa2')">وردي</button>
              <button onclick="setDrawColor('#8d5cff')">بنفسجي</button>
              <button onclick="setDrawColor('#111111')">أسود</button>
              <button onclick="setDrawColor('#ffd166')">ذهبي</button>
              <button class="danger" onclick="clearDraw()">مسح للجميع</button>
            </div>
            <canvas id="drawCanvas" width="1200" height="600"></canvas>
          </div>
        </section>

        <section class="tab hidden" id="tabNotes">
          <div class="grid">
            <div class="card span-8">
              <h2>صندوق الوعود والأفكار</h2>
              <label>اكتب وعد أو فكرة موعد</label>
              <textarea id="noteInput" placeholder="مثال: نوعد بعض نسمع لبعض بدون مقاطعة..."></textarea>
              <div class="actions">
                <button onclick="addNote()">إضافة للجميع</button>
                <button class="secondary" onclick="dateIdea()">اقتراح موعد</button>
              </div>
              <div class="result" id="dateResult">اقتراح الموعد يظهر هنا.</div>
            </div>
            <div class="card span-4">
              <h3>القائمة المشتركة</h3>
              <div class="players" id="notesList"></div>
            </div>
          </div>
        </section>
      </section>
    </section>
  </main>

  <div class="toast" id="toast"></div>

  <script type="module">
    import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.5/firebase-app.js";
    import {
      getDatabase,
      ref,
      set,
      update,
      get,
      onValue,
      onChildAdded,
      push,
      remove,
      serverTimestamp,
      onDisconnect,
      runTransaction
    } from "https://www.gstatic.com/firebasejs/10.12.5/firebase-database.js";

    /*
      ضع إعدادات Firebase هنا إذا تبي الملف يشتغل مباشرة بدون لصق الإعدادات من الواجهة.
      مثال:
      const FIREBASE_CONFIG = {
      "apiKey": "AIzaSyADMXsQoY1Y8hTv4UTnE-oAtuAcoRjqQgM",
      "authDomain": "adsdasd-6672f.firebaseapp.com",
      "databaseURL": "https://adsdasd-6672f-default-rtdb.firebaseio.com",
      "projectId": "adsdasd-6672f",
      "storageBucket": "adsdasd-6672f.firebasestorage.app",
      "messagingSenderId": "743897028959",
      "appId": "1:743897028959:web:e67a22d97b938324783eea",
      "measurementId": "G-PXEFSCJ6EZ"
};
    */
    const FIREBASE_CONFIG = {
      apiKey: "",
      authDomain: "",
      databaseURL: "",
      projectId: "",
      storageBucket: "",
      messagingSenderId: "",
      appId: ""
    };

    const $ = (id) => document.getElementById(id);

    let app = null;
    let db = null;
    let roomCode = null;
    let roomUnsub = null;
    let chatUnsub = null;
    let notesUnsub = null;
    let drawUnsub = null;
    let currentRoom = null;
    let currentEmojiAnswer = null;
    let ignoreOldChat = true;
    let wheelDeg = 0;

    const clientId = localStorage.getItem("coupleClientId") || crypto.randomUUID();
    localStorage.setItem("coupleClientId", clientId);

    const questionCards = [
      "وش أكثر شيء يخليك تحس إن الطرف الثاني قريب منك؟",
      "وش ذكرى بينكم تتمنى تعيشها مرة ثانية؟",
      "لو بنسافر الآن، وين تختارون؟",
      "وش أكثر كلمة تحب تسمعها من الطرف الثاني؟",
      "وش عادة صغيرة تسعدك جدًا؟",
      "وش أفضل موعد صار أو تتمنى يصير بينكم؟",
      "لو علاقتكم أغنية، وش بيكون عنوانها؟",
      "وش شيء بسيط لو سوّاه الطرف الثاني يغير يومك؟",
      "وش حلم تتمنى تحققونه مع بعض؟",
      "وش أكثر شيء يخليك تطمئن في العلاقة؟",
      "وش أكثر موقف ضحك بينكم؟",
      "وش شيء تتمنى نسويه كل أسبوع؟"
    ];

    const dareCards = [
      "مدح الطرف الثاني لمدة 30 ثانية بدون توقف.",
      "تحدي نظرات 20 ثانية، اللي يضحك يخسر.",
      "اكتب رسالة حب قصيرة في الشات الآن.",
      "اختار لقب لطيف للطرف الثاني لمدة يوم.",
      "قول ثلاث أشياء تحبها في الطرف الثاني.",
      "ارسم قلب في لوحة الرسم خلال 15 ثانية.",
      "اختاروا أغنية تكون أغنية الروم اليوم.",
      "كل واحد يكتب وعد بسيط للطرف الثاني.",
      "سووا تحدي: جواب سريع خلال 5 ثواني.",
      "الخاسر في اللعبة القادمة يرسل رسالة حلوة.",
      "كل واحد يقول ذكرى يحبها بينكم.",
      "اختاروا موعد قريب وخلوه في صندوق الوعود."
    ];

    const sweetCards = [
      "وجودك يجعل اليوم العادي يصير ذكرى.",
      "أحب تفاصيلك الصغيرة قبل الكبيرة.",
      "ضحكتك تختصر نص التعب.",
      "أنت أجمل مكان أرجع له.",
      "كل مرة أكلمك أحس الدنيا أخف.",
      "أحب إننا نخلق لحظاتنا حتى من أبسط الأشياء.",
      "قربك راحة ما تنوصف.",
      "أنت أجمل جزء في يومي."
    ];

    const deepCards = [
      "وش تحتاج وقت زعلك عشان أحسسك بالأمان؟",
      "وش أكثر شيء يخوفك في العلاقات؟",
      "كيف أقدر أكون أقرب لك؟",
      "وش طريقة الاعتذار اللي تريحك؟",
      "وش حدود تحب الطرف الثاني يحترمها دائمًا؟",
      "متى تحس إننا فريق واحد؟",
      "وش حلم خاص تبغى الطرف الثاني يكون جزء منه؟",
      "وش شيء لو تغير في علاقتنا يخليها أجمل؟"
    ];

    const wheelItems = [
      "سؤال عميق 🌙",
      "تحدي ضحك 😂",
      "رسالة حب 💌",
      "موعد قهوة ☕",
      "مدح 30 ثانية ✨",
      "لعبة إكس أو ❌",
      "لعبة الذاكرة 🃏",
      "وعد صغير 🤝"
    ];

    const activities = [
      "كل واحد يكتب 5 أشياء يحبها في الثاني.",
      "اختاروا موعد بسيط تسوونه هذا الأسبوع.",
      "تحدي نظرات 20 ثانية، اللي يضحك يخسر.",
      "ارسموا بعض في لوحة الرسم خلال دقيقة.",
      "اكتبوا وعد واحد سهل التنفيذ اليوم.",
      "كل واحد يختار أغنية تمثل الطرف الثاني.",
      "قولوا ذكرى حلوة بينكم وليه تحبونها.",
      "اسحبوا بطاقة عميقة وجاوبوا بصدق.",
      "العبوا جولة إكس أو والخاسر يمدح الفائز.",
      "سووا لغز إيموجي، والخاسر يرسل رسالة حب.",
      "كل واحد يرسل رسالة تبدأ بـ: أحب فيك...",
      "قرروا شيء لطيف تسوونه الليلة."
    ];

    const dateIdeas = [
      "ليلة فيلم + فشار + كل واحد يختار مشهد يحبه.",
      "طبخة مشتركة: واحد يختار الطبق والثاني يختار الحلى.",
      "جلسة أسئلة عميقة مع إضاءة هادئة.",
      "بطولة ألعاب: إكس أو ثم ذاكرة ثم سؤال نهائي.",
      "قهوة ومشي مع تصوير ذكرى بسيطة.",
      "مكان جديد قريب وتقييمه من 10.",
      "عشاء خفيف ثم جولة بالسيارة مع أغانيكم.",
      "جلسة امتنان: كل واحد يقول 3 أشياء ممتن لها.",
      "رسم حر على اللوحة ثم اختيار أجمل رسمة.",
      "مسابقة ضحك ونكت، اللي يضحك أول يخسر."
    ];

    const emojiPuzzles = [
      { p:"🍕🎬🏠", a:["ليلة فيلم","فيلم","فلم","موعد بيت"] },
      { p:"☕🚶‍♂️🌙", a:["قهوة ومشي","مشي وقهوة","قهوه ومشي"] },
      { p:"💌📱❤️", a:["رسالة حب","رساله حب"] },
      { p:"🎧🚗🌃", a:["جولة بالسيارة","طلعة سيارة","سيارة"] },
      { p:"🎨💖🖼️", a:["رسم قلب","رسم","لوحة"] },
      { p:"🍿😂🎞️", a:["فيلم كوميدي","فلم كوميدي","كوميديا"] },
      { p:"🧸🌙💬", a:["سوالف ليلية","سوالف","حديث"] },
      { p:"🍓🍫💝", a:["حلى","هدية حلى","شوكولاته"] }
    ];

    const quizQuestions = [
      { q:"أفضل موعد لكم؟", options:["فيلم وبيت","قهوة ومشي","مطعم","ألعاب وتحديات"] },
      { q:"أفضل طريقة للاهتمام؟", options:["كلام حلو","وقت طويل","هدايا بسيطة","مساعدة وقت الزعل"] },
      { q:"مزاجكم غالبًا؟", options:["هادئ","حماسي","رومانسي","عشوائي"] },
      { q:"أجمل هدية معنوية؟", options:["رسالة","صورة ذكرى","وعد","دعاء وكلام طيب"] },
      { q:"وقت الخلاف الأفضل؟", options:["نهدأ ثم نتكلم","نتكلم فورًا","نكتب لبعض","نمزح ونخفف"] }
    ];

    function escapeHtml(value){
      return String(value || "")
        .replaceAll("&","&amp;")
        .replaceAll("<","&lt;")
        .replaceAll(">","&gt;")
        .replaceAll('"',"&quot;")
        .replaceAll("'","&#039;");
    }

    function clean(value, fallback = ""){
      return String(value || fallback).replace(/[<>]/g,"").replace(/\s+/g," ").trim();
    }

    function pick(arr){
      return arr[Math.floor(Math.random() * arr.length)];
    }

    function toast(message){
      const el = $("toast");
      el.textContent = message;
      el.classList.add("show");
      clearTimeout(window.__toastTimer);
      window.__toastTimer = setTimeout(() => el.classList.remove("show"), 3200);
    }

    function validConfig(config){
      return config && config.apiKey && config.authDomain && config.databaseURL && config.projectId && config.appId;
    }

    function getStoredConfig(){
      try{
        const saved = JSON.parse(localStorage.getItem("firebaseConfigCoupleRoom") || "null");
        if(validConfig(saved)) return saved;
      }catch(_e){}
      if(validConfig(FIREBASE_CONFIG)) return FIREBASE_CONFIG;
      return null;
    }

    function saveFirebaseConfig(){
      try{
        const raw = $("firebaseConfigInput").value.trim();
        const parsed = JSON.parse(raw);
        if(!validConfig(parsed)){
          toast("الإعدادات ناقصة. لازم apiKey و authDomain و databaseURL و projectId و appId");
          return;
        }
        localStorage.setItem("firebaseConfigCoupleRoom", JSON.stringify(parsed));
        toast("تم حفظ إعدادات Firebase");
        initFirebase();
      }catch(err){
        toast("صيغة JSON غلط. انسخ firebaseConfig كامل بدون أخطاء.");
      }
    }

    function clearFirebaseConfig(){
      localStorage.removeItem("firebaseConfigCoupleRoom");
      toast("تم مسح إعدادات Firebase من هذا المتصفح");
      location.reload();
    }

    function initFirebase(){
      if(db) return true;
      const config = getStoredConfig();
      if(!config){
        $("setupBox").classList.remove("hidden");
        return false;
      }
      try{
        app = initializeApp(config);
        db = getDatabase(app);
        $("setupBox").classList.add("hidden");
        return true;
      }catch(err){
        console.error(err);
        toast("تعذر تشغيل Firebase. تأكد من الإعدادات.");
        $("setupBox").classList.remove("hidden");
        return false;
      }
    }

    function ensureFirebase(){
      if(initFirebase()) return true;
      toast("لازم تضيف إعدادات Firebase أولًا عشان الأونلاين يشتغل.");
      return false;
    }

    function getProfile(){
      const name = clean($("nameInput").value, localStorage.getItem("coupleName") || "ضيف").slice(0,30) || "ضيف";
      const avatar = clean($("avatarInput").value, localStorage.getItem("coupleAvatar") || "💖").slice(0,4) || "💖";
      localStorage.setItem("coupleName", name);
      localStorage.setItem("coupleAvatar", avatar);
      return { name, avatar };
    }

    function makeCode(){
      const chars = "ABCDEFGHJKLMNPQRSTUVWXYZ23456789";
      let code = "";
      for(let i=0;i<5;i++) code += chars[Math.floor(Math.random()*chars.length)];
      return code;
    }

    function makeMemoryCards(){
      const icons = ["💖","🌙","✨","🍓","🧸","💌","☕","🎧"];
      return [...icons,...icons].map((icon,i)=>({
        id:`${Date.now()}-${i}-${Math.random().toString(16).slice(2)}`,
        icon,
        open:false,
        matched:false
      })).sort(()=>Math.random()-.5);
    }

    function initialRoom(code){
      return {
        code,
        createdAt:Date.now(),
        meta:{
          lastActivity:"الروم جاهز",
          done:0
        },
        games:{
          xo:{ board:["","","","","","","","",""], turn:"💖", winner:"" },
          memory:{ cards:makeMemoryCards(), lock:false },
          quiz:{ index:0, finished:false, score:0 },
          card:{ text:"اسحب بطاقة.", label:"" },
          wheel:{ result:"النتيجة تظهر هنا.", deg:0 },
          emoji:{ puzzle:"---", answer:"" },
          date:{ text:"اقتراح الموعد يظهر هنا." }
        }
      };
    }

    async function createRoom(){
      if(!ensureFirebase()) return;
      let code = makeCode();
      let snap = await get(ref(db, `couplesTextRooms/${code}`));
      while(snap.exists()){
        code = makeCode();
        snap = await get(ref(db, `couplesTextRooms/${code}`));
      }
      await set(ref(db, `couplesTextRooms/${code}`), initialRoom(code));
      await joinRoomByCode(code);
      toast("تم إنشاء الروم الخاص");
    }

    async function joinRoom(){
      if(!ensureFirebase()) return;
      const code = clean(($("roomCodeInput").value || new URLSearchParams(location.search).get("room") || "").toUpperCase()).slice(0,8);
      if(!code){
        toast("اكتب كود الروم أولًا");
        return;
      }
      await joinRoomByCode(code);
    }

    async function joinRoomByCode(code){
      const roomRef = ref(db, `couplesTextRooms/${code}`);
      const snap = await get(roomRef);
      if(!snap.exists()){
        toast("الروم غير موجود. تأكد من الكود.");
        return;
      }

      roomCode = code;
      const profile = getProfile();
      const playerRef = ref(db, `couplesTextRooms/${code}/players/${clientId}`);
      await update(playerRef, {
        id:clientId,
        name:profile.name,
        avatar:profile.avatar,
        online:true,
        score:0,
        joinedAt:serverTimestamp(),
        lastSeen:serverTimestamp()
      });
      onDisconnect(playerRef).update({ online:false, lastSeen:serverTimestamp() });

      $("loginView").classList.add("hidden");
      $("appView").classList.remove("hidden");
      $("roomCodeLabel").textContent = code;
      history.replaceState(null,"",`${location.pathname}?room=${code}`);

      subscribeRoom(code);
      subscribeChat(code);
      subscribeNotes(code);
      subscribeDraw(code);
      toast("دخلت الروم");
    }

    function unsubscribeAll(){
      if(roomUnsub) roomUnsub();
      if(chatUnsub) chatUnsub();
      if(notesUnsub) notesUnsub();
      if(drawUnsub) drawUnsub();
      roomUnsub = chatUnsub = notesUnsub = drawUnsub = null;
    }

    async function leaveRoom(){
      if(db && roomCode){
        await update(ref(db, `couplesTextRooms/${roomCode}/players/${clientId}`), {
          online:false,
          lastSeen:serverTimestamp()
        }).catch(()=>{});
      }
      unsubscribeAll();
      roomCode = null;
      currentRoom = null;
      $("appView").classList.add("hidden");
      $("loginView").classList.remove("hidden");
      history.replaceState(null,"",location.pathname);
      toast("خرجت من الروم");
    }

    function subscribeRoom(code){
      if(roomUnsub) roomUnsub();
      roomUnsub = onValue(ref(db, `couplesTextRooms/${code}`), (snap)=>{
        if(!snap.exists()) return;
        currentRoom = snap.val();
        renderRoom(currentRoom);
      });
    }

    function subscribeChat(code){
      if(chatUnsub) chatUnsub();
      ignoreOldChat = true;
      setTimeout(()=>{ ignoreOldChat = false; }, 1200);
      const chatRef = ref(db, `couplesTextRooms/${code}/chat`);
      chatUnsub = onChildAdded(chatRef, (snap)=>{
        const msg = { id:snap.key, ...snap.val() };
        addMessageToUI(msg);
        if(!ignoreOldChat && msg.senderId !== clientId && !msg.system){
          incomingMessageNotify(msg);
        }
      });
      $("chatMessages").innerHTML = "";
    }

    function subscribeNotes(code){
      if(notesUnsub) notesUnsub();
      notesUnsub = onValue(ref(db, `couplesTextRooms/${code}/notes`), (snap)=>{
        const notes = snap.val() || {};
        const arr = Object.entries(notes).map(([id,n])=>({id,...n})).sort((a,b)=>(b.createdAt || 0) - (a.createdAt || 0));
        $("notesList").innerHTML = arr.length ? arr.map(n=>`
          <div class="player">
            <div>
              <strong>${escapeHtml(n.text)}</strong>
              <span class="small">${escapeHtml(n.byName || "")}</span>
            </div>
            <button class="small-btn danger" onclick="removeNote('${n.id}')">حذف</button>
          </div>
        `).join("") : `<div class="small">مافي وعود أو أفكار حتى الآن.</div>`;
      });
    }

    function subscribeDraw(code){
      if(drawUnsub) drawUnsub();
      drawUnsub = onChildAdded(ref(db, `couplesTextRooms/${code}/drawLines`), (snap)=>{
        const line = snap.val();
        if(!line) return;
        if(line.clear){
          ctx.clearRect(0,0,canvas.width,canvas.height);
          return;
        }
        if(line.senderId === clientId) return;
        drawLine(line.from, line.to, line.color, false);
      });
    }

    function renderRoom(room){
      const meta = room.meta || {};
      const games = room.games || {};
      const players = Object.values(room.players || {}).sort((a,b)=>(b.online===true)-(a.online===true));

      $("roomCodeLabel").textContent = room.code || roomCode || "-----";
      $("lastActivity").textContent = meta.lastActivity || "الروم جاهز";
      $("doneCount").textContent = meta.done || 0;

      $("playersList").innerHTML = players.map((u)=>`
        <div class="player">
          <div>
            <strong><span class="status-dot ${u.online ? "on" : ""}"></span>${escapeHtml(u.avatar || "💖")} ${escapeHtml(u.name || "ضيف")} ${u.id === clientId ? "أنت" : ""}</strong>
            <span class="small">${u.online ? "متصل الآن" : "غير متصل"}</span>
          </div>
          <div class="score">${u.score || 0}</div>
        </div>
      `).join("");

      renderAchievements(players);

      if(games.card) $("cardResult").textContent = games.card.label ? `${games.card.label}\n\n${games.card.text}` : (games.card.text || "اسحب بطاقة.");
      if(games.wheel){
        $("wheelResult").textContent = games.wheel.result || "النتيجة تظهر هنا.";
        if(Number(games.wheel.deg || 0) !== wheelDeg){
          wheelDeg = Number(games.wheel.deg || 0);
          $("wheel").style.transform = `rotate(${wheelDeg}deg)`;
        }
      }
      if(games.xo) renderXO(games.xo);
      if(games.memory) renderMemory(games.memory);
      if(games.quiz) renderQuiz(games.quiz);
      if(games.emoji){
        $("emojiPuzzle").textContent = games.emoji.puzzle || "---";
        currentEmojiAnswer = games.emoji.answer || "";
      }
      if(games.date) $("dateResult").textContent = games.date.text || "اقتراح الموعد يظهر هنا.";
    }

    function addMessageToUI(msg){
      const box = $("chatMessages");
      const div = document.createElement("div");
      div.className = msg.system ? "message system" : `message ${msg.senderId === clientId ? "me" : ""}`;
      if(msg.system){
        div.innerHTML = `${escapeHtml(msg.text)}<small>${formatTime(msg.createdAt)}</small>`;
      }else{
        div.innerHTML = `<b>${escapeHtml(msg.avatar || "")} ${escapeHtml(msg.name || "ضيف")}</b><div>${escapeHtml(msg.text)}</div><small>${formatTime(msg.createdAt)}</small>`;
      }
      box.appendChild(div);
      box.scrollTop = box.scrollHeight;
    }

    function formatTime(ts){
      try{
        if(typeof ts === "number") return new Date(ts).toLocaleTimeString("ar-SA",{hour:"2-digit",minute:"2-digit"});
      }catch(_e){}
      return new Date().toLocaleTimeString("ar-SA",{hour:"2-digit",minute:"2-digit"});
    }

    async function sendChat(){
      if(!roomCode) return toast("ادخل روم أولًا");
      const input = $("chatInput");
      const text = clean(input.value).slice(0,400);
      if(!text) return;
      const profile = getProfile();
      await push(ref(db, `couplesTextRooms/${roomCode}/chat`), {
        senderId:clientId,
        name:profile.name,
        avatar:profile.avatar,
        text,
        createdAt:Date.now()
      });
      input.value = "";
      toast("تم إرسال الرسالة ✅");
      beep(540, .05);
    }

    function incomingMessageNotify(msg){
      const title = `رسالة من ${msg.name || "الطرف الثاني"}`;
      const body = msg.text || "";
      toast(`${title}: ${body}`);
      beep(760, .08);

      if("Notification" in window && Notification.permission === "granted" && document.hidden){
        new Notification(title, {
          body,
          tag:`couple-room-${roomCode}`,
          icon:"data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='128' height='128'%3E%3Crect width='128' height='128' rx='32' fill='%23ff5fa2'/%3E%3Ctext x='64' y='82' font-size='66' text-anchor='middle'%3E%F0%9F%92%96%3C/text%3E%3C/svg%3E"
        });
      }
    }

    async function requestNotify(){
      if(!("Notification" in window)){
        toast("متصفحك لا يدعم إشعارات المتصفح، لكن تنبيهات الموقع تعمل.");
        updateNotifyStatus();
        return;
      }
      const result = await Notification.requestPermission();
      updateNotifyStatus();
      toast(result === "granted" ? "تم تفعيل الإشعارات 🔔" : "لم يتم السماح بالإشعارات");
    }

    function updateNotifyStatus(){
      const ok = "Notification" in window && Notification.permission === "granted";
      $("notifyStatus").textContent = ok ? "مفعّلة 🔔" : "غير مفعّلة";
    }

    function testNotify(){
      const fake = { name:"تجربة", text:"هذا تنبيه تجريبي للرسائل" };
      incomingMessageNotify(fake);
    }

    function beep(freq = 660, duration = .07){
      try{
        const AudioContext = window.AudioContext || window.webkitAudioContext;
        const ac = new AudioContext();
        const osc = ac.createOscillator();
        const gain = ac.createGain();
        osc.frequency.value = freq;
        gain.gain.value = 0.035;
        osc.connect(gain);
        gain.connect(ac.destination);
        osc.start();
        osc.stop(ac.currentTime + duration);
        setTimeout(()=>ac.close(), 250);
      }catch(_e){}
    }

    function copyInvite(){
      if(!roomCode) return;
      const url = `${location.origin}${location.pathname}?room=${roomCode}`;
      navigator.clipboard.writeText(url).then(()=>toast("تم نسخ رابط الروم"));
    }

    function showTab(id){
      document.querySelectorAll(".tab").forEach(tab=>tab.classList.add("hidden"));
      $(id).classList.remove("hidden");
      document.querySelectorAll(".tabs button").forEach(btn=>btn.classList.remove("active"));
      const clicked = [...document.querySelectorAll(".tabs button")].find(b=>b.getAttribute("onclick")?.includes(id));
      if(clicked) clicked.classList.add("active");
    }

    async function setMetaActivity(label){
      if(!roomCode) return;
      await update(ref(db, `couplesTextRooms/${roomCode}/meta`), { lastActivity:label });
    }

    async function completeActivity(label, points = 10){
      if(!roomCode) return toast("ادخل روم أولًا");
      await runTransaction(ref(db, `couplesTextRooms/${roomCode}/players/${clientId}/score`), (value)=>(value || 0) + points);
      await runTransaction(ref(db, `couplesTextRooms/${roomCode}/meta/done`), (value)=>(value || 0) + 1);
      await setMetaActivity(label || "فعالية مكتملة");
      burstHearts(12);
      toast(`تم احتساب ${points}+ نقطة`);
    }

    function randomActivity(){
      $("homeResult").textContent = pick(activities);
    }

    async function drawCard(type){
      if(!roomCode) return toast("ادخل روم أولًا");
      const decks = { question:questionCards, dare:dareCards, sweet:sweetCards, deep:deepCards };
      const labels = { question:"سؤال", dare:"تحدي", sweet:"كلام حلو", deep:"سؤال عميق" };
      await set(ref(db, `couplesTextRooms/${roomCode}/games/card`), {
        type,
        label:labels[type] || "بطاقة",
        text:pick(decks[type] || questionCards),
        by:clientId,
        at:Date.now()
      });
      await setMetaActivity(labels[type] || "بطاقة");
      showTab("tabCards");
    }

    async function spinWheel(){
      if(!roomCode) return toast("ادخل روم أولًا");
      const index = Math.floor(Math.random() * wheelItems.length);
      const result = wheelItems[index];
      wheelDeg += 1440 + index * 45 + Math.floor(Math.random()*40);
      await set(ref(db, `couplesTextRooms/${roomCode}/games/wheel`), {
        index,
        result,
        deg:wheelDeg,
        at:Date.now()
      });
      await setMetaActivity(result);
      showTab("tabWheel");
    }

    function renderXO(xo){
      const board = Array.isArray(xo.board) ? xo.board : ["","","","","","","","",""];
      $("xoStatus").textContent = xo.winner ? (xo.winner === "تعادل" ? "تعادل 🤝" : `الفائز ${xo.winner} 🎉`) : `دور ${xo.turn || "💖"}`;
      $("xoBoard").innerHTML = board.map((cell,i)=>`<div class="cell" onclick="playXO(${i})">${escapeHtml(cell || "")}</div>`).join("");
    }

    function checkXOWinner(board){
      const wins = [[0,1,2],[3,4,5],[6,7,8],[0,3,6],[1,4,7],[2,5,8],[0,4,8],[2,4,6]];
      for(const [a,b,c] of wins){
        if(board[a] && board[a] === board[b] && board[a] === board[c]) return board[a];
      }
      return board.every(Boolean) ? "تعادل" : "";
    }

    async function playXO(index){
      if(!roomCode || !currentRoom) return;
      const xo = currentRoom.games?.xo || { board:["","","","","","","","",""], turn:"💖", winner:"" };
      const board = Array.isArray(xo.board) ? [...xo.board] : ["","","","","","","","",""];
      if(xo.winner || board[index]) return;
      board[index] = xo.turn || "💖";
      const winner = checkXOWinner(board);
      const nextTurn = (xo.turn || "💖") === "💖" ? "🌙" : "💖";
      await set(ref(db, `couplesTextRooms/${roomCode}/games/xo`), {
        board,
        turn:winner ? (xo.turn || "💖") : nextTurn,
        winner
      });
      if(winner && winner !== "تعادل") await completeActivity("فوز في إكس أو",15);
      if(winner === "تعادل") await setMetaActivity("تعادل في إكس أو");
    }

    async function resetXO(){
      if(!roomCode) return;
      await set(ref(db, `couplesTextRooms/${roomCode}/games/xo`), { board:["","","","","","","","",""], turn:"💖", winner:"" });
    }

    function renderMemory(memory){
      const cards = Array.isArray(memory.cards) ? memory.cards : [];
      $("memoryBoard").innerHTML = cards.map(card=>`
        <div class="memory-card ${card.matched ? "matched" : ""}" onclick="flipMemory('${card.id}')">${card.open || card.matched ? card.icon : "?"}</div>
      `).join("");
    }

    async function resetMemory(){
      if(!roomCode) return;
      await set(ref(db, `couplesTextRooms/${roomCode}/games/memory`), { cards:makeMemoryCards(), lock:false, firstId:"" });
      await setMetaActivity("خلط لعبة الذاكرة");
    }

    async function flipMemory(id){
      if(!roomCode || !currentRoom) return;
      const memory = currentRoom.games?.memory || { cards:[] };
      if(memory.lock) return;
      const cards = JSON.parse(JSON.stringify(memory.cards || []));
      const card = cards.find(c=>c.id === id);
      if(!card || card.open || card.matched) return;

      const openCards = cards.filter(c=>c.open && !c.matched);
      card.open = true;

      if(openCards.length === 0){
        await set(ref(db, `couplesTextRooms/${roomCode}/games/memory`), { cards, lock:false, firstId:id });
        return;
      }

      const first = cards.find(c=>c.id === openCards[0].id);
      if(first && first.icon === card.icon){
        first.matched = true;
        card.matched = true;
        first.open = true;
        card.open = true;
        await set(ref(db, `couplesTextRooms/${roomCode}/games/memory`), { cards, lock:false, firstId:"" });
        await completeActivity("تطابق في الذاكرة",5);
        if(cards.every(c=>c.matched)) await completeActivity("إنهاء لعبة الذاكرة",20);
      }else{
        await set(ref(db, `couplesTextRooms/${roomCode}/games/memory`), { cards, lock:true, firstId:"" });
        setTimeout(async()=>{
          const snap = await get(ref(db, `couplesTextRooms/${roomCode}/games/memory/cards`));
          const latest = snap.val() || cards;
          const latestCards = Array.isArray(latest) ? latest : Object.values(latest);
          latestCards.forEach(c=>{ if(!c.matched) c.open = false; });
          await set(ref(db, `couplesTextRooms/${roomCode}/games/memory`), { cards:latestCards, lock:false, firstId:"" });
        },850);
      }
    }

    function renderQuiz(quiz){
      const index = quiz.index || 0;
      const q = quizQuestions[index];
      $("quizProgress").style.width = `${quiz.finished ? 100 : Math.round((index / quizQuestions.length) * 100)}%`;
      if(quiz.finished){
        $("quizQuestion").textContent = "انتهى الاختبار";
        $("quizOptions").innerHTML = "";
        $("quizResult").textContent = `نسبة التوافق: ${quiz.score || 90}% 💞\nواضح بينكم أشياء مشتركة جميلة، والاختلاف يعطيكم سوالف أكثر.`;
        return;
      }
      $("quizQuestion").textContent = `سؤال ${index+1}: ${q.q}`;
      $("quizOptions").innerHTML = q.options.map((op,i)=>`<button class="option" onclick="answerQuiz(${i})">${escapeHtml(op)}</button>`).join("");
      $("quizResult").textContent = "اختار جوابك، وبعدها اضغطوا السؤال التالي.";
    }

    async function startQuiz(){
      if(!roomCode) return;
      await set(ref(db, `couplesTextRooms/${roomCode}/games/quiz`), { index:0, finished:false, score:0, answers:{} });
      await setMetaActivity("اختبار التوافق");
    }

    async function answerQuiz(answerIndex){
      if(!roomCode || !currentRoom) return;
      const index = currentRoom.games?.quiz?.index || 0;
      await set(ref(db, `couplesTextRooms/${roomCode}/games/quiz/answers/${clientId}/${index}`), answerIndex);
      document.querySelectorAll("#quizOptions .option").forEach((btn,i)=>btn.classList.toggle("selected", i === answerIndex));
    }

    async function nextQuiz(){
      if(!roomCode || !currentRoom) return;
      const quiz = currentRoom.games?.quiz || { index:0, answers:{} };
      const index = quiz.index || 0;
      if(index < quizQuestions.length - 1){
        await update(ref(db, `couplesTextRooms/${roomCode}/games/quiz`), { index:index+1 });
      }else{
        const values = [];
        Object.values(quiz.answers || {}).forEach(arr=>{
          if(Array.isArray(arr)) arr.forEach(x=>Number.isInteger(x) && values.push(x));
          else Object.values(arr || {}).forEach(x=>Number.isInteger(x) && values.push(x));
        });
        const variety = new Set(values).size;
        const score = Math.min(99, 74 + variety * 4 + Math.floor(Math.random()*9));
        await update(ref(db, `couplesTextRooms/${roomCode}/games/quiz`), { finished:true, score });
        await completeActivity("اختبار التوافق",20);
      }
    }

    async function newEmoji(){
      if(!roomCode) return;
      const item = pick(emojiPuzzles);
      await set(ref(db, `couplesTextRooms/${roomCode}/games/emoji`), {
        puzzle:item.p,
        answer:item.a[0],
        answers:item.a,
        at:Date.now()
      });
      await setMetaActivity("لغز إيموجي");
      showTab("tabEmoji");
    }

    async function answerEmoji(){
      if(!roomCode || !currentRoom) return;
      const ans = clean($("emojiAnswer").value).toLowerCase();
      if(!ans) return;
      const answers = currentRoom.games?.emoji?.answers || [currentEmojiAnswer];
      const ok = answers.some(x=>ans.includes(String(x).toLowerCase()) || String(x).toLowerCase() === ans);
      if(ok){
        $("emojiResult").textContent = "صح عليك! ✅";
        $("emojiAnswer").value = "";
        await completeActivity("حل لغز إيموجي",10);
      }else{
        $("emojiResult").textContent = "غلط، جرب جواب ثاني 😄";
      }
    }

    async function dateIdea(){
      if(!roomCode) return;
      const text = pick(dateIdeas);
      await set(ref(db, `couplesTextRooms/${roomCode}/games/date`), { text, at:Date.now() });
      await push(ref(db, `couplesTextRooms/${roomCode}/notes`), {
        text:`فكرة موعد: ${text}`,
        by:clientId,
        byName:getProfile().name,
        createdAt:Date.now()
      });
      await setMetaActivity("اقتراح موعد");
    }

    async function addNote(){
      if(!roomCode) return;
      const text = clean($("noteInput").value).slice(0,280);
      if(!text) return;
      await push(ref(db, `couplesTextRooms/${roomCode}/notes`), {
        text,
        by:clientId,
        byName:getProfile().name,
        createdAt:Date.now()
      });
      $("noteInput").value = "";
      toast("تمت إضافة الوعد/الفكرة للجميع");
    }

    async function removeNote(id){
      if(!roomCode) return;
      await remove(ref(db, `couplesTextRooms/${roomCode}/notes/${id}`));
    }

    function renderAchievements(players){
      const me = players.find(u=>u.id === clientId);
      const score = me ? (me.score || 0) : 0;
      const data = [
        ["بداية الحب",10,"🌱"],
        ["ثنائي نشيط",50,"⚡"],
        ["قلوب محترفة",100,"💖"],
        ["أبطال الروم",200,"🏆"],
        ["أسطورة الروم",500,"👑"]
      ];
      $("achievements").innerHTML = data.map(([name,need,icon])=>`
        <div class="achievement ${score >= need ? "open" : ""}">
          <span>${icon} ${name}</span>
          <b>${score >= need ? "مفتوح" : need + " نقطة"}</b>
        </div>
      `).join("");
    }

    const canvas = $("drawCanvas");
    const ctx = canvas.getContext("2d");
    let drawing = false;
    let lastPoint = null;
    let drawColor = "#ff5fa2";
    ctx.lineWidth = 7;
    ctx.lineCap = "round";
    ctx.lineJoin = "round";

    function setDrawColor(color){
      drawColor = color;
    }

    function canvasPos(event){
      const rect = canvas.getBoundingClientRect();
      const t = event.touches ? event.touches[0] : event;
      return {
        x:(t.clientX - rect.left) * (canvas.width / rect.width),
        y:(t.clientY - rect.top) * (canvas.height / rect.height)
      };
    }

    function drawLine(from,to,color,emit = false){
      if(!from || !to) return;
      ctx.strokeStyle = color || drawColor;
      ctx.beginPath();
      ctx.moveTo(from.x, from.y);
      ctx.lineTo(to.x, to.y);
      ctx.stroke();
      if(emit && roomCode){
        push(ref(db, `couplesTextRooms/${roomCode}/drawLines`), {
          senderId:clientId,
          from,
          to,
          color:drawColor,
          at:Date.now()
        });
      }
    }

    function startDraw(event){
      drawing = true;
      lastPoint = canvasPos(event);
    }

    function moveDraw(event){
      if(!drawing) return;
      event.preventDefault();
      const point = canvasPos(event);
      drawLine(lastPoint, point, drawColor, true);
      lastPoint = point;
    }

    function endDraw(){
      drawing = false;
      lastPoint = null;
    }

    async function clearDraw(){
      ctx.clearRect(0,0,canvas.width,canvas.height);
      if(roomCode){
        await push(ref(db, `couplesTextRooms/${roomCode}/drawLines`), { clear:true, senderId:clientId, at:Date.now() });
      }
    }

    canvas.addEventListener("mousedown", startDraw);
    canvas.addEventListener("mousemove", moveDraw);
    window.addEventListener("mouseup", endDraw);
    canvas.addEventListener("touchstart", startDraw, { passive:false });
    canvas.addEventListener("touchmove", moveDraw, { passive:false });
    canvas.addEventListener("touchend", endDraw);

    function makeHearts(){
      const box = $("hearts");
      for(let i=0;i<26;i++){
        const heart = document.createElement("span");
        heart.className = "heart";
        heart.textContent = ["💗","💖","💘","💕"][i%4];
        heart.style.left = `${Math.random()*100}%`;
        heart.style.animationDuration = `${7 + Math.random()*11}s`;
        heart.style.animationDelay = `${-Math.random()*12}s`;
        heart.style.fontSize = `${16 + Math.random()*24}px`;
        box.appendChild(heart);
      }
    }

    function burstHearts(n){
      for(let i=0;i<n;i++){
        const h = document.createElement("div");
        h.textContent = "💖";
        h.style.position = "fixed";
        h.style.zIndex = "99";
        h.style.left = `${45 + Math.random()*10}%`;
        h.style.top = "58%";
        h.style.fontSize = `${22 + Math.random()*22}px`;
        h.style.pointerEvents = "none";
        h.style.transition = "1.1s ease";
        document.body.appendChild(h);
        requestAnimationFrame(()=>{
          h.style.transform = `translate(${(Math.random()-.5)*260}px, ${-180-Math.random()*180}px) rotate(${Math.random()*260}deg)`;
          h.style.opacity = "0";
        });
        setTimeout(()=>h.remove(),1200);
      }
    }

    window.addEventListener("beforeunload", ()=>{
      if(db && roomCode){
        update(ref(db, `couplesTextRooms/${roomCode}/players/${clientId}`), {
          online:false,
          lastSeen:serverTimestamp()
        }).catch(()=>{});
      }
    });

    function initPage(){
      makeHearts();
      updateNotifyStatus();
      $("nameInput").value = localStorage.getItem("coupleName") || "";
      $("avatarInput").value = localStorage.getItem("coupleAvatar") || "💖";
      const savedConfig = getStoredConfig();
      if(savedConfig){
        $("firebaseConfigInput").value = JSON.stringify(savedConfig, null, 2);
        initFirebase();
      }else{
        $("setupBox").classList.remove("hidden");
      }
      const urlRoom = new URLSearchParams(location.search).get("room");
      if(urlRoom) $("roomCodeInput").value = clean(urlRoom.toUpperCase()).slice(0,8);
      $("xoBoard").innerHTML = Array.from({length:9}).map((_,i)=>`<div class="cell" onclick="playXO(${i})"></div>`).join("");
    }

    Object.assign(window, {
      saveFirebaseConfig,
      clearFirebaseConfig,
      createRoom,
      joinRoom,
      leaveRoom,
      copyInvite,
      showTab,
      sendChat,
      requestNotify,
      testNotify,
      randomActivity,
      completeActivity,
      drawCard,
      spinWheel,
      playXO,
      resetXO,
      resetMemory,
      flipMemory,
      startQuiz,
      answerQuiz,
      nextQuiz,
      newEmoji,
      answerEmoji,
      dateIdea,
      addNote,
      removeNote,
      setDrawColor,
      clearDraw
    });

    initPage();
  </script>
</body>
</html>
