[idex.html](https://github.com/user-attachments/files/33228422/idex.html)
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Crypto Imposter Adventure</title>
<style>
/* ============================================================
   RESET & BASE
   ============================================================ */
* { margin: 0; padding: 0; box-sizing: border-box; }

body {
    font-family: 'Segoe UI', Tahoma, sans-serif;
    background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
    background-attachment: fixed;
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 10px;
    color: white;
    overflow-x: hidden;
}

body::before {
    content: '';
    position: fixed;
    inset: 0;
    background:
        radial-gradient(circle at 20% 30%, rgba(102,126,234,0.15), transparent 50%),
        radial-gradient(circle at 80% 70%, rgba(255,215,0,0.1), transparent 50%);
    pointer-events: none;
    z-index: 0;
}

/* ============================================================
   LAYOUT WRAPPER
   ============================================================ */
.game-wrapper {
    max-width: 900px;
    width: 100%;
    background: linear-gradient(145deg, #1a1a2e, #0f3460);
    border-radius: 20px;
    overflow: hidden;
    box-shadow:
        0 25px 60px rgba(0,0,0,0.6),
        0 0 0 2px rgba(255,215,0,0.2),
        inset 0 1px 0 rgba(255,255,255,0.1);
    position: relative;
    z-index: 1;
}

/* ============================================================
   HEADER
   ============================================================ */
.game-header {
    background: linear-gradient(135deg, #667eea, #764ba2, #f093fb);
    background-size: 200% 200%;
    animation: gradientMove 5s ease infinite;
    padding: 18px;
    text-align: center;
    position: relative;
    overflow: hidden;
}

@keyframes gradientMove {
    0%, 100% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
}

.game-header::before {
    content: '';
    position: absolute;
    top: 0; left: -100%;
    width: 100%; height: 100%;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
    animation: shine 3s infinite;
}

@keyframes shine {
    0% { left: -100%; }
    100% { left: 100%; }
}

.game-header h1 {
    font-size: 1.3em;
    text-shadow: 0 2px 10px rgba(0,0,0,0.4);
    margin-bottom: 4px;
    letter-spacing: 1px;
}
.game-header p {
    font-size: 0.75em;
    opacity: 0.95;
    text-shadow: 0 1px 3px rgba(0,0,0,0.4);
}

/* ============================================================
   STORY PANEL
   ============================================================ */
.story-panel {
    background: linear-gradient(135deg, #2c1810, #3d2317);
    padding: 14px 20px;
    border-bottom: 3px solid #ffd700;
    color: #ffd700;
    font-size: 0.85em;
    min-height: 50px;
    display: flex;
    align-items: center;
    font-style: italic;
    text-shadow: 0 0 10px rgba(255,215,0,0.5);
    box-shadow: inset 0 0 20px rgba(255,215,0,0.1);
}

/* ============================================================
   INTRO PAGE
   ============================================================ */
.intro-panel {
    padding: 30px 25px;
    background: linear-gradient(135deg, #0f3460, #1a1a2e);
    min-height: 520px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    position: relative;
    overflow: hidden;
}

.intro-panel::before {
    content: '🌲🌳🌲🌳🌲';
    position: absolute;
    top: 10px; left: 0; right: 0;
    text-align: center;
    font-size: 1.5em;
    opacity: 0.3;
    letter-spacing: 30px;
}

.intro-title {
    text-align: center;
    color: #ffd700;
    font-size: 1.6em;
    margin-bottom: 20px;
    font-weight: bold;
    text-shadow: 0 0 20px rgba(255,215,0,0.8), 0 0 40px rgba(255,215,0,0.4);
    animation: pulseGlow 2s infinite;
}

@keyframes pulseGlow {
    0%, 100% { text-shadow: 0 0 20px rgba(255,215,0,0.8), 0 0 40px rgba(255,215,0,0.4); }
    50% { text-shadow: 0 0 30px rgba(255,215,0,1), 0 0 60px rgba(255,215,0,0.6); }
}

.pesan-rahasia-intro {
    background: linear-gradient(135deg, rgba(255,215,0,0.15), rgba(255,140,0,0.1));
    border: 3px solid #ffd700;
    padding: 25px;
    border-radius: 15px;
    margin: 15px 0;
    color: #ffd700;
    font-size: 0.9em;
    line-height: 1.8;
    max-width: 600px;
    box-shadow: 0 0 30px rgba(255,215,0,0.3), inset 0 0 30px rgba(255,215,0,0.1);
    animation: boxGlow 3s infinite;
    position: relative;
}

@keyframes boxGlow {
    0%, 100% { box-shadow: 0 0 30px rgba(255,215,0,0.3), inset 0 0 30px rgba(255,215,0,0.1); }
    50% { box-shadow: 0 0 50px rgba(255,215,0,0.5), inset 0 0 40px rgba(255,215,0,0.2); }
}

.pesan-rahasia-intro .pesan-judul {
    font-size: 1.1em;
    font-weight: bold;
    margin-bottom: 15px;
    text-align: center;
}
.pesan-rahasia-intro .pesan-isi {
    color: #fff;
    font-style: italic;
}
.pesan-rahasia-intro .pesan-penting {
    margin-top: 15px;
    padding-top: 15px;
    border-top: 1px dashed #ffd700;
    color: #ff7676;
    font-weight: bold;
    text-align: center;
    animation: pulseRed 1.5s infinite;
}

@keyframes pulseRed {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.6; }
}

/* ============================================================
   PROGRESS TRACKER
   ============================================================ */
.progress-tracker {
    display: flex;
    justify-content: space-around;
    padding: 12px 8px;
    background: linear-gradient(180deg, #0a0a15, #15152a);
    border-bottom: 2px solid rgba(102,126,234,0.3);
}
.progress-item {
    text-align: center;
    font-size: 0.6em;
    color: #555;
    flex: 1;
    transition: all 0.4s;
    position: relative;
}
.progress-item .icon {
    font-size: 1.6em;
    display: block;
    transition: all 0.4s;
    filter: grayscale(1);
}
.progress-item.done {
    color: #28a745;
    text-shadow: 0 0 10px rgba(40,167,69,0.6);
}
.progress-item.done .icon { filter: grayscale(0); }
.progress-item.active {
    color: #ffd700;
    text-shadow: 0 0 15px rgba(255,215,0,0.8);
    transform: scale(1.15);
}
.progress-item.active .icon {
    filter: grayscale(0);
    animation: pulse 1s infinite;
}
@keyframes pulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.2); }
}

/* ============================================================
   GAME SCREEN & MAZE
   ============================================================ */
.game-screen {
    position: relative;
    height: 350px;
    background: linear-gradient(180deg, #0a2818, #0d2818);
    overflow: hidden;
    box-shadow: inset 0 0 40px rgba(0,0,0,0.5);
}

.maze {
    position: absolute;
    inset: 0;
    display: grid;
    grid-template-columns: repeat(10, 10%);
    grid-template-rows: repeat(7, 14.28%);
}

.cell {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
}
.cell.path {
    background: linear-gradient(135deg, #1a4d2e, #215c37);
    border: 1px solid #0d2818;
}
.cell.wall { background: #0d2818; }
.cell.tree::before {
    content: '🌲';
    font-size: 1.6em;
    filter: drop-shadow(0 2px 4px rgba(0,0,0,0.5));
}
.cell.rock::before {
    content: '🪨';
    font-size: 1.3em;
    filter: drop-shadow(0 2px 4px rgba(0,0,0,0.5));
}

/* ============================================================
   PLAYER & ENTITAS
   ============================================================ */
.player {
    position: absolute;
    z-index: 20;
    transition: all 0.3s ease;
    pointer-events: none;
    transform: translate(-50%, -50%);
    filter: drop-shadow(0 0 15px rgba(102,126,234,0.9));
    animation: playerFloat 1.5s infinite;
}
@keyframes playerFloat {
    0%, 100% { transform: translate(-50%, -50%); }
    50% { transform: translate(-50%, -55%); }
}

.entitas {
    position: absolute;
    z-index: 10;
    transform: translate(-50%, -50%);
    cursor: pointer;
    transition: all 0.3s ease;
    animation: entitasBounce 1.5s infinite;
}
@keyframes entitasBounce {
    0%, 100% { transform: translate(-50%, -50%) scale(1); }
    50% { transform: translate(-50%, -55%) scale(1.1); }
}

.entitas.peti {
    filter: drop-shadow(0 0 20px rgba(255,215,0,1));
    animation: petiShake 2s infinite;
}
@keyframes petiShake {
    0%, 100% { transform: translate(-50%, -50%) scale(1); }
    50% { transform: translate(-50%, -55%) scale(1.15); }
}

.entitas.pintu {
    filter: drop-shadow(0 0 25px rgba(40,167,69,1));
    animation: pintuGlow 1.5s infinite;
}
@keyframes pintuGlow {
    0%, 100% { transform: translate(-50%, -50%) scale(1); filter: drop-shadow(0 0 25px rgba(40,167,69,1)); }
    50% { transform: translate(-50%, -55%) scale(1.1); filter: drop-shadow(0 0 40px rgba(40,167,69,1)); }
}

.entitas.npc {
    filter: drop-shadow(0 0 12px rgba(102,126,234,0.9));
}

.entitas-label {
    position: absolute;
    top: -25px;
    left: 50%;
    transform: translateX(-50%);
    background: linear-gradient(135deg, #ffd700, #ff8c00);
    color: #000;
    padding: 4px 10px;
    border-radius: 12px;
    font-size: 0.65em;
    font-weight: bold;
    white-space: nowrap;
    box-shadow: 0 4px 10px rgba(0,0,0,0.4);
    animation: labelBounce 1s infinite;
}
@keyframes labelBounce {
    0%, 100% { transform: translateX(-50%) translateY(0); }
    50% { transform: translateX(-50%) translateY(-3px); }
}

/* ============================================================
   HUD INFO
   ============================================================ */
.game-info {
    display: flex;
    justify-content: space-around;
    padding: 10px;
    background: linear-gradient(180deg, #15152a, #0a0a15);
    font-size: 0.8em;
    flex-wrap: wrap;
    gap: 5px;
    border-top: 2px solid rgba(102,126,234,0.3);
}
.info-item {
    display: flex;
    align-items: center;
    gap: 5px;
    background: rgba(102,126,234,0.1);
    padding: 5px 12px;
    border-radius: 20px;
    border: 1px solid rgba(102,126,234,0.3);
}
.info-item .value {
    color: #ffd700;
    font-weight: bold;
    text-shadow: 0 0 8px rgba(255,215,0,0.6);
}

/* ============================================================
   KONTROL
   ============================================================ */
.game-kontrol {
    display: flex;
    justify-content: center;
    gap: 10px;
    padding: 15px;
    background: linear-gradient(180deg, #0a0a15, #15152a);
    flex-wrap: wrap;
    border-top: 1px solid rgba(102,126,234,0.2);
}
.control-btn {
    width: 58px;
    height: 58px;
    background: linear-gradient(145deg, #667eea, #764ba2);
    border: 2px solid rgba(255,255,255,0.2);
    border-radius: 15px;
    color: white;
    font-size: 1.4em;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    user-select: none;
    -webkit-tap-highlight-color: transparent;
    box-shadow: 0 6px 15px rgba(102,126,234,0.4), inset 0 2px 4px rgba(255,255,255,0.2);
    transition: all 0.15s;
}
.control-btn:hover {
    background: linear-gradient(145deg, #764ba2, #667eea);
    transform: translateY(-2px);
    box-shadow: 0 10px 25px rgba(102,126,234,0.6);
}
.control-btn:active {
    transform: scale(0.92);
    box-shadow: 0 3px 8px rgba(102,126,234,0.4);
}
.control-btn.aksi {
    background: linear-gradient(145deg, #ff6b6b, #ee5a24);
    width: 75px;
    box-shadow: 0 6px 15px rgba(255,107,107,0.5), inset 0 2px 4px rgba(255,255,255,0.2);
}
.control-btn.aksi:hover {
    background: linear-gradient(145deg, #ee5a24, #ff6b6b);
    box-shadow: 0 10px 25px rgba(255,107,107,0.7);
}

/* ============================================================
   KONTEN AREA
   ============================================================ */
.game-konten {
    padding: 20px;
    min-height: 220px;
    background: linear-gradient(180deg, #0f3460, #1a1a2e);
    color: #ddd;
}
.game-konten h2 {
    color: #ffd700;
    margin-bottom: 12px;
    font-size: 1.15em;
    text-shadow: 0 0 10px rgba(255,215,0,0.5);
}
.game-konten h3 {
    color: #ffd700;
    margin: 15px 0 10px 0;
    font-size: 1em;
    text-shadow: 0 0 8px rgba(255,215,0,0.4);
}
.game-konten p {
    line-height: 1.6;
    margin-bottom: 8px;
    font-size: 0.88em;
}

.dialog-box {
    background: linear-gradient(135deg, rgba(102,126,234,0.1), rgba(118,75,162,0.1));
    padding: 14px;
    border-radius: 12px;
    border-left: 4px solid #667eea;
    margin: 10px 0;
    box-shadow: 0 4px 15px rgba(0,0,0,0.2);
}
.dialog-box .nama {
    color: #ffd700;
    font-weight: bold;
    margin-bottom: 6px;
    text-shadow: 0 0 8px rgba(255,215,0,0.4);
}

/* ============================================================
   BUTTONS
   ============================================================ */
.btn-group {
    display: flex;
    gap: 10px;
    margin-top: 12px;
    flex-wrap: wrap;
}
.btn {
    flex: 1;
    min-width: 100px;
    background: linear-gradient(145deg, #667eea, #764ba2);
    color: white;
    border: 2px solid rgba(255,255,255,0.1);
    padding: 13px 15px;
    border-radius: 12px;
    font-size: 0.9em;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.15s;
    -webkit-tap-highlight-color: transparent;
    box-shadow: 0 6px 15px rgba(102,126,234,0.4), inset 0 2px 4px rgba(255,255,255,0.2);
}
.btn:hover {
    background: linear-gradient(145deg, #764ba2, #667eea);
    transform: translateY(-2px);
    box-shadow: 0 10px 25px rgba(102,126,234,0.6);
}
.btn:active { transform: translateY(0) scale(0.98); }
.btn.success {
    background: linear-gradient(145deg, #28a745, #20c997);
    box-shadow: 0 6px 15px rgba(40,167,69,0.4), inset 0 2px 4px rgba(255,255,255,0.2);
}
.btn.success:hover {
    background: linear-gradient(145deg, #20c997, #28a745);
    box-shadow: 0 10px 25px rgba(40,167,69,0.6);
}
.btn.danger {
    background: linear-gradient(145deg, #dc3545, #c82333);
    box-shadow: 0 6px 15px rgba(220,53,69,0.4), inset 0 2px 4px rgba(255,255,255,0.2);
}
.btn.danger:hover {
    background: linear-gradient(145deg, #c82333, #dc3545);
    box-shadow: 0 10px 25px rgba(220,53,69,0.6);
}
.btn.info {
    background: linear-gradient(145deg, #17a2b8, #138496);
    box-shadow: 0 6px 15px rgba(23,162,184,0.4), inset 0 2px 4px rgba(255,255,255,0.2);
}
.btn.info:hover {
    background: linear-gradient(145deg, #138496, #17a2b8);
}

/* ============================================================
   INPUT
   ============================================================ */
input {
    width: 100%;
    padding: 12px 15px;
    border: 2px solid rgba(102,126,234,0.3);
    background: linear-gradient(135deg, #1a1a2e, #15152a);
    color: white;
    border-radius: 10px;
    font-size: 0.95em;
    margin-bottom: 10px;
    transition: all 0.3s;
    font-family: inherit;
}
input:focus {
    outline: none;
    border-color: #ffd700;
    box-shadow: 0 0 20px rgba(255,215,0,0.4);
    background: linear-gradient(135deg, #1a1a2e, #202040);
}
input::placeholder { color: #666; }

label {
    display: block;
    margin-bottom: 6px;
    font-size: 0.85em;
    color: #a6e3a1;
    font-weight: bold;
    text-shadow: 0 0 5px rgba(166,227,161,0.3);
}

/* ============================================================
   HITUNG BOX
   ============================================================ */
.hitung-box {
    background: linear-gradient(135deg, rgba(40,167,69,0.1), rgba(40,167,69,0.05));
    border-left: 4px solid #28a745;
    padding: 14px;
    border-radius: 12px;
    margin: 12px 0;
    font-family: 'Courier New', monospace;
    font-size: 0.72em;
    white-space: pre-wrap;
    color: #a6e3a1;
    max-height: 320px;
    overflow-y: auto;
    line-height: 1.6;
    box-shadow: inset 0 0 20px rgba(40,167,69,0.1);
    text-shadow: 0 0 3px rgba(166,227,161,0.3);
}

/* ============================================================
   TERSANGKA GRID
   ============================================================ */
.tersangka-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
    margin: 15px 0;
}
.tersangka-card {
    background: linear-gradient(145deg, rgba(255,255,255,0.05), rgba(255,255,255,0.02));
    border: 3px solid #2c2c3e;
    border-radius: 15px;
    padding: 18px 10px;
    cursor: pointer;
    transition: all 0.3s;
    text-align: center;
    user-select: none;
    position: relative;
    overflow: hidden;
}
.tersangka-card:hover {
    border-color: #667eea;
    background: linear-gradient(145deg, rgba(102,126,234,0.15), rgba(118,75,162,0.1));
    transform: translateY(-5px);
    box-shadow: 0 15px 30px rgba(102,126,234,0.4);
}
.tersangka-card.selected {
    border-color: #ffd700;
    background: linear-gradient(145deg, rgba(255,215,0,0.2), rgba(255,140,0,0.1));
    transform: scale(1.05);
    box-shadow: 0 15px 35px rgba(255,215,0,0.5);
}
.tersangka-body {
    display: block;
    margin-bottom: 10px;
    filter: drop-shadow(0 4px 8px rgba(0,0,0,0.3));
}
.tersangka-body svg {
    width: 55px;
    height: 110px;
}
.tersangka-nama {
    font-size: 0.95em;
    font-weight: bold;
    color: #ffd700;
    text-shadow: 0 0 8px rgba(255,215,0,0.5);
}

/* ============================================================
   TABEL VERIFIKASI
   ============================================================ */
.tabel-verifikasi {
    width: 100%;
    border-collapse: collapse;
    margin: 12px 0;
    font-size: 0.78em;
    background: rgba(0,0,0,0.2);
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 4px 15px rgba(0,0,0,0.3);
}
.tabel-verifikasi th {
    background: linear-gradient(135deg, #667eea, #764ba2);
    color: #ffd700;
    padding: 10px;
    text-align: left;
    font-weight: bold;
}
.tabel-verifikasi td {
    padding: 10px;
    color: #ddd;
    border-bottom: 1px solid rgba(255,255,255,0.08);
}
.tabel-verifikasi tr.benar td {
    background: linear-gradient(90deg, rgba(40,167,69,0.3), rgba(40,167,69,0.1));
    color: #28a745;
    font-weight: bold;
}
.tabel-verifikasi tr.salah td {
    background: linear-gradient(90deg, rgba(220,53,69,0.2), rgba(220,53,69,0.05));
    color: #dc3545;
}

/* ============================================================
   SKOR PANEL
   ============================================================ */
.skor-panel {
    background: linear-gradient(135deg, rgba(255,215,0,0.15), rgba(255,140,0,0.08));
    border: 2px solid #ffd700;
    border-radius: 15px;
    padding: 20px;
    text-align: center;
    margin: 15px 0;
    box-shadow: 0 0 30px rgba(255,215,0,0.3);
}
.skor-panel .skor-besar {
    font-size: 3em;
    font-weight: bold;
    color: #ffd700;
    text-shadow: 0 0 30px rgba(255,215,0,0.8);
    line-height: 1;
}
.skor-panel .skor-label {
    font-size: 0.8em;
    color: #a6e3a1;
    margin-top: 5px;
    letter-spacing: 2px;
}
.skor-panel .skor-detail {
    display: flex;
    justify-content: space-around;
    margin-top: 15px;
    flex-wrap: wrap;
    gap: 10px;
}
.skor-panel .skor-item {
    background: rgba(0,0,0,0.3);
    padding: 8px 15px;
    border-radius: 10px;
    font-size: 0.8em;
}
.skor-panel .skor-item .angka {
    color: #ffd700;
    font-weight: bold;
    font-size: 1.2em;
    display: block;
    margin-top: 3px;
}

/* ============================================================
   LEADERBOARD
   ============================================================ */
.leaderboard {
    background: linear-gradient(135deg, rgba(102,126,234,0.1), rgba(118,75,162,0.05));
    border: 2px solid rgba(102,126,234,0.4);
    border-radius: 15px;
    padding: 15px;
    margin: 15px 0;
}
.leaderboard h3 {
    color: #ffd700;
    margin-bottom: 10px;
    text-align: center;
    font-size: 1em;
}
.leaderboard-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 8px 12px;
    background: rgba(0,0,0,0.3);
    border-radius: 8px;
    margin-bottom: 6px;
    font-size: 0.85em;
}
.leaderboard-item.medali-1 { border-left: 4px solid #ffd700; }
.leaderboard-item.medali-2 { border-left: 4px solid #c0c0c0; }
.leaderboard-item.medali-3 { border-left: 4px solid #cd7f32; }
.leaderboard-item.medali-aktif {
    background: linear-gradient(90deg, rgba(255,215,0,0.2), rgba(255,215,0,0.05));
    border: 1px solid #ffd700;
}
.leaderboard-item .nama-pemain {
    color: #ffd700;
    font-weight: bold;
}
.leaderboard-item .skor-pemain {
    color: #a6e3a1;
    font-weight: bold;
}

/* ============================================================
   NOTIFIKASI
   ============================================================ */
.notif {
    position: fixed;
    top: 20px;
    left: 50%;
    transform: translateX(-50%) translateY(-100px);
    background: linear-gradient(135deg, #28a745, #20c997);
    color: white;
    padding: 14px 30px;
    border-radius: 30px;
    font-weight: bold;
    font-size: 0.9em;
    z-index: 1000;
    transition: transform 0.5s cubic-bezier(0.68, -0.55, 0.265, 1.55);
    pointer-events: none;
    box-shadow: 0 10px 30px rgba(40,167,69,0.5);
    border: 2px solid rgba(255,255,255,0.2);
    max-width: 90%;
    text-align: center;
}
.notif.show { transform: translateX(-50%) translateY(0); }

/* ============================================================
   FINISH (MENANG / KALAH)
   ============================================================ */
.finish-menang {
    background: linear-gradient(135deg, #28a745, #20c997);
    padding: 30px 25px;
    border-radius: 20px;
    text-align: center;
    margin: 20px 0;
    box-shadow: 0 20px 50px rgba(40,167,69,0.5), inset 0 2px 4px rgba(255,255,255,0.3);
    animation: winPulse 1.5s infinite;
    position: relative;
    overflow: hidden;
}
.finish-menang::before {
    content: '🎉🎊✨🎉🎊✨🎉';
    position: absolute;
    top: 5px; left: 0; right: 0;
    text-align: center;
    font-size: 1.2em;
    opacity: 0.5;
    animation: floatDown 3s infinite;
}
@keyframes floatDown {
    0%, 100% { transform: translateY(-10px); opacity: 0.5; }
    50% { transform: translateY(0); opacity: 0.8; }
}
@keyframes winPulse {
    0%, 100% { box-shadow: 0 20px 50px rgba(40,167,69,0.5), inset 0 2px 4px rgba(255,255,255,0.3); }
    50% { box-shadow: 0 25px 60px rgba(40,167,69,0.8), inset 0 2px 4px rgba(255,255,255,0.3); }
}
.finish-menang .icon {
    font-size: 4.5em;
    margin-bottom: 10px;
    animation: bounce 1s infinite;
}
@keyframes bounce {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-15px); }
}
.finish-menang h2 {
    color: white;
    font-size: 1.8em;
    margin-bottom: 10px;
    text-shadow: 0 3px 10px rgba(0,0,0,0.4);
}
.finish-menang p { color: white; font-size: 1em; }

.finish-kalah {
    background: linear-gradient(135deg, #dc3545, #721c24);
    padding: 30px 25px;
    border-radius: 20px;
    text-align: center;
    margin: 20px 0;
    box-shadow: 0 20px 50px rgba(220,53,69,0.5), inset 0 2px 4px rgba(255,255,255,0.2);
    animation: losePulse 2s infinite;
}
@keyframes losePulse {
    0%, 100% { box-shadow: 0 20px 50px rgba(220,53,69,0.5); }
    50% { box-shadow: 0 25px 60px rgba(220,53,69,0.8); }
}
.finish-kalah .icon {
    font-size: 4.5em;
    margin-bottom: 10px;
    animation: shake 0.8s infinite;
}
@keyframes shake {
    0%, 100% { transform: rotate(0deg); }
    25% { transform: rotate(-5deg); }
    75% { transform: rotate(5deg); }
}
.finish-kalah h2 {
    color: white;
    font-size: 1.8em;
    margin-bottom: 10px;
}
.finish-kalah p { color: white; font-size: 1em; }

/* ============================================================
   UTIL
   ============================================================ */
.hidden { display: none; }

::-webkit-scrollbar { width: 8px; }
::-webkit-scrollbar-track { background: rgba(0,0,0,0.3); border-radius: 10px; }
::-webkit-scrollbar-thumb {
    background: linear-gradient(135deg, #667eea, #764ba2);
    border-radius: 10px;
}

/* ============================================================
   RESPONSIVE
   ============================================================ */
@media (max-width: 600px) {
    .game-screen { height: 280px; }
    .control-btn { width: 50px; height: 50px; font-size: 1.2em; }
    .control-btn.aksi { width: 65px; }
    .tersangka-grid { gap: 6px; }
    .tersangka-body svg { width: 42px; height: 85px; }
    .tabel-verifikasi { font-size: 0.68em; }
    .pesan-rahasia-intro { padding: 18px; font-size: 0.8em; }
    .hitung-box { font-size: 0.65em; }
    .game-header h1 { font-size: 1.1em; }
    .skor-panel .skor-besar { font-size: 2.2em; }
}
</style>
</head>
<body>

<div class="game-wrapper">
    <div class="game-header">
        <h1>🎮 Crypto Imposter Adventure</h1>
        <p>3 Orang Tersesat &bull; 1 Imposter &bull; RSA + Current</p>
    </div>
    
    <!-- ==================== INTRO PAGE ==================== -->
    <div id="introPage" class="intro-panel">
        <div class="intro-title">📜 PESAN RAHASIA DITERIMA</div>
        <div class="pesan-rahasia-intro">
            <div class="pesan-judul">🔐 DARI: KEPALA DESA</div>
            <div class="pesan-isi">
                "3 orang tersesat di hutan labirin. Salah satunya adalah IMPOSTER.
                <br><br>
                Imposter memegang <strong>KUNCI PRIVAT</strong> untuk membuka peta keluar.
                <br><br>
                Kamu memegang <strong>KUNCI PUBLIK</strong>.
                <br><br>
                Temukan imposter dengan memecahkan puzzle RSA dan Algoritma Current!"
            </div>
            <div class="pesan-penting">
                ⚠️ NYAWA: 2 &bull; +2 POIN / LEVEL<br>
                Kalau salah 2 kali, kamu KALAH!
            </div>
        </div>
        <button class="btn success" type="button" id="btnMulai" 
                style="margin-top:20px;padding:15px 30px;font-size:1.05em;max-width:300px;">
            🎮 Mulai Petualangan
        </button>
    </div>
    
    <!-- ==================== GAME PAGE ==================== -->
    <div id="gamePage" class="hidden">
        <div class="story-panel">
            <span id="storyText">3 orang tersesat di hutan. Salah satunya imposter!</span>
        </div>
        
        <!-- Progress Tracker -->
        <div class="progress-tracker">
            <div class="progress-item active" id="pt-1">
                <div class="icon">📦</div>
                <div>Cari Peti</div>
            </div>
            <div class="progress-item" id="pt-2">
                <div class="icon">🔐</div>
                <div>Puzzle RSA</div>
            </div>
            <div class="progress-item" id="pt-3">
                <div class="icon">🧑</div>
                <div>Cari Ciri</div>
            </div>
            <div class="progress-item" id="pt-4">
                <div class="icon">🚪</div>
                <div>Pintu Keluar</div>
            </div>
            <div class="progress-item" id="pt-5">
                <div class="icon">🗺️</div>
                <div>Buka Peta</div>
            </div>
        </div>
        
        <!-- Game Screen (Maze) -->
        <div class="game-screen" id="gameScreen">
            <div class="maze" id="maze"></div>
        </div>
        
        <!-- HUD -->
        <div class="game-info">
            <div class="info-item">
                <span>👤</span>
                <span class="value" id="hudPemain">-</span>
            </div>
            <div class="info-item">
                <span>💬</span>
                <span class="value" id="hudCiri">0/3 Ciri</span>
            </div>
            <div class="info-item">
                <span>❤️</span>
                <span class="value" id="hudNyawa">2</span>
            </div>
            <div class="info-item">
                <span>⭐</span>
                <span class="value" id="hudSkor">0</span>
            </div>
            <div class="info-item">
                <span>🏆</span>
                <span class="value" id="hudLevel">Lv.1</span>
            </div>
        </div>
        
        <!-- Kontrol -->
        <div class="game-kontrol">
            <button class="control-btn" id="btnKiri" type="button">⬅️</button>
            <button class="control-btn" id="btnAtas" type="button">⬆️</button>
            <button class="control-btn" id="btnBawah" type="button">⬇️</button>
            <button class="control-btn" id="btnKanan" type="button">➡️</button>
            <button class="control-btn aksi" id="btnAksi" type="button">🎯</button>
        </div>
        
        <!-- Konten -->
        <div class="game-konten" id="gameKonten"></div>
    </div>
</div>

<div class="notif" id="notif"></div>

<script>
/* ============================================================
   1. KONSTANTA & DATA
   ============================================================ */

// Tabel Base Algoritma Current (dari Fibonacci + Hexagonal)
const TABEL_BASE = {
    'A': 101, 'B': 126, 'C': 523, 'D': 358, 'E': 548, 'F': 136,
    'G': 121, 'H': 340, 'I': 355, 'J': 890, 'K': 144, 'L': 336,
    'M': 577, 'N': 108, 'O': 587, 'P': 976, 'Q': 184, 'R': 810,
    'S': 365, 'T': 460, 'U': 111, 'V': 546, 'W': 562, 'X': 168,
    'Y': 578, 'Z': 946
};

// Reverse lookup: nilai → huruf
const TABEL_BASE_INV = {};
for (const h in TABEL_BASE) TABEL_BASE_INV[TABEL_BASE[h]] = h;

const HURUF = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ';

// Pool nama & ciri karakter
const POOL_KARAKTER = [
    {nama: 'Michael', ciri: 'AKU SUKA PAKAI TOPI MERAH', warna: '#FFD700', peta: 'Utara 100m, lalu kiri'},
    {nama: 'Citra',   ciri: 'AKU SUKA BACA BUKU',        warna: '#4ECDC4', peta: 'Selatan 50m, lalu kanan'},
    {nama: 'Dedi',    ciri: 'AKU SUKA MAIN BOLA',        warna: '#BB8FCE', peta: 'Timur 200m, lurus terus'},
    {nama: 'Eka',     ciri: 'AKU SUKA MINUM KOPI',       warna: '#A8E6CF', peta: 'Barat 75m, lalu kanan'},
    {nama: 'Fani',    ciri: 'AKU SUKA DENGAR MUSIK',     warna: '#FF8B94', peta: 'Utara 150m, lalu kiri'},
    {nama: 'Gilang',  ciri: 'AKU SUKA JALAN-JALAN',      warna: '#C7CEEA', peta: 'Selatan 300m, lurus'},
    {nama: 'Hana',    ciri: 'AKU SUKA MAKAN NASI GORENG',warna: '#FFB6B9', peta: 'Timur 120m, lalu kanan'}
];

// Maze layout (0 = jalan, 1 = tembok)
const MAZE = [
    [1,1,1,1,1,1,1,1,1,1],
    [1,0,0,0,0,0,0,0,0,1],
    [1,0,1,0,1,0,1,0,0,1],
    [0,0,1,0,0,0,1,0,0,0],
    [1,0,1,1,1,0,1,0,0,1],
    [1,0,0,0,0,0,0,0,0,1],
    [1,1,1,1,1,1,1,1,1,1]
];

/* ============================================================
   2. STATE GAME
   ============================================================ */
const game = {
    // Posisi pemain di maze
    playerRow: 3,
    playerCol: 0,
    
    // Statistik sesi
    nyawa: 2,
    skor: 0,
    level: 1,
    
    // RSA & Current
    p: 41, q: 43,
    rsa: null,
    kunciCurrent: 7,
    pesanCiri: '',
    encArr: [],
    encStr: '',
    
    // Karakter & imposter
    karakter: [],      // 3 karakter (NPC) di hutan
    imposter: null,    // salah satu dari karakter
    dataImposter: null,
    posisiNPC: [],
    
    // Progress
    sudahBukaPeti: false,
    ciriDitemukan: [false, false, false],
    tebakan: null,
    
    // Posisi objek
    posisiPeti: {row: 1, col: 4},
    posisiPintu: {row: 3, col: 9},
    
    // Pemain aktif (yang main)
    pemainAktif: '',
    
    // Skor per pemain (leaderboard)
    leaderboard: {}
};

/* ============================================================
   3. ALGORITMA CURRENT (Shift Alfabet - MOD 26)
   ============================================================ */

/**
 * Enkripsi Algoritma Current
 * Rumus: C = TABEL_BASE[(pos + (kunci-1)) mod 26]
 */
function currentEncrypt(plaintext, kunci) {
    plaintext = plaintext.toUpperCase();
    const offset = (kunci - 1) % 26;
    const out = [];
    
    for (const c of plaintext) {
        if (c === ' ') {
            out.push('SP');
        } else {
            const idx = HURUF.indexOf(c);
            if (idx !== -1) {
                const posBaru = (idx + offset) % 26;
                out.push(TABEL_BASE[HURUF[posBaru]]);
            }
        }
    }
    return out;
}

/**
 * Dekripsi Algoritma Current
 * Rumus: M = HURUF[(posCipher - (kunci-1) + 26) mod 26]
 */
function currentDecrypt(cipherArr, kunci) {
    const offset = (kunci - 1) % 26;
    let out = '';
    
    for (const t of cipherArr) {
        if (t === 'SP') {
            out += ' ';
        } else {
            const hurufCipher = TABEL_BASE_INV[parseInt(t)];
            if (hurufCipher) {
                const idxCipher = HURUF.indexOf(hurufCipher);
                const posAsli = ((idxCipher - offset) % 26 + 26) % 26;
                out += HURUF[posAsli];
            }
        }
    }
    return out;
}

/* ============================================================
   4. ALGORITMA RSA
   ============================================================ */

function gcd(a, b) {
    while (b) { [a, b] = [b, a % b]; }
    return a;
}

function modInverse(e, phi) {
    for (let d = 2; d < phi; d++) {
        if ((e * d) % phi === 1) return d;
    }
    return null;
}

function generateRSA(p, q) {
    const n = p * q;
    const phi = (p - 1) * (q - 1);
    let e = 3;
    while (e < phi && gcd(e, phi) !== 1) e += 2;
    const d = modInverse(e, phi);
    return { e, d, n, phi, p, q };
}

/* ============================================================
   5. UTILITAS
   ============================================================ */

function shuffle(arr) {
    const a = arr.slice();
    for (let i = a.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [a[i], a[j]] = [a[j], a[i]];
    }
    return a;
}

function randInt(min, max) {
    return Math.floor(Math.random() * (max - min + 1)) + min;
}

function showNotif(msg) {
    const n = document.getElementById('notif');
    n.textContent = msg;
    n.classList.add('show');
    setTimeout(() => n.classList.remove('show'), 2000);
}

function setStory(text) {
    document.getElementById('storyText').textContent = text;
}

function setProgress(step) {
    for (let i = 1; i <= 5; i++) {
        const el = document.getElementById('pt-' + i);
        el.className = 'progress-item';
        if (i < step) el.classList.add('done');
        else if (i === step) el.classList.add('active');
    }
}

function updateHUD() {
    const jmlCiri = game.ciriDitemukan.filter(Boolean).length;
    document.getElementById('hudPemain').textContent = game.pemainAktif || '-';
    document.getElementById('hudCiri').textContent = jmlCiri + '/3 Ciri';
    document.getElementById('hudNyawa').textContent = game.nyawa;
    document.getElementById('hudSkor').textContent = game.skor;
    document.getElementById('hudLevel').textContent = 'Lv.' + game.level;
}

function getCellPosition(row, col) {
    const cellW = 100 / 10;
    const cellH = 100 / 7;
    return {
        left: (col * cellW + cellW / 2) + '%',
        top: (row * cellH + cellH / 2) + '%'
    };
}

function buatSVGKarakter(warna) {
    return '<svg viewBox="0 0 50 100" style="width:48px;height:96px;">' +
        '<circle cx="25" cy="20" r="15" fill="#FFD700"/>' +
        '<circle cx="20" cy="17" r="2" fill="#000"/>' +
        '<circle cx="30" cy="17" r="2" fill="#000"/>' +
        '<path d="M 19 25 Q 25 30 31 25" stroke="#000" fill="none" stroke-width="1.5"/>' +
        '<rect x="15" y="36" width="20" height="35" fill="' + warna + '" rx="3"/>' +
        '<rect x="5" y="40" width="10" height="25" fill="' + warna + '" rx="3"/>' +
        '<rect x="35" y="40" width="10" height="25" fill="' + warna + '" rx="3"/>' +
        '<rect x="17" y="70" width="7" height="25" fill="#333" rx="2"/>' +
        '<rect x="26" y="70" width="7" height="25" fill="#333" rx="2"/>' +
        '</svg>';
}

/* ============================================================
   6. LEADERBOARD
   ============================================================ */

function tambahSkorPemain(nama, poin) {
    if (!game.leaderboard[nama]) game.leaderboard[nama] = 0;
    game.leaderboard[nama] += poin;
}

function renderLeaderboard() {
    const entries = Object.entries(game.leaderboard)
        .sort((a, b) => b[1] - a[1]);
    
    if (entries.length === 0) {
        return '<div class="leaderboard"><h3>🏆 Leaderboard</h3><p style="text-align:center;font-size:0.85em;color:#888;">Belum ada skor</p></div>';
    }
    
    let html = '<div class="leaderboard"><h3>🏆 Leaderboard</h3>';
    entries.forEach(([nama, skor], i) => {
        let cls = 'leaderboard-item';
        if (i === 0) cls += ' medali-1';
        else if (i === 1) cls += ' medali-2';
        else if (i === 2) cls += ' medali-3';
        if (nama === game.pemainAktif) cls += ' medali-aktif';
        
        const medali = i === 0 ? '🥇' : i === 1 ? '🥈' : i === 2 ? '🥉' : '  ';
        html += '<div class="' + cls + '">';
        html += '<span class="nama-pemain">' + medali + ' ' + nama + '</span>';
        html += '<span class="skor-pemain">' + skor + ' poin</span>';
        html += '</div>';
    });
    html += '</div>';
    return html;
}

/* ============================================================
   7. SETUP FORM (PEMAIN AKTIF & KARAKTER)
   ============================================================ */

function tampilkanFormSetup() {
    // Ambil 3 karakter random dari pool (untuk default)
    const pool = shuffle(POOL_KARAKTER);
    game.karakter = [pool[0], pool[1], pool[2]];
    
    const savedPemain = game.pemainAktif || '';
    const savedKarakter = game.karakter.map(k => k.nama);
    
    let html = '<h2>🎮 Setup Permainan</h2>';
    
    // === Form Pemain Aktif ===
    html += '<h3>👤 Siapa yang Main?</h3>';
    html += '<label>Nama Pemain</label>';
    html += '<input type="text" id="inputPemainAktif" value="' + savedPemain + '" maxlength="15" placeholder="Contoh: Andi">';
    
    // === Form Karakter NPC ===
    html += '<h3 style="margin-top:20px;">🧑 3 Karakter di Hutan (bisa diubah)</h3>';
    for (let i = 0; i < 3; i++) {
        html += '<label>Karakter ' + (i + 1) + '</label>';
        html += '<input type="text" id="inputKarakter' + i + '" value="' + savedKarakter[i] + '" maxlength="15" placeholder="Nama karakter">';
    }
    
    // === Leaderboard ===
    html += renderLeaderboard();
    
    // === Tombol ===
    html += '<div class="btn-group">';
    html += '<button class="btn" type="button" id="btnAcakNama">🎲 Acak Karakter</button>';
    html += '<button class="btn success" type="button" id="btnMulaiMain">✅ Simpan & Mulai</button>';
    html += '</div>';
    
    document.getElementById('gameKonten').innerHTML = html;
    
    // Event listeners
    document.getElementById('btnAcakNama').onclick = acakKarakter;
    document.getElementById('btnMulaiMain').onclick = simpanSetupDanMulai;
}

function acakKarakter() {
    const pool = shuffle(POOL_KARAKTER);
    for (let i = 0; i < 3; i++) {
        document.getElementById('inputKarakter' + i).value = pool[i].nama;
    }
    showNotif('🎲 Karakter diacak!');
}

function simpanSetupDanMulai() {
    const namaPemain = document.getElementById('inputPemainAktif').value.trim();
    const namaKarakter = [0, 1, 2].map(i => 
        document.getElementById('inputKarakter' + i).value.trim()
    );
    
    // Validasi
    if (!namaPemain) {
        showNotif('❌ Nama pemain harus diisi!');
        return;
    }
    if (namaKarakter.some(n => !n)) {
        showNotif('❌ Semua nama karakter harus diisi!');
        return;
    }
    if (new Set(namaKarakter).size !== 3) {
        showNotif('❌ Nama karakter tidak boleh sama!');
        return;
    }
    
    // Simpan pemain aktif
    game.pemainAktif = namaPemain;
    
    // Update nama karakter
    for (let i = 0; i < 3; i++) {
        game.karakter[i].nama = namaKarakter[i];
    }
    
    // Mulai level 1
    mulaiLevelBaru();
}

/* ============================================================
   8. LEVEL & ROUND MANAGEMENT
   ============================================================ */

/**
 * Memulai level baru (pesan & imposter baru)
 * Dipakai untuk: level 1, lanjut level, dan ulang level
 */
function mulaiLevelBaru() {
    // Reset posisi & progress
    game.playerRow = 3;
    game.playerCol = 0;
    game.nyawa = 2;
    game.sudahBukaPeti = false;
    game.ciriDitemukan = [false, false, false];
    game.tebakan = null;
    
    // Generate RSA baru
    game.rsa = generateRSA(game.p, game.q);
    
    // Generate kunci Current random (1-26)
    game.kunciCurrent = randInt(1, 26);
    
    // Pilih imposter random dari 3 karakter
    const idxImposter = randInt(0, 2);
    game.imposter = game.karakter[idxImposter];
    game.dataImposter = {ciri: game.imposter.ciri};
    game.pesanCiri = game.imposter.ciri.toUpperCase();
    
    // Enkripsi ciri imposter dengan Current
    game.encArr = currentEncrypt(game.pesanCiri, game.kunciCurrent);
    game.encStr = game.encArr.join(',');
    
    // Posisi NPC di maze
    game.posisiNPC = [
        {row: 1, col: 1},
        {row: 5, col: 4},
        {row: 1, col: 7}
    ];
    
    // Update UI
    buildMaze();
    renderEntitas();
    updateHUD();
    setProgress(1);
    setStory('🔺 Level ' + game.level + ' — Jalan ke 📦 untuk mulai!');
    
    // Tampilkan info level
    document.getElementById('gameKonten').innerHTML = 
        '<h2>🔺 Level ' + game.level + '</h2>' +
        '<p>Pemain: <strong style="color:#ffd700;">' + game.pemainAktif + '</strong></p>' +
        '<p>Pesan rahasia baru sudah dikirim! Imposter sudah bersembunyi.</p>' +
        '<div class="hitung-box">' +
        '⭐ Skor Saat Ini: ' + game.skor + '\n' +
        '❤️ Nyawa: ' + game.nyawa + '\n' +
        '🎯 Misi: Temukan imposter untuk +2 poin!' +
        '</div>' +
        '<p style="color:#ffd700;">📦 Jalan ke peti untuk mulai!</p>';
}

/* ============================================================
   9. MAZE & RENDER
   ============================================================ */

function buildMaze() {
    const mazeEl = document.getElementById('maze');
    mazeEl.innerHTML = '';
    
    for (let r = 0; r < 7; r++) {
        for (let c = 0; c < 10; c++) {
            const cell = document.createElement('div');
            cell.className = 'cell';
            
            if (MAZE[r][c] === 1) {
                cell.classList.add('wall');
                if (r === 0 || r === 6 || c === 0 || c === 9) {
                    cell.classList.add('tree');
                } else {
                    cell.classList.add('rock');
                }
            } else {
                cell.classList.add('path');
            }
            mazeEl.appendChild(cell);
        }
    }
}

function renderEntitas() {
    const screen = document.getElementById('gameScreen');
    
    // Hapus entitas lama
    screen.querySelectorAll('.entitas, .player').forEach(el => el.remove());
    
    // Render player
    const player = document.createElement('div');
    player.className = 'player';
    player.innerHTML = buatSVGKarakter('#667eea');
    const posP = getCellPosition(game.playerRow, game.playerCol);
    player.style.left = posP.left;
    player.style.top = posP.top;
    screen.appendChild(player);
    
    // Render peti (kalau belum dibuka)
    if (!game.sudahBukaPeti) {
        const peti = document.createElement('div');
        peti.className = 'entitas peti';
        peti.innerHTML = '<span style="font-size:2.8em;">📦</span><div class="entitas-label">Peti</div>';
        const pos = getCellPosition(game.posisiPeti.row, game.posisiPeti.col);
        peti.style.left = pos.left;
        peti.style.top = pos.top;
        screen.appendChild(peti);
    }
    
    // Render NPC
    for (let j = 0; j < game.posisiNPC.length; j++) {
        const npc = document.createElement('div');
        npc.className = 'entitas npc';
        npc.innerHTML = buatSVGKarakter(game.karakter[j].warna) +
            '<div class="entitas-label">' + game.karakter[j].nama + '</div>';
        const pos = getCellPosition(game.posisiNPC[j].row, game.posisiNPC[j].col);
        npc.style.left = pos.left;
        npc.style.top = pos.top;
        screen.appendChild(npc);
    }
    
    // Render pintu (kalau peti sudah dibuka)
    if (game.sudahBukaPeti) {
        const pintu = document.createElement('div');
        pintu.className = 'entitas pintu';
        pintu.innerHTML = '<span style="font-size:3.2em;">🚪</span><div class="entitas-label">KELUAR</div>';
        const pos = getCellPosition(game.posisiPintu.row, game.posisiPintu.col);
        pintu.style.left = pos.left;
        pintu.style.top = pos.top;
        screen.appendChild(pintu);
    }
}

/* ============================================================
   10. GERAK & INTERAKSI
   ============================================================ */

function gerak(dr, dc) {
    const newRow = game.playerRow + dr;
    const newCol = game.playerCol + dc;
    
    if (newRow < 0 || newRow >= 7 || newCol < 0 || newCol >= 10) return;
    if (MAZE[newRow][newCol] === 1) return;
    
    game.playerRow = newRow;
    game.playerCol = newCol;
    renderEntitas();
    cekInteraksi();
}

function cekInteraksi() {
    // Cek peti
    if (!game.sudahBukaPeti && 
        game.playerRow === game.posisiPeti.row && 
        game.playerCol === game.posisiPeti.col) {
        tampilkanPuzzleRSA();
        return;
    }
    
    // Cek NPC
    for (let i = 0; i < game.posisiNPC.length; i++) {
        if (game.playerRow === game.posisiNPC[i].row && 
            game.playerCol === game.posisiNPC[i].col) {
            lihatCiri(i);
            return;
        }
    }
    
    // Cek pintu keluar
    if (game.sudahBukaPeti && 
        game.playerRow === game.posisiPintu.row && 
        game.playerCol === game.posisiPintu.col) {
        tampilkanPintuKeluar();
        return;
    }
}

/* ============================================================
   11. PUZZLE RSA (BUKA PETI)
   ============================================================ */

function tampilkanPuzzleRSA() {
    setProgress(2);
    const rsa = game.rsa;
    
    document.getElementById('gameKonten').innerHTML = 
        '<h2>📦 Peti Terkunci!</h2>' +
        '<p>Hitung kunci privat RSA untuk membuka peti!</p>' +
        '<div class="hitung-box">' +
        'p = ' + rsa.p + '\n' +
        'q = ' + rsa.q + '\n\n' +
        'n = p × q = ' + rsa.n + '\n' +
        'φ(n) = (p-1)(q-1) = ' + rsa.phi + '\n' +
        'e = ' + rsa.e + '\n' +
        'd = ' + rsa.d + '\n\n' +
        '✅ Kunci Privat = (' + rsa.d + ', ' + rsa.n + ')' +
        '</div>' +
        '<div class="btn-group">' +
        '<button class="btn success" type="button" id="btnBukaPeti">🔓 Buka Peti</button>' +
        '</div>';
    
    document.getElementById('btnBukaPeti').onclick = bukaPeti;
}

function bukaPeti() {
    game.sudahBukaPeti = true;
    showNotif('📦 Peti terbuka!');
    setStory('Peti berisi pesan terenkripsi. Ada Kunci Current di dalamnya!');
    
    renderEntitas();
    
    document.getElementById('gameKonten').innerHTML = 
        '<h2>📜 Isi Peti</h2>' +
        '<p>Di dalam peti ada pesan terenkripsi dan kunci:</p>' +
        '<div class="hitung-box">' +
        '🔑 KUNCI CURRENT: ' + game.kunciCurrent + '\n\n' +
        '📜 Ciphertext:\n' + game.encStr.substring(0, 120) + '...' +
        '</div>' +
        '<p style="color:#ffd700;">💡 Dekripsi ciphertext ini untuk tahu ciri imposter!</p>' +
        '<p style="color:#aaa;font-size:0.8em;">Pemain harus dekripsi sendiri (manual atau pakai rumus).</p>' +
        '<div class="btn-group">' +
        '<button class="btn" type="button" id="btnLanjut">🚶 Cari Karakter</button>' +
        '</div>';
    
    document.getElementById('btnLanjut').onclick = function() {
        setStory('Cari 3 karakter di peta! Dekati mereka untuk lihat jawaban terenkripsi.');
        setProgress(3);
        document.getElementById('gameKonten').innerHTML = 
            '<h2>🚶 Cari Karakter!</h2>' +
            '<p>Gunakan tombol ⬅️⬆️⬇️➡️ untuk jalan.</p>' +
            '<p>Dekati 🧑 untuk lihat jawaban mereka (terenkripsi).</p>' +
            '<div class="hitung-box">' +
            '🔑 KUNCI CURRENT: ' + game.kunciCurrent + '\n\n' +
            '📜 Ciphertext Ciri Imposter:\n' + game.encStr.substring(0, 80) + '...' +
            '</div>';
    };
}

/* ============================================================
   12. LIHAT CIRI NPC
   ============================================================ */

function lihatCiri(idx) {
    if (game.ciriDitemukan[idx]) return;
    
    game.ciriDitemukan[idx] = true;
    updateHUD();
    
    const p = game.karakter[idx];
    const encJawaban = currentEncrypt(p.ciri, game.kunciCurrent);
    const encStr = encJawaban.slice(0, 8).join('_');
    
    showNotif('🧑 ' + p.nama + ' menjawab!');
    
    let html = '<h2>🧑 ' + p.nama + '</h2>';
    html += '<div class="dialog-box">';
    html += '<div class="nama">' + p.nama + '</div>';
    html += '<p>"Jawabanku: <strong>' + encStr + '...</strong>"</p>';
    html += '<p style="font-size:0.8em;color:#aaa;">(Dekripsi dengan Kunci Current ' + game.kunciCurrent + ')</p>';
    html += '</div>';
    
    html += '<p style="color:#ffd700;">📋 Jawaban yang sudah ditemukan:</p>';
    html += '<div class="hitung-box">';
    for (let i = 0; i < game.karakter.length; i++) {
        if (game.ciriDitemukan[i]) {
            const enc = currentEncrypt(game.karakter[i].ciri, game.kunciCurrent);
            html += '🧑 ' + game.karakter[i].nama + ': ' + enc.slice(0, 8).join('_') + '...\n';
        } else {
            html += '🧑 ' + game.karakter[i].nama + ': ??? (belum ditemukan)\n';
        }
    }
    html += '</div>';
    
    const semuaCiri = game.ciriDitemukan.every(Boolean);
    if (semuaCiri) {
        html += '<p style="color:#28a745;">✅ Semua jawaban ditemukan! Cari pintu keluar 🚪</p>';
    }
    
    html += '<div class="btn-group">';
    html += '<button class="btn" type="button" id="btnTutup">🚶 Lanjut Jalan</button>';
    html += '</div>';
    
    document.getElementById('gameKonten').innerHTML = html;
    document.getElementById('btnTutup').onclick = function() {
        document.getElementById('gameKonten').innerHTML = 
            '<h2>🚶 Cari Karakter!</h2>' +
            '<p>Gunakan tombol ⬅️⬆️⬇️➡️ untuk jalan.</p>' +
            '<div class="hitung-box">' +
            '🔑 KUNCI CURRENT: ' + game.kunciCurrent + '\n\n' +
            '📜 Ciphertext Ciri Imposter:\n' + game.encStr.substring(0, 80) + '...' +
            '</div>';
    };
}

/* ============================================================
   13. PINTU KELUAR (PILIH IMPOSTER)
   ============================================================ */

function tampilkanPintuKeluar() {
    const semuaCiri = game.ciriDitemukan.every(Boolean);
    
    if (!semuaCiri) {
        showNotif('❌ Cari semua karakter dulu!');
        return;
    }
    
    setProgress(4);
    game.tebakan = null;
    
    let html = '<h2>🚪 Pintu Keluar</h2>';
    html += '<p>Pilih siapa imposter-nya!</p>';
    
    html += '<div class="hitung-box">';
    html += '🔑 KUNCI CURRENT: ' + game.kunciCurrent + '\n\n';
    html += '📜 Ciphertext Ciri Imposter:\n' + game.encStr.substring(0, 120) + '...';
    html += '</div>';
    
    html += '<p style="color:#ffd700;">💡 Dekripsi ciphertext di atas untuk tahu ciri imposter!</p>';
    
    html += '<div class="tersangka-grid">';
    for (let i = 0; i < game.karakter.length; i++) {
        html += '<div class="tersangka-card" id="card-' + i + '">';
        html += '<span class="tersangka-body">' + buatSVGKarakter(game.karakter[i].warna) + '</span>';
        html += '<div class="tersangka-nama">' + game.karakter[i].nama + '</div>';
        html += '</div>';
    }
    html += '</div>';
    
    html += '<div class="btn-group">';
    html += '<button class="btn danger" type="button" id="btnKonfirmasi">🎯 Pilih sebagai Imposter</button>';
    html += '</div>';
    
    document.getElementById('gameKonten').innerHTML = html;
    
    // Event: pilih tersangka
    for (let j = 0; j < game.karakter.length; j++) {
        document.getElementById('card-' + j).onclick = function() {
            document.querySelectorAll('.tersangka-card').forEach(c => c.classList.remove('selected'));
            this.classList.add('selected');
            game.tebakan = j;
        };
    }
    
    document.getElementById('btnKonfirmasi').onclick = konfirmasiTangkap;
}

/* ============================================================
   14. KONFIRMASI TANGKAP IMPOSTER
   ============================================================ */

function konfirmasiTangkap() {
    if (game.tebakan === null) {
        showNotif('⚠️ Pilih satu karakter dulu!');
        return;
    }
    
    const terpilih = game.karakter[game.tebakan];
    const benar = (terpilih.nama === game.imposter.nama);
    
    if (benar) {
        // BENAR: +2 poin, lanjut level
        game.skor += 2;
        tambahSkorPemain(game.pemainAktif, 2);
        updateHUD();
        showNotif('🎉 Benar! +2 poin untuk ' + game.pemainAktif);
        setStory('Imposter tertangkap! Pintu terbuka!');
        setProgress(5);
        tampilkanVerifikasi(true);
    } else {
        // SALAH: -1 nyawa
        game.nyawa--;
        updateHUD();
        
        if (game.nyawa <= 0) {
            showNotif('💀 Game Over!');
            setStory('Kamu gagal menemukan imposter!');
            tampilkanVerifikasi(false);
        } else {
            showNotif('❌ Salah! Nyawa -1');
            document.getElementById('gameKonten').innerHTML = 
                '<h2>❌ SALAH!</h2>' +
                '<div style="background:linear-gradient(135deg,rgba(220,53,69,0.3),rgba(220,53,69,0.1));border:2px solid #dc3545;padding:18px;border-radius:12px;text-align:center;margin:12px 0;">' +
                '<p><strong>' + terpilih.nama + '</strong> bukan imposter.</p>' +
                '<p>Nyawa tersisa: <strong style="color:#ffd700;font-size:1.3em;">' + game.nyawa + '</strong></p>' +
                '</div>' +
                '<p>Coba lagi! Baca ciphertext dengan teliti.</p>' +
                '<div class="hitung-box">' +
                '🔑 KUNCI CURRENT: ' + game.kunciCurrent + '\n\n' +
                '📜 Ciphertext Ciri Imposter:\n' + game.encStr.substring(0, 120) + '...' +
                '</div>' +
                '<div class="btn-group">' +
                '<button class="btn danger" type="button" id="btnCobaLagi">🎯 Coba Lagi</button>' +
                '</div>';
            
            document.getElementById('btnCobaLagi').onclick = tampilkanPintuKeluar;
        }
    }
}

/* ============================================================
   15. VERIFIKASI & HASIL AKHIR
   ============================================================ */

function tampilkanVerifikasi(menang) {
    const offset = (game.kunciCurrent - 1) % 26;
    let html = '';
    
    // === Panel Hasil ===
    if (menang) {
        html += '<div class="finish-menang">';
        html += '<div class="icon">🎉</div>';
        html += '<h2>SELAMAT! KAMU MENANG!</h2>';
        html += '<p>Imposter tertangkap! Pintu terbuka!</p>';
        html += '</div>';
        
        // Skor panel
        html += '<div class="skor-panel">';
        html += '<div class="skor-label">SKOR ' + game.pemainAktif.toUpperCase() + '</div>';
        html += '<div class="skor-besar">' + (game.leaderboard[game.pemainAktif] || 0) + '</div>';
        html += '<div class="skor-detail">';
        html += '<div class="skor-item">Level<span class="angka">' + game.level + '</span></div>';
        html += '<div class="skor-item">Nyawa<span class="angka">' + game.nyawa + '</span></div>';
        html += '<div class="skor-item">+Poin<span class="angka">+2</span></div>';
        html += '</div>';
        html += '</div>';
    } else {
        html += '<div class="finish-kalah">';
        html += '<div class="icon">💀</div>';
        html += '<h2>GAME OVER</h2>';
        html += '<p>Kamu gagal menemukan imposter!</p>';
        html += '<p style="font-size:1.2em;margin-top:10px;">🚪🔒 PINTU TERKUNCI! 🔒🚪</p>';
        html += '</div>';
    }
    
    // === Verifikasi Perhitungan ===
    html += '<h3>📊 VERIFIKASI — CARA MENDAPATKAN JAWABAN</h3>';
    
    // 1. Ciri Imposter
    html += '<div class="hitung-box">';
    html += '<strong style="color:#ffd700;">1️⃣ CIRI IMPOSTER (dari ciphertext):</strong>\n\n';
    html += 'Ciphertext    : ' + game.encStr.substring(0, 80) + '...\n';
    html += 'Kunci Current : ' + game.kunciCurrent + '\n';
    html += 'Offset        : (' + game.kunciCurrent + ' − 1) mod 26 = ' + offset + '\n\n';
    html += '<strong>Dekripsi 8 angka pertama:</strong>\n';
    
    const tokens = game.encArr.slice(0, 8);
    let hasilDekripsi = '';
    
    for (const tok of tokens) {
        if (tok === 'SP') {
            html += '  SP → [spasi]\n';
            hasilDekripsi += ' ';
        } else {
            const hurufC = TABEL_BASE_INV[parseInt(tok)];
            if (hurufC) {
                const idxC = HURUF.indexOf(hurufC);
                const posA = ((idxC - offset) % 26 + 26) % 26;
                const hurufA = HURUF[posA];
                html += '  ' + tok + ' → ' + hurufC + ' (idx ' + idxC + '), (' + idxC + '−' + offset + ') mod 26 = ' + posA + ' → ' + hurufA + '\n';
                hasilDekripsi += hurufA;
            }
        }
    }
    
    html += '\n<strong>Hasil: "' + hasilDekripsi + '..."</strong>\n';
    html += 'Ciri lengkap: <strong style="color:#28a745;">"' + game.dataImposter.ciri + '"</strong>';
    html += '</div>';
    
    // 2. Jawaban setiap karakter
    html += '<div class="hitung-box">';
    html += '<strong style="color:#ffd700;">2️⃣ JAWABAN SETIAP KARAKTER:</strong>\n\n';
    
    for (const p of game.karakter) {
        const encC = currentEncrypt(p.ciri, game.kunciCurrent);
        const encStr = encC.slice(0, 6).join('_');
        const decC = currentDecrypt(encC, game.kunciCurrent);
        const isCocok = (p.ciri === game.dataImposter.ciri);
        
        html += '<strong>' + p.nama + ':</strong>\n';
        html += '  Ciphertext : ' + encStr + '...\n';
        html += '  Dekripsi   : "' + decC + '"\n';
        html += '  Status     : ' + (isCocok ? '✅ COCOK' : '❌ Tidak cocok') + '\n\n';
    }
    html += '</div>';
    
    // 3. Kesimpulan
    html += '<div class="hitung-box" style="border-left-color:#ffd700;background:linear-gradient(135deg,rgba(255,215,0,0.15),rgba(255,140,0,0.05));">';
    html += '<strong style="color:#ffd700;">3️⃣ KESIMPULAN:</strong>\n\n';
    html += 'Ciri imposter      : "' + game.dataImposter.ciri + '"\n';
    html += 'Karakter yang cocok: <strong style="color:#28a745;">' + game.imposter.nama + '</strong>\n';
    html += 'Kamu pilih         : <strong>' + game.karakter[game.tebakan].nama + '</strong>\n';
    html += 'Status             : <strong style="color:' + (menang ? '#28a745' : '#dc3545') + ';">' + (menang ? '✅ BENAR' : '❌ SALAH') + '</strong>';
    html += '</div>';
    
    // Tabel perbandingan
    html += '<h3>📋 TABEL PERBANDINGAN</h3>';
    html += '<table class="tabel-verifikasi">';
    html += '<tr><th>Karakter</th><th>Ciri Asli</th><th>Status</th></tr>';
    for (let i = 0; i < game.karakter.length; i++) {
        const pp = game.karakter[i];
        const isImp = (pp.nama === game.imposter.nama);
        const isPilih = (i === game.tebakan);
        let cls = '';
        if (isImp) cls = 'benar';
        else if (isPilih && !menang) cls = 'salah';
        
        html += '<tr class="' + cls + '">';
        html += '<td>' + pp.nama + (isImp ? ' 👑' : '') + '</td>';
        html += '<td>"' + pp.ciri + '"</td>';
        html += '<td>' + (isImp ? '✅ IMPOSTER' : '') + '</td>';
        html += '</tr>';
    }
    html += '</table>';
    
    // Kunci privat (kalau menang)
    if (menang) {
        html += '<div class="hitung-box">';
        html += '<strong style="color:#ffd700;">🔑 KUNCI PRIVAT RSA:</strong>\n\n';
        html += 'Kunci Privat : (' + game.rsa.d + ', ' + game.rsa.n + ')\n';
        html += 'Peta         : ' + game.imposter.peta;
        html += '</div>';
    }
    
    // Leaderboard
    html += renderLeaderboard();
    
    // === Tombol Aksi ===
    html += '<div class="btn-group" style="margin-top:20px;">';
    if (menang) {
        html += '<button class="btn success" id="btnLanjutLevel" type="button">➡️ Lanjut Level ' + (game.level + 1) + '</button>';
        html += '<button class="btn info" id="btnUlangLevel" type="button">🔄 Ulang Level</button>';
        html += '<button class="btn danger" id="btnMenuUtama" type="button">🏠 Menu Utama</button>';
    } else {
        html += '<button class="btn success" id="btnUlangLevel" type="button">🔄 Coba Lagi</button>';
        html += '<button class="btn danger" id="btnMenuUtama" type="button">🏠 Menu Utama</button>';
    }
    html += '</div>';
    
    document.getElementById('gameKonten').innerHTML = html;
    
    // Attach event listeners
    if (menang) {
        document.getElementById('btnLanjutLevel').onclick = lanjutLevel;
    }
    document.getElementById('btnUlangLevel').onclick = ulangLevel;
    document.getElementById('btnMenuUtama').onclick = keMenuUtama;
}

/* ============================================================
   16. AKSI LEVEL (LANJUT / ULANG / MENU)
   ============================================================ */

function lanjutLevel() {
    game.level++;
    
    // Reset nyawa untuk level baru
    // (skor tetap, tidak direset)
    
    showNotif('➡️ Level ' + game.level + ' dimulai!');
    mulaiLevelBaru();
}

function ulangLevel() {
    // Reset nyawa untuk level baru
    // (skor tetap, tidak direset)
    
    showNotif('🔄 Level diulang!');
    mulaiLevelBaru();
}

function keMenuUtama() {
    document.getElementById('gamePage').classList.add('hidden');
    document.getElementById('introPage').classList.remove('hidden');
}

/* ============================================================
   17. INISIALISASI
   ============================================================ */

function initGame() {
    // Reset state
    game.level = 1;
    game.skor = 0;
    game.nyawa = 2;
    game.playerRow = 3;
    game.playerCol = 0;
    game.sudahBukaPeti = false;
    game.ciriDitemukan = [false, false, false];
    game.tebakan = null;
    
    // Reset leaderboard (opsional, bisa dikomentari kalau mau persistent)
    // game.leaderboard = {};
    
    // Ambil karakter default
    const pool = shuffle(POOL_KARAKTER);
    game.karakter = [pool[0], pool[1], pool[2]];
    
    // Build maze & render
    buildMaze();
    renderEntitas();
    updateHUD();
    setProgress(1);
    setStory('Setup permainan dulu ya!');
    
    // Tampilkan form setup
    tampilkanFormSetup();
    
    // Attach kontrol
    document.getElementById('btnKiri').onclick = () => gerak(0, -1);
    document.getElementById('btnKanan').onclick = () => gerak(0, 1);
    document.getElementById('btnAtas').onclick = () => gerak(-1, 0);
    document.getElementById('btnBawah').onclick = () => gerak(1, 0);
    document.getElementById('btnAksi').onclick = cekInteraksi;
}

// Event: tombol mulai
document.getElementById('btnMulai').onclick = function() {
    document.getElementById('introPage').classList.add('hidden');
    document.getElementById('gamePage').classList.remove('hidden');
    initGame();
};
</script>
</body>
</html>
