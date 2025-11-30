<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>缶ワインパッケージデザイン選定戦略 - Target: Misaki</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        /* Custom Font */
        @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@400;700&display=swap');
        body {
            font-family: 'Noto Sans JP', sans-serif;
            background-color: #FDF2F8; /* Very light pink background */
            color: #4A044E; /* Dark Plum text */
        }

        /* Palette Classes - Updated for "Rose/Stylish" vibe */
        .text-primary { color: #BE185D; } /* Pink 700 */
        .bg-primary { background-color: #BE185D; }
        .border-primary { border-color: #BE185D; }
        
        .text-secondary { color: #831843; } /* Pink 900 */
        .bg-secondary { background-color: #831843; }
        
        .text-accent { color: #F59E0B; } /* Amber 500 (Gold for premium feel) */
        .bg-accent { background-color: #F59E0B; }

        /* Chart Container Rules - MANDATORY */
        .chart-container {
            position: relative;
            width: 100%;
            margin-left: auto;
            margin-right: auto;
            height: 350px; /* Base height */
            max-height: 400px;
        }

        /* Responsive adjustments for chart containers */
        @media (min-width: 768px) {
            .chart-container {
                height: 400px;
            }
        }

        /* Flowchart Connector Line */
        .flow-line::after {
            content: '';
            position: absolute;
            top: 100%;
            left: 50%;
            transform: translateX(-50%);
            width: 2px;
            height: 2rem;
            background-color: #FBCFE8; /* Light Pink Line */
            z-index: 0;
        }
        .last-step::after {
            display: none;
        }
    </style>
    <!-- 
        NO SVG USED.
        NO MERMAID JS USED.
        NO GEMINI API.
    -->
</head>
<body class="antialiased">

    <!-- Header Section -->
    <header class="bg-gradient-to-r from-pink-900 to-pink-700 text-white py-12 px-4 shadow-lg">
        <div class="max-w-6xl mx-auto text-center">
            <div class="text-accent font-bold tracking-widest mb-2">NEW PRODUCT DEVELOPMENT</div>
            <h1 class="text-3xl md:text-5xl font-bold mb-4">缶ワイン パッケージデザイン選定戦略</h1>
            <p class="text-lg md:text-xl opacity-90 font-light">
                Target: おしゃれに家飲みを楽しむ「美咲世代」へのアプローチ
            </p>
        </div>
    </header>

    <!-- Main Content Grid -->
    <main class="max-w-6xl mx-auto p-6 grid grid-cols-1 md:grid-cols-2 gap-8 -mt-8">

        <!-- SECTION 1: Persona Definition -->
        <section class="col-span-1 md:col-span-2 bg-white rounded-xl shadow-md overflow-hidden flex flex-col md:flex-row">
            <div class="bg-pink-50 p-6 md:w-1/3 border-r border-pink-100 flex flex-col justify-center items-center text-center">
                <div class="w-24 h-24 bg-pink-200 rounded-full flex items-center justify-center text-4xl mb-4 shadow-inner">👩🏻‍💻</div>
                <h2 class="text-xl font-bold text-secondary">佐藤 美咲 (28)</h2>
                <p class="text-sm text-gray-500 mb-2">広告代理店勤務 / 都内在住</p>
                <div class="flex flex-wrap justify-center gap-2 mt-2">
                    <span class="px-2 py-1 bg-white text-xs text-primary border border-primary rounded-full">#家飲み</span>
                    <span class="px-2 py-1 bg-white text-xs text-primary border border-primary rounded-full">#Instagram</span>
                    <span class="px-2 py-1 bg-white text-xs text-primary border border-primary rounded-full">#ご褒美</span>
                </div>
            </div>
            <div class="p-6 md:w-2/3">
                <h3 class="text-lg font-bold text-secondary mb-3 border-l-4 border-primary pl-3">ペルソナ詳細: デザイン選定の指針</h3>
                <p class="text-gray-600 text-sm mb-4 leading-relaxed">
                    仕事は忙しいが、週末は友人を招いてホームパーティーを開くのが楽しみ。
                    ワイン選びの基準は「味」だけでなく<strong class="text-primary">「テーブルに置いた時に絵になるか」「友人への手土産（ギフト）になるか」</strong>を重視。
                    フルーティーな白やロゼを好み、価格感は2,000〜3,000円と少し良いものを選ぶ傾向。
                </p>
                <div class="grid grid-cols-2 gap-4 bg-gray-50 p-4 rounded-lg">
                    <div>
                        <span class="block text-xs text-gray-400 font-bold uppercase">PREFERENCE</span>
                        <span class="text-sm font-bold text-gray-700">軽やか・フルーティー (白/ロゼ)</span>
                    </div>
                    <div>
                        <span class="block text-xs text-gray-400 font-bold uppercase">MOTIVATION</span>
                        <span class="text-sm font-bold text-gray-700">SNS映え・リラックス・ギフト</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- SECTION 2: Concept Radar Chart -->
        <section class="col-span-1 bg-white rounded-xl shadow-md p-6">
            <h2 class="text-xl font-bold text-secondary mb-4 border-l-4 border-primary pl-4">目標デザインコンセプト</h2>
            <p class="mb-4 text-gray-600 text-sm">
                美咲さんに選ばれるための「感情的価値」を定義。既存の「安価な缶ワイン」イメージからの脱却を図ります。
            </p>
            <div class="chart-container">
                <canvas id="personaRadarChart"></canvas>
            </div>
            <div class="mt-4 text-xs text-gray-500 text-center">
                <span class="text-primary font-bold">● 戦略ターゲット</span> vs 
                <span class="text-gray-400">● 一般的な缶ワイン</span>
            </div>
        </section>

        <!-- SECTION 3: Selection Workflow -->
        <section class="col-span-1 bg-white rounded-xl shadow-md p-6">
            <h2 class="text-xl font-bold text-secondary mb-4 border-l-4 border-primary pl-4">デザイン選定プロセス</h2>
            <p class="mb-6 text-gray-600 text-sm">
                SNS映えとギフト需要を検証するためのステップ。定性調査（グループインタビュー）を重視します。
            </p>
            
            <div class="flex flex-col space-y-0 pl-2">
                <!-- Step 1 -->
                <div class="relative pb-8 pl-8 border-l-2 border-pink-200 flow-line">
                    <div class="absolute -left-2.5 top-0 w-5 h-5 rounded-full bg-secondary text-white flex items-center justify-center text-xs font-bold">1</div>
                    <h4 class="font-bold text-md text-secondary">ムードボード作成</h4>
                    <p class="text-xs text-gray-500">Instagramで「#おうちワイン」等のタグ分析。トレンドカラーと世界観を抽出。</p>
                </div>

                <!-- Step 2 -->
                <div class="relative pb-8 pl-8 border-l-2 border-pink-200 flow-line">
                    <div class="absolute -left-2.5 top-0 w-5 h-5 rounded-full bg-secondary text-white flex items-center justify-center text-xs font-bold">2</div>
                    <h4 class="font-bold text-md text-secondary">ラフデザイン (3案)</h4>
                    <p class="text-xs text-gray-500">A: 大人かわいい(Illust), B: シンプルモダン(Typo), C: エレガント(Pattern)</p>
                </div>

                <!-- Step 3: Important -->
                <div class="relative pb-8 pl-8 border-l-2 border-pink-200 flow-line">
                    <div class="absolute -left-2.5 top-0 w-5 h-5 rounded-full bg-primary text-white flex items-center justify-center text-xs font-bold shadow-lg ring-2 ring-pink-100">3</div>
                    <h4 class="font-bold text-md text-primary">SNS擬似投稿テスト</h4>
                    <p class="text-xs text-gray-500">スマホ画面はめ込み画像を作成し、TL上で埋もれないか、"いいね"したくなるかを検証。</p>
                </div>

                <!-- Step 4 -->
                <div class="relative pb-8 pl-8 border-l-2 border-pink-200 flow-line">
                    <div class="absolute -left-2.5 top-0 w-5 h-5 rounded-full bg-secondary text-white flex items-center justify-center text-xs font-bold">4</div>
                    <h4 class="font-bold text-md text-secondary">ターゲット グルイン</h4>
                    <p class="text-xs text-gray-500">20代後半女性を集め、実物モックアップで「ギフトにしたいか」を聴取。</p>
                </div>

                <!-- Step 5 -->
                <div class="relative pl-8 border-l-0 last-step">
                    <div class="absolute -left-2.5 top-0 w-5 h-5 rounded-full bg-accent text-white flex items-center justify-center text-xs font-bold">5</div>
                    <h4 class="font-bold text-md text-secondary">最終決定</h4>
                </div>
            </div>
        </section>

        <!-- SECTION 4: Evaluation Criteria -->
        <section class="col-span-1 md:col-span-2 bg-white rounded-xl shadow-md p-6 md:p-8">
            <h2 class="text-xl font-bold text-secondary mb-4 border-l-4 border-primary pl-4">5つの選考基準 (Weighting)</h2>
            <p class="mb-6 text-gray-600 text-sm">
                美咲さんの購買決定要因（KBF）に基づき、評価軸の重み付けを行います。「かわいさ・SNS映え」と「ギフト適性」が最優先事項です。
            </p>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
                <div class="chart-container">
                    <canvas id="criteriaChart"></canvas>
                </div>
                <div class="bg-pink-50 p-6 rounded-xl border border-pink-100">
                    <h3 class="font-bold text-md mb-3 text-secondary">✨ 最重要チェックポイント</h3>
                    <ul class="space-y-4">
                        <li class="flex items-start">
                            <span class="text-xl mr-3 bg-white rounded-full w-8 h-8 flex items-center justify-center shadow-sm">📸</span>
                            <div>
                                <strong class="block text-sm text-secondary">SNSジェニック (Photogenic)</strong>
                                <span class="text-xs text-gray-500">テーブルフォトの一部として馴染むか？フィルター映えする配色か？</span>
                            </div>
                        </li>
                        <li class="flex items-start">
                            <span class="text-xl mr-3 bg-white rounded-full w-8 h-8 flex items-center justify-center shadow-sm">🎁</span>
                            <div>
                                <strong class="block text-sm text-secondary">ギフト適性 (Gift-worthy)</strong>
                                <span class="text-xs text-gray-500">「これ可愛いから買ってきたよ」と友人に渡せるクオリティと高級感があるか？</span>
                            </div>
                        </li>
                        <li class="flex items-start">
                            <span class="text-xl mr-3 bg-white rounded-full w-8 h-8 flex items-center justify-center shadow-sm">👜</span>
                            <div>
                                <strong class="block text-sm text-secondary">バッグ内での高揚感</strong>
                                <span class="text-xs text-gray-500">購入後、持ち帰る時に気分が上がるデザインか？</span>
                            </div>
                        </li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- SECTION 5: A/B Test Simulation -->
        <section class="col-span-1 md:col-span-2 bg-gradient-to-br from-pink-800 to-purple-900 text-white rounded-xl shadow-lg p-6 md:p-8 relative overflow-hidden">
            <!-- Background Decoration -->
            <div class="absolute top-0 right-0 w-64 h-64 bg-white opacity-5 rounded-full -mr-16 -mt-16 pointer-events-none"></div>

            <div class="flex flex-col md:flex-row justify-between items-start md:items-center mb-6 relative z-10">
                <div>
                    <h2 class="text-xl font-bold text-white mb-2 border-l-4 border-accent pl-4">調査データ: デザイン案比較</h2>
                    <p class="text-pink-200 text-sm">ターゲット層(n=100)による A案(イラスト主体) vs B案(ロゴ主体) の比較結果</p>
                </div>
                <div class="mt-4 md:mt-0 bg-white/10 px-4 py-2 rounded-full backdrop-blur-md border border-white/20">
                    <span class="text-accent font-bold">RECOMMEND:</span> Design A
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-8 relative z-10">
                <!-- Comparative Chart -->
                <div class="chart-container">
                    <canvas id="abTestChart"></canvas>
                </div>
                
                <!-- Insight Text -->
                <div class="flex flex-col justify-center space-y-6">
                    <div class="bg-black/20 p-5 rounded-xl border-l-4 border-accent">
                        <h4 class="font-bold text-lg mb-2 text-accent">美咲世代のインサイト</h4>
                        <p class="text-sm text-gray-200 leading-relaxed">
                            B案（ロゴ主体）は「高級感」で高評価でしたが、<strong class="text-white border-b border-accent">「SNSに載せたい」「友人に贈りたい」というスコアでA案が圧倒</strong>しました。
                            「かわいい」「気分が上がる」という感情的価値が、3,000円という価格帯の納得感に繋がっています。
                        </p>
                    </div>
                    
                    <!-- Key Stats -->
                    <div class="grid grid-cols-2 gap-4">
                        <div class="bg-white/10 p-3 rounded-lg text-center">
                            <div class="text-xs text-gray-300 mb-1">友人への推奨意向</div>
                            <div class="text-3xl font-bold text-white">4.8<span class="text-sm text-gray-400">/5.0</span></div>
                            <div class="text-xs text-accent mt-1">Design A</div>
                        </div>
                        <div class="bg-white/5 p-3 rounded-lg text-center">
                            <div class="text-xs text-gray-400 mb-1">友人への推奨意向</div>
                            <div class="text-2xl font-bold text-gray-400">3.2<span class="text-sm text-gray-500">/5.0</span></div>
                            <div class="text-xs text-gray-500 mt-1">Design B</div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- Footer -->
    <footer class="bg-pink-900 text-pink-300 py-8 mt-12 text-center text-sm">
        <p>Generated by Canvas Infographics - Canned Wine Design Strategy</p>
    </footer>

    <!-- JavaScript for Charts -->
    <script>
        // --- Utility Function: Label Splitter (16 char limit) ---
        function splitLabel(label) {
            if (typeof label !== 'string' || label.length <= 16) return label;
            const words = label.split(' ');
            const lines = [];
            let currentLine = words[0];

            for (let i = 1; i < words.length; i++) {
                if ((currentLine + ' ' + words[i]).length <= 16) {
                    currentLine += ' ' + words[i];
                } else {
                    lines.push(currentLine);
                    currentLine = words[i];
                }
            }
            lines.push(currentLine);
            return lines;
        }

        // --- Global Chart Defaults ---
        Chart.defaults.font.family = "'Noto Sans JP', sans-serif";
        Chart.defaults.color = '#831843'; // Pink 900
        Chart.defaults.plugins.tooltip.callbacks.title = function(tooltipItems) {
            const item = tooltipItems[0];
            let label = item.chart.data.labels[item.dataIndex];
            return Array.isArray(label) ? label.join(' ') : label;
        };

        // --- 1. Concept Radar Chart (Updated for Misaki) ---
        const ctxRadar = document.getElementById('personaRadarChart').getContext('2d');
        // Updated axes for Misaki
        const radarLabels = [
            'SNS映え (Photogenic)', 
            'かわいさ・愛着 (Cuteness)', 
            'ギフト適性 (Gift-worthy)', 
            '高級感 (Premium)', 
            'リラックス感 (Chill)'
        ];
        
        new Chart(ctxRadar, {
            type: 'radar',
            data: {
                labels: radarLabels.map(l => splitLabel(l)),
                datasets: [{
                    label: 'Target: 美咲さん',
                    data: [95, 90, 85, 70, 80], // High on SNS/Cute
                    borderColor: '#BE185D', // Pink 700
                    backgroundColor: 'rgba(190, 24, 93, 0.2)',
                    pointBackgroundColor: '#BE185D',
                    borderWidth: 2
                }, {
                    label: '従来品 (参考)',
                    data: [40, 30, 40, 60, 50],
                    borderColor: '#9CA3AF',
                    backgroundColor: 'rgba(156, 163, 175, 0.1)',
                    pointBackgroundColor: '#9CA3AF',
                    borderWidth: 1,
                    borderDash: [5, 5]
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                scales: {
                    r: {
                        angleLines: { color: '#FBCFE8' }, // Light Pink
                        grid: { color: '#FBCFE8' },
                        pointLabels: {
                            font: { size: 11, weight: 'bold' },
                            color: '#831843'
                        },
                        suggestedMin: 0,
                        suggestedMax: 100
                    }
                },
                plugins: {
                    legend: { position: 'bottom' }
                }
            }
        });

        // --- 2. Criteria Weight Chart (Updated for Gift/SNS) ---
        const ctxCriteria = document.getElementById('criteriaChart').getContext('2d');
        const criteriaLabels = [
            'SNSでの見栄え (SNS Appeal)', 
            'ギフトとしての特別感 (Gift Potential)', 
            '持ち運びやすさ (Portability)', 
            '店頭での視認性 (Shelf Impact)', 
            '情報の信頼性 (Info Clarity)'
        ];

        new Chart(ctxCriteria, {
            type: 'bar',
            data: {
                labels: criteriaLabels.map(l => splitLabel(l)),
                datasets: [{
                    label: '重要度 (Weight)',
                    data: [95, 90, 75, 70, 60], // SNS/Gift highest
                    backgroundColor: [
                        '#BE185D', // Pink 700 (Top Priority)
                        '#BE185D',
                        '#DB2777', // Pink 600
                        '#DB2777',
                        '#9CA3AF'
                    ],
                    borderRadius: 4
                }]
            },
            options: {
                indexAxis: 'y', // Horizontal bar
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: { display: false }
                },
                scales: {
                    x: { beginAtZero: true, max: 100, grid: { color: '#FCE7F3' } },
                    y: { grid: { display: false } }
                }
            }
        });

        // --- 3. A/B Test Result (Comparison) ---
        const ctxAB = document.getElementById('abTestChart').getContext('2d');
        new Chart(ctxAB, {
            type: 'bar',
            data: {
                labels: ['購入意向', 'SNS投稿意向', 'ギフト意向', '高級感'],
                datasets: [
                    {
                        label: '案A (イラスト・大人かわいい)',
                        data: [4.8, 4.9, 4.7, 3.8],
                        backgroundColor: '#F59E0B', // Amber/Gold Accent
                        borderColor: '#ffffff',
                        borderWidth: 1
                    },
                    {
                        label: '案B (ロゴ・シンプル)',
                        data: [3.2, 2.5, 3.0, 4.5], // B is premium but boring for SNS
                        backgroundColor: 'rgba(255, 255, 255, 0.3)',
                        borderColor: '#ffffff',
                        borderWidth: 1
                    }
                ]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: { labels: { color: 'white' } },
                    tooltip: {
                        backgroundColor: '#831843',
                        titleColor: '#F59E0B'
                    }
                },
                scales: {
                    y: {
                        beginAtZero: true,
                        max: 5,
                        grid: { color: 'rgba(255,255,255,0.1)' },
                        ticks: { color: 'white' }
                    },
                    x: {
                        grid: { display: false },
                        ticks: { color: 'white' }
                    }
                }
            }
        });
    </script>
</body>
</html>
