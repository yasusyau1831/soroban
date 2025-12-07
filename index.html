<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>わくわくそろばん 16きゅう</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Yomogi&family=Zen+Maru+Gothic:wght@500;700&display=swap" rel="stylesheet">
    <style>
        /* 基本設定 */
        body {
            font-family: 'Zen Maru Gothic', sans-serif;
            background-color: #f3f4f6;
            touch-action: manipulation;
            user-select: none;
            overscroll-behavior: none;
            cursor: default;
        }

        /* --- デザインパーツ --- */

        /* 黒板 */
        .chalkboard {
            background-color: #1a472a;
            background-image: 
                radial-gradient(#ffffff05 10%, transparent 10%),
                radial-gradient(#00000010 10%, transparent 10%);
            background-size: 20px 20px;
            box-shadow: inset 0 0 20px #00000080;
            font-family: 'Yomogi', cursive;
            color: white;
            text-shadow: 2px 2px 0px rgba(255,255,255,0.1), 1px 1px 2px rgba(0,0,0,0.5);
        }
        .chalk-text { filter: drop-shadow(0 0 1px rgba(255,255,255,0.8)); }

        /* 木枠 */
        .wood-frame {
            background: #8B4513;
            background: repeating-linear-gradient(45deg, #8B4513, #8B4513 10px, #A0522D 10px, #A0522D 20px);
            box-shadow: inset 2px 2px 5px rgba(255,255,255,0.3), inset -2px -2px 5px rgba(0,0,0,0.5), 5px 5px 10px rgba(0,0,0,0.3);
            border: 4px solid #5D4037;
            border-radius: 8px;
        }

        /* そろばんの背景と串 */
        .soroban-column {
            position: relative;
            height: 100%;
            width: 100%;
            /* 串（rod）を中心線として背景で描画 */
            background: 
                linear-gradient(90deg, transparent calc(50% - 2px), #5D4037 calc(50% - 2px), #5D4037 calc(50% + 3px), transparent calc(50% + 3px));
        }

        /* 梁（はり） */
        .beam {
            position: absolute;
            top: 25%; /* 上から25%の位置に配置 */
            left: 0;
            width: 100%;
            height: 14px; /* 少し太く */
            background: linear-gradient(to bottom, #d1d5db, #9ca3af, #d1d5db);
            border-top: 1px solid #4b5563;
            border-bottom: 1px solid #4b5563;
            z-index: 20;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        /* 定位点 */
        .dot {
            width: 6px;
            height: 6px;
            background-color: #111;
            border-radius: 50%;
            z-index: 21;
        }

        /* 珠（たま） */
        .bead {
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            width: 85%; /* カラム幅の85% */
            max-width: 80px; /* モバイルでのデフォルト */
            aspect-ratio: 1.8 / 1; /* 横長比率を固定 */
            cursor: pointer;
            z-index: 10;
            transition: top 0.15s cubic-bezier(0.25, 1, 0.5, 1), transform 0.1s; /* アニメーション調整 */
            
            /* 珠の見た目 */
            background: radial-gradient(circle at 30% 30%, #d97706, #92400e);
            clip-path: polygon(10% 0%, 90% 0%, 100% 50%, 90% 100%, 10% 100%, 0% 50%);
            filter: drop-shadow(1px 1px 2px rgba(0,0,0,0.5));
        }
        
        /* PC向け：珠の最大サイズを大きくする */
        @media (min-width: 768px) {
            .bead {
                max-width: 140px; /* PCではもっと大きく */
            }
        }

        /* PC向け：マウスホバー時のエフェクト */
        @media (hover: hover) {
            .bead:hover {
                filter: drop-shadow(2px 2px 4px rgba(0,0,0,0.4)) brightness(1.2); /* 明るくする */
                transform: translateX(-50%) scale(1.05); /* 少し大きく */
            }
        }
        
        .bead::after {
            content: '';
            position: absolute;
            top: 15%; left: 20%;
            width: 25%; height: 25%;
            background: rgba(255,255,255,0.3);
            border-radius: 50%;
            pointer-events: none;
        }

        /* --- 珠の配置ロジック (topプロパティで制御) --- */

        /* 天エリア (0% ~ 25%) */
        /* 天の珠: OFF=上端(2%), ON=梁の上(25% - 珠の高さ - わずかな隙間) */
        /* ※CSS変数やcalcを使うと確実ですが、ここでは%で簡易調整します */
        
        .bead-heaven {
            top: 2%; /* OFF状態（上にある） */
        }
        .bead-heaven.active {
            top: calc(25% - 14% - 2px); /* ON状態（下がって梁につく） 14%は珠の高さ概算 */
        }

        /* 地エリア (25% ~ 100%) */
        /* 地の珠の高さは約14%と仮定 (75% / 5 = 15%) */
        
        /* 1番上の珠 (値1) */
        .bead-earth-1 { top: calc(25% + 14px + 5%); } /* OFF: 少し離れる */
        .bead-earth-1.active { top: calc(25% + 14px + 0px); } /* ON: 梁の直下 */

        /* 2番目の珠 (値2) */
        .bead-earth-2 { top: calc(25% + 14px + 5% + 14% + 1%); } /* OFF */
        .bead-earth-2.active { top: calc(25% + 14px + 0px + 14%); } /* ON: 1番目の直下 */

        /* 3番目の珠 (値3) */
        .bead-earth-3 { top: calc(25% + 14px + 5% + 28% + 2%); } /* OFF */
        .bead-earth-3.active { top: calc(25% + 14px + 0px + 28%); } /* ON */

        /* 4番目の珠 (値4) */
        .bead-earth-4 { top: calc(25% + 14px + 5% + 42% + 3%); } /* OFF */
        .bead-earth-4.active { top: calc(25% + 14px + 0px + 42%); } /* ON */

        /* ※上記は重なりを防ぐため、JSで珠ごとにクラスを割り当てて制御します */


        /* 花丸アニメーション */
        @keyframes drawFlower {
            0% { stroke-dasharray: 0 1000; opacity: 0; }
            100% { stroke-dasharray: 1000 0; opacity: 1; }
        }
        .hanamaru {
            position: absolute;
            top: 50%; left: 50%;
            transform: translate(-50%, -50%) rotate(-10deg);
            width: 200px; height: 200px;
            pointer-events: none;
            display: none;
            z-index: 50;
        }
        .hanamaru.show { display: block; }
        .hanamaru path {
            fill: none; stroke: #ff6b6b; stroke-width: 8;
            stroke-linecap: round; stroke-linejoin: round;
            animation: drawFlower 1s ease-out forwards;
        }
    </style>
</head>
<body class="h-screen flex flex-col items-center justify-center overflow-hidden bg-stone-100">

    <!-- PC向けに幅を max-w-6xl まで拡大し、余白を調整 -->
    <div class="w-full max-w-6xl px-4 flex flex-col gap-4 h-full py-4 justify-between">
        
        <!-- 黒板エリア -->
        <div class="wood-frame p-3 shrink-0 shadow-xl">
            <!-- 高さをPC向けに md:h-64 へ拡大 -->
            <div class="chalkboard h-48 md:h-64 rounded-lg flex flex-col items-center justify-center relative overflow-hidden">
                
                <!-- 文字サイズをPC向けに md:text-9xl へ巨大化 -->
                <div id="problem-text" class="text-6xl md:text-9xl font-bold tracking-widest chalk-text mt-2">
                    1 + 2
                </div>

                <!-- メッセージも大きく -->
                <div id="message" class="text-xl md:text-4xl mt-4 text-yellow-100 opacity-80 h-12 font-bold flex items-center justify-center">
                    そろばん を はじいてね
                </div>

                <div class="absolute bottom-4 right-6 flex gap-3 opacity-90 scale-125 origin-bottom-right">
                    <div class="w-8 h-2 bg-yellow-200 rounded transform rotate-3 shadow"></div>
                    <div class="w-6 h-2 bg-red-200 rounded transform -rotate-6 shadow"></div>
                    <div class="w-12 h-4 bg-blue-900 rounded border border-gray-600 shadow-md"></div>
                </div>

                <svg class="hanamaru" id="hanamaru-svg" viewBox="0 0 200 200">
                    <path d="M40,100 A60,60 0 1,1 160,100 A60,60 0 1,1 40,100 M20,100 L180,100 M100,20 L100,180" />
                </svg>
            </div>
        </div>

        <!-- コントロールボタン -->
        <div class="flex justify-center gap-4 md:gap-8 shrink-0 py-2">
            <button onclick="resetAbacus()" class="bg-gray-600 hover:bg-gray-700 text-white font-bold py-3 px-6 md:px-10 rounded-full border-b-4 border-gray-800 active:border-b-0 active:translate-y-1 shadow-lg transition text-lg md:text-2xl transform hover:scale-105">
                やりなおす
            </button>
            <button onclick="checkAnswer()" class="bg-red-500 hover:bg-red-600 text-white font-bold py-3 px-8 md:px-12 rounded-full border-b-4 border-red-700 active:border-b-0 active:translate-y-1 shadow-lg transition text-xl md:text-3xl transform hover:scale-105">
                こたえあわせ
            </button>
            <button onclick="nextProblem()" id="next-btn" class="hidden bg-blue-500 hover:bg-blue-600 text-white font-bold py-3 px-8 md:px-12 rounded-full border-b-4 border-blue-700 active:border-b-0 active:translate-y-1 shadow-lg transition text-xl md:text-3xl transform hover:scale-105">
                つぎのもんだい
            </button>
        </div>

        <!-- そろばんエリア -->
        <div class="wood-frame p-4 flex-grow relative flex items-center justify-center bg-gray-300 overflow-hidden min-h-[400px] shadow-2xl">
            <!-- そろばん本体 -->
            <div class="bg-black p-2 w-full h-full shadow-inner rounded relative flex justify-center gap-2" id="abacus-container">
                <!-- JSで桁を生成 -->
            </div>
        </div>

    </div>

    <script>
        const COLUMN_COUNT = 7;
        let currentProblemResult = 0;
        let columnsState = []; // {heaven: 0 or 1, earth: 0~4}

        function init() {
            createAbacus();
            generateProblem();
        }

        // そろばん生成
        function createAbacus() {
            const container = document.getElementById('abacus-container');
            container.innerHTML = '';
            columnsState = [];

            for (let i = 0; i < COLUMN_COUNT; i++) {
                columnsState.push({ heaven: 0, earth: 0 });

                // カラム (1桁)
                const col = document.createElement('div');
                col.className = 'soroban-column flex-1 max-w-[150px]'; // 最大幅を大きく

                // 梁 (Beam)
                const beam = document.createElement('div');
                beam.className = 'beam';
                // 定位点（3桁ごと）
                const centerIdx = Math.floor(COLUMN_COUNT / 2);
                if (i === centerIdx || i === centerIdx - 3 || i === centerIdx + 3) {
                    if (i >= 0 && i < COLUMN_COUNT) {
                        const dot = document.createElement('div');
                        dot.className = 'dot';
                        beam.appendChild(dot);
                    }
                }
                col.appendChild(beam);

                // --- 天の珠 (Heaven) ---
                const heavenBead = document.createElement('div');
                heavenBead.className = 'bead bead-heaven';
                heavenBead.id = `c${i}-h`;
                heavenBead.onclick = () => toggleHeaven(i);
                col.appendChild(heavenBead);

                // --- 地の珠 (Earth) × 4 ---
                // ID: c{col}-e{1~4}  (1が一番上)
                for (let j = 1; j <= 4; j++) {
                    const earthBead = document.createElement('div');
                    earthBead.className = `bead bead-earth-${j}`; // クラスで位置制御
                    earthBead.id = `c${i}-e${j}`;
                    earthBead.onclick = () => toggleEarth(i, j);
                    col.appendChild(earthBead);
                }

                container.appendChild(col);
            }
        }

        function toggleHeaven(colIdx) {
            columnsState[colIdx].heaven = columnsState[colIdx].heaven === 0 ? 1 : 0;
            updateVisuals(colIdx);
        }

        // 地の珠ロジック: クリックした珠が「ON（梁側）」になるようにする
        // 例: 値が0のとき、2番目(e2)をクリック -> 値を2にする（e1, e2がON）
        // 例: 値が2のとき、2番目(e2)をクリック -> 値を0にする（OFF）? または 1にする?
        // 子供向けUIとして、「そこまで動かす」のが直感的
        // 現在値2 (e1, e2がON)。 e3をクリック -> 値3 (e3までON)
        // 現在値3 (e1, e2, e3がON)。 e2をクリック -> 値2 (e2までON、e3はOFF)
        // 現在値2。 e2をクリック -> 値0 (OFF) にするトグル動作
        function toggleEarth(colIdx, beadNum) {
            const currentVal = columnsState[colIdx].earth;
            
            if (currentVal === beadNum) {
                // 同じ場所を押したら解除 (0に戻すのが一番わかりやすい、または1つ減らす？)
                // 一般的には「払う」動作なので、その珠を無効にする＝beadNum-1 になるのが自然だが、
                // タッチ操作では「0にする」方が誤操作リカバリしやすいこともある。
                // ここでは「その珠をOFFにする」= beadNum - 1 にします。
                // 例: 3が入っていて、3番目の珠を弾くと2になる。
                columnsState[colIdx].earth = beadNum - 1;
            } else {
                // その位置まで有効にする
                columnsState[colIdx].earth = beadNum;
            }
            updateVisuals(colIdx);
        }

        function updateVisuals(colIdx) {
            const state = columnsState[colIdx];

            // 天
            const h = document.getElementById(`c${colIdx}-h`);
            if (state.heaven === 1) h.classList.add('active');
            else h.classList.remove('active');

            // 地
            for (let j = 1; j <= 4; j++) {
                const e = document.getElementById(`c${colIdx}-e${j}`);
                // 値が j 以上なら、その珠はON（上に移動）
                if (state.earth >= j) {
                    e.classList.add('active');
                } else {
                    e.classList.remove('active');
                }
            }
        }

        function getAbacusValue() {
            // カラム数7の場合、index 3が一の位と仮定
            const centerIdx = Math.floor(COLUMN_COUNT / 2);
            // 実際には右端を一の位にするか、真ん中を一の位にするか。
            // 16級（簡単）なので、右端を一の位として計算したほうが混乱がないかも？
            // ただし、画像や一般的な練習では定位点（真ん中）を一の位にすることが多い。
            // ここでは「入力されている数字全体」を読み取ります。
            
            let total = 0;
            let currentPlaceVal = 1;

            // 真ん中(centerIdx)を一の位として、左へ向かって計算
            for (let i = centerIdx; i >= 0; i--) {
                const val = columnsState[i].earth + (columnsState[i].heaven * 5);
                total += val * currentPlaceVal;
                currentPlaceVal *= 10;
            }
            
            // 真ん中より右側に誤って入力していた場合の処理は？ -> 無視するか、小数として扱うか。
            // 今回はシンプルに「真ん中より左」のみ判定対象とします。
            
            return total;
        }

        function generateProblem() {
            document.getElementById('hanamaru-svg').classList.remove('show');
            document.getElementById('message').innerText = "そろばん を はじいてね";
            // メッセージスタイルもPC向けに大きく調整
            document.getElementById('message').className = "text-xl md:text-4xl mt-4 text-yellow-100 opacity-80 h-12 font-bold flex items-center justify-center";
            document.getElementById('next-btn').classList.add('hidden');

            const mode = Math.random();
            let num1, num2, num3, text;
            
            // 16級レベル: 1桁の見取り算 (3口)
            // 答えが負にならない、繰り上がりなし（5の合成・分解はあるかも）
            
            // パターンA: 2口 (簡単)
            if (mode > 0.7) {
                num1 = rand(1, 8);
                // 足して9以下
                let max2 = 9 - num1;
                num2 = rand(1, max2);
                text = `${num1} + ${num2}`;
                currentProblemResult = num1 + num2;
            } 
            // パターンB: 3口 (1 + 2 - 1 など)
            else {
                num1 = rand(1, 8);
                // 2つ目
                let max2 = 9 - num1;
                num2 = rand(1, max2);
                // 3つ目 (引く)
                let current = num1 + num2;
                num3 = rand(1, current); // 全部引くこともありうる
                
                text = `${num1} + ${num2} - ${num3}`;
                currentProblemResult = current - num3;
            }

            document.getElementById('problem-text').innerText = text;
        }

        function rand(min, max) {
            if (max < min) return min;
            return Math.floor(Math.random() * (max - min + 1)) + min;
        }

        function resetAbacus() {
            columnsState = columnsState.map(() => ({ heaven: 0, earth: 0 }));
            for(let i=0; i<COLUMN_COUNT; i++) updateVisuals(i);
        }

        function checkAnswer() {
            const userVal = getAbacusValue();
            const msg = document.getElementById('message');
            
            if (userVal === currentProblemResult) {
                msg.innerText = "せいかい！すごい！";
                // 正解メッセージも大きく
                msg.className = "text-xl md:text-4xl mt-4 text-red-300 font-bold h-12 flex items-center justify-center";
                document.getElementById('hanamaru-svg').classList.add('show');
                document.getElementById('next-btn').classList.remove('hidden');
                
                // 真ん中より右に珠がある場合、注意を促す？（今回は省略）
            } else {
                msg.innerText = `おしい！ いまのすうじは ${userVal} だよ`;
                // 不正解メッセージも大きく
                msg.className = "text-xl md:text-4xl mt-4 text-blue-200 font-bold h-12 flex items-center justify-center";
            }
        }

        function nextProblem() {
            resetAbacus();
            generateProblem();
        }

        // Init
        init();

    </script>
</body>
</html>
