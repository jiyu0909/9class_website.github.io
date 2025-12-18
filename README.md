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

        .background-layer {
            position: fixed;
            top: 0; left: 0; right: 0; bottom: 0;
            z-index: -1;
            background: radial-gradient(at 0% 0%, rgba(245, 245, 247, 1) 0px, transparent 50%),
                        radial-gradient(at 100% 0%, rgba(226, 226, 234, 0.4) 0px, transparent 50%),
                        radial-gradient(at 50% 100%, rgba(242, 242, 247, 0.8) 0px, transparent 50%);
        }

        .glass-panel {
            background: rgba(255, 255, 255, 0.75) !important;
            backdrop-filter: blur(25px) saturate(180%) !important;
            -webkit-backdrop-filter: blur(25px) saturate(180%) !important;
            border: 1px solid rgba(255, 255, 255, 0.5);
            border-radius: 28px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.03);
        }

        #main-content { display: none; }
        .fade-in { animation: fadeIn 0.6s cubic-bezier(0.2, 0.8, 0.2, 1) forwards; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

        .timetable-scroll {
            display: flex; gap: 12px; overflow-x: auto; padding: 10px 0;
            scrollbar-width: none;
        }
        .timetable-scroll::-webkit-scrollbar { display: none; }
        .day-box { flex: 0 0 145px; background: rgba(255, 255, 255, 0.5); border: 1px solid rgba(0,0,0,0.03); border-radius: 20px; padding: 20px; text-align: center; }
    </style>
</head>
<body>
    <div class="background-layer"></div>

    <div id="login-section" class="min-h-screen flex items-center justify-center p-6">
        <div class="w-full max-w-[380px] glass-panel p-12 text-center fade-in">
            <h1 class="text-7xl font-bold text-[#e5e5ea] tracking-tighter mb-8 italic">Login</h1>
            
            <div class="space-y-1 mb-8">
                <p class="text-sm font-bold text-[#86868b]">209**으로 입력해 주세요</p>
                <p class="text-[11px] text-[#aeaeb2]">(최은지 선생님은 20900)</p>
            </div>

            <div class="space-y-3">
                <input id="login-number" type="text" placeholder="학번" class="w-full h-14 px-5 rounded-2xl bg-white/60 border border-gray-100 focus:bg-white outline-none text-center">
                <input id="login-name" type="text" placeholder="이름" class="w-full h-14 px-5 rounded-2xl bg-white/60 border border-gray-100 focus:bg-white outline-none text-center">
                <button onclick="checkLogin()" class="w-full h-14 bg-[#1d1d1f] text-white rounded-2xl font-bold mt-4 active:scale-95 transition-transform">입장하기</button>
            </div>
            <p id="login-error" class="text-red-500 text-[11px] mt-6 hidden font-bold">다시 확인해 주세요.</p>
        </div>
    </div>

    <div id="main-content" class="fade-in">
        <nav class="sticky top-0 z-50 bg-white/70 backdrop-blur-xl border-b border-gray-100">
            <div class="max-w-[800px] mx-auto px-6 h-[52px] flex items-center justify-between">
                <span class="font-bold text-lg tracking-tight">2-9</span>
                <span class="text-[10px] font-bold tracking-widest text-gray-400 uppercase">수능 Countdown</span>
            </div>
        </nav>

        <main class="max-w-[800px] mx-auto px-6 py-12 space-y-10">
            <section class="text-center py-8">
                <p class="text-blue-600 text-[10px] font-black tracking-[0.4em] mb-2 uppercase">November 19, 2026</p>
                <div id="dday-display" class="text-[90px] md:text-[130px] font-bold tracking-tighter leading-none">D-???</div>
            </section>

            <section class="glass-panel p-8 border-l-[8px] border-black">
                <p class="text-[10px] font-black text-gray-400 tracking-widest mb-4 uppercase">Notice</p>
                <h2 class="text-xl md:text-2xl font-bold leading-relaxed mb-8">
                    "지각, 교복 제대로 안 입으면 학년에서 강력하게 지도한다고 함. 잘 챙겨 입고 늦지 않게 등교하자~"
                </h2>
                <p class="font-bold text-sm">최은지 선생님</p>
            </section>

            <section class="glass-panel p-8 md:p-10">
                <div class="flex items-baseline justify-between mb-10 border-b border-black/5 pb-6">
                    <h3 class="text-2xl font-bold tracking-tight text-black">오늘의 식단</h3>
                    <span id="current-date-display" class="text-gray-400 font-bold text-xs uppercase tracking-widest"></span>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-12">
                    <div>
                        <p class="text-[10px] font-black text-gray-300 tracking-widest uppercase mb-4">Lunch</p>
                        <ul id="lunch-list" class="text-[15px] font-medium leading-relaxed space-y-2 text-gray-600"></ul>
                    </div>
                    <div>
                        <p class="text-[10px] font-black text-gray-300 tracking-widest uppercase mb-4">Dinner</p>
                        <ul id="dinner-list" class="text-[15px] font-medium leading-relaxed space-y-2 text-gray-600"></ul>
                    </div>
                </div>
            </section>

            <section class="glass-panel p-8">
                <div class="timetable-scroll">
                    <div class="day-box"><span class="block font-bold mb-4 border-b pb-2">월</span><ul class="text-xs space-y-2 text-gray-400"><li>자습</li><li>독서</li><li>영어2</li><li>2-A</li><li>일본어</li><li>2-B</li><li>체육</li></ul></div>
                    <div class="day-box"><span class="block font-bold mb-4 border-b pb-2">화</span><ul class="text-xs space-y-2 text-gray-400"><li>확통</li><li>2-A</li><li>수학2</li><li>영어2</li><li>2-B</li><li>2-C</li><li>독서</li></ul></div>
                    <div class="day-box"><span class="block font-bold mb-4 border-b pb-2">수</span><ul class="text-xs space-y-2 text-gray-400"><li>2-A</li><li>수학2</li><li>독서</li><li>2-B</li><li>진로</li><li>영어2</li><li>2-C</li></ul></div>
                    <div class="day-box"><span class="block font-bold mb-4 border-b pb-2">목</span><ul class="text-xs space-y-2 text-gray-400"><li>독서</li><li>확통</li><li>2-C</li><li>일본어</li><li>2-A</li><li>수학2</li></ul></div>
                    <div class="day-box"><span class="block font-bold mb-4 border-b pb-2 text-blue-600">금</span><ul class="text-xs space-y-2 text-gray-400"><li>영어2</li><li>2-C</li><li>창체</li><li>창체</li><li>수학2</li><li>2-B</li></ul></div>
                </div>
            </section>
        </main>
    </div>

    <script>
        const mealData = {
            "2025-12-18": { lunch: ["식단 정보가 없습니다."], dinner: ["식단 정보가 없습니다."] },
            "2025-12-19": {
                lunch: ["혼합잡곡밥", "한우들깨미역국", "돈안심떡장조림", "참나물무생채", "살살녹는 슈프림치킨", "뿌링클크림치즈볼", "멜론", "배추김치"],
                dinner: ["강황쌀밥", "얼큰동태찌개", "매콤갑오징어볶음", "언양식불고기전 & 상추파채무침", "요구르트(런)", "배추김치"]
            },
            "2025-12-22": {
                lunch: ["한우콩나물비빔밥", "부추양념장", "두부된장국", "순살맛쵸킹치킨&웨지감자", "다시마채무침", "요거트과일샐러드", "팥앙코증편", "동지팥죽(자율)", "배추김치"],
                dinner: ["기장밥", "부대찌개", "한입떡갈비&떡조림", "두부양념구이", "멸치마늘쫑조림", "사과", "배추김치"]
            },
            "2025-12-23": {
                lunch: ["찹쌀밥", "누룽지삼계탕", "두부오징어김치전", "메추리알어묵조림", "오이고추쌈장무침", "황금향", "깍두기"],
                dinner: ["베이컨김치볶음밥&스크램블드에그", "가쓰오장국", "바질페스토 크림떡볶이", "수원왕갈비맛돈강정", "파인애플C주스", "깍두기"]
            },
            "2025-12-24": {
                lunch: ["흑미기장밥", "사골육개장", "황금랍스터치즈구이&구운야채", "우엉당면잡채", "케이준치킨샐러드", "꽈리고추찜", "크리스마스케이크", "배추김치"],
                dinner: ["혼합잡곡밥", "순살안동찜닭", "에그랑땡전", "미역줄기볶음", "김치왕만두", "멜론", "배추김치"]
            },
            "2025-12-26": {
                lunch: ["누룽현미밥", "단배추들깨된장국", "동파육&청경채숙회", "해물콩나물찜", "가리비꽃빵", "파인애플곤약젤리", "배추김치"],
                dinner: ["찹쌀밥", "맑은콩나물국", "흑초간장오리불고기&레몬무쌈", "일식달걀찜", "부추겉절이", "감귤", "배추김치"]
            },
            "2025-12-29": {
                lunch: ["기장밥", "강릉식 짬뽕순두부국", "제육불고기", "훈제오리감자볶음", "숙주미나리무침", "다시마양배추쌈(자율)", "오렌지", "배추김치"],
                dinner: ["돈육직화자장면", "파송송계란국", "쫄깃바삭닭가슴살 꿔바로우", "육즙소룡포", "반달단무지", "해가득포도주스", "배추김치"]
            },
            "2025-12-30": {
                lunch: ["새우달걀볶음밥", "꼬지어묵국", "수제치킨커틀릿&소스", "토마토양상추샐러드", "초코생크림 오믈렛", "매일요구르트", "배추김치"],
                dinner: ["혼합잡곡밥", "굴림만두꽃떡국", "고등어무조림", "분홍소시지전", "매콤콩나물무침", "미니도시락김", "깍두기"]
            }
        };

        function checkLogin() {
            const num = document.getElementById('login-number').value.trim();
            const name = document.getElementById('login-name').value.trim();
            if((num === "20900" || num.startsWith("209")) && name.length >= 2) {
                document.getElementById('login-section').style.display = 'none';
                document.getElementById('main-content').style.display = 'block';
                initPage();
            } else {
                document.getElementById('login-error').classList.remove('hidden');
            }
        }

        function initPage() {
            const target = new Date("2026-11-19T00:00:00");
            const now = new Date();
            const diff = target - now;
            document.getElementById('dday-display').innerText = `D-${Math.ceil(diff / (1000 * 60 * 60 * 24))}`;

            const year = now.getFullYear();
            const month = String(now.getMonth() + 1).padStart(2, '0');
            const date = String(now.getDate()).padStart(2, '0');
            const dayNames = ["일요일", "월요일", "화요일", "수요일", "목요일", "금요일", "토요일"];
            
            document.getElementById('current-date-display').innerText = `${month}월 ${date}일 ${dayNames[now.getDay()]}`;

            const todayStr = `${year}-${month}-${date}`;
            const todayMeal = mealData[todayStr] || { lunch: ["정보가 없습니다."], dinner: ["정보가 없습니다."] };

            document.getElementById('lunch-list').innerHTML = todayMeal.lunch.map(item => `<li>${item}</li>`).join('');
            document.getElementById('dinner-list').innerHTML = todayMeal.dinner.map(item => `<li>${item}</li>`).join('');
        }
        document.addEventListener('keypress', (e) => { if(e.key === 'Enter') checkLogin(); });
    </script>
</body>
</html>
