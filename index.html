<!DOCTYPE html>
<html lang="zh-TW">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
  <title>那群跟我變美(發酒癲）的朋友點名簿</title>
  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- PeerJS CDN for Realtime Cross-Device Sync -->
  <script src="https://unpkg.com/peerjs@1.5.2/dist/peerjs.min.js"></script>
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            muji: {
              bg: '#F7F5F0',
              card: '#FFFFFF',
              border: '#E3DFD5',
              text: '#333333',
              muted: '#7F7B75',
              accent: '#8C7A6B',
              accentLight: '#F0EAE1',
              sober: '#6E8B74',      // 清醒變美
              leave: '#D99B00',      // 喝茫請假
              late: '#C86D51',       // 微醺遲到
              absent: '#A94442'      // 發酒癲失聯
            }
          },
          fontFamily: {
            sans: ['-apple-system', 'BlinkMacSystemFont', '"Segoe UI"', 'Roboto', '"Hiragino Sans GB"', '"Microsoft JhengHei"', sans-serif],
          }
        }
      }
    }
  </script>
  <style>
    body {
      background-color: #F7F5F0;
      color: #333333;
      -webkit-tap-highlight-color: transparent;
      user-select: none;
    }
    .long-press-active {
      transform: scale(0.96);
      transition: transform 0.1s ease;
    }
    .progress-bar {
      transition: width 0.5s linear;
    }
    /* Custom Scrollbar for MUJI aesthetics */
    ::-webkit-scrollbar {
      width: 6px;
      height: 6px;
    }
    ::-webkit-scrollbar-track {
      background: #F7F5F0;
    }
    ::-webkit-scrollbar-thumb {
      background: #D5D0C5;
      border-radius: 3px;
    }
  </style>
</head>
<body class="min-h-screen flex flex-col font-sans">

  <!-- Top Header -->
  <header class="bg-white border-b border-muji-border sticky top-0 z-30 shadow-sm">
    <div class="max-w-4xl mx-auto px-4 py-3 flex flex-col sm:flex-row justify-between items-center gap-2">
      <div class="flex items-center space-x-2">
        <span class="text-2xl">🍷</span>
        <div>
          <h1 class="text-lg font-bold tracking-wide text-muji-text">那群跟我變美(發酒癲）的朋友點名簿</h1>
          <p class="text-xs text-muji-muted">MUJI Style • 跨裝置即時雲端點名</p>
        </div>
      </div>
      
      <!-- Sync Room Box -->
      <div class="flex items-center space-x-2 bg-muji-bg px-3 py-1.5 rounded-lg border border-muji-border text-xs">
        <div class="flex items-center space-x-1">
          <span id="syncStatusDot" class="w-2.5 h-2.5 rounded-full bg-amber-400 inline-block animate-pulse"></span>
          <span class="text-muji-muted font-medium">房間:</span>
          <span id="roomIdDisplay" class="font-mono font-bold text-muji-text">建立中...</span>
        </div>
        <button onclick="copyShareLink()" class="ml-2 bg-white px-2 py-1 rounded border border-muji-border hover:bg-muji-accentLight text-muji-accent font-medium transition">
          複製共享連結
        </button>
      </div>
    </div>
  </header>

  <!-- Navigation Tabs -->
  <div class="bg-white border-b border-muji-border">
    <div class="max-w-4xl mx-auto px-4 flex space-x-8 text-sm font-medium">
      <button id="tab1Btn" onclick="switchTab(1)" class="py-3 border-b-2 border-muji-accent text-muji-accent font-semibold transition">
        👥 1. 酒精閨蜜名單
      </button>
      <button id="tab2Btn" onclick="switchTab(2)" class="py-3 border-b-2 border-transparent text-muji-muted hover:text-muji-text transition">
        📅 2. 變美與醉酒日曆
      </button>
    </div>
  </div>

  <!-- Main Content Container -->
  <main class="max-w-4xl mx-auto px-4 py-6 flex-1 w-full">

    <!-- PAGE 1: Friends Management -->
    <section id="page1" class="space-y-6">
      <div class="bg-white p-5 rounded-xl border border-muji-border shadow-sm">
        <h2 class="text-base font-semibold mb-3 text-muji-text flex items-center">
          <span class="mr-2">➕</span> 新增閨蜜成員
        </h2>
        <div class="flex gap-2">
          <input type="text" id="newMemberName" placeholder="輸入朋友暱稱（如：喝酒怪、酒後失憶王）" 
                 class="flex-1 px-4 py-2.5 bg-muji-bg border border-muji-border rounded-lg text-sm focus:outline-none focus:border-muji-accent transition">
          <button onclick="addMember()" class="bg-muji-accent text-white px-5 py-2.5 rounded-lg text-sm font-medium hover:opacity-90 active:scale-95 transition">
            新增成員
          </button>
        </div>
      </div>

      <div class="bg-white p-5 rounded-xl border border-muji-border shadow-sm">
        <div class="flex justify-between items-center mb-4">
          <h2 class="text-base font-semibold text-muji-text">👥 名單管理 (<span id="memberCount">0</span>人)</h2>
          <span class="text-xs text-muji-muted">點擊可直接刪除成員</span>
        </div>
        <div id="memberList" class="flex flex-wrap gap-2.5">
          <!-- Dynamically populated -->
        </div>
      </div>
    </section>

    <!-- PAGE 2: Calendar & Roll Call -->
    <section id="page2" class="space-y-6 hidden">
      <!-- Controls Header -->
      <div class="bg-white p-4 rounded-xl border border-muji-border shadow-sm flex flex-col md:flex-row justify-between items-center gap-4">
        <!-- Target Selection -->
        <div class="flex items-center space-x-2 w-full md:w-auto">
          <label class="text-xs font-semibold text-muji-muted whitespace-nowrap">查看對象：</label>
          <select id="memberFilter" onchange="renderCalendar()" class="bg-muji-bg border border-muji-border px-3 py-1.5 rounded-lg text-sm text-muji-text focus:outline-none focus:border-muji-accent w-full">
            <option value="ALL">全體成員總覽</option>
          </select>
        </div>

        <!-- Month Navigation -->
        <div class="flex items-center space-x-3">
          <button onclick="changeMonth(-1)" class="p-1.5 rounded-lg border border-muji-border hover:bg-muji-bg transition">👈</button>
          <span id="currentMonthLabel" class="text-base font-bold text-muji-text font-mono">2026 年 09 月</span>
          <button onclick="changeMonth(1)" class="p-1.5 rounded-lg border border-muji-border hover:bg-muji-bg transition">👉</button>
        </div>

        <!-- Export / Import -->
        <div class="flex space-x-2">
          <button onclick="exportData()" class="px-2.5 py-1.5 border border-muji-border rounded-lg text-xs font-medium text-muji-muted hover:bg-muji-bg transition">匯出 JSON</button>
          <button onclick="document.getElementById('importFile').click()" class="px-2.5 py-1.5 border border-muji-border rounded-lg text-xs font-medium text-muji-muted hover:bg-muji-bg transition">匯入 JSON</button>
          <input type="file" id="importFile" accept=".json" class="hidden" onchange="importData(event)">
        </div>
      </div>

      <!-- Long Press Guide -->
      <div class="bg-muji-accentLight p-3 rounded-lg border border-muji-border text-xs text-muji-accent flex items-center justify-between">
        <span>💡 <b>點名操作說明：</b>在下方日曆格子上記住<b>長按 0.5 秒</b>即可觸發醉酒變美點名！</span>
      </div>

      <!-- Calendar Grid -->
      <div class="bg-white p-4 rounded-xl border border-muji-border shadow-sm">
        <!-- Weekday Headers -->
        <div class="grid grid-cols-7 gap-1 text-center font-semibold text-xs text-muji-muted py-2 border-b border-muji-border mb-2">
          <div class="text-red-400">日</div>
          <div>一</div>
          <div>二</div>
          <div>三</div>
          <div>四</div>
          <div>五</div>
          <div class="text-amber-600">六</div>
        </div>

        <!-- Days Cells -->
        <div id="calendarGrid" class="grid grid-cols-7 gap-1.5 sm:gap-2">
          <!-- Dynamically Generated -->
        </div>
      </div>

      <!-- Monthly Stats -->
      <div class="bg-white p-5 rounded-xl border border-muji-border shadow-sm">
        <h3 class="text-sm font-semibold text-muji-text mb-3">📊 本月醉酒變美戰績統計</h3>
        <div class="grid grid-cols-2 sm:grid-cols-4 gap-3 text-center">
          <div class="p-3 rounded-lg bg-emerald-50 border border-emerald-100">
            <div class="text-xs text-emerald-700">✨ 清醒變美</div>
            <div id="statSober" class="text-xl font-bold text-emerald-800 mt-1">0</div>
          </div>
          <div class="p-3 rounded-lg bg-amber-50 border border-amber-100">
            <div class="text-xs text-amber-700">🍹 喝茫請假</div>
            <div id="statLeave" class="text-xl font-bold text-amber-800 mt-1">0</div>
          </div>
          <div class="p-3 rounded-lg bg-orange-50 border border-orange-100">
            <div class="text-xs text-orange-700">🥴 微醺遲到</div>
            <div id="statLate" class="text-xl font-bold text-orange-800 mt-1">0</div>
          </div>
          <div class="p-3 rounded-lg bg-red-50 border border-red-100">
            <div class="text-xs text-red-700">🤪 發酒癲失聯</div>
            <div id="statAbsent" class="text-xl font-bold text-red-800 mt-1">0</div>
          </div>
        </div>
      </div>
    </section>

  </main>

  <!-- ROLL CALL MODAL -->
  <div id="rollCallModal" class="fixed inset-0 bg-black/40 backdrop-blur-sm z-50 flex items-center justify-center p-4 hidden">
    <div class="bg-white rounded-2xl border border-muji-border max-w-md w-full p-6 shadow-xl space-y-4 transform transition-all">
      <div class="flex justify-between items-center border-b border-muji-border pb-3">
        <div>
          <h3 id="modalTitle" class="font-bold text-base text-muji-text">日曆點名</h3>
          <p id="modalSubTitle" class="text-xs text-muji-muted mt-0.5"></p>
        </div>
        <button onclick="closeModal()" class="text-muji-muted hover:text-muji-text text-xl font-bold">✕</button>
      </div>

      <!-- Roll Call Member Selector (if ALL is selected) -->
      <div id="modalMemberSelectGroup" class="space-y-1">
        <label class="text-xs font-semibold text-muji-muted">選擇點名對象：</label>
        <select id="modalMemberSelect" class="w-full bg-muji-bg border border-muji-border px-3 py-2 rounded-lg text-sm text-muji-text focus:outline-none">
          <!-- Dynamically populated -->
        </select>
      </div>

      <!-- Status Options -->
      <div class="space-y-2">
        <label class="text-xs font-semibold text-muji-muted">選擇微醺變美狀態：</label>
        <div class="grid grid-cols-2 gap-2">
          <button type="button" onclick="selectStatus('sober')" id="statusBtn_sober" class="p-2.5 border border-muji-border rounded-xl text-xs font-semibold flex items-center space-x-2 transition">
            <span class="w-3 h-3 rounded-full bg-emerald-600 inline-block"></span>
            <span>✨ 清醒變美</span>
          </button>
          <button type="button" onclick="selectStatus('leave')" id="statusBtn_leave" class="p-2.5 border border-muji-border rounded-xl text-xs font-semibold flex items-center space-x-2 transition">
            <span class="w-3 h-3 rounded-full bg-amber-500 inline-block"></span>
            <span>🍹 喝茫請假</span>
          </button>
          <button type="button" onclick="selectStatus('late')" id="statusBtn_late" class="p-2.5 border border-muji-border rounded-xl text-xs font-semibold flex items-center space-x-2 transition">
            <span class="w-3 h-3 rounded-full bg-orange-500 inline-block"></span>
            <span>🥴 微醺遲到</span>
          </button>
          <button type="button" onclick="selectStatus('absent')" id="statusBtn_absent" class="p-2.5 border border-muji-border rounded-xl text-xs font-semibold flex items-center space-x-2 transition">
            <span class="w-3 h-3 rounded-full bg-red-600 inline-block"></span>
            <span>🤪 發酒癲失聯</span>
          </button>
        </div>
      </div>

      <!-- Note Input -->
      <div class="space-y-1">
        <label class="text-xs font-semibold text-muji-muted">醉酒事由 / 戰績備註：</label>
        <input type="text" id="modalNote" placeholder="例：喝了2瓶紅酒、敷面膜中、發酒癲斷片" 
               class="w-full bg-muji-bg border border-muji-border px-3 py-2 rounded-lg text-sm text-muji-text focus:outline-none focus:border-muji-accent">
      </div>

      <!-- Action Buttons -->
      <div class="flex justify-between items-center pt-2">
        <button onclick="clearRecord()" class="text-xs text-red-500 hover:underline">清除本日紀錄</button>
        <div class="flex space-x-2">
          <button onclick="closeModal()" class="px-4 py-2 border border-muji-border rounded-lg text-xs font-medium text-muji-muted hover:bg-muji-bg">取消</button>
          <button onclick="saveRollCall()" class="px-5 py-2 bg-muji-accent text-white rounded-lg text-xs font-medium hover:opacity-90">保存並同步</button>
        </div>
      </div>
    </div>
  </div>

  <script>
    // --- Application State ---
    let appState = {
      members: ['閨蜜A', '閨蜜B'],
      records: {}, // Key: "YYYY-MM-DD", Value: { "memberName": { status: 'sober', note: '...' } }
      currentYear: new Date().getFullYear(),
      currentMonth: new Date().getMonth()
    };

    let selectedDateStr = '';
    let currentSelectedStatus = 'sober';
    let peer = null;
    let connections = [];
    let myRoomId = '';

    // --- Core Initialization ---
    window.addEventListener('DOMContentLoaded', () => {
      loadLocalStorage();
      setupPeerSync();
      renderMembers();
      renderCalendar();
      checkUrlRoom();
    });

    // --- Local Storage Management ---
    function loadLocalStorage() {
      const saved = localStorage.getItem('drunk_friends_app_data');
      if (saved) {
        try {
          const parsed = JSON.parse(saved);
          if (parsed.members) appState.members = parsed.members;
          if (parsed.records) appState.records = parsed.records;
        } catch(e) {
          console.error(e);
        }
      }
    }

    function saveData(broadcast = true) {
      localStorage.setItem('drunk_friends_app_data', JSON.stringify({
        members: appState.members,
        records: appState.records
      }));

      if (broadcast) {
        broadcastState();
      }
    }

    // --- Tab Switching ---
    function switchTab(tabNum) {
      const page1 = document.getElementById('page1');
      const page2 = document.getElementById('page2');
      const tab1Btn = document.getElementById('tab1Btn');
      const tab2Btn = document.getElementById('tab2Btn');

      if (tabNum === 1) {
        page1.classList.remove('hidden');
        page2.classList.add('hidden');
        tab1Btn.className = "py-3 border-b-2 border-muji-accent text-muji-accent font-semibold transition";
        tab2Btn.className = "py-3 border-b-2 border-transparent text-muji-muted hover:text-muji-text transition";
      } else {
        page1.classList.add('hidden');
        page2.classList.remove('hidden');
        tab2Btn.className = "py-3 border-b-2 border-muji-accent text-muji-accent font-semibold transition";
        tab1Btn.className = "py-3 border-b-2 border-transparent text-muji-muted hover:text-muji-text transition";
        renderCalendar();
      }
    }

    // --- Member Management ---
    function renderMembers() {
      const memberList = document.getElementById('memberList');
      const memberFilter = document.getElementById('memberFilter');
      const memberCount = document.getElementById('memberCount');

      memberCount.innerText = appState.members.length;
      memberList.innerHTML = '';

      if (appState.members.length === 0) {
        memberList.innerHTML = `<span class="text-xs text-muji-muted">尚未新增任何酒精閨蜜，請在上方輸入框新增！</span>`;
      } else {
        appState.members.forEach((m) => {
          const tag = document.createElement('div');
          tag.className = "flex items-center space-x-1.5 px-3 py-1.5 bg-muji-bg border border-muji-border rounded-lg text-xs font-medium text-muji-text hover:border-red-300 transition cursor-pointer group";
          tag.innerHTML = `
            <span>🥂 ${escapeHtml(m)}</span>
            <span onclick="deleteMember('${escapeHtml(m)}')" class="text-muji-muted group-hover:text-red-500 font-bold ml-1">×</span>
          `;
          memberList.appendChild(tag);
        });
      }

      // Update Calendar Member Filter Dropdown
      const currentVal = memberFilter.value;
      memberFilter.innerHTML = `<option value="ALL">全體成員總覽</option>`;
      appState.members.forEach(m => {
        const opt = document.createElement('option');
        opt.value = m;
        opt.innerText = m;
        memberFilter.appendChild(opt);
      });
      if (appState.members.includes(currentVal)) {
        memberFilter.value = currentVal;
      } else {
        memberFilter.value = 'ALL';
      }
    }

    function addMember() {
      const input = document.getElementById('newMemberName');
      const name = input.value.trim();
      if (!name) return;
      if (appState.members.includes(name)) {
        alert('該成員名稱已存在！');
        return;
      }
      appState.members.push(name);
      input.value = '';
      saveData();
      renderMembers();
    }

    function deleteMember(name) {
      if (confirm(`確定要移除酒精閨蜜「${name}」嗎？`)) {
        appState.members = appState.members.filter(m => m !== name);
        saveData();
        renderMembers();
        renderCalendar();
      }
    }

    // --- Calendar Rendering & Navigation ---
    function changeMonth(delta) {
      appState.currentMonth += delta;
      if (appState.currentMonth < 0) {
        appState.currentMonth = 11;
        appState.currentYear--;
      } else if (appState.currentMonth > 11) {
        appState.currentMonth = 0;
        appState.currentYear++;
      }
      renderCalendar();
    }

    function renderCalendar() {
      const grid = document.getElementById('calendarGrid');
      const label = document.getElementById('currentMonthLabel');
      const filter = document.getElementById('memberFilter').value;

      grid.innerHTML = '';
      label.innerText = `${appState.currentYear} 年 ${String(appState.currentMonth + 1).padStart(2, '0')} 月`;

      const firstDay = new Date(appState.currentYear, appState.currentMonth, 1).getDay();
      const daysInMonth = new Date(appState.currentYear, appState.currentMonth + 1, 0).getDate();

      // Reset Monthly Stats
      let statSober = 0, statLeave = 0, statLate = 0, statAbsent = 0;

      // Blank Padding Cells
      for (let i = 0; i < firstDay; i++) {
        const emptyCell = document.createElement('div');
        emptyCell.className = "h-20 bg-muji-bg/30 rounded-xl border border-transparent";
        grid.appendChild(emptyCell);
      }

      // Date Cells
      const todayStr = new Date().toISOString().split('T')[0];

      for (let day = 1; day <= daysInMonth; day++) {
        const dateStr = `${appState.currentYear}-${String(appState.currentMonth + 1).padStart(2, '0')}-${String(day).padStart(2, '0')}`;
        const isToday = (dateStr === todayStr);

        const cell = document.createElement('div');
        cell.className = `relative h-20 p-1.5 rounded-xl border transition flex flex-col justify-between cursor-pointer select-none overflow-hidden ${
          isToday ? 'bg-amber-50/50 border-amber-300' : 'bg-white border-muji-border hover:border-muji-accent'
        }`;

        // Top Row: Date Number
        const topRow = document.createElement('div');
        topRow.className = "flex justify-between items-center";
        topRow.innerHTML = `
          <span class="text-xs font-bold font-mono ${isToday ? 'text-amber-700 bg-amber-100 px-1.5 py-0.5 rounded-md' : 'text-muji-text'}">${day}</span>
        `;
        cell.appendChild(topRow);

        // Content Area for Attendance Badges
        const contentArea = document.createElement('div');
        contentArea.className = "flex-1 my-1 overflow-y-auto space-y-1 text-[10px]";

        const dayRecord = appState.records[dateStr] || {};

        if (filter === 'ALL') {
          // Show indicators for all members
          const keys = Object.keys(dayRecord);
          if (keys.length > 0) {
            keys.forEach(m => {
              const rec = dayRecord[m];
              const badge = createBadgeElement(m, rec.status, rec.note);
              contentArea.appendChild(badge);

              // Update Stats
              if (rec.status === 'sober') statSober++;
              if (rec.status === 'leave') statLeave++;
              if (rec.status === 'late') statLate++;
              if (rec.status === 'absent') statAbsent++;
            });
          }
        } else {
          // Show specific member status
          const rec = dayRecord[filter];
          if (rec) {
            const badge = createBadgeElement(filter, rec.status, rec.note);
            contentArea.appendChild(badge);

            // Update Stats
            if (rec.status === 'sober') statSober++;
            if (rec.status === 'leave') statLeave++;
            if (rec.status === 'late') statLate++;
            if (rec.status === 'absent') statAbsent++;
          }
        }

        cell.appendChild(contentArea);

        // Progress Overlay for Long Press Feedback
        const progress = document.createElement('div');
        progress.className = "absolute bottom-0 left-0 h-1 bg-muji-accent w-0 progress-bar";
        cell.appendChild(progress);

        // Bind Long Press & Click Events
        bindLongPress(cell, dateStr, progress);

        grid.appendChild(cell);
      }

      // Update Monthly Statistics
      document.getElementById('statSober').innerText = statSober;
      document.getElementById('statLeave').innerText = statLeave;
      document.getElementById('statLate').innerText = statLate;
      document.getElementById('statAbsent').innerText = statAbsent;
    }

    function createBadgeElement(name, status, note) {
      const div = document.createElement('div');
      let bgColor = 'bg-emerald-100 text-emerald-800 border-emerald-200';
      let icon = '✨';

      if (status === 'leave') {
        bgColor = 'bg-amber-100 text-amber-800 border-amber-200';
        icon = '🍹';
      } else if (status === 'late') {
        bgColor = 'bg-orange-100 text-orange-800 border-orange-200';
        icon = '🥴';
      } else if (status === 'absent') {
        bgColor = 'bg-red-100 text-red-800 border-red-200';
        icon = '🤪';
      }

      div.className = `px-1.5 py-0.5 rounded border ${bgColor} flex items-center justify-between truncate`;
      div.title = note ? `${name}: ${note}` : name;
      div.innerHTML = `
        <span class="truncate">${icon} ${escapeHtml(name)}</span>
        ${note ? `<span class="ml-0.5 text-[9px] opacity-75">💬</span>` : ''}
      `;
      return div;
    }

    // --- Long Press Detection Logic ---
    function bindLongPress(element, dateStr, progressEl) {
      let timer = null;
      const pressDuration = 500; // 0.5 seconds

      const startPress = (e) => {
        element.classList.add('long-press-active');
        progressEl.style.width = '100%';

        timer = setTimeout(() => {
          openRollCallModal(dateStr);
          resetPress();
        }, pressDuration);
      };

      const resetPress = () => {
        clearTimeout(timer);
        element.classList.remove('long-press-active');
        progressEl.style.width = '0%';
      };

      element.addEventListener('touchstart', startPress, { passive: true });
      element.addEventListener('touchend', resetPress);
      element.addEventListener('touchcancel', resetPress);

      element.addEventListener('mousedown', startPress);
      element.addEventListener('mouseup', resetPress);
      element.addEventListener('mouseleave', resetPress);
    }

    // --- Modal Logic ---
    function openRollCallModal(dateStr) {
      selectedDateStr = dateStr;
      const modal = document.getElementById('rollCallModal');
      const title = document.getElementById('modalTitle');
      const subtitle = document.getElementById('modalSubTitle');
      const filter = document.getElementById('memberFilter').value;
      const memberSelectGroup = document.getElementById('modalMemberSelectGroup');
      const memberSelect = document.getElementById('modalMemberSelect');

      title.innerText = `📅 日曆點名: ${dateStr}`;

      if (appState.members.length === 0) {
        alert('請先在第一頁新增酒精閨蜜成員！');
        return;
      }

      // Populate Modal Member Select Dropdown
      memberSelect.innerHTML = '';
      appState.members.forEach(m => {
        const opt = document.createElement('option');
        opt.value = m;
        opt.innerText = m;
        memberSelect.appendChild(opt);
      });

      if (filter !== 'ALL') {
        memberSelect.value = filter;
        memberSelectGroup.classList.add('hidden');
        subtitle.innerText = `正在記錄朋友：${filter}`;
      } else {
        memberSelectGroup.classList.remove('hidden');
        subtitle.innerText = `請選擇成員進行醉酒變美記錄`;
      }

      // Load existing record for selected date/member
      loadModalFormData();

      memberSelect.onchange = () => loadModalFormData();

      modal.classList.remove('hidden');
    }

    function loadModalFormData() {
      const memberName = document.getElementById('modalMemberSelect').value;
      const dayRecord = appState.records[selectedDateStr] || {};
      const memberRec = dayRecord[memberName];

      if (memberRec) {
        selectStatus(memberRec.status);
        document.getElementById('modalNote').value = memberRec.note || '';
      } else {
        selectStatus('sober');
        document.getElementById('modalNote').value = '';
      }
    }

    function selectStatus(status) {
      currentSelectedStatus = status;
      ['sober', 'leave', 'late', 'absent'].forEach(s => {
        const btn = document.getElementById(`statusBtn_${s}`);
        if (s === status) {
          btn.className = "p-2.5 border-2 border-muji-accent bg-muji-accentLight rounded-xl text-xs font-bold flex items-center space-x-2 transition";
        } else {
          btn.className = "p-2.5 border border-muji-border bg-white rounded-xl text-xs font-semibold flex items-center space-x-2 transition opacity-60";
        }
      });
    }

    function closeModal() {
      document.getElementById('rollCallModal').classList.add('hidden');
    }

    function saveRollCall() {
      const memberName = document.getElementById('modalMemberSelect').value;
      const note = document.getElementById('modalNote').value.trim();

      if (!appState.records[selectedDateStr]) {
        appState.records[selectedDateStr] = {};
      }

      appState.records[selectedDateStr][memberName] = {
        status: currentSelectedStatus,
        note: note
      };

      saveData();
      renderCalendar();
      closeModal();
    }

    function clearRecord() {
      const memberName = document.getElementById('modalMemberSelect').value;
      if (appState.records[selectedDateStr] && appState.records[selectedDateStr][memberName]) {
        delete appState.records[selectedDateStr][memberName];
        if (Object.keys(appState.records[selectedDateStr]).length === 0) {
          delete appState.records[selectedDateStr];
        }
        saveData();
        renderCalendar();
      }
      closeModal();
    }

    // --- JSON Export / Import ---
    function exportData() {
      const dataStr = "data:text/json;charset=utf-8," + encodeURIComponent(JSON.stringify(appState, null, 2));
      const anchor = document.createElement('a');
      anchor.setAttribute("href", dataStr);
      anchor.setAttribute("download", `drunk_friends_backup_${new Date().toISOString().split('T')[0]}.json`);
      document.body.appendChild(anchor);
      anchor.click();
      anchor.remove();
    }

    function importData(event) {
      const file = event.target.files[0];
      if (!file) return;

      const reader = new FileReader();
      reader.onload = function(e) {
        try {
          const imported = JSON.parse(e.target.result);
          if (imported.members && imported.records) {
            appState.members = imported.members;
            appState.records = imported.records;
            saveData();
            renderMembers();
            renderCalendar();
            alert('匯入成功！數據已同步至本地。');
          } else {
            alert('檔案格式不正確！');
          }
        } catch(err) {
          alert('解析 JSON 檔案失敗！');
        }
      };
      reader.readAsText(file);
    }

    // --- Realtime P2P Sync (PeerJS) ---
    function setupPeerSync() {
      const urlParams = new URLSearchParams(window.location.search);
      const targetRoom = urlParams.get('room');

      if (targetRoom) {
        myRoomId = targetRoom;
        document.getElementById('roomIdDisplay').innerText = myRoomId;
        connectToHost(targetRoom);
      } else {
        // Generate random room code
        myRoomId = 'BEAUTY-' + Math.floor(1000 + Math.random() * 9000);
        document.getElementById('roomIdDisplay').innerText = myRoomId;
        initHostPeer();
      }
    }

    function initHostPeer() {
      peer = new Peer(myRoomId);

      peer.on('open', (id) => {
        document.getElementById('syncStatusDot').className = "w-2.5 h-2.5 rounded-full bg-emerald-500 inline-block";
      });

      peer.on('connection', (conn) => {
        connections.push(conn);
        conn.on('open', () => {
          // Send current state to newly connected client
          conn.send({ type: 'STATE_UPDATE', data: appState });
        });

        conn.on('data', (data) => {
          if (data.type === 'STATE_UPDATE') {
            appState = data.data;
            saveData(false); // Don't broadcast loop
            renderMembers();
            renderCalendar();
          }
        });
      });
    }

    function connectToHost(hostId) {
      peer = new Peer();

      peer.on('open', () => {
        const conn = peer.connect(hostId);
        connections.push(conn);

        conn.on('open', () => {
          document.getElementById('syncStatusDot').className = "w-2.5 h-2.5 rounded-full bg-emerald-500 inline-block";
        });

        conn.on('data', (data) => {
          if (data.type === 'STATE_UPDATE') {
            appState = data.data;
            localStorage.setItem('drunk_friends_app_data', JSON.stringify({
              members: appState.members,
              records: appState.records
            }));
            renderMembers();
            renderCalendar();
          }
        });
      });
    }

    function broadcastState() {
      connections.forEach(conn => {
        if (conn.open) {
          conn.send({ type: 'STATE_UPDATE', data: appState });
        }
      });
    }

    function copyShareLink() {
      const shareUrl = `${window.location.origin}${window.location.pathname}?room=${myRoomId}`;
      navigator.clipboard.writeText(shareUrl).then(() => {
        alert(`已複製共享連結！\n將此連結發給朋友，大家就能進入同一個房間（${myRoomId}）即時同步點名：\n${shareUrl}`);
      }).catch(() => {
        prompt("請複製以下連結發給朋友：", shareUrl);
      });
    }

    function checkUrlRoom() {
      // Handled in setupPeerSync
    }

    // --- Helper Functions ---
    function escapeHtml(str) {
      return String(str).replace(/&/g, '&amp;').replace(/</g, '&lt;').replace(/>/g, '&gt;').replace(/"/g, '&quot;');
    }
  </script>
</body>
</html>
