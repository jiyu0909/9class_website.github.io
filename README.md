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
            margin: 0;
            background-color: #ffffff;
            color: #1d1d1f;
            -webkit-font-smoothing: antialiased;
        }

        /* 유리 질감이 돋보이게 하는 은은한 배경 */
        .background-layer {
            position: fixed;
            top: 0; left: 0; right: 0; bottom: 0;
            z-index: -1;
            background: 
                radial-gradient(at 0% 0%, rgba(245, 245, 247, 1) 0px, transparent 50%),
                radial-gradient(at 100% 0%, rgba(226, 226, 234, 0.4) 0px, transparent 50%),
                radial-gradient(at 50% 100%, rgba(242, 242, 247, 0.8) 0px, transparent 50%);
        }

        /* [핵심] 유리 질감 수정 버전 */
        .glass-panel {
            background: rgba(255, 255, 255, 0.7) !important;
            backdrop-filter: blur(20px) saturate(180%) !important;
            -webkit-backdrop-filter: blur(20px) saturate(180%) !important; /* Safari 지원 */
            border: 1px solid rgba(255, 255, 255, 0.4);
            border-radius: 28px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.04);
        }

        #main-content { display: none; }
        
        /* 애니메이션 */
        .fade-in {
            animation: fadeIn 0.8s cubic-bezier(0.2, 0.8, 0.2, 1) forwards;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(15px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .timetable-scroll {
            display: flex; gap: 12px; overflow-x: auto; padding: 10px 0;
            scrollbar-width: none; -ms-overflow-style: none;
        }
        .timetable-scroll::-webkit-scrollbar { display: none; }
        .day-box {
            flex: 0 0 145px; background: rgba(255, 255, 255, 0.5); 
            border: 1px solid rgba(0,0,0,0.03); border-radius: 20px; padding: 20px; text-align: center;
        }
    </style>
</head>
<body>
    <div class="background-layer"></div>

    <div id="login-section" class="min-h-screen flex items-center justify-center p-6">
        <div class="w-full max-w-[400px] glass-panel p-12 text-center fade-in">
            <h1 class="text-7xl font-bold text-[#d2d2d7] tracking-tighter mb-8 italic">Login</h1>
            <div class="space-y-1 mb-10">
                <p class="text-sm font-bold text-[#86868b]">학번 209**으로 입장</p>
                <p class="text-[11px] text-[#aeaeb2]">(선생님 전용: 20900)</p>
            </div>
            <div class="space-y-4">
                <input id="login-number" type="text" placeholder="학번" class="w-full h-15 px-6 py-4 rounded-2xl bg-white/50 border border-gray-100 focus:bg-white focus:ring-2 focus:ring-gray-200 outline-none transition-all text-center">
                <input id="login-name" type="text" placeholder="이름" class="w-full h-15 px-6 py-4 rounded-2xl bg-white/50 border border-gray-100 focus:bg-white focus:ring-2 focus:ring-gray-200 outline-none transition-all text-center">
                <button onclick="checkLogin()" class="w-full h-15 bg-[#1d1d1f] text-white rounded-2xl font-bold text-lg mt-6 hover:bg-black transition-all shadow-lg">계속하기</button>
            </div>
            <p id="login-error" class="text-red-500 text-sm mt-6 hidden">다시 확인해 주세요.</p>
        </div>
    </div>

    <div id="main-content" class="fade-in">
        <nav class="sticky top-0 z-50 bg-white/70 backdrop-blur-xl border-b border-gray-100">
            <div class="max-w-[900px] mx-auto px-6 h-[56px] flex items-center justify-between">
                <span class="font-bold text-xl tracking-tight">2-9</span>
                <span class="text-[10px] font-bold tracking-widest text-gray-400 uppercase">수능 Countdown</span>
            </div>
        </nav>

        <main class="max-w-[900px] mx-auto px-6 py-12 space-y-10">
            <section class="text-center py-12">
                <p class="text-blue-600 text-xs font-black tracking-[0.4em] mb-4">NOVEMBER 19, 2026</p>
                <div id="dday-display" class="text-[100px] md:text-[150px] font-bold tracking-tighter leading-none">D-???</div>
            </section>

            <section class="glass-panel p-10 border-l-[12px] border-black">
                <p class="text-[10px] font-black text-gray-400 tracking-widest mb-4 uppercase">Notice</p>
                <h2 class="text-2xl md:text-3xl font-bold leading-relaxed mb-10">
                    "지각, 교복 제대로 안 입으면 학년에서 강력하게 지도한다고 함. 잘 챙겨 입고 늦지 않게 등교하자~"
                </h2>
                <div class="flex items-center gap-4 border-t border-black/5 pt-8">
                    <div class="w-12 h-12 rounded-full bg-black flex items-center justify-center text-white font-bold">최</div>
                    <div>
                        <p class="font-bold">최은지 선생님</p>
                        <p class="text-xs text-gray-400">2학년 9반 담임선생님</p>
                    </div>
                </div>
            </section>

            <section class="glass-panel p-10">
                <div class="flex items-baseline justify-between mb-12 border-b border-black/5 pb-6">
                    <h3 class="text-3xl font-bold tracking-tight">오늘의 식단</h3>
                    <span class="text-gray-400 font-bold text-xs uppercase tracking-widest">12월 19일 금요일</span>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-16">
                    <div class="space-y-6">
                        <p class="text-[10px] font-black text-gray-300 tracking-widest uppercase">Lunch</p>
                        <ul class="text-[18px] font-medium leading-relaxed space-y-3">
                            <li>혼합잡곡밥</li>
                            <li>한우들깨미역국</li>
                            <li>돈안심떡장조림</li>
                            <li>참나물무생채</li>
                            <li class="text-black font-bold text-2xl">살살녹는 슈프림치킨</li>
                            <li class="text-black font-bold text-xl">뿌링클크림치즈볼</li>
                            <li>멜론</li>
                            <li>배추김치</li>
                        </ul>
                    </div>
                    <div class="space-y-6">
                        <p class="text-[10px] font-black text-gray-300 tracking-widest uppercase">Dinner</p>
                        <ul class="text-[18px] font-medium leading-relaxed space-y-3">
                            <li>강황쌀밥</li>
                            <li>얼큰동태찌개</li>
                            <li>매콤갑오징어볶음</li>
                            <li class="text-black font-bold text-2xl">언양식불고기전 & 상추파채무침</li>
                            <li>배추김치</li>
                            <li>요구르트(런)</li>
                        </ul>
                    </div>
                </div>
            </section>

            <section class="glass-panel p-8">
                <h3 class="text-[10px] font-black mb-8 text-center text-gray-300 tracking-[0.4em] uppercase">Weekly Timetable</h3>
                <div class="timetable-scroll">
                    <div class="day-box"><span class="block font-bold text-black mb-4 border-b pb-2">월</span><ul class="text-sm space-y-2 text-gray-400"><li>독서</li><li>영어2</li><li>수학2</li><li>일어</li><li>체육</li></ul></div>
                    <div class="day-box"><span class="block font-bold text-black mb-4 border-b pb-2">화</span><ul class="text-sm space-y-2 text-gray-400"><li>확통</li><li>수학2</li><li>영어2</li><li>독서</li><li>진로</li></ul></div>
                    <div class="day-box"><span class="block font-bold text-black mb-4 border-b pb-2">수</span><ul class="text-sm space-y-2 text-gray-400"><li>수학2</li><li>독서</li><li>영어2</li><li>체육</li><li>일어</li></ul></div>
                    <div class="day-box"><span class="block font-bold text-black mb-4 border-b pb-2">목</span><ul class="text-sm space-y-2 text-gray-400"><li>영독</li><li>수학2</li><li>음악</li><li>독서</li><li>영어2</li></ul></div>
                    <div class="day-box"><span class="block font-bold text-black mb-4 border-b pb-2">금</span><ul class="text-sm space-y-2 text-gray-400"><li>일어</li><li>확통</li><li>독서</li><li>영어2</li><li>수학2</li></ul></div>
                </div>
            </section>
        </main>

        <footer class="py-24 text-center text-gray-300 text-[9px] font-bold tracking-[0.6em] uppercase">
            © 2-9 Class Center
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
