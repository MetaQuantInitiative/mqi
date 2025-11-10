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
           1. 顏色與變量定義
           ==================================== */
        :root {
            --color-primary: #004d99; /* 深蓝 */
            --color-secondary: #008cff; /* 亮蓝 */
            --color-accent: #ffcc00; /* 强调黄 */
            --color-text: #333;
            --color-bg-dark: #002d5c;
            --color-hover-light: #f0f8ff;
        }

        /* ====================================
           2. 基本与重设
           ==================================== */
        html {
            scroll-behavior: smooth;
        }

        body { 
            font-family: '微軟正黑體', 'Microsoft JhengHei', 'PingFang TC', sans-serif; 
            margin: 0; 
            padding: 0; 
            background-color: #ffffff;
            color: var(--color-text); 
            line-height: 1.6;
        }
        
        /* ====================================
           3. 导航列 (Navbar) - Glassmorphism
           ==================================== */
        nav { 
            display: flex; 
            justify-content: center; 
            align-items: center; /* 确保垂直居中 */
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 15px 0;
            
            /* Glassmorphism 核心 CSS */
            background-color: rgba(255, 255, 255, 0.5); /* 略微提高透明度 */
            backdrop-filter: blur(12px); 
            -webkit-backdrop-filter: blur(12px); 
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            z-index: 1000;
        }
        nav a { 
            color: var(--color-primary);
            padding: 8px 18px; 
            text-decoration: none; 
            font-weight: 600; /* 略微减轻粗细 */
            font-size: 0.95em;
            transition: color 0.3s, background-color 0.3s;
            border-radius: 6px;
        }
        nav a:hover { 
            color: white; 
            background-color: var(--color-secondary);
        }

        /* ====================================
           4. 宣傳區 (Hero) - 粒子光影
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

        .hero::before { /* 粒子/光影效果 */
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

        .hero h1 { /* 修正為 H1 提升 SEO 權重 */
            color: white;
            font-size: clamp(2.5em, 5vw, 3.5em); /* 響應式字體 */
            margin-top: 0;
            max-width: 900px;
            text-shadow: 0 0 12px rgba(0, 140, 255, 0.8); 
        }
        
        /* 計數器樣式 */
        .count-up-wrapper {
            margin: 30px 0;
        }
        .count-label {
            font-size: 1.2em; 
            color: rgba(255, 255, 255, 0.8); 
            margin-bottom: 5px;
            display: block;
        }
        .count-up {
            font-size: 5.5em; /* 略微放大 */
            font-weight: 800;
            color: var(--color-accent);
            display: inline-block;
            line-height: 1;
        }
        .count-up-plus {
            font-size: 4em;
            font-weight: 800;
            color: var(--color-accent);
            display: inline-block;
            line-height: 1;
            vertical-align: super;
            margin-left: -5px; /* 微調對齊 */
        }


        /* ====================================
           5. 內容區與排版
           ==================================== */
        .container { 
            width: 90%; /* 擴大內容寬度 */
            max-width: 1200px;
            margin: 0 auto;
            overflow: hidden; 
        }

        .section { 
            background: white; 
            padding: 80px 0;
            margin-bottom: 0; 
        }
        .section h3 {
            border-bottom: 3px solid var(--color-secondary);
            padding-bottom: 10px;
            margin-top: 0;
            color: var(--color-primary);
            font-size: 2em;
            margin-bottom: 35px;
        }

        /* 專案列表樣式 */
        .project-item {
            margin-bottom: 20px;
            padding: 20px;
            border: 1px solid #ddd;
            border-left: 4px solid #ff6600;
            cursor: pointer;
            transition: background-color 0.3s, transform 0.2s, box-shadow 0.3s;
            border-radius: 6px;
        }
        .project-item:hover {
            background-color: var(--color-hover-light); 
            transform: translateY(-3px); /* 微微上抬 */
            box-shadow: 0 4px 12px rgba(0,0,0,0.05);
        }
        .project-item h4 {
            margin: 0 0 5px 0;
            color: var(--color-text);
            font-size: 1.3em;
            display: flex;
            align-items: center;
        }
        .project-item h4 i {
            margin-right: 10px;
            color: #ff6600;
        }
        .project-details {
             /* 使用 max-height 實現平滑展開動畫 */
             max-height: 0;
             overflow: hidden;
             transition: max-height 0.5s ease-in-out;
             opacity: 0;
             padding-top: 0;
             color: #555;
        }
        .project-item.expanded .project-details {
            max-height: 100px; /* 足够显示内容的高度 */
            opacity: 1;
            padding-top: 10px;
        }

        /* 社群連結樣式 */
        .social-links {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
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
            transition: background-color 0.3s, transform 0.3s;
        }
        .social-links a:hover {
            background-color: var(--color-primary);
            transform: translateY(-2px);
        }
        .social-links a i {
            margin-right: 8px;
        }

        /* 頁腳樣式 */
        footer { 
            background-color: #1a1a1a;
            color: #ccc; 
            text-align: center; 
            padding: 30px 0;
            font-size: 0.9em;
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
        
        /* 響應式調整 */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2em;
            }
            nav a:nth-child(1) { /* 隱藏手機版 Logo 以外的連結 */
                display: none;
            }
        }
    </style>
</head>
<body>

    <nav>
        <a href="#top" style="margin-right: 20px; color: var(--color-primary); font-size: 1.3em; font-weight: 800; background: none;">MQI</a>
        
        <a href="#about">團隊介紹</a>
        <a href="#projects">專案成果</a>
        <a href="#vision">核心理念</a>
        <a href="#contact">聯絡我們</a>
    </nav>

    <div class="main-content">
        <section class="hero" id="top">
            <h1>全臺第一個由國高中生主導的跨世代科技革命。</h1>
            
            <div class="count-up-wrapper">
                <p class="count-label">活躍技術成員總數</p>
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
                
                <div class="project-list">
                    <div class="project-item" data-project-id="1">
                        <h4><i class="fas fa-gamepad"></i> 沉浸式應用開發</h4>
                        <div class="project-details"> 
                            <p>嘗試打造高性能的**遊戲模擬器**，深入理解軟硬體架構與優化，推動互動體驗的新界限。</p>
                        </div>
                    </div>

                    <div class="project-item" data-project-id="2">
                        <h4><i class="fas fa-robot"></i> 人工智慧與數據分析</h4>
                        <div class="project-details"> 
                            <p>開發實用的 **AI 工具**，從機器學習模型到自動化解決方案，應對現實世界的挑戰。</p>
                        </div>
                    </div>

                    <div class="project-item" data-project-id="3">
                        <h4><i class="fas fa-sitemap"></i> 系統架構與資料整合</h4>
                        <div class="project-details"> 
                            <p>建構穩健高效的資料系統與後端服務，奠定未來數位基礎，確保專案具備規模化能力。</p>
                        </div>
                    </div>
                </div>
                
                <p style="margin-top: 30px;">每一個專案都是我們挑戰自我、追求卓越的證明。你會親眼見證學生的創意想法如何蛻變成真實可用的作品。</p>
            </section>

            <section id="vision" class="section">
                <h3>核心理念：用創意翻轉未來 🌟</h3>
                <p>我們的最終願景，就是成為**「MetaQuant Initiative：下一代的科技解方」**。</p>
                <p>我們相信透過不斷的學習、協作與實踐，能夠真正做到**「量元計畫– 用創意翻轉未來」**。我們歡迎所有關注科技、渴望創新的朋友，一同追蹤量元計畫MQI，見證這股蓬勃而充滿活力的年輕世代科技火花！</p>
            </section>

            <section id="contact" class="section">
                <h3>聯絡與追蹤我們</h3>
                <p style="text-align: center;">想了解更多資訊或尋求合作？請點擊下方連結，透過我們的社群媒體追蹤最新的動態：</p>
                
                <div class="social-links">
                    <a href="https://www.facebook.com/share/15LSr9zVen6/" target="_blank">
                        <i class="fab fa-facebook-f"></i> Facebook
                    </a>
                    <a href="https://www.tiktok.com/@mqi_tw" target="_blank">
                        <i class="fab fa-tiktok"></i> TikTok
                    </a>
# 🚀 MetaQuant Initiative (MQI) 量元計畫

**全臺第一個由國高中生主導的跨世代科技革命。**

我們相信：**年齡不是限制，而是創造力的起點。**

---

## 💡 關於此專案

此存儲庫（Repository）包含 **MetaQuant Initiative (MQI) 量元計畫**的官方網站代碼，用於展示我們的團隊介紹、專案成果及核心理念。

### 部署狀態 (GitHub Pages)

| 狀態 | 連結 |
| :--- | :--- |
| **網站連結** | [前往 MQI 官方網站](https://MetaQuantInitiative.github.io/mqi/) |

---

## 🔬 我們的專注領域

MQI 專案聚焦於最具前瞻性的科技領域，以確保我們的成員能夠掌握下一代技術的核心：

* **🤖 人工智慧與數據分析 (AI/Data):** 應用機器學習模型應對現實世界的數據挑戰。
* **🕹️ 沉浸式應用與模擬器 (Immersive Tech):** 開發高性能遊戲模擬器和互動應用，深入理解系統架構與優化。
* **⚙️ 系統架構與後端服務 (System Architecture):** 構建穩健、可擴展的後端系統和資料庫基礎設施。

---

## 🤝 聯絡與追蹤我們

我們歡迎所有對科技有熱忱的朋友與潛在合作夥伴聯繫，或透過我們的社群媒體追蹤最新的專案動態。

| 平台 | 連結 |
| :--- | :--- |
| **Facebook** | [前往 Facebook](https://www.facebook.com/share/15LSr9zVen6/) |
| **Instagram** | [前往 Instagram](https://www.instagram.com/metaquant_initiative) |
| **YouTube** | [前往 YouTube 頻道](https://youtube.com/channel/UCffKddZyMhuY7NWDVkq-Pvg?si=ueWSHiu8RGNj7E5D) |
| **Discord** | [加入我們的社群](https://discord.gg/yHRkzDAFGK) |
| **TikTok** | [前往 TikTok](https://www.tiktok.com/@mqi_tw) |
</body>
</html>
