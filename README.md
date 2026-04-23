<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Executive AI Hub | منصة الإدارة الذكية - 16 مدير AI</title>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --bg-dark: #05070a;
            --panel-bg: rgba(13, 17, 23, 0.8);
            --accent-blue: #00d2ff;
            --accent-purple: #9d50bb;
            --text-main: #e6edf3;
            --border-color: rgba(48, 54, 61, 0.8);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        body {
            font-family: 'Cairo', sans-serif;
            background: var(--bg-dark);
            background-image: 
                radial-gradient(circle at 10% 20%, rgba(0, 210, 255, 0.05) 0%, transparent 40%),
                radial-gradient(circle at 90% 80%, rgba(157, 80, 187, 0.05) 0%, transparent 40%);
            color: var(--text-main);
            overflow-x: hidden;
            min-height: 100vh;
        }

        .container { max-width: 1600px; margin: 0 auto; padding: 1.5rem; }

        /* Header Section */
        header {
            text-align: center;
            padding: 2rem 0;
            border-bottom: 1px solid var(--border-color);
            margin-bottom: 2rem;
        }

        header h1 {
            font-weight: 900;
            font-size: 3rem;
            letter-spacing: -1px;
            background: linear-gradient(to right, #fff, var(--accent-blue));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 0.5rem;
        }

        .badge {
            display: inline-block;
            background: rgba(0, 210, 255, 0.1);
            border-radius: 100px;
            padding: 0.3rem 1rem;
            font-size: 0.8rem;
            margin-top: 0.5rem;
        }

        header p { color: #8b949e; font-size: 1.1rem; }

        /* Main Grid */
        .main-layout {
            display: grid;
            grid-template-columns: 1fr 400px;
            gap: 1.5rem;
        }

        /* Managers Grid */
        .managers-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(210px, 1fr));
            gap: 1rem;
        }

        .manager-card {
            background: var(--panel-bg);
            border: 1px solid var(--border-color);
            border-radius: 1.25rem;
            padding: 1.2rem;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
        }

        .manager-card::before {
            content: '';
            position: absolute;
            top: 0; left: 0; width: 100%; height: 4px;
            background: linear-gradient(90deg, var(--accent-blue), var(--accent-purple));
            opacity: 0; transition: 0.3s;
        }

        .manager-card:hover {
            transform: translateY(-8px);
            border-color: var(--accent-blue);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
        }

        .manager-card:hover::before { opacity: 1; }

        .card-icon {
            width: 45px; height: 45px;
            background: rgba(0, 210, 255, 0.1);
            border-radius: 12px;
            display: flex; align-items: center; justify-content: center;
            font-size: 1.3rem; color: var(--accent-blue);
            margin-bottom: 0.8rem;
        }

        .manager-title { font-size: 0.7rem; color: #8b949e; text-transform: uppercase; font-weight: bold; letter-spacing: 1px; }
        .manager-name { font-size: 1.1rem; font-weight: 700; margin-bottom: 0.5rem; }
        .manager-role { font-size: 0.7rem; color: var(--accent-purple); margin-bottom: 0.8rem; }

        .btn-chat-sm {
            width: 100%;
            padding: 8px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
            background: transparent;
            color: #fff;
            cursor: pointer;
            font-size: 0.8rem;
            transition: 0.3s;
        }

        .btn-chat-sm:hover { background: var(--accent-blue); color: #000; border-color: var(--accent-blue); }

        /* Control Panel */
        .control-panel {
            background: var(--panel-bg);
            border-radius: 1.5rem;
            border: 1px solid var(--border-color);
            padding: 1.5rem;
            height: calc(100vh - 180px);
            position: sticky;
            top: 1.5rem;
            display: flex;
            flex-direction: column;
        }

        .section-title { font-size: 1rem; font-weight: 700; margin-bottom: 0.8rem; display: flex; align-items: center; gap: 10px; }

        .log-container {
            flex: 0.35;
            background: #010409;
            border-radius: 10px;
            padding: 10px;
            font-family: 'Courier New', monospace;
            font-size: 0.7rem;
            overflow-y: auto;
            margin-bottom: 1rem;
            border: 1px solid #21262d;
        }

        .input-box {
            background: #0d1117;
            border: 1px solid #30363d;
            border-radius: 10px;
            padding: 10px;
            color: #fff;
            width: 100%;
            margin-bottom: 0.5rem;
            font-family: 'Cairo';
        }

        .action-btns { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-bottom: 1rem; }

        .btn-main {
            padding: 10px;
            border-radius: 10px;
            border: none;
            font-weight: 700;
            cursor: pointer;
            transition: 0.3s;
            display: flex; align-items: center; justify-content: center; gap: 8px;
            font-family: 'Cairo';
        }

        .btn-primary { background: var(--accent-blue); color: #000; }
        .btn-secondary { background: var(--accent-purple); color: #fff; }

        .output-area {
            flex: 1;
            background: rgba(0,0,0,0.3);
            border: 1px dashed var(--border-color);
            border-radius: 12px;
            padding: 1rem;
            overflow-y: auto;
            font-size: 0.9rem;
            line-height: 1.7;
            position: relative;
        }

        /* Loading Animation */
        .typing-dots { display: none; padding: 10px; text-align: center; }
        .dot { height: 8px; width: 8px; background: var(--accent-blue); border-radius: 50%; display: inline-block; animation: bounce 1.4s infinite ease-in-out both; margin: 0 2px; }
        .dot:nth-child(1) { animation-delay: -0.32s; }
        .dot:nth-child(2) { animation-delay: -0.16s; }
        @keyframes bounce { 0%, 80%, 100% { transform: scale(0); } 40% { transform: scale(1.0); } }

        /* Modal Customization */
        .modal {
            display: none; position: fixed; inset: 0;
            background: rgba(0,0,0,0.95);
            backdrop-filter: blur(8px);
            z-index: 9999;
            align-items: center; justify-content: center;
        }

        .modal-body {
            width: 90%; max-width: 600px;
            height: 70vh;
            background: var(--panel-bg);
            border: 1px solid var(--accent-blue);
            border-radius: 1.5rem;
            display: flex; flex-direction: column;
            overflow: hidden;
        }

        .chat-header { padding: 1rem; background: rgba(255,255,255,0.05); border-bottom: 1px solid var(--border-color); display: flex; justify-content: space-between; align-items: center; }
        .chat-window { flex: 1; padding: 1rem; overflow-y: auto; display: flex; flex-direction: column; gap: 0.8rem; }
        .msg { padding: 10px 15px; border-radius: 15px; max-width: 85%; line-height: 1.5; }
        .msg-ai { background: #21262d; align-self: flex-start; border-bottom-left-radius: 4px; }
        .msg-user { background: var(--accent-blue); color: #000; align-self: flex-end; margin-left: auto; border-bottom-right-radius: 4px; }

        @media (max-width: 1100px) {
            .main-layout { grid-template-columns: 1fr; }
            .control-panel { position: static; height: auto; }
        }
    </style>
</head>
<body>

<div class="container">
    <header>
        <h1>Executive Hub <span style="font-weight: 300; font-size: 1.5rem; color: var(--accent-blue);">AI</span></h1>
        <p>قم بقيادة شركتك الافتراضية عبر فريق من 16 مدير AI يتعاونون كفريق حقيقي</p>
        <div class="badge"><i class="fas fa-robot"></i> مدعوم بـ Google Gemini AI</div>
    </header>

    <div class="main-layout">
        <div class="managers-grid" id="managersGrid"></div>

        <div class="control-panel">
            <div class="section-title"><i class="fas fa-terminal"></i> سجل العمليات</div>
            <div class="log-container" id="sysLog"></div>

            <div class="section-title"><i class="fas fa-edit"></i> مدخلات البيانات</div>
            <input type="text" id="topicInput" class="input-box" placeholder="ما هو الموضوع أو التحدي الحالي؟" value="استراتيجية التوسع في الأسواق الجديدة">
            <select id="managerSelect" class="input-box"></select>
            
            <div class="action-btns">
                <button class="btn-main btn-primary" id="writeBtn"><i class="fas fa-file-signature"></i> إنشاء تقرير</button>
                <button class="btn-main btn-secondary" id="meetingBtn"><i class="fas fa-handshake"></i> جلسة طوارئ</button>
            </div>

            <div class="section-title"><i class="fas fa-microchip"></i> المخرج النهائي</div>
            <div class="output-area">
                <div class="typing-dots" id="loadingDots">
                    <span class="dot"></span> <span class="dot"></span> <span class="dot"></span>
                </div>
                <div id="finalOutput">✨ جاهز لتحليل طلباتك... اختر مديراً وموضوعاً ثم اضغط على الزر المناسب.</div>
            </div>
        </div>
    </div>
</div>

<div class="modal" id="chatModal">
    <div class="modal-body">
        <div class="chat-header">
            <h3 id="currentChatManager">الدردشة الذكية</h3>
            <button onclick="closeChat()" style="background:none; border:none; color:#fff; font-size:1.5rem; cursor:pointer;">&times;</button>
        </div>
        <div class="chat-window" id="chatWindow">
            <div class="msg msg-ai">مرحباً! أنا هنا لمساعدتك. اسألني أي شيء يتعلق باختصاصي.</div>
        </div>
        <div style="padding: 1rem; border-top: 1px solid var(--border-color); display: flex; gap: 10px;">
            <input type="text" id="chatInput" class="input-box" style="margin-bottom:0" placeholder="اسأل المدير عن أي تفاصيل...">
            <button class="btn-main btn-primary" style="width: auto; padding: 0 20px;" id="sendChat">إرسال</button>
        </div>
    </div>
</div>

<script>
    // ====================== إعدادات API ======================
    // ⚠️ ضع مفتاح Google Gemini API الخاص بك هنا
    // احصل عليه من: https://aistudio.google.com/app/apikey
    const API_KEY = "YOUR_API_KEY_HERE";
    
    // ====================== المديرين الـ 16 الكاملين ======================
    const managers = [
        { id: "CEO", title: "المدير التنفيذي", name: "صقر الاستراتيجي", role: "الرؤية والقيادة", icon: "fa-crown", prompt: "أنت المدير التنفيذي (CEO)، خبير في وضع الرؤية الاستراتيجية وتحديد الأهداف الكبرى للشركة." },
        { id: "CFO", title: "المدير المالي", name: "عصام المالي", role: "الأرقام والميزانية", icon: "fa-chart-line", prompt: "أنت المدير المالي (CFO)، خبير في تحليل التكاليف، إدارة الميزانية، وتعظيم الأرباح." },
        { id: "CTO", title: "المدير التقني", name: "رعد التقني", role: "التكنولوجيا والابتكار", icon: "fa-microchip", prompt: "أنت المدير التقني (CTO)، خبير في البنية التحتية التقنية، الأمن السيبراني، والذكاء الاصطناعي." },
        { id: "CMO", title: "مدير التسويق", name: "ليلى التسويقية", role: "العلامة التجارية والنمو", icon: "fa-bullhorn", prompt: "أنت مدير التسويق (CMO)، خبيرة في استراتيجيات النمو، العلامة التجارية، وجذب العملاء." },
        { id: "COO", title: "مدير العمليات", name: "فهد العمليات", role: "التنفيذ والجودة", icon: "fa-gears", prompt: "أنت مدير العمليات (COO)، خبير في سرعة التنفيذ، الكفاءة التشغيلية، وتقليل الهدر." },
        { id: "CISO", title: "مدير الأمن السيبراني", name: "حازم الأمن", role: "الأمن والحماية", icon: "fa-shield-haltered", prompt: "أنت مدير الأمن السيبراني (CISO)، خبير في حماية البيانات، تقييم المخاطر، والامتثال الأمني." },
        { id: "CDO", title: "مدير البيانات", name: "وسام البيانات", role: "البيانات والتحليلات", icon: "fa-database", prompt: "أنت مدير البيانات (CDO)، خبير في تحليل البيانات، حوكمتها، واستخراج الرؤى." },
        { id: "CLO", title: "المستشار القانوني", name: "منصور القانوني", role: "الامتثال والعقود", icon: "fa-gavel", prompt: "أنت المستشار القانوني (CLO)، خبير في حماية الشركة قانونياً، العقود، وتجنب الثغرات." },
        { id: "CPO", title: "مدير المنتج", name: "نور المنتج", role: "تطوير المنتجات", icon: "fa-box", prompt: "أنت مدير المنتج (CPO)، خبيرة في تطوير المنتجات، تحديد الميزات، وتحسين تجربة المستخدم." },
        { id: "CHRO", title: "مدير الموارد البشرية", name: "سامر الموارد", role: "الكفاءات البشرية", icon: "fa-users", prompt: "أنت مدير الموارد البشرية (CHRO)، خبير في التوظيف، تطوير المواهب، وثقافة الشركة." },
        { id: "CIO", title: "مدير نظم المعلومات", name: "إياد المعلومات", role: "تكامل الأنظمة", icon: "fa-network-wired", prompt: "أنت مدير نظم المعلومات (CIO)، خبير في تكامل الأنظمة، البنية التحتية لتقنية المعلومات." },
        { id: "CInO", title: "مدير الابتكار", name: "رياض الابتكار", role: "البحث والتطوير", icon: "fa-lightbulb", prompt: "أنت مدير الابتكار (CInO)، خبير في التقنيات الناشئة، البحث والتطوير، والأفكار المستقبلية." },
        { id: "CSO", title: "مدير الاستدامة", name: "وئام الاستدامة", role: "الاستدامة والبيئة", icon: "fa-leaf", prompt: "أنت مدير الاستدامة (CSO)، خبيرة في تقليل الأثر البيئي، الممارسات المستدامة، والمسؤولية الاجتماعية." },
        { id: "CCO", title: "مدير تجربة العملاء", name: "ريان العملاء", role: "ولاء العملاء", icon: "fa-headset", prompt: "أنت مدير تجربة العملاء (CCO)، خبير في تحسين رضا العملاء، ولاء العملاء، وجودة الخدمة." },
        { id: "CDAO", title: "مدير التحليلات", name: "آسيا التحليلات", role: "النمذجة التنبؤية", icon: "fa-chart-line", prompt: "أنت مدير التحليلات (CDAO)، خبيرة في النمذجة التنبؤية، الإحصاء المتقدم، واستخراج الرؤى." },
        { id: "CTrO", title: "مدير الثقة الرقمية", name: "أمين الثقة", role: "الأخلاقيات والخصوصية", icon: "fa-hand-peace", prompt: "أنت مدير الثقة الرقمية (CTrO)، خبير في أخلاقيات الذكاء الاصطناعي، الخصوصية، والشفافية." }
    ];

    // ====================== دوال مساعدة ======================
    
    async function callGemini(prompt) {
        if (API_KEY === "YOUR_API_KEY_HERE") {
            return "⚠️ يرجى إدخال مفتاح Google Gemini API الصحيح في الكود. احصل عليه مجاناً من https://aistudio.google.com/app/apikey";
        }
        
        try {
            const response = await fetch(`https://generativelanguage.googleapis.com/v1beta/models/gemini-1.5-flash:generateContent?key=${API_KEY}`, {
                method: "POST",
                headers: { "Content-Type": "application/json" },
                body: JSON.stringify({ 
                    contents: [{ parts: [{ text: prompt }] }] 
                })
            });
            
            if (!response.ok) {
                const errorData = await response.json();
                console.error("API Error:", errorData);
                return `❌ خطأ في API: ${errorData.error?.message || "يرجى التحقق من المفتاح"}`;
            }
            
            const data = await response.json();
            if (data.candidates && data.candidates[0] && data.candidates[0].content && data.candidates[0].content.parts[0]) {
                return data.candidates[0].content.parts[0].text;
            } else {
                return "❌ لم يتم استلام رد صحيح من الذكاء الاصطناعي";
            }
        } catch (e) {
            console.error("Network Error:", e);
            return "❌ فشل الاتصال بالخادم. تحقق من اتصالك بالإنترنت.";
        }
    }

    // تأثير الكتابة التدريجي
    function streamText(text, targetId) {
        const target = document.getElementById(targetId);
        if (!target) return;
        target.innerHTML = "";
        let i = 0;
        const interval = setInterval(() => {
            if (i < text.length) {
                const char = text.charAt(i);
                if (char === "\n") {
                    target.innerHTML += "<br>";
                } else {
                    target.innerHTML += char;
                }
                i++;
                const outputArea = document.querySelector('.output-area');
                if (outputArea) outputArea.scrollTop = outputArea.scrollHeight;
            } else {
                clearInterval(interval);
                document.getElementById('loadingDots').style.display = "none";
            }
        }, 8);
        return interval;
    }

    function addLog(name, message) {
        const logBox = document.getElementById('sysLog');
        if (!logBox) return;
        const time = new Date().toLocaleTimeString('ar-EG', { hour12: false });
        logBox.innerHTML += `<div><span style="color:var(--accent-blue)">[${time}]</span> <b>${name}:</b> ${message}</div>`;
        logBox.scrollTop = logBox.scrollHeight;
        
        // منع تراكم السجلات بشكل مفرط
        if (logBox.children.length > 100) {
            while (logBox.children.length > 80) {
                logBox.removeChild(logBox.firstChild);
            }
        }
    }

    // ====================== بناء واجهة المديرين ======================
    const grid = document.getElementById('managersGrid');
    const select = document.getElementById('managerSelect');

    managers.forEach(m => {
        // بطاقات المديرين
        const card = document.createElement('div');
        card.className = 'manager-card';
        card.innerHTML = `
            <div class="card-icon"><i class="fas ${m.icon}"></i></div>
            <div class="manager-title">${m.title}</div>
            <div class="manager-name">${m.name}</div>
            <div class="manager-role">${m.role}</div>
            <button class="btn-chat-sm" onclick="openChat('${m.id}')"><i class="fas fa-comments"></i> استشارة خاصة</button>
        `;
        grid.appendChild(card);
        
        // القائمة المنسدلة
        const option = document.createElement('option');
        option.value = m.id;
        option.textContent = `${m.title} - ${m.name}`;
        select.appendChild(option);
    });

    // ====================== الوظائف الأساسية ======================
    
    // 1. إنشاء تقرير/مسودة من مدير محدد
    document.getElementById('writeBtn').onclick = async () => {
        const topic = document.getElementById('topicInput').value;
        const managerId = select.value;
        const manager = managers.find(m => m.id === managerId);
        
        if (!topic) {
            alert("يرجى كتابة موضوع أولاً");
            return;
        }
        
        document.getElementById('loadingDots').style.display = "block";
        addLog("النظام", `طلب تقرير من ${manager.title}`);
        
        const prompt = `${manager.prompt} اكتب تقريراً احترافياً مفصلاً باللغة العربية حول: ${topic}. استخدم عناوين فرعية ونقاطاً واضحة وقدم توصيات قابلة للتنفيذ.`;
        const response = await callGemini(prompt);
        
        streamText(response, 'finalOutput');
        addLog(manager.title, "تم تسليم التقرير بنجاح");
    };

    // 2. اجتماع طوارئ مع جميع المديرين
    const emergencyMeeting = async () => {
        const topic = document.getElementById('topicInput').value;
        if (!topic) {
            alert("يرجى كتابة موضوع الاجتماع أولاً");
            return;
        }
        
        const outputDiv = document.getElementById('finalOutput');
        outputDiv.innerHTML = `<i class="fas fa-users" style="color: var(--accent-blue);"></i> 🚨 <strong>جلسة طوارئ تنفيذية</strong><br>الموضوع: ${topic}<br><hr><br>`;
        document.getElementById('loadingDots').style.display = "block";
        addLog("النظام", `بدء جلسة طوارئ تنفيذية حول: ${topic}`);
        
        // جمع آراء أول 8 مديرين للسرعة (يمكن تعديل العدد)
        const opinions = [];
        for (let i = 0; i < Math.min(managers.length, 12); i++) {
            const m = managers[i];
            addLog(m.title, "يدلي برأيه في الاجتماع...");
            const prompt = `${m.prompt} قدم رأياً مختصراً (لا يزيد عن 3 أسطر) حول الموضوع: ${topic} من منظور اختصاصك.`;
            const response = await callGemini(prompt);
            opinions.push({ title: m.title, name: m.name, opinion: response });
            
            // تحديث الواجهة بشكل تدريجي
            outputDiv.innerHTML += `<div style="margin-bottom: 15px;"><span style="color: var(--accent-blue);">${m.title}:</span> ${response}</div>`;
            outputDiv.scrollTop = outputDiv.scrollHeight;
        }
        
        // إضافة القرار النهائي
        const finalPrompt = `بناءً على آراء المدراء التنفيذيين التالية، قم بصياغة قرار نهائي واحد واضح ومختصر (سطرين كحد أقصى) حول: ${topic}\n${opinions.map(o => `${o.title}: ${o.opinion}`).join('\n')}`;
        const finalDecision = await callGemini(finalPrompt);
        outputDiv.innerHTML += `<hr><div style="margin-top: 15px;"><span style="color: var(--accent-purple);">✨ القرار النهائي:</span> ${finalDecision}</div>`;
        
        document.getElementById('loadingDots').style.display = "none";
        addLog("اللجنة", "انتهت جلسة الطوارئ وتم اتخاذ القرارات");
    };
    
    document.getElementById('meetingBtn').onclick = emergencyMeeting;

    // ====================== نظام الدردشة ======================
    let currentChatManager = null;
    
    window.openChat = function(managerId) {
        currentChatManager = managers.find(m => m.id === managerId);
        if (!currentChatManager) return;
        
        document.getElementById('currentChatManager').innerText = `استشارة مع: ${currentChatManager.title}`;
        const chatWindow = document.getElementById('chatWindow');
        chatWindow.innerHTML = `<div class="msg msg-ai">مرحباً! أنا ${currentChatManager.name}، ${currentChatManager.title}. كيف يمكنني مساعدتك بخصوص ${currentChatManager.role}؟</div>`;
        document.getElementById('chatModal').style.display = 'flex';
        addLog(currentChatManager.title, "فتح نافذة دردشة");
    };
    
    window.closeChat = function() {
        document.getElementById('chatModal').style.display = 'none';
        currentChatManager = null;
    };
    
    document.getElementById('sendChat').onclick = async () => {
        const input = document.getElementById('chatInput');
        const userMessage = input.value.trim();
        if (!userMessage || !currentChatManager) return;
        
        const chatWindow = document.getElementById('chatWindow');
        chatWindow.innerHTML += `<div class="msg msg-user">${userMessage}</div>`;
        input.value = "";
        chatWindow.scrollTop = chatWindow.scrollHeight;
        
        addLog(currentChatManager.title, `سؤال: ${userMessage.substring(0, 50)}...`);
        
        const prompt = `${currentChatManager.prompt} أجب على سؤال المستخدم التالي بأسلوب مهني ومفيد: ${userMessage}`;
        const response = await callGemini(prompt);
        
        chatWindow.innerHTML += `<div class="msg msg-ai">${response}</div>`;
        chatWindow.scrollTop = chatWindow.scrollHeight;
        addLog(currentChatManager.title, "تم الرد على الاستفسار");
    };
    
    document.getElementById('chatInput').addEventListener('keypress', (e) => {
        if (e.key === 'Enter') document.getElementById('sendChat').click();
    });
    
    // إغلاق المودال عند الضغط خارجها
    window.onclick = (e) => {
        const modal = document.getElementById('chatModal');
        if (e.target === modal) closeChat();
    };
    
    addLog("النظام", "✅ المنصة جاهزة. تم تحميل " + managers.length + " مديراً تنفيذياً");
    
    // تحذير إذا لم يتم إدخال المفتاح
    if (API_KEY === "YOUR_API_KEY_HERE") {
        setTimeout(() => {
            addLog("⚠️ تنبيه", "لم يتم إدخال مفتاح Gemini API. يرجى الحصول على مفتاح مجاني من Google AI Studio وإضافته إلى الكود.");
        }, 1000);
    }
</script>
</body>
</html>
