# -
منصة لصناعة الدروس و المستندات بالذكاء الاصطناعي 
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>المساعد المهني - LALAOUNARIBAI</title>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        :root {
            /* الثيم الافتراضي: الأسود والذهبي الداكن (Luxury Dark) */
            --bg-color: #0d0d0d;
            --card-bg: rgba(26, 26, 26, 0.8); /* تأثير زجاجي خفيف */
            --primary-gold: #d4af37;
            --secondary-gold: #b8860b;
            --text-color: #e0e0e0;
            --accent-glow: rgba(212, 175, 55, 0.5);
            --transition-speed: 0.4s;
        }

        body {
            font-family: 'Tajawal', sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            margin: 0;
            padding-top: 20px;
            transition: background var(--transition-speed);
        }

        /* حاوية الزر المتوهج */
        .glow-btn-container {
            text-align: center;
            margin-bottom: 30px;
            position: relative;
            z-index: 10;
        }

        /* الزر المتوهج التفاعلي (رابط تيليجرام) */
        #dynamic-btn {
            display: inline-block;
            background: linear-gradient(45deg, var(--secondary-gold), var(--primary-gold));
            color: #000;
            text-decoration: none;
            padding: 15px 35px;
            border-radius: 50px;
            font-weight: 900;
            font-size: 1.2rem;
            box-shadow: 0 0 20px var(--accent-glow);
            transition: all 0.5s ease;
            animation: pulse 2s infinite;
        }

        #dynamic-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 0 40px var(--primary-gold);
        }

        @keyframes pulse {
            0% { box-shadow: 0 0 15px var(--accent-glow); }
            50% { box-shadow: 0 0 35px var(--primary-gold); }
            100% { box-shadow: 0 0 15px var(--accent-glow); }
        }

        /* قسم الأرشيف والسجلات */
        .archive-section {
            padding: 20px;
            max-width: 1100px;
            margin: auto;
        }

        .lesson-card {
            background: var(--card-bg);
            border: 1px solid var(--secondary-gold);
            backdrop-filter: blur(10px); /* تأثير الزجاج */
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .lesson-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.5);
            border-color: var(--primary-gold);
        }

        .btn-group button {
            margin-left: 8px;
            padding: 10px 18px;
            border-radius: 8px;
            border: 1px solid var(--primary-gold);
            background: transparent;
            color: var(--primary-gold);
            font-family: inherit;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .btn-group button:hover {
            background: var(--accent-glow);
            color: #fff;
        }

        .btn-edit { background: var(--primary-gold) !important; color: #000 !important; }
        .btn-edit:hover { background: var(--secondary-gold) !important; }

        /* تذييل الصفحة الملكي */
        footer {
            text-align: center;
            padding: 40px 20px;
            border-top: 1px solid #333;
            margin-top: 60px;
            background: linear-gradient(to top, #000, transparent);
        }

        .dev-names {
            color: var(--primary-gold);
            font-size: 1.4rem;
            font-weight: 900;
            text-shadow: 0 2px 4px rgba(0,0,0,0.8);
            margin: 10px 0;
        }
    </style>
</head>
<body>

    <div class="glow-btn-container">
        <a href="https://t.me/+213555545020" target="_blank" id="dynamic-btn">اضغط هنا إذا تريد دعم ومشاركت رأيك</a>
    </div>

    <div class="archive-section">
        <h2 style="color: var(--primary-gold); border-bottom: 2px solid var(--secondary-gold); padding-bottom: 10px; display: inline-block;">سجلات الدروس المصنوعة</h2>
        
        <div class="lesson-card">
            <div>
                <strong style="font-size: 1.4rem; color: #fff;">الدرس الأول: مدخل للكهرباء المعمارية</strong>
                <p style="font-size: 1rem; color: #aaa; margin-top: 8px;">التخصص: ELE0703 | التاريخ: اليوم</p>
            </div>
            <div class="btn-group">
                <button class="btn-edit" onclick="openEditor()">📝 تعديل</button>
                <button>📥 Word</button>
                <button>📥 PDF</button>
            </div>
        </div>
    </div>

    <footer>
        <p style="color: #aaa; font-size: 1.1rem; margin-bottom: 5px;">المصممان والمبرمجان:</p>
        <div class="dev-names">لعلاونة رضاالله (خنشلة) & لعلاونة عبد الرقيب (خنشلة)</div>
        <p style="color: #666; font-size: 0.9rem; margin-top: 15px;">
            حقوق نشر 2026 © التطبيق مدعوم من تطبيق <strong>LALAOUNARIBAI</strong>
        </p>
    </footer>

    <script>
        // منطق تبديل الزر المتوهج كل 4 ثوانٍ مع انتقال سلس
        const btn = document.getElementById('dynamic-btn');
        const text1 = "اضغط هنا إذا تريد دعم ومشاركت رأيك 💖";
        const text2 = "إذا واجهت مشاكل اضغط هنا 🛠️";
        let isFirstText = true;

        setInterval(() => {
            // تأثير اختفاء خفيف لتغيير النص بسلاسة
            btn.style.opacity = '0';
            setTimeout(() => {
                btn.innerText = isFirstText ? text2 : text1;
                btn.style.opacity = '1';
                isFirstText = !isFirstText;
            }, 300); // 300ms ليختفي ويظهر النص الجديد
        }, 4000);
    </script>
</body>
</html>
    <div id="editor-modal" style="display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.9); z-index: 1000; padding: 20px; box-sizing: border-box;">
        <div style="background: var(--card-bg); border: 2px solid var(--primary-gold); border-radius: 15px; max-width: 900px; margin: 20px auto; padding: 20px; height: 85vh; display: flex; flex-direction: column;">
            
            <div style="display: flex; justify-content: space-between; align-items: center; border-bottom: 1px solid #333; padding-bottom: 10px; margin-bottom: 15px;">
                <h3 style="color: var(--primary-gold); margin: 0;">المحرر الذكي - LALAOUNAKIB Smart Teacher</h3>
                <button onclick="closeEditor()" style="background: red; color: white; border: none; padding: 5px 15px; border-radius: 5px; cursor: pointer;">إغلاق X</button>
            </div>

            <div style="background: #111; padding: 10px; border-radius: 5px; margin-bottom: 10px; display: flex; gap: 10px;">
                <button onclick="document.execCommand('bold')" style="padding: 5px 10px; cursor: pointer; background: #333; color: white; border: 1px solid #555;">B عريض</button>
                <button onclick="document.execCommand('underline')" style="padding: 5px 10px; cursor: pointer; background: #333; color: white; border: 1px solid #555;">U تسطير</button>
                <button onclick="generateWithAI()" style="padding: 5px 10px; cursor: pointer; background: var(--primary-gold); color: black; border: none; font-weight: bold;">✨ توليد فقرة بالذكاء الاصطناعي</button>
            </div>

            <div id="rich-editor" contenteditable="true" style="flex-grow: 1; background: #fff; color: #000; padding: 20px; border-radius: 5px; overflow-y: auto; font-family: 'Arial', sans-serif; direction: rtl; text-align: right;">
                <h2 style="text-align: center;">مذكرة درس: مدخل للكهرباء المعمارية</h2>
                <p><strong>التخصص:</strong> ELE0703</p>
                <p><strong>الهدف الإجرائي:</strong> في نهاية الدرس، يجب أن يكون المتدرب قادراً على التعرف على مكونات الدارة الكهربائية البسيطة دون أخطاء.</p>
                <p><br>... (يمكنك التعديل هنا بحرية تامة كأنك في برنامج الوورد) ...</p>
            </div>

            <div style="margin-top: 15px; display: flex; gap: 10px; justify-content: flex-end;">
                <button onclick="exportToWord()" style="padding: 10px 20px; background: #2b579a; color: white; border: none; border-radius: 5px; cursor: pointer; font-weight: bold;">📥 حفظ كملف Word</button>
                <button onclick="exportToPDF()" style="padding: 10px 20px; background: #c62828; color: white; border: none; border-radius: 5px; cursor: pointer; font-weight: bold;">📥 حفظ كملف PDF</button>
            </div>
        </div>
    </div>

    <script>
        // --- 1. إعدادات مفاتيح الذكاء الاصطناعي (العقل المدبر) ---
        const aiModels = {
            pro: "gemini-3.1-pro-preview",          // لتحليل وإنتاج المذكرات
            vision: "gemini-3.1-flash-image-preview", // للمخططات والصور
            video: "veo-3.1-generate-preview"       // للمقاطع التوضيحية
        };

        // --- 2. التحكم في شاشة التعديل (المحرر) ---
        function openEditor() {
            document.getElementById('editor-modal').style.display = 'block';
            document.body.style.overflow = 'hidden'; // منع التمرير في الخلفية
        }

        function closeEditor() {
            document.getElementById('editor-modal').style.display = 'none';
            document.body.style.overflow = 'auto';
        }

        // --- 3. محاكاة التوليد بالذكاء الاصطناعي داخل المحرر ---
        function generateWithAI() {
            const editor = document.getElementById('rich-editor');
            const placeholderText = "\n[جاري استدعاء نموذج " + aiModels.pro + " لكتابة النشاط التقويمي...]\n";
            
            // إضافة نص مؤقت
            editor.innerHTML += `<p style="color: var(--primary-gold);"><i>${placeholderText}</i></p>`;
            
            // محاكاة تأخير الشبكة ثم كتابة النتيجة
            setTimeout(() => {
                editor.innerHTML = editor.innerHTML.replace(`<i>${placeholderText}</i>`, "");
                editor.innerHTML += `
                    <div style="border: 1px dashed #ccc; padding: 10px; margin-top: 10px;">
                        <strong>النشاط التقويمي (تم التوليد):</strong>
                        <ul>
                            <li>ارسم المخطط النظري لدارة إنارة بسيطة.</li>
                            <li>حدد وسائل الحماية اللازمة في ورشة التكوين المهني.</li>
                        </ul>
                    </div>
                `;
            }, 1500);
        }

        // --- 4. وظائف التصدير (Word & PDF) ---
        function exportToWord() {
            const content = document.getElementById('rich-editor').innerHTML;
            const preHtml = "<html xmlns:o='urn:schemas-microsoft-com:office:office' xmlns:w='urn:schemas-microsoft-com:office:word' xmlns='http://www.w3.org/TR/REC-html40'><head><meta charset='utf-8'><title>Export HTML To Doc</title></head><body>";
            const postHtml = "</body></html>";
            const html = preHtml + content + postHtml;

            const blob = new Blob(['\ufeff', html], {
                type: 'application/msword'
            });
            
            // إنشاء رابط التحميل الوهمي وتفعيله
            const url = 'data:application/vnd.ms-word;charset=utf-8,' + encodeURIComponent(html);
            const downloadLink = document.createElement("a");
            document.body.appendChild(downloadLink);
            downloadLink.href = url;
            downloadLink.download = 'مذكرة_المساعد_المهني.doc';
            downloadLink.click();
            document.body.removeChild(downloadLink);
        }

        function exportToPDF() {
            alert("لتفعيل تحميل PDF بشكل مثالي، سنقوم لاحقاً بربط مكتبة html2pdf.js. سيتم حفظ محتواك الآن!");
            // ملاحظة للمبرمج: يتم إضافة مكتبة خارجية لاحقاً لتحويل HTML إلى PDF بشكل دقيق.
        }
    </script>
// --- 5. محرك الذاكرة الدائمة (The Archive Core) ---
const PersonalAssistantDB = {
    saveLesson: function(lessonData) {
        let lessons = JSON.parse(localStorage.getItem('LALAOUNAKIB_Lessons')) || [];
        lessons.unshift(lessonData); // إضافة الدرس الجديد في البداية
        localStorage.setItem('LALAOUNAKIB_Lessons', JSON.stringify(lessons));
        this.renderLessons();
    },

    renderLessons: function() {
        const container = document.querySelector('.archive-section');
        const lessons = JSON.parse(localStorage.getItem('LALAOUNAKIB_Lessons')) || [];
        
        // المحافظة على العنوان وتحديث القائمة
        container.innerHTML = `<h2 style="color: var(--primary-gold); border-bottom: 2px solid var(--secondary-gold); padding-bottom: 10px; display: inline-block;">سجلات الدروس المصنوعة</h2>`;
        
        lessons.forEach((lesson, index) => {
            container.innerHTML += `
                <div class="lesson-card">
                    <div>
                        <strong style="font-size: 1.4rem; color: #fff;">${lesson.title}</strong>
                        <p style="font-size: 1rem; color: #aaa; margin-top: 8px;">التخصص: ${lesson.code} | التاريخ: ${lesson.date}</p>
                    </div>
                    <div class="btn-group">
                        <button class="btn-edit" onclick="openEditor(${index})">📝 تعديل</button>
                        <button onclick="exportToWord(${index})">📥 Word</button>
                    </div>
                </div>
            `;
        });
    }
};

// تشغيل النظام عند التحميل
window.onload = () => {
    PersonalAssistantDB.renderLessons();
    console.log("الوحش جاهز للعمل - تطوير لعلاونة رضاالله وعبد الرقيب");
};
