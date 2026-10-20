# -<!DOCTYPE html>
<html lang="ta">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ahlul Wafa - Super Glow Editable</title>
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif+Tamil:wght@600;700&family=Inter:wght@600;700;800&family=Cinzel:wght@700;800&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box}
body{background:#040404;color:#fff;font-family:'Inter',sans-serif}
body.editing [data-edit]{outline:2px dashed #d4af37;background:rgba(212,175,55,0.1)!important;cursor:text}
.browser{max-width:1280px;margin:auto;background:#0a0a0a;min-height:100vh;border-left:1px solid rgba(212,175,55,0.2);border-right:1px solid rgba(212,175,55,0.2)}
.header{padding:16px 22px;display:flex;justify-content:space-between;align-items:center;background:#000;border-bottom:2px solid #d4af37;position:sticky;top:0;z-index:200;flex-wrap:wrap;gap:10px}
.logo-wrap{display:flex;gap:12px;align-items:center;cursor:pointer}
.logo-icon{width:44px;height:44px;border:2px solid #d4af37;border-radius:50%;display:flex;align-items:center;justify-content:center;color:#d4af37;transition:all 0.4s ease!important}
.logo-icon:hover{box-shadow:0 0 30px rgba(212,175,55,0.6),0 0 60px rgba(212,175,55,0.3)!important;transform:rotate(10deg) scale(1.1);border-color:#f5e7a1!important}
.logo-text h1{font-family:'Cinzel';font-size:22px;color:#f5e7a1}
.nav{display:flex;gap:6px;flex-wrap:wrap}
.nav-btn{padding:7px 14px;border-radius:20px;border:1.5px solid rgba(212,175,55,0.3);background:transparent;color:#b8aa80;cursor:pointer;font-weight:700;font-size:11px;transition:all 0.3s cubic-bezier(0.4,0,0.2,1)!important;position:relative;overflow:hidden}
.nav-btn::before{content:'';position:absolute;top:0;left:-100%;width:100%;height:100%;background:linear-gradient(90deg,transparent,rgba(255,255,255,0.2),transparent);transition:left 0.5s}
.nav-btn:hover::before{left:100%}
.nav-btn:hover{background:linear-gradient(180deg,#f5e7a1,#d4af37)!important;color:#000!important;box-shadow:0 0 25px rgba(212,175,55,0.6),0 0 50px rgba(212,175,55,0.3),0 5px 15px rgba(0,0,0,0.3)!important;transform:translateY(-2px) scale(1.05);border-color:#f5e7a1!important}
.nav-btn.active{background:linear-gradient(180deg,#f5e7a1,#d4af37)!important;color:#000!important;box-shadow:0 0 20px rgba(212,175,55,0.5),0 0 40px rgba(212,175,55,0.2)!important;animation:navPulse 2s infinite}
@keyframes navPulse{0%,100%{box-shadow:0 0 20px rgba(212,175,55,0.5),0 0 40px rgba(212,175,55,0.2)}50%{box-shadow:0 0 30px rgba(212,175,55,0.8),0 0 60px rgba(212,175,55,0.4)}}
.page{display:none}.page.active{display:block;animation:pageGlow 0.6s ease}
@keyframes pageGlow{0%{opacity:0;transform:translateY(15px);filter:brightness(0.8)}100%{opacity:1;transform:translateY(0);filter:brightness(1)}}
.main{padding:22px;display:grid;grid-template-columns:1.2fr 1fr;gap:16px}
.stat{background:#17130a;border:1.5px solid #d4af37;border-radius:14px;padding:16px;text-align:center;transition:all 0.4s cubic-bezier(0.4,0,0.2,1)!important;cursor:pointer;position:relative;overflow:hidden}
.stat::after{content:'';position:absolute;top:-50%;left:-50%;width:200%;height:200%;background:radial-gradient(circle,rgba(212,175,55,0.15) 0%,transparent 60%);opacity:0;transition:opacity 0.4s;pointer-events:none}
.stat:hover{transform:translateY(-6px) scale(1.03);border-color:#f5e7a1!important;box-shadow:0 10px 30px rgba(212,175,55,0.3),0 0 40px rgba(212,175,55,0.15),0 0 0 1px rgba(212,175,55,0.2)!important;background:linear-gradient(145deg,#251e0a,#17130a)!important}
.stat:hover::after{opacity:1}
.campaign{background:#16120a;border:1.5px solid #d4af37;border-radius:14px;padding:16px;margin-top:12px;transition:all 0.4s ease!important;cursor:pointer}
.campaign:hover{transform:translateY(-3px);box-shadow:0 10px 30px rgba(212,175,55,0.2),0 0 0 1px rgba(212,175,55,0.3)!important;border-color:#f5e7a1!important}
.progress{height:7px;background:#1e1e1e;border-radius:10px;margin:10px 0;overflow:hidden}
.progress-bar{width:42%;height:100%;background:linear-gradient(90deg,#8a6d1b,#f5e7a1)}
.recent{grid-column:1/-1;background:#0f0f0f;border:1px solid #333;border-radius:12px;overflow:hidden}
.recent .row{padding:10px 16px;border-bottom:1px solid #222;transition:all 0.3s ease!important;cursor:pointer}
.recent .row:hover{background:rgba(212,175,55,0.08)!important;padding-left:22px!important;box-shadow:inset 4px 0 0 #d4af37,0 2px 10px rgba(212,175,55,0.1)!important}
.welfare{padding:24px;background:#050505;border-top:1.5px solid #d4af37}
.w-grid{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-top:18px}
.w-col{background:#0f0f0f;border-radius:12px;padding:16px;transition:all 0.35s cubic-bezier(0.4,0,0.2,1)!important;cursor:pointer}
.w-col.done{border-top:3px solid #22c55e}.w-col.todo{border-top:3px solid #ff4444}
.w-col:hover{transform:translateY(-4px) scale(1.02);box-shadow:0 8px 25px rgba(0,0,0,0.4),0 0 30px rgba(212,175,55,0.15)!important}
.task{background:#15120a;border:1px solid #2a2a2a;border-radius:10px;padding:12px;margin-bottom:10px;transition:all 0.35s cubic-bezier(0.4,0,0.2,1)!important;cursor:pointer}
.task:hover{transform:translateY(-3px) scale(1.02);border-color:rgba(212,175,55,0.5)!important;box-shadow:0 5px 20px rgba(212,175,55,0.15)!important;background:#1f1a0e!important}
.donate-page{padding:28px;background:#080808}
.donate-grid{display:grid;grid-template-columns:1fr 1fr;gap:20px;margin-top:20px}
.donate-card{background:#1e190b;border:1.8px solid #d4af37;border-radius:18px;padding:22px;transition:all 0.35s cubic-bezier(0.4,0,0.2,1)!important;cursor:pointer}
.donate-card:hover{transform:translateY(-5px) scale(1.02);border-color:#f5e7a1!important;box-shadow:0 12px 35px rgba(0,0,0,0.4),0 0 40px rgba(212,175,55,0.2)!important;background:linear-gradient(145deg,#2a220f,#1e190b)!important}
.donate-card .detail{background:rgba(0,0,0,0.4);border:1px solid rgba(212,175,55,0.2);border-radius:10px;padding:12px;margin:8px 0;display:flex;justify-content:space-between;transition:all 0.3s ease!important}
.donate-card .detail:hover{background:rgba(212,175,55,0.1)!important;border-color:#d4af37!important;transform:translateX(3px)}
.qr-box{background:#fff;border-radius:16px;padding:16px;text-align:center;color:#000;transition:all 0.4s ease!important;cursor:pointer}
.qr-box:hover{transform:scale(1.03);box-shadow:0 0 30px rgba(212,175,55,0.4)!important}
.suggest-page{padding:28px;background:#080808}
.form-grid{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-top:20px;max-width:800px;margin:auto}
.form-box{background:#1e190b;border:1.5px solid rgba(212,175,55,0.35);border-radius:16px;padding:20px;transition:all 0.35s cubic-bezier(0.4,0,0.2,1)!important}
.form-box:hover{transform:translateY(-3px);box-shadow:0 8px 25px rgba(212,175,55,0.15)!important;border-color:rgba(212,175,55,0.6)!important}
.form-box.full{grid-column:1/-1}
.form-box label{color:#d4af37;font-size:12px;font-weight:700;display:block;margin-bottom:6px}
.form-box input,.form-box textarea,.form-box select{width:100%;padding:12px;border-radius:10px;border:1.5px solid rgba(212,175,55,0.3);background:#000;color:#fff;transition:all 0.3s ease!important}
.form-box input:focus,.form-box textarea:focus{box-shadow:0 0 0 2px rgba(212,175,55,0.2),0 0 20px rgba(212,175,55,0.15)!important;transform:translateY(-1px);border-color:#f5e7a1!important}
.nirvagam-page{padding:28px;background:#080808}
.n-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(300px,1fr));gap:18px;margin-top:22px}
.card{background:#1e190b;border:1.6px solid #d4af37;border-radius:18px;padding:20px;position:relative;transition:all 0.45s cubic-bezier(0.4,0,0.2,1)!important;cursor:pointer;overflow:hidden}
.card::before{content:'';position:absolute;top:0;left:-100%;width:100%;height:100%;background:linear-gradient(90deg,transparent,rgba(212,175,55,0.15),transparent);transition:left 0.6s;pointer-events:none}
.card:hover::before{left:100%}
.card:hover{transform:translateY(-8px) scale(1.03);border-color:#f5e7a1!important;box-shadow:0 15px 40px rgba(0,0,0,0.5),0 0 50px rgba(212,175,55,0.25),0 0 0 1px rgba(212,175,55,0.3),inset 0 1px 0 rgba(245,231,161,0.2)!important;background:linear-gradient(145deg,#2a220f,#1e190b)!important}
.card.founder{border:2px solid #f5e7a1;background:#251e0a}
.card.founder:hover{box-shadow:0 20px 50px rgba(0,0,0,0.6),0 0 60px rgba(212,175,55,0.35),0 0 0 2px #f5e7a1!important;transform:translateY(-10px) scale(1.04)}
.role{position:absolute;top:-10px;left:16px;background:#d4af37;color:#000;padding:4px 12px;border-radius:20px;font-weight:800;font-size:11px;transition:all 0.3s ease!important}
.card:hover .role{background:linear-gradient(90deg,#f5e7a1,#d4af37);box-shadow:0 0 15px rgba(212,175,55,0.5)}
.mobile{background:rgba(212,175,55,0.1);border:1px solid #d4af37;padding:10px;border-radius:10px;margin-top:10px;font-weight:700;transition:all 0.3s ease!important;cursor:pointer}
.mobile:hover{background:linear-gradient(90deg,rgba(212,175,55,0.25),rgba(212,175,55,0.1))!important;border-color:#f5e7a1!important;box-shadow:0 0 20px rgba(212,175,55,0.3),inset 0 1px 0 rgba(212,175,55,0.2)!important;transform:scale(1.03)}
.admin-bar{display:none;position:fixed;bottom:0;left:0;right:0;background:#000;border-top:2px solid #d4af37;padding:10px;z-index:9999;gap:8px;flex-wrap:wrap;justify-content:center}
.admin-bar.active{display:flex}
.admin-bar button{background:#111;border:1px solid #d4af37;color:#d4af37;padding:8px 14px;border-radius:20px;cursor:pointer;font-weight:700;transition:all 0.3s ease!important}
.admin-bar button:hover{background:#d4af37;color:#000;box-shadow:0 0 15px rgba(212,175,55,0.5);transform:translateY(-2px)}
#login{position:fixed;inset:0;background:rgba(0,0,0,0.9);display:none;justify-content:center;align-items:center;z-index:99999}
#login.active{display:flex}
.modal{background:#111;border:2px solid #d4af37;border-radius:16px;padding:20px;width:90%;max-width:340px;box-shadow:0 0 40px rgba(212,175,55,0.3)}
.modal input{width:100%;padding:12px;margin:8px 0;border-radius:10px;border:1px solid #d4af37;background:#000;color:#fff}
.footer{padding:14px 22px;display:flex;justify-content:space-between;font-size:10px;color:#666;border-top:1px solid #222;background:#080808}
@media(max-width:900px){.main{grid-template-columns:1fr}.w-grid{grid-template-columns:1fr}.donate-grid{grid-template-columns:1fr}.form-grid{grid-template-columns:1fr}.n-grid{grid-template-columns:1fr}}
</style>
</head>
<body>
<div class="browser">
<div class="header">
<div class="logo-wrap" id="logoSecret"><div class="logo-icon">☪</div><div class="logo-text"><h1 data-edit>Ahlul Wafa</h1><p data-edit>அஹ்லுல் வஃபா இஸ்லாமிய தொண்டு நிறுவனம்</p></div></div>
<div class="nav">
<button class="nav-btn active" onclick="showPage('home')">🏠 Home</button>
<button class="nav-btn" onclick="showPage('donate')">💰 நன்கொடை</button>
<button class="nav-btn" onclick="showPage('nirvagam')">👑 நிர்வாகிகள்</button>
<button class="nav-btn" onclick="showPage('suggest')">💬 ஆலோசனை</button>
</div>
</div>

<div id="home" class="page active">
<div class="main">
<div>
<h2 data-edit style="font-family:Cinzel;color:#f5e7a1;font-size:20px">Empowering Lives with Compassion & Faith</h2>
<h3 data-edit style="font-size:14px;margin:6px 0">இரக்கத்துடனும் நம்பிக்கையுடனும் வாழ்க்கையை மேம்படுத்துதல்</h3>
<div class="campaign">
<h4 data-edit style="color:#f5e7a1">🍱 பசியை போக்கும் திட்டம் - மண்ணடி</h4>
<div style="display:flex;justify-content:space-between;font-size:11px;color:#888;margin-top:8px"><span data-edit>Raised: ₹11,300</span><span data-edit>Goal: ₹27,000 • 42%</span></div>
<div class="progress"><div class="progress-bar"></div></div>
</div>
</div>
<div style="display:grid;grid-template-columns:1fr 1fr;gap:12px">
<div class="stat"><div style="font-size:26px;color:#d4af37">👥</div><div data-edit style="font-size:10px;color:#888">Total Donors</div><div data-edit style="font-size:20px;font-weight:900">19</div></div>
<div class="stat"><div style="font-size:26px;color:#d4af37">💵</div><div data-edit style="font-size:10px;color:#888">Funds Raised</div><div data-edit style="font-size:20px;font-weight:900">₹11,300</div></div>
<div class="stat"><div style="font-size:26px;color:#d4af37">🍱</div><div data-edit style="font-size:10px;color:#888">Meals Served</div><div data-edit style="font-size:20px;font-weight:900">40</div></div>
<div class="stat"><div style="font-size:26px;color:#d4af37">📋</div><div data-edit style="font-size:10px;color:#888">Active Campaigns</div><div data-edit style="font-size:20px;font-weight:900">01</div></div>
</div>
<div class="recent">
<div style="display:flex;justify-content:space-between;padding:12px 16px;background:#000;border-bottom:1px solid #333;color:#f5e7a1;font-weight:700"><span data-edit>Recent Donations - ₹11,300</span></div>
<div data-edit class="row">إعجاز أحمد - ₹2,200 • இன்று</div>
<div data-edit class="row">عبد الرحمن - ₹2,000 • இன்று</div>
<div data-edit class="row">محمد عادل - ₹1,000 • இன்று</div>
</div>
</div>
<div class="welfare">
<h2 data-edit style="font-family:Cinzel;text-align:center;color:#f5e7a1">🌟 நலத்திட்டங்கள்</h2>
<div class="w-grid">
<div class="w-col done"><h3 data-edit style="color:#4ade80">🟢 செய்து முடித்தவை</h3><div class="task"><h4 data-edit style="color:#f5e7a1">✅ முதல் நாள் உணவு விநியோகம்</h4><p data-edit style="font-size:11px;color:#888">20/10/2026 - 40 நபர்களுக்கு மதிய உணவு</p></div><div class="task"><h4 data-edit style="color:#f5e7a1">✅ நன்கொடை வசூல் - 1வது கட்டம்</h4><p data-edit style="font-size:11px;color:#888">19 நபர்கள் - ₹11,300</p></div></div>
<div class="w-col todo"><h3 data-edit style="color:#ff6b6b">🔴 செய்ய வேண்டியவை</h3><div class="task"><h4 data-edit style="color:#f5e7a1">🍱 தினசரி உணவு விரிவாக்கம்</h4><p data-edit style="font-size:11px;color:#888">40-ல் இருந்து 60 நபர்கள்</p></div><div class="task"><h4 data-edit style="color:#f5e7a1">📚 கல்வி உதவி திட்டம்</h4><p data-edit style="font-size:11px;color:#888">ஏழை மாணவர்களுக்கு புத்தகம்</p></div><div class="task"><h4 data-edit style="color:#f5e7a1">🧥 குளிர்கால உடை</h4><p data-edit style="font-size:11px;color:#888">100 நபர்களுக்கு போர்வை</p></div></div>
</div>
</div>
</div>

<div id="donate" class="page">
<div class="donate-page">
<h2 data-edit style="font-family:Cinzel;text-align:center;color:#f5e7a1">💰 நன்கொடை விவரங்கள்</h2>
<p data-edit style="text-align:center;color:#888;font-size:12px;margin-top:6px">Bank • GPay • QR Code - எல்லாம் மின்னும்!</p>
<div class="donate-grid">
<div class="donate-card">
<h3 data-edit>🏦 வங்கி விவரங்கள் - Bank Details</h3>
<div class="detail"><span>வங்கி பெயர்</span><span data-edit>SBI - State Bank of India</span></div>
<div class="detail"><span>கணக்கு பெயர்</span><span data-edit>Ahlul Wafa Trust</span></div>
<div class="detail"><span>கணக்கு எண்</span><span data-edit>123456789012</span></div>
<div class="detail"><span>IFSC Code</span><span data-edit>SBIN0001234</span></div>
<div class="detail"><span>கிளை</span><span data-edit>Mannadi, Chennai</span></div>
<div class="detail"><span>Account Type</span><span data-edit>Savings</span></div>
</div>
<div class="donate-card">
<h3 data-edit>📱 GPay / PhonePe / UPI - மின்னும்!</h3>
<div class="detail"><span>GPay Number</span><span data-edit>99527 01147</span></div>
<div class="detail"><span>UPI ID</span><span data-edit>ahlulwafa@oksbi</span></div>
<div class="detail"><span>PhonePe</span><span data-edit>99527 01147</span></div>
<div class="detail"><span>Paytm</span><span data-edit>99527 01147</span></div>
<div class="qr-box"><div data-edit style="width:200px;height:200px;background:#f0f0f0;border:2px dashed #d4af37;border-radius:12px;display:flex;align-items:center;justify-content:center;margin:10px auto;color:#666;flex-direction:column"><div style="font-size:48px">📱</div><div style="font-weight:700">QR Code இங்கே வரும்</div><div style="font-size:10px">உங்கள் QR Upload செய்யவும்</div></div><p data-edit style="font-size:11px;color:#666;margin-top:8px">GPay-ல் Scan செய்து நன்கொடை</p></div>
</div>
<div class="donate-card" style="grid-column:1/-1;text-align:center;border:2px solid #f5e7a1">
<h3 data-edit style="justify-content:center">💎 உங்கள் நன்கொடை எப்படி பயன்படும்?</h3>
<div style="display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin-top:14px">
<div style="background:rgba(0,0,0,0.3);padding:12px;border-radius:10px;transition:all 0.3s ease;cursor:pointer" onmouseover="this.style.transform='scale(1.05)';this.style.boxShadow='0 0 20px rgba(212,175,55,0.3)'" onmouseout="this.style.transform='scale(1)';this.style.boxShadow='none'"><div style="font-size:24px">🍱</div><div data-edit style="font-size:12px;color:#f5e7a1;margin-top:4px;font-weight:700">₹50 = 1 நபருக்கு உணவு</div></div>
<div style="background:rgba(0,0,0,0.3);padding:12px;border-radius:10px;transition:all 0.3s ease;cursor:pointer" onmouseover="this.style.transform='scale(1.05)';this.style.boxShadow='0 0 20px rgba(212,175,55,0.3)'" onmouseout="this.style.transform='scale(1)';this.style.boxShadow='none'"><div style="font-size:24px">📚</div><div data-edit style="font-size:12px;color:#f5e7a1;margin-top:4px;font-weight:700">₹500 = 1 மாணவருக்கு புத்தகம்</div></div>
<div style="background:rgba(0,0,0,0.3);padding:12px;border-radius:10px;transition:all 0.3s ease;cursor:pointer" onmouseover="this.style.transform='scale(1.05)';this.style.boxShadow='0 0 20px rgba(212,175,55,0.3)'" onmouseout="this.style.transform='scale(1)';this.style.boxShadow='none'"><div style="font-size:24px">🧥</div><div data-edit style="font-size:12px;color:#f5e7a1;margin-top:4px;font-weight:700">₹1000 = 1 போர்வை</div></div>
</div>
<p data-edit style="font-size:11px;color:#d4af37;margin-top:14px">جزاكم الله خيرا • அல்லாஹ் உங்கள் நன்கொடையை ஏற்றுக்கொள்வானாக</p>
</div>
</div>
<div style="text-align:center;margin-top:20px"><button class="nav-btn" onclick="showPage('home')">← Home திரும்ப</button></div>
</div>
</div>

<div id="nirvagam" class="page">
<div class="nirvagam-page">
<h2 data-edit style="font-family:Cinzel;text-align:center;color:#f5e7a1;font-size:26px">👑 நிர்வாகிகள் குழு - ஒவ்வொருவரும் மின்னுவார்!</h2>
<p data-edit style="text-align:center;color:#888;font-size:11px;margin-top:6px">ஒவ்வொரு Card-ஐ தொட்டாலும் தங்க நிறத்தில் மின்னும் - Shimmer ஓடும்!</p>
<div class="n-grid">
<div class="card founder"><span class="role">🌟 நிறுவனர்</span><h3 data-edit style="color:#f5e7a1;margin-top:12px">மௌலானா முஃப்தி T. ஷர்ஃபுத்தீன் பாகவி ஹழ்ரத்</h3><p data-edit style="font-size:12px;color:#c8b88a;margin:8px 0">சேவை: ஷரீஅத் வழிகாட்டுதல், துஆ, இறுதி முடிவு</p><div class="mobile" data-edit>📞 94446 48516</div></div>
<div class="card"><span class="role">👑 தலைவர்</span><h3 data-edit style="color:#f5e7a1;margin-top:12px">ஜனாப். முஹம்மது ரசூல்</h3><p data-edit style="font-size:12px;color:#c8b88a">சேவை: குழுவை வழிநடத்துதல், திட்டமிடல்</p><div class="mobile" data-edit>📞 +91 89252 32136</div></div>
<div class="card"><span class="role">👑 துணைத் தலைவர்</span><h3 data-edit style="color:#f5e7a1;margin-top:12px">ஜனாப். முஹம்மது தவ்ஃபீக்</h3><p data-edit style="font-size:12px;color:#c8b88a">சேவை: தலைவருக்கு உதவி, கூட்டம் நடத்துதல்</p><div class="mobile" data-edit>📞 +91 00000 00000</div></div>
<div class="card"><span class="role">📝 செயலாளர்</span><h3 data-edit style="color:#f5e7a1;margin-top:12px">ஜனாப். அப்துல் ஹஸீப்</h3><p data-edit style="font-size:12px;color:#c8b88a">சேவை: பதிவுகள் பராமரிப்பு, அறிக்கை தயாரித்தல்</p><div class="mobile" data-edit>📞 +91 74183 55830</div></div>
<div class="card"><span class="role">📝 துணைச் செயலாளர்</span><h3 data-edit style="color:#f5e7a1;margin-top:12px">ஜனாப். அபூபக்கர் சித்திக்</h3><p data-edit style="font-size:12px;color:#c8b88a">சேவை: பயனாளிகள் பட்டியல், விநியோகம்</p><div class="mobile" data-edit>📞 +91 00000 00000</div></div>
<div class="card"><span class="role">💰 பொருளாளர்</span><h3 data-edit style="color:#f5e7a1;margin-top:12px">ஜனாப். இஃஜாஸ் அஹ்மது</h3><p data-edit style="font-size:12px;color:#c8b88a">சேவை: வரவு செலவு கணக்கு, வெளிப்படைத்தன்மை</p><div class="mobile" data-edit>📞 99527 01147</div></div>
<div class="card"><span class="role">💰 துணைப் பொருளாளர்</span><h3 data-edit style="color:#f5e7a1;margin-top:12px">ஜனாப். அப்துர் ரஷீத்</h3><p data-edit style="font-size:12px;color:#c8b88a">சேவை: பில் சேகரிப்பு, பொருளாளருக்கு உதவி</p><div class="mobile" data-edit>📞 +91 00000 00000</div></div>
</div>
<div style="text-align:center;margin-top:20px"><button class="nav-btn" onclick="showPage('home')">← Home திரும்ப</button></div>
</div>
</div>

<div id="suggest" class="page">
<div class="suggest-page">
<h2 data-edit style="font-family:Cinzel;text-align:center;color:#f5e7a1;font-size:24px">💬 ஆலோசனைகள் / புகார்கள் - Box Box-ஆக மின்னும்!</h2>
<p data-edit style="text-align:center;color:#888;font-size:12px;margin-top:6px">ஒவ்வொரு Box-ஐ தொட்டாலும் தங்க நிறத்தில் மின்னும்!</p>
<div class="form-grid" style="margin-top:20px">
<div class="form-box"><label>👤 பெயர் - Name *</label><input type="text" placeholder="உங்கள் பெயரை எழுதவும்"></div>
<div class="form-box"><label>📍 ஊர் - Place *</label><input type="text" placeholder="உங்கள் ஊர் / ஏரியா"></div>
<div class="form-box"><label>📞 மொபைல் நம்பர் - Mobile *</label><input type="tel" placeholder="+91 00000 00000"></div>
<div class="form-box"><label>📂 விஷயம் - Subject</label><select><option>நலத்திட்டம் பற்றி</option><option>நன்கொடை பற்றி</option><option>புதிய யோசனை</option><option>புகார் / குறை</option><option>மற்றவை</option></select></div>
<div class="form-box full"><label>💬 விஷயம் / ஆலோசனை - Message *</label><textarea placeholder="உங்கள் ஆலோசனை, கருத்து, புகாரை இங்கே விரிவாக எழுதவும்..." style="min-height:100px"></textarea></div>
<div class="form-box full" style="text-align:center;background:transparent;border:none"><button style="background:linear-gradient(180deg,#f5e7a1,#d4af37);color:#000;padding:12px 20px;border-radius:20px;border:none;font-weight:800;width:100%;max-width:300px;cursor:pointer;transition:all 0.3s ease" onmouseover="this.style.transform='scale(1.05)';this.style.boxShadow='0 0 25px rgba(212,175,55,0.5)'" onmouseout="this.style.transform='scale(1)';this.style.boxShadow='none'">📤 ஆலோசனை அனுப்பு - Submit</button><p data-edit style="font-size:10px;color:#888;margin-top:10px">உங்கள் தகவல்கள் பாதுகாப்பாக இருக்கும் • 24 மணி நேரத்தில் பதில்</p></div>
</div>
<div style="text-align:center;margin-top:20px"><button class="nav-btn" onclick="showPage('home')">← Home திரும்ப</button></div>
</div>
</div>

<div class="footer"><span data-edit>© 2024-2026 Ahlul Wafa • Chennai Mannadi • Super Glow Edition ✨</span><span data-edit>Privacy • Terms • Contact • جزاكم الله خيرا</span></div>
</div>

<div class="admin-bar" id="adminBar"><b style="color:#f5e7a1">🔓 ADMIN - GLOW ON ✨</b><button onclick="toggleEdit()">✏️ எடிட் ON/OFF</button><button onclick="saveAll()">💾 Save</button><button onclick="exportHTML()">📤 Export HTML</button><button onclick="logout()" style="background:#c00;color:#fff;border-color:#c00">Logout</button><span id="status" style="color:#7CFC00;margin-left:10px"></span></div>

<div id="login"><div class="modal"><h3 style="color:#d4af37;text-align:center;font-family:Cinzel">🔐 Admin Login - Glow Edition</h3><p style="text-align:center;font-size:11px;color:#777;margin:8px 0">லோகோ ☪ 5 முறை தட்டவும்</p><input type="password" id="pInput" placeholder="Password: ahlulwafa786"><button style="width:100%;margin-top:10px;background:linear-gradient(180deg,#f5e7a1,#d4af37);color:#000;padding:10px;border-radius:20px;border:none;font-weight:800;cursor:pointer" onclick="login()">✨ Login - Glow ON</button><p id="err" style="color:#ff4444;font-size:12px;text-align:center;margin-top:8px"></p><button onclick="closeL()" style="background:none;border:none;color:#666;width:100%;margin-top:10px">Cancel</button></div></div>

<script>
let PASS='ahlulwafa786',isAdmin=false,editing=false;
function init(){let c=0;const logo=document.getElementById('logoSecret');function trig(){c++;logo.style.transform='scale(1.2) rotate(5deg)';logo.style.filter='drop-shadow(0 0 15px #d4af37)';setTimeout(()=>{logo.style.transform='scale(1) rotate(0)';logo.style.filter='none'},200);if(c>=5){openL();c=0}setTimeout(()=>c=0,3500)}logo.addEventListener('click',trig)}
function openL(){document.getElementById('login').classList.add('active')}
function closeL(){document.getElementById('login').classList.remove('active')}
function login(){const v=document.getElementById('pInput').value;if(v===PASS){isAdmin=true;document.getElementById('adminBar').classList.add('active');closeL();document.getElementById('status').innerText='✅ Super Glow Admin ON - எல்லாம் மின்னும்! ✨'}else document.getElementById('err').innerText='❌ தவறு'}
function logout(){isAdmin=false;editing=false;document.body.classList.remove('editing');document.getElementById('adminBar').classList.remove('active');document.querySelectorAll('[data-edit]').forEach(e=>e.contentEditable=false)}
function toggleEdit(){if(!isAdmin)return;editing=!editing;document.body.classList.toggle('editing',editing);document.querySelectorAll('[data-edit]').forEach(el=>{el.contentEditable=editing});document.getElementById('status').innerText=editing?'✏️ Edit ON - இப்போது எல்லா இடத்திலும் Type செய்யலாம் + மின்னும்! ✨':'Edit OFF'}
function saveAll(){localStorage.setItem('ahlul_glow_super',document.documentElement.innerHTML);document.getElementById('status').innerText='💾 Saved! Super Glow Saved ✨'}
function exportHTML(){const full=document.documentElement.outerHTML;const blob=new Blob([full],{type:'text/html'});const a=document.createElement('a');a.href=URL.createObjectURL(blob);a.download='AhlulWafa-SUPER-GLOW-Final.html';a.click();document.getElementById('status').innerText='📤 Exported! ✨'}
function showPage(id){document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));document.getElementById(id).classList.add('active');document.querySelectorAll('.nav-btn').forEach(b=>b.classList.remove('active'));const map={'home':0,'donate':1,'nirvagam':2,'suggest':3};if(map[id]!==undefined)document.querySelectorAll('.nav-btn')[map[id]].classList.add('active');window.scrollTo({top:0,behavior:'smooth'});}
window.onload=()=>{init();console.log('%c✨ Ahlul Wafa Super Glow Edition Loaded! ✨','color:#d4af37;font-size:16px;font-weight:bold');}
</script>
</body>
</html>
