<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MQI 量元計畫 | 台灣學生跨領域科技團隊 | AI, 模擬器, 系統架構</title>
    <meta name="description" content="MetaQuant Initiative (MQI) 是全臺第一個由國高中生主導的跨領域科技團隊，專注於 AI、遊戲模擬器、系統架構等前沿專案。用創意翻轉未來。">
    <meta name="keywords" content="MQI, 量元計畫, 學生團隊, 程式設計, 科技, AI, 遊戲模擬器, 系統架構, 台灣, 國高中生">
    <link rel="canonical" href="https://MQI.qzz.io/"> 
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    
    <style>
        /* ====================================
           1. 基本与重设
           ==================================== */
        :root {
            /* 品牌颜色定义 */
            --color-primary: #004d99; /* 深蓝 */
            --color-secondary: #008cff; /* 亮蓝 */
            --color-accent: #ffcc00; /* 强调黄 */
            --color-text: #333;
            --color-bg-dark: #002d5c;
            --color-bg-footer: #1a1a1a;
            --color-hover-light: #f0f8ff;
            --shadow-nav: 0 4px 6px rgba(0,0,0,0.1);
        }

        html {
            scroll-behavior: smooth;
        }

        body { 
            font-family: '微軟正黑體', 'Microsoft JhengHei', sans-serif; 
            margin: 0; 
            padding: 0; 
            background-color: #ffffff;
            color: var(--color-text); 
            line-height: 1.6;
        }
        
        a {
            text-decoration: none;
            color: var(--color-secondary);
        }

        /* ====================================
           2. 导航列 (Navbar) - Glassmorphism
           ==================================== */
        .navbar { 
            display: flex; 
            justify-content: center; 
            align-items: center;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 15px 0;
            
            /* Glassmorphism 核心 */
            background-color: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(12px); /* 略微增强模糊 */
            -webkit-backdrop-filter: blur(12px);
            box-shadow: var(--shadow-nav);
            z-index: 1000;
        }
        
        .nav-logo {
            color: var(--color-primary);
            font-size: 1.3em;
            font-weight: 800;
            margin-right: 30px;
        }
        
        .nav-link { 
            color: var(--color-primary);
            padding: 8px 18px; 
            font-weight: 600;
            font-size: 0.95em;
            transition: color 0.3s, background-color 0.3s;
            border-radius: 6px;
        }
        
        .nav-link:hover { 
            color: white; 
            background-color: var(--color-secondary);
        }

        /* ====================================
           3. 宣傳区 (Hero) - 粒子光影
           ==================================== */
        .hero { 
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative;
            overflow: hidden;
            
            background: var(--color-bg-dark); 
            color: white;
            padding: 100px 20px 40px;
            text-align: center; 
        }

        /* 粒子/光影效果 */
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(0, 140, 255, 0.25) 0%, rgba(0, 45, 92, 0) 70%);
            animation: pulse 18s infinite alternate; /* 略微放慢动画 */
            z-index: 1;
        }
        @keyframes pulse {
            0% { transform: scale(1.0); opacity: 0.8; }
            100% { transform: scale(1.6); opacity: 0.5; }
        }

        .hero > * {
            position: relative;
            z-index: 2;
        }

        .hero h1 { 
            font-size: clamp(2em, 5vw, 3.5em); /* 响应式字体 */
            margin-top: 0;
            max-width: 900px;
            text-shadow: 0 0 12px rgba(0, 140, 255, 0.8);
        }
        
        .hero-stats {
            margin: 30px 0;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* 计数器样式 */
        .count-label {
            font-size: 1.1em;
            color: rgba(255, 255, 255, 0.8); 
            margin-bottom: 5px;
        }
        .count-display {
            font-size: 5.5em; /* 略微放大 */
            font-weight: 800;
            color: var(--color-accent);
            line-height: 1;
        }
        .count-plus {
            font-size: 4em;
            font-weight: 800;
            color: var(--color-accent);
            vertical-align: super; /* 调整对齐 */
        }


        /* ====================================
           4. 通用内容区
           ==================================== */
        .main-container { 
            width: 90%; /* 增加宽度 */
            max-width: 1200px; /* 增加最大宽度 */
            margin: 0 auto;
            overflow: hidden; 
        }

        .section { 
            background: white; 
            padding: 80px 0; /* 增加垂直内边距 */
            margin-bottom: 0; 
        }
        
        .section-header {
            border-bottom: 3px solid var(--color-secondary);
            padding-bottom: 10px;
            margin-top: 0;
            color: var(--color-primary);
            font-size: 2em;
            margin-bottom: 35px;
        }

        /* 滚动淡入效果 */
        .section {
            opacity: 0;
            transform: translateY(40px);
            transition: opacity 1.2s ease-out, transform 1.2s ease-out;
        }
        .section.fade-in {
            opacity: 1;
            transform: translateY(0);
        }

        /* ====================================
           5. 专案列表 (Projects)
           ==================================== */
        .project-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); /* 响应式网格 */
            gap: 20px;
        }
        
        .project-card {
            padding: 20px;
            border: 1px solid #ddd;
            border-radius: 8px;
            cursor: pointer;
            transition: box-shadow 0.3s, transform 0.3s;
            position: relative;
            overflow: hidden;
            background-color: white;
        }
        
        /* Hover 效果：卡片抬升与边框强调 */
        .project-card:hover {
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
            transform: translateY(-5px);
        }
        
        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 4px;
            height: 100%;
            background-color: var(--color-secondary); /* 强调色条 */
            transition: width 0.3s;
        }
        
        .project-card:hover::before {
            width: 8px;
        }

        .project-card-header {
            margin: 0 0 10px 0;
            color: var(--color-primary);
            font-size: 1.3em;
        }
        
        .project-description {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.5s ease-in-out, opacity 0.5s;
            opacity: 0;
            padding-top: 5px;
            color: #555;
        }
        
        .project-card.expanded .project-description {
            max-height: 200px; /* 足够显示内容的固定高度 */
            opacity: 1;
        }

        /* ====================================
           6. 社交链接 (Social Links)
           ==================================== */
        .social-links {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            margin-top: 30px;
        }

        .social-links a {
            display: inline-flex;
            align-items: center;
            background-color: var(--color-secondary);
            color: white;
            padding: 12px 25px;
            margin: 10px;
            text-decoration: none;
            border-radius: 30px;
            font-weight: 600;
            transition: background-color 0.3s, box-shadow 0.3s, transform 0.3s;
        }
        
        .social-links a i {
            margin-right: 8px;
            font-size: 1.2em;
        }

        .social-links a:hover {
            background-color: var(--color-primary);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            transform: translateY(-3px);
        }

        /* ====================================
           7. 頁腳 (Footer)
           ==================================== */
        .footer { 
            background-color: var(--color-bg-footer);
            color: #ccc; 
            text-align: center; 
            padding: 35px 20px;
            font-size: 0.9em;
        }

        /* ====================================
           8. 响应式 (Responsive)
           ==================================== */
        @media (max-width: 768px) {
            .navbar {
                padding: 10px 0;
            }
            .nav-link {
                padding: 6px 10px;
                font-size: 0.9em;
            }
            .nav-logo {
                margin-right: 15px;
                font-size: 1.1em;
            }
            
            .hero h1 {
                font-size: 2em;
            }
            .count-display {
                font-size: 4em;
            }
            .count-plus {
                font-size: 3em;
            }
            
            .section {
                padding: 50px 0;
            }
            .section-header {
                font-size: 1.6em;
            }
            
            .project-list {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>

    <nav class="navbar">
        <a href="#top" class="nav-logo">MQI 量元計畫</a>
        
        <a href="#about" class="nav-link">團隊介紹</a>
        <a href="#projects" class="nav-link">專案成果</a>
        <a href="#vision" class="nav-link">核心理念</a>
        <a href="#contact" class="nav-link">聯絡我們</a>
    </nav>

    <div class="main-content">
        <section class="hero" id="top">
            <h1>全臺第一個由國高中生主導的跨世代科技革命。</h1>
            
            <div class="hero-stats">
                <p class="count-label">活躍技術成員總數</p>
                <span class="count-display"><span id="member-count">0</span></span><span class="count-plus">+</span>
            </div>
            
            <p style="font-size: 1.1em; max-width: 600px; opacity: 0.9;">我們是 MetaQuant Initiative (MQI) 量元計畫，點燃年輕世代的科技火花，**年齡不是限制，而是創造力的起點。**</p>
        </section>

        <div class="main-container">
            <section id="about" class="section">
                <h3 class="section-header">關於我們：定義新世代科技力量</h3>
                <p>我們是一群來自臺灣各地的國中生與高中生，因為對前沿科技抱持著共同的熱忱與好奇心而聚集。</p>
                <p>不同於制式的教育框架，在 MQI，我們互相挑戰、激發潛能，將腦海中的創意大膽付諸實踐。我們的團隊定位是明確且堅定的：**「全台第一個由國高中生主導的跨領域科技團隊」**。</p>
                <p>我們樂於突破傳統思維，以創新的方式解決問題，讓全世界看到臺灣年輕人的科技潛能！</p>
            </section>

            <section id="projects" class="section">
                <h3 class="section-header">我們的挑戰與專案成果 🔬🎮</h3>
                <p>在量元計畫中，我們將學習到的理論知識轉化為實際的應用成果。我們的專案涵蓋多個前瞻領域，展現了團隊在多元科技整合上的雄心：</p>

                <div class="project-list">
                    
                    <div class="project-card" data-project-id="1">
                        <h4 class="project-card-header"><i class="fas fa-vr-cardboard"></i> 沉浸式應用開發</h4>
                        <div class="project-description"> 
                            <p>嘗試打造高性能的**遊戲模擬器**，深入理解軟硬體架構與優化，推動互動體驗的新界限。</p>
                        </div>
                    </div>

                    <div class="project-card" data-project-id="2">
                        <h4 class="project-card-header"><i class="fas fa-robot"></i> 人工智慧與數據分析</h4>
                        <div class="project-description"> 
                            <p>開發實用的 **AI 工具**，從機器學習模型到自動化解決方案，應對現實世界的挑戰。</p>
                        </div>
                    </div>

                    <div class="project-card" data-project-id="3">
                        <h4 class="project-card-header"><i class="fas fa-sitemap"></i> 系統架構與資料整合</h4>
                        <div class="project-description"> 
                            <p>建構穩健高效的資料系統與後端服務，奠定未來數位基礎，確保專案具備規模化能力。</p>
                        </div>
                    </div>
                </div>
                
                <p style="margin-top: 30px;">每一個專案都是我們挑戰自我、追求卓越的證明。你會親眼見證學生的創意想法如何蛻變成真實可用的作品。</p>
            </section>

            <section id="vision" class="section">
                <h3 class="section-header">核心理念：用創意翻轉未來 🌟</h3>
                <p>我們的最終願景，就是成為**「MetaQuant Initiative：下一代的科技解方」**。</p>
                <p>我們相信透過不斷的學習、協作與實踐，能夠真正做到**「量元計畫– 用創意翻轉未來」**。我們歡迎所有關注科技、渴望創新的朋友，一同追蹤量元計畫MQI，見證這股蓬勃而充滿活力的年輕世代科技火花！</p>
            </section>

            <section id="contact" class="section">
                <h3 class="section-header">聯絡與追蹤我們</h3>
                <p style="text-align: center;">想了解更多資訊或尋求合作？請點擊下方連結，透過我們的社群媒體追蹤最新的動態：</p>
                
                <div class="social-links">
                    <a href="https://www.facebook.com/share/15LSr9zVen6/" target="_blank">
                        <i class="fab fa-facebook-f"></i> Facebook
                    </a>
<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MQI 量元計畫 | 台灣學生跨領域科技團隊 | AI, 模擬器, 系統架構</title>
    <meta name="description" content="MetaQuant Initiative (MQI) 是全臺第一個由國高中生主導的跨領域科技團隊，專注於 AI、遊戲模擬器、系統架構等前沿專案。用創意翻轉未來。">
    <meta name="keywords" content="MQI, 量元計畫, 學生團隊, 程式設計, 科技, AI, 遊戲模擬器, 系統架構, 台灣, 國高中生">
    <link rel="canonical" href="https://MQI.qzz.io/"> 
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    
    <style>
        /* ====================================
           1. 基本与重设
           ==================================== */
        :root {
            /* 品牌颜色定义 */
            --color-primary: #004d99; /* 深蓝 */
            --color-secondary: #008cff; /* 亮蓝 */
            --color-accent: #ffcc00; /* 强调黄 */
            --color-text: #333;
            --color-bg-dark: #002d5c;
            --color-bg-footer: #1a1a1a;
            --color-hover-light: #f0f8ff;
            --shadow-nav: 0 4px 6px rgba(0,0,0,0.1);
        }

        html {
            scroll-behavior: smooth;
        }

        body { 
            /* 字体栈优化，兼容不同系统 */
            font-family: '微軟正黑體', 'Microsoft JhengHei', 'PingFang TC', 'Apple LiGothic', sans-serif; 
            margin: 0; 
            padding: 0; 
            background-color: #ffffff;
            color: var(--color-text); 
            line-height: 1.6;
        }
        
        a {
            text-decoration: none;
            color: var(--color-secondary);
        }

        /* ====================================
           2. 导航列 (Navbar) - Glassmorphism
           ==================================== */
        .navbar { 
            display: flex; 
            justify-content: center; 
            align-items: center;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 15px 0;
            
            /* Glassmorphism 核心 */
            /* 修正：增加透明度，确保背景可见度 */
            background-color: rgba(255, 255, 255, 0.5); 
            backdrop-filter: blur(12px); 
            -webkit-backdrop-filter: blur(12px);
            box-shadow: var(--shadow-nav);
            z-index: 1000;
        }
        
        .nav-logo {
            color: var(--color-primary);
            font-size: 1.3em;
            font-weight: 800;
            margin-right: 30px;
        }
        
        .nav-link { 
            color: var(--color-primary);
            padding: 8px 18px; 
            font-weight: 600;
            font-size: 0.95em;
            transition: color 0.3s, background-color 0.3s;
            border-radius: 6px;
        }
        
        .nav-link:hover { 
            color: white; 
            background-color: var(--color-secondary);
        }

        /* ====================================
           3. 宣傳区 (Hero) - 粒子光影
           ==================================== */
        .hero { 
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative;
            overflow: hidden;
            
            background: var(--color-bg-dark); 
            color: white;
            padding: 100px 20px 40px;
            text-align: center; 
        }

        /* 粒子/光影效果 */
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(0, 140, 255, 0.25) 0%, rgba(0, 45, 92, 0) 70%);
            animation: pulse 18s infinite alternate; 
            z-index: 1;
        }
        @keyframes pulse {
            0% { transform: scale(1.0); opacity: 0.8; }
            100% { transform: scale(1.6); opacity: 0.5; }
        }

        .hero > * {
            position: relative;
            z-index: 2;
        }

        .hero h1 { 
            font-size: clamp(2em, 5vw, 3.5em); 
            margin-top: 0;
            max-width: 900px;
            text-shadow: 0 0 12px rgba(0, 140, 255, 0.8);
        }
        
        .hero-stats {
            margin: 30px 0;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* 计数器样式 */
        .count-label {
            font-size: 1.1em;
            color: rgba(255, 255, 255, 0.8); 
            margin-bottom: 5px;
        }
        .count-display {
            font-size: 5.5em; 
            font-weight: 800;
            color: var(--color-accent);
            line-height: 1;
        }
        .count-plus {
            font-size: 4em;
            font-weight: 800;
            color: var(--color-accent);
            vertical-align: super; 
        }


        /* ====================================
           4. 通用内容区
           ==================================== */
        .main-container { 
            width: 90%; 
            max-width: 1200px; 
            margin: 0 auto;
            overflow: hidden; 
        }

        .section { 
            background: white; 
            padding: 80px 0; 
            margin-bottom: 0; 
        }
        
        .section-header {
            border-bottom: 3px solid var(--color-secondary);
            padding-bottom: 10px;
            margin-top: 0;
            color: var(--color-primary);
            font-size: 2em;
            margin-bottom: 35px;
        }

        /* 滚动淡入效果 */
        .section {
            opacity: 0;
            transform: translateY(40px);
            transition: opacity 1.2s ease-out, transform 1.2s ease-out;
        }
        .section.fade-in {
            opacity: 1;
            transform: translateY(0);
        }

        /* ====================================
           5. 专案列表 (Projects)
           ==================================== */
        .project-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); 
            gap: 20px;
        }
        
        .project-card {
            padding: 20px;
            border: 1px solid #ddd;
            border-radius: 8px;
            cursor: pointer;
            transition: box-shadow 0.3s, transform 0.3s;
            position: relative;
            overflow: hidden;
            background-color: white;
        }
        
        /* Hover 效果：卡片抬升与边框强调 */
        .project-card:hover {
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
            transform: translateY(-5px);
        }
        
        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 4px;
            height: 100%;
            background-color: var(--color-secondary); 
            transition: width 0.3s;
        }
        
        .project-card:hover::before {
            width: 8px;
        }

        .project-card-header {
            margin: 0 0 10px 0;
            color: var(--color-primary);
            font-size: 1.3em;
        }
        
        .project-description {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.5s ease-in-out, opacity 0.5s;
            opacity: 0;
            padding-top: 5px;
            color: #555;
        }
        
        .project-card.expanded .project-description {
            max-height: 200px; 
            opacity: 1;
        }

        /* ====================================
           6. 社交链接 (Social Links)
           ==================================== */
        .social-links {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            margin-top: 30px;
        }

        .social-links a {
            display: inline-flex;
            align-items: center;
            background-color: var(--color-secondary);
            color: white;
            padding: 12px 25px;
            margin: 10px;
            text-decoration: none;
            border-radius: 30px;
            font-weight: 600;
            transition: background-color 0.3s, box-shadow 0.3s, transform 0.3s;
        }
        
        .social-links a i {
            margin-right: 8px;
            font-size: 1.2em;
        }

        .social-links a:hover {
            background-color: var(--color-primary);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            transform: translateY(-3px);
        }

        /* ====================================
           7. 頁腳 (Footer)
           ==================================== */
        .footer { 
            background-color: var(--color-bg-footer);
            color: #ccc; 
            text-align: center; 
            padding: 35px 20px;
            font-size: 0.9em;
        }

        /* ====================================
           8. 响应式 (Responsive)
           ==================================== */
        @media (max-width: 768px) {
            .navbar {
                padding: 10px 0;
            }
            .nav-link {
                padding: 6px 10px;
                font-size: 0.9em;
            }
            .nav-logo {
                margin-right: 15px;
                font-size: 1.1em;
            }
            
            .hero h1 {
                font-size: 2em;
            }
            .count-display {
                font-size: 4em;
            }
            .count-plus {
                font-size: 3em;
            }
            
            .section {
                padding: 50px 0;
            }
            .section-header {
                font-size: 1.6em;
            }
            
            .project-list {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>

    <nav class="navbar">
        <a href="#top" class="nav-logo">MQI 量元計畫</a>
        
        <a href="#about" class="nav-link">團隊介紹</a>
        <a href="#projects" class="nav-link">專案成果</a>
        <a href="#vision" class="nav-link">核心理念</a>
        <a href="#contact" class="nav-link">聯絡我們</a>
    </nav>

    <div class="main-content">
        <section class="hero" id="top">
            <h1>全臺第一個由國高中生主導的跨世代科技革命。</h1>
            
            <div class="hero-stats">
                <p class="count-label">活躍技術成員總數</p>
                <span class="count-display"><span id="member-count">0</span></span><span class="count-plus">+</span>
            </div>
            
            <p style="font-size: 1.1em; max-width: 600px; opacity: 0.9;">我們是 MetaQuant Initiative (MQI) 量元計畫，點燃年輕世代的科技火花，**年齡不是限制，而是創造力的起點。**</p>
        </section>

        <div class="main-container">
            <section id="about" class="section">
                <h3 class="section-header">關於我們：定義新世代科技力量</h3>
                <p>我們是一群來自臺灣各地的國中生與高中生，因為對前沿科技抱持著共同的熱忱與好奇心而聚集。</p>
                <p>不同於制式的教育框架，在 MQI，我們互相挑戰、激發潛能，將腦海中的創意大膽付諸實踐。我們的團隊定位是明確且堅定的：**「全台第一個由國高中生主導的跨領域科技團隊」**。</p>
                <p>我們樂於突破傳統思維，以創新的方式解決問題，讓全世界看到臺灣年輕人的科技潛能！</p>
            </section>

            <section id="projects" class="section">
                <h3 class="section-header">我們的挑戰與專案成果 🔬🎮</h3>
                <p>在量元計畫中，我們將學習到的理論知識轉化為實際的應用成果。我們的專案涵蓋多個前瞻領域，展現了團隊在多元科技整合上的雄心：</p>

                <div class="project-list">
                    
                    <div class="project-card" data-project-id="1">
                        <h4 class="project-card-header"><i class="fas fa-vr-cardboard"></i> 沉浸式應用開發</h4>
                        <div class="project-description"> 
                            <p>嘗試打造高性能的**遊戲模擬器**，深入理解軟硬體架構與優化，推動互動體驗的新界限。</p>
                        </div>
                    </div>

                    <div class="project-card" data-project-id="2">
                        <h4 class="project-card-header"><i class="fas fa-robot"></i> 人工智慧與數據分析</h4>
                        <div class="project-description"> 
                            <p>開發實用的 **AI 工具**，從機器學習模型到自動化解決方案，應對現實世界的挑戰。</p>
                        </div>
                    </div>

                    <div class="project-card" data-project-id="3">
                        <h4 class="project-card-header"><i class="fas fa-sitemap"></i> 系統架構與資料整合</h4>
                        <div class="project-description"> 
                            <p>建構穩健高效的資料系統與後端服務，奠定未來數位基礎，確保專案具備規模化能力。</p>
                        </div>
                    </div>
                </div>
                
                <p style="margin-top: 30px;">每一個專案都是我們挑戰自我、追求卓越的證明。你會親眼見證學生的創意想法如何蛻變成真實可用的作品。</p>
            </section>

            <section id="vision" class="section">
                <h3 class="section-header">核心理念：用創意翻轉未來 🌟</h3>
                <p>我們的最終願景，就是成為**「MetaQuant Initiative：下一代的科技解方」**。</p>
                <p>我們相信透過不斷的學習、協作與實踐，能夠真正做到**「量元計畫– 用創意翻轉未來」**。我們歡迎所有關注科技、渴望創新的朋友，一同追蹤量元計畫MQI，見證這股蓬勃而充滿活力的年輕世代科技火花！</p>
            </section>

            <section id="contact" class="section">
                <h3 class="section-header">聯絡與追蹤我們</h3>
                <p style="text-align: center;">想了解更多資訊或尋求合作？請點擊下方連結，透過我們的社群媒體追蹤最新的動態：</p>
                
                <div class="social-links">
                    <a href="https://www.facebook.com/share/15LSr9zVen6/" target="_blank">
                    <a href="#" target="_blank">
                        <i class="fab fa-github"></i> GitHub (專案代碼)
                    </a>
                    <a href="#" target="_blank">
                        <i class="fas fa-envelope"></i> 合作洽詢
                    </a>
                </div>
            </section>
        </div>
    </div>

    <footer class="footer">
        © 2025 MetaQuant Initiative (MQI) 量元計畫. All Rights Reserved.
    </footer>

    <script>
        // ====================================
        // JavaScript: 行为与结构分离
        // ====================================

        // 1. 计数器动画逻辑
        const targetCount = 20; // 目标成员数 (您原先的代码中隐含的值)
        const countElement = document.getElementById('member-count');
        const duration = 2000; // 动画持续时间 (毫秒)

        function animateCount(target, element, duration) {
            let start = 0;
            const step = target / (duration / 16); // 假设每 16ms 更新一次 (约 60fps)
            
            // 使用 Intersection Observer 确保只有滚动到 Hero 区时才开始动画
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        const interval = setInterval(() => {
                            start += step;
                            if (start >= target) {
                                element.textContent = target;
                                clearInterval(interval);
                            } else {
                                element.textContent = Math.ceil(start);
                            }
                        }, 16);
                        observer.unobserve(entry.target); // 动画完成后停止观察
                    }
                });
            }, { threshold: 0.5 }); // 当 50% 可见时触发

            observer.observe(document.getElementById('top'));
        }

        // 2. 专案卡片展开/收起逻辑 (用 Event Delegation 优化)
        const projectList = document.querySelector('.project-list');
        if (projectList) {
            projectList.addEventListener('click', (event) => {
                const card = event.target.closest('.project-card');
                if (card) {
                    // 切换 expanded 类
                    card.classList.toggle('expanded');
                }
            });
        }


        // 3. 滚动时的淡入效果逻辑
        function setupScrollFadeIn() {
            const sections = document.querySelectorAll('.section');
            
            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        // 目标元素进入可视区
                        entry.target.classList.add('fade-in');
                        observer.unobserve(entry.target); // 淡入一次后停止观察
                    }
                });
            }, {
                rootMargin: '0px',
                threshold: 0.2 // 当元素 20% 进入可视区时触发
            });

            sections.forEach(section => {
                observer.observe(section);
            });
        }
        
        // 4. 启动所有功能
        document.addEventListener('DOMContentLoaded', () => {
            // 启动计数器动画
            animateCount(targetCount, countElement, duration);
            
            // 启动滚动淡入
            setupScrollFadeIn();
        });
    </script>
</body>
</html>
<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MQI 量元計畫 | 台灣學生跨領域科技團隊 | AI, 模擬器, 系統架構</title>
    <meta name="description" content="MetaQuant Initiative (MQI) 是全臺第一個由國高中生主導的跨領域科技團隊，專注於 AI、遊戲模擬器、系統架構等前沿專案。用創意翻轉未來。">
    <meta name="keywords" content="MQI, 量元計畫, 學生團隊, 程式設計, 科技, AI, 遊戲模擬器, 系統架構, 台灣, 國高中生">
    <link rel="canonical" href="https://MQI.qzz.io/"> 
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    
    <style>
        /* ====================================
           1. 基本与重设
           ==================================== */
        :root {
            /* 品牌颜色定义 */
            --color-primary: #004d99; /* 深蓝 */
            --color-secondary: #008cff; /* 亮蓝 */
            --color-accent: #ffcc00; /* 强调黄 */
            --color-text: #333;
            --color-bg-dark: #002d5c;
            --color-bg-footer: #1a1a1a;
            --color-hover-light: #f0f8ff;
            --shadow-nav: 0 4px 6px rgba(0,0,0,0.1);
        }

        html {
            scroll-behavior: smooth;
        }

        body { 
            /* 字体栈优化，兼容不同系统 */
            font-family: '微軟正黑體', 'Microsoft JhengHei', 'PingFang TC', 'Apple LiGothic', sans-serif; 
            margin: 0; 
            padding: 0; 
            background-color: #ffffff;
            color: var(--color-text); 
            line-height: 1.6;
        }
        
        a {
            text-decoration: none;
            color: var(--color-secondary);
        }

        /* ====================================
           2. 导航列 (Navbar) - Glassmorphism
           ==================================== */
        .navbar { 
            display: flex; 
            justify-content: center; 
            align-items: center;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 15px 0;
            
            /* Glassmorphism 核心 */
            /* 修正：增加透明度，确保背景可见度 */
            background-color: rgba(255, 255, 255, 0.5); 
            backdrop-filter: blur(12px); 
            -webkit-backdrop-filter: blur(12px);
            box-shadow: var(--shadow-nav);
            z-index: 1000;
        }
        
        .nav-logo {
            color: var(--color-primary);
            font-size: 1.3em;
            font-weight: 800;
            margin-right: 30px;
        }
        
        .nav-link { 
            color: var(--color-primary);
            padding: 8px 18px; 
            font-weight: 600;
            font-size: 0.95em;
            transition: color 0.3s, background-color 0.3s;
            border-radius: 6px;
        }
        
        .nav-link:hover { 
            color: white; 
            background-color: var(--color-secondary);
        }

        /* ====================================
           3. 宣傳区 (Hero) - 粒子光影
           ==================================== */
        .hero { 
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative;
            overflow: hidden;
            
            background: var(--color-bg-dark); 
            color: white;
            padding: 100px 20px 40px;
            text-align: center; 
        }

        /* 粒子/光影效果 */
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(0, 140, 255, 0.25) 0%, rgba(0, 45, 92, 0) 70%);
            animation: pulse 18s infinite alternate; 
            z-index: 1;
        }
        @keyframes pulse {
            0% { transform: scale(1.0); opacity: 0.8; }
            100% { transform: scale(1.6); opacity: 0.5; }
        }

        .hero > * {
            position: relative;
            z-index: 2;
        }

        .hero h1 { 
            font-size: clamp(2em, 5vw, 3.5em); 
            margin-top: 0;
            max-width: 900px;
            text-shadow: 0 0 12px rgba(0, 140, 255, 0.8);
        }
        
        .hero-stats {
            margin: 30px 0;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* 计数器样式 */
        .count-label {
            font-size: 1.1em;
            color: rgba(255, 255, 255, 0.8); 
            margin-bottom: 5px;
        }
        .count-display {
            font-size: 5.5em; 
            font-weight: 800;
            color: var(--color-accent);
            line-height: 1;
        }
        .count-plus {
            font-size: 4em;
            font-weight: 800;
            color: var(--color-accent);
            vertical-align: super; 
        }


        /* ====================================
           4. 通用内容区
           ==================================== */
        .main-container { 
            width: 90%; 
            max-width: 1200px; 
            margin: 0 auto;
            overflow: hidden; 
        }

        .section { 
            background: white; 
            padding: 80px 0; 
            margin-bottom: 0; 
        }
        
        .section-header {
            border-bottom: 3px solid var(--color-secondary);
            padding-bottom: 10px;
            margin-top: 0;
            color: var(--color-primary);
            font-size: 2em;
            margin-bottom: 35px;
        }

        /* 滚动淡入效果 */
        .section {
            opacity: 0;
            transform: translateY(40px);
            transition: opacity 1.2s ease-out, transform 1.2s ease-out;
        }
        .section.fade-in {
            opacity: 1;
            transform: translateY(0);
        }

        /* ====================================
           5. 专案列表 (Projects)
           ==================================== */
        .project-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); 
            gap: 20px;
        }
        
        .project-card {
            padding: 20px;
            border: 1px solid #ddd;
            border-radius: 8px;
            cursor: pointer;
            transition: box-shadow 0.3s, transform 0.3s;
            position: relative;
            overflow: hidden;
            background-color: white;
        }
        
        /* Hover 效果：卡片抬升与边框强调 */
        .project-card:hover {
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
            transform: translateY(-5px);
        }
        
        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 4px;
            height: 100%;
            background-color: var(--color-secondary); 
            transition: width 0.3s;
        }
        
        .project-card:hover::before {
            width: 8px;
        }

        .project-card-header {
            margin: 0 0 10px 0;
            color: var(--color-primary);
            font-size: 1.3em;
        }
        
        .project-description {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.5s ease-in-out, opacity 0.5s;
            opacity: 0;
            padding-top: 5px;
            color: #555;
        }
        
        .project-card.expanded .project-description {
            max-height: 200px; 
            opacity: 1;
        }

        /* ====================================
           6. 社交链接 (Social Links)
           ==================================== */
        .social-links {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            margin-top: 30px;
        }

        .social-links a {
            display: inline-flex;
            align-items: center;
            background-color: var(--color-secondary);
            color: white;
            padding: 12px 25px;
            margin: 10px;
            text-decoration: none;
            border-radius: 30px;
            font-weight: 600;
            transition: background-color 0.3s, box-shadow 0.3s, transform 0.3s;
        }
        
        .social-links a i {
            margin-right: 8px;
            font-size: 1.2em;
        }

        .social-links a:hover {
            background-color: var(--color-primary);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            transform: translateY(-3px);
        }

        /* ====================================
           7. 頁腳 (Footer)
           ==================================== */
        .footer { 
            background-color: var(--color-bg-footer);
            color: #ccc; 
            text-align: center; 
            padding: 35px 20px;
            font-size: 0.9em;
        }

        /* ====================================
           8. 响应式 (Responsive)
           ==================================== */
        @media (max-width: 768px) {
            .navbar {
                padding: 10px 0;
            }
            .nav-link {
                padding: 6px 10px;
                font-size: 0.9em;
            }
            .nav-logo {
                margin-right: 15px;
                font-size: 1.1em;
            }
            
            .hero h1 {
                font-size: 2em;
            }
            .count-display {
                font-size: 4em;
            }
            .count-plus {
                font-size: 3em;
            }
            
            .section {
                padding: 50px 0;
            }
            .section-header {
                font-size: 1.6em;
            }
            
            .project-list {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>

    <nav class="navbar">
        <a href="#top" class="nav-logo">MQI 量元計畫</a>
        
        <a href="#about" class="nav-link">團隊介紹</a>
        <a href="#projects" class="nav-link">專案成果</a>
        <a href="#vision" class="nav-link">核心理念</a>
        <a href="#contact" class="nav-link">聯絡我們</a>
    </nav>

    <div class="main-content">
        <section class="hero" id="top">
            <h1>全臺第一個由國高中生主導的跨世代科技革命。</h1>
            
            <div class="hero-stats">
                <p class="count-label">活躍技術成員總數</p>
                <span class="count-display"><span id="member-count">0</span></span><span class="count-plus">+</span>
            </div>
            
            <p style="font-size: 1.1em; max-width: 600px; opacity: 0.9;">我們是 MetaQuant Initiative (MQI) 量元計畫，點燃年輕世代的科技火花，**年齡不是限制，而是創造力的起點。**</p>
        </section>

        <div class="main-container">
            <section id="about" class="section">
                <h3 class="section-header">關於我們：定義新世代科技力量</h3>
                <p>我們是一群來自臺灣各地的國中生與高中生，因為對前沿科技抱持著共同的熱忱與好奇心而聚集。</p>
                <p>不同於制式的教育框架，在 MQI，我們互相挑戰、激發潛能，將腦海中的創意大膽付諸實踐。我們的團隊定位是明確且堅定的：**「全台第一個由國高中生主導的跨領域科技團隊」**。</p>
                <p>我們樂於突破傳統思維，以創新的方式解決問題，讓全世界看到臺灣年輕人的科技潛能！</p>
            </section>

            <section id="projects" class="section">
                <h3 class="section-header">我們的挑戰與專案成果 🔬🎮</h3>
                <p>在量元計畫中，我們將學習到的理論知識轉化為實際的應用成果。我們的專案涵蓋多個前瞻領域，展現了團隊在多元科技整合上的雄心：</p>

                <div class="project-list">
                    
                    <div class="project-card" data-project-id="1">
                        <h4 class="project-card-header"><i class="fas fa-vr-cardboard"></i> 沉浸式應用開發</h4>
                        <div class="project-description"> 
                            <p>嘗試打造高性能的**遊戲模擬器**，深入理解軟硬體架構與優化，推動互動體驗的新界限。</p>
                        </div>
                    </div>

                    <div class="project-card" data-project-id="2">
                        <h4 class="project-card-header"><i class="fas fa-robot"></i> 人工智慧與數據分析</h4>
                        <div class="project-description"> 
                            <p>開發實用的 **AI 工具**，從機器學習模型到自動化解決方案，應對現實世界的挑戰。</p>
                        </div>
                    </div>

                    <div class="project-card" data-project-id="3">
                        <h4 class="project-card-header"><i class="fas fa-sitemap"></i> 系統架構與資料整合</h4>
                        <div class="project-description"> 
                            <p>建構穩健高效的資料系統與後端服務，奠定未來數位基礎，確保專案具備規模化能力。</p>
                        </div>
                    </div>
                </div>
                
                <p style="margin-top: 30px;">每一個專案都是我們挑戰自我、追求卓越的證明。你會親眼見證學生的創意想法如何蛻變成真實可用的作品。</p>
            </section>

            <section id="vision" class="section">
                <h3 class="section-header">核心理念：用創意翻轉未來 🌟</h3>
                <p>我們的最終願景，就是成為**「MetaQuant Initiative：下一代的科技解方」**。</p>
                <p>我們相信透過不斷的學習、協作與實踐，能夠真正做到**「量元計畫– 用創意翻轉未來」**。我們歡迎所有關注科技、渴望創新的朋友，一同追蹤量元計畫MQI，見證這股蓬勃而充滿活力的年輕世代科技火花！</p>
            </section>

            <section id="contact" class="section">
                <h3 class="section-header">聯絡與追蹤我們</h3>
                <p style="text-align: center;">想了解更多資訊或尋求合作？請點擊下方連結，透過我們的社群媒體追蹤最新的動態：</p>
                
                <div class="social-links">
                    <a href="https://www.facebook.com/share/15LSr9zVen6/" target="_blank">
                        <i class="fab fa-facebook-f"></i> Facebook
                    </a>
                    <a href="#" target="_blank">
                        <i class="fab fa-github"></i> GitHub (專案代碼)
                    </a>
                    <a href="#" target="_blank">
                        <i class="fas fa-envelope"></i> 合作洽詢
                    </a>
                </div>
            </section>
        </div>
    </div> <footer class="footer">
        © 2025 MetaQuant Initiative (MQI) 量元計畫. All Rights Reserved.
    </footer>

    <script>
        // ====================================
        // JavaScript: 行为与结构分离
        // ====================================

        // 1. 计数器动画逻辑
        const targetCount = 20; // 目标成员数 (可根据实际情况修改)
        const countElement = document.getElementById('member-count');
        const duration = 2000; // 动画持续时间 (毫秒)

        function animateCount(target, element, duration) {
            let start = 0;
            const step = target / (duration / 16); 
            
            // 使用 Intersection Observer 确保只有滚动到 Hero 区时才开始动画
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        const interval = setInterval(() => {
                            start += step;
                            if (start >= target) {
                                element.textContent = target;
                                clearInterval(interval);
                            } else {
                                element.textContent = Math.ceil(start);
                            }
                        }, 16);
                        observer.unobserve(entry.target); 
                    }
                });
            }, { threshold: 0.5 }); 

            observer.observe(document.getElementById('top'));
        }

        // 2. 专案卡片展开/收起逻辑
        const projectList = document.querySelector('.project-list');
        if (projectList) {
            projectList.addEventListener('click', (event) => {
                // 确保点击的是卡片本身或卡片内部的元素
                const card = event.target.closest('.project-card');
                if (card) {
                    card.classList.toggle('expanded');
                }
            });
        }


        // 3. 滚动时的淡入效果逻辑
        function setupScrollFadeIn() {
            const sections = document.querySelectorAll('.section');
            
            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('fade-in');
                        observer.unobserve(entry.target); 
                    }
                });
            }, {
                rootMargin: '0px',
                threshold: 0.2 // 当元素 20% 进入可视区时触发
            });

            sections.forEach(section => {
                observer.observe(section);
            });
        }
        
        // 4. 启动所有功能
        document.addEventListener('DOMContentLoaded', () => {
            // 启动计数器动画
            animateCount(targetCount, countElement, duration);
            
            // 启动滚动淡入
            setupScrollFadeIn();
        });
    </script>
</body>
</html>
