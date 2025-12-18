<!doctype html>
<html lang="ko">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>📚 2-9반 알리미 🤍</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@700&display=swap" rel="stylesheet">
    <style>
        @font-face {
            font-family: 'Gonici';
            src: url('https://cdn.jsdelivr.net/gh/projectnoonnu/noonfonts_2108@1.1/Gonici.woff2') format('woff2');
        }
        body {
            font-family: 'Gonici', 'Baloo 2', sans-serif;
            min-height: 100vh;
            background: linear-gradient(-45deg, #fbcfe8, #ecc8d4, #fecaca, #fae8ff);
            background-size: 400% 400%;
            animation: gradient 15s ease infinite;
            word-break: keep-all; /* 한글 줄바꿈 예쁘게 */
        }
        @keyframes gradient {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        .card { transition: all 0.3s ease-in-out; }
        .card:hover {
            transform: translateY(-4px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }
        .today-schedule {
            border: 3px solid #db2777 !important;
            background-color: #fff1f2 !important;
            transform: scale(1.02);
            z-index: 10;
        }
        /* 시간표 글씨 겹침 방지 */
        .timetable-box ul li {
            padding: 4px 0;
            border-bottom: 1px dashed #fce7f3;
        }
        .timetable-box ul li:last-child { border-bottom: none; }
    </style>
</head>
<body class="p-4 md:p-8">
    <div class="max-w-7xl mx-auto space-y-8">
        <header class="sticky top-4 bg-white/90 backdrop-blur-md shadow-xl rounded-3xl py-6 px-8 z-50 border border-white/50">
            <h1 class="text-3xl md:text-4xl font-extrabold text-pink-600 text-center tracking-tight">
                📚 2학년 9반 알리미 💖
            </h1>
        </header>

        <main class="grid grid-cols-1 lg:grid-cols-12 gap-8">
            <div class="lg:col-span-4 space-y-8">
                <section class="card bg-white/80 rounded-3xl shadow-xl p-6 border border-white">
                    <h2 class="text-2xl font-bold text-pink-700 border-b-2 border-pink-100 pb-3 mb-4 flex items-center">
                        📢 은지쌤의 말씀
                    </h2>
                    <ul class="space-y-3">
                        <li class="p-3 rounded-2xl bg-pink-50/50 border border-pink-100 text-pink-800 text-sm md:text-base">
                            ✨ 2학기 기말고사 준비! 열공하기~
                        </li>
                        <li class="p-3 rounded-2xl bg-white border border-pink-100 text-pink-800 text-sm italic">
                            💡 패드 딴짓 금지! (일주일 압수 🤐)
                        </li>
                        <li class="p-3 rounded-2xl bg-white border border-pink-100 text-pink-800 text-sm">
                            🧥 사복은 마이 위에 입기
                        </li>
                        <li class="p-3 rounded-2xl bg-white border border-pink-100 text-pink-800 text-sm">
                            🧹 책상 위 항상 깔끔하게 유지
                        </li>
                    </ul>
                </section>

                <section class="card bg-white/80 rounded-3xl shadow-xl p-6 border border-white">
                    <h2 class="text-2xl font-bold text-pink-700 border-b-2 border-pink-100 pb-3 mb-4">🗓️ 다가오는 일정</h2>
                    <div class="space-y-4">
                        <div class="p-4 rounded-2xl border-l-8 border-red-500 bg-red-50 shadow-sm">
                            <h3 class="font-bold text-red-600 text-lg">📅 시험 D-Day</h3>
                            <ul id="dday-list" class="mt-2 space-y-1 font-bold"></ul>
                        </div>
                        <div class="p-4 rounded-2xl border-l-4 border-pink-400 bg-white">
                            <div class="text-xs text-pink-400 font-bold">2025-09-08</div>
                            <div class="font-bold text-pink-800">국어, 확통 수행평가</div>
                        </div>
                    </div>
                </section>
            </div>

            <div class="lg:col-span-8 space-y-8">
                <section class="card bg-white rounded-3xl shadow-xl p-6 border border-white">
                    <h2 class="text-2xl font-bold text-pink-700 border-b-2 border-pink-100 pb-3 mb-6">🕒 주간 시간표</h2>
                    <div class="overflow-x-auto pb-4">
                        <div class="flex lg:grid lg:grid-cols-5 gap-4 min-w-[800px] lg:min-w-full">
                            <div id="mon" class="timetable-box flex-1 bg-white rounded-2xl shadow-sm p-4 border border-pink-50">
                                <h3 class="font-bold text-pink-600 text-center mb-3 border-b border-pink-100 pb-1">월</h3>
                                <ul class="text-center text-gray-700 text-sm space-y-2 font-medium">
                                    <li>H.R</li><li>독서</li><li>영어2</li><li>2-A</li><li>일본어</li><li>2-B</li><li>체육</li>
                                </ul>
                            </div>
                            <div id="tue" class="timetable-box flex-1 bg-white rounded-2xl shadow-sm p-4 border border-pink-50">
                                <h3 class="font-bold text-pink-600 text-center mb-3 border-b border-pink-100 pb-1">화</h3>
                                <ul class="text-center text-gray-700 text-sm space-y-2 font-medium">
                                    <li>확통</li><li>2-A</li><li>수학2</li><li>영어2</li><li>2-B</li><li>2-C</li><li>독서</li>
                                </ul>
                            </div>
                            <div id="wed" class="timetable-box flex-1 bg-white rounded-2xl shadow-sm p-4 border border-pink-50">
                                <h3 class="font-bold text-pink-600 text-center mb-3 border-b border-pink-100 pb-1">수</h3>
                                <ul class="text-center text-gray-700 text-sm space-y-2 font-medium">
                                    <li>2-A</li><li>수학2</li><li>독서</li><li>2-B</li><li>진로</li><li>영어2</li><li>2-C</li>
                                </ul>
                            </div>
                            <div id="thu" class="timetable-box flex-1 bg-white rounded-2xl shadow-sm p-4 border border-pink-50">
                                <h3 class="font-bold text-pink-600 text-center mb-3 border-b border-pink-100 pb-1">목</h3>
                                <ul class="text-center text-gray-700 text-sm space-y-2 font-medium">
                                    <li>독서</li><li>확통</li><li>2-C</li><li>일본어</li><li>2-A</li><li>수학2</li><li>자율</li>
                                </ul>
                            </div>
                            <div id="fri" class="timetable-box flex-1 bg-white rounded-2xl shadow-sm p-4 border border-pink-50">
                                <h3 class="font-bold text-pink-600 text-center mb-3 border-b border-pink-100 pb-1">금</h3>
                                <ul class="text-center text-gray-700 text-sm space-y-2 font-medium">
                                    <li>2-B</li><li>2-C</li><li>체육</li><li>창체</li><li>창체</li><li>수학2</li><li>-</li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </section>

                <section class="card bg-white rounded-3xl shadow-xl p-6 border border-white">
                    <h2 class="text-2xl font-bold text-pink-700 border-b-2 border-pink-100 pb-3 mb-6">📚 시험공부 참고자료</h2>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div class="p-5 rounded-2xl bg-orange-50 border border-orange-100 flex flex-col justify-between">
                            <h3 class="font-bold text-orange-700 mb-3">📖 국어 독서 해설 (오은지T)</h3>
                            <div class="flex gap-2 flex-wrap">
                                <a href="https://youtu.be/75pzWRiKqyE" target="_blank" class="bg-orange-500 text-white px-3 py-1.5 rounded-xl text-xs hover:bg-orange-600">16~21번</a>
                                <a href="https://youtu.be/bHFxqPdb6pw" target="_blank" class="bg-orange-500 text-white px-3 py-1.5 rounded-xl text-xs hover:bg-orange-600">22~26번</a>
                                <a href="https://youtu.be/ZNWJjvwaGOo" target="_blank" class="bg-orange-500 text-white px-3 py-1.5 rounded-xl text-xs hover:bg-orange-600">34~37번</a>
                            </div>
                        </div>
                        <div class="p-5 rounded-2xl bg-indigo-50 border border-indigo-100 flex flex-col justify-between">
                            <h3 class="font-bold text-indigo-700 mb-3">🖋️ 국어 문학 (이우진T)</h3>
                            <a href="https://www.youtube.com/playlist?list=PLr_xvqtyr_SYBmAwD-AXSumMbhYocbGDB" target="_blank" class="bg-indigo-500 text-white text-center py-2 rounded-xl text-sm hover:bg-indigo-600 shadow-sm">플레이리스트 보기</a>
                        </div>
                        <div class="p-5 rounded-2xl bg-emerald-50 border border-emerald-100 md:col-span-2">
                            <h3 class="font-bold text-emerald-700 mb-2">🔤 영어 모고 해설 (김세원T)</h3>
                            <a href="https://open.kakao.com/o/gO4vr1og" target="_blank" class="text-emerald-600 underline text-sm">오픈카톡 바로가기</a>
                        </div>
                    </div>
                </section>

                <section class="card bg-white rounded-3xl shadow-xl p-6 border border-white">
                    <h2 class="text-2xl font-bold text-pink-700 border-b-2 border-pink-100 pb-3 mb-6">🍚 오늘의 급식</h2>
                    <div class="bg-gray-50 rounded-2xl p-6 border border-gray-100">
                        <h3 class="font-bold text-pink-600 mb-4">9월 5일 (금) 메뉴</h3>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                            <div>
                                <h4 class="font-bold text-blue-500 mb-2 flex items-center">🌞 중식</h4>
                                <p class="text-gray-600 text-sm leading-relaxed">흑미기장밥, 들깨삼계탕, 갈비맛찐만두, 가을노란호박전, 깍두기, 샤인머스캣</p>
                            </div>
                            <div>
                                <h4 class="font-bold text-green-500 mb-2 flex items-center">🌙 석식</h4>
                                <p class="text-gray-600 text-sm leading-relaxed">콩나물비빔밥, 뿌링뿌링돈가스&감자튀김, 다시마채무침, 요거트 런</p>
                            </div>
                        </div>
                    </div>
                </section>
            </div>
        </main>

        <footer class="text-center text-pink-500/80 text-sm py-10">
            제작: 20919 이지유 | <a href="#" class="font-bold hover:underline">GitHub</a>
        </footer>
    </div>

    <script>
        // D-Day 계산
        const exams = [{ name: "2학기 기말고사", date: "2025-12-09" }];
        const today = new Date();
        today.setHours(0,0,0,0);

        const ddayList = document.getElementById("dday-list");
        exams.forEach(({ name, date }) => {
            const target = new Date(date);
            const diffDays = Math.ceil((target - today) / (1000 * 60 * 60 * 24));
            const label = diffDays > 0 ? `D-${diffDays}` : (diffDays === 0 ? "D-DAY" : `D+${Math.abs(diffDays)}`);
            const li = document.createElement("li");
            li.className = "flex justify-between items-center";
            li.innerHTML = `<span>${name}</span> <span class="text-2xl text-red-600">${label}</span>`;
            ddayList.appendChild(li);
        });

        // 오늘 요일 강조
        const dayOfWeek = new Date().getDay();
        const days = [null, 'mon', 'tue', 'wed', 'thu', 'fri'];
        if (days[dayOfWeek]) {
            document.getElementById(days[dayOfWeek]).classList.add("today-schedule");
        }
    </script>
</body>
</html>
