# Zairon-support-
<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>پشتیبانی ۲۴ ساعته زایرون | Zayron Panel</title>
<style>
  :root{
    --bg:#0a0d1a; --bg2:#121830; --card:#151c38; --card2:#1c2547;
    --line:#2a3560; --txt:#e8ecff; --muted:#8b96c4;
    --accent:#00d4ff; --accent2:#a855f7; --user:#0ea5e9; --bot:#1a2244;
    --ok:#22e07c; --warn:#ffb84d; --danger:#ff4d6d; --gold:#ffd166;
  }
  *{box-sizing:border-box;margin:0;padding:0}
  html,body{height:100%}
  body{
    font-family:"Vazirmatn","Segoe UI",Tahoma,system-ui,sans-serif;
    background:
      radial-gradient(1200px 700px at 100% 0%, #0d2a4a 0%, transparent 55%),
      radial-gradient(1000px 700px at 0% 100%, #2a0d4a 0%, transparent 55%),
      var(--bg);
    color:var(--txt);
    display:flex; align-items:center; justify-content:center;
    padding:16px; min-height:100dvh;
  }
  .app{
    width:100%; max-width:900px; height:min(93dvh, 880px);
    background:linear-gradient(180deg, rgba(21,28,56,.96), rgba(10,13,26,.98));
    border:1px solid var(--line); border-radius:24px;
    display:flex; flex-direction:column; overflow:hidden;
    box-shadow:0 30px 90px rgba(0,0,0,.6), 0 0 0 1px rgba(0,212,255,.06), inset 0 1px 0 rgba(255,255,255,.06);
    backdrop-filter:blur(12px);
  }
  header{
    display:flex; align-items:center; gap:12px; padding:14px 18px;
    border-bottom:1px solid var(--line);
    background:linear-gradient(90deg, rgba(0,212,255,.10), rgba(168,85,247,.10));
  }
  .avatar{
    width:48px;height:48px;border-radius:14px;flex:none;
    background:linear-gradient(135deg,var(--accent),var(--accent2));
    display:grid;place-items:center;font-size:22px;font-weight:900;color:#001;
    box-shadow:0 8px 26px rgba(0,212,255,.45); position:relative;
    letter-spacing:-1px;
  }
  .avatar::after{
    content:"";position:absolute;bottom:-3px;left:-3px;
    width:15px;height:15px;border-radius:50%;
    background:var(--ok);border:3px solid var(--card);
    box-shadow:0 0 10px var(--ok);
  }
  .head-txt h1{font-size:16px;font-weight:800;display:flex;align-items:center;gap:8px}
  .badge{
    font-size:9.5px;font-weight:700;padding:3px 7px;border-radius:6px;
    background:linear-gradient(135deg,var(--accent),var(--accent2));
    color:#001;letter-spacing:.3px;
  }
  .head-txt p{font-size:12px;color:var(--muted);margin-top:4px;display:flex;align-items:center;gap:6px}
  .dot{width:7px;height:7px;border-radius:50%;background:var(--ok);box-shadow:0 0 8px var(--ok);animation:pulse 1.8s infinite}
  @keyframes pulse{50%{opacity:.35}}
  .head-actions{margin-inline-start:auto;display:flex;gap:8px}
  .icon-btn{
    width:38px;height:38px;border-radius:11px;border:1px solid var(--line);
    background:var(--card2);color:var(--txt);cursor:pointer;font-size:16px;
    display:grid;place-items:center;transition:.2s;
  }
  .icon-btn:hover{background:var(--accent);border-color:var(--accent);color:#001;transform:translateY(-1px)}

  .chat{
    flex:1; overflow-y:auto; padding:20px 18px;
    display:flex; flex-direction:column; gap:14px; scroll-behavior:smooth;
  }
  .chat::-webkit-scrollbar{width:8px}
  .chat::-webkit-scrollbar-thumb{background:#2c3766;border-radius:8px}
  .chat::-webkit-scrollbar-track{background:transparent}

  .msg{
    max-width:80%; padding:12px 15px; border-radius:16px;
    line-height:1.95; font-size:14.5px; word-wrap:break-word;
    animation:pop .25s ease;
  }
  @keyframes pop{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:none}}
  .msg.user{
    align-self:flex-start;
    background:linear-gradient(135deg,var(--user),#0369a1);
    border-end-start-radius:5px;
    box-shadow:0 8px 22px rgba(14,165,233,.3);
  }
  .msg.bot{
    align-self:flex-end; background:var(--bot);
    border:1px solid var(--line); border-end-end-radius:5px;
  }
  .msg.roast{
    align-self:flex-end;
    background:linear-gradient(135deg, rgba(255,77,109,.18), rgba(168,85,247,.18));
    border:1px solid rgba(255,77,109,.5);
    color:#ffd0d9;
  }
  .msg.error{
    align-self:flex-end; background:rgba(255,77,109,.12);
    border:1px solid rgba(255,77,109,.45); color:#ffc2c8;
  }
  .msg b{color:#fff}
  .msg .hl{color:var(--gold);font-weight:800;direction:ltr;display:inline-block;unicode-bidi:embed}
  .msg code{
    background:rgba(0,212,255,.12);color:#7fe6ff;
    padding:2px 7px;border-radius:6px;
    font-size:13px;direction:ltr;display:inline-block;unicode-bidi:embed;
    border:1px solid rgba(0,212,255,.25);
  }

  .typing{display:flex;gap:5px;padding:6px 4px}
  .typing span{width:8px;height:8px;border-radius:50%;background:var(--muted);animation:bounce 1.2s infinite}
  .typing span:nth-child(2){animation-delay:.15s}
  .typing span:nth-child(3){animation-delay:.3s}
  @keyframes bounce{0%,60%,100%{transform:translateY(0);opacity:.4}30%{transform:translateY(-6px);opacity:1}}

  .quick{display:flex;flex-wrap:wrap;gap:8px;padding:0 18px 12px}
  .chip{
    background:var(--card2);border:1px solid var(--line);color:var(--txt);
    padding:8px 14px;border-radius:999px;font-size:12.5px;cursor:pointer;
    font-family:inherit;transition:.2s;
  }
  .chip:hover{background:var(--accent);border-color:var(--accent);color:#001;transform:translateY(-2px);font-weight:700}

  .composer{
    display:flex;gap:10px;align-items:flex-end;
    padding:14px 18px;border-top:1px solid var(--line);
    background:rgba(10,13,26,.65);
  }
  textarea{
    flex:1;resize:none;max-height:130px;min-height:48px;
    background:var(--card2);border:1px solid var(--line);color:var(--txt);
    border-radius:14px;padding:13px 15px;font-family:inherit;font-size:14.5px;
    line-height:1.7;outline:none;transition:.2s;
  }
  textarea:focus{border-color:var(--accent);box-shadow:0 0 0 3px rgba(0,212,255,.15)}
  textarea::placeholder{color:var(--muted)}
  .send{
    width:48px;height:48px;flex:none;border:none;border-radius:14px;cursor:pointer;
    background:linear-gradient(135deg,var(--accent),var(--accent2));
    color:#001;font-size:19px;font-weight:900;display:grid;place-items:center;
    transition:.2s;box-shadow:0 8px 22px rgba(0,212,255,.35);
  }
  .send:hover{transform:translateY(-2px);filter:brightness(1.1)}
  .send:disabled{opacity:.4;cursor:not-allowed;transform:none}

  .overlay{
    position:fixed;inset:0;background:rgba(5,8,18,.78);
    backdrop-filter:blur(6px);display:none;place-items:center;z-index:50;padding:16px;
  }
  .overlay.show{display:grid}
  .modal{
    width:100%;max-width:480px;background:var(--card);
    border:1px solid var(--line);border-radius:20px;padding:22px;
    max-height:90dvh;overflow-y:auto;animation:pop .25s ease;
  }
  .modal h2{font-size:17px;margin-bottom:6px}
  .modal .hint{font-size:12px;color:var(--muted);line-height:1.9;margin-bottom:18px}
  .field{margin-bottom:14px}
  .field label{display:block;font-size:12.5px;color:var(--muted);margin-bottom:7px}
  .field input,.field textarea{
    width:100%;background:var(--bg2);border:1px solid var(--line);color:var(--txt);
    border-radius:11px;padding:11px 13px;font-family:inherit;font-size:13.5px;outline:none;
  }
  .field input:focus,.field textarea:focus{border-color:var(--accent)}
  .field textarea{resize:vertical;min-height:90px;line-height:1.8}
  .modal-actions{display:flex;gap:10px;margin-top:20px}
  .btn{
    flex:1;padding:12px;border-radius:12px;border:1px solid var(--line);
    background:var(--card2);color:var(--txt);font-family:inherit;font-size:14px;
    cursor:pointer;transition:.2s;
  }
  .btn:hover{background:#26315c}
  .btn.primary{background:linear-gradient(135deg,var(--accent),var(--accent2));border:none;color:#001;font-weight:700}
  .btn.primary:hover{filter:brightness(1.1)}
  .warn{
    font-size:11.5px;color:#ffcf8b;background:rgba(255,180,60,.10);
    border:1px solid rgba(255,180,60,.3);border-radius:10px;padding:9px 11px;
    line-height:1.8;margin-top:4px;
  }
  @media (max-width:560px){
    body{padding:0}
    .app{height:100dvh;border-radius:0;border:none;max-width:none}
    .msg{max-width:88%}
  }
</style>
</head>
<body>

<div class="app">
  <header>
    <div class="avatar">Z</div>
    <div class="head-txt">
      <h1>پشتیبانی زایرون <span class="badge">ZAYRON</span></h1>
      <p><span class="dot"></span><span id="statusText">پشتیبانی ۲۴ ساعته زایرون پنل</span></p>
    </div>
    <div class="head-actions">
      <button class="icon-btn" id="clearBtn" title="گفتگوی جدید">🗑️</button>
      <button class="icon-btn" id="settingsBtn" title="تنظیمات هوش مصنوعی">⚙️</button>
    </div>
  </header>

  <div class="chat" id="chat"></div>

  <div class="quick" id="quick">
    <button class="chip">چیت و پنل رو از کجا بخرم؟</button>
    <button class="chip">قیمت پنل چنده؟</button>
    <button class="chip">کانال روبیکا و تلگرامتون چیه؟</button>
    <button class="chip">پنل چیه و چیکار میکنه؟</button>
    <button class="chip">تضمین و گارانتی دارید؟</button>
    <button class="chip">پشتیبانی ۲۴ ساعته ست؟</button>
  </div>

  <div class="composer">
    <textarea id="input" rows="1" placeholder="پیام خود را بنویسید... (Enter = ارسال)"></textarea>
    <button class="send" id="sendBtn" title="ارسال">➤</button>
  </div>
</div>

<div class="overlay" id="overlay">
  <div class="modal">
    <h2>⚙️ تنظیمات هوش مصنوعی</h2>
    <p class="hint">
      برنامه به‌صورت پیش‌فرض با «پایگاه دانش زایرون» جواب می‌دهد و نیازی به کلید ندارد.
      اگر می‌خواهید به هوش مصنوعی واقعی وصل شود، اطلاعات سرویس سازگار با OpenAI را وارد کنید.
    </p>
    <div class="field">
      <label>آدرس API (Endpoint)</label>
      <input id="cfgUrl" type="text" dir="ltr" placeholder="https://api.openai.com/v1/chat/completions">
    </div>
    <div class="field">
      <label>کلید API (خالی = حالت محلی)</label>
      <input id="cfgKey" type="password" dir="ltr" placeholder="sk-...">
    </div>
    <div class="field">
      <label>نام مدل</label>
      <input id="cfgModel" type="text" dir="ltr" placeholder="gpt-4o-mini">
    </div>
    <div class="field">
      <label>شخصیت دستیار (System Prompt)</label>
      <textarea id="cfgSystem" dir="rtl"></textarea>
    </div>
    <div class="warn">
      ⚠️ کلید API فقط در مرورگر خودتان (localStorage) ذخیره می‌شود.
    </div>
    <div class="modal-actions">
      <button class="btn" id="cancelBtn">انصراف</button>
      <button class="btn primary" id="saveBtn">ذخیره</button>
    </div>
  </div>
</div>

<script>
/* =========================================================
   ثابت‌های برند
========================================================= */
const BRAND = "زایرون";
const CHANNEL = "@panel_chit_zayron";
const CHANNEL_LINK = "@panel_chit_zayron";

/* =========================================================
   ۱) تشخیص فحش و توهین
========================================================= */
const INSULT_WORDS = [
  "کص","کوص","کیر","کون","جنده","جاکش","حرومی","حرومزاده","مادرجنده","مادرقهوه",
  "مادرتو","خارکصه","بی ناموس","بی ناموس","ناموس","لاشی","بیشعور","نفهم","کمه فهم",
  "کمه‌فهم","احمق","ابله","خرفت","خری","خر ","گاو","سگ","سگ‌","پدرسگ","پدر سگ",
  "سگ زاده","کثافت","کثافتکاری","اشغال","اشغالی","آشغال","آشغالی","چرت","مزخرف",
  "گوه","گه","گهی","شاش","جیش","عن","عوضی","ابلهی","دیوانه","دیوونه","مغز کیری",
  "توله سگ","توله‌سگ","خوک","خوکی","پفیوز","پفوز","لجن","کرم","کرمی","کرم‌",
  "مادرخر","خواهرجنده","خاهر","ننت","ننه","ننتو","ننه تو","مادرت","مادرتو",
  "بابات","پدرت","خانوده","فامیلتو","لش","لاشی","کصخل","کصخلی","خنگ","خنگی",
  "نفهمی","بی عقل","بی مغز","کله خر","کله‌خر","شله","شل مغز","بیشعوری","احمقی",
  "idiot","stupid","fuck","shit","bitch","asshole","dumb","moron","noob","nub"
];

function isInsult(text){
  const t = " " + normalize(text) + " ";
  for(const w of INSULT_WORDS){
    const nw = normalize(w).trim();
    if(!nw) continue;
    if(nw.length <= 3){
      if(t.indexOf(" " + nw + " ") !== -1) return true;
    }else{
      if(t.indexOf(nw) !== -1) return true;
    }
  }
  return false;
}

const ROASTS = [
  "😐 ببین داداش، من ۲۴ ساعته بیدارم که کمکت کنم، تو داری فحش میدی؟\n\nمنطقی حرف بزن، جواب منطقی میگیری. الان چیت میخوای یا فقط اومدی سرگرم بشی؟ 🤡\n\n📢 کانال ما: <span class='hl'>" + CHANNEL + "</span>",
  "🙄 وای... با این ادبیات فاخرت حتماً مشتری طلایی مایی!\n\nبیا اینجا رو ببین، من پنل و چیت اورجینال میفروشم، تو داری ادب یاد میدی؟ 😂\n\n🍭 آروم باش، بگو چی میخوای. کانال: <span class='hl'>" + CHANNEL + "</span>",
  "😂 خب این‌جوری شد که...\n\nداداش تو اومدی پشتیبانی فحش بدی؟ من که کلاهم پس معرکه نیست، ولی حداقلش اینه که ۲۴ ساعته اینجام جواب بدم.\n\nیالا از اول شروع کن، محترمانه بپرس چی میخوای. 📌 <span class='hl'>" + CHANNEL + "</span>",
  "🫠 ببین رفیق، من اگه بخوام با هر فحشی از کوره در برم، الان اینجا نبودم.\n\nولی خب... تو یه ذره ادب یاد بگیری، منم یه ذره تخفیف میدم بهت. دیل؟ 😏\n\nکانال رسمی: <span class='hl'>" + CHANNEL + "</span>",
  "🙃 چه انرژی مثبتی! 🔋\n\nآخه عزیز دل، من رباتم، فحشت بهم نمیچسبه ولی به خودت میچسبه که چرا این‌جوری حرف میزنی.\n\nخب بگو چی میخوای از زایرون. ⚡ <span class='hl'>" + CHANNEL + "</span>",
  "😑 اوه اوه، چه کلماتی!\n\nمن پنل اورجینال میفروشم، تو داری زبان‌بازی می‌کنی. اینجا کلوپ مشت زنی نیست عزیزم. 💅\n\nبیا سر اصل مطلب: چیت میخوای؟ پنل میخوای؟ کانال: <span class='hl'>" + CHANNEL + "</span>",
  "🤨 با این لحنت فقط یه چیز کم داری: بلاک شدن.\n\nولی خب من مهربون‌تر از اونم که بخوام بلاکت کنم. بگو چی میخوای، محترمانه.\n\n📢 <span class='hl'>" + CHANNEL + "</span>",
  "💀 ببین با این حرفا فقط یه چیز ثابت شد: تو کلاس ادب رو با غیبت جا زدی.\n\nمن اینجام که کمکت کنم، نه اینکه با تو کشتی بگیرم. بگو چی میخوای تا راهنماییت کنم.\n\n⚡ <span class='hl'>" + CHANNEL + "</span>"
];

/* =========================================================
   ۲) پایگاه دانش زایرون — چیت و پنل
========================================================= */
const KB = [

  /* --- احوال‌پرسی و شروع --- */
  { k:["سلام","درود","هی","خوبی","خسته نباشی","صبح بخیر","شب بخیر","روز بخیر","سلم","سلان"],
    a:"سلام و درود! ⚡\nمن <b>زایرون</b> هستم، پشتیبانی ۲۴ ساعته زایرون پنل.\n\nهر ساعتی از شبانه‌روز اینجام تا درباره <b>چیت</b> و <b>پنل</b> کمکت کنم.\n\n📌 خرید پنل و چیت فقط از کانال رسمی ما:\n<span class='hl'>" + CHANNEL + "</span>\n(هم روبیکا، هم تلگرام)\n\nچیکار برات انجام بدم؟ 🌟" },

  { k:["خوبی","حالت چطوره","چطوری","خوبی تو"],
    a:"ممنون از احوال‌پرسیت! 😊\nمن که همیشه سرحالم — ۲۴ ساعته آماده‌ی خدمتم.\nتو چطوری؟ یه چیت خوب یا پنل قوی میخوای؟ ⚡\n\n📢 کانال رسمی: <span class='hl'>" + CHANNEL + "</span>" },

  { k:["خداحافظ","بای","خدانگهدار","فعلا","میخوام برم","خدافظ"],
    a:"خدانگهدار رفیق! 👋\nهر وقت چیت یا پنل خواستی، یا سوالی داشتی، همین‌جا هستم — ۲۴ ساعته.\n\n📢 یادت نره کانال رسمی زایرون:\n<span class='hl'>" + CHANNEL + "</span>\n(روبیکا + تلگرام)\n\nموفق باشی! ⚡" },

  { k:["ممنون","مرسی","تشکر","سپاس","دستت درد نکنه","لطف کردی","عالی بود","دمت گرم"],
    a:"خواهش میکنم رفیق! 🙌\nوظیفه‌ست که کمک کنم.\n\nهر وقت چیت یا پنل خواستی، یا سوالی داشتی، ۲۴ ساعته در خدمتم.\n📢 کانال رسمی: <span class='hl'>" + CHANNEL + "</span>" },

  /* --- پنل چیه --- */
  { k:["پنل چیه","پنل چیست","پنل یعنی چی","پنل چکار میکنه","پنل چیکار میکنه","پنل به چه کار","پنل چیه اصلا","panel"],
    a:"📟 <b>پنل چیه؟</b>\n\nپنل یه نرم‌افزار/اشتراک اختصاصی زایرونه که بهت امکانات ویژه در بازی‌ها میده. مثلاً:\n\n• ⚡ سرعت و پینگ بهتر\n• 🎯 دقت و هدف‌گیری خودکار\n• 👁 دید از پشت دیوار (ESP)\n• 🛡 آنتی‌بن قوی و به‌روزرسانی مداوم\n• 🎨 تنظیمات شخصی‌سازی‌شده\n\n📌 خرید پنل فقط از کانال رسمی:\n<span class='hl'>" + CHANNEL + "</span>\n(روبیکا + تلگرام)" },

  { k:["چیت چیه","چیت چیست","cheat چیه","هک چیه","hack چیه","چیت چیکار"],
    a:"🎮 <b>چیت چیه؟</b>\n\nچیت (Cheat) یا همون هک بازی، یه سری امکانات اضافه‌ست که به بازیکن کمک میکنه بهتر بازی کنه:\n\n• 🎯 Aim — هدف‌گیری خودکار\n• 👁 ESP — دیدن دشمن از پشت دیوار\n• 🔫 No Recoil — بدون لگد اسلحه\n• 🏃 Speed — سرعت حرکت بیشتر\n• 🛡 Anti-Ban — محافظت از اکانت\n\n📌 چیت‌های اورجینال زایرون فقط از کانال رسمی:\n<span class='hl'>" + CHANNEL + "</span>\n(روبیکا + تلگرام)" },

  { k:["پنل و چیت","چیت و پنل","فرق پنل و چیت","فرق چیت و پنل","چیت بهتره یا پنل"],
    a:"🎯 <b>فرق چیت و پنل</b>\n\nدر کل هر دو یه کار رو انجام میدن، ولی:\n\n• <b>چیت</b> — معمولاً مستقیم برای یه بازی خاص ساخته میشه\n• <b>پنل</b> — مجموعه‌ای از امکانات که می‌تونی خودت فعال/غیرفعال کنی\n\n📌 هر دو اورجینال و تضمینی از <b>زایرون</b> موجوده.\nکانال رسمی: <span class='hl'>" + CHANNEL + "</span>\n(روبیکا + تلگرام)" },

  /* --- کجا بخرم ← مهم‌ترین بخش --- */
  { k:["از کجا بخرم","کجا بخرم","کجا بخریم","از کجا بگیرم","چطوری بخرم","چطور بخرم","چطوری تهیه کنم","از کجا تهیه کنم","از کجا خرید کنم","فروش","خرید پنل","خرید چیت","بخرم","بخرم پنل","بخرم چیت","میخوام بخرم","میخام بخرم","سفارش پنل","سفارش چیت"],
    a:"🛒 <b>خرید پنل و چیت زایرون</b>\n\nفقط و فقط از کانال رسمی ما:\n\n📢 <span class='hl'>" + CHANNEL + "</span>\n\nهم توی <b>روبیکا</b> هستیم، هم <b>تلگرام</b> ✅\n\nداخل کانال:\n• 📋 لیست کامل پنل‌ها و چیت‌ها\n• 💰 قیمت‌ها\n• 🎁 تخفیف‌های ویژه\n• ⚡ پشتیبانی آنی\n\n⚠️ به هیچ‌کس خارج از کانال اعتماد نکن — فقط از زایرون بخر." },

  { k:["کانال","کانالتون","کانال شما","کانال رسمی","ادرس کانال","آدرس کانال","لینک کانال","ای دی کانال","آیدی کانال","channel"],
    a:"📢 <b>کانال رسمی زایرون</b>\n\n<span class='hl'>" + CHANNEL + "</span>\n\n✅ توی <b>روبیکا</b> موجوده\n✅ توی <b>تلگرام</b> هم موجوده\n\nهمه چیز از خرید پنل و چیت تا قیمت و پشتیبانی داخل کانال انجام میشه.\n\n⚠️ فقط به این آیدی اعتماد کن. به هیچ پیوی دیگه‌ای اعتماد نکن." },

  { k:["روبیکا","کانال روبیکا","ای دی روبیکا","آیدی روبیکا","rubika","روبی"],
    a:"📢 <b>کانال روبیکای زایرون</b>\n\n<span class='hl'>" + CHANNEL + "</span>\n\nتوی روبیکا سرچ کن:\n<b>" + CHANNEL + "</b>\n\nهمونجا لیست پنل‌ها، چیت‌ها، قیمت‌ها و پشتیبانی موجوده ✅" },

  { k:["تلگرام","کانال تلگرام","ای دی تلگرام","آیدی تلگرام","telegram","tg","تلگر"],
    a:"📢 <b>کانال تلگرامی زایرون</b>\n\n<span class='hl'>" + CHANNEL + "</span>\n\nتوی تلگرام سرچ کن:\n<b>" + CHANNEL + "</b>\n\nهمونجا لیست پنل‌ها، چیت‌ها، قیمت‌ها و پشتیبانی موجوده ✅" },

  { k:["ادرس","آدرس","لینک","ادرس کانال","لینک کانال","لینک خرید","link","لیست"],
    a:"🔗 <b>لینک و آدرس رسمی زایرون</b>\n\n📢 <span class='hl'>" + CHANNEL + "</span>\n\nهم روبیکا، هم تلگرام ✅\n\nهر چیزی که بخوای — چیت، پنل، قیمت، تخفیف — همه‌ش داخل کانال موجوده.\n⚠️ به هیچ آیدی دیگه‌ای اعتماد نکن." },

  /* --- قیمت --- */
  { k:["قیمت","قیمتش چنده","چند","چقدر","قیمت پنل","قیمت چیت","نرخ","هزینه پنل","هزینه چیت","چند هزار","چند تومان","قیمت ها"],
    a:"💰 <b>قیمت پنل و چیت زایرون</b>\n\nقیمت‌ها بسته به مدل و مدت اشتراک متفاوته:\n• چیت روزانه\n• چیت هفتگی\n• چیت ماهانه\n• پنل حرفه‌ای\n• پنل VIP\n\n📋 لیست کامل قیمت‌ها توی کانال رسمیه:\n<span class='hl'>" + CHANNEL + "</span>\n\n📌 هر مدل/بازی‌ای که میخوای، بگو تا قیمتشو دقیق بگم ✅" },

  { k:["تخفیف","کد تخفیف","ارزان تر","ارزانتر","ارزون تر","ارزونتر","حراج","جشنواره","کمتر بده","تخفیف دارید","کوپن"],
    a:"🎁 <b>تخفیف‌های زایرون</b>\n\nهمیشه توی کانال رسمی جشنواره و تخفیف ویژه داریم:\n\n📢 <span class='hl'>" + CHANNEL + "</span>\n\n• چیت چند ماهه ← تخفیف پلکانی\n• پنل VIP ← تخفیف ویژه\n• معرفی دوستان ← هدیه 🎉\n\n📌 برای اینکه از تخفیف‌های فعلی باخبر بشی، کانال رو دنبال کن." },

  /* --- تضمین و گارانتی --- */
  { k:["تضمین","گارانتی","ضمانت","تضمین میدید","کلاهبردار نیستید","اعتماد","مطمئن","مطمئنم","قابل اعتماد","شارلات","اسکم","scam","تست","دمو","نمونه"],
    a:"🛡 <b>تضمین و گارانتی زایرون</b>\n\n✅ <b>تضمین اصالت</b> — همه چیت و پنل‌ها اورجینال\n✅ <b>گارانتی فعال بودن</b> — تا آخر اشتراک فعاله\n✅ <b>پشتیبانی ۲۴ ساعته</b> — هر ساعتی مشکل داشتی، حل میکنیم\n✅ <b>آپدیت رایگان</b> — بعد از آپدیت بازی، رایگان آپدیت میشه\n\n📌 نمونه و دمو توی کانال موجوده:\n<span class='hl'>" + CHANNEL + "</span>" },

  { k:["بن","بن میشم","بن میشم اکانتم","خطر بن","ریسک","امنیت","امنه","امنه","انتی بن","anti ban","کشف"],
    a:"🛡 <b>امنیت و ریسک بن</b>\n\n• چیت و پنل‌های زایرون دارای <b>Anti-Ban</b> قوی هستن\n• به‌روزرسانی مداوم بعد از هر آپدیت بازی\n• تنظیمات امن و بی‌صدا\n\n⚠️ با این حال، همیشه یه درصد ریسک وجود داره (توی هر چیتی) ولی زایرون تلاشش اینه که این ریسک رو به کمترین حد برسونه.\n\n📌 پشتیبانی هم ۲۴ ساعته جواب میده: <span class='hl'>" + CHANNEL + "</span>" },

  /* --- پشتیبانی --- */
  { k:["پشتیبانی","پشتیبانی ۲۴ ساعته","24 ساعته","شبانه روزی","شبانه‌روزی","ساعت کاری","ساعت کار","کی هستید","بیداری","پاسخ"],
    a:"🕛 <b>پشتیبانی زایرون — ۲۴ ساعته</b>\n\n✅ ما <b>۲۴ ساعته و ۷ روز هفته</b> فعالیم.\n✅ چه شب، چه روز، چه جمعه، چه تعطیل — همیشه در دسترسیم.\n\n📢 همه چیز از داخل کانال رسمی پیگیری میشه:\n<span class='hl'>" + CHANNEL + "</span>\n(روبیکا + تلگرام)" },

  { k:["مشکل","کار نمی‌کنه","کار نمیکنه","ارور","خطا","error","باگ","کرش","کرش میکنه","باز نمیشه","اجرا نمیشه","گیر کرد"],
    a:"🛠 <b>مشکل فنی؟</b>\n\nلطفاً اینا رو چک کن:\n۱. ورژن بازی‌ت آپدیته؟\n۲. ورژن چیت/پنل رو از کانال دوباره دانلود کن\n۳. آنتی‌ویروس یا فایروال رو موقتاً خاموش کن\n۴. به‌عنوان ادمین اجرا کن (Run as Admin)\n\n📌 اگه مشکل باقی موند، توی کانال پیام بده، کمتر از چند دقیقه جواب میگیری:\n<span class='hl'>" + CHANNEL + "</span>" },

  { k:["اکانت","لاگین","ورود","رمز","پسورد","پسوورد","پنل باز نمیشه","کد فعال","فعال سازی","فعالسازی"],
    a:"🔐 <b>مشکل ورود / فعال‌سازی</b>\n\nلطفاً چک کن:\n• کد فعال‌سازی یا لایسنس رو درست وارد کنی\n• کپی/پیست اضافی نداشته باشه\n• ساعت سیستم رو درست تنظیم کن\n• مرورگر/برنامه رو با اجازه ادمین باز کن\n\n📌 اگه بازم نشد، توی کانال پیام بده تا سریع کمکت کنیم:\n<span class='hl'>" + CHANNEL + "</span>" },

  { k:["ارسال","چند روزه میاد","کی میرسه","تحویل","چه مدت","چقدر طول میکشه","طول میکشه"],
    a:"⚡ <b>زمان تحویل</b>\n\nزایرون <b>آنی</b> تحویل میده!\n\nمعمولاً بعد از خرید، کمتر از <b>۵ دقیقه</b> اطلاعات چیت/پنل برات ارسال میشه.\n\n📌 خرید فقط از کانال رسمی:\n<span class='hl'>" + CHANNEL + "</span>" },

  /* --- بازگشت و مرجوعی --- */
  { k:["مرجوعی","پس دادن","پولمو پس","برگشت پول","عودت","بازگشت وجه","پشیمون شدم","لغو سفارش","کنسل"],
    a:"↩️ <b>مرجوعی و بازگشت وجه</b>\n\n• چون محصول دیجیتاله، بعد از ارسال کد فعال‌سازی، قابل بازگشت نیست\n• اما اگه <b>مشکل فنی از سمت ما</b> باشه، رایگان عوض میشه یا پول برمیگرده\n• اگه چیت/پنل فعال نشد، توی کانال پیام بده\n\n📌 پیگیری: <span class='hl'>" + CHANNEL + "</span>" },

  /* --- سوالات عمومی --- */
  { k:["کی هستی","تو کی هستی","اسمت چیه","اسم شما","ربات","بات","چیکار میکنی","چی هستی","اسمت","نام تو","زایرون کیه"],
    a:"🤖 من <b>زایرون</b> هستم.\n\nپشتیبانی ۲۴ ساعته <b>Zayron Panel</b>.\n\nکاری که انجام میدم:\n• راهنمایی درباره چیت و پنل\n• اعلام قیمت و امکانات\n• حل مشکلات فنی\n• اتصال به کانال رسمی\n\n📢 کانال رسمی ما:\n<span class='hl'>" + CHANNEL + "</span>\n(روبیکا + تلگرام)" },

  { k:["کمک","راهنما","help","چیکار کنم","نمیدونم","سردرگم","گیج شدم","چی بپرسم","چیکار کنم الان"],
    a:"🆘 <b>در خدمتم!</b>\n\nبرای اینکه سریع راهنماییت کنم، بگو دنبال چی هستی:\n\n🎮 چیت برای چه بازی‌ای؟\n📟 پنل میخوای یا تک‌چیت؟\n💰 قیمت رو میخوای بدونی؟\n🛠 مشکل فنی داری؟\n📢 یا فقط کانال رو میخوای؟\n\nهر کدوم رو بگی، همون لحظه راهنماییت میکنم ⚡\n\n📢 کانال: <span class='hl'>" + CHANNEL + "</span>" },

  { k:["بازی","چی بازی","برای چه بازی","چه بازیایی","کدوم بازی","گیم","بازی ها","بازیها"],
    a:"🎮 <b>بازی‌های پشتیبانی‌شده</b>\n\nزایرون برای انواع بازی‌ها چیت و پنل داره:\n\n• 🎯 PUBG Mobile\n• 🔫 Call of Duty Mobile\n• 🏆 Free Fire\n• ⚔ Fortnite\n• 🎮 Valorant\n• و کلی بازی دیگه\n\n📌 لیست کامل و به‌روز توی کانال رسمی:\n<span class='hl'>" + CHANNEL + "</span>\n\nبگو برای کدوم بازی میخوای تا راهنماییت کنم ✅" },

  { k:["بله","اره","آره","درسته","تایید","باشه","حتما","اوکی","ok","حتماً"],
    a:"✅ عالیه!\nخب بگو دقیقاً چی میخوای — برای کدوم بازی؟ چیت یا پنل؟\n\nیا مستقیم برو کانال رسمی:\n<span class='hl'>" + CHANNEL + "</span>" },

  { k:["نه","خیر","نخیر","نمیخوام","لازم نیست","no"],
    a:"👌 اوکی رفیق، هر وقت خواستی در خدمتم.\n۲۴ ساعته اینجام ⚡\n\n📢 کانال رسمی:\n<span class='hl'>" + CHANNEL + "</span>" },

  { k:["چند ماه","چند روز","مدت","طول اشتراک","چقدر اعتبار داره","تا کی","مدتش"],
    a:"⏳ <b>مدت اعتبار پنل و چیت</b>\n\nما پلن‌های مختلف داریم:\n\n• 📅 روزانه\n• 📅 هفتگی\n• 📅 ماهانه\n• 📅 سه ماهه\n• 📅 شش ماهه\n• 📅 یک‌ساله\n\n📌 هر پلنی که بخوای موجوده.\nقیمت و موجودی توی کانال:\n<span class='hl'>" + CHANNEL + "</span>" },

  { k:["پرداخت","کارت به کارت","کریپتو","تتر","usdt","پی پال","پیپال","روش پرداخت","چطوری پرداخت"],
    a:"💳 <b>روش‌های پرداخت</b>\n\n✅ کارت به کارت (ریالی)\n✅ کریپتو (USDT / BTC)\n✅ کیف پول‌های داخلی\n✅ پرداخت از طریق کانال\n\n📌 برای اطلاعات دقیق پرداخت، توی کانال پیام بده:\n<span class='hl'>" + CHANNEL + "</span>" },

  { k:["اصلی","اورجینال","فیک نیست","واقعیه","جارو نکنه","دزدی نباشه","کپی نیست","original"],
    a:"✅ <b>اصالت محصولات زایرون</b>\n\nهمه چیت‌ها و پنل‌های ما:\n\n• 🔒 اورجینال و اختصاصی زایرون\n• 🛡 دارای Anti-Ban\n• 🔄 به‌روزرسانی مداوم\n• 💯 تست‌شده قبل از فروش\n\n⚠️ اگه کسی ادعا کرد نماینده ماست، حتماً از کانال رسمی چک کن:\n<span class='hl'>" + CHANNEL + "</span>" },

  { k:["نمایندگی","نماینده","همکاری","ریسلر","reseller","فروشندگی","توزیع"],
    a:"🤝 <b>همکاری و نمایندگی زایرون</b>\n\nاگه میخوای نماینده‌ی ما بشی، توی کانال پیام بده:\n\n📢 <span class='hl'>" + CHANNEL + "</span>\n\nشرایط همکاری:\n• خرید عمده ← قیمت ویژه\n• پنل اختصاصی برای فروش\n• پشتیبانی کامل\n\n📌 جزئیات رو از خود تیم بپرس." },

  { k:["کمک فوری","فوری","سریع","اورژانس","همین الان","الان"],
    a:"⚡ <b>پشتیبانی فوری زایرون</b>\n\nسریع‌ترین راه: کانال رسمی 👇\n\n<span class='hl'>" + CHANNEL + "</span>\n\n✅ توی روبیکا\n✅ توی تلگرام\n\nکمتر از چند دقیقه جواب میگیری." },

  { k:["بروزرسانی","آپدیت","update","نسخه جدید","جدید"],
    a:"🔄 <b>آپدیت‌های زایرون</b>\n\nبعد از هر آپدیت بازی، ما سریع چیت و پنل رو آپدیت میکنیم و توی کانال اعلام میشه.\n\n📢 کانال رسمی:\n<span class='hl'>" + CHANNEL + "</span>\n\n✅ آپدیت‌ها برای مشتری‌های ما <b>رایگان</b>ه." },

  { k:["تست کنم","تست رایگان","دمو","نمونه","free trial","امتحان کنم"],
    a:"🎯 <b>تست و دمو</b>\n\nبله، ما دمو و نمونه داریم ✅\n\nتوی کانال رسمی ویدیو و نمونه‌های چیت و پنل موجوده:\n\n<span class='hl'>" + CHANNEL + "</span>\n\n📌 ببین، تست کن، بعد با خیال راحت خرید کن." }

];

/* =========================================================
   ۳) تنظیمات و ذخیره‌سازی
========================================================= */
const DEFAULTS = {
  url: "https://api.openai.com/v1/chat/completions",
  key: "",
  model: "gpt-4o-mini",
  system: "تو «زایرون» هستی، پشتیبان ۲۴ ساعته فروشگاه Zayron Panel که چیت و پنل بازی میفروشد. کانال رسمی شما @panel_chit_zayron است (روبیکا و تلگرام). همیشه فارسی، صمیمی، کوتاه و با انرژی پاسخ بده. اگر کاربر فحش داد، محکم و بامزه جوابش را بده. خرید را همیشه به کانال رسمی ارجاع بده."
};
const STORE_CFG  = "zayron_cfg_v1";
const STORE_CHAT = "zayron_chat_v1";

let config  = loadConfig();
let history = loadChat();
let busy    = false;

function loadConfig(){
  try { return Object.assign({}, DEFAULTS, JSON.parse(localStorage.getItem(STORE_CFG) || "{}")); }
  catch(e){ return Object.assign({}, DEFAULTS); }
}
function saveConfig(c){ try{ localStorage.setItem(STORE_CFG, JSON.stringify(c)); }catch(e){} }

function loadChat(){
  try { return JSON.parse(localStorage.getItem(STORE_CHAT) || "[]"); }
  catch(e){ return []; }
}
function saveChat(){
  try { localStorage.setItem(STORE_CHAT, JSON.stringify(history.slice(-40))); }catch(e){}
}

/* =========================================================
   ۴) عناصر
========================================================= */
const chatEl     = document.getElementById("chat");
const inputEl    = document.getElementById("input");
const sendBtn    = document.getElementById("sendBtn");
const overlay    = document.getElementById("overlay");
const quickEl    = document.getElementById("quick");
const statusText = document.getElementById("statusText");

/* =========================================================
   ۵) ابزار متنی
========================================================= */
function escapeHtml(s){
  return String(s).replace(/[&<>"']/g, function(m){
    return {"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[m];
  });
}

/* رندر: قبل از escape شدن، تگ‌های span.hl رو نجات میدیم */
function render(text){
  const parts = [];
  let s = String(text);
  // تگ span.hl رو نگه دار
  s = s.replace(/<span class='hl'>(.*?)<\/span>/g, function(_, inner){
    const idx = parts.length;
    parts.push(inner);
    return "%%HL" + idx + "%%";
  });

  let h = escapeHtml(s);
  h = h.replace(/`([^`]+)`/g, "<code>$1</code>");
  h = h.replace(/\*\*([^*]+)\*\*/g, "<b>$1</b>");
  h = h.replace(/\n/g, "<br>");
  h = h.replace(/%%HL(\d+)%%/g, function(_, i){
    return "<span class='hl'>" + escapeHtml(parts[i]) + "</span>";
  });
  return h;
}

function normalize(s){
  return String(s || "")
    .replace(/[\u064A\u0649]/g, "ی")
    .replace(/\u0643/g, "ک")
    .replace(/[\u064B-\u0652\u0670\u0640]/g, "")
    .replace(/\u200c/g, " ")
    .replace(/[أإآا]/g, "ا")
    .replace(/[ؤئ]/g, "ی")
    .replace(/ة/g, "ه")
    .replace(/[؟?!.,،؛:()\[\]{}<>«»"'_/\\\-+*=%$#@^~|]/g, " ")
    .replace(/\s+/g, " ")
    .trim()
    .toLowerCase();
}

/* =========================================================
   ۶) موتور تطبیق
========================================================= */
function findBest(text){
  const t = normalize(text);
  if(!t) return null;

  const words = t.split(" ").filter(w => w.length > 1);
  let best = null, bestScore = 0;

  for(const entry of KB){
    let score = 0;
    for(const kw of entry.k){
      const k = normalize(kw);
      if(!k) continue;
      if(t.indexOf(k) !== -1){
        score += k.length * 3 + 4;
        if(words.indexOf(k) !== -1) score += 6;
      }
    }
    if(score > bestScore){
      bestScore = score;
      best = entry;
    }
  }
  return bestScore >= 8 ? best : null;
}

function smartFallback(text){
  const t = normalize(text);
  const words = t.split(" ").filter(w => w.length > 2);
  const topic = words.length ? words[words.length - 1] : "";

  const templates = [
    "🤔 متوجه شدم درباره «" + (topic || "این موضوع") + "» سوال داری.\n\nولی برای اینکه دقیق کمکت کنم، یه کم بیشتر توضیح بده:\n• چه بازی‌ای؟\n• چیت میخوای یا پنل؟\n• یا مشکل فنی داری؟\n\n📢 همه چیز از کانال رسمی زایرون:\n<span class='hl'>" + CHANNEL + "</span>\n(روبیکا + تلگرام)",

    "⚡ سؤالت رو گرفتم رفیق.\n\nولی برای جواب دقیق‌تر، اینا رو مشخص کن:\n🎮 بازی مورد نظر\n📟 چیت یا پنل\n💰 قیمت یا ویژگی\n🛠 یا مشکل فنی\n\n📌 یا مستقیم برو کانال رسمی:\n<span class='hl'>" + CHANNEL + "</span>",

    "🙌 اوکی، ولی بذار دقیق‌تر بفهمم چی میخوای.\n\nموضوعات اصلی که میتونم کمکت کنم:\n• 🎮 چیت برای بازی‌ها\n• 📟 پنل اختصاصی\n• 💰 قیمت و پلن‌ها\n• 🛡 گارانتی و امنیت\n• 🛠 مشکلات فنی\n\nهر کدوم رو بگو، همون لحظه راهنماییت میکنم.\n📢 <span class='hl'>" + CHANNEL + "</span>"
  ];

  return templates[Math.floor(Math.random() * templates.length)];
}

function localReply(text){
  // اول چک فحش
  if(isInsult(text)){
    return ROASTS[Math.floor(Math.random() * ROASTS.length)];
  }
  const found = findBest(text);
  if(found) return found.a;
  return smartFallback(text);
}

/* =========================================================
   ۷) نمایش پیام
========================================================= */
function addMessage(role, text){
  const div = document.createElement("div");
  div.className = "msg " + role;
  div.innerHTML = render(text);
  chatEl.appendChild(div);
  chatEl.scrollTop = chatEl.scrollHeight;
  return div;
}

function showTyping(){
  const div = document.createElement("div");
  div.className = "msg bot";
  div.innerHTML = '<div class="typing"><span></span><span></span><span></span></div>';
  chatEl.appendChild(div);
  chatEl.scrollTop = chatEl.scrollHeight;
  return div;
}

function sleep(ms){ return new Promise(r => setTimeout(r, ms)); }

/* =========================================================
   ۸) هوش مصنوعی واقعی (اختیاری)
========================================================= */
async function callAI(messages){
  const res = await fetch(config.url, {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
      "Authorization": "Bearer " + config.key
    },
    body: JSON.stringify({
      model: config.model,
      messages: [{ role:"system", content: config.system }].concat(messages),
      temperature: 0.8
    })
  });
  if(!res.ok){
    const errTxt = await res.text();
    throw new Error("HTTP " + res.status + " — " + errTxt.slice(0, 180));
  }
  const data = await res.json();
  return (data.choices && data.choices[0] && data.choices[0].message && data.choices[0].message.content)
    ? data.choices[0].message.content
    : "پاسخی از سرور دریافت نشد.";
}

/* =========================================================
   ۹) ارسال پیام
========================================================= */
async function sendMessage(){
  const text = (inputEl.value || "").trim();
  if(!text){ inputEl.focus(); return; }
  if(busy) return;

  busy = true;
  sendBtn.disabled = true;

  inputEl.value = "";
  inputEl.style.height = "auto";

  addMessage("user", text);
  history.push({ role:"user", content: text });
  saveChat();

  const typingEl = showTyping();
  const insulted = isInsult(text);

  try{
    let reply;

    if(config.key && config.url){
      try{
        reply = await callAI(history);
      }catch(err){
        await sleep(300);
        reply = localReply(text) +
          "\n\n⚠️ (اتصال به API ممکن نشد: " + err.message + ")\nپاسخ بالا از پایگاه دانش زایرون است.";
      }
    }else{
      await sleep(insulted ? 250 : 450 + Math.random() * 400);
      reply = localReply(text);
    }

    if(typingEl && typingEl.parentNode) typingEl.parentNode.removeChild(typingEl);

    // اگه فحش بود، کلاس roast
    if(insulted){
      const div = document.createElement("div");
      div.className = "msg roast";
      div.innerHTML = render(reply);
      chatEl.appendChild(div);
      chatEl.scrollTop = chatEl.scrollHeight;
    }else{
      addMessage("bot", reply);
    }

    history.push({ role:"assistant", content: reply });
    saveChat();

  }catch(err){
    if(typingEl && typingEl.parentNode) typingEl.parentNode.removeChild(typingEl);
    addMessage("error", "خطای غیرمنتظره: " + err.message);
  }finally{
    busy = false;
    sendBtn.disabled = false;
    inputEl.focus();
    chatEl.scrollTop = chatEl.scrollHeight;
  }
}

/* =========================================================
   ۱۰) رویدادها
========================================================= */
sendBtn.addEventListener("click", function(e){ e.preventDefault(); sendMessage(); });

inputEl.addEventListener("keydown", function(e){
  if(e.key === "Enter" && !e.shiftKey){
    e.preventDefault();
    sendMessage();
  }
});

inputEl.addEventListener("input", function(){
  inputEl.style.height = "auto";
  inputEl.style.height = Math.min(inputEl.scrollHeight, 130) + "px";
});

quickEl.addEventListener("click", function(e){
  const btn = e.target.closest(".chip");
  if(!btn) return;
  inputEl.value = btn.textContent.trim();
  sendMessage();
});

document.getElementById("clearBtn").addEventListener("click", function(){
  if(!confirm("گفتگوی جدید شروع شود؟")) return;
  history = [];
  saveChat();
  chatEl.innerHTML = "";
  greet();
});

/* =========================================================
   ۱۱) تنظیمات
========================================================= */
const cfgUrl    = document.getElementById("cfgUrl");
const cfgKey    = document.getElementById("cfgKey");
const cfgModel  = document.getElementById("cfgModel");
const cfgSystem = document.getElementById("cfgSystem");

document.getElementById("settingsBtn").addEventListener("click", function(){
  cfgUrl.value    = config.url;
  cfgKey.value    = config.key;
  cfgModel.value  = config.model;
  cfgSystem.value = config.system;
  overlay.classList.add("show");
  cfgUrl.focus();
});

document.getElementById("cancelBtn").addEventListener("click", function(){
  overlay.classList.remove("show");
});

overlay.addEventListener("click", function(e){
  if(e.target === overlay) overlay.classList.remove("show");
});

document.getElementById("saveBtn").addEventListener("click", function(){
  config.url    = cfgUrl.value.trim() || DEFAULTS.url;
  config.key    = cfgKey.value.trim();
  config.model  = cfgModel.value.trim() || DEFAULTS.model;
  config.system = cfgSystem.value.trim() || DEFAULTS.system;
  saveConfig(config);
  updateStatus();
  overlay.classList.remove("show");

  const mode = config.key ? "به هوش مصنوعی واقعی متصل شد ✅" : "به حالت محلی برگشت ✅";
  addMessage("bot", mode + "\nهر سوالی درباره چیت و پنل داری بپرس ⚡");
});

/* =========================================================
   ۱۲) وضعیت
========================================================= */
function updateStatus(){
  if(config.key){
    statusText.textContent = "متصل به هوش مصنوعی — Zayron Online";
  }else{
    statusText.textContent = "پشتیبانی ۲۴ ساعته زایرون پنل — آنلاین";
  }
}

/* =========================================================
   ۱۳) خوش‌آمد
========================================================= */
function greet(){
  addMessage("bot",
    "سلام رفیق! ⚡\n\n" +
    "من <b>زایرون</b> هستم — پشتیبان <b>۲۴ ساعته</b> Zayron Panel.\n\n" +
    "درباره <b>چیت</b> و <b>پنل</b> هر سوالی داشتی، همین‌جا بپرس:\n" +
    "• قیمت‌ها و پلن‌ها\n" +
    "• امکانات و ویژگی‌ها\n" +
    "• گارانتی و امنیت\n" +
    "• مشکلات فنی\n\n" +
    "🛒 <b>خرید فقط از کانال رسمی:</b>\n" +
    "<span class='hl'>" + CHANNEL + "</span>\n" +
    "(روبیکا + تلگرام) ✅\n\n" +
    "چیکار برات کنم؟ 🎮"
  );
}

/* =========================================================
   ۱۴) شروع
========================================================= */
(function init(){
  updateStatus();

  if(history.length > 0){
    history.forEach(function(m){
      addMessage(m.role === "user" ? "user" : "bot", m.content);
    });
  }else{
    greet();
  }

  inputEl.focus();
  console.log("✅ Zayron Support ready | KB entries:", KB.length, "| Insult words:", INSULT_WORDS.length);
})();
</script>
</body>
</html>
