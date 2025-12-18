<!doctype html>
<html lang="ko">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2-9 | Info Center</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" as="style" crossorigin href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.css" />
    <style>
        body {
            font-family: "Pretendard Variable", -apple-system, sans-serif;
            background: #ffffff;
            color: #1d1d1f;
            -webkit-font-smoothing: antialiased;
            word-break: keep-all;
        }

        .bg-pure {
            position: fixed;
            top: 0; left: 0; right: 0; bottom: 0;
            z-index: -1;
            background: #ffffff;
        }

        .glass-card {
            background: #ffffff;
            border: 1px solid #f2f2f7;
            border-radius: 24px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.01);
        }

        #main-content { display: none; }
        .fade-in { animation: fadeIn 0.4s ease-out forwards; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

        .timetable-scroll {
            display: flex; gap: 12px; overflow-x: auto; padding-bottom: 10px;
            scrollbar-width: none;
        }
        .timetable-scroll::-webkit-scrollbar { display: none; }
        .day-item {
            flex: 0 0 140px; background: #fbfbfd; border-radius: 18px; padding: 20px; text-align: center;
        }
    </style>
</head>
<body>
    <div class="bg-pure"></div>

    <div id="login-section" class="min-h-screen flex items-center justify-center p-6">
        <div class="w-full max-w-[380px] text-center fade-in">
            <h1 class="text-7xl font-bold text-[#f2f2f7] tracking-tighter mb-8 italic">Login</h1>
            <div class="space-y-1 mb-8">
                <p class="text-sm font-bold text-[#86868b]">학번 209**으로 입장</p>
                <p class="text-[11px] text-[#aeaeb2]">(선생님은 20900)</p>
            </div>
            
            <div class="space-y-3">
                <input id="login-number" type="text" placeholder="학번" class="w-full h-14 px-5 rounded-2xl bg-[#f5f5f7] border-none focus:ring-1 focus:ring-gray-300 outline-none text-center text-lg">
                <input id="login-name" type="text" placeholder="이름" class="w-full h-14 px-5 rounded-2xl bg-[#f5f5f7] border-none focus:ring-1 focus:ring-gray-300 outline-none text-center text-lg">
                <button onclick="checkLogin()" class="w-full h-14 bg-[#1d1d1f] text-white rounded-2xl font-bold text-lg mt-4 hover:bg-black transition-all">입장하기</button>
            </div>
            <p id="login-error" class="text-red-500 text-sm mt-4 hidden">다시 확인해 주세요.</p>
        </div>
    </div>

    <div id="main-content">
        <nav class="sticky top-0 z-50 bg-white/95 backdrop-blur-md border-b border-gray-100">
            <div class="max-w-[900px] mx-auto px-6 h-[52px] flex items-center justify-between font-bold">
                <span class="text-xl tracking-tight">2-9</span>
                <span class="text-[10px] tracking-widest uppercase text-gray-400">수능 Countdown</span>
            </div>
        </nav>

        <main class="max-w-[900px] mx-auto px-6 py-12 space-y-10">
            <section class="text-center py-12 fade-in">
                <p class="text-[#86868b] text-xs font-black tracking-[0.4em] mb-4 uppercase text-blue-600">November 19, 2026</p>
                <div id="dday-display" class="text-[100px] md:text-[150px] font-bold tracking-tighter leading-none">D-???</div>
                <p class="text-xl font-medium text-gray-300 mt-4">2학년 9반의 시간</p>
            </section>

            <section class="glass-card p-10 border-l-[10px] border-black fade-in">
                <p class="text-[10px] font-black text-gray-400 tracking-widest mb-4 uppercase italic">Notice</p>
                <h2 class="text-2xl md:text-3xl font-bold leading-snug mb-8">
                    "지각, 교복 제대로 안 입으면 학년에서 강력하게 지도한다고 함. 잘 챙겨 입고 늦지 않게 등교하자~"
                </h2>
                <div class="flex items-center gap-4 pt-6 border-t border-gray-50">
                    <div class="w-10 h-10 rounded-full bg-black flex items-center justify-center text-white font-bold text-xs">최</div>
                    <div>
                        <p class="font-bold text-sm text-black">최은지 선생님</p>
                        <p class="text-[11px] text-[#86868b]">2학년 9반 담임선생님</p>
                    </div>
                </div>
            </section>

            <section class="glass-card p-10 fade-in">
                <div class="flex items-baseline justify-between mb-12">
                    <h3 class="text-3xl font-bold tracking-tight text-black">오늘의 식단</h3>
                    <span class="text-gray-400 font-bold text-xs uppercase tracking-widest">12월 19일 금요일</span>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-16">
                    <div class="space-y-8">
                        <p class="text-[10px] font-black text-gray-300 tracking-[0.3em] uppercase border-b-2 border-gray-50 pb-2">Lunch</p>
                        <ul class="text-[17px] font-semibold leading-relaxed space-y-3 text-gray-600">
                            <li>혼합잡곡밥</li>
                            <li>한우들깨미역국</li>
                            <li>돈안심떡장조림</li>
                            <li>참나물무생채</li>
                            <li class="text-black font-bold text-2xl tracking-tight">살살녹는 슈프림치킨</li>
                            <li class="text-black font-bold text-xl tracking-tight">뿌링클크림치즈볼</li>
                            <li>멜론</li>
                            <li>배추김치</li>
                        </ul>
                    </div>
                    <div class="space-y-8">
                        <p class="text-[10px] font-black text-gray-300 tracking-[0.3em] uppercase border-b-2 border-gray-50 pb-2">Dinner</p>
                        <ul class="text-[17px] font-semibold leading-relaxed space-y-3 text-gray-600">
                            <li>강황쌀밥</li>
                            <li>얼큰동태찌개</li>
                            <li>매콤갑오징어볶음</li>
                            <li class="text-black font-bold text-2xl tracking-tight">언양식불고기전 & 상추파채무침</li>
                            <li>배추김치</li>
                            <li>요구르트(런)</li>
                        </ul>
                    </div>
                </div>
            </section>

            <section class="glass-card p-8 fade-in">
                <h3 class="text-[10px] font-black mb-8 text-center text-gray-300 tracking-[0.4em] uppercase">Weekly Timetable</h3>
                <div class="timetable-scroll">
                    <div class="day-item"><span class="block font-bold text-black mb-4 border-b pb-2">월</span><ul class="text-sm space-y-2 text-gray-400"><li>독서</li><li>영어2</li><li>수학2</li><li>일어</li><li>체육</li></ul></div>
                    <div class="day-item"><span class="block font-bold text-black mb-4 border-b pb-2">화</span><ul class="text-sm space-y-2 text-gray-400"><li>확통</li><li>수학2</li><li>영어2</li><li>독서</li><li>진로</li></ul></div>
                    <div class="day-item"><span class="block font-bold text-black mb-4 border-b pb-2">수</span><ul class="text-sm space-y-2 text-gray-400"><li>수학2</li><li>독서</li><li>영어2</li><li>체육</li><li>일어</li></ul></div>
                    <div class="day-item"><span class="block font-bold text-black mb-4 border-b pb-2">목</span><ul class="text-sm space-y-2 text-gray-400"><li>영독</li><li>수학2</li><li>음악</li><li>독서</li><li>영어2</li></ul></div>
                    <div class="day-item"><span class="block font-bold text-black mb-4 border-b pb-2">금</span><ul class="text-sm space-y-2 text-gray-400"><li>일어</li><li>확통</li><li>독서</li><li>영어2</li><li>수학2</li></ul></div>
                </div>
            </section>
        </main>

        <footer class="py-24 text-center text-gray-200 text-[9px] font-bold tracking-[0.6em] uppercase">
            © 2-9 Class • Stay Focused
        </footer>
    </div>

    <script>
        function checkLogin() {
            const num = document.getElementById('login-number').value.trim();
            const name = document.getElementById('login-name').value.trim();
            if((num.startsWith("209") || num === "20900") && name.length >= 2) {
                document.getElementById('login-section').style.display = 'none';
                document.getElementById('main-content').style.display = 'block';
                startDDay();
                window.scrollTo(0, 0);
            } else {
                document.getElementById('login-error').classList.remove('hidden');
            }
        }
        function startDDay() {
            const target = new Date("2026-11-19T00:00:00");
            const diff = target - new Date();
            const days = Math.ceil(diff / (1000 * 60 * 60 * 24));
            document.getElementById('dday-display').innerText = days > 0 ? `D-${days}` : "PASS";
        }
        document.addEventListener('keypress', (e) => { if(e.key === 'Enter') checkLogin(); });
    </script>
</body>
</html>
