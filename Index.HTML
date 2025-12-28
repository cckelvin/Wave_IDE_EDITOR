<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Wave IDE Pro</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <style>
        :root {
            --bg: #0d0d0d;
            --action-bar: #1a1a1a;
            --tab-active: #1e1e1e;
            --text: #d4d4d4;
            --gutter-bg: #111;
            --gutter-text: #888;
            --accent: #007acc;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; }
        body, html { 
            height: 100%; width: 100%; background: var(--bg); 
            color: var(--text); font-family: 'Segoe UI', sans-serif; 
            overflow: hidden; display: flex; flex-direction: column; 
        }

        /* --- 12 COLOR ANIMATED NOTCH --- */
        @keyframes cycleColors {
            0%, 8.33% { background: #ff4757; }   
            8.33%, 16.66% { background: #ffa502; } 
            16.66%, 25% { background: #eccc68; }  
            25%, 33.33% { background: #2ed573; }  
            33.33%, 41.66% { background: #1e90ff; } 
            41.66%, 50% { background: #3742fa; }  
            50%, 58.33% { background: #a29bfe; }  
            58.33%, 66.66% { background: #ff7f50; } 
            66.66%, 75% { background: #70a1ff; }  
            75%, 83.33% { background: #2f3542; }  
            83.33%, 91.66% { background: #747d8c; } 
            91.66%, 100% { background: #007acc; }
        }

        .wave-notch {
            height: 44px; width: 100%; flex-shrink: 0;
            animation: cycleColors 72s infinite;
            color: white; display: flex; align-items: center; justify-content: center;
            font-weight: 900; font-size: 13px; letter-spacing: 2px;
            text-transform: uppercase; position: relative; z-index: 11000;
        }

        #back-btn {
            position: absolute; right: 12px; top: 50%; transform: translateY(-50%);
            background: rgba(0,0,0,0.5); border: 1px solid white;
            color: white; padding: 5px 12px; border-radius: 4px; font-size: 10px;
            display: none; cursor: pointer;
        }

        /* --- SPLASH SCREEN --- */
        #splash {
            position: fixed; inset: 0; background: #000; z-index: 12000;
            display: flex; flex-direction: column; align-items: center; justify-content: center;
        }
        .splash-logo { font-size: 42px; font-weight: 900; color: #007acc; margin-bottom: 20px; letter-spacing: 8px; }
        .progress-bar { width: 180px; height: 3px; background: #222; border-radius: 10px; overflow: hidden; }
        .progress-fill { width: 0%; height: 100%; background: #007acc; animation: fill 5s linear forwards; }
        @keyframes fill { to { width: 100%; } }

        /* --- HEADER --- */
        .fixed-header { flex-shrink: 0; background: var(--bg); z-index: 1000; }
        .action-bar { padding: 10px 15px; background: var(--action-bar); display: flex; align-items: center; border-bottom: 1px solid #222; }
        .file-meta { flex: 1; }
        .file-meta .filename { font-size: 14px; font-weight: bold; color: #fff; }
        .file-meta .proj-path { font-size: 9px; color: #666; text-transform: uppercase; }

        .tabs { display: flex; background: #111; border-bottom: 1px solid #333; overflow-x: auto; }
        .tab { padding: 12px 20px; font-size: 11px; cursor: pointer; color: #666; border-right: 1px solid #222; white-space: nowrap; }
        .tab.active { background: var(--tab-active); color: #007acc; border-bottom: 2px solid #007acc; }

        /* --- EDITOR --- */
        .workspace { flex: 1; display: flex; position: relative; background: #1e1e1e; overflow: hidden; }
        .gutter {
            width: 55px; background: var(--gutter-bg); color: var(--gutter-text); 
            padding-top: 15px; text-align: right; padding-right: 12px; 
            font-family: 'Consolas', monospace; font-size: 14px; line-height: 1.6;
            user-select: none; border-right: 2px solid #2a2a2a; overflow: hidden;
        }

        #editor {
            flex: 1; background: transparent; border: none; outline: none; 
            color: #9cdcfe; padding: 15px; font-family: 'Consolas', monospace; 
            font-size: 14px; line-height: 1.6; resize: none; 
            white-space: pre; overflow: auto; tab-size: 4;
            padding-bottom: 150px;
        }

        /* --- TOOLBAR --- */
        .toolbar { height: 55px; background: #1a1a1a; display: flex; align-items: center; justify-content: space-around; border-top: 1px solid #333; flex-shrink: 0; }
        .key { background: #333; color: white; border: none; padding: 10px 15px; border-radius: 6px; font-size: 11px; font-weight: bold; }
        .key.special { background: #007acc; }

        /* --- PREVIEW & CONSOLE --- */
        #play-screen { position: fixed; top: 44px; bottom: 0; left: 0; right: 0; background: #fff; z-index: 10005; display: none; }
        iframe { width: 100%; height: 100%; border: none; background: white; }
        
        #console-panel {
            position: absolute; bottom: 0; left: 0; right: 0; height: 35%;
            background: rgba(10, 10, 10, 0.95); color: #0f0; font-family: monospace;
            padding: 10px; font-size: 12px; overflow-y: auto; display: none;
            border-top: 2px solid #444; pointer-events: auto; z-index: 10010;
        }
        .toggle-console {
            position: absolute; bottom: 15px; left: 15px; background: #333;
            color: white; border: 1px solid #555; padding: 6px 12px; border-radius: 4px; font-size: 10px; z-index: 10011;
        }
    </style>
</head>
<body>

<div id="splash">
    <div class="splash-logo">WAVE</div>
    <div class="progress-bar"><div class="progress-fill"></div></div>
</div>

<div class="wave-notch">
    <span>Wave IDE Pro</span>
    <button id="back-btn" onclick="closePlay()">EXIT</button>
</div>

<div class="fixed-header">
    <header class="action-bar">
        <div class="file-meta">
            <span class="filename" id="file-title">index.html</span><br>
            <span class="proj-path" id="proj-display">WAVE/IDE/LOCAL</span>
        </div>
        <div style="display:flex; gap:18px; align-items:center;">
            <button onclick="runProject()" style="background:none; border:none; color:#4ec9b0; font-size:22px;">▶</button>
            <button onclick="showModal('new-project-modal')" style="background:none; border:none; color:#007acc; font-size:28px;">+</button>
        </div>
    </header>

    <nav class="tabs">
        <div class="tab active" id="t-html" onclick="switchTab('html')">index.html</div>
        <div class="tab" id="t-css" onclick="switchTab('css')">style.css</div>
        <div class="tab" id="t-js" onclick="switchTab('js')">script.js</div>
    </nav>
</div>

<div class="workspace">
    <div class="gutter" id="gutter">1</div>
    <textarea id="editor" spellcheck="false" wrap="off" onscroll="syncScroll()"></textarea>
</div>

<footer class="toolbar">
    <button class="key" onclick="insert('    ')">TAB</button>
    <button class="key" onclick="insert(';')"> ; </button>
    <button class="key" onclick="insert('\"')"> " </button>
    <button class="key special" onclick="beautifyCode()">BEAUTIFY</button>
    <button class="key" onclick="manualSave()">SAVE</button>
</footer>

<div id="play-screen">
    <iframe id="play-frame"></iframe>
    <div id="console-panel"></div>
    <button class="toggle-console" onclick="toggleConsole()">Toggle Console</button>
</div>

<div id="new-project-modal" class="modal">
    <div class="modal-content">
        <h3 style="color:#007acc; margin-bottom: 10px;">Project Settings</h3>
        <input type="text" id="proj-name" placeholder="Project Name">
        <button class="btn-folder" onclick="pickFolder()" style="background:#444; color:white; border:none; padding:12px; width:100%; border-radius:6px; margin-bottom:10px;">📂 SELECT FOLDER</button>
        <p id="folder-status" style="font-size: 10px; color: #4ec9b0; margin-bottom: 10px;">Using browser storage</p>
        <button onclick="confirmNewProject()" style="width:100%; padding:12px; background:#007acc; border:none; color:white; font-weight:bold; border-radius:6px;">CREATE</button>
        <button onclick="closeModal('new-project-modal')" style="width:100%; background:none; border:none; color:#555; margin-top:10px; font-size:11px;">Cancel</button>
    </div>
</div>

<script>
    setTimeout(() => { document.getElementById('splash').style.display = 'none'; }, 5000);

    let activeFile = 'html';
    let directoryHandle = null;
    const projectFiles = { 
        html: localStorage.getItem('w_h') || '<h1>Wave IDE</h1>', 
        css: localStorage.getItem('w_c') || 'body { background: white; text-align: center; }', 
        js: localStorage.getItem('w_j') || 'console.log("Ready.");' 
    };

    const editArea = document.getElementById('editor');
    const gutterArea = document.getElementById('gutter');

    function init() {
        editArea.value = projectFiles[activeFile];
        updateLines();
    }

    async function pickFolder() {
        try {
            directoryHandle = await window.showDirectoryPicker();
            document.getElementById('folder-status').innerText = "✔ " + directoryHandle.name;
        } catch (e) { console.warn("Picker failed"); }
    }

    function syncScroll() { gutterArea.scrollTop = editArea.scrollTop; }

    function updateLines() {
        const lines = editArea.value.split('\n').length;
        let nums = '';
        for (let i = 1; i <= lines; i++) nums += i + '\n';
        gutterArea.innerText = nums;
    }

    function switchTab(type) {
        projectFiles[activeFile] = editArea.value;
        activeFile = type;
        editArea.value = projectFiles[activeFile];
        document.getElementById('file-title').innerText = `index.${type === 'js' ? 'js' : type === 'css' ? 'css' : 'html'}`;
        document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
        document.getElementById('t-' + type).classList.add('active');
        updateLines();
    }

    function beautifyCode() {
        let code = editArea.value;
        let tab = "    ";
        let level = 0;
        let beautified = code.split('\n').map(line => {
            line = line.trim();
            if (line.match(/[}\]]/)) level--;
            let result = tab.repeat(Math.max(0, level)) + line;
            if (line.match(/[{[]/)) level++;
            return result;
        }).join('\n');
        editArea.value = beautified;
        updateLines();
    }

    function runProject() {
        projectFiles[activeFile] = editArea.value;
        document.getElementById('play-screen').style.display = 'block';
        document.getElementById('back-btn').style.display = 'block';
        document.getElementById('console-panel').innerHTML = '--- Debug Console ---<br>';
        
        const consoleScript = `
            <script>
                const panel = window.parent.document.getElementById('console-panel');
                const log = (msg, color) => {
                    const div = document.createElement('div');
                    div.style.color = color || '#0f0';
                    div.textContent = msg;
                    panel.appendChild(div);
                    panel.scrollTop = panel.scrollHeight;
                };
                console.log = (...args) => log("LOG: " + args.join(' '));
                console.error = (...args) => log("ERR: " + args.join(' '), '#ff4757');
                window.onerror = (m, u, l) => log("FATAL: " + m + " at line " + l, '#ff4757');
            <\/script>
        `;

        const content = `<!DOCTYPE html><html><head><meta name="viewport" content="width=device-width, initial-scale=1.0">${consoleScript}<style>html,body{margin:0;padding:0;}${projectFiles.css}</style></head><body>${projectFiles.html}<script>${projectFiles.js}<\/script></body></html>`;
        document.getElementById('play-frame').srcdoc = content;
    }

    function toggleConsole() {
        const p = document.getElementById('console-panel');
        p.style.display = p.style.display === 'block' ? 'none' : 'block';
    }

    function closePlay() {
        document.getElementById('play-screen').style.display = 'none';
        document.getElementById('back-btn').style.display = 'none';
    }

    function insert(code) {
        const start = editArea.selectionStart;
        editArea.value = editArea.value.substring(0, start) + code + editArea.value.substring(editArea.selectionEnd);
        editArea.focus();
        editArea.selectionEnd = start + code.length;
        updateLines();
    }

    function showModal(id) { document.getElementById(id).style.display = 'flex'; }
    function closeModal(id) { document.getElementById(id).style.display = 'none'; }
    
    function confirmNewProject() {
        const name = document.getElementById('proj-name').value;
        if(name) {
            document.getElementById('proj-display').innerText = (directoryHandle ? directoryHandle.name : "LOCAL") + "/" + name.toUpperCase();
            closeModal('new-project-modal');
        }
    }

    function manualSave() {
        projectFiles[activeFile] = editArea.value;
        localStorage.setItem('w_h', projectFiles.html);
        localStorage.setItem('w_c', projectFiles.css);
        localStorage.setItem('w_j', projectFiles.js);
    }

    editArea.addEventListener('input', updateLines);
    init();
</script>
</body>
</html>
