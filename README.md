<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>مركز جمالك | التميز في التجميل والعناية</title>
    <!-- Font Awesome Icons (CDN) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <!-- Google Fonts: Tajawal (حديثة وجميلة) -->
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Tajawal', sans-serif;
            background: #fef9f5;
            color: #2e241f;
            line-height: 1.5;
        }

        /* تنسيق شريط التنقل */
        .navbar {
            background: rgba(255, 248, 241, 0.96);
            backdrop-filter: blur(2px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.03);
            padding: 0.9rem 2rem;
            position: sticky;
            top: 0;
            width: 100%;
            z-index: 1000;
            transition: all 0.3s ease;
            border-bottom: 1px solid #ffe0ce;
        }

        .nav-container {
            max-width: 1300px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .logo i {
            font-size: 2rem;
            color: #c67b4e;
        }

        .logo h1 {
            font-size: 1.8rem;
            font-weight: 800;
            color: #7e4a2e;
            letter-spacing: -0.5px;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links li a {
            text-decoration: none;
            font-weight: 600;
            font-size: 1.15rem;
            color: #4f3422;
            padding: 8px 0;
            transition: 0.2s;
            border-bottom: 2px solid transparent;
        }

        .nav-links li a.active,
        .nav-links li a:hover {
            color: #c2592b;
            border-bottom-color: #d97a4a;
        }

        /* المحتوى الرئيسي */
        .page {
            display: none;
            opacity: 0;
            transition: opacity 0.3s ease-in-out;
            max-width: 1300px;
            margin: 2rem auto;
            padding: 0 2rem 3rem;
        }

        .page.active-page {
            display: block;
            opacity: 1;
        }

        /* Hero الصفحة الرئيسية */
        .hero {
            background: linear-gradient(135deg, #fff2e9, #ffe6da);
            border-radius: 3rem;
            padding: 3rem 2.5rem;
            margin-bottom: 3rem;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            gap: 2rem;
            box-shadow: 0 12px 25px rgba(0,0,0,0.02);
        }

        .hero-text {
            flex: 1;
        }

        .hero-text h2 {
            font-size: 2.8rem;
            font-weight: 800;
            color: #7b3f1f;
            margin-bottom: 1rem;
        }

        .hero-text p {
            font-size: 1.2rem;
            color: #5f3c26;
            margin-bottom: 1.8rem;
        }

        .btn {
            background: #d seventeen;
            background-color: #d97a4a;
            border: none;
            padding: 0.8rem 1.8rem;
            border-radius: 60px;
            font-weight: bold;
            color: white;
            font-size: 1rem;
            font-family: 'Tajawal', sans-serif;
            cursor: pointer;
            transition: 0.2s;
            display: inline-block;
            text-decoration: none;
            box-shadow: 0 4px 8px rgba(0,0,0,0.05);
        }

        .btn-outline {
            background: transparent;
            border: 1.5px solid #d97a4a;
            color: #d97a4a;
        }

        .btn-outline:hover {
            background: #d97a4a;
            color: white;
        }

        .btn:hover {
            background-color: #b85f34;
            transform: translateY(-3px);
        }

        .hero-img {
            flex: 0.8;
            display: flex;
            justify-content: center;
        }

        .hero-img i {
            font-size: 12rem;
            color: #e0a17a;
            filter: drop-shadow(8px 10px 12px rgba(0,0,0,0.1));
        }

        /* بطاقات الخدمات */
        .section-title {
            font-size: 2rem;
            font-weight: 800;
            margin: 2rem 0 1.5rem;
            color: #4f2d18;
            position: relative;
            display: inline-block;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 2rem;
            margin-top: 1rem;
        }

        .service-card {
            background: white;
            border-radius: 2rem;
            padding: 2rem 1.5rem;
            text-align: center;
            transition: all 0.25s;
            box-shadow: 0 12px 24px rgba(0,0,0,0.04);
            border: 1px solid #fae3d4;
        }

        .service-card i {
            font-size: 3rem;
            color: #d97a4a;
            margin-bottom: 1rem;
        }

        .service-card h3 {
            font-size: 1.6rem;
            margin-bottom: 0.8rem;
        }

        .service-card p {
            color: #6b4c38;
        }

        /* صفحة الخدمات التفصيلية */
        .services-detailed {
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }

        .service-item {
            background: white;
            border-radius: 2rem;
            padding: 1.8rem;
            display: flex;
            flex-wrap: wrap;
            gap: 1.5rem;
            align-items: center;
            box-shadow: 0 4px 12px rgba(0,0,0,0.03);
            border: 1px solid #ffefe3;
        }

        .service-icon {
            font-size: 3rem;
            min-width: 80px;
            text-align: center;
            color: #c9764b;
        }

        .service-info {
            flex: 1;
        }

        .service-info h3 {
            font-size: 1.7rem;
            color: #7c482c;
        }

        .price {
            font-weight: 800;
            color: #aa693f;
            font-size: 1.2rem;
            margin-top: 0.5rem;
        }

        /* نموذج حجز / صفحة اتصل بنا */
        .contact-wrapper {
            display: flex;
            flex-wrap: wrap;
            gap: 2.5rem;
            margin-top: 1.5rem;
        }

        .contact-form {
            flex: 1.5;
            background: white;
            padding: 2rem;
            border-radius: 2rem;
            box-shadow: 0 12px 28px rgba(0,0,0,0.05);
        }

        .contact-info {
            flex: 1;
            background: #fff5ef;
            padding: 2rem;
            border-radius: 2rem;
        }

        .form-group {
            margin-bottom: 1.2rem;
        }

        input, select, textarea {
            width: 100%;
            padding: 0.9rem 1rem;
            border-radius: 1.5rem;
            border: 1px solid #eedbcb;
            font-family: 'Tajawal', sans-serif;
            background: #fffcf9;
            font-size: 1rem;
            transition: 0.2s;
        }

        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: #d97a4a;
            box-shadow: 0 0 0 3px rgba(217,122,74,0.2);
        }

        label {
            font-weight: 600;
            margin-bottom: 0.4rem;
            display: block;
            color: #472d1e;
        }

        .contact-info i {
            width: 35px;
            color: #d97a4a;
            font-size: 1.4rem;
        }

        .contact-info p {
            margin: 1rem 0;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .working-hours {
            margin-top: 1.2rem;
            border-top: 1px dashed #eccbbb;
            padding-top: 1rem;
        }

        footer {
            background: #f1e4db;
            text-align: center;
            padding: 1.5rem;
            margin-top: 3rem;
            color: #5f3a23;
            font-size: 0.9rem;
            border-top: 1px solid #ecd9cd;
        }

        /* ميديا */
        @media (max-width: 768px) {
            .nav-container {
                flex-direction: column;
                gap: 0.8rem;
            }
            .nav-links {
                gap: 1.2rem;
                flex-wrap: wrap;
                justify-content: center;
            }
            .hero-text h2 {
                font-size: 2rem;
            }
            .hero-img i {
                font-size: 6rem;
            }
            .hero {
                text-align: center;
                justify-content: center;
            }
        }

        .toast-msg {
            position: fixed;
            bottom: 2rem;
            left: 2rem;
            background: #2e241f;
            color: #fbeadf;
            padding: 0.8rem 1.5rem;
            border-radius: 3rem;
            font-weight: 500;
            z-index: 1100;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            opacity: 0;
            transition: 0.3s;
            pointer-events: none;
        }
    </style>
</head>
<body>

<div class="navbar">
    <div class="nav-container">
        <div class="logo">
            <i class="fas fa-spa"></i>
            <h1>مركز جمالك</h1>
        </div>
        <ul class="nav-links">
            <li><a href="#" data-page="home" class="nav-link active">الرئيسية</a></li>
            <li><a href="#" data-page="services" class="nav-link">خدماتنا</a></li>
            <li><a href="#" data-page="contact" class="nav-link">حجز & اتصل</a></li>
        </ul>
    </div>
</div>

<!-- الصفحة الرئيسية (الرئيسية) -->
<div id="homePage" class="page active-page">
    <div class="hero">
        <div class="hero-text">
            <h2>جمالك يبدأ من هنا ✨</h2>
            <p>أحدث تقنيات التجميل والعناية بالبشرة مع نخبة من الخبراء. استشاريون متخصصون وأجواء هادئة تمنحك تجربة لا تُنسى.</p>
            <a href="#" class="btn" id="heroBookBtn">احجزي موعدك الآن <i class="fas fa-arrow-left"></i></a>
        </div>
        <div class="hero-img">
            <i class="fas fa-female"></i>
        </div>
    </div>

    <div>
        <h2 class="section-title">خدماتنا الأكثر طلباً</h2>
        <div class="services-grid">
            <div class="service-card">
                <i class="fas fa-hand-sparkles"></i>
                <h3>عناية بالبشرة</h3>
                <p>جلسات تنظيف عميق وتقشير وترطيب فائق.</p>
            </div>
            <div class="service-card">
                <i class="fas fa-smile-wink"></i>
                <h3>مكياج احترافي</h3>
                <p>لإطلالة ساحرة تناسب المناسبات الخاصة.</p>
            </div>
            <div class="service-card">
                <i class="fas fa-cut"></i>
                <h3>قص & تسريحات</h3>
                <p>أحدث صيحات الشعر بتصاميم عصرية.</p>
            </div>
            <div class="service-card">
                <i class="fas fa-dharmachakra"></i>
                <h3>علاجات ليزر</h3>
                <p>إزالة الشعر نهائياً بتقنيات آمنة.</p>
            </div>
        </div>
        <div style="margin-top: 2rem; text-align: center;">
            <a href="#" data-page="services" class="btn btn-outline nav-link-internal">استكشف كل الخدمات <i class="fas fa-chevron-left"></i></a>
        </div>
    </div>
</div>

<!-- صفحة الخدمات التفصيلية -->
<div id="servicesPage" class="page">
    <h2 class="section-title">✨ جميع خدمات التجميل</h2>
    <div class="services-detailed">
        <div class="service-item">
            <div class="service-icon"><i class="fas fa-face-grin-tongue-squint"></i></div>
            <div class="service-info">
                <h3>تنظيف البشرة العميق</h3>
                <p>إزالة الشوائب والرؤوس السوداء مع تقشير إنزيمي وترطيب مكثف.</p>
                <div class="price">150 ر.س</div>
            </div>
        </div>
        <div class="service-item">
            <div class="service-icon"><i class="fas fa-magic"></i></div>
            <div class="service-info">
                <h3>مكياج سهرة / عروس</h3>
                <p>جلسة مكياج كامل بأحدث المنتجات العالمية ليدوم طويلاً.</p>
                <div class="price">250 ر.س</div>
            </div>
        </div>
        <div class="service-item">
            <div class="service-icon"><i class="fas fa-paint-brush"></i></div>
            <div class="service-info">
                <h3>صبغات & هايلايت</h3>
                <p>ألوان عصرية وتقنيات balayage من نخبة المصممين.</p>
                <div class="price">220 ر.س</div>
            </div>
        </div>
        <div class="service-item">
            <div class="service-icon"><i class="fas fa-hand-holding-heart"></i></div>
            <div class="service-info">
                <h3>مساج استرخائي</h3>
                <p>مساج سويدي وزيوت عطرية لتخفيف التوتر.</p>
                <div class="price">180 ر.س</div>
            </div>
        </div>
        <div class="service-item">
            <div class="service-icon"><i class="fas fa-feather-alt"></i></div>
            <div class="service-info">
                <h3>إزالة الشعر بالشمع / السكر</h3>
                <p>بشرة ناعمة لمدة طويلة بدون تهيج.</p>
                <div class="price">100 ر.س</div>
            </div>
        </div>
    </div>
    <div style="margin: 2rem 0; background:#fff0e8; border-radius: 2rem; padding: 1rem 2rem; text-align: center;">
        <p><i class="fas fa-gift"></i>   خصم 15% على أول جلسة عند الحجز من الموقع!</p>
    </div>
</div>

<!-- صفحة الحجز والاتصال -->
<div id="contactPage" class="page">
    <h2 class="section-title">📅 احجزي موعدك الآن</h2>
    <div class="contact-wrapper">
        <div class="contact-form">
            <form id="bookingForm">
                <div class="form-group">
                    <label><i class="fas fa-user"></i> الاسم الكامل</label>
                    <input type="text" id="fullName" placeholder="أدخل اسمك" required>
                </div>
                <div class="form-group">
                    <label><i class="fas fa-phone-alt"></i> رقم الهاتف</label>
                    <input type="tel" id="phone" placeholder="05xxxxxxxx" required>
                </div>
                <div class="form-group">
                    <label><i class="fas fa-calendar-alt"></i> التاريخ المفضل</label>
                    <input type="date" id="appointmentDate" required>
                </div>
                <div class="form-group">
                    <label><i class="fas fa-clock"></i> الوقت</label>
                    <select id="appointmentTime">
                        <option>10:00 صباحاً</option>
                        <option>12:00 ظهراً</option>
                        <option>14:00 عصراً</option>
                        <option>16:00 مساءً</option>
                        <option>18:00 مساءً</option>
                    </select>
                </div>
                <div class="form-group">
                    <label><i class="fas fa-concierge-bell"></i> الخدمة المرغوبة</label>
                    <select id="serviceSelect">
                        <option>تنظيف البشرة العميق</option>
                        <option>مكياج سهرة / عروس</option>
                        <option>صبغات & هايلايت</option>
                        <option>مساج استرخائي</option>
                        <option>إزالة الشعر بالشمع</option>
                    </select>
                </div>
                <div class="form-group">
                    <label><i class="fas fa-comment"></i> ملاحظات إضافية</label>
                    <textarea rows="3" placeholder="أي طلبات خاصة..."></textarea>
                </div>
                <button type="submit" class="btn" style="width: 100%;">إرسال طلب الحجز <i class="fas fa-paper-plane"></i></button>
            </form>
        </div>
        <div class="contact-info">
            <h3><i class="fas fa-address-card"></i> تواصل معنا</h3>
            <p><i class="fas fa-map-marker-alt"></i> الرياض - طريق الأمير محمد بن سلمان، برج الجمال</p>
            <p><i class="fas fa-phone"></i> 9200 12345</p>
            <p><i class="fas fa-envelope"></i> info@jamalik.sa</p>
            <div class="working-hours">
                <h4><i class="far fa-clock"></i> ساعات العمل</h4>
                <p>السبت - الخميس: 10 صباحاً - 10 مساءً</p>
                <p>الجمعة: مغلق (للراحة)</p>
                <p><i class="fab fa-instagram"></i> @jamalik_center &nbsp; <i class="fab fa-whatsapp"></i> 0551234567</p>
            </div>
        </div>
    </div>
</div>

<footer>
    <p>© 2025 مركز جمالك - التميز في خدمات التجميل بالرياض | جميع الحقوق محفوظة</p>
</footer>
<div id="toastMsg" class="toast-msg">تم بنجاح 🎀</div>

<script>
    // إدارة التنقل بين الصفحات الثلاث (Single Page Application behavior)
    const pages = {
        home: document.getElementById('homePage'),
        services: document.getElementById('servicesPage'),
        contact: document.getElementById('contactPage')
    };

    // تحديث الروابط النشطة
    function setActiveNav(pageId) {
        document.querySelectorAll('.nav-link').forEach(link => {
            const linkPage = link.getAttribute('data-page');
            if (linkPage === pageId) {
                link.classList.add('active');
            } else {
                link.classList.remove('active');
            }
        });
    }

    // إظهار صفحة محددة
    function showPage(pageId) {
        // إخفاء الكل
        Object.values(pages).forEach(page => {
            page.classList.remove('active-page');
        });
        // إظهار المطلوبة
        if (pages[pageId]) {
            pages[pageId].classList.add('active-page');
            setActiveNav(pageId);
            // تحديث عنوان الصفحة
            if (pageId === 'home') document.title = 'مركز جمالك | الرئيسية';
            else if (pageId === 'services') document.title = 'خدمات التجميل | مركز جمالك';
            else if (pageId === 'contact') document.title = 'حجز موعد | مركز جمالك';
        }
    }

    // إضافة مستمعي الأحداث للروابط الرئيسية
    document.querySelectorAll('.nav-link').forEach(link => {
        link.addEventListener('click', (e) => {
            e.preventDefault();
            const page = link.getAttribute('data-page');
            if (page && pages[page]) {
                showPage(page);
            }
        });
    });

    // أي روابط داخلية من أزرار (مثل "استكشف كل الخدمات")
    document.querySelectorAll('.nav-link-internal').forEach(btn => {
        btn.addEventListener('click', (e) => {
            e.preventDefault();
            const page = btn.getAttribute('data-page');
            if (page && pages[page]) showPage(page);
        });
    });

    // زر الحجز من الهيرو ينقل إلى صفحة الحجز
    const heroBookBtn = document.getElementById('heroBookBtn');
    if (heroBookBtn) {
        heroBookBtn.addEventListener('click', (e) => {
            e.preventDefault();
            showPage('contact');
        });
    }

    // Toast رسالة قصيرة
    function showToast(message, isError = false) {
        const toast = document.getElementById('toastMsg');
        toast.textContent = message || (isError ? 'حدث خطأ، حاول مجدداً' : 'تم بنجاح 🎀');
        toast.style.backgroundColor = isError ? '#b13e3e' : '#2e241f';
        toast.style.opacity = '1';
        setTimeout(() => {
            toast.style.opacity = '0';
        }, 2800);
    }

    // معالجة نموذج الحجز
    const bookingForm = document.getElementById('bookingForm');
    if (bookingForm) {
        bookingForm.addEventListener('submit', (e) => {
            e.preventDefault();
            const name = document.getElementById('fullName')?.value.trim();
            const phone = document.getElementById('phone')?.value.trim();
            const date = document.getElementById('appointmentDate')?.value;
            const time = document.getElementById('appointmentTime')?.value;
            const service = document.getElementById('serviceSelect')?.value;

            if (!name || !phone || !date) {
                showToast('الرجاء ملء جميع الحقول الأساسية (الاسم، الهاتف، التاريخ)', true);
                return;
            }
            if (phone.length < 9) {
                showToast('رقم الهاتف يجب أن يكون صحيحاً', true);
                return;
            }
            // محاكاة إرسال ناجح
            console.log(`حجز جديد: ${name}, ${phone}, ${date}, ${time}, خدمة: ${service}`);
            showToast(`شكراً ${name}! تم استلام طلب حجزك وسنقوم بالتواصل قريباً.`, false);
            bookingForm.reset();
            // يمكن إضافة أي إجراء إضافي
        });
    }

    // إضافة تاريخ الحد الأدنى اليوم (لا يمكن حجز موعد بالماضي)
    const dateInput = document.getElementById('appointmentDate');
    if (dateInput) {
        const today = new Date().toISOString().split('T')[0];
        dateInput.setAttribute('min', today);
    }

    // التأكد أن عند تحميل الصفحة نعرض الصفحة الرئيسية (حتى لو تم إعادة تحميل)
    // لكن ممكن أن يظل active-page كما هو، لكن للتأكد
    const currentActive = document.querySelector('.page.active-page');
    if (!currentActive || currentActive.id !== 'homePage') {
        // الافتراضي الصفحة الرئيسية
        showPage('home');
    } else {
        // تأكد من تفعيل النشاط الصحيح
        let activeId = 'home';
        if (document.getElementById('servicesPage').classList.contains('active-page')) activeId = 'services';
        else if (document.getElementById('contactPage').classList.contains('active-page')) activeId = 'contact';
        setActiveNav(activeId);
    }

    // بعض التفاعلات الإضافية : إضافة تأثير hover للبطاقات
    const cards = document.querySelectorAll('.service-card');
    cards.forEach(card => {
        card.addEventListener('mouseenter', () => {
            card.style.transform = 'translateY(-8px)';
        });
        card.addEventListener('mouseleave', () => {
            card.style.transform = 'translateY(0px)';
        });
    });
</script>
</body>
</html>
