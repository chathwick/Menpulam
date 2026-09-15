<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Menpulam - Farmer Registration</title>
  <style>
    * { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: Arial, "Noto Sans Tamil", sans-serif;
      background: #eef7ee;
      color: #17351b;
    }
    .topbar {
      background: #216b36;
      color: white;
      padding: 18px 24px;
      text-align: center;
    }
    .topbar h1 { margin: 0; font-size: 30px; }
    .topbar p { margin: 6px 0 0; }
    .container {
      max-width: 850px;
      margin: 30px auto;
      padding: 0 18px 40px;
    }
    .card {
      background: white;
      border-radius: 18px;
      padding: 28px;
      margin-bottom: 20px;
      box-shadow: 0 5px 18px rgba(0,0,0,.08);
    }
    h2 { color: #216b36; margin-top: 0; }
    .grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 16px;
    }
    label {
      display: block;
      font-weight: bold;
      margin-bottom: 7px;
    }
    input, select {
      width: 100%;
      padding: 12px;
      border: 1px solid #b8cdbb;
      border-radius: 10px;
      font-size: 15px;
    }
    .full { grid-column: 1 / -1; }
    .note {
      background: #fff8dc;
      border-left: 5px solid #e2b100;
      padding: 12px;
      border-radius: 8px;
      margin: 15px 0;
      font-size: 14px;
    }
    .plan {
      border: 2px solid #216b36;
      border-radius: 14px;
      padding: 18px;
      background: #f4fbf4;
    }
    .price { font-size: 26px; font-weight: bold; color: #216b36; }
    button {
      width: 100%;
      padding: 14px;
      border: 0;
      border-radius: 10px;
      background: #216b36;
      color: white;
      font-size: 17px;
      font-weight: bold;
      cursor: pointer;
      margin-top: 15px;
    }
    button:hover { background: #18542a; }
    .secondary { background: #6b7c6d; }
    #success {
      display: none;
      background: #e1f5e4;
      border: 2px solid #4b9b59;
      padding: 20px;
      border-radius: 14px;
      margin-top: 20px;
    }
    .dashboard { display: none; }
    .feature {
      display: inline-block;
      background: #eaf6ec;
      padding: 8px 11px;
      border-radius: 20px;
      margin: 4px;
      font-size: 14px;
    }
    @media (max-width: 650px) {
      .grid { grid-template-columns: 1fr; }
      .full { grid-column: auto; }
    }
  #registrationScreen { display:block; }
#dashboardScreen { display:none; }
body.dashboard-active #registrationScreen { display:none; }
body.dashboard-active #dashboardScreen { display:block; }

/* Cool animation pack */
html{scroll-behavior:smooth}
body{overflow-x:hidden}
@keyframes floatY{0%,100%{transform:translateY(0)}50%{transform:translateY(-8px)}}
@keyframes glowPulse{0%,100%{box-shadow:0 0 0 rgba(46,125,50,0)}50%{box-shadow:0 0 28px rgba(46,125,50,.22)}}
@keyframes fadeUp{from{opacity:0;transform:translateY(18px)}to{opacity:1;transform:translateY(0)}}
@keyframes shimmer{from{background-position:-200% 0}to{background-position:200% 0}}
@keyframes leafDrift{0%{transform:translate(0,0) rotate(0)}50%{transform:translate(12px,-8px) rotate(8deg)}100%{transform:translate(0,0) rotate(0)}}
.hero,.hero-section{animation:fadeUp .8s ease both}
.logo,.brand-logo{animation:floatY 4s ease-in-out infinite}
.card,.feature-card,.feature,.market-card,.scheme-card,.labour-card{transition:transform .35s cubic-bezier(.2,.8,.2,1),box-shadow .35s ease, border-color .35s ease}
.card:hover,.feature-card:hover,.feature:hover,.market-card:hover,.scheme-card:hover,.labour-card:hover{transform:translateY(-7px) scale(1.015);animation:glowPulse 1.6s ease-in-out infinite}
button,.btn,a.button{transition:transform .2s ease,box-shadow .2s ease}
button:hover,.btn:hover,a.button:hover{transform:translateY(-2px);box-shadow:0 8px 22px rgba(0,0,0,.12)}
button:active,.btn:active{transform:scale(.97)}
input:focus,select:focus,textarea:focus{outline:none;transform:scale(1.01);transition:.2s;box-shadow:0 0 0 4px rgba(46,125,50,.12)}
section,.page,.detail-page{animation:fadeUp .55s ease both}
.progress,.progress-bar,.loading-bar{background-image:linear-gradient(90deg,transparent,rgba(255,255,255,.55),transparent);background-size:200% 100%;animation:shimmer 2s linear infinite}
.leaf,.floating-leaf{animation:leafDrift 5s ease-in-out infinite}
.toast,.notification{animation:fadeUp .35s ease both}
@media(prefers-reduced-motion:reduce){*,*:before,*:after{animation:none!important;transition:none!important;scroll-behavior:auto!important}}

/* Header spacing enhancement */
header, .header, .topbar, .navbar { gap: 28px; }
header .brand, .header .brand, .topbar .brand, .navbar .brand, .logo, .brand { margin-right: 34px; }
header select, header .language-selector, .header select, .topbar select, .navbar select { margin-left: 18px; }
@media (max-width: 700px) {
  header, .header, .topbar, .navbar { gap: 16px; flex-wrap: wrap; }
  header .brand, .header .brand, .topbar .brand, .navbar .brand, .logo, .brand { margin-right: 12px; }
}
</style>

<style>
*{box-sizing:border-box}
body{margin:0;font-family:Inter,Arial,sans-serif;background:#f4f6f2;color:#17231a}
.app-shell{min-height:100vh}
.topbar{height:76px;background:#183d29;color:white;display:flex;align-items:center;justify-content:space-between;padding:0 5%;position:sticky;top:0;z-index:10}
.brand{font-size:26px;font-weight:800}
.brand-sub{font-size:12px;opacity:.78;margin-top:2px}
#languageSelect{border:1px solid #d7e0d8;border-radius:8px;padding:9px 12px;background:white;color:#17231a}
main{width:min(1180px,92%);margin:30px auto}
.hero{display:flex;justify-content:space-between;align-items:center;gap:20px;margin-bottom:22px}
.eyebrow,.card-kicker{font-size:11px;letter-spacing:1.2px;font-weight:800;color:#55705e;margin:0 0 7px}
h1{font-size:34px;margin:0 0 8px}h2{margin:0 0 10px;font-size:21px}h3{margin:0 0 7px}
.hero p:not(.eyebrow){margin:0;color:#5b685f}
button{font:inherit;cursor:pointer}
.outline-btn,.primary-btn,.voice-btn{border-radius:8px;padding:10px 15px;font-weight:700}
.outline-btn{background:white;border:1px solid #9eaea2;color:#183d29}
.primary-btn,.voice-btn{background:#183d29;color:white;border:1px solid #183d29}
.primary-btn:hover,.voice-btn:hover{background:#24553a}
.farm-summary{display:grid;grid-template-columns:repeat(4,1fr);background:white;border:1px solid #dde4de;border-radius:12px;margin-bottom:20px;overflow:hidden}
.farm-summary div{padding:17px;border-right:1px solid #e5e9e5}.farm-summary div:last-child{border-right:0}
.farm-summary span,.mini-grid span{display:block;color:#68746c;font-size:12px;margin-bottom:5px}
.farm-summary strong{font-size:16px}
.grid{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
.card{background:white;border:1px solid #dde4de;border-radius:12px;padding:22px;min-height:190px;box-shadow:0 3px 12px rgba(20,40,25,.04)}
.card.large{grid-column:span 2;min-height:260px}
.card p:not(.card-kicker){color:#59665d;line-height:1.5}
.card-head{display:flex;justify-content:space-between;align-items:start}
.status{font-size:11px;border:1px solid #cbd8ce;border-radius:20px;padding:6px 9px;color:#355741}
.update-box{background:#f2f6f1;border-radius:9px;padding:15px;margin:16px 0}
.update-box p{margin:0}
.mini-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}.mini-grid div{border-top:1px solid #e4e9e5;padding-top:12px}
.voice-card{grid-column:span 2}.voice-controls{display:flex;gap:9px;margin:12px 0}
.voice-controls select{border:1px solid #cbd5cd;border-radius:8px;padding:9px;flex:1}
.voice-btn{white-space:nowrap}.voice-card textarea{width:100%;border:1px solid #cbd5cd;border-radius:8px;padding:10px;resize:vertical}
.voice-result{font-size:13px;color:#526158;margin-top:8px;min-height:18px}
.calendar-panel{background:white;border:1px solid #dde4de;border-radius:12px;padding:22px;margin-top:20px}
.calendar-head{display:flex;justify-content:space-between;align-items:center;margin-bottom:18px}
.calendar-nav{display:flex;align-items:center;gap:15px}.calendar-nav button{width:34px;height:34px;border:1px solid #ccd6ce;background:white;border-radius:7px}
.weekdays,.calendar-grid{display:grid;grid-template-columns:repeat(7,1fr);gap:7px}
.weekdays span{text-align:center;font-size:12px;font-weight:800;color:#69756d;padding:8px}
.day{min-height:45px;border:1px solid #e1e6e2;background:#fbfcfb;border-radius:7px}
.day.today{border:2px solid #183d29;font-weight:800}.day.task-day{background:#edf4ee}
.task-list{margin-top:18px;border-top:1px solid #e2e7e3;padding-top:14px}.task-list li{margin:7px 0;color:#4f5e55}
.hidden{display:none!important}
.modal{position:fixed;inset:0;background:rgba(10,20,13,.48);display:flex;align-items:center;justify-content:center;padding:20px;z-index:30}
.modal-box{background:white;border-radius:12px;padding:26px;max-width:460px;width:100%;position:relative}
.modal-box .close{position:absolute;right:13px;top:10px;border:0;background:transparent;font-size:25px}
footer{display:flex;justify-content:center;gap:10px;padding:28px;color:#637067;font-size:13px}
@media(max-width:850px){.grid{grid-template-columns:1fr}.card.large,.voice-card{grid-column:span 1}.farm-summary{grid-template-columns:1fr 1fr}.farm-summary div:nth-child(2){border-right:0}.farm-summary div{border-bottom:1px solid #e5e9e5}.hero{align-items:flex-start;flex-direction:column}.calendar-head{align-items:flex-start;gap:15px;flex-direction:column}}
@media(max-width:520px){h1{font-size:27px}.farm-summary{grid-template-columns:1fr}.farm-summary div{border-right:0}.voice-controls{flex-direction:column}}
</style>


<style>
*{box-sizing:border-box}
body{margin:0;font-family:Inter,Arial,sans-serif;background:#f4f6f2;color:#17231a}
button,select,input,textarea{font:inherit}
button{cursor:pointer}
.hidden{display:none!important}
.app-shell{min-height:100vh}
.topbar{height:76px;background:#183d29;color:#fff;display:flex;align-items:center;justify-content:space-between;padding:0 5%;position:sticky;top:0;z-index:10}
.brand{font-size:26px;font-weight:800}.brand-sub{font-size:12px;opacity:.78;margin-top:2px}
.topbar select{border:1px solid #d7e0d8;border-radius:8px;padding:9px 12px;background:#fff;color:#17231a}
.top-actions{display:flex;gap:10px;align-items:center}.header-btn{border:1px solid #b9c8bd;background:transparent;color:white;border-radius:8px;padding:9px 13px}
.registration-main{width:min(850px,92%);margin:42px auto}.registration-card{background:#fff;border:1px solid #dce4de;border-radius:14px;padding:30px;box-shadow:0 4px 18px rgba(20,40,25,.05)}
.eyebrow,.card-kicker{font-size:11px;letter-spacing:1.2px;font-weight:800;color:#55705e;margin:0 0 7px}
.registration-card h1{font-size:32px;margin:0 0 8px}.intro{color:#5b685f;margin-top:0;margin-bottom:25px;line-height:1.5}
.form-grid{display:grid;grid-template-columns:1fr 1fr;gap:18px}label{display:block;font-size:13px;font-weight:700;margin-bottom:7px}
input,select,textarea{width:100%;border:1px solid #cbd5cd;border-radius:8px;padding:11px 12px;background:#fff;color:#17231a}
.subscription{display:flex;justify-content:space-between;align-items:center;gap:20px;background:#f1f5f1;border-radius:10px;padding:18px;margin-bottom:18px}.subscription h2{margin:0 0 6px;font-size:19px}.subscription p{margin:4px 0;color:#5c695f;font-size:13px}
.subscription-price{font-size:22px;font-weight:800;white-space:nowrap}.primary-btn,.voice-btn{background:#183d29;color:white;border:1px solid #183d29;border-radius:8px;padding:10px 15px;font-weight:700}.primary-btn:hover,.voice-btn:hover{background:#24553a}.full-btn{width:100%}
.registration-success{margin-top:15px;padding-top:15px;border-top:1px solid #e1e7e2}.registration-success h2{margin-top:0}
main{width:min(1180px,92%);margin:30px auto}.hero{display:flex;justify-content:space-between;align-items:center;gap:20px;margin-bottom:22px}.hero h1{font-size:34px;margin:0 0 8px}.hero p:not(.eyebrow){margin:0;color:#5b685f}
.farm-summary{display:grid;grid-template-columns:repeat(4,1fr);background:#fff;border:1px solid #dde4de;border-radius:12px;margin-bottom:20px;overflow:hidden}
.farm-summary div{padding:17px;border-right:1px solid #e5e9e5}.farm-summary div:last-child{border-right:0}.farm-summary span,.mini-grid span{display:block;color:#68746c;font-size:12px;margin-bottom:5px}.farm-summary strong{font-size:16px}
.dashboard-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}.card{background:#fff;border:1px solid #dde4de;border-radius:12px;padding:22px;min-height:190px;box-shadow:0 3px 12px rgba(20,40,25,.04)}.card.large{grid-column:span 2;min-height:260px}
.card h2{margin:0 0 10px;font-size:21px}.card p:not(.card-kicker){color:#59665d;line-height:1.5}.card-head{display:flex;justify-content:space-between}.status{font-size:11px;border:1px solid #cbd8ce;border-radius:20px;padding:6px 9px;color:#355741}
.update-box{background:#f2f6f1;border-radius:9px;padding:15px;margin:16px 0}.update-box p{margin:0}.mini-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}.mini-grid div{border-top:1px solid #e4e9e5;padding-top:12px}
.voice-card{grid-column:span 2}.voice-controls{display:flex;gap:9px;margin:12px 0}.voice-controls select{flex:1}.voice-btn{white-space:nowrap}.voice-card textarea{resize:vertical}.voice-result{font-size:13px;color:#526158;margin-top:8px;min-height:18px}
.calendar-panel{background:#fff;border:1px solid #dde4de;border-radius:12px;padding:22px;margin-top:20px}.calendar-head{display:flex;justify-content:space-between;align-items:center;margin-bottom:18px}.calendar-nav{display:flex;align-items:center;gap:15px}.calendar-nav button{width:34px;height:34px;border:1px solid #ccd6ce;background:#fff;border-radius:7px}
.weekdays,.calendar-grid{display:grid;grid-template-columns:repeat(7,1fr);gap:7px}.weekdays span{text-align:center;font-size:12px;font-weight:800;color:#69756d;padding:8px}.day{min-height:45px;border:1px solid #e1e6e2;background:#fbfcfb;border-radius:7px}.day.today{border:2px solid #183d29;font-weight:800}.day.task-day{background:#edf4ee}
.task-list{margin-top:18px;border-top:1px solid #e2e7e3;padding-top:14px}.task-list li{margin:7px 0;color:#4f5e55}
.modal{position:fixed;inset:0;background:rgba(10,20,13,.48);display:flex;align-items:center;justify-content:center;padding:20px;z-index:30}.modal-box{background:#fff;border-radius:12px;padding:26px;max-width:460px;width:100%;position:relative}.modal-box .close{position:absolute;right:13px;top:10px;border:0;background:transparent;font-size:25px}
footer{display:flex;justify-content:center;gap:10px;padding:28px;color:#637067;font-size:13px}
@media(max-width:850px){.dashboard-grid{grid-template-columns:1fr}.card.large,.voice-card{grid-column:span 1}.farm-summary{grid-template-columns:1fr 1fr}.hero{align-items:flex-start;flex-direction:column}}
@media(max-width:650px){.form-grid{grid-template-columns:1fr}.subscription{align-items:flex-start;flex-direction:column}.registration-card{padding:20px}.top-actions{gap:5px}.header-btn{display:none}}
@media(max-width:520px){.farm-summary{grid-template-columns:1fr}.farm-summary div{border-right:0;border-bottom:1px solid #e5e9e5}.voice-controls{flex-direction:column}.calendar-head{align-items:flex-start;flex-direction:column}}
</style>


<style>
.detail-page{max-width:1100px;margin:0 auto;padding:28px 22px 50px;background:#f7f8fa;min-height:100vh}
.detail-header{background:#fff;border:1px solid #e1e5e9;border-radius:14px;padding:22px;margin-bottom:20px}
.detail-header h2{margin:14px 0 6px;font-size:28px;color:#1f2937}
.detail-header p{margin:0;color:#667085}
.back-btn{border:1px solid #cfd5dc;background:#fff;border-radius:8px;padding:9px 14px;cursor:pointer;font-weight:600}
.detail-content{display:grid;gap:16px}
.data-card{background:#fff;border:1px solid #e1e5e9;border-radius:12px;padding:20px}
.data-card h3{margin:0 0 12px;color:#1f2937}
.data-card p{margin:7px 0;color:#4b5563;line-height:1.5}
.data-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(230px,1fr));gap:12px}
.data-item{border:1px solid #e5e7eb;border-radius:9px;padding:13px;background:#fafbfc}
.data-label{font-size:12px;color:#667085;margin-bottom:4px}
.data-value{font-weight:600;color:#1f2937}
.data-table{width:100%;border-collapse:collapse;margin-top:8px}
.data-table th,.data-table td{text-align:left;padding:12px;border-bottom:1px solid #e5e7eb}
.data-table th{background:#f5f6f8;font-weight:700;color:#344054}
.status{display:inline-block;padding:5px 9px;border-radius:7px;background:#eef2f6;font-size:12px;font-weight:600}
.action-btn{border:0;border-radius:8px;padding:9px 13px;background:#1f2937;color:white;cursor:pointer}
@media(max-width:650px){.data-table{font-size:13px}.detail-page{padding:16px 12px}}
</style>

<style>.detail-page{max-width:1200px;margin:0 auto;padding:34px 28px 80px;background:#f5f7f9;min-height:100vh}.detail-header{padding:28px 30px;margin-bottom:24px;border-radius:16px}.detail-header h2{font-size:34px;margin:18px 0 8px}.detail-content{gap:22px}.data-card{padding:28px;border-radius:16px;box-shadow:0 2px 10px rgba(16,24,40,.05)}.data-card h3{font-size:22px;margin-bottom:18px}.data-grid{gap:18px}.data-item{padding:20px;min-height:82px}.data-value{font-size:18px}.data-table th,.data-table td{padding:16px;font-size:15px}.help-panel{position:fixed;right:22px;bottom:22px;z-index:50;background:#fff;border:1px solid #dfe4ea;border-radius:14px;box-shadow:0 8px 28px rgba(16,24,40,.14);padding:13px 16px;display:flex;align-items:center;gap:12px}.help-logo{width:36px;height:36px;border-radius:10px;background:#1f2937;color:#fff;display:grid;place-items:center;font-weight:800}.help-panel strong{display:block;font-size:14px}.help-panel a{display:block;color:#344054;text-decoration:none;font-size:14px;margin-top:3px}.voice-box{background:#fff;border:1px solid #dfe4ea;border-radius:16px;padding:28px}.voice-lang-row{display:flex;gap:10px;flex-wrap:wrap;margin:14px 0}.voice-lang{border:1px solid #cfd5dc;background:#fff;border-radius:8px;padding:9px 14px;cursor:pointer;font-weight:600}.voice-lang.active{background:#1f2937;color:#fff}.voice-answer{margin-top:18px;padding:18px;border:1px solid #e5e7eb;border-radius:10px;background:#fafbfc;line-height:1.6;min-height:55px}.contact-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(270px,1fr));gap:18px}.contact-card{border:1px solid #e3e7ec;border-radius:12px;padding:20px;background:#fafbfc}.contact-card h4{margin:0 0 8px;font-size:17px}.contact-card p{margin:5px 0}.contact-card a{display:inline-block;margin-top:10px;padding:9px 13px;border-radius:8px;background:#1f2937;color:#fff;text-decoration:none;font-weight:600}@media(max-width:650px){.detail-page{padding:18px 14px 90px}.detail-header h2{font-size:28px}.help-panel{left:14px;right:14px;bottom:14px}}</style></head>



<body>
  <div class="app-shell">

    <!-- REGISTRATION PAGE -->
    <section id="registrationPage">
      <header class="topbar">
        <div>
          <div class="brand">Menpulam</div>
          <div class="brand-sub" id="regBrandSub">Smart Farming Platform</div>
        </div>
        <select id="regLanguageSelect" aria-label="Language">
          <option value="en">English</option>
          <option value="ta">Tamil</option>
          <option value="te">తెలుగు</option>
          <option value="kn">ಕನ್ನಡ</option>
          <option value="hi">हिन्दी</option>
        </select>
      </header>

      <main class="registration-main">
        <div class="registration-card">
          <p class="eyebrow" id="regEyebrow">GET STARTED</p>
          <h1 id="regTitle">Farmer Registration</h1>
          <p class="intro" id="regIntro">Enter your details once to create your personalized farming dashboard.</p>

          <form id="farmerForm">
            <div class="form-grid">
              <div>
                <label id="nameLabel" for="name">Farmer Name</label>
                <input id="name" required placeholder="Enter your name" value="Ravi Kumar">
              </div>
              <div>
                <label id="mobileLabel" for="mobile">Mobile Number</label>
                <input id="mobile" type="tel" required pattern="[0-9]{10}" placeholder="9876543210" value="9876543210">
              </div>
              <div>
                <label id="villageLabel" for="village">Village</label>
                <input id="village" required placeholder="Perundurai" value="Perundurai">
              </div>
              <div>
                <label id="districtLabel" for="district">District</label>
                <input id="district" required placeholder="Erode" value="Erode">
              </div>
              <div>
                <label id="cropLabel" for="crop">Main Crop</label>
                <select id="crop" required>
                  <option value="">Select your crop</option>
                  <option selected>Paddy</option><option>Sugarcane</option><option>Turmeric</option>
                  <option>Banana</option><option>Coconut</option><option>Groundnut</option>
                  <option>Vegetables</option><option>Other</option>
                </select>
              </div>
              <div>
                <label id="landLabel" for="land">Land Size (acres)</label>
                <input id="land" type="number" min="0" step="0.01" required placeholder="e.g. 2.5" value="2.5">
              </div>
              <div>
                <label id="soilLabel" for="soil">Soil Type</label>
                <select id="soil" required>
                  <option value="">Select soil type</option>
                  <option selected>Red Soil</option><option>Black Soil</option><option>Alluvial Soil</option>
                  <option>Sandy Soil</option><option>Other</option>
                </select>
              </div>
              <div>
                <label id="waterLabel" for="water">Irrigation</label>
                <select id="water" required>
                  <option value="">Select irrigation source</option>
                  <option selected>Well</option><option>Borewell</option><option>Canal</option>
                  <option>Rainwater</option><option>Other</option>
                </select>
              </div>
              <div>
                <label id="rationLabel" for="ration">Ration Card Details</label>
                <input id="ration" placeholder="RC-ERD-20481" value="RC-ERD-20481">
              </div>
              <div>
                <label id="aadhaarLabel" for="aadhaar">Aadhaar Details</label>
                <input id="aadhaar" inputmode="numeric" maxlength="4" placeholder="4821" value="4821">
              </div>
            </div>


            <div class="subscription">
              <div>
                <p class="eyebrow">PLAN</p>
                <h2 id="planTitle">Menpulam Subscription</h2>
                <p id="trialText"><strong>First 3 days FREE</strong></p>
                <p id="afterTrial">After the free trial, continue with the monthly plan.</p>
              </div>
              <div class="subscription-price">₹100 / month</div>
            </div>

            <button class="primary-btn full-btn" type="submit" id="registerButton">
              Register & Start 3-Day Free Trial
            </button>
          </form>

          <div id="registrationSuccess" class="registration-success hidden">
            <h2 id="successTitle">Registration Successful</h2>
            <p id="successMessage"></p>
            <p id="successTrial"><strong>Your 3-day free trial starts now.</strong></p>
            <button class="primary-btn full-btn" id="continueButton" type="button">Continue to Dashboard</button>
          </div>
        </div>
      </main>
    </section>

    <!-- MAIN DASHBOARD -->
    <section id="dashboardPage" class="hidden">
      <header class="topbar">
        <div>
          <div class="brand">Menpulam</div>
          <div class="brand-sub" id="dashBrandSub">Smart Farming Platform</div>
        </div>
        <div class="top-actions">
          <button class="header-btn" onclick="showRegistration()" id="editProfileBtn">Edit Details</button>
          <select id="dashboardLanguageSelect" aria-label="Language">
            <option value="en">English</option>
            <option value="ta">Tamil</option>
            <option value="te">తెలుగు</option>
            <option value="kn">ಕನ್ನಡ</option>
            <option value="hi">हिन्दी</option>
          </select>
        </div>
      </header>

      <main>
        <section class="hero">
          <div>
            <p class="eyebrow" id="welcomeSmall">FARMER DASHBOARD</p>
            <h1 id="welcomeTitle">Good morning, Farmer</h1>
            <p id="welcomeText">Your farming information, tasks and support in one place.</p>
          </div>
        </section>

        <section class="farm-summary">
          <div><span id="dashCropLabel">Main Crop</span><strong id="cropValue">Paddy</strong></div>
          <div><span id="stageLabel">Crop Stage</span><strong>Vegetative</strong></div>
          <div><span id="dashLandLabel">Land</span><strong id="landValue">2 acres</strong></div>
          <div><span id="irrigationLabel">Irrigation</span><strong id="irrigationValue">Available</strong></div>
        </section>

        <section class="dashboard-grid">
          <article class="card large" onclick="openExtraPage('todayPage'); renderTodayPage()" style="cursor:pointer">
            <div class="card-head">
              <div>
                <p class="card-kicker">TODAY</p>
                <h2 id="todayTitle">Today's Farm Update</h2>
              </div>
              <span class="status">Updated</span>
            </div>
            <div class="update-box">
              <h3 id="taskTitle">Farm Task</h3>
              <p id="taskText">Check irrigation conditions and observe the crop for signs of stress.</p>
            </div>
            <div class="mini-grid">
              <div><span id="weatherLabel">Weather</span><b>Rain possible after 3 PM</b></div>
              <div><span id="marketLabel">Market</span><b>Paddy ₹2,340 / quintal</b></div>
            </div>
          </article>

          <article class="card">
            <p class="card-kicker">MARKET</p><h2>MarketMate</h2>
            <p id="marketDesc">Compare crop market information and make a better selling decision.</p>
            <button class="primary-btn" onclick="openDetailPage('market')" id="marketBtn">View Market</button>
          </article>

          <article class="card">
            <p class="card-kicker">SCHEMES</p><h2>SchemeFinder</h2>
            <p id="schemeDesc">See government schemes that may match your farmer profile.</p>
            <button class="primary-btn" onclick="openDetailPage('scheme')" id="schemeBtn">Find Schemes</button>
          </article>

          <article class="card">
            <p class="card-kicker">LABOUR</p><h2>LabourLink</h2>
            <p id="labourDesc">Find available agricultural workers for important farm periods.</p>
            <button class="primary-btn" onclick="openDetailPage('labour')" id="labourBtn">View Labour</button>
          </article>

          <article class="card">
            <p class="card-kicker">CALENDAR</p><h2 id="calendarCardTitle">Smart Calendar</h2>
            <p id="calendarDesc">Plan farming tasks and reminders month by month.</p>
            <button class="primary-btn" onclick="openExtraPage('calendarPage'); renderFullCalendar()" id="calendarBtn">Open Calendar</button>
          </article>

          <article class="card voice-card" onclick="openExtraPage('voicePage')" style="cursor:pointer">
            <p class="card-kicker">VOICE</p><h2 id="voiceTitle">Voice Assistant</h2>
            <p id="voiceDesc">Ask your farming question in English, Tamil, Telugu or Kannada.</p>
            <div class="voice-controls" onclick="event.stopPropagation()">
              <select id="voiceLanguage"\>
                <option value="en-IN">English</option>
                <option value="ta-IN">Tamil</option>
                <option value="te-IN">తెలుగు</option>
                <option value="kn-IN">ಕನ್ನಡ</option>
              </select>
              <button class="voice-btn" onclick="event.stopPropagation(); openExtraPage('voicePage')" id="voiceBtn">Open Voice Assistant</button>
            </div>
            <textarea id="voiceQuestion" rows="2" placeholder="Your spoken question will appear here..."></textarea>
            <div id="voiceResult" class="voice-result"></div>
          </article>

          <article class="card">
            <p class="card-kicker">BUYER / SELLER</p><h2>Marketplace</h2>
            <p id="marketplaceDesc">A place for farmers and buyers to connect.</p>
            <button class="primary-btn" onclick="openDetailPage('marketplace')" id="marketplaceBtn">Open Marketplace</button>
          </article>
        </section>

        <section class="calendar-panel hidden" id="calendarPanel">
          <div class="calendar-head">
            <div><p class="card-kicker">FARM PLAN</p><h2 id="calendarTitle">Smart Farming Calendar</h2></div>
            <div class="calendar-nav">
              <button onclick="changeMonth(-1)">‹</button>
              <strong id="monthTitle"></strong>
              <button onclick="changeMonth(1)">›</button>
            </div>
          </div>
          <div class="weekdays" id="weekdays"></div>
          <div class="calendar-grid" id="calendarGrid"></div>
          <div class="task-list"><h3 id="tasksTitle">Suggested Tasks</h3><ul id="taskList"></ul></div>
        </section>
      </main>

      <footer>
        <span>3-day free trial</span><span>•</span><span>₹100/month after trial</span>
      </footer>
    </section>

    <div class="modal hidden" id="demoModal">
      <div class="modal-box">
        <button class="close" onclick="closeModal()">×</button>
        <h2 id="modalTitle">Demo</h2><p id="modalText"></p>
        <button class="primary-btn" onclick="closeModal()">Close</button>
      </div>
    </div>
  </div>

<script>
const T = {
en:{regEyebrow:"GET STARTED",regTitle:"Farmer Registration",regIntro:"Enter your details once to create your personalized farming dashboard.",
nameLabel:"Farmer Name",mobileLabel:"Mobile Number",villageLabel:"Village",districtLabel:"District",cropLabel:"Main Crop",
landLabel:"Land Size (acres)",soilLabel:"Soil Type",waterLabel:"Irrigation",rationLabel:"Ration Card Details",aadhaarLabel:"Aadhaar Details",
securityNote:"",
planTitle:"Menpulam Subscription",trialText:"First 3 days FREE",afterTrial:"After the free trial, continue with the monthly plan.",
registerButton:"Register & Start 3-Day Free Trial",successTitle:"Registration Successful",successTrial:"Your 3-day free trial starts now.",
continueButton:"Continue to Dashboard",editProfileBtn:"Edit Details",welcomeSmall:"FARMER DASHBOARD",welcomeTitle:"Good morning, Farmer",
welcomeText:"Your farming information, tasks and support in one place.",dashCropLabel:"Main Crop",stageLabel:"Crop Stage",dashLandLabel:"Land",
irrigationLabel:"Irrigation",todayTitle:"Today's Farm Update",taskTitle:"Farm Task",taskText:"Check irrigation conditions and observe the crop for signs of stress.",
weatherLabel:"Weather",marketLabel:"Market",marketDesc:"Compare crop market information and make a better selling decision.",marketBtn:"View Market",
schemeDesc:"See government schemes that may match your farmer profile.",schemeBtn:"Find Schemes",labourDesc:"Find available agricultural workers for important farm periods.",
labourBtn:"View Labour",calendarCardTitle:"Smart Calendar",calendarDesc:"Plan farming tasks and reminders month by month.",calendarBtn:"Open Calendar",
voiceTitle:"Voice Assistant",voiceDesc:"Ask your farming question in English, Tamil, Telugu or Kannada.",voiceBtn:"Start Voice",
marketplaceDesc:"A place for farmers and buyers to connect.",marketplaceBtn:"Open Marketplace",calendarTitle:"Smart Farming Calendar",tasksTitle:"Suggested Tasks"
},
ta:{regEyebrow:"Get Started",regTitle:"Farmer Register",regIntro:"        .",
nameLabel:"Farmer ",mobileLabel:" ",villageLabel:"",districtLabel:"",cropLabel:" Crop",landLabel:"  ()",
soilLabel:" ",waterLabel:"",rationLabel:"  Details",aadhaarLabel:" Details",
securityNote:" :        .  4      .",
planTitle:"Menpulam ",trialText:" 3  ",afterTrial:"     .",
registerButton:"Register  3    Get Started",successTitle:"Register ",successTrial:" 3     .",
continueButton:" ",editProfileBtn:" ",welcomeSmall:"Farmer Home",welcomeTitle:" , Farmer",
welcomeText:"  ,   Help  .",dashCropLabel:" Crop",stageLabel:"Crop ",dashLandLabel:"Land",irrigationLabel:"",
todayTitle:"  ",taskTitle:" ",taskText:"    .",weatherLabel:"",marketLabel:"Market",
marketDesc:"Crop Market      .",marketBtn:"Market ",schemeDesc:"   Government  .",
schemeBtn:" ",labourDesc:"     .",labourBtn:" ",
calendarCardTitle:" Calendar",calendarDesc:"    .",calendarBtn:" ",
voiceTitle:"Voice Assistant",voiceDesc:"English, Tamil,     Question Ask.",voiceBtn:" ",
marketplaceDesc:"Farmer Buyer  .",marketplaceBtn:"Market ",calendarTitle:"  Calendar",tasksTitle:" "
},
te:{regEyebrow:"ప్రారంభించండి",regTitle:"రైతు నమోదు",regIntro:"మీ వ్యక్తిగత వ్యవసాయ డ్యాష్‌బోర్డ్ కోసం మీ వివరాలను నమోదు చేయండి.",nameLabel:"రైతు పేరు",mobileLabel:"మొబైల్ నంబర్",
villageLabel:"గ్రామం",districtLabel:"జిల్లా",cropLabel:"ప్రధాన పంట",landLabel:"భూమి పరిమాణం (ఎకరాలు)",soilLabel:"నేల రకం",waterLabel:"నీటిపారుదల",
rationLabel:"రేషన్ కార్డు వివరాలు",aadhaarLabel:"ఆధార్ వివరాలు",securityNote:"ప్రోటోటైప్ భద్రత: పూర్తి ఆధార్ నంబర్ లేదా నిజమైన గుర్తింపు పత్రాలను నమోదు చేయవద్దు. చివరి 4 అంకెలు లేదా డమ్మీ వివరాలను మాత్రమే ఉపయోగించండి.",
planTitle:"మెులం సబ్‌స్క్రిప్షన్",trialText:"మొదటి 3 రోజులు ఉచితం",afterTrial:"ఉచిత పరీక్ష తర్వాత నెలవారీ ప్లాన్ కొనసాగించవచ్చు.",registerButton:"నమోదు చేసి 3 రోజుల ఉచిత పరీక్ష ప్రారంభించండి",
successTitle:"నమోదు విజయవంతమైంది",successTrial:"మీ 3 రోజుల ఉచిత పరీక్ష ఇప్పుడు ప్రారంభమైంది.",continueButton:"డ్యాష్‌బోర్డ్‌కు వెళ్లండి",editProfileBtn:"వివరాలు మార్చండి",
welcomeSmall:"రైతు డ్యాష్‌బోర్డ్",welcomeTitle:"శుభోదయం, రైతు",welcomeText:"మీ వ్యవసాయ సమాచారం, పనులు మరియు సహాయం ఒకే చోట.",dashCropLabel:"ప్రధాన పంట",stageLabel:"పంట దశ",dashLandLabel:"భూమి",irrigationLabel:"నీటిపారుదల",
todayTitle:"ఈ రోజు వ్యవసాయ సమాచారం",taskTitle:"ఈ రోజు పని",taskText:"నీటిపారుదల పరిస్థితిని తనిఖీ చేసి పంటను గమనించండి.",weatherLabel:"వాతావరణం",marketLabel:"మార్కెట్",
marketDesc:"పంట మార్కెట్ సమాచారాన్ని పోల్చి మంచి విక్రయ నిర్ణయం తీసుకోండి.",marketBtn:"మార్కెట్ చూడండి",schemeDesc:"మీ రైతు వివరాలకు సరిపడే ప్రభుత్వ పథకాలను చూడండి.",schemeBtn:"పథకాలు చూడండి",
labourDesc:"ముఖ్యమైన వ్యవసాయ సమయంలో అందుబాటులో ఉన్న కూలీలను కనుగొనండి.",labourBtn:"కూలీలను చూడండి",calendarCardTitle:"స్మార్ట్ క్యాలెండర్",calendarDesc:"నెలవారీ వ్యవసాయ పనులు మరియు రిమైండర్లను ప్లాన్ చేయండి.",
calendarBtn:"క్యాలెండర్ తెరవండి",voiceTitle:"వాయిస్ అసిస్టెంట్",voiceDesc:"ఇంగ్లీష్, తమిళం, తెలుగు లేదా కన్నడలో వ్యవసాయ ప్రశ్న అడగండి.",voiceBtn:"వాయిస్ ప్రారంభించండి",
marketplaceDesc:"రైతులు మరియు కొనుగోలుదారులు కలిసే స్థలం.",marketplaceBtn:"మార్కెట్‌ప్లేస్ తెరవండి",calendarTitle:"స్మార్ట్ వ్యవసాయ క్యాలెండర్",tasksTitle:"సూచించిన పనులు"
},
kn:{regEyebrow:"ಪ್ರಾರಂಭಿಸಿ",regTitle:"ರೈತ ನೋಂದಣಿ",regIntro:"ನಿಮ್ಮ ವೈಯಕ್ತಿಕ ಕೃಷಿ ಡ್ಯಾಶ್‌ಬೋರ್ಡ್‌ಗಾಗಿ ನಿಮ್ಮ ವಿವರಗಳನ್ನು ನಮೂದಿಸಿ.",nameLabel:"ರೈತರ ಹೆಸರು",mobileLabel:"ಮೊಬೈಲ್ ಸಂಖ್ಯೆ",
villageLabel:"ಗ್ರಾಮ",districtLabel:"ಜಿಲ್ಲೆ",cropLabel:"ಮುಖ್ಯ ಬೆಳೆ",landLabel:"ಜಮೀನು (ಎಕರೆ)",soilLabel:"ಮಣ್ಣಿನ ಪ್ರಕಾರ",waterLabel:"ನೀರಾವರಿ",
rationLabel:"ರೇಷನ್ ಕಾರ್ಡ್ ವಿವರಗಳು",aadhaarLabel:"ಆಧಾರ್ ವಿವರಗಳು",securityNote:"ಪ್ರೋಟೋಟೈಪ್ ಸುರಕ್ಷತೆ: ಪೂರ್ಣ ಆಧಾರ್ ಸಂಖ್ಯೆ ಅಥವಾ ನಿಜವಾದ ಗುರುತಿನ ದಾಖಲೆಗಳನ್ನು ನಮೂದಿಸಬೇಡಿ. ಕೊನೆಯ 4 ಅಂಕೆಗಳು ಅಥವಾ ಡಮ್ಮಿ ವಿವರಗಳನ್ನು ಮಾತ್ರ ಬಳಸಿ.",
planTitle:"ಮೆಂ ಚಂದಾದಾರಿಕೆ",trialText:"ಮೊದಲ 3 ದಿನಗಳು ಉಚಿತ",afterTrial:"ಉಚಿತ ಪ್ರಯೋಗದ ನಂತರ ಮಾಸಿಕ ಯೋಜನೆಯನ್ನು ಮುಂದುವರಿಸಬಹುದು.",registerButton:"ನೋಂದಣಿ ಮಾಡಿ 3 ದಿನಗಳ ಉಚಿತ ಪ್ರಯೋಗ ಪ್ರಾರಂಭಿಸಿ",
successTitle:"ನೋಂದಣಿ ಯಶಸ್ವಿಯಾಗಿದೆ",successTrial:"ನಿಮ್ಮ 3 ದಿನಗಳ ಉಚಿತ ಪ್ರಯೋಗ ಈಗ ಪ್ರಾರಂಭವಾಗಿದೆ.",continueButton:"ಡ್ಯಾಶ್‌ಬೋರ್ಡ್ ತೆರೆಯಿರಿ",editProfileBtn:"ವಿವರ ಬದಲಿಸಿ",
welcomeSmall:"ರೈತ ಡ್ಯಾಶ್‌ಬೋರ್ಡ್",welcomeTitle:"ಶುಭೋದಯ, ರೈತ",welcomeText:"ನಿಮ್ಮ ಕೃಷಿ ಮಾಹಿತಿ, ಕೆಲಸಗಳು ಮತ್ತು ಸಹಾಯ ಒಂದೇ ಸ್ಥಳದಲ್ಲಿ.",dashCropLabel:"ಮುಖ್ಯ ಬೆಳೆ",stageLabel:"ಬೆಳೆ ಹಂತ",dashLandLabel:"ಭೂಮಿ",irrigationLabel:"ನೀರಾವರಿ",
todayTitle:"ಇಂದಿನ ಕೃಷಿ ಮಾಹಿತಿ",taskTitle:"ಇಂದಿನ ಕೆಲಸ",taskText:"ನೀರಾವರಿ ಪರಿಸ್ಥಿತಿಯನ್ನು ಪರಿಶೀಲಿಸಿ ಮತ್ತು ಬೆಳೆಯನ್ನು ಗಮನಿಸಿ.",weatherLabel:"ಹವಾಮಾನ",marketLabel:"ಮಾರುಕಟ್ಟೆ",
marketDesc:"ಬೆಳೆ ಮಾರುಕಟ್ಟೆ ಮಾಹಿತಿಯನ್ನು ಹೋಲಿಸಿ ಉತ್ತಮ ಮಾರಾಟ ನಿರ್ಧಾರ ತೆಗೆದುಕೊಳ್ಳಿ.",marketBtn:"ಮಾರುಕಟ್ಟೆ ನೋಡಿ",schemeDesc:"ನಿಮ್ಮ ರೈತ ವಿವರಗಳಿಗೆ ಹೊಂದುವ ಸರ್ಕಾರಿ ಯೋಜನೆಗಳನ್ನು ನೋಡಿ.",schemeBtn:"ಯೋಜನೆಗಳನ್ನು ನೋಡಿ",
labourDesc:"ಮುಖ್ಯ ಕೃಷಿ ಸಮಯದಲ್ಲಿ ಲಭ್ಯವಿರುವ ಕಾರ್ಮಿಕರನ್ನು ಹುಡುಕಿ.",labourBtn:"ಕಾರ್ಮಿಕರನ್ನು ನೋಡಿ",calendarCardTitle:"ಸ್ಮಾರ್ಟ್ ಕ್ಯಾಲೆಂಡರ್",calendarDesc:"ತಿಂಗಳ ಕೃಷಿ ಕೆಲಸಗಳು ಮತ್ತು ನೆನಪುಗಳನ್ನು ಯೋಜಿಸಿ.",calendarBtn:"ಕ್ಯಾಲೆಂಡರ್ ತೆರೆಯಿರಿ",
voiceTitle:"ಧ್ವನಿ ಸಹಾಯಕ",voiceDesc:"ಇಂಗ್ಲಿಷ್, ತಮಿಳು, ತೆಲುಗು ಅಥವಾ ಕನ್ನಡದಲ್ಲಿ ಕೃಷಿ ಪ್ರಶ್ನೆ ಕೇಳಿ.",voiceBtn:"ಧ್ವನಿ ಪ್ರಾರಂಭಿಸಿ",marketplaceDesc:"ರೈತರು ಮತ್ತು ಖರೀದಿದಾರರು ಸಂಪರ್ಕಿಸುವ ಸ್ಥಳ.",marketplaceBtn:"ಮಾರುಕಟ್ಟೆ ತೆರೆಯಿರಿ",
calendarTitle:"ಸ್ಮಾರ್ಟ್ ಕೃಷಿ ಕ್ಯಾಲೆಂಡರ್",tasksTitle:"ಸೂಚಿಸಲಾದ ಕೆಲಸಗಳು"
},
hi:{regEyebrow:"शुरू करें",regTitle:"किसान पंजीकरण",regIntro:"अपना व्यक्तिगत खेती डैशबोर्ड बनाने के लिए अपनी जानकारी दर्ज करें.",nameLabel:"किसान का नाम",mobileLabel:"मोबाइल नंबर",
villageLabel:"गाँव",districtLabel:"जिला",cropLabel:"मुख्य फसल",landLabel:"भूमि का आकार (एकड़)",soilLabel:"मिट्टी का प्रकार",waterLabel:"सिंचाई",
rationLabel:"राशन कार्ड विवरण",aadhaarLabel:"आधार विवरण",securityNote:"प्रोटोटाइप सुरक्षा: पूरा आधार नंबर या असली पहचान दस्तावेज दर्ज न करें। केवल अंतिम 4 अंक या डेमो विवरण का उपयोग करें.",
planTitle:"मेन्पुलम सदस्यता",trialText:"पहले 3 दिन मुफ्त",afterTrial:"मुफ्त ट्रायल के बाद मासिक योजना जारी रख सकते हैं.",registerButton:"पंजीकरण करें और 3 दिन का मुफ्त ट्रायल शुरू करें",
successTitle:"पंजीकरण सफल",successTrial:"आपका 3 दिन का मुफ्त ट्रायल अभी शुरू हो गया है.",continueButton:"डैशबोर्ड खोलें",editProfileBtn:"विवरण बदलें",
welcomeSmall:"किसान डैशबोर्ड",welcomeTitle:"सुप्रभात, किसान",welcomeText:"आपकी खेती की जानकारी, काम और सहायता एक ही जगह।",dashCropLabel:"मुख्य फसल",stageLabel:"फसल अवस्था",dashLandLabel:"भूमि",irrigationLabel:"सिंचाई",
todayTitle:"आज की खेती की जानकारी",taskTitle:"आज का काम",taskText:"सिंचाई की स्थिति जांचें और फसल में बदलाव देखें.",weatherLabel:"मौसम",marketLabel:"बाजार",
marketDesc:"फसल बाजार की जानकारी की तुलना करके बेहतर बिक्री निर्णय लें.",marketBtn:"बाजार देखें",schemeDesc:"आपकी किसान प्रोफ़ाइल से मेल खाने वाली सरकारी योजनाएं देखें.",schemeBtn:"योजनाएं देखें",
labourDesc:"महत्वपूर्ण खेती के समय उपलब्ध कृषि श्रमिक खोजें.",labourBtn:"श्रमिक देखें",calendarCardTitle:"स्मार्ट कैलेंडर",calendarDesc:"महीने के अनुसार खेती के काम और रिमाइंडर की योजना बनाएं.",calendarBtn:"कैलेंडर खोलें",
voiceTitle:"वॉइस असिस्टेंट",voiceDesc:"अंग्रेज़ी, तमिल, तेलुगु या कन्नड़ में खेती का सवाल पूछें.",voiceBtn:"वॉइस शुरू करें",marketplaceDesc:"किसानों और खरीदारों को जोड़ने की जगह.",marketplaceBtn:"मार्केटप्लेस खोलें",
calendarTitle:"स्मार्ट खेती कैलेंडर",tasksTitle:"सुझाए गए काम"
}
};

const ids = Object.keys(T.en);
function setLanguage(lang) {
  const t=T[lang]||T.en;
  ids.forEach(id=>{
    const el=document.getElementById(id);
    if(el && typeof t[id]==="string") el.textContent=t[id];
  });
  document.documentElement.lang=lang;
  document.getElementById("regLanguageSelect").value=lang;
  document.getElementById("dashboardLanguageSelect").value=lang;
  localStorage.setItem("menpulamLanguage",lang);
  renderCalendar();
}
document.getElementById("regLanguageSelect").addEventListener("change",e=>setLanguage(e.target.value));
document.getElementById("dashboardLanguageSelect").addEventListener("change",e=>setLanguage(e.target.value));

document.getElementById("farmerForm").addEventListener("submit", e=>{
  e.preventDefault();
  const name=document.getElementById("name").value.trim();
  const crop=document.getElementById("crop").value;
  const village=document.getElementById("village").value.trim();
  const land=document.getElementById("land").value;
  const district=document.getElementById("district").value.trim();
  const water=document.getElementById("water").value;
  document.getElementById("successMessage").textContent =
    `Welcome ${name}. Your ${crop} farm in ${village}, ${district} has been registered.`;
  document.getElementById("cropValue").textContent=crop;
  document.getElementById("landValue").textContent=land+" acres";
  document.getElementById("irrigationValue").textContent=water;
  document.getElementById("welcomeTitle").textContent =
    (T[document.documentElement.lang]||T.en).welcomeTitle.replace("Farmer",name).replace("Farmer",name).replace("రైతు",name).replace("ರೈತ",name).replace("किसान",name);
  document.getElementById("registrationSuccess").classList.remove("hidden");
  document.getElementById("farmerForm").classList.add("hidden");
  localStorage.setItem("menpulamFarmer",JSON.stringify({name,crop,village,land,district,water}));
});

document.getElementById("continueButton").addEventListener("click",()=>{
  document.getElementById("registrationPage").classList.add("hidden");
  document.getElementById("dashboardPage").classList.remove("hidden");
  window.scrollTo({top:0,behavior:"smooth"});
  renderCalendar();
});

function showRegistration(){
  document.getElementById("dashboardPage").classList.add("hidden");
  document.getElementById("registrationPage").classList.remove("hidden");
  document.getElementById("farmerForm").classList.remove("hidden");
  document.getElementById("registrationSuccess").classList.add("hidden");
  window.scrollTo({top:0,behavior:"smooth"});
}

let currentMonth=new Date().getMonth(), currentYear=new Date().getFullYear();
function openCalendar(){
  document.getElementById("calendarPanel").classList.remove("hidden");
  renderCalendar();
  document.getElementById("calendarPanel").scrollIntoView({behavior:"smooth"});
}
function changeMonth(delta){
  currentMonth+=delta;
  if(currentMonth<0){currentMonth=11;currentYear--}
  if(currentMonth>11){currentMonth=0;currentYear++}
  renderCalendar();
}
function renderCalendar(){
  const grid=document.getElementById("calendarGrid"), weekdays=document.getElementById("weekdays"), title=document.getElementById("monthTitle");
  if(!grid)return;
  const lang=document.documentElement.lang||"en";
  const locale={en:"en-IN",ta:"ta-IN",te:"te-IN",kn:"kn-IN",hi:"hi-IN"}[lang]||"en-IN";
  const first=new Date(currentYear,currentMonth,1).getDay(), days=new Date(currentYear,currentMonth+1,0).getDate();
  title.textContent=new Date(currentYear,currentMonth,1).toLocaleDateString(locale,{month:"long",year:"numeric"});
  weekdays.innerHTML=[0,1,2,3,4,5,6].map(i=>new Date(2024,0,7+i).toLocaleDateString(locale,{weekday:"short"})).map(x=>`<span>${x}</span>`).join("");
  grid.innerHTML="";
  for(let i=0;i<first;i++)grid.appendChild(document.createElement("div"));
  for(let day=1;day<=days;day++){
    const b=document.createElement("button"); b.className="day"; b.textContent=day;
    const now=new Date();
    if(day===now.getDate()&&currentMonth===now.getMonth()&&currentYear===now.getFullYear())b.classList.add("today");
    if([5,10,15,20,25].includes(day))b.classList.add("task-day");
    b.onclick=()=>alert("Farm reminder for "+day+" "+title.textContent);
    grid.appendChild(b);
  }
  document.getElementById("taskList").innerHTML=[
    "Check irrigation and soil condition","Review paddy market prices","Arrange harvesting labour","Review eligible government schemes"
  ].map(x=>`<li>${x}</li>`).join("");
}

function startVoice(){
  const SR=window.SpeechRecognition||window.webkitSpeechRecognition, result=document.getElementById("voiceResult");
  if(!SR){result.textContent="Voice input is not supported in this browser. Try Google Chrome or Microsoft Edge.";return;}
  const r=new SR(); r.lang=document.getElementById("voiceLanguage").value;r.interimResults=false;r.maxAlternatives=1;
  result.textContent="Listening...";
  r.onresult=e=>{document.getElementById("voiceQuestion").value=e.results[0][0].transcript;result.textContent="Question received. Sample answer: For paddy, check irrigation regularly and review the latest market price before selling.";};
  r.onerror=()=>result.textContent="Voice input could not be completed. Please try again.";
  r.start();
}
function showDemo(type){
  const title={market:"MarketMate",scheme:"SchemeFinder",labour:"LabourLink",marketplace:"Marketplace"}[type];
  const text={
    market:"Paddy: ₹2,340 per quintal at Erode market. Nearby: Gobichettipalayam ₹2,310; Bhavani ₹2,325. Best recent price: ₹2,365.",
    scheme:"3 possible schemes found: PM-KISAN, crop insurance support, and agricultural machinery assistance. Tap to view eligibility details.",
    labour:"8 workers available near Perundurai. Harvesting: 5 workers available tomorrow. Estimated daily rate: ₹650.",
    marketplace:"4 buyers are currently looking for paddy near Erode. Sample listing: 20 quintals of paddy available from Perundurai."
  }[type];
  document.getElementById("modalTitle").textContent=title;document.getElementById("modalText").textContent=text;
  document.getElementById("demoModal").classList.remove("hidden");
}
function closeModal(){document.getElementById("demoModal").classList.add("hidden")}

const saved=localStorage.getItem("menpulamLanguage")||"en";
setLanguage(saved);
</script>

<div id="detailPage" class="detail-page" style="display:none;">
  <div class="detail-header">
    <button class="back-btn" onclick="closeDetailPage()">Back to Dashboard</button>
    <h2 id="detailTitle">Details</h2>
    <p id="detailSubtitle"></p>
  </div>
  <div id="detailContent" class="detail-content"></div>
</div>


<script>
function openDetailPage(type){
  const dash = document.querySelector('.dashboard') || document.querySelector('#dashboard');
  if(dash) dash.style.display='none';
  document.getElementById('detailPage').style.display='block';

  const title=document.getElementById('detailTitle');
  const subtitle=document.getElementById('detailSubtitle');
  const content=document.getElementById('detailContent');

  if(type==='market'){
    title.textContent='MarketMate';
    subtitle.textContent='Compare current market information for your crop.';
    content.innerHTML=`
      <div class="data-card">
        <h3>Current Crop</h3>
        <div class="data-grid">
          <div class="data-item"><div class="data-label">Crop</div><div class="data-value">Paddy</div></div>
          <div class="data-item"><div class="data-label">Best recent price</div><div class="data-value">₹2,365 / quintal</div></div>
          <div class="data-item"><div class="data-label">Main market</div><div class="data-value">Erode</div></div>
          <div class="data-item"><div class="data-label">Last updated</div><div class="data-value">Today</div></div>
        </div>
      </div>
      <div class="data-card">
        <h3>Market Comparison</h3>
        <table class="data-table">
          <tr><th>Market</th><th>Current Price</th><th>Comparison</th></tr>
          <tr><td>Erode</td><td>₹2,340</td><td><span class="status">Reference</span></td></tr>
          <tr><td>Gobichettipalayam</td><td>₹2,310</td><td><span class="status">₹30 lower</span></td></tr>
          <tr><td>Bhavani</td><td>₹2,325</td><td><span class="status">₹15 lower</span></td></tr>
        </table>
      </div>
      <div class="data-card">
        <h3>Suggested Check</h3>
        <p>Review the latest price before deciding where and when to sell.</p>
      </div>`;
  } else if(type==='scheme'){
    title.textContent='SchemeFinder';
    subtitle.textContent='Government schemes that may be relevant to your farm.';
    content.innerHTML=`
      <div class="data-card">
        <h3>Possible Schemes</h3>
        <div class="data-grid">
          <div class="data-item"><div class="data-label">Scheme</div><div class="data-value">PM-KISAN</div><p>Income support for eligible farmer families.</p><span class="status">Check eligibility</span></div>
          <div class="data-item"><div class="data-label">Scheme</div><div class="data-value">Crop Insurance Support</div><p>Insurance support for eligible crops and farmers.</p><span class="status">Check eligibility</span></div>
          <div class="data-item"><div class="data-label">Scheme</div><div class="data-value">Agricultural Machinery Assistance</div><p>Support related to eligible agricultural machinery.</p><span class="status">Check eligibility</span></div>
        </div>
      </div>
      <div class="data-card">
        <h3>Farmer Profile Used</h3>
        <div class="data-grid">
          <div class="data-item"><div class="data-label">Crop</div><div class="data-value">Paddy</div></div>
          <div class="data-item"><div class="data-label">Land</div><div class="data-value">2.5 acres</div></div>
          <div class="data-item"><div class="data-label">District</div><div class="data-value">Erode</div></div>
          <div class="data-item"><div class="data-label">Irrigation</div><div class="data-value">Well</div></div>
        </div>
      </div>`;
  } else if(type==='labour'){
    title.textContent='LabourLink';
    subtitle.textContent='Available agricultural workers and work details.';
    content.innerHTML=`
      <div class="data-card">
        <h3>Availability Near Your Farm</h3>
        <div class="data-grid">
          <div class="data-item"><div class="data-label">Workers available</div><div class="data-value">8 workers</div></div>
          <div class="data-item"><div class="data-label">Harvesting tomorrow</div><div class="data-value">5 workers</div></div>
          <div class="data-item"><div class="data-label">Estimated daily rate</div><div class="data-value">₹650</div></div>
          <div class="data-item"><div class="data-label">Area</div><div class="data-value">Perundurai</div></div>
        </div>
      </div>
      <div class="data-card">
        <h3>Worker Availability</h3>
        <table class="data-table">
          <tr><th>Work Type</th><th>Workers</th><th>Availability</th></tr>
          <tr><td>Harvesting</td><td>5</td><td><span class="status">Tomorrow</span></td></tr>
          <tr><td>General farm work</td><td>3</td><td><span class="status">Available</span></td></tr>
        </table>
      </div>`;
  } else if(type==='marketplace'){
    title.textContent='Buyer & Seller Marketplace';
    subtitle.textContent='Connect farmers with nearby buyers and sample produce listings.';
    content.innerHTML=`
      <div class="data-card">
        <h3>Buyer Demand Near You</h3>
        <div class="data-grid">
          <div class="data-item"><div class="data-label">Buyers looking for paddy</div><div class="data-value">4 buyers</div></div>
          <div class="data-item"><div class="data-label">Area</div><div class="data-value">Erode</div></div>
          <div class="data-item"><div class="data-label">Sample demand</div><div class="data-value">20 quintals</div></div>
          <div class="data-item"><div class="data-label">Listing status</div><div class="data-value">Active</div></div>
        </div>
      </div>
      <div class="data-card">
        <h3>Sample Listings</h3>
        <table class="data-table">
          <tr><th>Listing</th><th>Quantity</th><th>Location</th></tr>
          <tr><td>Paddy</td><td>20 quintals</td><td>Perundurai</td></tr>
          <tr><td>Paddy</td><td>10 quintals</td><td>Erode</td></tr>
        </table>
      </div>
      <div class="data-card">
        <h3>How It Helps</h3>
        <p>Farmers can view buyer demand and list their produce in one place. This is sample prototype data, not a live marketplace.</p>
      </div>`;
  }
}
function closeDetailPage(){
  document.getElementById('detailPage').style.display='none';
  const dash = document.querySelector('.dashboard') || document.querySelector('#dashboard');
  if(dash) dash.style.display='';
}
</script>

<div id="voicePage" class="detail-page" style="display:none"><div class="detail-header"><button class="back-btn" onclick="closeExtraPage('voicePage')">Back to Dashboard</button><h2>Voice Assistant</h2><p>Ask a farming question using English or Tamil voice input.</p></div><div class="voice-box"><h3>Voice Language</h3><div class="voice-lang-row"><button class="voice-lang active" id="voiceEnglishBtn" onclick="setVoiceLanguage('en-IN')">English</button><button class="voice-lang" id="voiceTamilBtn" onclick="setVoiceLanguage('ta-IN')">Tamil</button></div><button class="action-btn" onclick="startMenpulamVoice()">Start Voice Input</button><div id="voiceStatus" style="margin-top:12px;color:#667085">Ready for your question.</div><div class="voice-answer" id="voiceAnswer">Example: "What is today's market price for paddy?"</div></div></div><div id="contactPage" class="detail-page" style="display:none"><div class="detail-header"><button class="back-btn" onclick="closeExtraPage('contactPage')">Back to Dashboard</button><h2>Government Agriculture Contacts</h2><p>Official agriculture contacts for Erode district.</p></div><div class="data-card"><div class="contact-grid"><div class="contact-card"><h4>Joint Director of Agriculture, Erode</h4><p>Vidhyanagar, Thindal, Erode</p><a href="tel:9894730543">Call 98947 30543</a></div><div class="contact-card"><h4>Agriculture Officer, Government Schemes</h4><p>Vidhyanagar, Thindal, Erode</p><a href="tel:8940141976">Call 89401 41976</a></div><div class="contact-card"><h4>Assistant Director of Agriculture, Perundurai</h4><p>Integrated Agriculture Extension Centre, Perundurai</p><a href="tel:9486012682">Call 94860 12682</a></div><div class="contact-card"><h4>District Agriculture Office</h4><p>General office line</p><a href="tel:04242339101">Call 0424 233 9101</a></div></div></div></div><div id="todayPage" class="detail-page" style="display:none"><div class="detail-header"><button class="back-btn" onclick="closeExtraPage('todayPage')">Back to Dashboard</button><h2>Today's Farm Update</h2><p>Your personalized information for today.</p></div><div id="todayContent" class="detail-content"></div></div>
<div id="calendarPage" class="detail-page" style="display:none"><div class="detail-header"><button class="back-btn" onclick="closeExtraPage('calendarPage')">Back to Dashboard</button><h2>Smart Farming Calendar</h2><p>Plan and track important farming tasks.</p></div><div class="data-card"><div class="calendar-head"><h3 id="fullMonthTitle">Calendar</h3><div class="calendar-nav"><button onclick="changeFullMonth(-1)">‹</button><button onclick="changeFullMonth(1)">›</button></div></div><div class="weekdays" id="fullWeekdays"></div><div class="calendar-grid" id="fullCalendarGrid"></div></div><div class="data-card"><h3>Farm Tasks</h3><div class="data-grid"><div class="data-item"><div class="data-label">Today</div><div class="data-value">Check irrigation</div></div><div class="data-item"><div class="data-label">Tomorrow</div><div class="data-value">Inspect crop growth</div></div><div class="data-item"><div class="data-label">This week</div><div class="data-value">Review market prices</div></div></div></div></div>
<div class="help-panel"><div class="help-logo">M</div><div><strong>Need Help?</strong><a href="tel:04242339101">Agriculture Help: 0424 233 9101</a></div></div><script>let menpulamVoiceLang='en-IN';function openExtraPage(id){const d=document.querySelector('.dashboard')||document.querySelector('#dashboard');if(d)d.style.display='none';['detailPage','voicePage','contactPage'].forEach(x=>{const e=document.getElementById(x);if(e)e.style.display='none'});document.getElementById(id).style.display='block'}function closeExtraPage(id){document.getElementById(id).style.display='none';const d=document.querySelector('.dashboard')||document.querySelector('#dashboard');if(d)d.style.display=''}function setVoiceLanguage(l){menpulamVoiceLang=l;document.getElementById('voiceEnglishBtn').classList.toggle('active',l==='en-IN');document.getElementById('voiceTamilBtn').classList.toggle('active',l==='ta-IN')}function startMenpulamVoice(){const SR=window.SpeechRecognition||window.webkitSpeechRecognition,s=document.getElementById('voiceStatus'),a=document.getElementById('voiceAnswer');if(!SR){s.textContent='Voice input is not supported in this browser. Try Chrome or Edge.';return}const r=new SR();r.lang=menpulamVoiceLang;r.interimResults=false;r.maxAlternatives=1;s.textContent='Listening...';r.onresult=e=>{const q=e.results[0][0].transcript;a.innerHTML='<strong>You asked:</strong> '+q+'<br><br><strong>Menpulam:</strong> '+voiceReply(q);s.textContent='Voice question received.'};r.onerror=()=>s.textContent='Could not hear the question. Please try again.';r.start()}function voiceReply(q){const s=q.toLowerCase();if(s.includes('price')||s.includes('market')||s.includes('Price')||s.includes('Market'))return menpulamVoiceLang==='ta-IN'?'   Market  Price  ₹2,340.    Price .':'The sample paddy price at Erode market is ₹2,340 per quintal. Check the latest price before selling.';if(s.includes('scheme')||s.includes(''))return menpulamVoiceLang==='ta-IN'?'PM-KISAN, Crop      Help   .':'You can check PM-KISAN, crop insurance support, and agricultural machinery assistance.';if(s.includes('labour')||s.includes('worker')||s.includes('')||s.includes(''))return menpulamVoiceLang==='ta-IN'?' Nearby   8 Workers . Tomorrow  5 Workers .':'The sample data shows 8 workers near Perundurai, with 5 available for harvesting tomorrow.';return menpulamVoiceLang==='ta-IN'?'Crop, Market Price, Government Schemes  Workers  .':'You can ask about your crop, market prices, government schemes, or available workers.'}</script><style>
.detail-page{min-height:100vh;padding:32px 5%;background:#f7faf7}.detail-header{max-width:1100px;margin:0 auto 24px}.detail-content{max-width:1100px;margin:0 auto}.data-card{max-width:1100px;margin:18px auto;padding:28px;border-radius:20px;background:#fff;box-shadow:0 8px 28px rgba(0,0,0,.06)}.data-grid{gap:20px}.data-item{padding:22px;border-radius:16px}.data-table{width:100%;border-collapse:separate;border-spacing:0 8px}.data-table th,.data-table td{padding:16px;text-align:left}.feature-actions{display:flex;gap:12px;flex-wrap:wrap;margin-top:20px}.feature-actions button{padding:13px 18px;border-radius:10px;border:0;cursor:pointer}.interactive-row{cursor:pointer;transition:.2s}.interactive-row:hover{transform:translateY(-2px)}
</style>
<script>
let fullCalDate=new Date();
function dashboard(){return document.getElementById('dashboardPage')}
function hideAllPages(){['detailPage','voicePage','contactPage','todayPage','calendarPage'].forEach(id=>{let e=document.getElementById(id);if(e)e.style.display='none'});dashboard().style.display='block'}
function openExtraPage(id){dashboard().style.display='none';['detailPage','voicePage','contactPage','todayPage','calendarPage'].forEach(x=>{let e=document.getElementById(x);if(e)e.style.display='none'});let e=document.getElementById(id);if(e)e.style.display='block'}
function closeExtraPage(id){document.getElementById(id).style.display='none';dashboard().style.display='block'}
function closeDetailPage(){closeExtraPage('detailPage')}
function openDetailPage(type){openExtraPage('detailPage');let title=document.getElementById('detailTitle'),sub=document.getElementById('detailSubtitle'),content=document.getElementById('detailContent');
if(type==='market'){title.textContent='MarketMate';sub.textContent='Explore prices, compare markets and make a selling decision.';content.innerHTML=`<div class="data-card"><h3>Paddy Market Prices</h3><div class="data-grid"><div class="data-item interactive-row" onclick="alert('Erode selected')"><div class="data-label">Erode</div><div class="data-value">₹2,340 / quintal</div></div><div class="data-item interactive-row" onclick="alert('Gobichettipalayam selected')"><div class="data-label">Gobichettipalayam</div><div class="data-value">₹2,310 / quintal</div></div><div class="data-item interactive-row" onclick="alert('Bhavani selected')"><div class="data-label">Bhavani</div><div class="data-value">₹2,325 / quintal</div></div></div></div><div class="data-card"><h3>Market Actions</h3><div class="feature-actions"><button onclick="alert('Sample: latest price checked')">Refresh Prices</button><button onclick="alert('Sample: Erode market selected')">Choose Market</button><button onclick="alert('Sample: selling reminder created')">Set Selling Reminder</button></div></div>`}
else if(type==='scheme'){title.textContent='SchemeFinder';sub.textContent='Explore schemes and check what information may be needed.';content.innerHTML=`<div class="data-card"><h3>Possible Matches</h3><div class="data-grid"><div class="data-item interactive-row" onclick="alert('PM-KISAN selected')"><div class="data-label">PM-KISAN</div><div class="data-value">Income support</div><p>Tap to view sample eligibility information.</p></div><div class="data-item interactive-row" onclick="alert('Crop Insurance selected')"><div class="data-label">Crop Insurance Support</div><div class="data-value">Insurance support</div><p>Tap to view sample requirements.</p></div><div class="data-item interactive-row" onclick="alert('Machinery Assistance selected')"><div class="data-label">Agricultural Machinery Assistance</div><div class="data-value">Machinery support</div><p>Tap to view sample details.</p></div></div></div><div class="data-card"><h3>Profile Match</h3><p>Crop: Paddy · Land: 2 acres · District: Erode · Irrigation: Available</p><button onclick="alert('Sample eligibility check complete')">Check My Matches</button></div>`}
else if(type==='labour'){title.textContent='LabourLink';sub.textContent='Find workers, view availability and send a sample request.';content.innerHTML=`<div class="data-card"><h3>Workers Available</h3><div class="data-grid"><div class="data-item interactive-row" onclick="alert('Harvesting team selected')"><div class="data-label">Harvesting</div><div class="data-value">5 workers</div><p>Available tomorrow · Perundurai</p></div><div class="data-item interactive-row" onclick="alert('General farm team selected')"><div class="data-label">General farm work</div><div class="data-value">3 workers</div><p>Available nearby</p></div></div></div><div class="data-card"><h3>Labour Actions</h3><div class="feature-actions"><button onclick="alert('Sample labour request sent')">Request Workers</button><button onclick="alert('Sample availability refreshed')">Refresh Availability</button><button onclick="alert('Sample work reminder created')">Set Reminder</button></div></div>`}
else {title.textContent='Buyer & Seller Marketplace';sub.textContent='Explore sample listings and buyer demand.';content.innerHTML=`<div class="data-card"><h3>Buyer Demand</h3><div class="data-grid"><div class="data-item interactive-row" onclick="alert('Buyer selected')"><div class="data-label">Paddy buyers</div><div class="data-value">4 buyers</div><p>Sample demand: 20 quintals</p></div><div class="data-item interactive-row" onclick="alert('Listing selected')"><div class="data-label">Active listings</div><div class="data-value">2 listings</div><p>Perundurai and Erode</p></div></div></div><div class="data-card"><h3>Marketplace Actions</h3><div class="feature-actions"><button onclick="alert('Sample produce listing created')">List My Produce</button><button onclick="alert('Sample buyer search opened')">Find Buyers</button><button onclick="alert('Sample seller search opened')">Find Sellers</button></div></div>`}}
function renderTodayPage(){document.getElementById('todayContent').innerHTML=`<div class="data-card"><h3>Farm Status</h3><div class="data-grid"><div class="data-item"><div class="data-label">Crop</div><div class="data-value">Paddy</div></div><div class="data-item"><div class="data-label">Stage</div><div class="data-value">Vegetative</div></div><div class="data-item"><div class="data-label">Weather</div><div class="data-value">Rain possible after 3 PM</div></div><div class="data-item"><div class="data-label">Market</div><div class="data-value">₹2,340 / quintal</div></div></div></div><div class="data-card"><h3>Today's Actions</h3><div class="feature-actions"><button onclick="alert('Irrigation marked as checked')">Mark Irrigation Checked</button><button onclick="openDetailPage('market')">Open MarketMate</button><button onclick="openExtraPage('voicePage')">Ask Voice Assistant</button></div></div>`}
function renderFullCalendar(){let d=fullCalDate,y=d.getFullYear(),m=d.getMonth();document.getElementById('fullMonthTitle').textContent=d.toLocaleString('en-US',{month:'long',year:'numeric'});let w=document.getElementById('fullWeekdays');w.innerHTML=['Sun','Mon','Tue','Wed','Thu','Fri','Sat'].map(x=>`<div>${x}</div>`).join('');let g=document.getElementById('fullCalendarGrid');let first=new Date(y,m,1).getDay(),days=new Date(y,m+1,0).getDate();g.innerHTML='';for(let i=0;i<first;i++)g.innerHTML+='<div></div>';for(let day=1;day<=days;day++){let task=day%5===0?'Check irrigation':day%7===0?'Review market':'Farm task';g.innerHTML+=`<button class="calendar-day" onclick="alert('Day ${day}: ${task}')"><strong>${day}</strong><small>${task}</small></button>`}}
function changeFullMonth(delta){fullCalDate.setMonth(fullCalDate.getMonth()+delta);renderFullCalendar()}
// Make the voice card open the dedicated voice page without triggering inline legacy controls.
document.addEventListener('DOMContentLoaded',()=>{let v=document.querySelector('.voice-card');if(v)v.addEventListener('click',()=>openExtraPage('voicePage'));let d=document.getElementById('dashboardLanguageSelect');if(d){d.style.display='none'}let vl=document.getElementById('voiceLanguage');if(vl)vl.innerHTML='<option value="en-IN">English</option><option value="ta-IN">Tamil</option>'});
</script>

<style>
/* Menpulam modern interactive layer */
:root{--m-green:#216b36;--m-dark:#17351b;--m-soft:#eef7ee;--m-accent:#6fbf73;--m-gold:#e8b94a;--m-blue:#2d6cdf;--m-card:#fff}
body{overflow-x:hidden}
.card,.data-card,.contact-card,.voice-box{animation:riseIn .55s ease both}
.card:hover,.data-card:hover,.contact-card:hover{box-shadow:0 16px 40px rgba(24,73,35,.12);transform:translateY(-3px)}
.primary-btn,.action-btn,.feature-actions button,.back-btn,.header-btn,.voice-lang{transition:transform .2s ease,box-shadow .2s ease,background .2s ease}
.primary-btn:hover,.action-btn:hover,.feature-actions button:hover,.back-btn:hover,.header-btn:hover,.voice-lang:hover{transform:translateY(-2px);box-shadow:0 8px 18px rgba(33,107,54,.18)}
@keyframes riseIn{from{opacity:0;transform:translateY(14px)}to{opacity:1;transform:translateY(0)}}
@keyframes pulseSoft{0%,100%{box-shadow:0 0 0 0 rgba(111,191,115,.18)}50%{box-shadow:0 0 0 12px rgba(111,191,115,0)}}
@keyframes floatLeaf{0%,100%{transform:translateY(0) rotate(0)}50%{transform:translateY(-6px) rotate(2deg)}}
.modern-hero{background:linear-gradient(135deg,#216b36,#3d8e4e);color:#fff;border-radius:28px;padding:34px;position:relative;overflow:hidden;margin-bottom:24px;box-shadow:0 18px 45px rgba(33,107,54,.2)}
.modern-hero:after{content:'🌱';position:absolute;right:28px;bottom:-18px;font-size:110px;opacity:.13;animation:floatLeaf 4s ease-in-out infinite}
.modern-hero h2{font-size:clamp(28px,4vw,42px);margin:4px 0 10px}.modern-hero p{max-width:760px;line-height:1.6;margin:0;opacity:.94}
.modern-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(230px,1fr));gap:18px;margin:18px 0}
.modern-tile{background:#fff;border:1px solid #e4eee5;border-radius:20px;padding:22px;cursor:pointer;transition:.25s;position:relative;overflow:hidden}.modern-tile:hover{transform:translateY(-5px);border-color:#b9d9bd}.modern-tile .tile-icon{font-size:28px;margin-bottom:12px}.modern-tile h3{margin:0 0 8px}.modern-tile p{color:#667085;line-height:1.5;margin:0}.tile-arrow{position:absolute;right:18px;top:18px;font-weight:700;color:var(--m-green)}
.status-pill{display:inline-flex;align-items:center;gap:7px;background:rgba(255,255,255,.15);border:1px solid rgba(255,255,255,.25);padding:8px 12px;border-radius:999px;font-size:13px}.status-dot{width:8px;height:8px;border-radius:50%;background:#8be28f;animation:pulseSoft 2s infinite}
.photo-upload{border:2px dashed #b7d5ba;border-radius:18px;padding:26px;text-align:center;background:#f8fcf8;cursor:pointer;transition:.2s}.photo-upload:hover{background:#f0f8f1;border-color:#75ad7c}.photo-upload input{display:none}.photo-preview-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(140px,1fr));gap:12px;margin-top:16px}.photo-preview{height:130px;border-radius:14px;overflow:hidden;background:#edf4ee;position:relative}.photo-preview img{width:100%;height:100%;object-fit:cover}.photo-preview span{position:absolute;left:7px;bottom:7px;background:rgba(0,0,0,.58);color:#fff;border-radius:8px;padding:3px 7px;font-size:11px}
.listing-card{background:#fff;border:1px solid #e3ebe4;border-radius:22px;overflow:hidden;transition:.25s}.listing-card:hover{transform:translateY(-4px);box-shadow:0 16px 36px rgba(20,60,30,.1)}.listing-image{height:190px;background:#e9f2ea;display:flex;align-items:center;justify-content:center;overflow:hidden}.listing-image img{width:100%;height:100%;object-fit:cover}.listing-body{padding:20px}.listing-meta{display:flex;flex-wrap:wrap;gap:7px;margin:10px 0}.meta-chip{background:#eef7ee;color:#285d34;border-radius:999px;padding:6px 10px;font-size:12px}.offer-box{background:#f8fbf8;border:1px solid #e2ece3;border-radius:16px;padding:15px;margin-top:14px}.offer-row{display:flex;gap:10px;align-items:center}.offer-row input{flex:1;padding:11px;border:1px solid #ccd9ce;border-radius:10px}.offer-status{font-size:13px;color:#667085;margin-top:9px;min-height:18px}
.contact-card a{display:inline-block;margin-top:8px}.contact-card .contact-icon{width:46px;height:46px;border-radius:14px;background:#eef7ee;display:grid;place-items:center;font-size:23px;margin-bottom:12px}
.small-note{font-size:12px;color:#667085;line-height:1.5}.demo-badge{display:inline-block;background:#fff4d6;color:#765b14;border-radius:999px;padding:5px 9px;font-size:11px;font-weight:700}
.floating-help{position:fixed;right:18px;bottom:18px;z-index:50;display:flex;align-items:center;gap:10px;background:#fff;padding:10px 14px;border-radius:18px;box-shadow:0 12px 32px rgba(0,0,0,.15);border:1px solid #e2ebe3}.floating-help .help-logo{width:38px;height:38px}.floating-help a{font-weight:700;color:#216b36;text-decoration:none}
@media(max-width:650px){.modern-hero{padding:25px}.listing-image{height:155px}.floating-help{left:12px;right:12px;bottom:12px}.offer-row{flex-direction:column;align-items:stretch}}
</style>
<script>
/* Enhanced Menpulam interactions: keeps the original features and adds photo listings, offers and official contacts. */
(function(){
  const originalOpenDetail=window.openDetailPage;
  window.openDetailPage=function(type){
    if(type==='marketplace'){return openModernMarketplace();}
    if(typeof originalOpenDetail==='function') originalOpenDetail(type);
  };

  window.openModernMarketplace=function(){
    openExtraPage('detailPage');
    const title=document.getElementById('detailTitle'), sub=document.getElementById('detailSubtitle'), content=document.getElementById('detailContent');
    title.textContent='Buyer & Seller Marketplace';
    sub.textContent='Share crop photos, list your produce, view buyer demand and negotiate a sample rate.';
    content.innerHTML=`
      <div class="modern-hero">
        <span class="status-pill"><span class="status-dot"></span> Interactive marketplace demo</span>
        <h2>Show your crop. Find a buyer. Discuss the rate.</h2>
        <p>Farmers can create a sample listing with crop photos, quantity and an asking price. Buyers can view the listing and send a sample offer.</p>
      </div>
      <div class="modern-grid">
        <div class="modern-tile" onclick="document.getElementById('listingFormCard').scrollIntoView({behavior:'smooth'})"><div class="tile-icon">📷</div><h3>Add Crop Photos</h3><p>Show the crop condition with multiple images.</p><span class="tile-arrow">→</span></div>
        <div class="modern-tile" onclick="showBuyerDemand()"><div class="tile-icon">🤝</div><h3>Buyer Demand</h3><p>See sample demand for crops in nearby markets.</p><span class="tile-arrow">→</span></div>
        <div class="modern-tile" onclick="document.getElementById('listingsArea').scrollIntoView({behavior:'smooth'})"><div class="tile-icon">💬</div><h3>Discuss Offers</h3><p>Send an asking price and a sample counter-offer.</p><span class="tile-arrow">→</span></div>
        <div class="modern-tile" onclick="openDetailPage('market')"><div class="tile-icon">📊</div><h3>Compare Market Rates</h3><p>Check the sample MarketMate prices before listing.</p><span class="tile-arrow">→</span></div>
      </div>
      <div class="data-card" id="listingFormCard">
        <div style="display:flex;justify-content:space-between;gap:12px;align-items:center;flex-wrap:wrap"><div><h3 style="margin-bottom:6px">Create a Produce Listing</h3><p style="margin-top:0;color:#667085">Use sample information for your school demonstration.</p></div><span class="demo-badge">Prototype data</span></div>
        <div class="modern-grid">
          <div><label>Crop</label><select id="listingCrop" style="width:100%;padding:12px;border:1px solid #ccd9ce;border-radius:10px"><option>Paddy</option><option>Turmeric</option><option>Banana</option><option>Maize</option><option>Groundnut</option></select></div>
          <div><label>Quantity (quintals)</label><input id="listingQty" type="number" value="10" min="1" style="width:100%;padding:12px;border:1px solid #ccd9ce;border-radius:10px"></div>
          <div><label>Asking Price (₹/quintal)</label><input id="listingPrice" type="number" value="2400" min="1" style="width:100%;padding:12px;border:1px solid #ccd9ce;border-radius:10px"></div>
          <div><label>Location</label><input id="listingLocation" value="Perundurai" style="width:100%;padding:12px;border:1px solid #ccd9ce;border-radius:10px"></div>
        </div>
        <label style="display:block;margin-top:8px">Crop Photos</label>
        <label class="photo-upload" for="cropPhotoInput"><input id="cropPhotoInput" type="file" accept="image/*" multiple><strong>Click to upload crop photos</strong><div class="small-note">For the prototype, photos stay in this browser session only.</div></label>
        <div id="photoPreviewGrid" class="photo-preview-grid"></div>
        <div class="feature-actions"><button class="primary-btn" onclick="createProduceListing()">Publish Sample Listing</button><button class="feature-actions" onclick="clearProducePhotos()">Clear Photos</button></div>
        <div id="listingCreatedMsg" class="small-note" style="margin-top:12px"></div>
      </div>
      <div class="data-card" id="listingsArea"><div style="display:flex;justify-content:space-between;align-items:center;gap:10px;flex-wrap:wrap"><h3 style="margin:0">Sample Produce Listings</h3><button class="back-btn" onclick="showBuyerDemand()">View Buyer Demand</button></div><div id="listingGrid" class="modern-grid" style="margin-top:20px"></div></div>`;
    bindPhotoInput(); renderSampleListings();
  };

  window.bindPhotoInput=function(){const input=document.getElementById('cropPhotoInput'); if(!input)return; input.onchange=()=>{const grid=document.getElementById('photoPreviewGrid');grid.innerHTML='';[...input.files].slice(0,4).forEach((file,i)=>{const url=URL.createObjectURL(file);grid.innerHTML+=`<div class="photo-preview"><img src="${url}" alt="Crop photo ${i+1}"><span>Photo ${i+1}</span></div>`})};};
  window.clearProducePhotos=function(){const i=document.getElementById('cropPhotoInput'),g=document.getElementById('photoPreviewGrid');if(i)i.value='';if(g)g.innerHTML='';};
  window.createProduceListing=function(){const crop=document.getElementById('listingCrop').value,qty=document.getElementById('listingQty').value,price=document.getElementById('listingPrice').value,loc=document.getElementById('listingLocation').value;const files=document.getElementById('cropPhotoInput')?.files?.length||0;document.getElementById('listingCreatedMsg').innerHTML=`<strong>Listing created in demo mode.</strong> ${crop} · ${qty} quintals · ₹${Number(price).toLocaleString('en-IN')}/quintal · ${loc}. ${files} photo(s) attached.`; renderSampleListings(true);};
  window.renderSampleListings=function(){const g=document.getElementById('listingGrid');if(!g)return;const listings=[{crop:'Paddy',qty:'20 quintals',price:'₹2,400/quintal',loc:'Perundurai',buyer:'4 buyers interested',img:'https://images.unsplash.com/photo-1536633058897-5c2d0d4b0e1b?auto=format&fit=crop&w=900&q=80'},{crop:'Turmeric',qty:'12 quintals',price:'₹12,800/quintal',loc:'Erode',buyer:'2 buyers interested',img:'https://images.unsplash.com/photo-1615485290382-441e4d049cb5?auto=format&fit=crop&w=900&q=80'}];g.innerHTML=listings.map((x,i)=>`<div class="listing-card"><div class="listing-image"><img src="${x.img}" alt="${x.crop} crop"></div><div class="listing-body"><span class="demo-badge">Sample listing</span><h3 style="margin:10px 0 5px">${x.crop}</h3><div class="listing-meta"><span class="meta-chip">${x.qty}</span><span class="meta-chip">${x.loc}</span><span class="meta-chip">${x.buyer}</span></div><strong>${x.price}</strong><div class="offer-box"><strong>Buyer offer</strong><div class="offer-row" style="margin-top:9px"><input id="offer${i}" type="number" placeholder="₹ / quintal"><button class="primary-btn" onclick="sendOffer(${i})">Send Offer</button></div><div id="offerStatus${i}" class="offer-status"></div></div></div></div>`).join('');};
  window.sendOffer=function(i){const v=document.getElementById('offer'+i)?.value,s=document.getElementById('offerStatus'+i);if(!v){s.textContent='Enter an offer amount first.';return}s.textContent=`Sample offer sent: ₹${Number(v).toLocaleString('en-IN')}/quintal. The farmer can accept, reject or counter-offer.`;};
  window.showBuyerDemand=function(){const content=document.getElementById('detailContent');if(!content)return;content.insertAdjacentHTML('afterbegin',`<div class="data-card" id="buyerDemandBox"><div style="display:flex;justify-content:space-between;gap:12px;align-items:center"><div><h3 style="margin-bottom:5px">Buyer Demand Near You</h3><p style="margin:0;color:#667085">Sample marketplace demand for demonstration.</p></div><button class="back-btn" onclick="document.getElementById('buyerDemandBox')?.remove()">Close</button></div><div class="modern-grid"><div class="modern-tile"><h3>Paddy</h3><p>4 interested buyers · 20 quintals requested</p><strong>Target: ₹2,300–₹2,450</strong></div><div class="modern-tile"><h3>Turmeric</h3><p>2 interested buyers · 12 quintals requested</p><strong>Target: ₹12,500–₹13,000</strong></div></div></div>`);document.getElementById('buyerDemandBox').scrollIntoView({behavior:'smooth'});};

  /* Replace the contact page with a larger official directory using the current Erode district government directory. */
  window.openOfficialContacts=function(){openExtraPage('contactPage');const page=document.getElementById('contactPage');page.innerHTML=`<div class="detail-header"><button class="back-btn" onclick="closeExtraPage('contactPage')">Back to Dashboard</button><div class="modern-hero"><span class="status-pill"><span class="status-dot"></span> Official directory</span><h2>Government Agriculture Help</h2><p>Verified agriculture and allied-department contacts from the Erode District government directory.</p></div></div><div class="data-card"><div class="modern-grid"><div class="contact-card"><div class="contact-icon">🌾</div><h4>Joint Director of Agriculture, Erode</h4><p>Vidhyanagar, Thindal, Erode</p><a href="tel:9894730543">Call 98947 30543</a></div><div class="contact-card"><div class="contact-icon">🏛️</div><h4>Government Schemes</h4><p>Agriculture Officer — Government of India Schemes</p><a href="tel:8940141976">Call 89401 41976</a></div><div class="contact-card"><div class="contact-icon">📊</div><h4>Agricultural Marketing & Agri Business</h4><p>Deputy Director, Erode</p><a href="tel:9486412102">Call 94864 12102</a></div><div class="contact-card"><div class="contact-icon">☎️</div><h4>District Agriculture Office</h4><p>District-level agriculture office</p><a href="tel:04242339101">Call 0424 233 9101</a></div></div><p class="small-note">Contacts are from the official Erode District government directory. Phone details can change, so the app should refresh its directory from an official source in a real deployment.</p></div>`;};

  /* Add a dashboard shortcut if there is no existing contacts button. */
  document.addEventListener('DOMContentLoaded',()=>{
    const dash=document.getElementById('dashboardPage'); if(!dash)return;
    const main=dash.querySelector('main'); if(main && !document.getElementById('officialContactShortcut')){
      const sec=document.createElement('section');sec.className='modern-grid';sec.id='officialContactShortcut';sec.innerHTML=`<div class="modern-tile" onclick="openOfficialContacts()"><div class="tile-icon">🏛️</div><h3>Government Help</h3><p>Call official agriculture contacts for schemes, marketing and general support.</p><span class="tile-arrow">→</span></div><div class="modern-tile" onclick="openModernMarketplace()"><div class="tile-icon">📷</div><h3>Sell With Photos</h3><p>Upload crop photos, set an asking rate and receive sample buyer offers.</p><span class="tile-arrow">→</span></div>`;main.appendChild(sec);
    }
  });
})();
</script>


<script>
(function(){
  const layer=document.createElement('div'); layer.className='menpulam-particles';
  Object.assign(layer.style,{position:'fixed',inset:'0',pointerEvents:'none',zIndex:'0',overflow:'hidden'});
  for(let i=0;i<16;i++){const d=document.createElement('span'); d.textContent=['✦','•','✧'][i%3]; Object.assign(d.style,{position:'absolute',left:(Math.random()*100)+'%',top:(Math.random()*100)+'%',fontSize:(8+Math.random()*10)+'px',opacity:.10+Math.random()*.12,animation:`leafDrift ${4+Math.random()*5}s ease-in-out ${Math.random()*3}s infinite`}); layer.appendChild(d)}
  document.body.prepend(layer);
  document.querySelectorAll('.feature-card,.card,.market-card,.scheme-card,.labour-card').forEach((el,i)=>{el.style.animationDelay=(i*.06)+'s';});
})();
</script>
</body>


</html>
