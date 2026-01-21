<html lang="th" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>คณิตศาสตร์การเงิน ป.5</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;500;600;700&amp;display=swap" rel="stylesheet">
  <style>
    body {
      box-sizing: border-box;
      font-family: 'Kanit', sans-serif;
    }
    .coin {
      animation: bounce 2s infinite;
    }
    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }
    .sparkle {
      animation: sparkle 1.5s ease-in-out infinite;
    }
    @keyframes sparkle {
      0%, 100% { opacity: 1; transform: scale(1); }
      50% { opacity: 0.7; transform: scale(1.1); }
    }
    .slide-in {
      animation: slideIn 0.5s ease-out;
    }
    @keyframes slideIn {
      from { opacity: 0; transform: translateX(20px); }
      to { opacity: 1; transform: translateX(0); }
    }
    .pop {
      animation: pop 0.3s ease-out;
    }
    @keyframes pop {
      0% { transform: scale(0.8); }
      50% { transform: scale(1.1); }
      100% { transform: scale(1); }
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full">
  <div id="app" class="h-full overflow-auto" style="background: linear-gradient(135deg, #10b981 0%, #059669 50%, #34d399 100%);"><!-- หน้าหลัก -->
   <div id="home-screen" class="min-h-full p-4 md:p-8">
    <div class="max-w-4xl mx-auto"><!-- Header -->
     <div class="text-center mb-8">
      <div class="inline-block p-4 bg-white/20 backdrop-blur-sm rounded-full mb-4">
       <svg class="w-16 h-16 coin" viewbox="0 0 64 64"><circle cx="32" cy="32" r="28" fill="#FFD700" stroke="#FFA500" stroke-width="3" /> <circle cx="32" cy="32" r="22" fill="#FFEC8B" stroke="#FFD700" stroke-width="2" /> <text x="32" y="40" text-anchor="middle" font-size="24" font-weight="bold" fill="#B8860B">
         ฿
        </text>
       </svg>
      </div>
      <h1 id="app-title" class="text-3xl md:text-4xl font-bold text-white drop-shadow-lg mb-2">คณิตศาสตร์การเงิน ป.5</h1>
      <p id="welcome-msg" class="text-white/90 text-lg">เรียนรู้เรื่องเงินอย่างสนุกสนาน!</p>
      <div class="mt-4 inline-block bg-white/20 backdrop-blur-sm rounded-xl px-6 py-3">
       <p class="text-white/95 text-sm font-medium">👩‍🎓 ผู้สร้าง: เด็กหญิงสุนิสา แสงประดับ</p>
       <p class="text-white/90 text-xs">ชั้นประถมศึกษาปีที่ 5/5 สาย MEP</p>
      </div>
     </div><!-- เมนูหลัก -->
     <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-8"><!-- บทเรียน --> <button onclick="showLessons()" class="group bg-white/95 backdrop-blur-sm rounded-2xl p-6 shadow-xl hover:shadow-2xl transform hover:scale-105 transition-all duration-300 text-left">
       <div class="flex items-center gap-4">
        <div class="w-16 h-16 bg-gradient-to-br from-blue-400 to-blue-600 rounded-xl flex items-center justify-center text-3xl shadow-lg group-hover:scale-110 transition-transform">
         📚
        </div>
        <div>
         <h3 class="text-xl font-bold text-gray-800">บทเรียน</h3>
         <p class="text-gray-600 text-sm">เรียนรู้เรื่องเงินและการคำนวณ</p>
        </div>
       </div></button> <!-- แบบฝึกหัด --> <button onclick="showPractice()" class="group bg-white/95 backdrop-blur-sm rounded-2xl p-6 shadow-xl hover:shadow-2xl transform hover:scale-105 transition-all duration-300 text-left">
       <div class="flex items-center gap-4">
        <div class="w-16 h-16 bg-gradient-to-br from-green-400 to-green-600 rounded-xl flex items-center justify-center text-3xl shadow-lg group-hover:scale-110 transition-transform">
         ✏️
        </div>
        <div>
         <h3 class="text-xl font-bold text-gray-800">แบบฝึกหัด</h3>
         <p class="text-gray-600 text-sm">ฝึกคำนวณเงินแบบโต้ตอบ</p>
        </div>
       </div></button> <!-- เกมส์ --> <button onclick="showGames()" class="group bg-white/95 backdrop-blur-sm rounded-2xl p-6 shadow-xl hover:shadow-2xl transform hover:scale-105 transition-all duration-300 text-left">
       <div class="flex items-center gap-4">
        <div class="w-16 h-16 bg-gradient-to-br from-yellow-400 to-orange-500 rounded-xl flex items-center justify-center text-3xl shadow-lg group-hover:scale-110 transition-transform">
         🎮
        </div>
        <div>
         <h3 class="text-xl font-bold text-gray-800">เกมส์</h3>
         <p class="text-gray-600 text-sm">เล่นเกมส์คิดเงินสนุกๆ</p>
        </div>
       </div></button> <!-- คะแนน --> <button onclick="showScore()" class="group bg-white/95 backdrop-blur-sm rounded-2xl p-6 shadow-xl hover:shadow-2xl transform hover:scale-105 transition-all duration-300 text-left">
       <div class="flex items-center gap-4">
        <div class="w-16 h-16 bg-gradient-to-br from-purple-400 to-purple-600 rounded-xl flex items-center justify-center text-3xl shadow-lg group-hover:scale-110 transition-transform">
         🏆
        </div>
        <div>
         <h3 class="text-xl font-bold text-gray-800">คะแนนของฉัน</h3>
         <p class="text-gray-600 text-sm">ดูความก้าวหน้าของตัวเอง</p>
        </div>
       </div></button>
     </div><!-- ข้อมูลเหรียญและธนบัตร -->
     <div class="bg-white/95 backdrop-blur-sm rounded-2xl p-6 shadow-xl">
      <h3 class="text-xl font-bold text-gray-800 mb-4 flex items-center gap-2"><span>💰</span> เหรียญและธนบัตรไทย</h3>
      <div class="grid grid-cols-3 md:grid-cols-6 gap-3">
       <div class="text-center p-3 bg-gradient-to-br from-amber-100 to-amber-200 rounded-xl">
        <div class="text-2xl mb-1">
         🪙
        </div>
        <div class="text-xs font-medium text-amber-800">
         25 สต.
        </div>
       </div>
       <div class="text-center p-3 bg-gradient-to-br from-amber-100 to-amber-200 rounded-xl">
        <div class="text-2xl mb-1">
         🪙
        </div>
        <div class="text-xs font-medium text-amber-800">
         50 สต.
        </div>
       </div>
       <div class="text-center p-3 bg-gradient-to-br from-yellow-100 to-yellow-200 rounded-xl">
        <div class="text-2xl mb-1">
         🥇
        </div>
        <div class="text-xs font-medium text-yellow-800">
         1 บาท
        </div>
       </div>
       <div class="text-center p-3 bg-gradient-to-br from-yellow-100 to-yellow-200 rounded-xl">
        <div class="text-2xl mb-1">
         🥇
        </div>
        <div class="text-xs font-medium text-yellow-800">
         2 บาท
        </div>
       </div>
       <div class="text-center p-3 bg-gradient-to-br from-yellow-100 to-yellow-200 rounded-xl">
        <div class="text-2xl mb-1">
         🥇
        </div>
        <div class="text-xs font-medium text-yellow-800">
         5 บาท
        </div>
       </div>
       <div class="text-center p-3 bg-gradient-to-br from-yellow-100 to-yellow-200 rounded-xl">
        <div class="text-2xl mb-1">
         🥇
        </div>
        <div class="text-xs font-medium text-yellow-800">
         10 บาท
        </div>
       </div>
      </div>
      <div class="grid grid-cols-2 md:grid-cols-5 gap-3 mt-3">
       <div class="text-center p-3 bg-gradient-to-br from-green-100 to-green-200 rounded-xl">
        <div class="text-2xl mb-1">
         💵
        </div>
        <div class="text-xs font-medium text-green-800">
         20 บาท
        </div>
       </div>
       <div class="text-center p-3 bg-gradient-to-br from-blue-100 to-blue-200 rounded-xl">
        <div class="text-2xl mb-1">
         💵
        </div>
        <div class="text-xs font-medium text-blue-800">
         50 บาท
        </div>
       </div>
       <div class="text-center p-3 bg-gradient-to-br from-red-100 to-red-200 rounded-xl">
        <div class="text-2xl mb-1">
         💵
        </div>
        <div class="text-xs font-medium text-red-800">
         100 บาท
        </div>
       </div>
       <div class="text-center p-3 bg-gradient-to-br from-purple-100 to-purple-200 rounded-xl">
        <div class="text-2xl mb-1">
         💵
        </div>
        <div class="text-xs font-medium text-purple-800">
         500 บาท
        </div>
       </div>
       <div class="text-center p-3 bg-gradient-to-br from-gray-100 to-gray-200 rounded-xl">
        <div class="text-2xl mb-1">
         💵
        </div>
        <div class="text-xs font-medium text-gray-800">
         1,000 บาท
        </div>
       </div>
      </div>
     </div>
    </div>
   </div><!-- หน้าบทเรียน -->
   <div id="lessons-screen" class="min-h-full p-4 md:p-8 hidden">
    <div class="max-w-4xl mx-auto"><button onclick="goHome()" class="mb-4 flex items-center gap-2 text-white hover:text-white/80 transition-colors">
      <svg class="w-6 h-6" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
      </svg><span class="font-medium">กลับหน้าหลัก</span> </button>
     <h2 class="text-2xl md:text-3xl font-bold text-white mb-6 flex items-center gap-3"><span class="text-4xl">📚</span> บทเรียน</h2>
     <div class="space-y-4" id="lessons-list"><!-- บทเรียนที่ 1 -->
      <div class="bg-white/95 backdrop-blur-sm rounded-2xl p-6 shadow-xl slide-in">
       <div class="flex items-start gap-4">
        <div class="w-12 h-12 bg-gradient-to-br from-blue-400 to-blue-600 rounded-xl flex items-center justify-center text-xl text-white font-bold shadow-lg">
         1
        </div>
        <div class="flex-1">
         <h3 class="text-lg font-bold text-gray-800 mb-2">การนับเงินและแลกเปลี่ยนเหรียญ</h3>
         <p class="text-gray-600 text-sm mb-3">เรียนรู้การนับเงินและแลกเปลี่ยนเหรียญต่างๆ</p>
         <div class="bg-blue-50 rounded-xl p-4 text-sm text-gray-700">
          <p class="font-medium mb-2">📝 เนื้อหาสำคัญ:</p>
          <ul class="space-y-1 ml-4">
           <li>• 100 สตางค์ = 1 บาท</li>
           <li>• เหรียญ 25 สตางค์ 4 เหรียญ = 1 บาท</li>
           <li>• เหรียญ 50 สตางค์ 2 เหรียญ = 1 บาท</li>
           <li>• เหรียญ 5 บาท 2 เหรียญ = 10 บาท</li>
          </ul>
         </div>
        </div>
       </div>
      </div><!-- บทเรียนที่ 2 -->
      <div class="bg-white/95 backdrop-blur-sm rounded-2xl p-6 shadow-xl slide-in" style="animation-delay: 0.1s">
       <div class="flex items-start gap-4">
        <div class="w-12 h-12 bg-gradient-to-br from-green-400 to-green-600 rounded-xl flex items-center justify-center text-xl text-white font-bold shadow-lg">
         2
        </div>
        <div class="flex-1">
         <h3 class="text-lg font-bold text-gray-800 mb-2">การบวกและลบเงิน</h3>
         <p class="text-gray-600 text-sm mb-3">ฝึกคำนวณเงินรวมและเงินทอน</p>
         <div class="bg-green-50 rounded-xl p-4 text-sm text-gray-700">
          <p class="font-medium mb-2">📝 ตัวอย่าง:</p>
          <ul class="space-y-1 ml-4">
           <li>• ซื้อ��อง 45 บาท + 30 บาท = 75 บาท</li>
           <li>• จ่าย 100 บาท ซื้อของ 67 บาท ทอน 33 บาท</li>
           <li>• รวมเงิน 50.50 + 25.25 = 75.75 บาท</li>
          </ul>
         </div>
        </div>
       </div>
      </div><!-- บทเรียนที่ 3 -->
      <div class="bg-white/95 backdrop-blur-sm rounded-2xl p-6 shadow-xl slide-in" style="animation-delay: 0.2s">
       <div class="flex items-start gap-4">
        <div class="w-12 h-12 bg-gradient-to-br from-yellow-400 to-orange-500 rounded-xl flex items-center justify-center text-xl text-white font-bold shadow-lg">
         3
        </div>
        <div class="flex-1">
         <h3 class="text-lg font-bold text-gray-800 mb-2">การคูณและหารเงิน</h3>
         <p class="text-gray-600 text-sm mb-3">คำนวณราคาสินค้าหลายชิ้นและแบ่งเงิน</p>
         <div class="bg-yellow-50 rounded-xl p-4 text-sm text-gray-700">
          <p class="font-medium mb-2">📝 ตัวอย่าง:</p>
          <ul class="space-y-1 ml-4">
           <li>• ขนม 15 บาท ซื้อ 4 ซอง = 15 × 4 = 60 บาท</li>
           <li>• มีเงิน 200 บาท แบ่ง 4 คน = 200 ÷ 4 = 50 บาท</li>
           <li>• ดินสอแท่งละ 8 บาท มี 100 บาท ซื้อได้ 12 แท่ง</li>
          </ul>
         </div>
        </div>
       </div>
      </div><!-- บทเรียนที่ 4 -->
      <div class="bg-white/95 backdrop-blur-sm rounded-2xl p-6 shadow-xl slide-in" style="animation-delay: 0.3s">
       <div class="flex items-start gap-4">
        <div class="w-12 h-12 bg-gradient-to-br from-purple-400 to-purple-600 rounded-xl flex items-center justify-center text-xl text-white font-bold shadow-lg">
         4
        </div>
        <div class="flex-1">
         <h3 class="text-lg font-bold text-gray-800 mb-2">โจทย์ปัญหาเกี่ยวกับเงิน</h3>
         <p class="text-gray-600 text-sm mb-3">แก้โจทย์ปัญหาในชีวิตประจำวัน</p>
         <div class="bg-purple-50 rounded-xl p-4 text-sm text-gray-700">
          <p class="font-medium mb-2">📝 ตัวอย่างโจทย์:</p>
          <p class="ml-4">แม่ให้เงินค่าขนม 50 บาท น้องซื้อนม 18 บาท และขนมปัง 12 บาท น้องเหลือเงินกี่บาท?</p>
          <p class="ml-4 mt-2 text-purple-600 font-medium">คำตอบ: 50 - 18 - 12 = 20 บาท</p>
         </div>
        </div>
       </div>
      </div>
     </div>
    </div>
   </div><!-- หน้าแบบฝึกหัด -->
   <div id="practice-screen" class="min-h-full p-4 md:p-8 hidden">
    <div class="max-w-2xl mx-auto"><button onclick="goHome()" class="mb-4 flex items-center gap-2 text-white hover:text-white/80 transition-colors">
      <svg class="w-6 h-6" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
      </svg><span class="font-medium">กลับหน้าหลัก</span> </button>
     <h2 class="text-2xl md:text-3xl font-bold text-white mb-6 flex items-center gap-3"><span class="text-4xl">✏️</span> แบบฝึกหัด</h2>
     <div class="bg-white/95 backdrop-blur-sm rounded-2xl p-6 shadow-xl">
      <div class="flex justify-between items-center mb-4"><span class="text-sm font-medium text-gray-600">ข้อ <span id="practice-current">1</span>/10</span> <span class="text-sm font-medium text-green-600">คะแนน: <span id="practice-score">0</span></span>
      </div>
      <div class="w-full bg-gray-200 rounded-full h-2 mb-6">
       <div id="practice-progress" class="bg-gradient-to-r from-green-400 to-green-600 h-2 rounded-full transition-all duration-500" style="width: 10%"></div>
      </div>
      <div id="practice-question" class="text-center py-8">
       <p class="text-gray-600 mb-2">โจทย์</p>
       <p id="practice-q-text" class="text-2xl font-bold text-gray-800 mb-6">ซื้อขนม 25 บาท กับนม 18 บาท ต้องจ่ายเงินเท่าไร?</p>
       <div class="flex items-center justify-center gap-2 mb-6"><input type="number" id="practice-answer" class="w-32 px-4 py-3 text-xl text-center border-2 border-gray-300 rounded-xl focus:border-purple-500 focus:outline-none" placeholder="??"> <span class="text-xl font-medium text-gray-600">บาท</span>
       </div><button onclick="checkPracticeAnswer()" class="px-8 py-3 bg-gradient-to-r from-emerald-500 to-emerald-700 text-white font-bold rounded-xl shadow-lg hover:shadow-xl transform hover:scale-105 transition-all"> ตรวจคำตอบ </button>
      </div>
      <div id="practice-feedback" class="hidden text-center py-4">
       <div id="feedback-content"></div><button onclick="nextPractice()" class="mt-4 px-6 py-2 bg-blue-500 text-white font-medium rounded-lg hover:bg-blue-600 transition-colors"> ข้อถัดไป </button>
      </div>
     </div>
    </div>
   </div><!-- หน้าเกมส์ -->
   <div id="games-screen" class="min-h-full p-4 md:p-8 hidden">
    <div class="max-w-2xl mx-auto"><button onclick="goHome()" class="mb-4 flex items-center gap-2 text-white hover:text-white/80 transition-colors">
      <svg class="w-6 h-6" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
      </svg><span class="font-medium">กลับหน้าหลัก</span> </button>
     <h2 class="text-2xl md:text-3xl font-bold text-white mb-6 flex items-center gap-3"><span class="text-4xl">🎮</span> เกมส์คิดเงินทอน</h2>
     <div class="bg-white/95 backdrop-blur-sm rounded-2xl p-6 shadow-xl">
      <div class="flex justify-between items-center mb-4"><span class="text-sm font-medium text-gray-600">⏱️ เวลา: <span id="game-time">60</span> วินาที</span> <span class="text-sm font-medium text-yellow-600">⭐ คะแนน: <span id="game-score">0</span></span>
      </div>
      <div id="game-start" class="text-center py-8">
       <div class="text-6xl mb-4">
        🛒
       </div>
       <h3 class="text-xl font-bold text-gray-800 mb-2">เกมส์ร้านค้า</h3>
       <p class="text-gray-600 mb-6">คำนวณเงินทอนให้ถูกต้องภายในเวลา!</p><button onclick="startGame()" class="px-8 py-4 bg-gradient-to-r from-yellow-400 to-orange-500 text-white font-bold text-xl rounded-xl shadow-lg hover:shadow-xl transform hover:scale-105 transition-all"> 🎮 เริ่มเล่น! </button>
      </div>
      <div id="game-play" class="hidden">
       <div class="text-center mb-6 p-4 bg-gradient-to-r from-blue-50 to-purple-50 rounded-xl">
        <p class="text-gray-600 mb-1">ลูกค้าซื้อของราคา</p>
        <p class="text-3xl font-bold text-purple-600" id="game-price">35 บาท</p>
        <p class="text-gray-600 mt-2">จ่ายมา</p>
        <p class="text-3xl font-bold text-green-600" id="game-paid">50 บาท</p>
       </div>
       <p class="text-center text-gray-700 font-medium mb-4">ต้องทอนเท่าไร?</p>
       <div id="game-choices" class="grid grid-cols-2 gap-3"><!-- Choices will be inserted here -->
       </div>
      </div>
      <div id="game-over" class="hidden text-center py-8">
       <div class="text-6xl mb-4" id="game-result-emoji">
        🎉
       </div>
       <h3 class="text-2xl font-bold text-gray-800 mb-2">หมดเวลา!</h3>
       <p class="text-gray-600 mb-2">คะแนนที่ได้: <span class="text-2xl font-bold text-yellow-600" id="final-score">0</span></p>
       <p class="text-gray-600 mb-6">ตอบถูก: <span id="correct-count">0</span> ข้อ</p><button onclick="startGame()" class="px-8 py-3 bg-gradient-to-r from-green-400 to-green-600 text-white font-bold rounded-xl shadow-lg hover:shadow-xl transform hover:scale-105 transition-all"> 🔄 เล่นอีกครั้ง </button>
      </div>
     </div>
    </div>
   </div><!-- หน้าคะแน��� -->
   <div id="score-screen" class="min-h-full p-4 md:p-8 hidden">
    <div class="max-w-2xl mx-auto"><button onclick="goHome()" class="mb-4 flex items-center gap-2 text-white hover:text-white/80 transition-colors">
      <svg class="w-6 h-6" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
      </svg><span class="font-medium">กลับหน้าหลัก</span> </button>
     <h2 class="text-2xl md:text-3xl font-bold text-white mb-6 flex items-center gap-3"><span class="text-4xl">🏆</span> คะแนนของฉัน</h2>
     <div class="bg-white/95 backdrop-blur-sm rounded-2xl p-6 shadow-xl mb-4">
      <div class="text-center">
       <div class="inline-block p-4 bg-gradient-to-br from-yellow-100 to-yellow-200 rounded-full mb-4"><span class="text-5xl">🏅</span>
       </div>
       <h3 class="text-2xl font-bold text-gray-800 mb-1">คะแนนรวม</h3>
       <p class="text-5xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-yellow-500 to-orange-500" id="total-score">0</p>
       <p class="text-gray-600">คะแนน</p>
      </div>
     </div>
     <div class="grid grid-cols-2 gap-4 mb-4">
      <div class="bg-white/95 backdrop-blur-sm rounded-2xl p-4 shadow-xl text-center">
       <div class="text-3xl mb-2">
        ✏️
       </div>
       <p class="text-gray-600 text-sm">แบบฝึกหัด</p>
       <p class="text-2xl font-bold text-green-600" id="practice-total">0</p>
      </div>
      <div class="bg-white/95 backdrop-blur-sm rounded-2xl p-4 shadow-xl text-center">
       <div class="text-3xl mb-2">
        🎮
       </div>
       <p class="text-gray-600 text-sm">เกมส์</p>
       <p class="text-2xl font-bold text-yellow-600" id="game-total">0</p>
      </div>
     </div>
     <div class="bg-white/95 backdrop-blur-sm rounded-2xl p-6 shadow-xl">
      <h3 class="font-bold text-gray-800 mb-4 flex items-center gap-2"><span>📊</span> สถิติการเล่น</h3>
      <div class="space-y-3">
       <div class="flex justify-between items-center"><span class="text-gray-600">แบบฝึกหัดที่ทำ</span> <span class="font-bold text-gray-800" id="practice-done">0 ชุด</span>
       </div>
       <div class="flex justify-between items-center"><span class="text-gray-600">เกมส์ที่เล่น</span> <span class="font-bold text-gray-800" id="games-played">0 ครั้ง</span>
       </div>
       <div class="flex justify-between items-center"><span class="text-gray-600">คะแนนสูงสุด (เกมส์)</span> <span class="font-bold text-yellow-600" id="high-score">0</span>
       </div>
      </div>
     </div><button onclick="resetScore()" class="mt-4 w-full py-3 bg-red-100 text-red-600 font-medium rounded-xl hover:bg-red-200 transition-colors"> 🔄 รีเซ็ตคะแนน </button>
    </div>
   </div>
  </div>
  <script>
    // Default configuration
    const defaultConfig = {
      app_title: 'คณิตศาสตร์การเงิน ป.5',
      welcome_message: 'เรียนรู้เรื่องเงินอย่างสนุกสนาน!',
      background_color: '#10b981',
      surface_color: '#ffffff',
      text_color: '#1f2937',
      primary_action_color: '#059669',
      secondary_action_color: '#34d399'
    };

    let config = { ...defaultConfig };

    // Score tracking
    let scores = {
      practice: 0,
      game: 0,
      practiceDone: 0,
      gamesPlayed: 0,
      highScore: 0
    };

    // Practice state
    let practiceQuestions = [];
    let currentPractice = 0;
    let practiceScore = 0;

    // Game state
    let gameTimer = null;
    let gameTime = 60;
    let gameScore = 0;
    let correctAnswers = 0;

    // Generate practice questions
    function generatePracticeQuestions() {
      practiceQuestions = [
        { q: 'ซื้อขนม 25 บาท กับนม 18 บาท ต้องจ่ายเงินเท่าไร?', a: 43 },
        { q: 'จ่ายเงิน 100 บาท ซื้อของ 67 บาท ได้เงินทอนเท่าไร?', a: 33 },
        { q: 'ดินสอแท่งละ 8 บาท ซื้อ 5 แท่ง ราคาเท่าไร?', a: 40 },
        { q: 'มีเงิน 200 บาท แบ่งให้เพื่อน 4 คน คนละเท่าไร?', a: 50 },
        { q: 'ซื้อหนังสือ 85 บาท จ่าย 100 บาท ได้ทอนเท่าไร?', a: 15 },
        { q: 'ขนมถุงละ 12 บาท ซื้อ 3 ถุง จ่ายเท่าไร?', a: 36 },
        { q: 'มีเงิน 150 บาท ซื้อของ 48 และ 37 บาท เหลือเท่าไร?', a: 65 },
        { q: 'น้ำ 15 บาท ขนมปัง 22 บาท รวมเท่าไร?', a: 37 },
        { q: 'มี 500 บาท ซื้อของ 275 บาท เหลือเท่าไร?', a: 225 },
        { q: 'ปากกาด้ามละ 15 บาท ซื้อ 4 ด้าม ราคาเท่าไร?', a: 60 }
      ];
    }

    // Navigation functions
    function goHome() {
      hideAllScreens();
      document.getElementById('home-screen').classList.remove('hidden');
    }

    function showLessons() {
      hideAllScreens();
      document.getElementById('lessons-screen').classList.remove('hidden');
    }

    function showPractice() {
      hideAllScreens();
      document.getElementById('practice-screen').classList.remove('hidden');
      resetPractice();
    }

    function showGames() {
      hideAllScreens();
      document.getElementById('games-screen').classList.remove('hidden');
      resetGame();
    }

    function showScore() {
      hideAllScreens();
      document.getElementById('score-screen').classList.remove('hidden');
      updateScoreDisplay();
    }

    function hideAllScreens() {
      document.getElementById('home-screen').classList.add('hidden');
      document.getElementById('lessons-screen').classList.add('hidden');
      document.getElementById('practice-screen').classList.add('hidden');
      document.getElementById('games-screen').classList.add('hidden');
      document.getElementById('score-screen').classList.add('hidden');
    }

    // Practice functions
    function resetPractice() {
      generatePracticeQuestions();
      currentPractice = 0;
      practiceScore = 0;
      document.getElementById('practice-score').textContent = '0';
      document.getElementById('practice-feedback').classList.add('hidden');
      document.getElementById('practice-question').classList.remove('hidden');
      showPracticeQuestion();
    }

    function showPracticeQuestion() {
      const q = practiceQuestions[currentPractice];
      document.getElementById('practice-current').textContent = currentPractice + 1;
      document.getElementById('practice-q-text').textContent = q.q;
      document.getElementById('practice-answer').value = '';
      document.getElementById('practice-progress').style.width = ((currentPractice + 1) * 10) + '%';
    }

    function checkPracticeAnswer() {
      const answer = parseInt(document.getElementById('practice-answer').value);
      const correct = practiceQuestions[currentPractice].a;
      const feedback = document.getElementById('feedback-content');
      
      document.getElementById('practice-question').classList.add('hidden');
      document.getElementById('practice-feedback').classList.remove('hidden');

      if (answer === correct) {
        practiceScore += 10;
        document.getElementById('practice-score').textContent = practiceScore;
        feedback.innerHTML = `
          <div class="text-6xl mb-2 pop">🎉</div>
          <p class="text-2xl font-bold text-green-600">ถูกต้อง!</p>
          <p class="text-gray-600">+10 คะแนน</p>
        `;
      } else {
        feedback.innerHTML = `
          <div class="text-6xl mb-2">💭</div>
          <p class="text-2xl font-bold text-red-500">ไม่ถูกต้อง</p>
          <p class="text-gray-600">คำตอบที่ถูกคือ <span class="font-bold text-green-600">${correct} บาท</span></p>
        `;
      }
    }

    function nextPractice() {
      currentPractice++;
      if (currentPractice >= 10) {
        scores.practice += practiceScore;
        scores.practiceDone++;
        saveScores();
        
        document.getElementById('feedback-content').innerHTML = `
          <div class="text-6xl mb-2">🏆</div>
          <p class="text-2xl font-bold text-purple-600">จบแบบฝึกหัด!</p>
          <p class="text-gray-600 mb-2">คุณได้ <span class="font-bold text-green-600">${practiceScore}</span> คะแนน</p>
        `;
        document.querySelector('#practice-feedback button').textContent = 'เริ่มใหม่';
        document.querySelector('#practice-feedback button').onclick = resetPractice;
      } else {
        document.getElementById('practice-feedback').classList.add('hidden');
        document.getElementById('practice-question').classList.remove('hidden');
        showPracticeQuestion();
      }
    }

    // Game functions
    function resetGame() {
      if (gameTimer) clearInterval(gameTimer);
      document.getElementById('game-start').classList.remove('hidden');
      document.getElementById('game-play').classList.add('hidden');
      document.getElementById('game-over').classList.add('hidden');
      gameTime = 60;
      gameScore = 0;
      correctAnswers = 0;
      document.getElementById('game-time').textContent = '60';
      document.getElementById('game-score').textContent = '0';
    }

    function startGame() {
      document.getElementById('game-start').classList.add('hidden');
      document.getElementById('game-over').classList.add('hidden');
      document.getElementById('game-play').classList.remove('hidden');
      
      gameTime = 60;
      gameScore = 0;
      correctAnswers = 0;
      document.getElementById('game-score').textContent = '0';
      
      generateGameQuestion();
      
      gameTimer = setInterval(() => {
        gameTime--;
        document.getElementById('game-time').textContent = gameTime;
        if (gameTime <= 0) {
          endGame();
        }
      }, 1000);
    }

    function generateGameQuestion() {
      const prices = [15, 20, 25, 28, 32, 35, 38, 42, 45, 48, 55, 63, 67, 72, 78, 85];
      const payments = [50, 100, 200, 500];
      
      const price = prices[Math.floor(Math.random() * prices.length)];
      let paid = payments.find(p => p > price);
      if (!paid) paid = 500;
      
      const correct = paid - price;
      
      document.getElementById('game-price').textContent = price + ' บาท';
      document.getElementById('game-paid').textContent = paid + ' บาท';
      
      // Generate choices
      const choices = [correct];
      while (choices.length < 4) {
        const wrong = correct + (Math.random() > 0.5 ? 1 : -1) * (Math.floor(Math.random() * 20) + 1);
        if (wrong > 0 && !choices.includes(wrong)) {
          choices.push(wrong);
        }
      }
      
      // Shuffle choices
      choices.sort(() => Math.random() - 0.5);
      
      const choicesDiv = document.getElementById('game-choices');
      choicesDiv.innerHTML = choices.map(c => `
        <button onclick="checkGameAnswer(${c}, ${correct})" class="p-4 bg-gradient-to-r from-blue-100 to-purple-100 text-xl font-bold text-gray-800 rounded-xl hover:from-blue-200 hover:to-purple-200 transform hover:scale-105 transition-all">
          ${c} บาท
        </button>
      `).join('');
    }

    function checkGameAnswer(answer, correct) {
      if (answer === correct) {
        gameScore += 10;
        correctAnswers++;
        document.getElementById('game-score').textContent = gameScore;
      }
      generateGameQuestion();
    }

    function endGame() {
      clearInterval(gameTimer);
      
      scores.game += gameScore;
      scores.gamesPlayed++;
      if (gameScore > scores.highScore) {
        scores.highScore = gameScore;
      }
      saveScores();
      
      document.getElementById('game-play').classList.add('hidden');
      document.getElementById('game-over').classList.remove('hidden');
      document.getElementById('final-score').textContent = gameScore;
      document.getElementById('correct-count').textContent = correctAnswers;
      
      const emoji = document.getElementById('game-result-emoji');
      if (gameScore >= 100) {
        emoji.textContent = '🏆';
      } else if (gameScore >= 50) {
        emoji.textContent = '🎉';
      } else {
        emoji.textContent = '👍';
      }
    }

    // Score functions
    function saveScores() {
      try {
        localStorage.setItem('mathMoney_scores', JSON.stringify(scores));
      } catch (e) {}
    }

    function loadScores() {
      try {
        const saved = localStorage.getItem('mathMoney_scores');
        if (saved) {
          scores = JSON.parse(saved);
        }
      } catch (e) {}
    }

    function updateScoreDisplay() {
      document.getElementById('total-score').textContent = scores.practice + scores.game;
      document.getElementById('practice-total').textContent = scores.practice;
      document.getElementById('game-total').textContent = scores.game;
      document.getElementById('practice-done').textContent = scores.practiceDone + ' ชุด';
      document.getElementById('games-played').textContent = scores.gamesPlayed + ' ครั้ง';
      document.getElementById('high-score').textContent = scores.highScore;
    }

    function resetScore() {
      scores = { practice: 0, game: 0, practiceDone: 0, gamesPlayed: 0, highScore: 0 };
      saveScores();
      updateScoreDisplay();
    }

    // Config update function
    async function onConfigChange(newConfig) {
      config = { ...defaultConfig, ...newConfig };
      
      document.getElementById('app-title').textContent = config.app_title || defaultConfig.app_title;
      document.getElementById('welcome-msg').textContent = config.welcome_message || defaultConfig.welcome_message;
    }

    // Initialize
    loadScores();
    generatePracticeQuestions();

    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange,
        mapToCapabilities: (cfg) => ({
          recolorables: [
            {
              get: () => cfg.background_color || defaultConfig.background_color,
              set: (v) => { cfg.background_color = v; window.elementSdk.setConfig({ background_color: v }); }
            },
            {
              get: () => cfg.surface_color || defaultConfig.surface_color,
              set: (v) => { cfg.surface_color = v; window.elementSdk.setConfig({ surface_color: v }); }
            },
            {
              get: () => cfg.text_color || defaultConfig.text_color,
              set: (v) => { cfg.text_color = v; window.elementSdk.setConfig({ text_color: v }); }
            },
            {
              get: () => cfg.primary_action_color || defaultConfig.primary_action_color,
              set: (v) => { cfg.primary_action_color = v; window.elementSdk.setConfig({ primary_action_color: v }); }
            },
            {
              get: () => cfg.secondary_action_color || defaultConfig.secondary_action_color,
              set: (v) => { cfg.secondary_action_color = v; window.elementSdk.setConfig({ secondary_action_color: v }); }
            }
          ],
          borderables: [],
          fontEditable: undefined,
          fontSizeable: undefined
        }),
        mapToEditPanelValues: (cfg) => new Map([
          ['app_title', cfg.app_title || defaultConfig.app_title],
          ['welcome_message', cfg.welcome_message || defaultConfig.welcome_message]
        ])
      });
    }
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9c133d3145948960',t:'MTc2ODk2MTA0Ny4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
