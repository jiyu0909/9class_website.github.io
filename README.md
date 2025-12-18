<!doctype html>
<html lang="ko">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2-9 | Information Center</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" as="style" crossorigin href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.css" />
    <style>
        body {
            font-family: "Pretendard Variable", -apple-system, sans-serif;
            background-color: #f5f5f7;
            color: #1d1d1f;
            word-break: keep-all;
            -webkit-font-smoothing: antialiased;
        }
        .apple-blur {
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: saturate(180%) blur(20px);
            -webkit-backdrop-filter: saturate(180%) blur(20px);
        }
        .card {
            background: #ffffff;
            border-radius: 30px;
            border: 1px solid rgba(0,0,0,0.03);
            box-shadow: 0 4px 24px rgba(0,0,0,0.04);
        }
        .timetable-container {
            display: flex;
            gap: 12px;
            overflow-x: auto;
            padding-bottom: 8px;
            scrollbar-width: none;
        }
        .timetable-container::-webkit-scrollbar { display: none; }
        .day-box {
            flex: 0 0 140px;
            background: #fbfbfd;
            padding: 18px;
            border-radius: 20px;
            text-align: center;
        }
        #main-content { display: none; }
        .fade-in { animation: fadeIn 1s cubic-bezier(0.4, 0, 0.2, 1); }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
        .quote-accent {
            background: linear-gradient(120deg, #0071e3, #00d2ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
    </style>
</head>
<body class="selection:bg-blue-100">

    <div id="login-section" class="min-h-screen flex items-center justify-center p-6">
        <div class="w-full max-w-[380px] text-center space-y-10 fade-in">
            <h1 class="text-5xl font-bold tracking-tight">2-9.</h1>
            <div class="space-y-3">
                <input id="login-number" type="text" placeholder="학번" class="w-full h-14 px-5 rounded-2xl border border-[#d2d2d7] bg-white/50 focus:border-[#0071e3] outline-none text-lg text-center">
                <input id="login-name" type="text" placeholder="이름" class="w-full h-14 px-5 rounded-2xl border border-[#d2d2d7] bg-white/50 focus:border-[#0071e3] outline-none text-lg text-center">
                <button onclick="checkLogin()" class="w-full h-14 bg-[#1d1d1f] text-white rounded-2xl font-semibold text-lg hover:opacity-90 transition-all mt-4">계속하기</button>
            </div>
            <p id="login-error" class="text-red-500 font-medium hidden">다시 한번 확인해 줄래? 😊</p>
        </div>
    </div>

    <div id="main-content">
        <nav class="apple-blur sticky top-0 z-50 border-b border-black/5">
            <div class="max-w-[980px] mx-auto px-6 h-[52px] flex items-center justify-between font-semibold">
                <span class="text-xl tracking-tight">2-9 Info</span>
                <span class="text-sm text-[#86868b]">Suneung D-Day</span>
            </div>
        </nav>

        <main class="max-w-[980px] mx-auto px-6 py-12 space-y-10">
            
            <section class="text-center space-y-4 py-8 fade-in">
                <p class="text-[#86868b] text-sm md:text-base font-bold tracking-[0.2em] uppercase">2027년 11월 19일 수능</p>
                <div id="dday-display" class="text-[100px] md:text-[160px] font-bold tracking-tighter leading-none">D-???</div>
                <p class="text-2xl md:text-3xl font-semibold text-gray-400 italic">"Stay hungry, Stay foolish."</p>
            </section>

            <section class="card p-10 md:p-16 border-l-[12px] border-blue-500 fade-in" style="animation-delay: 0.2s;">
                <div class="max-w-2xl">
                    <span class="text-blue-600 font-bold text-lg uppercase tracking-widest mb-4 block">Teacher's Message</span>
                    <h2 class="text-3xl md:text-4xl font-bold leading-[1.3] mb-8 quote-accent">
                        "기말고사 고생 많았어! <br>지치지 말고 끝까지 함께 가보자. <br>너희는 생각보다 훨씬 더 단단한 사람들이야."
                    </h2>
                    <div class="flex items-center gap-4">
                        <div class="w-12 h-12 rounded-full bg-blue-100 flex items-center justify-center text-xl font-bold text-blue-600">최</div>
                        <div>
                            <p class="text-xl font-bold">최은지 선생님</p>
                            <p class="text-[#86868b]">우리 2-9반의 든든한 가이드</p>
                        </div>
                    </div>
                </div>
            </section>

            <section class="card p-10 md:p-12 fade-in shadow-xl" style="animation-delay: 0.4s;">
                <div class="flex items-center justify-between mb-10">
                    <h3 class="text-3xl font-bold tracking-tight">오늘의 식단 🍴</h3>
                    <span class="bg-gray-100 px-4 py-1 rounded-full text-sm font-bold text-gray-500">1월 월요일</span>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-12">
                    <div class="space-y-6">
                        <div class="flex items-center gap-2">
                            <span class="w-3 h-3 rounded-full bg-blue-500"></span>
                            <span class="font-bold uppercase tracking-[0.2em] text-[#86868b]">Lunch</span>
                        </div>
                        <ul class="text-2xl font-semibold leading-relaxed space-y-2">
                            <li>오색현미밥</li>
                            <li>소고기배추된장국</li>
                            <li>숯불닭갈비보쌈</li>
                            <li>노란호박전</li>
                            <li class="text-blue-600">샤인머스켓 ✨</li>
                            <li class="text-sm font-medium text-gray-400">오이고추양파초절임, 배추김치, 상추깻잎쌈&쌈장</li>
                        </ul>
                    </div>
                    <div class="space-y-6">
                        <div class="flex items-center gap-2">
                            <span class="w-3 h-3 rounded-full bg-orange-500"></span>
                            <span class="font-bold uppercase tracking-[0.2em] text-[#86868b]">Dinner</span>
                        </div>
                        <ul class="text-2xl font-semibold leading-relaxed space-y-2">
                            <li>청차조밥</li>
                            <li>병천식순대국</li>
                            <li>돈사태메추리알조림</li>
                            <li>오징어야채초무침</li>
                            <li>깍두기</li>
                            <li class="text-orange-500">감귤 🍊</li>
                        </ul>
                    </div>
                </div>
            </section>

            <section class="card p-8 md:p-10 fade-in" style="animation-delay: 0.6s;">
                <h3 class="text-3xl font-bold tracking-tight mb-8">주간 시간표</h3>
                <div class="timetable-container">
                    <div class="day-box"><span class="block font-bold text-blue-600 mb-4 border-b border-blue-100 pb-2">월</span><ul class="space-y-3 font-medium text-gray-600 text-sm"><li>독서</li><li>영어2</li><li>수학2</li><li>일어</li><li>체육</li></ul></div>
                    <div class="day-box"><span class="block font-bold text-blue-600 mb-4 border-b border-blue-100 pb-2">화</span><ul class="space-y-3 font-medium text-gray-600 text-sm"><li>확통</li><li>수학2</li><li>영어2</li><li>독서</li><li>진로</li></ul></div>
                    <div class="day-box"><span class="block font-bold text-blue-600 mb-4 border-b border-blue-100 pb-2">수</span><ul class="space-y-3 font-medium text-gray-600 text-sm"><li>수학2</li><li>독서</li><li>영어2</li><li>체육</li><li>일어</li></ul></div>
                    <div class="day-box"><span class="block font-bold text-blue-600 mb-4 border-b border-blue-100 pb-2">목</span><ul class="space-y-3 font-medium text-gray-600 text-sm"><li>영독</li><li>수학2</li><li>음악</li><li>독서</li><li>영어2</li></ul></div>
                    <div class="day-box"><span class="block font-bold text-blue-600 mb-4 border-b border-blue-100 pb-2">금</span><ul class="space-y-3 font-medium text-gray-600 text-sm"><li>일어</li><li>확통</li><li>독서</li><li>영어2</li><li>수학2</li></ul></div>
                </div>
            </section>
        </main>

        <footer class="py-20 text-center text-[#86868b] text-sm font-medium">
            <p>© 2-9 Class. Dedicated to your success.</p>
        </footer>
    </div>

    <script>
        function checkLogin() {
            const num = document.getElementById('login-number').value;
            const name = document.getElementById('login-name').value;
            if(num.startsWith("209") && name.length >= 2) {
                document.getElementById('login-section').classList.add('hidden');
                document.getElementById('main-content').classList.add('block');
                startDDay();
            } else {
                document.getElementById('login-error').classList.remove('hidden');
            }
        }
        function startDDay() {
            const targetDate = new Date("2027-11-19T00:00:00");
            const today = new Date();
            const diff = targetDate - today;
            const days = Math.ceil(diff / (1000 * 60 * 60 * 24));
            document.getElementById('dday-display').innerText = days > 0 ? `D-${days}` : "START";
        }
    </script>
</body>
</html>
