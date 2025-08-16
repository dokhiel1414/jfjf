<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>موقعي الشخصي</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700&family=Tajawal:wght@300;400;500;700&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Cairo', 'Tahoma', 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 2rem;
            margin-bottom: 2rem;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            text-align: center;
            animation: slideInFromTop 1s ease-out;
        }
        
        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: linear-gradient(45deg, #667eea, #764ba2);
            margin: 0 auto 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            color: white;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s ease;
        }
        
        .profile-img:hover {
            transform: scale(1.1) rotate(5deg);
        }
        
        h1 {
            color: #333;
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            font-family: 'Cairo', 'Tahoma', sans-serif;
            font-weight: 700;
        }
        
        .subtitle {
            color: #666;
            font-size: 1.2rem;
            margin-bottom: 1rem;
            font-family: 'Cairo', 'Tahoma', sans-serif;
            font-weight: 500;
        }
        
        .section {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 2rem;
            margin-bottom: 2rem;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            animation: slideInFromBottom 1s ease-out;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .section:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
        }
        
        .section h2 {
            color: #667eea;
            font-size: 2rem;
            margin-bottom: 1.5rem;
            text-align: center;
            font-family: 'Cairo', 'Tahoma', sans-serif;
            font-weight: 600;
            position: relative;
        }
        
        .section h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 50px;
            height: 3px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            border-radius: 2px;
        }
        
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }
        
        .skill-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 2rem;
            border-radius: 25px;
            text-align: center;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
            cursor: pointer;
            border: 2px solid transparent;
        }
        
        .skill-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.2) 0%, transparent 70%);
            opacity: 0;
            transition: opacity 0.4s ease;
            transform: scale(0);
        }
        
        .skill-card:hover::before {
            opacity: 1;
            transform: scale(1);
        }
        
        .skill-card:hover {
            transform: translateY(-15px) scale(1.05) rotateX(10deg);
            box-shadow: 0 20px 50px rgba(102, 126, 234, 0.5);
            border-color: rgba(255, 255, 255, 0.3);
        }
        
        .skill-card h3 {
            font-family: 'Cairo', 'Tahoma', sans-serif;
            font-weight: 700;
            font-size: 1.4rem;
            margin-bottom: 1rem;
            position: relative;
            z-index: 2;
        }
        
        .skill-card p {
            font-family: 'Cairo', 'Tahoma', sans-serif;
            font-size: 1rem;
            position: relative;
            z-index: 2;
            opacity: 0.9;
        }
        
        .contact-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }
        
        .contact-item {
            background: linear-gradient(135deg, #ffffff 0%, #f8f9fa 100%);
            padding: 2rem;
            border-radius: 20px;
            text-align: center;
            border: 3px solid transparent;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }
        
        .contact-item::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(102, 126, 234, 0.1), transparent);
            transition: left 0.6s ease;
        }
        
        .contact-item:hover::after {
            left: 100%;
        }
        
        .contact-item:hover {
            border-color: #667eea;
            transform: scale(1.08) translateY(-10px) rotateY(8deg);
            box-shadow: 0 15px 40px rgba(102, 126, 234, 0.4);
            background: linear-gradient(135deg, #fff 0%, #f0f2ff 100%);
        }
        
        .contact-item h3 {
            font-family: 'Cairo', 'Tahoma', sans-serif;
            font-weight: 600;
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: #333;
        }
        
        .contact-item p {
            font-family: 'Cairo', 'Tahoma', sans-serif;
            color: #666;
            font-size: 1rem;
        }
        
        .btn {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 16px 40px;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1.2rem;
            font-weight: 600;
            font-family: 'Cairo', 'Tahoma', sans-serif;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            text-decoration: none;
            display: inline-block;
            margin: 15px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 8px 25px rgba(102, 126, 234, 0.4);
            border: 2px solid transparent;
        }
        
        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.4), transparent);
            transition: left 0.6s ease;
        }
        
        .btn:hover::before {
            left: 100%;
        }
        
        .btn:hover {
            transform: translateY(-8px) scale(1.1);
            box-shadow: 0 15px 35px rgba(102, 126, 234, 0.7);
            background: linear-gradient(135deg, #7b68ee 0%, #8b5cf6 100%);
            border-color: rgba(255, 255, 255, 0.2);
        }
        
        .btn:active {
            transform: translateY(-2px) scale(1.05);
            animation: buttonPulse 0.3s ease;
        }
        
        .ripple-effect {
            position: absolute;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.8);
            animation: ripple 0.8s linear;
            pointer-events: none;
        }
        
        footer {
            text-align: center;
            color: white;
            padding: 2rem;
            font-size: 1rem;
            font-family: 'Cairo', 'Tahoma', sans-serif;
            text-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
        }
        
        @keyframes ripple {
            0% {
                transform: scale(0);
                opacity: 1;
            }
            100% {
                transform: scale(4);
                opacity: 0;
            }
        }
        
        @keyframes buttonPulse {
            0%, 100% { transform: translateY(-2px) scale(1.05); }
            50% { transform: translateY(-2px) scale(1.1); }
        }
        
        @keyframes slideInFromTop {
            0% {
                opacity: 0;
                transform: translateY(-50px) rotateX(10deg);
            }
            100% {
                opacity: 1;
                transform: translateY(0) rotateX(0deg);
            }
        }
        
        @keyframes slideInFromBottom {
            0% {
                opacity: 0;
                transform: translateY(50px) rotateX(-10deg);
            }
            100% {
                opacity: 1;
                transform: translateY(0) rotateX(0deg);
            }
        }
        
        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-5px) rotateZ(1deg); }
            75% { transform: translateX(5px) rotateZ(-1deg); }
        }
        
        @keyframes glow {
            0%, 100% { box-shadow: 0 15px 35px rgba(102, 126, 234, 0.7); }
            50% { box-shadow: 0 15px 35px rgba(139, 92, 246, 0.9); }
        }
        
        @media (max-width: 768px) {
            .container {
                padding: 15px;
            }
            
            h1 {
                font-size: 2rem;
            }
            
            .section {
                padding: 1.5rem;
            }
            
            .skills-grid {
                grid-template-columns: 1fr;
            }
            
            .contact-info {
                grid-template-columns: 1fr;
            }
            
            .btn {
                padding: 14px 30px;
                font-size: 1.1rem;
            }
            
            .contact-item:hover,
            .skill-card:hover {
                transform: scale(1.02) translateY(-5px);
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="profile-img">🚀</div>
            <h1>اسمك هنا</h1>
            <p class="subtitle">مطور ويب محترف | مصمم إبداعي | مبرمج متميز</p>
            <p>مرحباً بك في موقعي الشخصي. أنا شغوف بالتكنولوجيا وأحب إنشاء تجارب رقمية استثنائية تترك أثراً إيجابياً.</p>
        </header>

        <section class="section">
            <h2>نبذة عني</h2>
            <p style="text-align: center; font-size: 1.1rem; line-height: 1.8;">أنا مطور ويب متحمس ومبدع، أملك خبرة واسعة في تطوير الحلول الرقمية المبتكرة. أسعى دائماً لتعلم أحدث التقنيات وتطوير مهاراتي لتقديم أفضل الخدمات والحلول للعملاء. أؤمن بأن التكنولوجيا يجب أن تكون في خدمة الإنسان وتحسين جودة حياته.</p>
        </section>

        <section class="section">
            <h2>مهاراتي التقنية</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <h3>🌐 تطوير الواجهات الأمامية</h3>
                    <p>إنشاء واجهات مستخدم تفاعلية وجميلة باستخدام أحدث التقنيات والمكتبات العصرية</p>
                </div>
                <div class="skill-card">
                    <h3>⚙️ البرمجة الخلفية</h3>
                    <p>تطوير أنظمة خلفية قوية وآمنة لدعم التطبيقات والمواقع الإلكترونية</p>
                </div>
                <div class="skill-card">
                    <h3>🎨 التصميم الرقمي</h3>
                    <p>تصميم هويات بصرية مميزة وواجهات مستخدم بديهية وجذابة</p>
                </div>
                <div class="skill-card">
                    <h3>📱 التطبيقات المحمولة</h3>
                    <p>تطوير تطبيقات محمولة سريعة الاستجابة تعمل على جميع المنصات</p>
                </div>
            </div>
        </section>

        <section class="section">
            <h2>الخدمات التي أقدمها</h2>
            <div class="contact-info">
                <div class="contact-item">
                    <h3>💻 تطوير المواقع الكاملة</h3>
                    <p>إنشاء مواقع ويب احترافية متكاملة مع أنظمة إدارة محتوى متقدمة</p>
                </div>
                <div class="contact-item">
                    <h3>🛒 المتاجر الإلكترونية</h3>
                    <p>بناء متاجر إلكترونية آمنة ومتطورة مع أنظمة دفع متعددة</p>
                </div>
                <div class="contact-item">
                    <h3>🚀 تحسين الأداء</h3>
                    <p>تحسين سرعة المواقع وتحسين محركات البحث SEO للوصول لأفضل النتائج</p>
                </div>
                <div class="contact-item">
                    <h3>🎯 الاستشارات التقنية</h3>
                    <p>تقديم استشارات تقنية متخصصة لاختيار أفضل الحلول التكنولوجية</p>
                </div>
            </div>
        </section>

        <section class="section">
            <h2>تواصل معي</h2>
            <div class="contact-info">
                <div class="contact-item">
                    <h3>📧 البريد الإلكتروني</h3>
                    <p>your.email@example.com</p>
                </div>
                <div class="contact-item">
                    <h3>📱 رقم الجوال</h3>
                    <p>+966 50 000 0000</p>
                </div>
                <div class="contact-item">
                    <h3>📍 العنوان</h3>
                    <p>الرياض، المملكة العربية السعودية</p>
                </div>
                <div class="contact-item">
                    <h3>🌐 منصات التواصل</h3>
                    <p>LinkedIn • Twitter • GitHub • Instagram</p>
                </div>
            </div>
            
            <div style="text-align: center; margin-top: 3rem;">
                <a href="mailto:your.email@example.com" class="btn">📩 راسلني الآن</a>
                <a href="tel:+966500000000" class="btn">📞 اتصل بي</a>
            </div>
        </section>
    </div>

    <footer>
        <p>&copy; 2024 اسمك هنا - جميع الحقوق محفوظة | تم التطوير بكل حب وإتقان 💜</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // تأثيرات الظهور عند التمرير
            const sections = document.querySelectorAll('.section');
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0) rotateX(0deg)';
                    }
                });
            }, { threshold: 0.1 });

            sections.forEach(section => {
                section.style.opacity = '0';
                section.style.transform = 'translateY(30px) rotateX(-5deg)';
                section.style.transition = 'all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275)';
                observer.observe(section);
            });

            // تأثيرات الأزرار المتقدمة
            const buttons = document.querySelectorAll('.btn');
            buttons.forEach(button => {
                // تأثير التمرير
                button.addEventListener('mouseenter', function() {
                    this.style.animation = 'glow 2s infinite alternate';
                });
                
                button.addEventListener('mouseleave', function() {
                    this.style.animation = '';
                });
                
                // تأثير النقر مع الموجات
                button.addEventListener('click', function(e) {
                    e.preventDefault();
                    
                    // إنشاء تأثير الموجة
                    const ripple = document.createElement('span');
                    const rect = this.getBoundingClientRect();
                    const size = Math.max(rect.width, rect.height);
                    const x = e.clientX - rect.left - size / 2;
                    const y = e.clientY - rect.top - size / 2;
                    
                    ripple.style.width = ripple.style.height = size + 'px';
                    ripple.style.left = x + 'px';
                    ripple.style.top = y + 'px';
                    ripple.classList.add('ripple-effect');
                    
                    this.appendChild(ripple);
                    
                    // تأثير الاهتزاز
                    this.style.animation = 'shake 0.5s ease, buttonPulse 0.3s ease';
                    
                    // تنفيذ الرابط بعد التأثير
                    setTimeout(() => {
                        if (this.href) {
                            window.location.href = this.href;
                        }
                        ripple.remove();
                        this.style.animation = '';
                    }, 600);
                });
            });
            
            // تأثيرات البطاقات المتقدمة
            const allCards = document.querySelectorAll('.skill-card, .contact-item');
            allCards.forEach(card => {
                card.addEventListener('mouseenter', function() {
                    // إضافة توهج للبطاقات المجاورة
                    const siblings = Array.from(this.parentNode.children);
                    siblings.forEach(sibling => {
                        if (sibling !== this) {
                            sibling.style.opacity = '0.7';
                            sibling.style.transform = 'scale(0.95)';
                        }
                    });
                });
                
                card.addEventListener('mouseleave', function() {
                    // إرجاع البطاقات لحالتها الطبيعية
                    const siblings = Array.from(this.parentNode.children);
                    siblings.forEach(sibling => {
                        sibling.style.opacity = '1';
                        sibling.style.transform = 'scale(1)';
                    });
                });
                
                card.addEventListener('click', function() {
                    this.style.animation = 'buttonPulse 0.6s ease';
                    setTimeout(() => {
                        this.style.animation = '';
                    }, 600);
                });
            });

            // تأثير خاص للصورة الشخصية
            const profileImg = document.querySelector('.profile-img');
            let rotationAngle = 0;
            
            profileImg.addEventListener('click', function() {
                rotationAngle += 360;
                this.style.transform = `scale(1.2) rotate(${rotationAngle}deg)`;
                setTimeout(() => {
                    this.style.transform = 'scale(1) rotate(0deg)';
                }, 1000);
            });

            // تأثير تفاعل الماوس مع الخلفية
            document.addEventListener('mousemove', function(e) {
                const cursor = document.createElement('div');
                cursor.style.position = 'fixed';
                cursor.style.left = e.clientX + 'px';
                cursor.style.top = e.clientY + 'px';
                cursor.style.width = '10px';
                cursor.style.height = '10px';
                cursor.style.background = 'rgba(102, 126, 234, 0.3)';
                cursor.style.borderRadius = '50%';
                cursor.style.pointerEvents = 'none';
                cursor.style.animation = 'ripple 1s linear forwards';
                cursor.style.zIndex = '1000';
                
                document.body.appendChild(cursor);
                
                setTimeout(() => {
                    cursor.remove();
                }, 1000);
            });
        });
    </script>
</body>
</html>
