<!doctype html>
<html lang="ko">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2-9 | Login</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" as="style" crossorigin href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.css" />
    <style>
        body {
            font-family: "Pretendard Variable", -apple-system, sans-serif;
            /* 애플 스타일 오로라 그라데이션 배경 */
            background: linear-gradient(135deg, #f5f5f7 0%, #e2e2e7 50%, #d2d2d7 100%);
            background-attachment: fixed;
            color: #1d1d1f;
            -webkit-font-smoothing: antialiased;
        }

        /* 유리 질감 효과 */
        .glass-panel {
            background: rgba(255, 255, 255, 0.6);
            backdrop-filter: blur(30px);
            -webkit-backdrop-filter: blur(30px);
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 32px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.06);
        }

        .apple-input {
            background: rgba(255, 255, 255, 0.8);
            border: 1px solid #d2d2d7;
            transition: all 0.3s ease;
        }

        .apple-input:focus {
            border-color: #0071e3;
            box-shadow: 0 0 0 4px rgba(0, 113, 227, 0.1);
        }

        #main-content { display: none; }
        .fade-in { animation: fadeIn 0.8s cubic-bezier(0.2, 0.8, 0.2, 1); }
        @keyframes fadeIn { from { opacity: 0; transform: scale(0.98); } to { opacity: 1; transform: scale(1); } }
    </style>
</head>
<body class="min-h-screen flex flex-col">

    <div id="login-section" class="flex-grow flex items-center justify-center p-6">
        <div class="w-full max-w-[420px] glass-panel p-12 text-center fade-in">
            <h1 class="text-6xl font-bold text-[#86868b] tracking-tighter mb-2 italic">Login</h1>
            <div class="space-y-1 mb-10">
                <p class="text-sm font-semibold text-[#1d1d1f]/60 uppercase tracking-widest">2-9 Information System</p>
                <p class="text-xs text-blue-600 font-medium pt-2 italic">학번은 209**으로 입력해주세요</p>
                <p class="text-[10px] text-gray-400">※ 최은지 선생님은 20900 입력</p>
            </div>

            <div class="space-y-4">
                <div class="text-left">
                    <label class="text-[11px] font-bold text-[#86868b] ml-4 mb-1 block uppercase">Student ID</label>
                    <input id="login-number" type="text" placeholder="20901" 
                        class="apple-input w-full h-[58px] px-6 rounded-2xl outline-none text-lg">
                </div>
                <div class="text-left">
                    <label class="text-[11px] font-bold text-[#86868b] ml-4 mb-1 block uppercase">Name</label>
                    <input id="login-name" type="text" placeholder="이름" 
                        class="apple-input w-full h-[58px] px-6 rounded-2xl outline-none text-lg">
                </div>
                <button onclick="checkLogin()" 
                    class="w-full h-[58px] bg-[#0071e3] text-white rounded-2xl font-semibold text-lg hover:bg-[#0077ed] transition-all mt-4 shadow-lg shadow-blue-500/20">
                    입장하기
                </button>
            </div>
            <p id="login-error" class="text-red-500 text-sm font-medium mt-6 hidden">로그인 정보를 다시 확인해주세요.</p>
        </div>
    </div>

    <div id="main-content" class="fade-in">
        <nav class="sticky top-0 z-50 bg-white/70 backdrop-blur-xl border-b border-black/5">
            <div class="max-w-[980px] mx-auto px-6 h-[48px] flex items-center justify-between">
                <span class="font-bold tracking-tight">2-9 Class</span>
                <span class="text-xs text-[#86868b]">Suneung D-Day</span>
            </div>
        </nav>

        <main class="max-w-[980px] mx-auto px-6 py-12 space-y-10">
            <section class="text-center py-12">
                <p class="text-[#86868b] text-sm font-bold tracking-[0.3em] uppercase mb-4">2027. 11. 19</p>
                <div id="dday-display" class="text-[100px] md:text-[150px] font-bold tracking-tighter leading-none mb-6">D-???</div>
                <p class="text-2xl font-medium text-blue-600 italic">"Stay focused, Keep going."</p>
            </section>

            <section class="bg-white rounded-[32px] p-10 md:p-16 border border-black/5 shadow-sm">
                <span class="text-blue-600 font-bold text-sm tracking-widest mb-6 block uppercase">Teacher's Message</span>
                <h2 class="text-3xl md:text-4xl font-bold leading-tight mb-10 tracking-tight">
                    "기말고사 고생 많았어! <br>지치지 말고 끝까지 함께 가보자. <br>너희는 생각보다 훨씬 더 단단한 사람들이야."
                </h2>
                <div class="flex items-center gap-4">
                    <div class="w-12 h-12 rounded-full bg-blue-500 flex items-center justify-center text-white font-bold text-xl">최</div>
                    <div>
                        <p class="text-lg font-bold text-[#1d1d1f]">최은지 선생님</p>
                        <p class="text-[#86868b] text-sm">2학년 9반 담임선생님</p>
                    </div>
                </div>
            </section>

            <section class="bg-white rounded-[32px] p-10 border border-black/5 shadow-sm">
                <h3 class="text-2xl font-bold mb-8">오늘의 식단 <span class="text-[#86868b] text-sm font-normal ml-2">12월 1일 월요일</span></h3>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-12 text-[#1d1d1f]">
                    <div class="space-y-4">
                        <p class="text-xs font-bold text-blue-600 tracking-widest uppercase">Lunch</p>
                        <p class="text-xl font-semibold leading-relaxed">오색현미밥, 소고기배추된장국, 숯불닭갈비보쌈, 노란호박전, 샤인머스켓 ✨</p>
                    </div>
                    <div class="space-y-4">
                        <p class="text-xs font-bold text-orange-500 tracking-widest uppercase">Dinner</p>
                        <p class="text-xl font-semibold leading-relaxed">청차조밥, 병천식순대국, 돈사태메추리알조림, 오징어야채초무침, 감귤 🍊</p>
                    </div>
                </div>
            </section>
        </main>
    </div>

    <script>
        function checkLogin() {
            const num = document.getElementById('login-number').value;
            const name = document.getElementById('login-name').value;

            // 209XX 학번 또는 선생님 전용 번호 체크
            if((num.startsWith("209") || num === "20900") && name.length >= 2) {
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
