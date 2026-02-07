# belyavski.github.io
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wedding 2026 - Signature Series with Gemini AI</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;800&display=swap');
        
        :root {
            --apple-bg: #f5f5f7;
            --apple-card: #ffffff;
            --apple-text: #1d1d1f;
            --apple-gray: #86868b;
            --apple-blue: #0066cc;
            --apple-red: #d70015;
        }

        body {
            background-color: var(--apple-bg);
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 40px;
            padding: 80px 20px;
            font-family: 'Inter', -apple-system, sans-serif;
            color: var(--apple-text);
            -webkit-font-smoothing: antialiased;
        }

        .container-header {
            text-align: center;
            max-width: 600px;
            margin-bottom: 20px;
        }

        .card {
            width: 100%;
            max-width: 400px;
            background: var(--apple-card);
            border-radius: 30px;
            padding: 40px;
            display: flex;
            flex-direction: column;
            box-shadow: 0 10px 40px rgba(0,0,0,0.04);
            transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            border: 1px solid rgba(0,0,0,0.05);
        }

        .card:hover {
            transform: scale(1.01);
            box-shadow: 0 20px 50px rgba(0,0,0,0.08);
        }

        .pill-badge {
            font-size: 11px;
            font-weight: 600;
            padding: 6px 14px;
            border-radius: 20px;
            display: inline-block;
            margin-bottom: 20px;
            text-transform: uppercase;
            letter-spacing: 0.05em;
        }

        .title {
            font-size: 32px;
            font-weight: 800;
            line-height: 1.1;
            margin-bottom: 12px;
            letter-spacing: -0.03em;
        }

        .subtitle {
            font-size: 14px;
            color: var(--apple-gray);
            line-height: 1.5;
            margin-bottom: 24px;
        }

        .feature-list {
            margin-top: 20px;
            border-top: 1px solid #f0f0f0;
            padding-top: 20px;
        }

        .feature-item {
            display: flex;
            gap: 12px;
            margin-bottom: 16px;
            font-size: 13px;
            line-height: 1.4;
        }

        .price-value {
            font-size: 42px;
            font-weight: 700;
            letter-spacing: -0.02em;
        }

        .cta-button {
            margin-top: 20px;
            background: var(--apple-text);
            color: #fff;
            padding: 16px;
            border-radius: 14px;
            text-align: center;
            font-weight: 600;
            font-size: 14px;
            cursor: pointer;
            border: none;
            width: 100%;
            transition: all 0.2s;
        }

        .cta-button:active {
            transform: scale(0.98);
        }

        .ai-section {
            width: 100%;
            max-width: 400px;
            background: #fff;
            border-radius: 30px;
            padding: 30px;
            border: 1px solid rgba(0,0,0,0.05);
            box-shadow: 0 4px 20px rgba(0,0,0,0.02);
        }

        .ai-input {
            width: 100%;
            padding: 12px;
            border-radius: 10px;
            border: 1px solid #eee;
            margin-top: 10px;
            font-size: 14px;
            background: var(--apple-bg);
            outline: none;
        }

        #ai-response, #chat-response {
            font-size: 13px;
            color: #444;
            line-height: 1.6;
            margin-top: 20px;
            white-space: pre-wrap;
            padding: 15px;
            background: var(--apple-bg);
            border-radius: 15px;
        }

        .loading-dots:after {
            content: ' .';
            animation: dots 1s steps(5, end) infinite;
        }

        @keyframes dots {
            0%, 20% { content: ' .'; }
            40% { content: ' ..'; }
            60% { content: ' ...'; }
            80%, 100% { content: ''; }
        }

        .ultra-accent {
            border: 1px solid #000;
            box-shadow: 0 25px 60px rgba(0,0,0,0.1);
        }

        .chat-container {
            width: 100%;
            max-width: 400px;
            background: #fff;
            border-radius: 30px;
            padding: 30px;
            border: 1px solid #eee;
        }
    </style>
</head>
<body>

    <div class="container-header">
        <h1 class="text-4xl font-extrabold tracking-tight mb-2 text-black">Signature Series 2026</h1>
        <p class="text-lg text-gray-500">Система сохранения ваших воспоминаний.</p>
    </div>

    <!-- AI PLANNING SECTION -->
    <div class="ai-section">
        <div class="flex items-center gap-2 mb-4">
            <span class="text-blue-600"><i class="fa-solid fa-sparkles"></i></span>
            <h3 class="font-bold text-sm uppercase tracking-wider">✨ AI Планировщик</h3>
        </div>
        
        <div class="mb-6">
            <p class="text-xs text-gray-500 mb-2">Начало регистрации:</p>
            <input type="time" id="wedding-time" class="ai-input" value="14:00">
            <button onclick="calculateTiming()" id="ai-btn" class="cta-button bg-blue-600 text-white mt-4 !py-3">
                ✨ Рассчитать идеальный день
            </button>
        </div>

        <div class="border-t pt-4">
            <p class="text-xs text-gray-500 mb-2">Стиль свадьбы (лофт, классика, бохо...):</p>
            <input type="text" id="wedding-style" class="ai-input" placeholder="Напр. Минималистичный лофт">
            <button onclick="generateConcept()" id="concept-btn" class="cta-button bg-black text-white mt-4 !py-3">
                ✨ Сгенерировать концепцию съемки
            </button>
        </div>

        <div id="ai-response" style="display:none;"></div>
    </div>

    <!-- PACKAGES SECTION (LITE, SIGNATURE, ULTRA) -->
    <div class="card">
        <div class="flex justify-between">
            <span class="pill-badge bg-gray-100 text-gray-500">Base</span>
            <button onclick="speak('Lite')" class="text-gray-400 hover:text-black"><i class="fa-solid fa-volume-high"></i></button>
        </div>
        <h2 class="title">Lite.</h2>
        <p class="subtitle">Фиксация факта. 80% контекста останется за кадром. Выбор для формального подтверждения события.</p>
        <div class="feature-list">
            <div class="feature-item">
                <i class="fa-solid fa-clock mt-1 text-gray-400"></i>
                <span><b>4 часа.</b> Только ЗАГС и прогулка.</span>
            </div>
        </div>
        <div class="price-section">
            <div class="price-value">$200</div>
            <button class="cta-button bg-gray-100 !text-black mt-4">Выбрать Lite</button>
        </div>
    </div>

    <div class="card" style="border: 2px solid #000;">
        <div class="flex justify-between">
            <span class="pill-badge bg-black text-white">Popular</span>
            <button onclick="speak('Signature')" class="text-gray-400 hover:text-black"><i class="fa-solid fa-volume-high"></i></button>
        </div>
        <h2 class="title">Signature.</h2>
        <p class="subtitle">Золотой стандарт. Полный отчет без сожалений. Оптимальное покрытие ключевых моментов дня.</p>
        <div class="feature-list">
            <div class="feature-item">
                <i class="fa-solid fa-check mt-1 text-black"></i>
                <span><b>8 часов.</b> От сборов до первого танца.</span>
            </div>
            <div class="feature-item">
                <i class="fa-solid fa-bolt mt-1 text-blue-500"></i>
                <span><b>14 дней.</b> Приоритетная выдача.</span>
            </div>
        </div>
        <div class="price-section">
            <div class="price-value">$300</div>
            <button class="cta-button">Забронировать Signature</button>
        </div>
    </div>

    <div class="card ultra-accent">
        <div class="flex justify-between">
            <span class="pill-badge bg-blue-50 text-blue-600">Premium Heritage</span>
            <button onclick="speak('Ultra')" class="text-gray-400 hover:text-black"><i class="fa-solid fa-volume-high"></i></button>
        </div>
        <h2 class="title">Ultra.</h2>
        <p class="subtitle">Создание семейной реликвии. Бескомпромиссное качество и скорость для тех, кто ценит момент выше цены.</p>
        <div class="feature-list">
            <div class="feature-item">
                <i class="fa-solid fa-star mt-1 text-black"></i>
                <span><b>Next Day.</b> 30 лучших фото утром.</span>
            </div>
            <div class="feature-item">
                <i class="fa-solid fa-infinity mt-1 text-black"></i>
                <span><b>500+ фото.</b> Расширенная летопись.</span>
            </div>
        </div>
        <div class="price-section">
            <div class="price-value">$450</div>
            <button class="cta-button bg-black text-white mt-4">Получить Ultra</button>
        </div>
    </div>

    <!-- AI CHAT SECTION -->
    <div class="chat-container shadow-sm">
        <div class="flex items-center gap-2 mb-4">
            <span class="text-purple-600"><i class="fa-solid fa-comments"></i></span>
            <h3 class="font-bold text-sm uppercase tracking-wider">✨ AI Консультант</h3>
        </div>
        <p class="text-xs text-gray-500 mb-4">Задайте любой вопрос о свадебной съемке:</p>
        <div class="flex gap-2">
            <input type="text" id="chat-input" class="ai-input !mt-0" placeholder="Что надеть на фотосессию?">
            <button onclick="askChat()" class="bg-gray-100 p-3 rounded-xl hover:bg-gray-200">
                <i class="fa-solid fa-paper-plane text-black"></i>
            </button>
        </div>
        <div id="chat-response" style="display:none;"></div>
    </div>

    <script>
        const apiKey = ""; // API Key provided by env

        async function callGemini(prompt, systemPrompt = "") {
            const url = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent?key=${apiKey}`;
            const payload = {
                contents: [{ parts: [{ text: prompt }] }],
                systemInstruction: { parts: [{ text: systemPrompt }] }
            };

            for (let i = 0; i < 5; i++) {
                try {
                    const response = await fetch(url, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify(payload)
                    });
                    const data = await response.json();
                    return data.candidates?.[0]?.content?.parts?.[0]?.text;
                } catch (e) {
                    await new Promise(r => setTimeout(r, Math.pow(2, i) * 1000));
                }
            }
            return "Извините, сейчас я не могу ответить. Пожалуйста, попробуйте позже.";
        }

        async function calculateTiming() {
            const time = document.getElementById('wedding-time').value;
            const resDiv = document.getElementById('ai-response');
            const btn = document.getElementById('ai-btn');

            resDiv.style.display = 'block';
            resDiv.innerHTML = '<span class="loading-dots">Gemini анализирует ваш график</span>';
            btn.disabled = true;

            const prompt = `Свадьба начинается в ${time}. Напиши краткий план дня (3 пункта) и порекомендуй пакет: Lite, Signature или Ultra. Аргументируй. Стиль: лаконичный Apple.`;
            const system = "Ты - эксперт по свадебной логистике. Твоя задача - помочь паре выбрать пакет услуг, рассчитав время съемки.";

            const result = await callGemini(prompt, system);
            resDiv.innerText = result;
            btn.disabled = false;
        }

        async function generateConcept() {
            const style = document.getElementById('wedding-style').value || "Классика";
            const resDiv = document.getElementById('ai-response');
            const btn = document.getElementById('concept-btn');

            resDiv.style.display = 'block';
            resDiv.innerHTML = '<span class="loading-dots">Создаем вашу историю</span>';
            btn.disabled = true;

            const prompt = `Стиль свадьбы: ${style}. Предложи 3 креативных идеи для фотосессии, которые подчеркнут этот стиль. Формат: короткие тезисы.`;
            const system = "Ты - топовый свадебный арт-директор. Твои идеи должны быть стильными, современными и вдохновляющими.";

            const result = await callGemini(prompt, system);
            resDiv.innerText = result;
            btn.disabled = false;
        }

        async function askChat() {
            const input = document.getElementById('chat-input');
            const resDiv = document.getElementById('chat-response');
            const query = input.value;
            if (!query) return;

            resDiv.style.display = 'block';
            resDiv.innerHTML = '<span class="loading-dots">Обдумываю ответ</span>';
            input.value = "";

            const result = await callGemini(query, "Ты - дружелюбный ассистент свадебного фотографа. Отвечай кратко, профессионально и с заботой о клиенте.");
            resDiv.innerText = result;
        }

        async function speak(packageName) {
            const ttsUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-tts:generateContent?key=${apiKey}`;
            let text = "";
            
            if(packageName === 'Lite') text = "Say professionally: Пакет Лайт. Четыре часа съемки. Только самое необходимое.";
            if(packageName === 'Signature') text = "Say elegantly: Пакет Сигначур. Восемь часов. Ваш полный свадебный день в идеальном качестве.";
            if(packageName === 'Ultra') text = "Say powerfully: Пакет Ультра. Премиальный выбор. Двенадцать часов и первые фото уже завтра.";

            try {
                const response = await fetch(ttsUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify({
                        contents: [{ parts: [{ text: text }] }],
                        generationConfig: {
                            responseModalities: ["AUDIO"],
                            speechConfig: { voiceConfig: { prebuiltVoiceConfig: { voiceName: "Puck" } } }
                        }
                    })
                });
                const data = await response.json();
                const pcmData = data.candidates[0].content.parts[0].inlineData.data;
                playAudio(pcmData);
            } catch (e) { console.error(e); }
        }

        function playAudio(base64Data) {
            const binaryString = atob(base64Data);
            const bytes = new Uint8Array(binaryString.length);
            for (let i = 0; i < binaryString.length; i++) bytes[i] = binaryString.charCodeAt(i);
            const wavHeader = createWavHeader(bytes.length, 24000); 
            const blob = new Blob([wavHeader, bytes], { type: 'audio/wav' });
            const audio = new Audio(URL.createObjectURL(blob));
            audio.play();
        }

        function createWavHeader(dataLength, sampleRate) {
            const buffer = new ArrayBuffer(44);
            const view = new DataView(buffer);
            const writeString = (offset, string) => {
                for (let i = 0; i < string.length; i++) view.setUint8(offset + i, string.charCodeAt(i));
            };
            writeString(0, 'RIFF');
            view.setUint32(4, 36 + dataLength, true);
            writeString(8, 'WAVE');
            writeString(12, 'fmt ');
            view.setUint32(16, 16, true);
            view.setUint16(20, 1, true);
            view.setUint16(22, 1, true);
            view.setUint32(24, sampleRate, true);
            view.setUint32(28, sampleRate * 2, true);
            view.setUint16(32, 2, true);
            view.setUint16(34, 16, true);
            writeString(36, 'data');
            view.setUint32(40, dataLength, true);
            return buffer;
        }
    </script>
</body>
</html>
