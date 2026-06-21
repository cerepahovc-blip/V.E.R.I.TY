<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes, viewport-fit=cover, maximum-scale=1.0, minimum-scale=1.0">
  
  <!-- Название приложения -->
  <title>V.E.R.I.T.Y.</title>
  <meta name="application-name" content="V.E.R.I.T.Y.">
  <meta name="apple-mobile-web-app-title" content="V.E.R.I.T.Y.">
  
  <!-- Иконки для разных платформ -->
  <link rel="icon" type="image/svg+xml" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Ccircle cx='50' cy='50' r='48' fill='%23f7c744' stroke='%23e8b830' stroke-width='3'/%3E%3Ccircle cx='33' cy='40' r='6' fill='%231e1e1e'/%3E%3Ccircle cx='67' cy='40' r='6' fill='%231e1e1e'/%3E%3Cpath d='M30 60 Q50 80 70 60' stroke='%231e1e1e' stroke-width='5' fill='none' stroke-linecap='round'/%3E%3Ctext x='50' y='95' text-anchor='middle' font-family='Arial' font-weight='bold' font-size='10' fill='%23f5e56c'%3EV.E.R.I.T.Y%3C/text%3E%3C/svg%3E">
  <link rel="icon" type="image/png" sizes="192x192" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 192 192'%3E%3Crect width='192' height='192' rx='40' fill='%231a1e2b'/%3E%3Ccircle cx='96' cy='80' r='60' fill='%23f7c744' stroke='%23e8b830' stroke-width='3'/%3E%3Ccircle cx='72' cy='65' r='9' fill='%231e1e1e'/%3E%3Ccircle cx='120' cy='65' r='9' fill='%231e1e1e'/%3E%3Cpath d='M60 95 Q96 125 132 95' stroke='%231e1e1e' stroke-width='7' fill='none' stroke-linecap='round'/%3E%3Ctext x='96' y='175' text-anchor='middle' font-family='Arial' font-weight='900' font-size='18' fill='%23f5e56c' letter-spacing='3'%3EV.E.R.I.T.Y%3C/text%3E%3C/svg%3E">
  <link rel="apple-touch-icon" sizes="180x180" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 180 180'%3E%3Crect width='180' height='180' rx='38' fill='%231a1e2b'/%3E%3Ccircle cx='90' cy='75' r='56' fill='%23f7c744' stroke='%23e8b830' stroke-width='3'/%3E%3Ccircle cx='68' cy='62' r='8' fill='%231e1e1e'/%3E%3Ccircle cx='112' cy='62' r='8' fill='%231e1e1e'/%3E%3Cpath d='M56 90 Q90 118 124 90' stroke='%231e1e1e' stroke-width='6' fill='none' stroke-linecap='round'/%3E%3Ctext x='90' y='165' text-anchor='middle' font-family='Arial' font-weight='900' font-size='16' fill='%23f5e56c' letter-spacing='3'%3EV.E.R.I.T.Y%3C/text%3E%3C/svg%3E">
  
  <!-- PWA манифест -->
  <meta name="theme-color" content="#1a1e2b">
  <meta name="apple-mobile-web-app-capable" content="yes">
  <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
  <meta name="mobile-web-app-capable" content="yes">
  
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }

    html, body {
      width: 100%;
      height: 100%;
      overflow: hidden;
      position: fixed;
      top: 0;
      left: 0;
    }

    body {
      font-family: 'Segoe UI', 'Roboto', system-ui, -apple-system, sans-serif;
      background: linear-gradient(145deg, #1a1e2b 0%, #2a2f3f 100%);
      display: flex;
      justify-content: center;
      align-items: center;
      transition: background 0.8s ease;
      -webkit-tap-highlight-color: transparent;
      -webkit-user-select: none;
      user-select: none;
      -webkit-touch-callout: none;
    }
    body.horror-theme {
      background: #000000;
    }

    .app-container {
      width: 100%;
      height: 100%;
      max-width: 550px;
      background: rgba(255,255,255,0.07);
      backdrop-filter: blur(24px);
      -webkit-backdrop-filter: blur(24px);
      display: flex;
      flex-direction: column;
      align-items: center;
      transition: all 0.8s ease;
      overflow-y: auto;
      -webkit-overflow-scrolling: touch;
      padding: 1rem 1rem 1.5rem;
      border: none;
      box-shadow: none;
    }
    @media (min-width: 550px) {
      .app-container {
        border-radius: 2.5rem;
        height: 90%;
        max-height: 850px;
        box-shadow: 0 25px 45px rgba(0,0,0,0.5), inset 0 1px 0 rgba(255,255,255,0.1);
        border: 1px solid rgba(255,255,255,0.12);
      }
    }
    body.horror-theme .app-container {
      background: rgba(20,0,0,0.5);
    }
    @media (min-width: 550px) {
      body.horror-theme .app-container {
        border: 1px solid rgba(255,0,0,0.3);
        box-shadow: 0 25px 45px rgba(0,0,0,0.8), 0 0 40px rgba(255,0,0,0.2);
      }
    }

    h1 {
      font-size: 1.5rem;
      font-weight: 700;
      letter-spacing: 0.3rem;
      color: #f5e56c;
      text-shadow: 0 0 12px rgba(245,229,108,0.55);
      margin-bottom: 0.5rem;
      transition: all 0.5s;
      flex-shrink: 0;
    }
    body.horror-theme h1 {
      color: #8b0000;
      text-shadow: 0 0 20px rgba(255,0,0,0.8);
    }

    /* Режимы */
    .mode-bar {
      display: flex; gap: 0.35rem; margin-bottom: 0.6rem; flex-shrink: 0;
    }
    .mode-btn {
      background: rgba(20,22,30,0.6); border: 1px solid rgba(255,215,0,0.25);
      color: #c0b78a; padding: 0.45rem 0.8rem; border-radius: 1.5rem;
      font-size: 0.7rem; font-weight: 600; cursor: pointer; transition: all 0.2s;
      white-space: nowrap; -webkit-tap-highlight-color: transparent;
    }
    .mode-btn:active { transform: scale(0.95); }
    .mode-btn.active {
      background: #f7c744; color: #1e1e1e; border-color: #f7c744;
      box-shadow: 0 0 10px rgba(247,199,68,0.5);
    }
    .mode-btn.mode-gopnik.active {
      background: #555; color: #fff; border-color: #888;
    }
    .mode-btn.mode-horror.active {
      background: #3a0000; color: #ff4444; border-color: #660000;
      box-shadow: 0 0 15px rgba(255,0,0,0.7);
    }

    /* Смайлик */
    .face-wrapper {
      width: 110px; height: 110px;
      border-radius: 50%;
      display: flex; justify-content: center; align-items: center;
      margin-bottom: 0.6rem;
      position: relative;
      flex-shrink: 0;
      transition: all 0.5s ease;
    }
    @media (min-height: 700px) {
      .face-wrapper { width: 130px; height: 130px; }
    }
    .face-wrapper.mode-normal {
      background: #f7c744;
      box-shadow: 0 12px 20px rgba(0,0,0,0.5), 0 0 0 4px rgba(255,215,0,0.3);
    }
    .face-wrapper.mode-gopnik {
      background: #e8c35c;
      box-shadow: 0 12px 20px rgba(0,0,0,0.6), 0 0 0 3px rgba(100,100,100,0.5);
    }
    .face-wrapper.mode-horror {
      background: #1a0a0a;
      box-shadow: 0 0 30px rgba(255,0,0,0.5), 0 0 0 3px rgba(180,0,0,0.6);
      animation: horrorPulse 2s infinite;
    }
    @keyframes horrorPulse {
      0%, 100% { box-shadow: 0 0 30px rgba(255,0,0,0.5), 0 0 0 3px rgba(180,0,0,0.6); }
      50% { box-shadow: 0 0 50px rgba(255,0,0,0.8), 0 0 0 5px rgba(255,0,0,0.4); }
    }

    .face { position: relative; width: 100%; height: 100%; }

    .cap {
      display: none; position: absolute;
      top: -15px; left: 50%; transform: translateX(-50%);
      width: 75px; height: 28px;
      background: #2c2c2c; border-radius: 35px 35px 6px 6px;
      border-bottom: 3px solid #1a1a1a; z-index: 10;
    }
    .cap::before {
      content: ''; position: absolute;
      bottom: -6px; left: -6px;
      width: 87px; height: 10px;
      background: #3a3a3a; border-radius: 0 0 16px 16px;
    }
    .face-wrapper.mode-gopnik .cap { display: block; }

    .black-eye {
      display: none; position: absolute;
      width: 20px; height: 16px;
      background: rgba(80,30,60,0.8); border-radius: 50%;
      top: 30px; left: 22px;
      box-shadow: 0 0 6px rgba(100,0,50,0.6); z-index: 5;
    }
    .face-wrapper.mode-gopnik .black-eye { display: block; }

    .scar {
      display: none; position: absolute;
      background: rgba(80,0,0,0.7); z-index: 4;
    }
    .scar1 { width: 2px; height: 20px; top: 12px; left: 42px; transform: rotate(15deg); }
    .scar2 { width: 2px; height: 16px; top: 20px; right: 34px; transform: rotate(-20deg); }
    .face-wrapper.mode-horror .scar { display: block; }

    .eye {
      position: absolute; width: 12px; height: 15px; border-radius: 50%;
      top: 34px; transition: all 0.3s; z-index: 3;
    }
    @media (min-height: 700px) {
      .eye { width: 14px; height: 18px; top: 38px; }
    }
    .face-wrapper.mode-normal .eye,
    .face-wrapper.mode-gopnik .eye {
      background: #1e1e1e; box-shadow: inset 0 2px 0 rgba(255,255,255,0.2);
    }
    .eye.left { left: 26px; }
    .eye.right { right: 26px; }
    @media (min-height: 700px) {
      .eye.left { left: 30px; } .eye.right { right: 30px; }
    }

    .face-wrapper.mode-gopnik .eye {
      height: 6px; top: 36px; border-radius: 0; background: #1a1a1a;
    }
    @media (min-height: 700px) {
      .face-wrapper.mode-gopnik .eye { height: 7px; top: 42px; }
    }

    .face-wrapper.mode-horror .eye {
      width: 16px; height: 18px;
      background: #000; border: 2px solid #4a0000;
      box-shadow: 0 0 12px rgba(255,0,0,0.8); top: 30px;
    }
    .face-wrapper.mode-horror .eye.left { left: 22px; }
    .face-wrapper.mode-horror .eye.right { right: 22px; }
    .face-wrapper.mode-horror .eye::after {
      content: ''; position: absolute;
      width: 6px; height: 6px;
      background: #ff0000; border-radius: 50%;
      top: 5px; left: 4px;
      box-shadow: 0 0 8px rgba(255,0,0,1);
      animation: horrorEyeGlow 1.5s infinite;
    }
    @keyframes horrorEyeGlow {
      0%, 100% { box-shadow: 0 0 8px rgba(255,0,0,1); }
      50% { box-shadow: 0 0 20px rgba(255,0,0,1); }
    }

    .face-wrapper.blinking .eye { height: 2px; top: 40px; border-radius: 0; }
    .face-wrapper.thinking-face .eye { height: 10px; top: 32px; }
    .face-wrapper.surprised .eye { width: 14px; height: 14px; top: 34px; }

    .mouth {
      position: absolute; background: transparent;
      transition: all 0.3s; z-index: 3;
    }
    .face-wrapper.mode-normal .mouth {
      width: 34px; height: 16px;
      border-bottom: 4px solid #1e1e1e;
      border-radius: 0 0 34px 34px;
      bottom: 26px; left: 50%; transform: translateX(-50%);
    }
    @media (min-height: 700px) {
      .face-wrapper.mode-normal .mouth { width: 40px; height: 18px; bottom: 28px; }
    }
    .face-wrapper.mode-gopnik .mouth {
      width: 28px; height: 11px;
      border-bottom: 3px solid #1a1a1a;
      border-radius: 0 0 16px 16px;
      bottom: 28px; left: 50%; transform: translateX(-50%) rotate(3deg);
    }

    .mouth-horror {
      display: none; position: absolute;
      bottom: 18px; left: 50%; transform: translateX(-50%);
      width: 52px; height: 32px; z-index: 3;
    }
    .face-wrapper.mode-horror .mouth-horror { display: block; }
    .face-wrapper.mode-horror .mouth { display: none; }
    .mouth-horror-bg {
      position: absolute; bottom: 0; left: 50%; transform: translateX(-50%);
      width: 52px; height: 28px;
      background: #0a0000; border: 2px solid #4a0000;
      border-radius: 4px 4px 20px 20px;
    }
    .tooth {
      position: absolute; background: #ddd;
      width: 6px; border-radius: 2px 2px 0 0; z-index: 2;
    }
    .tooth.t1 { height: 12px; top: -8px; left: 4px; }
    .tooth.t2 { height: 14px; top: -10px; left: 13px; }
    .tooth.t3 { height: 16px; top: -12px; left: 23px; }
    .tooth.t4 { height: 14px; top: -10px; left: 33px; }
    .tooth.t5 { height: 12px; top: -8px; left: 42px; }
    .fang {
      position: absolute; background: #ccc;
      width: 5px; border-radius: 2px 2px 3px 3px; z-index: 3;
    }
    .fang.f1 { height: 18px; top: -13px; left: 8px; }
    .fang.f2 { height: 18px; top: -13px; right: 8px; }

    .blood-drip {
      display: none; position: absolute;
      width: 2px; background: #8b0000; z-index: 1;
      animation: drip 2s infinite;
    }
    .blood-drip.b1 { height: 10px; bottom: -8px; left: 16px; }
    .blood-drip.b2 { height: 6px; bottom: -6px; left: 26px; animation-delay: 0.7s; }
    .blood-drip.b3 { height: 8px; bottom: -7px; left: 36px; animation-delay: 1.4s; }
    .face-wrapper.mode-horror .blood-drip { display: block; }
    @keyframes drip {
      0%, 100% { opacity: 0.6; transform: scaleY(1); }
      50% { opacity: 1; transform: scaleY(1.5); }
    }

    .face-wrapper.speaking .mouth { animation: speak 0.25s infinite alternate; }
    .face-wrapper.speaking .mouth-horror { animation: speakHorror 0.3s infinite alternate; }
    @keyframes speak { 0% { height: 6px; bottom: 30px; } 100% { height: 14px; bottom: 24px; } }
    @keyframes speakHorror { 0% { transform: translateX(-50%) scaleY(0.7); } 100% { transform: translateX(-50%) scaleY(1.2); } }

    /* Языки */
    .lang-bar {
      display: flex; gap: 0.25rem; margin-bottom: 0.5rem; flex-shrink: 0;
    }
    .lang-btn {
      background: rgba(20,22,30,0.6); border: 1px solid rgba(255,215,0,0.25);
      color: #c0b78a; padding: 0.25rem 0.5rem; border-radius: 1.2rem;
      font-size: 0.65rem; font-weight: 600; cursor: pointer;
    }
    .lang-btn:active { transform: scale(0.95); }
    .lang-btn.active { background: #f7c744; color: #1e1e1e; border-color: #f7c744; }

    /* Вкладки */
    .tabs { display: flex; width: 100%; gap: 0.3rem; margin-bottom: 0.5rem; flex-shrink: 0; }
    .tab-btn {
      flex: 1; background: rgba(20,22,30,0.6); border: 1px solid rgba(255,215,0,0.25);
      color: #c0b78a; padding: 0.4rem 0.2rem; border-radius: 1.5rem;
      font-weight: 600; font-size: 0.65rem; cursor: pointer; text-align: center;
    }
    .tab-btn:active { transform: scale(0.97); }
    .tab-btn.active { background: #f7c744; color: #1e1e1e; border-color: #f7c744; }

    .tab-content { display: none; width: 100%; flex: 1; flex-direction: column; align-items: center; min-height: 0; }
    .tab-content.active { display: flex; }

    /* Чат */
    .chat-history {
      background: rgba(20,22,30,0.7); border-radius: 1.2rem; padding: 0.6rem;
      width: 100%; flex: 1; overflow-y: auto; margin-bottom: 0.5rem;
      border: 1px solid rgba(255,255,255,0.15);
      display: flex; flex-direction: column; gap: 0.3rem;
      -webkit-overflow-scrolling: touch;
    }
    body.horror-theme .chat-history {
      background: rgba(10,0,0,0.7); border: 1px solid rgba(255,0,0,0.2);
    }
    .chat-msg {
      max-width: 85%; padding: 0.4rem 0.7rem; border-radius: 1rem;
      font-size: 0.75rem; line-height: 1.3; word-break: break-word;
      animation: fadeIn 0.3s;
    }
    @keyframes fadeIn { from { opacity: 0; transform: translateY(4px); } to { opacity: 1; transform: translateY(0); } }
    .chat-msg.user {
      align-self: flex-end; background: rgba(247,199,68,0.2);
      border: 1px solid rgba(247,199,68,0.3); color: #f5e9c0;
    }
    .chat-msg.bot {
      align-self: flex-start; background: rgba(255,255,255,0.08);
      border: 1px solid rgba(255,255,255,0.15); color: #e0d7b8;
    }
    body.horror-theme .chat-msg.user {
      background: rgba(139,0,0,0.2); border-color: rgba(200,0,0,0.3); color: #ffcccc;
    }
    body.horror-theme .chat-msg.bot {
      background: rgba(30,0,0,0.5); border-color: rgba(180,0,0,0.3); color: #ff9999;
    }

    .input-group { display: flex; width: 100%; gap: 0.3rem; flex-shrink: 0; }
    .question-input {
      flex: 1; background: rgba(10,12,20,0.7); border: 1.5px solid rgba(255,215,0,0.3);
      border-radius: 1.5rem; padding: 0.55rem 0.8rem; font-size: 0.8rem;
      color: #f7e9b0; outline: none; min-width: 0;
    }
    .question-input::placeholder { color: #a09b85; }
    .question-input:focus { border-color: #f7c744; }
    body.horror-theme .question-input {
      background: rgba(20,0,0,0.7); border-color: rgba(180,0,0,0.4); color: #ffcccc;
    }
    .ask-btn, .voice-btn {
      background: linear-gradient(135deg, #ffd966, #f7b32b); border: none;
      border-radius: 1.5rem; padding: 0.55rem 0.8rem; font-weight: 700;
      font-size: 0.75rem; color: #1e1e1e; cursor: pointer; flex-shrink: 0;
    }
    .voice-btn { padding: 0.55rem 0.6rem; font-size: 0.9rem; }
    .ask-btn:active, .voice-btn:active { transform: scale(0.95); }
    body.horror-theme .ask-btn, body.horror-theme .voice-btn {
      background: linear-gradient(135deg, #4a0000, #8b0000); color: #ffcccc;
    }

    .clear-btn {
      background: transparent; border: 1px solid rgba(255,255,255,0.2);
      color: #b9af8a; font-size: 0.6rem; padding: 0.15rem 0.6rem;
      border-radius: 0.8rem; cursor: pointer; margin-bottom: 0.3rem; flex-shrink: 0;
    }
    .clear-btn:active { background: rgba(255,255,255,0.1); }

    /* Обновления */
    .updates-box {
      background: rgba(20,22,30,0.7); border-radius: 1.2rem; padding: 0.8rem;
      width: 100%; flex: 1; overflow-y: auto;
      border: 1px solid rgba(255,255,255,0.15);
      color: #fff5d1; font-size: 0.7rem; line-height: 1.4;
      -webkit-overflow-scrolling: touch;
    }
    body.horror-theme .updates-box { background: rgba(15,0,0,0.7); border-color: rgba(180,0,0,0.3); color: #ffaaaa; }
    .updates-box h2 { color: #f7c744; font-size: 0.9rem; margin-bottom: 0.4rem; text-align: center; }
    .updates-box .version { color: #f5e56c; font-weight: 700; margin-top: 0.6rem; font-size: 0.75rem; }
    .updates-box ul { list-style: none; padding-left: 0; }
    .updates-box li { padding: 0.1rem 0; border-bottom: 1px solid rgba(255,255,255,0.05); }
    .updates-box li::before { content: '✨ '; }
    body.horror-theme .updates-box li::before { content: '💀 '; }
    .apology-box {
      background: rgba(255,200,200,0.12); border: 1px solid rgba(255,150,150,0.35);
      border-radius: 0.8rem; padding: 0.5rem 0.7rem; margin-top: 0.5rem;
      font-style: italic; color: #ffcccc; text-align: center;
    }
    .apology-box strong { color: #ffaaaa; }
    .future-box {
      background: rgba(200,255,200,0.1); border: 1px solid rgba(150,255,150,0.3);
      border-radius: 0.8rem; padding: 0.5rem 0.7rem; margin-top: 0.4rem;
      color: #ccffcc; text-align: center;
    }
  </style>
</head>
<body id="mainBody">
  <div class="app-container">
    <h1>V.E.R.I.T.Y</h1>

    <div class="face-wrapper mode-normal" id="faceWrapper">
      <div class="cap"></div>
      <div class="black-eye"></div>
      <div class="scar scar1"></div>
      <div class="scar scar2"></div>
      <div class="face">
        <div class="eye left"></div>
        <div class="eye right"></div>
        <div class="mouth"></div>
        <div class="mouth-horror">
          <div class="mouth-horror-bg"></div>
          <div class="tooth t1"></div><div class="tooth t2"></div><div class="tooth t3"></div><div class="tooth t4"></div><div class="tooth t5"></div>
          <div class="fang f1"></div><div class="fang f2"></div>
          <div class="blood-drip b1"></div><div class="blood-drip b2"></div><div class="blood-drip b3"></div>
        </div>
      </div>
    </div>

    <div class="mode-bar">
      <button class="mode-btn active" data-mode="normal">😊 Обычный</button>
      <button class="mode-btn mode-gopnik" data-mode="gopnik">😈 Гопник</button>
      <button class="mode-btn mode-horror" data-mode="horror">💀 Хоррор</button>
    </div>

    <div class="lang-bar">
      <button class="lang-btn active" data-lang="ru">🇷🇺 RU</button>
      <button class="lang-btn" data-lang="en">🇬🇧 EN</button>
      <button class="lang-btn" data-lang="ja">🇯🇵 日本語</button>
      <button class="lang-btn" data-lang="zh">🇨🇳 中文</button>
    </div>

    <div class="tabs">
      <button class="tab-btn active" data-tab="chat">💬 Чат</button>
      <button class="tab-btn" data-tab="updates">🔄 Обновления</button>
    </div>

    <div class="tab-content active" id="tab-chat">
      <div class="chat-history" id="chatHistory"></div>
      <button class="clear-btn" id="clearHistoryBtn">🗑 Очистить</button>
      <div class="input-group">
        <input type="text" id="questionInput" class="question-input" placeholder="Спроси..." autofocus autocomplete="off" enterkeyhint="send">
        <button id="voiceBtn" class="voice-btn" title="Озвучить">🔊</button>
        <button id="askButton" class="ask-btn">▶</button>
      </div>
    </div>

    <div class="tab-content" id="tab-updates">
      <div class="updates-box">
        <h2>📋 История версий</h2>
        <div class="version">Версия 6.0 — «Хоррор»</div>
        <ul>
        
