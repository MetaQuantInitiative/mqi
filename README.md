<div align="center">
  <img src="https://mqi.unaux.com/wp-content/uploads/2025/09/%E6%96%B0%E5%A2%9E%E6%A8%99%E9%A1%8C-1.png" width="100" alt="MQI 量元計畫 Logo"/>
  
  # Maker's Quest Initiative (MQI) 量元計畫
  
  <p>我們是**全臺第一個由國高中生主導的跨領域科技團隊**，專注於 **AI 人工智慧**、**遊戲模擬器**及**系統架構**的創新應用。用年輕的力量，重新定義科技的邊界。</p>

  [![GitHub Stars](https://img.shields.io/github/stars/Hgpcqyfyfyfhfdte74/mqi?style=for-the-badge&color=008cff&label=MQI%20Project%20Stars&logo=github)](https://github.com/Hgpcqyfyfyfhfdte74/mqi)
  [![Discord Community](https://img.shields.io/badge/Discord-Join%20Our%20Community-5865F2?style=for-the-badge&logo=discord)](https://discord.gg/yHRkzDAFGK)
  [![Official Website](https://img.shields.io/badge/Official%20Site-MQI.qzz.io-FF6600?style=for-the-badge&logo=internetexplorer)](https://MQI.qzz.io)
</div>

---<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MQI 量元計畫 | 台灣學生跨領域科技團隊 | AI, 模擬器, 系統架構</title>
    <meta name="description" content="MetaQuant Initiative (MQI) 是全臺第一個由國高中生主導的跨領域科技團隊，專注於 AI、遊戲模擬器、系統架構等前沿專案。用創意翻轉未來。">
    <meta name="keywords" content="MQI, 量元計畫, 學生團隊, 程式設計, 科技, AI, 遊戲模擬器, 系統架構, 台灣, 國高中生">
    <link rel="canonical" href="https://MQI.qzz.io/"> 
    
    <style>
        /* 1. 啟用平滑捲動 */
        html {
            scroll-behavior: smooth;
        }

        /* 基本重設與字體 */
        body { 
            font-family: '微軟正黑體', 'Microsoft JhengHei', sans-serif; 
            margin: 0; 
            padding: 0; 
            background-color: #ffffff;
            color: #333; 
            line-height: 1.6;
        }
        
        /* 導航列樣式 - 懸浮 Glassmorphism (炫酷效果 1) */
        nav { 
            display: flex; 
            justify-content: center; 
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 15px 0;
            /* Glassmorphism 核心 CSS */
            background-color: rgba(255, 255, 255, 0.2); /* 半透明背景 */
            backdrop-filter: blur(10px); /* 磨砂玻璃模糊效果 */
            -webkit-backdrop-filter: blur(10px); /* 兼容 Safari */
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            z-index: 1000;
        }
        nav a { 
            color: #004d99;
            padding: 8px 18px; 
            text-decoration: none; 
            font-weight: bold;
            font-size: 0.95em;
            transition: color 0.3s, background-color 0.3s;
            border-radius: 4px;
        }
        nav a:hover { 
            color: white; 
            background-color: #008cff;
        }

        /* 主要內容容器 */
        .container { 
            width: 85%; 
            max-width: 1100px;
            margin: 0 auto;
            overflow: hidden; 
        }

        /* 宣傳區 (Hero) - 全螢幕設計 */
        .hero { 
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative; /* 為了讓粒子背景絕對定位 */
            overflow: hidden;
            
            background: #002d5c; /* 深藍色基底 */
            color: white;
            padding: 100px 40px 40px;
            text-align: center; 
        }

        /* 動態粒子/光影效果 (炫酷效果 2: CSS 偽元素動畫) */
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(0, 140, 255, 0.2) 0%, rgba(0, 45, 92, 0) 70%);
            animation: pulse 15s infinite alternate; /* 緩慢閃爍動畫 */
            z-index: 1;
        }
        @keyframes pulse {
            0% { transform: scale(1.0); opacity: 0.8; }
            100% { transform: scale(1.5); opacity: 0.5; }
        }

        /* 確保 Hero 內容在偽元素之上 */
        .hero > * {
            position: relative;
            z-index: 2;
        }

        .hero h2 {
            color: white;
            font-size: 3em;
            margin-top: 0;
            max-width: 800px;
            text-shadow: 0 0 10px rgba(0, 140, 255, 0.8); /* 標題微弱發光 */
        }
        .hero p {
            font-size: 1.2em;
            max-width: 700px;
            opacity: 0.9;
        }
        .hero strong {
            color: #ffcc00;
            font-size: 1.1em;
        }
        
        /* 計數器樣式 */
        .count-up {
            font-size: 5em; 
            font-weight: 800;
            color: #ffcc00;
            display: inline-block;
            line-height: 1;
        }
        .count-up-plus {
            font-size: 4em;
            font-weight: 800;
            color: #ffcc00;
            display: inline-block;
            line-height: 1;
            vertical-align: top;
        }


        /* 區塊樣式 - 簡約設計 */
        .section { 
            background: white; 
            padding: 60px 40px;
            margin-bottom: 0; 
        }
        .section h3 {
            border-bottom: 3px solid #008cff;
            padding-bottom: 10px;
            margin-top: 0;
            color: #004d99;
            font-size: 1.8em;
            margin-bottom: 25px;
        }

        /* 專案列表樣式 */
        .project-item {
            margin-bottom: 25px;
            padding: 15px 20px; /* 增加 padding */
            border-left: 4px solid #ff6600;
            cursor: pointer;
            transition: background-color 0.3s, transform 0.2s;
            border-radius: 4px;
        }
        .project-item:hover {
            background-color: #f0f8ff; /* 淺藍色 hover */
            transform: translateX(5px); /* 微微右移，增加動態感 */
        }
        .project-item h4 {
            margin: 0 0 5px 0;
            color: #333;
            font-size: 1.2em;
        }
        .project-details {
             padding-top: 10px;
        }


        /* 社群連結樣式 - 膠囊按鈕 */
        .social-links a {
            display: inline-block;
            background-color: #008cff;
            color: white;
            padding: 12px 25px;
            margin: 8px;
            text-decoration: none;
            border-radius: 50px;
            transition: background-color 0.3s, box-shadow 0.3s, transform 0.3s;
        }
        .social-links a:hover {
            background-color: #004d99;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            transform: translateY(-2px);
        }

        /* 頁腳樣式 */
        footer { 
            background-color: #1a1a1a;
            color: #ccc; 
            text-align: center; 
            padding: 30px 0;
        }

        /* 滾動時的淡入動畫 */
        .section {
            opacity: 0;
            transform: translateY(40px);
            transition: opacity 1.2s ease-out, transform 1.2s ease-out;
        }
        .section.fade-in {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>

    <nav>
        <a href="#top" style="margin-right: 20px; color:#004d99; font-size:1.2em; border-bottom: none; background: none;">MQI</a>
        
        <a href="#about">團隊介紹</a>
        <a href="#projects">專案成果</a>
        <a href="#vision">核心理念</a>
        <a href="#contact">聯絡我們</a>
    </nav>

    <div class="main-content">
        <section class="hero" id="top">
            <h2>全臺第一個由國高中生主導的跨世代科技革命。</h2>
            
            <div style="margin: 30px 0;">
                <p style="font-size: 1.2em; color: rgba(255, 255, 255, 0.8); margin-bottom: 5px;">活躍技術成員總數</p>
                <span id="member-count" class="count-up">0</span><span class="count-up-plus">+</span>
            </div>
            
            <p style="font-size: 1.1em; max-width: 600px; opacity: 0.9;">我們是 MetaQuant Initiative (MQI) 量元計畫，點燃年輕世代的科技火花，**年齡不是限制，而是創造力的起點。**</p>
        </section>

        <div class="container">
            <section id="about" class="section">
                <h3>關於我們：定義新世代科技力量</h3>
                <p>我們是一群來自臺灣各地的國中生與高中生，因為對前沿科技抱持著共同的熱忱與好奇心而聚集。</p>
                <p>不同於制式的教育框架，在 MQI，我們互相挑戰、激發潛能，將腦海中的創意大膽付諸實踐。我們的團隊定位是明確且堅定的：**「全台第一個由國高中生主導的跨領域科技團隊」**。</p>
                <p>我們樂於突破傳統思維，以創新的方式解決問題，讓全世界看到臺灣年輕人的科技潛能！</p>
            </section>

            <section id="projects" class="section">
                <h3>我們的挑戰與專案成果 🔬🎮</h3>
                <p>在量元計畫中，我們將學習到的理論知識轉化為實際的應用成果。我們的專案涵蓋多個前瞻領域，展現了團隊在多元科技整合上的雄心：</p>

                <div class="project-item" onclick="toggleDetails(this)">
                    <h4>🕹️ 沉浸式應用開發</h4>
                    <div class="project-details" style="display: none;"> 
                        <p>嘗試打造高性能的**遊戲模擬器**，深入理解軟硬體架構與優化，推動互動體驗的新界限。</p>
                    </div>
                </div>

                <div class="project-item" onclick="toggleDetails(this)">
                    <h4>🤖 人工智慧與數據分析</h4>
                    <div class="project-details" style="display: none;"> 
                        <p>開發實用的 **AI 工具**，從機器學習模型到自動化解決方案，應對現實世界的挑戰。</p>
                    </div>
                </div>

                <div class="project-item" onclick="toggleDetails(this)">
                    <h4>📊 系統架構與資料整合</h4>
                    <div class="project-details" style="display: none;"> 
                        <p>建構穩健高效的資料系統與後端服務，奠定未來數位基礎，確保專案具備規模化能力。</p>
                    </div>
                </div>
                
                <p>每一個專案都是我們挑戰自我、追求卓越的證明。你會親眼見證學生的創意想法如何蛻變成真實可用的作品。</p>
<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MQI 量元計畫 | 台灣學生跨領域科技團隊 | AI, 模擬器, 系統架構</title>
    <meta name="description" content="MetaQuant Initiative (MQI) 是全臺第一個由國高中生主導的跨領域科技團隊，專注於 AI、遊戲模擬器、系統架構等前沿專案。用創意翻轉未來。">
    <meta name="keywords" content="MQI, 量元計畫, 學生團隊, 程式設計, 科技, AI, 遊戲模擬器, 系統架構, 台灣, 國高中生">
    <link rel="canonical" href="https://MQI.qzz.io/"> 
    
    <style>
        /* 1. 啟用平滑捲動 */
        html {
            scroll-behavior: smooth;
        }

        /* 基本重設與字體 */
        body { 
            font-family: '微軟正黑體', 'Microsoft JhengHei', sans-serif; 
            margin: 0; 
            padding: 0; 
            background-color: #ffffff;
            color: #333; 
            line-height: 1.6;
        }
        
        /* 導航列樣式 - 懸浮 Glassmorphism (炫酷效果 1) */
        nav { 
            display: flex; 
            justify-content: center; 
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 15px 0;
            /* Glassmorphism 核心 CSS */
            background-color: rgba(255, 255, 255, 0.2); /* 半透明背景 */
            backdrop-filter: blur(10px); /* 磨砂玻璃模糊效果 */
            -webkit-backdrop-filter: blur(10px); /* 兼容 Safari */
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            z-index: 1000;
        }
        nav a { 
            color: #004d99;
            padding: 8px 18px; 
            text-decoration: none; 
            font-weight: bold;
            font-size: 0.95em;
            transition: color 0.3s, background-color 0.3s;
            border-radius: 4px;
        }
        nav a:hover { 
            color: white; 
            background-color: #008cff;
        }

        /* 主要內容容器 */
        .container { 
            width: 85%; 
            max-width: 1100px;
            margin: 0 auto;
            overflow: hidden; 
        }

        /* 宣傳區 (Hero) - 全螢幕設計 */
        .hero { 
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative; /* 為了讓粒子背景絕對定位 */
            overflow: hidden;
            
            background: #002d5c; /* 深藍色基底 */
            color: white;
            padding: 100px 40px 40px;
            text-align: center; 
        }

        /* 動態粒子/光影效果 (炫酷效果 2: CSS 偽元素動畫) */
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(0, 140, 255, 0.2) 0%, rgba(0, 45, 92, 0) 70%);
            animation: pulse 15s infinite alternate; /* 緩慢閃爍動畫 */
            z-index: 1;
        }
        @keyframes pulse {
            0% { transform: scale(1.0); opacity: 0.8; }
            100% { transform: scale(1.5); opacity: 0.5; }
        }

        /* 確保 Hero 內容在偽元素之上 */
        .hero > * {
            position: relative;
            z-index: 2;
        }

        .hero h2 {
            color: white;
            font-size: 3em;
            margin-top: 0;
            max-width: 800px;
            text-shadow: 0 0 10px rgba(0, 140, 255, 0.8); /* 標題微弱發光 */
        }
        .hero p {
            font-size: 1.2em;
            max-width: 700px;
            opacity: 0.9;
        }
        .hero strong {
            color: #ffcc00;
            font-size: 1.1em;
        }
        
        /* 計數器樣式 */
        .count-up {
            font-size: 5em; 
            font-weight: 800;
            color: #ffcc00;
            display: inline-block;
            line-height: 1;
        }
        .count-up-plus {
            font-size: 4em;
            font-weight: 800;
            color: #ffcc00;
            display: inline-block;
            line-height: 1;
            vertical-align: top;
        }


        /* 區塊樣式 - 簡約設計 */
        .section { 
            background: white; 
            padding: 60px 40px;
            margin-bottom: 0; 
        }
        .section h3 {
            border-bottom: 3px solid #008cff;
            padding-bottom: 10px;
            margin-top: 0;
            color: #004d99;
            font-size: 1.8em;
            margin-bottom: 25px;
        }

        /* 專案列表樣式 */
        .project-item {
            margin-bottom: 25px;
            padding: 15px 20px; /* 增加 padding */
            border-left: 4px solid #ff6600;
            cursor: pointer;
            transition: background-color 0.3s, transform 0.2s;
            border-radius: 4px;
        }
        .project-item:hover {
            background-color: #f0f8ff; /* 淺藍色 hover */
            transform: translateX(5px); /* 微微右移，增加動態感 */
        }
        .project-item h4 {
            margin: 0 0 5px 0;
            color: #333;
            font-size: 1.2em;
        }
        .project-details {
             padding-top: 10px;
        }


        /* 社群連結樣式 - 膠囊按鈕 */
        .social-links a {
            display: inline-block;
            background-color: #008cff;
            color: white;
            padding: 12px 25px;
            margin: 8px;
            text-decoration: none;
            border-radius: 50px;
            transition: background-color 0.3s, box-shadow 0.3s, transform 0.3s;
        }
        .social-links a:hover {
            background-color: #004d99;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            transform: translateY(-2px);
        }

        /* 頁腳樣式 */
        footer { 
            background-color: #1a1a1a;
            color: #ccc; 
            text-align: center; 
            padding: 30px 0;
        }

        /* 滾動時的淡入動畫 */
        .section {
            opacity: 0;
            transform: translateY(40px);
            transition: opacity 1.2s ease-out, transform 1.2s ease-out;
        }
        .section.fade-in {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>

    <nav>
        <a href="#top" style="margin-right: 20px; color:#004d99; font-size:1.2em; border-bottom: none; background: none;">MQI</a>
        
        <a href="#about">團隊介紹</a>
        <a href="#projects">專案成果</a>
        <a href="#vision">核心理念</a>
        <a href="#contact">聯絡我們</a>
    </nav>

    <div class="main-content">
        <section class="hero" id="top">
            <h2>全臺第一個由國高中生主導的跨世代科技革命。</h2>
            
            <div style="margin: 30px 0;">
                <p style="font-size: 1.2em; color: rgba(255, 255, 255, 0.8); margin-bottom: 5px;">活躍技術成員總數</p>
                <span id="member-count" class="count-up">0</span><span class="count-up-plus">+</span>
            </div>
            
            <p style="font-size: 1.1em; max-width: 600px; opacity: 0.9;">我們是 MetaQuant Initiative (MQI) 量元計畫，點燃年輕世代的科技火花，**年齡不是限制，而是創造力的起點。**</p>
        </section>

        <div class="container">
            <section id="about" class="section">
                <h3>關於我們：定義新世代科技力量</h3>
                <p>我們是一群來自臺灣各地的國中生與高中生，因為對前沿科技抱持著共同的熱忱與好奇心而聚集。</p>
                <p>不同於制式的教育框架，在 MQI，我們互相挑戰、激發潛能，將腦海中的創意大膽付諸實踐。我們的團隊定位是明確且堅定的：**「全台第一個由國高中生主導的跨領域科技團隊」**。</p>
                <p>我們樂於突破傳統思維，以創新的方式解決問題，讓全世界看到臺灣年輕人的科技潛能！</p>
            </section>

            <section id="projects" class="section">
                <h3>我們的挑戰與專案成果 🔬🎮</h3>
                <p>在量元計畫中，我們將學習到的理論知識轉化為實際的應用成果。我們的專案涵蓋多個前瞻領域，展現了團隊在多元科技整合上的雄心：</p>

                <div class="project-item" onclick="toggleDetails(this)">
                    <h4>🕹️ 沉浸式應用開發</h4>
                    <div class="project-details" style="display: none;"> 
                        <p>嘗試打造高性能的**遊戲模擬器**，深入理解軟硬體架構與優化，推動互動體驗的新界限。</p>
                    </div>
                </div>

                <div class="project-item" onclick="toggleDetails(this)">
                    <h4>🤖 人工智慧與數據分析</h4>
                    <div class="project-details" style="display: none;"> 
                        <p>開發實用的 **AI 工具**，從機器學習模型到自動化解決方案，應對現實世界的挑戰。</p>
                    </div>
                </div>

                <div class="project-item" onclick="toggleDetails(this)">
                    <h4>📊 系統架構與資料整合</h4>
                    <div class="project-details" style="display: none;"> 
                        <p>建構穩健高效的資料系統與後端服務，奠定未來數位基礎，確保專案具備規模化能力。</p>
                    </div>
                </div>
                
                <p>每一個專案都是我們挑戰自我、追求卓越的證明。你會親眼見證學生的創意想法如何蛻變成真實可用的作品。</p>
            </section>

            <section id="vision" class="section">
                <h3>核心理念：用創意翻轉未來 🌟</h3>
                <p>我們的最終願景，就是成為**「MetaQuant Initiative：下一代的科技解方」**。</p>
                <p>我們相信透過不斷的學習、協作與實踐，能夠真正做到**「量元計畫– 用創意翻轉未來」**。我們歡迎所有關注科技、渴望創新的朋友，一同追蹤量元計畫MQI，見證這股蓬勃而充滿活力的年輕世代科技火花！</p>
            </section>

            <section id="contact" class="section">
                <h3>聯絡與追蹤我們</h3>
                <p>想了解更多資訊或尋求合作？請點擊下方連結，透過我們的社群媒體追蹤最新的動態：</p>
                
                <div class="social-links">
                    <a href="https://www.facebook.com/share/15LSr9zVen6/" target="_blank">Facebook</a>
                    <a href="https://www.tiktok.com/@mqi_tw" target="_blank">TikTok</a>
                    <a href="https://www.instagram.com/metaquant_initiative" target="_blank">Instagram</a>
                    <a href="https://youtube.com/channel/UCffKddZyMhuY7NWDVkq-Pvg?si=ueWSHiu8RGNj7E5D" target="_blank">YouTube</a>
                    <a href="https://discord.gg/yHRkzDAFGK" target="_blank">Discord</a>
                </div>
            </section>
        </div>
    </div>

    <footer>
        <p>© 2025~2099 MetaQuant Initiative 版權所有. 開發團隊MetaQuant Initiative 保留一切權利。</p>
    </footer>

    <script>
        document.addEventListener("DOMContentLoaded", function() {
            
            // --- 滾動淡入功能 (Fade-in on Scroll) ---
            const fadeElements = document.querySelectorAll('.section');
            
            const isVisible = (element) => {
                const rect = element.getBoundingClientRect();
                return (
                    rect.top <= (window.innerHeight || document.documentElement.clientHeight) - 150
                );
            };

            const handleScroll = () => {
                fadeElements.forEach(element => {
                    if (isVisible(element) && !element.classList.contains('fade-in')) {
                        element.classList.add('fade-in');
                    }
                });
            };

            handleScroll();
            window.addEventListener('scroll', handleScroll);
        
            
            // --- 數字計數器動畫功能 (Count-up Animation) ---
            const memberCountElement = document.getElementById('member-count');
            const targetNumber = 99;
            const duration = 2000;
            const frameRate = 1000 / 60;
            const totalFrames = Math.round(duration / frameRate);
            const step = targetNumber / totalFrames;
            
            let currentNumber = 0;
            let frame = 0;

            function animateCount() {
                const interval = setInterval(() => {
                    if (frame >= totalFrames) {
                        clearInterval(interval);
                        memberCountElement.textContent = targetNumber;
                        return;
                    }
                    
                    currentNumber += step;
                    memberCountElement.textContent = Math.round(currentNumber);
                    frame++;
                }, frameRate);
            }

            const handleCountAnimation = () => {
                if (isVisible(memberCountElement) && memberCountElement.textContent === '0') {
                    animateCount();
                    window.removeEventListener('scroll', handleCountAnimation);
                }
            };
            
            window.addEventListener('scroll', handleCountAnimation);
            handleCountAnimation();
        });

        // --- 專案點擊開合功能 (Toggle Details) ---
        window.toggleDetails = function(element) {
            const details = element.querySelector('.project-details');
            if (details.style.display === 'none') {
                details.style.display = 'block';
            } else {
                details.style.display = 'none';
            }
        };
    </script>
</body>
</html>
