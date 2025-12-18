<!doctype html>
<html lang="ko">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2-9반 전용 알리미</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @font-face {
            font-family: 'Gonici';
            src: url('https://cdn.jsdelivr.net/gh/projectnoonnu/noonfonts_2108@1.1/Gonici.woff2') format('woff2');
        }
        body {
            font-family: 'Gonici', sans-serif;
            background: linear-gradient(-45deg, #fbcfe8, #ecc8d4, #fecaca, #fae8ff);
            background-size: 400% 400%;
            animation: gradient 15s ease infinite;
        }
        @keyframes gradient {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        .glass {
            background: rgba(255, 255, 255, 0.75);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.4);
        }
        #main-content { display: none; }
        
        /* 시간표 가로 고정 스타일 */
        .timetable-wrapper {
            display: grid;
            grid-template-columns: repeat(5, minmax(120px, 1fr));
            gap: 10px;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col items-center justify-center p-4">

    <div id="login-section" class="w-full max-w-md glass p-10 rounded-[3rem] shadow-2xl text-center space-y-6">
        <h1 class="text-4xl font-black text-pink-600 tracking-tight">🔐 2-9 ONLY</h1>
        <p class="text-pink-800/70 font-bold">학번과 이름을 입력하세요</p>
        <div class="space-y-4">
            <input id="login-number" type="text" placeholder="학번 (예: 20901)" 
                class="w-full px-6 py-4 rounded-2xl border-none focus:ring-4 focus:ring-pink-300 outline-none shadow-inner text-center text-lg">
            <input id="login-name" type="text" placeholder="이름" 
                class="w-full px-6 py-4 rounded-2xl border-none focus:ring-4 focus:ring-pink-300 outline-none shadow-inner text-center text-lg">
            <button onclick="checkLogin()" 
                class="w-full bg-pink-500 text-white font-black py-4 rounded-2xl hover:bg-pink-600 transition-all shadow-lg text-xl">
                입장하기
            </button>
        </div>
        <p id="login-error" class="text-red-500 font-bold hidden">우리반 맞아요? 다시 확인해봐! 🧐</p>
    </div>

    <div id="main-content" class="w-full max-w-5xl space-y-6 py-6">
        
        <header class="glass rounded-[2rem] p-8 shadow-xl text-center border-b-8 border-red-400">
            <p class="text-red-500 font-bold mb-1">2026학년도 대학수학능력시험</p>
            <h1 id="dday-display" class="text-6xl font-black text-red-600 tracking-tighter italic">
                D-???
            </h1>
            <p class="text-pink-700/60 mt-2 font-medium">기말 끝! 이제 진짜 시작이다 우리반 🔥</p>
        </header>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
            <section class="md:col-span-1 glass p-6 rounded-[2rem] shadow-lg">
                <h2 class="text-2xl font-black text-pink-700 mb-4 flex items-center gap-2">
                    🍴 오늘의 급식
                </h2>
                <div class="bg-white/50 p-5 rounded-2xl border border-pink-200">
                    <ul class="space-y-2 text-pink-900 font-medium">
                        <li>🍚 흑미밥</li>
                        <li>🥘 부대찌개</li>
                        <li>🍖 제육볶음</li>
                        <li>🥗 겉절이</li>
                        <li>🥛 요구르트</li>
                    </ul>
                </div>
                <p class="text-xs text-pink-500/70 mt-4 text-center">※ 학교 사정에 따라 변경될 수 있음</p>
            </section>

            <section class="md:col-span-2 glass p-6 rounded-[2rem] shadow-lg overflow-hidden">
                <h2 class="text-2xl font-black text-pink-700 mb-4 flex items-center gap-2">
                    📅 주간 시간표
                </h2>
                <div class="overflow-x-auto pb-2">
                    <div class="timetable-wrapper">
                        <div class="bg-white/40 rounded-2xl p-3 text-center border border-pink-100">
                            <div class="font-black text-pink-600 mb-2 pb-1 border-b border-pink-200">월</div>
                            <div class="space-y-2 text-sm">
                                <p>독서</p><p>영어2</p><p>수학2</p><p>일본어</p><p>체육</p><p>창체</p><p>창체</p>
                            </div>
                        </div>
                        <div class="bg-white/40 rounded-2xl p-3 text-center border border-pink-100">
                            <div class="font-black text-pink-600 mb-2 pb-1 border-b border-pink-200">화</div>
                            <div class="space-y-2 text-sm">
                                <p>확통</p><p>수학2</p><p>영어2</p><p>독서</p><p>진로</p><p>영독</p><p>음악</p>
                            </div>
                        </div>
                        <div class="bg-white/40 rounded-2xl p-3 text-center border border-pink-100">
                            <div class="font-black text-pink-600 mb-2 pb-1 border-b border-pink-200">수</div>
                            <div class="space-y-2 text-sm">
                                <p>수학2</p><p>독서</p><p>영어2</p><p>체육</p><p>일본어</p><p>-</p><p>-</p>
                            </div>
                        </div>
                        <div class="bg-white/40 rounded-2xl p-3 text-center border border-pink-100">
                            <div class="font-black text-pink-600 mb-2 pb-1 border-b border-pink-200">목</div>
                            <div class="space-y-2 text-sm">
                                <p>영독</p><p>수학2</p><p>음악</p><p>독서</p><p>영어2</p><p>확통</p><p>자율</p>
                            </div>
                        </div>
                        <div class="bg-white/40 rounded-2xl p-3 text-center border border-pink-100">
                            <div class="font-black text-pink-600 mb-2 pb-1 border-b border-pink-200">금</div>
                            <div class="space-y-2 text-sm">
                                <p>일본어</p><p>확통</p><p>독서</p><p>영어2</p><p>영독</p><p>수학2</p><p>청소</p>
                            </div>
                        </div>
                    </div>
                </div>
            </section>
        </div>
    </div>

    <script>
        function checkLogin() {
            const num = document.getElementById('login-number').value;
            const name = document.getElementById('login-name').value;

            // 209로 시작하는 학번이면 통과
            if(num.startsWith("209") && name.length >= 2) {
                document.getElementById('login-section').classList.add('hidden');
                document.getElementById('main-content').style.display = 'block';
                document.body.classList.remove('items-center', 'justify-center');
                startDDay();
            } else {
                const errorMsg = document.getElementById('login-error');
                errorMsg.classList.remove('hidden');
            }
        }

        function startDDay() {
            // 2026학년도 수능일 (2025년 11월 13일 목요일)
            const targetDate = new Date("2025-11-13T00:00:00");
            const today = new Date();
            const diff = targetDate - today;
            const days = Math.ceil(diff / (1000 * 60 * 60 * 24));
            
            const display = document.getElementById('dday-display');
            if (days > 0) {
                display.innerText = `D-${days}`;
            } else if (days === 0) {
                display.innerText = `D-DAY`;
            } else {
                display.innerText = `수능 종료!`;
            }
        }

        document.addEventListener('keypress', (e) => {
            if(e.key === 'Enter') checkLogin();
        });
    </script>
</body>
</html>
