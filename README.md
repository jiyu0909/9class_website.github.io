# 9class_website.github.io[index.html](https://github.com/user-attachments/files/22097191/index.html)
[index.html](https://github.com/user-attachments/files/22081972/index.html)
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
            /* 더 부드러운 그라데이션과 애니메이션 속도 조정 */
            background: linear-gradient(-45deg, #fbcfe8, #ecc8d4, #fecaca, #fae8ff);
            background-size: 400% 400%;
            animation: gradient 15s ease infinite;
        }
        @keyframes gradient {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        /* 카드 호버 효과 */
        .card {
            transition: all 0.3s ease-in-out;
        }
        .card:hover {
            transform: translateY(-4px);
            box-shadow: 0 10px 15px rgba(0, 0, 0, 0.1), 0 4px 6px rgba(0, 0, 0, 0.05);
        }
        /* 오늘 시간표 강조 */
        .today-schedule {
            border: 3px solid #db2777 !important; /* 진한 핑크색 테두리 */
            background-color: #ffe4e6 !important; /* 연한 핑크 배경 */
            box-shadow: 0 4px 6px -1px rgba(219, 39, 119, 0.2), 0 2px 4px -2px rgba(219, 39, 119, 0.1);
        }
    </style>
</head>
<body class="min-h-screen">
    <div class="max-w-6xl mx-auto p-4 lg:p-8 space-y-6">

        <header class="sticky top-0 bg-white/80 backdrop-blur-sm shadow-lg rounded-2xl py-4 px-6 mb-8 z-10">
            <h1 class="text-3xl font-extrabold text-pink-600 text-center">
                📚 2학년 9반 알리미 💖
            </h1>
        </header>

        <main class="grid grid-cols-1 lg:grid-cols-3 gap-6">

            <div class="lg:col-span-1 space-y-6">
                
                <section class="card bg-white rounded-2xl shadow-xl p-6">
                    <h2 class="text-2xl font-bold text-pink-700 border-b pb-2 mb-4">📢 은지쌤의 말씀</h2>
                    <ul class="mt-4 space-y-3">
                        <li class="p-3 rounded-xl bg-pink-50 border border-pink-200">
                            <p class="text-base text-pink-800">✨ 2학기 기말고사 준비! 열공하기~</p>
                        </li>
                        <li class="p-3 rounded-xl bg-pink-50 border border-pink-200">
                            <p class="text-base text-pink-800">🧥 사복은 마이 입고 입기!</p>
                        </li>
                        <li class="p-3 rounded-xl bg-pink-50 border border-pink-200">
                            <p class="text-base text-pink-800">⏰ 이동수업 이동은 5분 전부터</p>
                        </li>
                        <li class="p-3 rounded-xl bg-pink-50 border border-pink-200">
                            <p class="text-base text-pink-800">❌ 수업/자습시간 잠자기 금지</p>
                        </li>
                        <li class="p-3 rounded-xl bg-pink-50 border border-pink-200">
                            <p class="text-base text-pink-800">담요 다리에만 덮고 추우면 체육복 후드 입기</p>
                        </li>
                        <li class="p-3 rounded-xl bg-pink-50 border border-pink-200">
                            <p class="text-base text-pink-800">🧹 책상 위 항상 깔끔히</p>
                        </li>
                        <li class="p-3 rounded-xl bg-pink-50 border border-pink-200">
                            <p class="text-base text-pink-800">신고서 당일에 나이스에 업로드 (인정결, 결석)</p>
                        </li>
                        <li class="p-3 rounded-xl bg-pink-50 border border-pink-200">
                            <p class="text-base text-pink-800">패드 사용 후 무조건 쉬는시간에 내기 딴짓하다 걸리면 **일주일 압수!!!**</p>
                        </li>
                    </ul>
                </section>

                <section class="card bg-white rounded-2xl shadow-xl p-6">
                    <h2 class="text-2xl font-bold text-pink-700 border-b pb-2 mb-4">🗓️ 다가오는 일정</h2>
                    <ol class="mt-4 space-y-4">
                        <li class="p-3 rounded-xl border-l-4 border-pink-500 bg-pink-50">
                            <div class="text-sm text-pink-500 font-semibold">2025-09-08</div>
                            <div class="font-bold text-lg mt-0.5">국어, 확통 수행평가</div>
                            <div class="text-sm text-pink-700">게시판 프린트 확인하고 미리 대비하기</div>
                        </li>
                        <li class="p-3 rounded-xl border-l-4 border-pink-500 bg-pink-50">
                            <div class="text-sm text-pink-500 font-semibold">2025-09-18 ~ 09-23</div>
                            <div class="font-bold text-lg mt-0.5">교과축전 준비기간</div>
                        </li>
                        <li class="p-3 rounded-xl border-l-4 border-pink-500 bg-pink-50">
                            <div class="text-sm text-pink-500 font-semibold">2025-09-25 ~ 09-30</div>
                            <div class="font-bold text-lg mt-0.5">축제제 준비기간</div>
                        </li>
                        <li class="p-3 rounded-xl border-l-4 border-red-500 bg-red-50">
                            <h3 class="font-bold text-red-600 text-lg">📅 시험 D-Day</h3>
                            <ul id="dday-list" class="mt-1 space-y-0.5 text-base"></ul>
                        </li>
                    </ol>
                </section>
            </div>

            <div class="lg:col-span-2 space-y-6">

                <section class="card bg-white rounded-2xl shadow-xl p-6">
    <h2 class="text-2xl font-bold text-pink-700 border-b pb-2 mb-4">🕒 주간 시간표</h2>
    <div class="grid grid-cols-2 md:grid-cols-5 gap-4 mt-4 text-sm">
        
        <div id="mon" class="timetable-box bg-white rounded-xl shadow p-3 border border-gray-100">
            <h3 class="font-bold text-pink-600 text-lg">월요일</h3>
            <ul class="mt-2 space-y-1">
                <li>H.R</li>
                <li>독서</li>
                <li>영어2</li>
                <li>2-A</li>
                <li>일본어</li>
                <li>2-B</li>
                <li>체육</li>
            </ul>
        </div>
        
        <div id="tue" class="timetable-box bg-white rounded-xl shadow p-3 border border-gray-100">
            <h3 class="font-bold text-pink-600 text-lg">화요일</h3>
            <ul class="mt-2 space-y-1">
                <li>확률과 통계</li>
                <li>2-A</li>
                <li>수학2</li>
                <li>영어2</li>
                <li>2-B</li>
                <li>2-C</li>
                <li>독서</li>
            </ul>
        </div>
        
        <div id="wed" class="timetable-box bg-white rounded-xl shadow p-3 border border-gray-100">
            <h3 class="font-bold text-pink-600 text-lg">수요일</h3>
            <ul class="mt-2 space-y-1">
                <li>2-A</li>
                <li>수학2</li>
                <li>독서</li>
                <li>2-B</li>
                <li>진로</li>
                <li>영어2</li>
                <li>2-C</li>
            </ul>
        </div>
        
        <div id="thu" class="timetable-box bg-white rounded-xl shadow p-3 border border-gray-100">
            <h3 class="font-bold text-pink-600 text-lg">목요일</h3>
            <ul class="mt-2 space-y-1">
                <li>독서</li>
                <li>확률과 통계</li>
                <li>2-C</li>
                <li>일본어</li>
                <li>2-A</li>
                <li>수학2</li>
                <li>(자율/빈 시간)</li>
            </ul>
        </div>
        
        <div id="fri" class="timetable-box bg-white rounded-xl shadow p-3 border border-gray-100">
            <h3 class="font-bold text-pink-600 text-lg">금요일</h3>
            <ul class="mt-2 space-y-

                <section class="card bg-white rounded-2xl shadow-xl p-6">
                    <h2 class="text-2xl font-bold text-pink-700 border-b pb-2 mb-4">📚 시험공부 참고자료</h2>
                    <ul class="mt-4 space-y-4">
                        <li class="border-l-4 border-orange-500 pl-3">
                            <p class="font-bold text-lg text-orange-600">오은지쌤 독서 해설 강의 (2025 9월 국어 모의고사)</p>
                            <div class="grid grid-cols-1 md:grid-cols-3 gap-3 mt-2">
                                <a href="https://youtu.be/75pzWRiKqyE" target="_blank"
                                    class="block bg-pink-500 text-white text-center px-4 py-2 rounded-lg shadow hover:bg-pink-600 transition-colors">
                                    📘 16~21번
                                </a>
                                <a href="https://youtu.be/bHFxqPdb6pw" target="_blank"
                                    class="block bg-pink-500 text-white text-center px-4 py-2 rounded-lg shadow hover:bg-pink-600 transition-colors">
                                    📗 22~26번
                                </a>
                                <a href="https://youtu.be/ZNWJjvwaGOo" target="_blank"
                                    class="block bg-pink-500 text-white text-center px-4 py-2 rounded-lg shadow hover:bg-pink-600 transition-colors">
                                    📙 34~37번
                                </a>
                            </div>
                        </li>
                        <li class="border-l-4 border-pink-500 pl-3">
                            <p class="font-bold text-lg text-pink-600">이우진쌤 문학 해설 강의 (2025 9월 국어 모의고사)</p>
                            <div class="mt-2">
                                <a href="https://www.youtube.com/playlist?list=PLr_xvqtyr_SYBmAwD-AXSumMbhYocbGDB" target="_blank"
                                    class="block bg-pink-500 text-white text-center px-4 py-2 rounded-lg shadow hover:bg-pink-600 transition-colors">
                                    🥰 2025 9월 고2 전국연합학력평가 플레이리스트
                                </a>
                            </div>
                        </li>
                        <li class="border-l-4 border-indigo-500 pl-3">
                            <p class="font-bold text-lg text-indigo-600">김세원쌤 영어 모고 해설 강의</p>
                            <div class="mt-2">
                                <a href="https://open.kakao.com/o/gO4vr1og" target="_blank"
                                    class="block bg-pink-500 text-white text-center px-4 py-2 rounded-lg shadow hover:bg-pink-600 transition-colors">
                                    🩵 2025 9월 고2 영어 전국연합학력평가 (오픈카톡)
                                </a>
                            </div>
                        </li>
                    </ul>
                </section>

                <section class="card bg-white rounded-2xl shadow-xl p-6">
                    <h2 class="text-2xl font-bold text-pink-700 border-b pb-2 mb-4">🍚 급식 정보</h2>
                    <div id="meal-container" class="space-y-6 mt-4 text-base">
                        <div class="meal-box p-4 rounded-xl border border-gray-100 bg-gray-50">
                            <h3 class="font-bold text-pink-600 text-lg mb-2">2025-09-05 (금)</h3>
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                                <div>
                                    <h4 class="font-semibold mt-2 text-blue-600">🌞 중식</h4>
                                    <ul class="list-disc list-inside mt-1 space-y-0.5 ml-2">
                                        <li>흑미기장밥</li>
                                        <li>들깨삼계탕</li>
                                        <li>갈비맛찐만두</li>
                                        <li>오이고추쌈장무침</li>
                                        <li>가을노란호박전</li>
                                        <li>깍두기</li>
                                        <li>친환경 샤인머스캣</li>
                                    </ul>
                                </div>
                                <div>
                                    <h4 class="font-semibold mt-2 text-green-600">🌙 석식</h4>
                                    <ul class="list-disc list-inside mt-1 space-y-0.5 ml-2">
                                        <li>콩나물비빔밥&부추양념장</li>
                                        <li>근대된장국</li>
                                        <li>샐러드</li>
                                        <li>다시마채무침</li>
                                        <li>뿌링뿌링돈가스&감자튀김</li>
                                        <li>배추김치</li>
                                        <li>마시는 요거트 런</li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                        <div class="meal-box p-4 rounded-xl border border-gray-100 bg-gray-50">
                            <h3 class="font-bold text-pink-600 text-lg mb-2">2025-09-08 (월)</h3>
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                                <div>
                                    <h4 class="font-semibold mt-2 text-blue-600">🌞 중식</h4>
                                    <ul class="list-disc list-inside mt-1 space-y-0.5 ml-2">
                                        <li>오색현미밥</li>
                                        <li>한우들깨미역국</li>
                                        <li>멸치꽈리고추조림</li>
                                        <li>새우고기완자전</li>
                                        <li>바베큐치킨스테이크&구운야채</li>
                                        <li>배추김치</li>
                                        <li>친환경멜론</li>
                                    </ul>
                                </div>
                                <div>
                                    <h4 class="font-semibold mt-2 text-green-600">🌙 석식</h4>
                                    <ul class="list-disc list-inside mt-1 space-y-0.5 ml-2">
                                        <li>혼합잡곡밥</li>
                                        <li>병천식순대국&소면</li>
                                        <li>오이고추쌈장무침</li>
                                        <li>부추겉절이</li>
                                        <li>광장시장완자전&양파절임소스</li>
                                        <li>깍두기</li>
                                        <li>친환경 거봉</li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                        <div class="meal-box p-4 rounded-xl border border-gray-100 bg-gray-50">
                            <h3 class="font-bold text-pink-600 text-lg mb-2">2025-09-15 (월)</h3>
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                                <div>
                                    <h4 class="font-semibold mt-2 text-blue-600">🌞 중식</h4>
                                    <ul class="list-disc list-inside mt-1 space-y-0.5 ml-2">
                                        <li>흥국쌀밥</li>
                                        <li>경상도식소고기국</li>
                                        <li>해물볶음우동</li>
                                        <li>다시마채무침</li>
                                        <li>순살치킨커틀릿</li>
                                        <li>배추김치</li>
                                        <li>삼색과일꼬지</li>
                                    </ul>
                                </div>
                                <div>
                                    <h4 class="font-semibold mt-2 text-green-600">🌙 석식</h4>
                                    <ul class="list-disc list-inside mt-1 space-y-0.5 ml-2">
                                        <li>찹쌀밥(작은밥)</li>
                                        <li>쉬림프 갈릭오일파스타</li>
                                        <li>배추김치</li>
                                        <li>삼색모듬피클</li>
                                        <li>치즈함박스테이크</li>
                                        <li>브로콜리 크림스프, 바게트스틱</li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                    </div>
                </section>

                <section class="card bg-white rounded-2xl shadow-xl p-6">
                    <h2 class="text-2xl font-bold text-pink-700 border-b pb-2 mb-4">📝 시험 범위</h2>
                    <div class="overflow-x-auto">
                        <table class="w-full text-left border-collapse">
                            <thead>
                                <tr class="bg-pink-100">
                                    <th class="px-4 py-3 text-pink-700 w-1/4">과목</th>
                                    <th class="px-4 py-3 text-pink-700 w-3/4">시험 범위</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr class="border-b hover:bg-gray-50"><td class="px-4 py-3 font-medium">독서</td><td>교과서: (범위 입력)</td></tr>
                                <tr class="border-b hover:bg-gray-50"><td class="px-4 py-3 font-medium">수학2</td><td>(범위 입력)</td></tr>
                                <tr class="border-b hover:bg-gray-50"><td class="px-4 py-3 font-medium">일본어</td><td>(범위 입력)</td></tr>
                                <tr class="border-b hover:bg-gray-50"><td class="px-4 py-3 font-medium">확률과 통계</td><td>(범위 입력)</td></tr>
                                <tr class="border-b hover:bg-gray-50"><td class="px-4 py-3 font-medium">영어2</td><td>(범위 입력)</td></tr>
                                <tr class="border-b hover:bg-gray-50"><td class="px-4 py-3 font-medium">지구과학</td><td>(범위 입력)</td></tr>
                                <tr class="hover:bg-gray-50"><td class="px-4 py-3 font-medium">물리</td><td>(범위 입력)</td></tr>
                            </tbody>
                        </table>
                        <p class="mt-4 text-sm text-gray-500">※ 시험 범위는 확정되는 대로 업데이트해주세요!</p>
                    </div>
                </section>
            </div>
        </main>

        <footer class="text-center text-pink-600 text-sm mt-8 py-4">
            제작: 20919 이지유 | <a href="https://github.com/9class_website/9class_website.github.io" target="_blank" class="hover:text-pink-800 transition-colors">GitHub에서 소스 보기</a>
        </footer>

    </div>

    <script>
        // --- D-Day 계산 스크립트 ---
        const exams = [
            { name: "2학기 기말고사", date: "2025-12-09" }
        ];

        const today = new Date();
        today.setHours(0, 0, 0, 0);

        const ddayList = document.getElementById("dday-list");

        exams.sort((a, b) => new Date(a.date) - new Date(b.date));

        exams.forEach(({ name, date }) => {
            const target = new Date(date + "T00:00:00");
            const diffDays = Math.ceil((target - today) / (1000 * 60 * 60 * 24));

            let label = "D-DAY";
            let colorClass = "text-red-500";

            if (diffDays > 0) {
                label = `D-${diffDays}`;
            } else if (diffDays < 0) {
                label = `D+${Math.abs(diffDays)}`;
                colorClass = "text-green-500"; // 시험 종료 후 색상 변경
            }

            const li = document.createElement("li");
            li.innerHTML = `${name}: <span class="font-bold ${colorClass}">${label}</span>`;
            ddayList.appendChild(li);
        });

        // --- 오늘의 시간표 강조 스크립트 ---
        document.addEventListener("DOMContentLoaded", () => {
            const dayOfWeek = new Date().getDay(); // 0:일, 1:월, ..., 5:금, 6:토
            let todayId = '';

            switch (dayOfWeek) {
                case 1: todayId = 'mon'; break;
                case 2: todayId = 'tue'; break;
                case 3: todayId = 'wed'; break;
                case 4: todayId = 'thu'; break;
                case 5: todayId = 'fri'; break;
                // 주말(토,일)에는 아무것도 강조하지 않음
                default: return; 
            }

            const todayBox = document.getElementById(todayId);
            if (todayBox) {
                todayBox.classList.add("today-schedule");
            }
        });
    </script>
</body>
</html>
