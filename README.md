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
            background: #fff5f7;
            overflow-x: hidden;
            -webkit-font-smoothing: antialiased;
        }

        /* 연핑크 오로라 배경 */
        .aurora-container {
            position: fixed;
            top: 0; left: 0; right: 0; bottom: 0;
            z-index: -1;
            background-image: 
                radial-gradient(at 0% 0%, rgba(255, 182, 193, 0.25) 0px, transparent 50%),
                radial-gradient(at 100% 0%, rgba(255, 224, 230, 0.35) 0px, transparent 50%),
                radial-gradient(at 100% 100%, rgba(255, 192, 203, 0.15) 0px, transparent 50%),
                radial-gradient(at 0% 100%, rgba(240, 240, 245, 0.4) 0px, transparent 50%);
            animation: auroraMove 15s ease infinite alternate;
        }

        @keyframes auroraMove {
            0% { transform: scale(1); }
            100% { transform: scale(1.05); }
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.75);
            backdrop-filter: blur(30px) saturate(160%);
            -webkit-backdrop-filter: blur(30px) saturate(160%);
            border: 1px solid rgba(255, 255, 255, 0.5);
            box-shadow: 0 10px 40px rgba(255, 182, 193, 0.12);
            border-radius: 32px;
        }

        #main-content { display: none; }
        
        .fade-in {
            animation: fadeIn 0.8s cubic-bezier(0.2, 0.8, 0.2, 1) forwards;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .timetable-wrapper {
            display: flex; gap: 14px; overflow-x: auto; padding: 5px;
            scrollbar-width: none;
        }
        .timetable-wrapper::-webkit-scrollbar { display: none; }
        .day-unit {
            flex: 0 0 145px;
            background: rgba(255, 255, 255, 0.4);
            border-radius: 20px; padding: 18px;
            border: 1px solid rgba(255, 192, 203, 0.15);
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="aurora-container"></div>

    <div id="login-section" class="min-h-screen flex items-center justify-center p-6 text-[#1d1d1f]">
        <div class="w-full max-w-[420px] glass-card p-12 text-center fade-in">
            <h1 class="text-7xl font-black mb-4 tracking-tighter italic opacity-90 text-[#ff8fa3]">Login</h1>
            <div class="mb-10 space-y-2">
                <p class="text-xs font-bold tracking-[0.3em] text-gray-400 uppercase">2-9 Information Center</p>
                <div class="bg-white/50 py-1.5 px-3 rounded-full inline-block mt-2">
                    <p class="text-[11px] text-[#ff8fa3] font-bold underline decoration-pink-200 underline-offset-2">학번 209** 입력 (최은지 선생님: 20900)</p>
                </div>
            </div>

            <div class="space-y-4">
                <input id="login-number" type="text" placeholder="Student ID" 
                    class="w-full h-15 px-6 py-4 rounded-2xl bg-white/80 border border-pink-50 focus:bg-white focus:border-[#ff8fa3] outline-none transition-all text-center text-lg shadow-sm">
                <input id="login-name" type="text" placeholder="Name" 
                    class="w-full h-15 px-6 py-4 rounded-2xl bg-white/80 border border-pink-50 focus:bg-white focus:border-[#ff8fa3] outline-none transition-all text-center text-lg shadow-sm">
                <button onclick="checkLogin()" 
                    class="w-full h-15 bg-[#ff8fa3] text-white rounded-2xl font-black text-xl hover:bg-[#ff7a91] transition-all mt-6 shadow-lg shadow-pink-100">
                    계속하기
                </button>
            </div>
            <p id="login-error" class="text-red-400 text-sm font-bold mt-6 hidden">정보를 다시 확인해 주세요.</p>
        </div>
    </div>

    <div id="main-content" class="fade-in">
        <nav class="sticky top-0 z-50 bg-white/60 backdrop-blur-xl border-b border-pink-50">
            <div class="max-w-[1000px] mx-auto px-6 h-[56px] flex items-center justify-between">
                <span class="font-black text-2xl tracking-tighter text-[#ff8fa3]">2-9</span>
                <span class="text-[10px] font-black bg-[#ff8fa3] text-white px-4 py-1.5 rounded-full uppercase tracking-widest">수능 Countdown</span>
            </div>
        </nav>

        <main class="max-w-[1000px] mx-auto px-6 py-12 space-y-12">
            <section class="text-center py-8">
                <p class="text-pink-300 text-sm font-black tracking-[0.5em] uppercase mb-4">Target: 2027. 11. 19</p>
                <div id="dday-display" class="text-[110px] md:text-[170px] font-black tracking-tighter leading-none text-[#1d1d1f]">D-???</div>
                <p class="text-2xl font-bold text-gray-400 italic mt-4">"Trust the process."</p>
            </section>

            <section class="glass-card p-10 md:p-14 border-l-[12px] border-[#ff8fa3]">
                <span class="text-[#ff8fa3] font-black text-sm tracking-widest mb-6 block uppercase">Notice from Teacher Choi</span>
                <h2 class="text-2xl md:text-3xl font-bold leading-relaxed mb-10 tracking-tight text-[#1d1d1f]">
                    "지각, 교복 제대로 안 입으면 <span class="text-red-500 underline decoration-2 underline-offset-4 font-black">학년에서 강력하게 지도</span>한다고 함. <br>잘 챙겨 입고 늦지 않게 등교하자~"
                </h2>
                <div class="flex items-center gap-4">
                    <div class="w-14 h-14 rounded-2xl bg-[#ff8fa3] flex items-center justify-center text-white font-black text-2xl shadow-md">최</div>
                    <div>
                        <p class="text-xl font-black">최은지 선생님</p>
                        <p class="text-gray-400 font-bold text-sm">2학년 9반 담임선생님</p>
                    </div>
                </div>
            </section>

            <section class="glass-card p-10 md:p-12">
                <div class="flex items-end justify-between mb-12 border-b border-pink-50 pb-6">
                    <h3 class="text-4xl font-black tracking-tighter">오늘의 식단</h3>
                    <p class="text-[#ff8fa3] font-black text-lg">12월 19일 금요일</p>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-16">
                    <div class="space-y-6">
                        <p class="text-xs font-black text-gray-400 tracking-[0.3em] uppercase bg-pink-50 px-3 py-1 rounded-md inline-block">Lunch</p>
                        <ul class="text-xl font-bold leading-relaxed space-y-3 text-[#1d1d1f]">
                            <li>혼합잡곡밥</li>
                            <li>한우들깨미역국</li>
                            <li>돈안심떡장조림</li>
                            <li>참나물무생채</li>
                            <li class="text-[#ff8fa3] text-2xl">살살녹는 슈프림치킨</li>
                            <li class="bg-[#ff8fa3]/10 px-3 py-2 rounded-xl text-[#ff8fa3] font-black border border-[#ff8fa3]/20">뿌링클크림치즈볼 (학생희망메뉴)</li>
                            <li class="text-gray-400">멜론</li>
                        </ul>
                    </div>
                    <div class="space-y-6">
                        <p class="text-xs font-black text-gray-400 tracking-[0.3em] uppercase bg-gray-50 px-3 py-1 rounded-md inline-block">Dinner</p>
                        <ul class="text-xl font-bold leading-relaxed space-y-3 text-[#1d1d1f]">
                            <li>강황쌀밥</li>
                            <li>얼큰동태찌개</li>
                            <li>매콤갑오징어볶음</li>
                            <li class="text-orange-500 font-black">언양식불고기전 & 상추파채무침</li>
                            <li>배추김치</li>
                            <li class="text-blue-500">요구르트(런)</li>
                        </ul>
                    </div>
                </div>
            </section>

            <section class="glass-card p-10">
                <h3 class="text-2xl font-black tracking-tighter mb-8 text-center text-gray-300 uppercase">Weekly Timetable</h3>
                <div class="timetable-wrapper">
                    <div class="day-unit"><span class="block font-black text-[#ff8fa3] mb-4 border-b border-pink-50 pb-2 text-lg">월</span><ul class="space-y-3 font-bold text-gray-600 text-sm"><li>독서</li><li>영어2</li><li>수학2</li><li>일본어</li><li>체육</li></ul></div>
                    <div class="day-unit"><span class="block font-black text-[#ff8fa3] mb-4 border-b border-pink-50 pb-2 text-lg">화</span><ul class="space-y-3 font-bold text-gray-600 text-sm"><li>확통</li><li>수학2</li><li>영어2</li><li>독서</li><li>진로</li></ul></div>
                    <div class="day-unit"><span class="block font-black text-[#ff8fa3] mb-4 border-b border-pink-50 pb-2 text-lg">수</span><ul class="space-y-3 font-bold text-gray-600 text-sm"><li>수학2</li><li>독서</li><li>영어2</li><li>체육</li><li>일본어</li></ul></div>
                    <div class="day-unit"><span class="block font-black text-[#ff8fa3] mb-4 border-b border-pink-50 pb-2 text-lg">목</span><ul class="space-y-3 font-bold text-gray-600 text-sm"><li>영어2</li><li>수학2</li><li>음악</li><li>독서</li><li>영어2</li></ul></div>
                    <div class="day-unit"><span class="block font-black text-[#ff8fa3] mb-4 border-b border-pink-50 pb-2 text-lg">금</span><ul class="space-y-3 font-bold text-gray-600 text-sm"><li>일어</li><li>확통</li><li>독서</li><li>영어2</li><li>수학2</li></ul></div>
                </div>
            </section>
        </main>

        <footer class="py-24 text-center">
            <p class="text-[10px] font-black text-pink-200 tracking-[0.5em] uppercase">© 2-9 Class • Stay Focused</p>
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
            const target = new Date("2027-11-19T00:00:00");
            const now = new Date();
            const diff = target - now;
            const days = Math.ceil(diff / (1000 * 60 * 60 * 24));
            document.getElementById('dday-display').innerText = days > 0 ? `D-${days}` : "PASS";
        }
        document.addEventListener('keypress', (e) => { if(e.key === 'Enter') checkLogin(); });
    </script>
</body>
</html>
