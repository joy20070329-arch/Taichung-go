<!DOCTYPE html>

<html lang="zh-Hant">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>台中東海商圈美食導覽</title>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+TC:wght@400;600;700;900&family=Noto+Sans+TC:wght@300;400;500&family=Playfair+Display:ital,wght@0,700;1,400&display=swap" rel="stylesheet">
  <style>
    :root {
      --ink: #1a0a00;
      --cream: #fdf6ec;
      --warm: #f5e6cc;
      --amber: #c8861a;
      --rust: #a84b1f;
      --sage: #6b7c5a;
      --pale-sage: #e8ede2;
      --border: rgba(200,134,26,0.25);
    }

```
* { margin: 0; padding: 0; box-sizing: border-box; }

html { scroll-behavior: auto; }

body {
  background: var(--cream);
  color: var(--ink);
  font-family: 'Noto Sans TC', sans-serif;
  font-weight: 300;
  line-height: 1.8;
  overflow-x: hidden;
}

/* ── HEADER ── */
header {
  position: relative;
  background: var(--ink);
  color: var(--cream);
  padding: 0;
  overflow: hidden;
}

.header-pattern {
  position: absolute;
  inset: 0;
  background-image:
    repeating-linear-gradient(45deg, transparent, transparent 20px, rgba(200,134,26,0.06) 20px, rgba(200,134,26,0.06) 21px),
    repeating-linear-gradient(-45deg, transparent, transparent 20px, rgba(200,134,26,0.06) 20px, rgba(200,134,26,0.06) 21px);
}

.header-inner {
  position: relative;
  z-index: 1;
  display: grid;
  grid-template-columns: 1fr auto 1fr;
  align-items: center;
  padding: 28px 48px;
  border-bottom: 1px solid rgba(200,134,26,0.3);
}

.site-badge {
  font-family: 'Noto Serif TC', serif;
  font-size: 11px;
  letter-spacing: 0.25em;
  color: var(--amber);
  text-transform: uppercase;
}

.site-title {
  text-align: center;
}

.site-title h1 {
  font-family: 'Noto Serif TC', serif;
  font-size: clamp(22px, 3vw, 36px);
  font-weight: 900;
  letter-spacing: 0.12em;
  line-height: 1.2;
  background: linear-gradient(135deg, #f5d78e, #c8861a, #e8b96a);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.site-title .sub {
  font-size: 11px;
  letter-spacing: 0.3em;
  color: rgba(245,230,204,0.5);
  font-family: 'Playfair Display', serif;
  font-style: italic;
  margin-top: 4px;
}

.header-contact {
  text-align: right;
  font-size: 11px;
  color: rgba(245,230,204,0.5);
  letter-spacing: 0.05em;
}

.header-contact a {
  color: var(--amber);
  text-decoration: none;
  transition: opacity 0.2s;
}
.header-contact a:hover { opacity: 0.7; }

/* ── NAV ── */
nav {
  background: var(--ink);
  border-bottom: 2px solid var(--amber);
  position: sticky;
  top: 0;
  z-index: 100;
}

nav ul {
  display: flex;
  justify-content: center;
  list-style: none;
  gap: 0;
}

nav ul li a {
  display: block;
  padding: 16px 32px;
  color: var(--cream);
  text-decoration: none;
  font-size: 13px;
  letter-spacing: 0.18em;
  font-family: 'Noto Serif TC', serif;
  font-weight: 600;
  position: relative;
  transition: color 0.3s;
}

nav ul li a::after {
  content: '';
  position: absolute;
  bottom: 0; left: 50%; right: 50%;
  height: 2px;
  background: var(--amber);
  transition: left 0.3s, right 0.3s;
}

nav ul li a:hover {
  color: var(--amber);
}

nav ul li a:hover::after {
  left: 12px;
  right: 12px;
}

/* ── HERO (首頁) ── */
#home {
  position: relative;
  min-height: 88vh;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  background: var(--ink);
}

.hero-bg {
  position: absolute;
  inset: 0;
  background:
    radial-gradient(ellipse 60% 50% at 30% 50%, rgba(200,134,26,0.15) 0%, transparent 70%),
    radial-gradient(ellipse 40% 60% at 80% 30%, rgba(168,75,31,0.12) 0%, transparent 60%),
    var(--ink);
}

.hero-grid {
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(200,134,26,0.07) 1px, transparent 1px),
    linear-gradient(90deg, rgba(200,134,26,0.07) 1px, transparent 1px);
  background-size: 60px 60px;
}

.hero-content {
  position: relative;
  z-index: 1;
  text-align: center;
  padding: 60px 40px;
  max-width: 760px;
}

.hero-eyebrow {
  font-size: 11px;
  letter-spacing: 0.4em;
  color: var(--amber);
  margin-bottom: 28px;
  opacity: 0;
  animation: fadeUp 0.8s ease 0.2s forwards;
}

.hero-headline {
  font-family: 'Noto Serif TC', serif;
  font-size: clamp(36px, 6vw, 72px);
  font-weight: 900;
  color: var(--cream);
  line-height: 1.15;
  letter-spacing: 0.05em;
  opacity: 0;
  animation: fadeUp 0.8s ease 0.4s forwards;
}

.hero-headline span {
  color: var(--amber);
}

.hero-divider {
  width: 60px;
  height: 1px;
  background: var(--amber);
  margin: 32px auto;
  opacity: 0;
  animation: fadeUp 0.8s ease 0.6s forwards;
}

.hero-desc {
  font-size: 15px;
  color: rgba(245,230,204,0.65);
  line-height: 2;
  letter-spacing: 0.06em;
  opacity: 0;
  animation: fadeUp 0.8s ease 0.8s forwards;
}

.hero-cta {
  margin-top: 44px;
  display: flex;
  gap: 16px;
  justify-content: center;
  flex-wrap: wrap;
  opacity: 0;
  animation: fadeUp 0.8s ease 1s forwards;
}

.btn-primary {
  padding: 14px 36px;
  background: var(--amber);
  color: var(--ink);
  font-family: 'Noto Serif TC', serif;
  font-weight: 700;
  font-size: 13px;
  letter-spacing: 0.2em;
  text-decoration: none;
  border: none;
  cursor: pointer;
  transition: background 0.3s, transform 0.2s;
}

.btn-primary:hover {
  background: #e09d2a;
  transform: translateY(-2px);
}

.btn-outline {
  padding: 14px 36px;
  background: transparent;
  color: var(--cream);
  font-family: 'Noto Serif TC', serif;
  font-weight: 600;
  font-size: 13px;
  letter-spacing: 0.2em;
  text-decoration: none;
  border: 1px solid rgba(245,230,204,0.3);
  transition: border-color 0.3s, color 0.3s, transform 0.2s;
}

.btn-outline:hover {
  border-color: var(--amber);
  color: var(--amber);
  transform: translateY(-2px);
}

/* ── 最新消息 ── */
.news-bar {
  background: var(--amber);
  padding: 14px 48px;
  display: flex;
  align-items: center;
  gap: 20px;
  overflow: hidden;
}

.news-label {
  font-family: 'Noto Serif TC', serif;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 0.2em;
  color: var(--ink);
  white-space: nowrap;
  background: var(--ink);
  color: var(--amber);
  padding: 4px 12px;
}

.news-items {
  display: flex;
  gap: 48px;
  animation: ticker 20s linear infinite;
  white-space: nowrap;
}

.news-item {
  font-size: 13px;
  color: var(--ink);
  letter-spacing: 0.05em;
}

.news-item .date {
  font-weight: 700;
  margin-right: 10px;
}

@keyframes ticker {
  0% { transform: translateX(0); }
  100% { transform: translateX(-50%); }
}

/* ── SECTION COMMON ── */
section {
  padding: 96px 48px;
}

.section-header {
  text-align: center;
  margin-bottom: 64px;
}

.section-kicker {
  font-size: 10px;
  letter-spacing: 0.4em;
  color: var(--amber);
  margin-bottom: 16px;
  display: block;
}

.section-title {
  font-family: 'Noto Serif TC', serif;
  font-size: clamp(26px, 3.5vw, 40px);
  font-weight: 900;
  color: var(--ink);
  letter-spacing: 0.08em;
}

.section-rule {
  width: 48px;
  height: 2px;
  background: var(--amber);
  margin: 20px auto 0;
}

/* ── 必吃美食 ── */
#food {
  background: var(--cream);
}

.food-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2px;
  max-width: 1100px;
  margin: 0 auto;
}

.food-card {
  background: var(--warm);
  padding: 40px 32px;
  border-top: 3px solid transparent;
  transition: border-color 0.3s, background 0.3s, transform 0.3s;
  cursor: default;
}

.food-card:hover {
  border-color: var(--amber);
  background: #fcefd8;
  transform: translateY(-4px);
}

.food-icon {
  font-size: 40px;
  margin-bottom: 20px;
  display: block;
}

.food-name {
  font-family: 'Noto Serif TC', serif;
  font-size: 18px;
  font-weight: 700;
  color: var(--ink);
  letter-spacing: 0.08em;
  margin-bottom: 10px;
}

.food-desc {
  font-size: 13px;
  color: #5a4030;
  line-height: 1.9;
}

.food-tag {
  display: inline-block;
  margin-top: 16px;
  padding: 3px 12px;
  background: var(--amber);
  color: var(--cream);
  font-size: 10px;
  letter-spacing: 0.15em;
}

/* ── 交通資訊 ── */
#transport {
  background: var(--ink);
  color: var(--cream);
}

#transport .section-title {
  color: var(--cream);
}

.transport-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 24px;
  max-width: 1000px;
  margin: 0 auto;
}

.transport-card {
  border: 1px solid rgba(200,134,26,0.25);
  padding: 36px 28px;
  transition: border-color 0.3s, background 0.3s;
}

.transport-card:hover {
  border-color: var(--amber);
  background: rgba(200,134,26,0.07);
}

.transport-icon {
  font-size: 32px;
  margin-bottom: 16px;
  display: block;
}

.transport-method {
  font-family: 'Noto Serif TC', serif;
  font-size: 16px;
  font-weight: 700;
  color: var(--amber);
  letter-spacing: 0.1em;
  margin-bottom: 12px;
}

.transport-detail {
  font-size: 13px;
  color: rgba(245,230,204,0.65);
  line-height: 1.9;
}

/* ── 聯絡我們 ── */
#contact {
  background: var(--pale-sage);
}

.contact-wrap {
  max-width: 640px;
  margin: 0 auto;
}

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 32px;
  margin-bottom: 48px;
}

.contact-item {
  padding: 28px 24px;
  background: white;
  border-left: 3px solid var(--sage);
}

.contact-label {
  font-size: 10px;
  letter-spacing: 0.25em;
  color: var(--sage);
  margin-bottom: 10px;
}

.contact-value {
  font-family: 'Noto Serif TC', serif;
  font-size: 15px;
  font-weight: 600;
  color: var(--ink);
}

.contact-value a {
  color: var(--rust);
  text-decoration: none;
}

.contact-value a:hover {
  text-decoration: underline;
}

.contact-form-note {
  text-align: center;
  font-size: 13px;
  color: #5a6650;
  padding: 28px;
  border: 1px dashed rgba(107,124,90,0.4);
  letter-spacing: 0.05em;
}

/* ── FOOTER ── */
footer {
  background: #0e0500;
  color: rgba(245,230,204,0.45);
  padding: 40px 48px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 16px;
  border-top: 1px solid rgba(200,134,26,0.2);
}

.footer-brand {
  font-family: 'Noto Serif TC', serif;
  font-size: 14px;
  font-weight: 700;
  color: var(--amber);
  letter-spacing: 0.1em;
}

.footer-copy {
  font-size: 12px;
  letter-spacing: 0.08em;
}

.footer-email {
  font-size: 12px;
  letter-spacing: 0.08em;
}

.footer-email a {
  color: var(--amber);
  text-decoration: none;
}

/* ── ANIMATIONS ── */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(24px); }
  to   { opacity: 1; transform: translateY(0); }
}

.reveal {
  opacity: 0;
  transform: translateY(30px);
  transition: opacity 0.7s ease, transform 0.7s ease;
}

.reveal.visible {
  opacity: 1;
  transform: none;
}

/* ── RESPONSIVE ── */
@media (max-width: 768px) {
  .header-inner { grid-template-columns: 1fr; text-align: center; gap: 12px; }
  .header-contact { text-align: center; }
  nav ul { flex-wrap: wrap; }
  nav ul li a { padding: 12px 18px; font-size: 12px; }
  section { padding: 64px 24px; }
  .news-bar { padding: 12px 24px; }
  footer { flex-direction: column; text-align: center; }
  .contact-grid { grid-template-columns: 1fr; }
}
```

  </style>
</head>
<body>

<!-- ════ HEADER ════ -->

<header>
  <div class="header-pattern"></div>
  <div class="header-inner">
    <div class="site-badge">Taichung · Donghai District</div>
    <div class="site-title">
      <h1>台中東海商圈美食導覽</h1>
      <p class="sub">A Culinary Journey Through Donghai</p>
    </div>
    <div class="header-contact">
      <span style="color:var(--amber)"><a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="b9ddd6d7ded1d8d097dfd6d6ddf9dcc1d8d4c9d5dc97dad6d4">[email&#160;protected]</a></span>
    </div>
  </div>
</header>

<!-- ════ NAV ════ -->

<nav>
  <ul>
    <li><a href="javascript:void(0)" onclick="scrollToSection('home')">頁首</a></li>
    <li><a href="javascript:void(0)" onclick="scrollToSection('food')">必吃美食</a></li>
    <li><a href="javascript:void(0)" onclick="scrollToSection('transport')">交通資訊</a></li>
    <li><a href="javascript:void(0)" onclick="scrollToSection('contact')">聯絡我們</a></li>
  </ul>
</nav>

<!-- ════ HERO ════ -->

<section id="home" style="padding:0;">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>
  <div class="hero-content">
    <p class="hero-eyebrow">TAICHUNG · DONGHAI COMMERCIAL DISTRICT</p>
    <h2 class="hero-headline">探索<span>東海</span>商圈<br>美食新天地</h2>
    <div class="hero-divider"></div>
    <p class="hero-desc">
      台中東海商圈匯聚各式在地美味，<br>
      從特色小吃到精緻餐廳，帶您一次品嚐道地台灣風味。
    </p>
    <div class="hero-cta">
      <a href="javascript:void(0)" onclick="scrollToSection('food')" class="btn-primary">探索美食</a>
      <a href="javascript:void(0)" onclick="scrollToSection('transport')" class="btn-outline">交通指南</a>
    </div>
  </div>
</section>

<!-- ════ NEWS TICKER ════ -->

<div class="news-bar">
  <span class="news-label">最新消息</span>
  <div style="overflow:hidden; flex:1;">
    <div class="news-items">
      <span class="news-item"><span class="date">2026.04</span>東海夜市春季限定美食祭正式開幕，精選 20 攤特色小吃！</span>
      <span class="news-item"><span class="date">2026.03</span>東海商圈停車場擴建完工，假日停車更便利，新增 200 個車位。</span>
      <span class="news-item"><span class="date">2026.04</span>東海夜市春季限定美食祭正式開幕，精選 20 攤特色小吃！</span>
      <span class="news-item"><span class="date">2026.03</span>東海商圈停車場擴建完工，假日停車更便利，新增 200 個車位。</span>
    </div>
  </div>
</div>

<!-- ════ 必吃美食 ════ -->

<section id="food">
  <div class="section-header reveal">
    <span class="section-kicker">MUST-EAT DISHES</span>
    <h2 class="section-title">東海必吃美食</h2>
    <div class="section-rule"></div>
  </div>

  <div class="food-grid">
    <div class="food-card reveal">
      <span class="food-icon">🍗</span>
      <div class="food-name">東海雞排</div>
      <p class="food-desc">東海商圈最具代表性的在地美食，外皮酥脆、肉質鮮嫩多汁，每日現點現炸，醬料獨門秘製。</p>
      <span class="food-tag">人氣必點</span>
    </div>
    <div class="food-card reveal">
      <span class="food-icon">🧋</span>
      <div class="food-name">珍珠奶茶</div>
      <p class="food-desc">台灣國民飲品，在東海商圈有多家知名茶飲店，手工珍珠 Q 彈有嚼勁，茶香清爽回甘。</p>
      <span class="food-tag">台灣之光</span>
    </div>
    <div class="food-card reveal">
      <span class="food-icon">🍢</span>
      <div class="food-name">滷味小攤</div>
      <p class="food-desc">深夜限定美味，多種食材任選，熬煮數小時的滷汁入味深層，是在地學生最愛的宵夜選擇。</p>
      <span class="food-tag">深夜必備</span>
    </div>
    <div class="food-card reveal">
      <span class="food-icon">🥟</span>
      <div class="food-name">水煎包</div>
      <p class="food-desc">現煎現賣，底部金黃酥脆，內餡飽滿鮮美，每天新鮮製作，早市限定，晚去就賣完了！</p>
      <span class="food-tag">早市限定</span>
    </div>
    <div class="food-card reveal">
      <span class="food-icon">🍜</span>
      <div class="food-name">牛肉麵</div>
      <p class="food-desc">精燉數小時的紅燒湯頭，濃郁醇厚，搭配手工粗麵條，牛肉軟嫩入味，是東海人心中的家鄉味。</p>
      <span class="food-tag">招牌主食</span>
    </div>
    <div class="food-card reveal">
      <span class="food-icon">🍡</span>
      <div class="food-name">麻糬甜點</div>
      <p class="food-desc">日式和風口感結合台灣在地食材，多種口味任選，外皮柔軟 Q 彈，餡料甜而不膩，老少咸宜。</p>
      <span class="food-tag">甜點首選</span>
    </div>
  </div>
</section>

<!-- ════ 交通資訊 ════ -->

<section id="transport">
  <div class="section-header reveal">
    <span class="section-kicker">HOW TO GET HERE</span>
    <h2 class="section-title">交通資訊</h2>
    <div class="section-rule"></div>
  </div>

  <div class="transport-grid">
    <div class="transport-card reveal">
      <span class="transport-icon">🚗</span>
      <div class="transport-method">自行開車</div>
      <p class="transport-detail">國道一號接台74快速道路，於大肚交流道下，沿中清路往南，接龍井路即可抵達東海商圈。</p>
    </div>
    <div class="transport-card reveal">
      <span class="transport-icon">🚌</span>
      <div class="transport-method">搭乘公車</div>
      <p class="transport-detail">搭乘台中公車71路或88快捷，於「東海大學」站下車，步行約5分鐘即達商圈核心地帶。</p>
    </div>
    <div class="transport-card reveal">
      <span class="transport-icon">🚇</span>
      <div class="transport-method">捷運轉乘</div>
      <p class="transport-detail">搭台中捷運至「文心森林公園站」，轉乘公車或計程車，約20分鐘可抵達東海商圈。</p>
    </div>
    <div class="transport-card reveal">
      <span class="transport-icon">🅿️</span>
      <div class="transport-method">停車資訊</div>
      <p class="transport-detail">商圈內設有多處停車場，建議前往「東海藝術街停車場」，假日容量充足，步行即達各餐廳。</p>
    </div>
  </div>
</section>

<!-- ════ 聯絡我們 ════ -->

<section id="contact">
  <div class="section-header reveal">
    <span class="section-kicker">GET IN TOUCH</span>
    <h2 class="section-title">聯絡我們</h2>
    <div class="section-rule"></div>
  </div>

  <div class="contact-wrap">
    <div class="contact-grid reveal">
      <div class="contact-item">
        <div class="contact-label">ADDRESS · 地址</div>
        <div class="contact-value">台中市龍井區<br>東海藝術街</div>
      </div>
      <div class="contact-item">
        <div class="contact-label">HOURS · 營業時間</div>
        <div class="contact-value">週一至週五<br>10:00 – 22:00</div>
      </div>
      <div class="contact-item">
        <div class="contact-label">EMAIL · 電子郵件</div>
        <div class="contact-value">
          <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="244d4a424b64404b4a434c454d09424b4b400a5053">[email&#160;protected]</a>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-label">PHONE · 聯絡電話</div>
        <div class="contact-value">04-2265-XXXX</div>
      </div>
    </div>

```
<div class="contact-form-note reveal">
  📮 如有合作洽詢或活動邀請，歡迎來信，我們將於兩個工作天內回覆。
</div>
```

  </div>
</section>

<!-- ════ FOOTER ════ -->

<footer>
  <div class="footer-brand">台中東海商圈美食導覽</div>
  <div class="footer-email">
    Email：<span style="color:var(--amber)"><a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="afc6c1c9c0efcbc0c1c8c7cec682c9c0c0cb81dbd8">[email&#160;protected]</a></span>
  </div>
  <div class="footer-copy">©2026 東海商圈美食導覽 · All Rights Reserved</div>
</footer>

<script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script>

// Smooth scroll helper (avoids href=”#” triggering Open Link dialog)
function scrollToSection(id) {
const el = document.getElementById(id);
if (el) el.scrollIntoView({ behavior: ‘smooth’ });
}

// Scroll reveal
const observer = new IntersectionObserver((entries) => {
entries.forEach((entry, i) => {
if (entry.isIntersecting) {
setTimeout(() => entry.target.classList.add(‘visible’), i * 80);
observer.unobserve(entry.target);
}
});
}, { threshold: 0.12 });

document.querySelectorAll(’.reveal’).forEach(el => observer.observe(el));

// Nav highlight on scroll
const
