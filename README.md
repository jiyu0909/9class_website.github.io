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
            padding: 0;
            background-color: #000; /* 기본 배경 검정 */
            color: #1d1d1f;
            -webkit-font-smoothing: antialiased;
            overflow-x: hidden;
        }

        /* [움직이는 오로라 배경] */
        .aurora-bg {
            position: fixed;
            top: 0; left: 0; right: 0; bottom: 0;
            z-index: -1;
            background: linear-gradient(125deg, #f5f5f7 0%, #e8e8ed 40%, #d2d2d7 100%);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
        }
        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .glass-panel {
            background: rgba(255, 255, 255, 0.55);
            backdrop-filter: blur(25px);
            -webkit-backdrop-filter: blur(25px);
            border: 1px solid rgba(255, 255, 255, 0.4);
            border-radius: 32px;
        }

        /* 시간표 가로 스크롤 고정 */
        .timetable-container {
            display: flex;
            gap: 12px;
            overflow-x: auto;
            padding-bottom: 15px;
            scrollbar-width: none;
        }
        .timetable-container::-webkit-scrollbar { display: none; }
        .day-box {
            flex: 0 0 145px;
            background: rgba(255, 255, 255, 0.4);
            padding: 20px;
            border-radius: 20px;
            text-align: center;
        }

        /* 애니메이션 효과 */
        .fade-in { animation: fadeIn 0.8s cubic-bezier(0.2, 0.8, 0.2, 1) forwards; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

        #main-content { display: none; } /* 초기에는 숨김 */
    </style>
</head>
<body>
    <div class="aurora-bg"></div>

    <div id="login-section" class="min-h-screen flex items-center justify-center p-6">
        <div class="w-full max-w-[420px] glass-panel p-12 text-center shadow-2xl fade-in">
            <h1 class="text-7xl font-bold text-[#86868b] tracking-tighter mb-4 italic opacity-80">Login</h1>
            <div class="space-y-2 mb-10">
                <p class="text-sm font-bold text-gray-500 tracking-[0.2em] uppercase">2-9 Information</p>
                <p class="text-xs text-blue-600 font-semibold italic">학번은 209**으로 입력해주세요</p>
                <p class="text-[10px] text-gray-400">※ 최은지 선생님은 20900 입력</p>
            </div>

            <div class="space-y-4">
                <input id="login-number" type="text" placeholder="Student ID" 
                    class="w-full h-14 px-6 rounded-2xl bg-white/80 border border-gray-200 outline-none focus:border-blue-500 transition-all text-lg text-center shadow-inner">
                <input id="login-name" type="text" placeholder="Name" 
                    class="w-full h-14 px-6 rounded-2xl bg-white/80 border border-gray-200 outline-none focus:border-blue-500 transition-all text-lg text-center shadow-inner">
                <button onclick="checkLogin()" 
                    class="w-full h-14 bg-[#1d1d1f] text-white rounded-2xl font-bold text-lg hover:bg-black transition-all mt-6 shadow-xl">
                    Enter Class
                </button>
            </div>
            <p id="login-error" class="text-red-500 text-sm font-medium mt-6 hidden">정보를 다시 확인해주세요! 😊</p>
        </div>
    </div>

    <div id="main-content" class="fade-in">
        <nav class="sticky top-0 z-50 bg-white/60 backdrop-blur-xl border-b border-black/5">
            <div class="max-w-[980px] mx-auto px-6 h-[52px] flex items-center justify-between">
                <span class="font-black text-xl tracking-tight">2-9</span>
                <span class="text-xs font-bold text-blue-600 uppercase tracking-widest">Suneung Countdown</span>
            </div>
        </nav>

        <main class="max-w-[980px] mx-auto px-6 py-12 space-y-10">
            <section class="text-center py-10">
                <p class="text-gray-500 text-sm font-bold tracking-[0.4em] uppercase mb-4">Target: 2027. 11. 19</p>
                <div id="dday-display" class="text-[100px] md:text-[160px] font-black tracking-tighter leading-none mb-6">D-???</div>
                <p class="text-2xl font-medium text-gray-400 italic">"Prove them wrong."</p>
            </section>

            <section class="glass-panel p-10 md:p-16 border-l-[10px] border-blue-500 shadow-lg">
                <span class="text-blue-600 font-bold text-sm tracking-widest mb-6 block uppercase">From. Teacher Choi</span>
                <h2 class="text-3xl md:text-5xl font-black leading-[1.2] mb-10 tracking-tight text-[#1d1d1f]">
                    "기말고사 고생 많았어! <br>지치지 말고 끝까지 함께 가보자. <br>너희는 생각보다 훨씬 더 단단하니까."
                </h2>
                <div class="flex items-center gap-4">
                    <div class="w-14 h-14 rounded-full bg-blue-600 flex items-center justify-center text-white font-black text-2xl">최</div>
                    <div>
                        <p class="text-xl font-bold">최은지 선생님</p>
                        <p class="text-gray-500 text-sm">2학년 9반 담임선생님</p>
                    </div>
                </div>
            </section>

            <section class="glass-panel p-10 shadow-lg">
                <h3 class="text-3xl font-bold mb-10 tracking-tight">오늘의 식단 <span class="text-blue-500 text-sm font-normal ml-3">12월 1일 월요일</span></h3>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-12">
                    <div class="space-y-4">
                        <p class="text-xs font-black text-blue-500 tracking-widest uppercase">Lunch</p>
                        <p class="text-2xl font-bold leading-relaxed">오색현미밥, 소고기배추된장국, <span class="text-blue-600">숯불닭갈비보쌈</span>, 노란호박전, 샤인머스켓 ✨</p>
                    </div>
                    <div class="space-y-4">
                        <p class="text-xs font-black text-orange-500 tracking-widest uppercase">Dinner</p>
                        <p class="text-2xl font-bold leading-relaxed">청차조밥, <span class="text-orange-600">병천식순대국</span>, 돈사태메추리알조림, 오징어야채초무침, 감귤 🍊</p>
                    </div>
                </div>
            </section>

            <section class="glass-panel p-10 shadow-lg">
                <h3 class="text-2xl font-bold mb-8 tracking-tight">주간 시간표</h3>
                <div class="timetable-container">
                    <div class="day-box"><span class="block font-black text-blue-600 mb-4 border-b pb-2 border-blue-100">월</span><ul class="space-y-3 font-medium text-gray-600 text-sm"><li>독서</li><li>영어2</li><li>수학2</li><li>일어</li><li>체육</li></ul></div>
                    <div class="day-box"><span class="block font-black text-blue-600 mb-4 border-b pb-2 border-blue-100">화</span><ul class="space-y-3 font-medium text-gray-600 text-sm"><li>확통</li><li>수학2</li><li>영어2</li><li>독서</li><li>진로</li></ul></div>
                    <div class="day-box"><span class="block font-black text-blue-600 mb-4 border-b pb-2 border-blue-100">수</span><ul class="space-y-3 font-medium text-gray-600 text-sm"><li>수학2</li><li>독서</li><li>영어2</li><li>체육</li><li>일어</li></ul></div>
                    <div class="day-box"><span class="block font-black text-blue-600 mb-4 border-b pb-2 border-blue-100">목</span><ul class="space-y-3 font-medium text-gray-600 text-sm"><li>영독</li><li>수학2</li><li>음악</li><li>독서</li><li>영어2</li></ul></div>
                    <div class="day-box"><span class="block font-black text-blue-600 mb-4 border-b pb-2 border-blue-100">금</span><ul class="space-y-3 font-medium text-gray-600 text-sm"><li>일어</li><li>확통</li><li>독서</li><li>영어2</li><li>수학2</li></ul></div>
                </div>
            </section>
        </main>

        <footer class="py-20 text-center text-gray-400 text-xs font-bold tracking-widest uppercase">
            <p>© 2-9 Class Center. Stay dedicated.</p>
        </footer>
    </div>

    <script>
        function checkLogin() {
            const num = document.getElementById('login-number').value.trim();
            const name = document.getElementById('login-name').value.trim();

            // 입장 조건: 209로 시작하거나 20900(선생님)일 때
            if((num.startsWith("209") || num === "20900") && name.length >= 2) {
                // 1. 로그인 섹션 숨기기
                document.getElementById('login-section').style.display = 'none';
                
                // 2. 메인 컨텐츠 보여주기 (display를 block으로 확실히 지정)
                const mainContent = document.getElementById('main-content');
                mainContent.style.display = 'block';
                
                // 3. 디데이 계산기 시작
                startDDay();
                
                // 4. 스크롤을 맨 위로 이동
                window.scrollTo(0, 0);
            } else {
                const errorMsg = document.getElementById('login-error');
                errorMsg.classList.remove('hidden');
            }
        }

        function startDDay() {
            const targetDate = new Date("2027-11-19T00:00:00");
            const today = new Date();
            const diff = targetDate - today;
            const days = Math.ceil(diff / (1000 * 60 * 60 * 24));
            
            const display = document.getElementById('dday-display');
            display.innerText = days > 0 ? `D-${days}` : (days === 0 ? "D-DAY" : "PASS");
        }

        // 엔터키 지원
        document.addEventListener('keypress', (e) => {
            if(e.key === 'Enter') checkLogin();
        });
    </script>
</body>
</html>
