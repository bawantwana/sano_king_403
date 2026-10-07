# sano_king_403
web
<!DOCTYPE html>
<html lang="ku" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- ناونیشانی وێبسایتەکە -->
    <title>Sanoking.com - پلاتفۆرمی ڤیدیۆی کوردی</title>
    <meta name="description" content="Sanoking.com - باشترین شوێن بۆ سەیرکردنی ڤیدیۆ و پەخشی زیندوو بە زمانی کوردی.">
    <meta name="keywords" content="Sanoking, ڤیدیۆی کوردی, پەخشی زیندوو, Sanoking.com">
    
    <!-- فۆنتی کوردی NRT -->
    <link href="https://fonts.googleapis.com/css2?family=NRT:wght@400;600;800&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg-dark: #0f172a;
            --bg-card: #1e293b;
            --primary: #3b82f6;
            --accent: #8b5cf6;
            --text-main: #f8fafc;
            --text-muted: #94a3b8;
            --gradient: linear-gradient(135deg, #3b82f6 0%, #8b5cf6 100%);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'NRT', sans-serif;
            background-color: var(--bg-dark);
            color: var(--text-main);
            line-height: 1.6;
        }

        /* Header */
        header {
            background: rgba(15, 23, 42, 0.95);
            backdrop-filter: blur(10px);
            position: sticky;
            top: 0;
            z-index: 100;
            border-bottom: 1px solid rgba(255,255,255,0.1);
            padding: 1rem 2rem;
        }

        nav {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 800;
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 10px;
            letter-spacing: 1px;
        }

        .search-bar {
            background: var(--bg-card);
            border: 1px solid rgba(255,255,255,0.1);
            padding: 0.5rem 1rem;
            border-radius: 50px;
            display: flex;
            align-items: center;
            width: 40%;
        }

        .search-bar input {
            background: transparent;
            border: none;
            color: white;
            width: 100%;
            outline: none;
            font-family: 'NRT', sans-serif;
            padding: 0 10px;
        }

        .upload-btn {
            background: var(--gradient);
            color: white;
            padding: 0.6rem 1.5rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 700;
            transition: transform 0.2s;
            border: none;
            cursor: pointer;
        }

        .upload-btn:hover { transform: scale(1.05); }

        /* Hero Section */
        .hero {
            max-width: 1400px;
            margin: 2rem auto;
            padding: 0 2rem;
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 2rem;
        }

        .main-player {
            position: relative;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(0,0,0,0.5);
            background: black;
        }

        .main-player video, .main-player iframe {
            width: 100%;
            aspect-ratio: 16/9;
            border: none;
        }

        .video-info {
            padding: 1.5rem 0;
        }

        .video-title {
            font-size: 1.8rem;
            margin-bottom: 0.5rem;
            color: white;
        }

        .video-meta {
            display: flex;
            gap: 1rem;
            color: var(--text-muted);
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }

        .channel-info {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding-top: 1rem;
            border-top: 1px solid rgba(255,255,255,0.1);
        }

        .avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--gradient);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 1.2rem;
        }

        /* Sidebar */
        .sidebar h3 { margin-bottom: 1rem; font-size: 1.2rem; color: white; }

        .video-list {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .video-item {
            display: flex;
            gap: 1rem;
            cursor: pointer;
            transition: background 0.2s;
            padding: 0.5rem;
            border-radius: 10px;
        }

        .video-item:hover { background: var(--bg-card); }

        .thumbnail {
            width: 160px;
            height: 90px;
            background: #334155;
            border-radius: 8px;
            object-fit: cover;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            color: rgba(255,255,255,0.2);
            font-size: 2rem;
        }

        .duration {
            position: absolute;
            bottom: 5px;
            right: 5px;
            background: rgba(0,0,0,0.8);
            padding: 2px 6px;
            border-radius: 4px;
            font-size: 0.75rem;
            color: white;
        }

        .item-info h4 {
            font-size: 1rem;
            margin-bottom: 0.3rem;
            line-height: 1.3;
            color: #e2e8f0;
        }

        .item-info p {
            color: var(--text-muted);
            font-size: 0.85rem;
        }

        /* Grid Section */
        .grid-section {
            max-width: 1400px;
            margin: 3rem auto;
            padding: 0 2rem;
        }

        .grid-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
        }

        .video-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1.5rem;
        }

        .grid-card {
            background: var(--bg-card);
            border-radius: 15px;
            overflow: hidden;
            transition: transform 0.3s;
            cursor: pointer;
            border: 1px solid rgba(255,255,255,0.05);
        }

        .grid-card:hover { transform: translateY(-5px); border-color: var(--primary); }

        .grid-thumbnail {
            width: 100%;
            height: 160px;
            background: linear-gradient(45deg, #1e293b, #334155);
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            color: rgba(255,255,255,0.2);
            font-size: 2rem;
        }

        .grid-content { padding: 1rem; }
        .grid-title { font-weight: 700; margin-bottom: 0.5rem; font-size: 1rem; color: #f1f5f9; }
        .grid-meta { color: var(--text-muted); font-size: 0.8rem; display: flex; justify-content: space-between; }

        /* Footer */
        footer {
            text-align: center;
            padding: 2rem;
            background: #0f172a;
            color: #64748b;
            border-top: 1px solid rgba(255,255,255,0.1);
            margin-top: 3rem;
        }

        /* Responsive */
        @media (max-width: 900px) {
            .hero { grid-template-columns: 1fr; }
            .search-bar { display: none; }
            .sidebar { display: none; }
            .video-grid { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>

    <!-- Header -->
    <header>
        <nav>
            <a href="#" class="logo">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polygon points="23 7 16 12 23 17 23 7"></polygon><rect x="1" y="5" width="15" height="14" rx="2" ry="2"></rect></svg>
                Sanoking
            </a>
            <div class="search-bar">
                <input type="text" placeholder="گەڕان لە Sanoking.com...">
            </div>
            <button class="upload-btn">بڵاوکردنەوە</button>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="main-player">
            <!-- نموونەی ڤیدیۆ -->
            <video controls poster="https://via.placeholder.com/1280x720/1e293b/ffffff?text=Sanoking+Video+Player">
                <source src="movie.mp4" type="video/mp4">
                بەرنامەکەت پشتگیری ویدیۆ ناکات.
            </video>
        </div>
        
        <div class="video-info">
            <h1 class="video-title">پێشکەشکردنی پلاتفۆرمی نوێی Sanoking</h1>
            <div class="video-meta">
                <span>١٢٬٥٠٠ بینین</span>
                <span>٢ کاتژمێر لەمەوبەر</span>
                <span>Sanoking TV</span>
            </div>
            <div class="channel-info">
                <div class="avatar">S</div>
                <div>
                    <h4>Sanoking Official</h4>
                    <p style="color: var(--text-muted); font-size: 0.8rem;">١٠٬٠٠٠ بڵاوکەرەوە</p>
                </div>
                <button class="upload-btn" style="padding: 0.4rem 1rem; font-size: 0.9rem; margin-right: auto;">دەستکردن</button>
            </div>
        </div>

        <!-- Sidebar -->
        <aside class="sidebar">
            <h3>دەربەدەست</h3>
            <div class="video-list">
                <div class="video-item">
                    <div class="thumbnail">
                        <span>▶</span>
                        <span class="duration">١٠:٢٤</span>
                    </div>
                    <div class="item-info">
                        <h4>چۆن دەتوانیت ڤیدیۆ بڵاوکەیتەوە لە Sanoking؟</h4>
                        <p>٥٬٠٠٠ بینین • ١ کاتژمێر لەمەوبەر</p>
                    </div>
                </div>
                <div class="video-item">
                    <div class="thumbnail">
                        <span>▶</span>
                        <span class="duration">٠٥:١٢</span>
                    </div>
                    <div class="item-info">
                        <h4>گەشتکردن بۆ هەولێر - ڤیدیۆیەکی تایبەت</h4>
                        <p>١٢٬٠٠٠ بینین • ٣ کاتژمێر لەمەوبەر</p>
                    </div>
                </div>
                <div class="video-item">
                    <div class="thumbnail">
                        <span>▶</span>
                        <span class="duration">١٥:٠٠</span>
                    </div>
                    <div class="item-info">
                        <h4>پەخشی زیندوو: کۆبوونەوەی Sanoking</h4>
                        <p>٢٥٬٠٠٠ بینین • ڕۆژێک لەمەوبەر</p>
                    </div>
                </div>
                <div class="video-item">
                    <div class="thumbnail">
                        <span>▶</span>
                        <span class="duration">٠٨:٤٥</span>
                    </div>
                    <div class="item-info">
                        <h4>نەرمەکاڵای نوێی کوردی بۆ مۆبایل</h4>
                        <p>٨٬٥٠٠ بینین • ٤ کاتژمێر لەمەوبەر</p>
                    </div>
                </div>
            </div>
        </aside>
    </section>

    <!-- Grid Section -->
    <section class="grid-section">
        <div class="grid-header">
            <h2>ڤیدیۆیەکانی نوێ</h2>
            <div style="color: var(--primary); font-weight: bold;">هەموویان ببینە</div>
        </div>
        <div class="video-grid">
            <!-- Video Card 1 -->
            <div class="grid-card">
                <div class="grid-thumbnail">▶</div>
                <div class="grid-content">
                    <h3 class="grid-title">بەشداریکردن لە بەرنامەی Sanoking</h3>
                    <div class="grid-meta">
                        <span>١٠٬٠٠٠ بینین</span>
                        <span>١ ڕۆژ لەمەوبەر</span>
                    </div>
                </div>
            </div>
            <!-- Video Card 2 -->
            <div class="grid-card">
                <div class="grid-thumbnail">▶</div>
                <div class="grid-content">
                    <h3 class="grid-title">تایبەتمەندییەکانی نوێی وێبسایتەکە</h3>
                    <div class="grid-meta">
                        <span>٥٬٤٠٠ بینین</span>
                        <span>٢ ڕۆژ لەمەوبەر</span>
                    </div>
                </div>
            </div>
            <!-- Video Card 3 -->
            <div class="grid-card">
                <div class="grid-thumbnail">▶</div>
                <div class="grid-content">
                    <h3 class="grid-title">چیرۆکی سەرکەوتنی کوردستان</h3>
                    <div class="grid-meta">
                        <span>٢٠٬٠٠٠ بینین</span>
                        <span>٣ ڕۆژ لەمەوبەر</span>
                    </div>
                </div>
            </div>
            <!-- Video Card 4 -->
            <div class="grid-card">
                <div class="grid-thumbnail">▶</div>
                <div class="grid-content">
                    <h3 class="grid-title">پەخشی زیندوو: وەڵامدانەوەی پرسیارەکان</h3>
                    <div class="grid-meta">
                        <span>١٥٬٠٠٠ بینین</span>
                        <span>٥ ڕۆژ لەمەوبەر</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <p>&copy; ٢٠٢٦ Sanoking.com - هەموو مافەکان پارێزراون. دروستکراوە بە VX.</p>
    </footer>

    <script>
        // کۆدێکی سادە بۆ ئەوەی کاتێک کلیک لەسەر ڤیدیۆ دەکەیت، پەیامێک بێت
        const videoItems = document.querySelectorAll('.video-item, .grid-card');
        videoItems.forEach(item => {
            item.addEventListener('click', () => {
                alert('ئەمە نموونەیە: ڤیدیۆکە دەکرێتەوە لە پەلەی سەرەکی!');
            });
        });
    </script>
</body>
</html>
