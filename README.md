<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>معرض أعمالي | GitHub</title>
    
    <!-- Font Awesome للأيقونات -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
    
    <style>
        /* ===== إعدادات عامة ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0d1117 0%, #161b22 100%);
            color: #c9d1d9;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .container {
            max-width: 1100px;
            width: 100%;
            background: rgba(22, 27, 34, 0.85);
            backdrop-filter: blur(10px);
            border-radius: 32px;
            padding: 40px 35px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.8);
            border: 1px solid #30363d;
            transition: 0.3s;
        }

        /* ===== الهيدر ===== */
        .header {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            margin-bottom: 40px;
        }

        .avatar {
            width: 130px;
            height: 130px;
            border-radius: 50%;
            background: linear-gradient(145deg, #238636, #2ea043);
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 60px;
            color: #fff;
            margin-bottom: 18px;
            box-shadow: 0 8px 30px rgba(46, 160, 67, 0.3);
            border: 3px solid #30363d;
        }

        .header h1 {
            font-size: 32px;
            font-weight: 700;
            background: linear-gradient(to right, #f0f6fc, #8b949e);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .header p {
            color: #8b949e;
            font-size: 18px;
            margin-top: 6px;
        }

        .badge-github {
            margin-top: 12px;
            background: #21262d;
            padding: 8px 22px;
            border-radius: 30px;
            font-size: 14px;
            border: 1px solid #30363d;
            display: inline-block;
            color: #58a6ff;
        }

        .badge-github i {
            margin-left: 8px;
        }

        /* ===== الشبكة ===== */
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 24px;
            margin: 35px 0 40px;
        }

        .card {
            background: #161b22;
            border-radius: 20px;
            padding: 28px 22px;
            border: 1px solid #30363d;
            transition: 0.25s ease;
            text-align: center;
        }

        .card:hover {
            transform: translateY(-6px);
            border-color: #58a6ff;
            box-shadow: 0 12px 30px -8px rgba(88, 166, 255, 0.15);
        }

        .card .icon {
            font-size: 44px;
            margin-bottom: 14px;
            display: inline-block;
        }

        .card h3 {
            font-size: 22px;
            font-weight: 600;
            margin-bottom: 8px;
            color: #f0f6fc;
        }

        .card p {
            color: #8b949e;
            font-size: 15px;
            line-height: 1.6;
        }

        /* ألوان خاصة لكل تقنية */
        .card.html .icon { color: #e34f26; }
        .card.css .icon { color: #1572b6; }
        .card.js .icon { color: #f7df1e; }
        .card.python .icon { color: #3776ab; }
        .card.flutter .icon { color: #02569b; }

        /* ===== قسم التطبيقات ===== */
        .apps-section {
            background: #0d1117;
            border-radius: 20px;
            padding: 28px 30px;
            border: 1px solid #30363d;
            margin-top: 10px;
        }

        .apps-section .title {
            font-size: 22px;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 18px;
        }

        .apps-section .title i {
            color: #f0883e;
        }

        .apps-list {
            display: flex;
            flex-wrap: wrap;
            gap: 18px;
            justify-content: center;
        }

        .app-item {
            background: #21262d;
            padding: 14px 25px;
            border-radius: 40px;
            border: 1px solid #30363d;
            display: flex;
            align-items: center;
            gap: 12px;
            font-size: 15px;
            transition: 0.2s;
        }

        .app-item i {
            color: #f0883e;
            font-size: 20px;
        }

        .app-item .status {
            background: #da3633;
            color: #fff;
            font-size: 11px;
            padding: 2px 12px;
            border-radius: 30px;
            font-weight: 600;
            letter-spacing: 0.3px;
        }

        .app-item:hover {
            border-color: #f0883e;
            background: #2d333b;
        }

        /* ===== الفوتر ===== */
        .footer {
            margin-top: 40px;
            text-align: center;
            border-top: 1px solid #21262d;
            padding-top: 25px;
            color: #8b949e;
            font-size: 14px;
        }

        .footer a {
            color: #58a6ff;
            text-decoration: none;
            margin: 0 8px;
        }

        .footer a:hover {
            text-decoration: underline;
        }

        .social-icons {
            margin-top: 12px;
            display: flex;
            justify-content: center;
            gap: 18px;
        }

        .social-icons a {
            color: #8b949e;
            font-size: 22px;
            transition: 0.2s;
        }

        .social-icons a:hover {
            color: #f0f6fc;
            transform: scale(1.1);
        }

        /* ===== متجاوب ===== */
        @media (max-width: 600px) {
            .container { padding: 25px 18px; }
            .header h1 { font-size: 26px; }
            .grid { grid-template-columns: 1fr; }
            .apps-list { flex-direction: column; align-items: center; }
            .app-item { width: 100%; justify-content: center; }
        }
    </style>
</head>
<body>

<div class="container">

    <!-- ===== الهيدر ===== -->
    <div class="header">
        <div class="avatar">
            <i class="fas fa-user-astronaut"></i>
        </div>
        <h1>أهلاً بك في ملفي</h1>
        <p>مطور تطبيقات ويب وهاتف محمول</p>
        <div class="badge-github">
            <i class="fab fa-github"></i> GitHub Profile
        </div>
    </div>

    <!-- ===== بطاقات المهارات ===== -->
    <div class="grid">
        <div class="card html">
            <div class="icon"><i class="fab fa-html5"></i></div>
            <h3>HTML5</h3>
            <p>هياكل ويب سليمة ودلالية (Semantic)</p>
        </div>
        <div class="card css">
            <div class="icon"><i class="fab fa-css3-alt"></i></div>
            <h3>CSS3</h3>
            <p>تصاميم عصرية مع Flexbox &amp; Grid</p>
        </div>
        <div class="card js">
            <div class="icon"><i class="fab fa-js"></i></div>
            <h3>JavaScript</h3>
            <p>تفاعل ووظائف ديناميكية على المتصفح</p>
        </div>
        <div class="card python">
            <div class="icon"><i class="fab fa-python"></i></div>
            <h3>Python</h3>
            <p>برمجة خلفية، أتمتة، وتحليل بيانات</p>
        </div>
        <div class="card flutter">
            <div class="icon"><i class="fas fa-mobile-alt"></i></div>
            <h3>Flutter</h3>
            <p>تطبيقات متعددة المنصات (Android &amp; iOS)</p>
        </div>
    </div>

    <!-- ===== قسم تطبيقات Flutter الجاهزة ===== -->
    <div class="apps-section">
        <div class="title">
            <i class="fas fa-rocket"></i>
            تطبيقات Flutter جاهزة
            <span style="font-size:14px; color:#8b949e; font-weight:400;">(لم تُرفع بعد)</span>
        </div>

        <div class="apps-list">
            <div class="app-item">
                <i class="fas fa-shopping-cart"></i>
                تطبيق متجر إلكتروني
                <span class="status">قريباً</span>
            </div>
            <div class="app-item">
                <i class="fas fa-calendar-check"></i>
                تطبيق مواعيد وحجوزات
                <span class="status">قريباً</span>
            </div>
            <div class="app-item">
                <i class="fas fa-dumbbell"></i>
                تطبيق لياقة بدنية
                <span class="status">قريباً</span>
            </div>
            <div class="app-item">
                <i class="fas fa-chart-line"></i>
                لوحة تحكم تحليلات
                <span class="status">قريباً</span>
            </div>
        </div>

        <p style="text-align:center; margin-top:20px; color:#8b949e; font-size:14px;">
            <i class="fas fa-code-branch" style="margin-left:8px;"></i>
            هذه التطبيقات مطورة بالكامل وسيتم رفعها قريباً على GitHub
        </p>
    </div>

    <!-- ===== الفوتر ===== -->
    <div class="footer">
        <p>
            <i class="fas fa-map-pin" style="margin-left:6px;"></i>
            متابعة وتواصل:
        </p>
        <div class="social-icons">
            <a href="#" title="GitHub"><i class="fab fa-github"></i></a>
            <a href="#" title="LinkedIn"><i class="fab fa-linkedin-in"></i></a>
            <a href="#" title="Twitter"><i class="fab fa-twitter"></i></a>
            <a href="#" title="YouTube"><i class="fab fa-youtube"></i></a>
        </div>
        <p style="margin-top:16px; font-size:13px;">
            &copy; 2026 · كل الحقوق محفوظة
        </p>
    </div>

</div>

<!-- ===== كود JavaScript بسيط ===== -->
<script>
    // عند تحميل الصفحة، تطبع رسالة في الكونسول
    document.addEventListener('DOMContentLoaded', function() {
        console.log('🚀 مرحباً! هذه صفحتي الشخصية على GitHub.');
        console.log('📱 لدي ' + document.querySelectorAll('.app-item').length + ' تطبيقات Flutter جاهزة للنشر!');
    });

    // تأثير إضافي: تغيير لون البطاقة عند النقر (مثال بسيط)
    const cards = document.querySelectorAll('.card');
    cards.forEach(card => {
        card.addEventListener('click', function() {
            this.style.borderColor = '#f0883e';
            setTimeout(() => {
                this.style.borderColor = '#30363d';
            }, 400);
        });
    });
</script>

</body>
</html>
