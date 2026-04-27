<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes">
  <title>Чайные заметки · Форматирование</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', system-ui, sans-serif;
    }

    body {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      min-height: 100vh;
      padding: 20px;
      color: #333;
      position: relative;
      overflow-x: hidden;
    }

    body::before {
      content: '';
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: radial-gradient(circle at 20% 50%, rgba(120, 119, 198, 0.3) 0%, transparent 50%),
                  radial-gradient(circle at 80% 20%, rgba(255, 255, 255, 0.1) 0%, transparent 50%),
                  radial-gradient(circle at 40% 80%, rgba(120, 119, 198, 0.2) 0%, transparent 50%);
      animation: backgroundShift 15s ease-in-out infinite;
      z-index: 0;
    }

    @keyframes backgroundShift {
      0%, 100% { transform: translate(0, 0) scale(1); }
      25% { transform: translate(-2%, 2%) scale(1.05); }
      50% { transform: translate(2%, -1%) scale(0.95); }
      75% { transform: translate(1%, 1%) scale(1.02); }
    }

    .particles {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 1;
    }

    .particle {
      position: absolute;
      background: rgba(255, 255, 255, 0.6);
      border-radius: 50%;
      animation: float 6s ease-in-out infinite;
    }

    .particle:nth-child(1) { width: 10px; height: 10px; left: 10%; top: 20%; animation-delay: 0s; }
    .particle:nth-child(2) { width: 15px; height: 15px; left: 20%; top: 60%; animation-delay: 1s; }
    .particle:nth-child(3) { width: 8px; height: 8px; left: 70%; top: 30%; animation-delay: 2s; }
    .particle:nth-child(4) { width: 12px; height: 12px; left: 80%; top: 70%; animation-delay: 3s; }
    .particle:nth-child(5) { width: 6px; height: 6px; left: 50%; top: 50%; animation-delay: 4s; }
    .particle:nth-child(6) { width: 9px; height: 9px; left: 30%; top: 40%; animation-delay: 5s; }

    @keyframes float {
      0%, 100% { transform: translateY(0) translateX(0) scale(1); opacity: 0.6; }
      25% { transform: translateY(-20px) translateX(10px) scale(1.2); opacity: 0.8; }
      50% { transform: translateY(-10px) translateX(-10px) scale(0.8); opacity: 0.4; }
      75% { transform: translateY(-30px) translateX(5px) scale(1.1); opacity: 0.7; }
    }

    .container {
      max-width: 1000px;
      margin: 0 auto;
      position: relative;
      z-index: 2;
    }

    .header {
      text-align: center;
      margin-bottom: 35px;
      padding-top: 15px;
      animation: fadeInDown 0.8s ease-out;
    }

    @keyframes fadeInDown {
      from { opacity: 0; transform: translateY(-30px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .logo {
      font-size: 2.8rem;
      color: white;
      margin-bottom: 8px;
      opacity: 0.9;
      animation: pulse 2s ease-in-out infinite;
    }

    @keyframes pulse {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.05); }
    }

    h1 {
      color: white;
      font-weight: 300;
      letter-spacing: 1px;
      font-size: 2.2rem;
      text-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
    }

    .subtitle {
      color: rgba(255, 255, 255, 0.8);
      font-size: 1rem;
      font-weight: 300;
      margin-top: 5px;
      font-style: italic;
    }

    /* === АККАУНТ-ПАНЕЛЬ === */
    .account-bar {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 15px;
      background: rgba(255, 255, 255, 0.15);
      backdrop-filter: blur(10px);
      padding: 10px 25px;
      border-radius: 50px;
      margin-bottom: 25px;
      flex-wrap: wrap;
      animation: fadeInDown 0.8s ease-out;
    }

    .account-bar span {
      color: white;
      font-weight: 500;
    }

    .account-bar .btn {
      padding: 8px 18px;
      font-size: 0.85rem;
      border-radius: 25px;
    }

    .btn-outline-light {
      background: transparent;
      border: 2px solid white;
      color: white;
    }

    .btn-outline-light:hover {
      background: white;
      color: #667eea;
    }

    .main-area {
      display: grid;
      grid-template-columns: 1fr 2fr;
      gap: 25px;
      background: rgba(255, 255, 255, 0.97);
      border-radius: 24px;
      padding: 35px;
      box-shadow: 0 25px 60px rgba(0, 0, 0, 0.3), 0 0 0 1px rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(12px);
      animation: fadeInUp 0.8s ease-out 0.2s both;
    }

    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @media (max-width: 768px) {
      .main-area {
        grid-template-columns: 1fr;
        padding: 20px;
      }
    }

    .note-form {
      display: flex;
      flex-direction: column;
      gap: 18px;
    }

    .form-group {
      display: flex;
      flex-direction: column;
      gap: 6px;
    }

    label {
      font-size: 0.9rem;
      color: #4b5563;
      font-weight: 500;
    }

    input, textarea, select {
      padding: 14px;
      border: 2px solid #e5e7eb;
      border-radius: 12px;
      font-size: 1rem;
      transition: all 0.2s;
      background: white;
    }

    input:focus, textarea:focus, select:focus {
      outline: none;
      border-color: #667eea;
      box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.15);
    }

    textarea {
      min-height: 130px;
      resize: vertical;
    }

    .btn {
      padding: 14px 20px;
      border: none;
      border-radius: 12px;
      font-size: 1rem;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.25s;
      position: relative;
      overflow: hidden;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
    }

    .btn-primary {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      color: white;
      box-shadow: 0 6px 18px rgba(102, 126, 234, 0.4);
    }

    .btn-primary:hover {
      transform: translateY(-2px);
      box-shadow: 0 10px 22px rgba(102, 126, 234, 0.55);
    }

    .btn-secondary {
      background: #f3f4f6;
      color: #374151;
    }

    .btn-secondary:hover {
      background: #e5e7eb;
    }

    .btn-small {
      padding: 6px 14px;
      font-size: 0.8rem;
      border-radius: 8px;
    }

    .notes-list {
      display: flex;
      flex-direction: column;
      gap: 16px;
      max-height: 600px;
      overflow-y: auto;
      padding-right: 8px;
    }

    .notes-list::-webkit-scrollbar {
      width: 6px;
    }

    .notes-list::-webkit-scrollbar-track {
      background: #f1f5f9;
      border-radius: 10px;
    }

    .notes-list::-webkit-scrollbar-thumb {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      border-radius: 10px;
    }

    .note-card {
      background: white;
      border-radius: 14px;
      padding: 18px 18px 14px;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.04);
      border: 1px solid #f0f0f0;
      transition: all 0.25s;
      cursor: pointer;
      animation: slideIn 0.4s ease-out;
    }

    .note-card:hover {
      transform: translateY(-3px);
      box-shadow: 0 12px 24px rgba(0, 0, 0, 0.08);
      border-color: #667eea;
    }

    @keyframes slideIn {
      from { opacity: 0; transform: translateX(20px); }
      to { opacity: 1; transform: translateX(0); }
    }

    .note-card-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 8px;
    }

    .note-card-title {
      font-weight: 650;
      font-size: 1.2rem;
      color: #1f2937;
      word-break: break-word;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .note-preview {
      color: #6b7280;
      line-height: 1.5;
      font-size: 0.95rem;
      display: -webkit-box;
      -webkit-line-clamp: 2;
      -webkit-box-orient: vertical;
      overflow: hidden;
      margin-bottom: 10px;
      word-break: break-word;
    }

    .note-meta {
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 0.8rem;
      color: #9ca3af;
    }

    .category-badge {
      padding: 4px 12px;
      border-radius: 20px;
      font-size: 0.75rem;
      font-weight: 600;
      background: rgba(102, 126, 234, 0.08);
      color: #667eea;
    }

    .empty-state {
      text-align: center;
      padding: 60px 20px;
      color: #9ca3af;
    }

    /* ---------- МОДАЛЬНОЕ ОКНО (РЕДАКТОР) ---------- */
    .modal-overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.5);
      backdrop-filter: blur(6px);
      display: none;
      align-items: center;
      justify-content: center;
      z-index: 1000;
      padding: 25px;
    }

    .modal-overlay.active {
      display: flex;
    }

    .modal-container {
      background: white;
      border-radius: 28px;
      width: 100%;
      max-width: 900px;
      height: 85vh;
      max-height: 900px;
      display: flex;
      flex-direction: column;
      box-shadow: 0 30px 60px rgba(0, 0, 0, 0.4);
      animation: modalAppear 0.3s ease-out;
    }

    @keyframes modalAppear {
      from { opacity: 0; transform: scale(0.95) translateY(20px); }
      to { opacity: 1; transform: scale(1) translateY(0); }
    }

    .modal-header {
      padding: 18px 24px;
      border-bottom: 1px solid #e5e7eb;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .modal-title-input {
      font-size: 1.6rem;
      font-weight: 600;
      border: none;
      outline: none;
      width: 100%;
      background: transparent;
      color: #1f2937;
    }

    .modal-close {
      background: none;
      border: none;
      font-size: 1.8rem;
      cursor: pointer;
      color: #6b7280;
      padding: 0 8px;
      transition: 0.2s;
    }

    .modal-close:hover {
      color: #111827;
    }

    .toolbar {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      padding: 10px 20px;
      background: #f9fafb;
      border-bottom: 1px solid #e5e7eb;
      align-items: center;
    }

    .tool-btn {
      background: transparent;
      border: 1px solid #d1d5db;
      border-radius: 8px;
      padding: 8px 12px;
      font-size: 1rem;
      cursor: pointer;
      color: #374151;
      transition: 0.15s;
      display: inline-flex;
      align-items: center;
      gap: 4px;
      font-weight: 500;
    }

    .tool-btn:hover {
      background: #e5e7eb;
      border-color: #9ca3af;
    }

    .tool-btn.active-tool {
      background: #667eea;
      color: white;
      border-color: #667eea;
    }

    .modal-editor {
      flex: 1;
      padding: 20px 24px;
      font-size: 1.05rem;
      line-height: 1.7;
      border: none;
      outline: none;
      overflow-y: auto;
      white-space: pre-wrap;
      word-wrap: break-word;
      background: white;
    }

    .modal-editor:focus {
      background: #fefefe;
    }

    .modal-footer {
      padding: 16px 24px;
      border-top: 1px solid #e5e7eb;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 15px;
    }

    .modal-meta {
      display: flex;
      gap: 15px;
      align-items: center;
    }

    .notification {
      position: fixed;
      top: 20px;
      right: 20px;
      padding: 14px 24px;
      background: white;
      border-radius: 12px;
      box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
      display: none;
      z-index: 2000;
      font-weight: 500;
    }

    .notification.show {
      display: block;
      animation: slideInRight 0.4s ease-out;
    }

    @keyframes slideInRight {
      from { transform: translateX(100%); opacity: 0; }
      to { transform: translateX(0); opacity: 1; }
    }

    .notification.success { border-left: 5px solid #2dce89; }
    .notification.error { border-left: 5px solid #ef4444; }

    /* ---------- МОДАЛЬНОЕ ОКНО АККАУНТА ---------- */
    .auth-form {
      display: flex;
      flex-direction: column;
      gap: 15px;
      padding: 20px;
    }

    .auth-form h2 {
      margin-bottom: 5px;
    }

    .auth-toggle {
      font-size: 0.9rem;
      text-align: center;
    }

    .auth-toggle a {
      color: #667eea;
      cursor: pointer;
      font-weight: 600;
    }
  </style>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body>
<div class="particles">
  <div class="particle"></div><div class="particle"></div><div class="particle"></div>
  <div class="particle"></div><div class="particle"></div><div class="particle"></div>
</div>

<div class="container">
  <div class="header">
    <div class="logo"><i class="fas fa-book"></i></div>
    <h1>Чайные заметки</h1>
    <p class="subtitle">пить их не надо</p>
  </div>

  <!-- ПАНЕЛЬ АККАУНТА -->
  <div class="account-bar" id="accountBar">
    <span id="accountStatus"><i class="fas fa-user-circle"></i> Не в сети</span>
    <button class="btn btn-outline-light btn-small" id="authActionBtn"><i class="fas fa-sign-in-alt"></i> Войти / Регистрация</button>
    <button class="btn btn-outline-light btn-small" id="exportBtn" title="Экспорт заметок"><i class="fas fa-download"></i> Экспорт</button>
    <button class="btn btn-outline-light btn-small" id="importBtn" title="Импорт заметок"><i class="fas fa-upload"></i> Импорт</button>
    <input type="file" id="importFileInput" accept=".json" style="display:none;">
  </div>

  <div class="main-area">
    <div class="note-form">
      <h2 style="margin-bottom: 4px; color: #1f2937;">Новая заметка</h2>
      <p style="color: #6b7280; margin-bottom: 12px; font-size: 0.9rem;">Добавьте заголовок и текст</p>
      <div class="form-group">
        <label for="note-title">Заголовок</label>
        <input type="text" id="note-title" placeholder="О чём заметка?" maxlength="120">
      </div>
      <div class="form-group">
        <label for="note-content">Содержание</label>
        <textarea id="note-content" placeholder="Напишите что-нибудь..."></textarea>
      </div>
      <div class="form-group">
        <label for="note-category">Категория</label>
        <select id="note-category">
          <option value="work">Работа</option>
          <option value="personal">Личное</option>
          <option value="ideas">Идеи</option>
          <option value="study">Учеба</option>
          <option value="other">Другое</option>
        </select>
      </div>
      <div style="display: flex; gap: 12px; margin-top: 8px;">
        <button class="btn btn-primary" id="save-note"><i class="fas fa-plus"></i> Сохранить</button>
        <button class="btn btn-secondary" id="clear-form"><i class="fas fa-eraser"></i> Очистить</button>
      </div>
    </div>

    <div class="notes-list" id="notes-list">
      <div class="empty-state">
        <i class="fas fa-sticky-note" style="font-size: 3rem; opacity: 0.4;"></i>
        <h3 style="font-weight: 400; margin-top: 10px;">Нет заметок</h3>
        <p>Создайте первую запись</p>
      </div>
    </div>
  </div>
</div>

<!-- МОДАЛЬНОЕ ОКНО РЕДАКТИРОВАНИЯ -->
<div class="modal-overlay" id="editModal">
  <div class="modal-container">
    <div class="modal-header">
      <input type="text" id="modal-title" class="modal-title-input" placeholder="Заголовок заметки">
      <button class="modal-close" id="closeModalBtn">&times;</button>
    </div>
    <div class="toolbar">
      <button class="tool-btn" data-command="bold" title="Жирный (Ctrl+B)"><b>B</b></button>
      <button class="tool-btn" data-command="italic" title="Курсив (Ctrl+I)"><i>I</i></button>
      <button class="tool-btn" data-command="underline" title="Подчёркнутый (Ctrl+U)"><u>U</u></button>
      <button class="tool-btn" data-command="insertUnorderedList" title="Маркированный список"><i class="fas fa-list-ul"></i></button>
      <button class="tool-btn" data-command="insertOrderedList" title="Нумерованный список"><i class="fas fa-list-ol"></i></button>
      <span style="color:#9ca3af; font-size:0.8rem; margin-left:auto;">Ctrl+B / Ctrl+I / Ctrl+U</span>
    </div>
    <div id="modalEditor" class="modal-editor" contenteditable="true" placeholder="Начните писать..."></div>
    <div class="modal-footer">
      <div class="modal-meta">
        <select id="modalCategory" style="padding: 8px 12px; border-radius: 10px; border:1px solid #d1d5db;">
          <option value="work">Работа</option>
          <option value="personal">Личное</option>
          <option value="ideas">Идеи</option>
          <option value="study">Учеба</option>
          <option value="other">Другое</option>
        </select>
        <label style="display: flex; align-items: center; gap: 6px; font-size:0.9rem;">
          <input type="checkbox" id="modalImportant"> Важная
        </label>
      </div>
      <div style="display: flex; gap: 10px;">
        <button class="btn btn-secondary" id="deleteNoteBtn"><i class="fas fa-trash"></i> Удалить</button>
        <button class="btn btn-primary" id="updateNoteBtn"><i class="fas fa-save"></i> Сохранить изменения</button>
      </div>
    </div>
  </div>
</div>

<!-- МОДАЛЬНОЕ ОКНО АККАУНТА -->
<div class="modal-overlay" id="authModal">
  <div class="modal-container" style="max-width: 500px; height: auto; min-height: 400px;">
    <div class="modal-header">
      <h2 id="authModalTitle">Вход в аккаунт</h2>
      <button class="modal-close" id="closeAuthModalBtn">&times;</button>
    </div>
    <div class="auth-form" id="authForm">
      <div class="form-group">
        <label for="authLogin">Логин</label>
        <input type="text" id="authLogin" placeholder="Придумайте логин">
      </div>
      <div class="form-group">
        <label for="authPassword">Пароль</label>
        <input type="password" id="authPassword" placeholder="Введите пароль">
      </div>
      <div class="form-group" id="authPasswordConfirmGroup" style="display: none;">
        <label for="authPasswordConfirm">Подтвердите пароль</label>
        <input type="password" id="authPasswordConfirm" placeholder="Повторите пароль">
      </div>
      <button class="btn btn-primary" id="authSubmitBtn">Войти</button>
      <p class="auth-toggle">
        <span id="authToggleText">Нет аккаунта?</span> <a id="authToggleLink">Зарегистрироваться</a>
      </p>
    </div>
  </div>
</div>

<div class="notification" id="notification"><span id="notification-text"></span></div>

<script>
  (function() {
    // ==================== ЭЛЕМЕНТЫ ====================
    const noteTitleInput = document.getElementById('note-title');
    const noteContentTextarea = document.getElementById('note-content');
    const noteCategorySelect = document.getElementById('note-category');
    const saveBtn = document.getElementById('save-note');
    const clearBtn = document.getElementById('clear-form');
    const notesListEl = document.getElementById('notes-list');

    // Модальные элементы редактора
    const modalOverlay = document.getElementById('editModal');
    const modalTitleInput = document.getElementById('modal-title');
    const modalEditor = document.getElementById('modalEditor');
    const modalCategory = document.getElementById('modalCategory');
    const modalImportant = document.getElementById('modalImportant');
    const closeModalBtn = document.getElementById('closeModalBtn');
    const updateNoteBtn = document.getElementById('updateNoteBtn');
    const deleteNoteBtn = document.getElementById('deleteNoteBtn');

    // Аккаунт
    const accountStatus = document.getElementById('accountStatus');
    const authActionBtn = document.getElementById('authActionBtn');
    const exportBtn = document.getElementById('exportBtn');
    const importBtn = document.getElementById('importBtn');
    const importFileInput = document.getElementById('importFileInput');

    // Модальное окно авторизации
    const authModal = document.getElementById('authModal');
    const authModalTitle = document.getElementById('authModalTitle');
    const authLogin = document.getElementById('authLogin');
    const authPassword = document.getElementById('authPassword');
    const authPasswordConfirm = document.getElementById('authPasswordConfirm');
    const authPasswordConfirmGroup = document.getElementById('authPasswordConfirmGroup');
    const authSubmitBtn = document.getElementById('authSubmitBtn');
    const authToggleText = document.getElementById('authToggleText');
    const authToggleLink = document.getElementById('authToggleLink');
    const closeAuthModalBtn = document.getElementById('closeAuthModalBtn');

    // ==================== СОСТОЯНИЕ ====================
    let isRegisterMode = false;
    let currentUser = null; // { login, passwordHash }
    let notes = [];

    // ==================== ШИФРОВАНИЕ (простое, через пароль) ====================
    function simpleEncrypt(text, password) {
      if (!password) return text;
      let result = '';
      for (let i = 0; i < text.length; i++) {
        const charCode = text.charCodeAt(i) ^ password.charCodeAt(i % password.length);
        result += String.fromCharCode(charCode);
      }
      return btoa(result); // base64
    }

    function simpleDecrypt(encrypted, password) {
      if (!password) return encrypted;
      try {
        const text = atob(encrypted);
        let result = '';
        for (let i = 0; i < text.length; i++) {
          const charCode = text.charCodeAt(i) ^ password.charCodeAt(i % password.length);
          result += String.fromCharCode(charCode);
        }
        return result;
      } catch (e) {
        return '';
      }
    }

    // ==================== ЗАГРУЗКА ДАННЫХ ====================
    function loadNotes() {
      if (!currentUser) {
        notes = [];
        return;
      }
      const key = `notes_${currentUser.login}`;
      const raw = localStorage.getItem(key);
      if (raw) {
        try {
          const decrypted = simpleDecrypt(raw, currentUser.password);
          notes = JSON.parse(decrypted) || [];
        } catch (e) {
          notes = [];
        }
      } else {
        notes = [];
      }
    }

    function saveNotes() {
      if (!currentUser) return;
      const key = `notes_${currentUser.login}`;
      const json = JSON.stringify(notes);
      const encrypted = simpleEncrypt(json, currentUser.password);
      localStorage.setItem(key, encrypted);
    }

    // ==================== ПОЛЬЗОВАТЕЛИ ====================
    function getUsers() {
      try {
        return JSON.parse(localStorage.getItem('tea_users') || '{}');
      } catch (e) {
        return {};
      }
    }

    function saveUsers(users) {
      localStorage.setItem('tea_users', JSON.stringify(users));
    }

    // Простой хеш пароля (не для реальной безопасности, а для демонстрации)
    function hashPassword(password) {
      let hash = 0;
      for (let i = 0; i < password.length; i++) {
        const char = password.charCodeAt(i);
        hash = ((hash << 5) - hash) + char;
        hash |= 0; // Convert to 32bit integer
      }
      return 'hash_' + Math.abs(hash).toString(16) + '_' + btoa(password).substring(0, 8);
    }

    function registerUser(login, password) {
      const users = getUsers();
      if (users[login]) {
        showNotification('Пользователь с таким логином уже существует', 'error');
        return false;
      }
      users[login] = hashPassword(password);
      saveUsers(users);
      return true;
    }

    function loginUser(login, password) {
      const users = getUsers();
      if (!users[login]) {
        showNotification('Пользователь не найден', 'error');
        return false;
      }
      if (users[login] !== hashPassword(password)) {
        showNotification('Неверный пароль', 'error');
        return false;
      }
      return true;
    }

    function updateUIForAuth() {
      if (currentUser) {
        accountStatus.innerHTML = `<i class="fas fa-user-check"></i> ${currentUser.login}`;
        authActionBtn.innerHTML = '<i class="fas fa-sign-out-alt"></i> Выйти';
        loadNotes();
        renderNotesList();
      } else {
        accountStatus.innerHTML = '<i class="fas fa-user-circle"></i> Не в сети';
        authActionBtn.innerHTML = '<i class="fas fa-sign-in-alt"></i> Войти / Регистрация';
        notes = [];
        renderNotesList();
      }
    }

    function logout() {
      currentUser = null;
      localStorage.removeItem('tea_current_session');
      updateUIForAuth();
      showNotification('Вы вышли из аккаунта');
    }

    // Сохранить сессию (только на этом устройстве)
    function saveSession() {
      if (currentUser) {
        localStorage.setItem('tea_current_session', JSON.stringify({
          login: currentUser.login,
          password: currentUser.password
        }));
      } else {
        localStorage.removeItem('tea_current_session');
      }
    }

    function loadSession() {
      try {
        const session = JSON.parse(localStorage.getItem('tea_current_session'));
        if (session && session.login && session.password) {
          const users = getUsers();
          if (users[session.login] && users[session.login] === hashPassword(session.password)) {
            currentUser = session;
            return true;
          }
        }
      } catch (e) {}
      return false;
    }

    // ==================== ЭКСПОРТ / ИМПОРТ ====================
    function exportNotes() {
      if (!currentUser) {
        showNotification('Сначала войдите в аккаунт', 'error');
        return;
      }
      const data = {
        login: currentUser.login,
        notes: notes,
        exportDate: new Date().toISOString()
      };
      const blob = new Blob([JSON.stringify(data, null, 2)], { type: 'application/json' });
      const url = URL.createObjectURL(blob);
      const a = document.createElement('a');
      a.href = url;
      a.download = `чайные-заметки-${currentUser.login}-${new Date().toISOString().slice(0,10)}.json`;
      a.click();
      URL.revokeObjectURL(url);
      showNotification('Заметки экспортированы в файл');
    }

    function importNotes(file) {
      const reader = new FileReader();
      reader.onload = function(e) {
        try {
          const data = JSON.parse(e.target.result);
          if (!data.notes || !Array.isArray(data.notes)) {
            showNotification('Неверный формат файла', 'error');
            return;
          }
          if (!currentUser) {
            showNotification('Сначала войдите в аккаунт', 'error');
            return;
          }
          if (data.login !== currentUser.login) {
            showNotification('Этот файл принадлежит другому пользователю: ' + data.login, 'error');
            return;
          }
          if (confirm(`Загрузить ${data.notes.length} заметок из файла? Текущие заметки будут заменены.`)) {
            notes = data.notes;
            saveNotes();
            renderNotesList();
            showNotification(`Загружено ${data.notes.length} заметок`);
          }
        } catch (err) {
          showNotification('Ошибка при чтении файла', 'error');
        }
      };
      reader.readAsText(file);
    }

    // ==================== УТИЛИТЫ ====================
    function getFirstSentence(html) {
      const doc = new DOMParser().parseFromString(html || '', 'text/html');
      const text = doc.body.textContent || '';
      const sentenceMatch = text.match(/^[^.!?]+[.!?]?/);
      return sentenceMatch ? sentenceMatch[0].trim() : text.substring(0, 70);
    }

    function showNotification(message, type = 'success') {
      const notif = document.getElementById('notification');
      document.getElementById('notification-text').textContent = message;
      notif.className = `notification ${type} show`;
      setTimeout(() => notif.classList.remove('show'), 2800);
    }

    function escapeHtml(text) {
      return String(text)
        .replace(/&/g, '&amp;')
        .replace(/</g, '&lt;')
        .replace(/>/g, '&gt;')
        .replace(/"/g, '&quot;');
    }

    // ==================== ОТОБРАЖЕНИЕ ЗАМЕТОК ====================
    function renderNotesList() {
      if (!notes.length) {
        notesListEl.innerHTML = `<div class="empty-state">
          <i class="fas fa-sticky-note" style="font-size:3rem;opacity:0.4;"></i>
          <h3 style="font-weight:400;margin-top:10px;">Нет заметок</h3><p>Создайте первую запись</p>
        </div>`;
        return;
      }

      notesListEl.innerHTML = notes.map((note, idx) => {
        const previewText = getFirstSentence(note.content || '');
        const categoryNames = { work:'Работа', personal:'Личное', ideas:'Идеи', study:'Учеба', other:'Другое' };
        const cat = categoryNames[note.category] || 'Другое';
        return `
          <div class="note-card" data-id="${note.id}" style="animation-delay:${idx * 0.03}s">
            <div class="note-card-header">
              <span class="note-card-title">${escapeHtml(note.title) || 'Без названия'} ${note.important ? '<i class="fas fa-star" style="color:#fbbf24;"></i>' : ''}</span>
            </div>
            <div class="note-preview">${escapeHtml(previewText) || 'Нет текста'}</div>
            <div class="note-meta">
              <span class="category-badge">${cat}</span>
              <span>${note.date || ''}</span>
            </div>
          </div>`;
      }).join('');

      document.querySelectorAll('.note-card').forEach(card => {
        card.addEventListener('click', (e) => {
          const id = parseInt(card.dataset.id, 10);
          openEditor(id);
        });
      });
    }

    // ==================== CRUD ЗАМЕТОК ====================
    function createNote() {
      if (!currentUser) {
        showNotification('Войдите в аккаунт, чтобы создавать заметки', 'error');
        return;
      }
      const title = noteTitleInput.value.trim();
      const rawContent = noteContentTextarea.value.trim();
      if (!title || !rawContent) {
        showNotification('Заполните заголовок и содержание', 'error');
        return;
      }

      const newNote = {
        id: Date.now(),
        title,
        content: rawContent.replace(/\n/g, '<br>'),
        category: noteCategorySelect.value,
        important: false,
        date: new Date().toLocaleDateString('ru-RU', { day:'2-digit', month:'2-digit', year:'numeric', hour:'2-digit', minute:'2-digit' })
      };

      notes.unshift(newNote);
      saveNotes();
      renderNotesList();
      clearForm();
      showNotification('Заметка добавлена');
    }

    function clearForm() {
      noteTitleInput.value = '';
      noteContentTextarea.value = '';
      noteCategorySelect.value = 'work';
      noteTitleInput.focus();
    }

    function openEditor(noteId) {
      const note = notes.find(n => n.id === noteId);
      if (!note) return;
      currentNoteId = note.id;
      modalTitleInput.value = note.title;
      modalEditor.innerHTML = note.content || '';
      modalCategory.value = note.category || 'work';
      modalImportant.checked = note.important || false;
      modalOverlay.classList.add('active');
      setTimeout(() => modalEditor.focus(), 50);
    }

    function closeEditor() {
      modalOverlay.classList.remove('active');
      currentNoteId = null;
      modalEditor.innerHTML = '';
    }

    function updateNoteFromModal() {
      if (!currentNoteId) return;
      const note = notes.find(n => n.id === currentNoteId);
      if (!note) return;
      const newTitle = modalTitleInput.value.trim();
      if (!newTitle) {
        showNotification('Заголовок не может быть пустым', 'error');
        return;
      }
      note.title = newTitle;
      note.content = modalEditor.innerHTML;
      note.category = modalCategory.value;
      note.important = modalImportant.checked;
      note.date = new Date().toLocaleDateString('ru-RU', { day:'2-digit', month:'2-digit', year:'numeric', hour:'2-digit', minute:'2-digit' });
      saveNotes();
      renderNotesList();
      closeEditor();
      showNotification('Изменения сохранены');
    }

    function deleteCurrentNote() {
      if (!currentNoteId) return;
      if (confirm('Удалить эту заметку навсегда?')) {
        notes = notes.filter(n => n.id !== currentNoteId);
        saveNotes();
        renderNotesList();
        closeEditor();
        showNotification('Заметка удалена');
      }
    }

    function execCommand(command, value = null) {
      document.execCommand(command, false, value);
      modalEditor.focus();
    }

    function updateToolbarState() {
      const tools = document.querySelectorAll('.tool-btn');
      tools.forEach(btn => {
        const cmd = btn.dataset.command;
        if (cmd && document.queryCommandState(cmd)) {
          btn.classList.add('active-tool');
        } else {
          btn.classList.remove('active-tool');
        }
      });
    }

    let currentNoteId = null;

    // ==================== АВТОРИЗАЦИЯ (МОДАЛЬНОЕ ОКНО) ====================
    function openAuthModal(mode = 'login') {
      isRegisterMode = (mode === 'register');
      if (isRegisterMode) {
        authModalTitle.textContent = 'Регистрация';
        authSubmitBtn.textContent = 'Зарегистрироваться';
        authToggleText.textContent = 'Уже есть аккаунт?';
        authToggleLink.textContent = 'Войти';
        authPasswordConfirmGroup.style.display = 'flex';
      } else {
        authModalTitle.textContent = 'Вход в аккаунт';
        authSubmitBtn.textContent = 'Войти';
        authToggleText.textContent = 'Нет аккаунта?';
        authToggleLink.textContent = 'Зарегистрироваться';
        authPasswordConfirmGroup.style.display = 'none';
      }
      authLogin.value = '';
      authPassword.value = '';
      authPasswordConfirm.value = '';
      authModal.classList.add('active');
      setTimeout(() => authLogin.focus(), 100);
    }

    function closeAuthModal() {
      authModal.classList.remove('active');
    }

    function handleAuthSubmit() {
      const login = authLogin.value.trim();
      const password = authPassword.value;

      if (!login || !password) {
        showNotification('Заполните все поля', 'error');
        return;
      }

      if (login.length < 3) {
        showNotification('Логин должен быть не менее 3 символов', 'error');
        return;
      }

      if (password.length < 3) {
        showNotification('Пароль должен быть не менее 3 символов', 'error');
        return;
      }

      if (isRegisterMode) {
        const passwordConfirm = authPasswordConfirm.value;
        if (password !== passwordConfirm) {
          showNotification('Пароли не совпадают', 'error');
          return;
        }
        if (registerUser(login, password)) {
          showNotification('Регистрация успешна! Войдите в аккаунт.');
          openAuthModal('login');
          return;
        }
      } else {
        if (loginUser(login, password)) {
          currentUser = { login, password };
          saveSession();
          closeAuthModal();
          updateUIForAuth();
          showNotification(`Добро пожаловать, ${login}!`);
        }
      }
    }

    function toggleAuthMode() {
      openAuthModal(isRegisterMode ? 'login' : 'register');
    }

    // ==================== ОБРАБОТЧИКИ СОБЫТИЙ ====================
    saveBtn.addEventListener('click', createNote);
    clearBtn.addEventListener('click', clearForm);
    noteContentTextarea.addEventListener('keydown', (e) => {
      if (e.ctrlKey && e.key === 'Enter') createNote();
    });

    closeModalBtn.addEventListener('click', closeEditor);
    modalOverlay.addEventListener('click', (e) => {
      if (e.target === modalOverlay) closeEditor();
    });
    updateNoteBtn.addEventListener('click', updateNoteFromModal);
    deleteNoteBtn.addEventListener('click', deleteCurrentNote);

    modalEditor.addEventListener('keydown', (e) => {
      if (e.ctrlKey && e.key === 's') {
        e.preventDefault();
        updateNoteFromModal();
      }
    });

    document.querySelectorAll('.tool-btn').forEach(btn => {
      btn.addEventListener('click', (e) => {
        e.preventDefault();
        const command = btn.dataset.command;
        if (command) execCommand(command);
      });
    });

    modalEditor.addEventListener('keyup', updateToolbarState);
    modalEditor.addEventListener('mouseup', updateToolbarState);

    // Аккаунт
    authActionBtn.addEventListener('click', () => {
      if (currentUser) {
        if (confirm('Выйти из аккаунта?')) logout();
      } else {
        openAuthModal('login');
      }
    });

    closeAuthModalBtn.addEventListener('click', closeAuthModal);
    authModal.addEventListener('click', (e) => {
      if (e.target === authModal) closeAuthModal();
    });

    authSubmitBtn.addEventListener('click', handleAuthSubmit);
    authToggleLink.addEventListener('click', toggleAuthMode);

    authPassword.addEventListener('keydown', (e) => {
      if (e.key === 'Enter') handleAuthSubmit();
    });
    authPasswordConfirm.addEventListener('keydown', (e) => {
      if (e.key === 'Enter') handleAuthSubmit();
    });

    // Экспорт / Импорт
    exportBtn.addEventListener('click', exportNotes);
    importBtn.addEventListener('click', () => importFileInput.click());
    importFileInput.addEventListener('change', (e) => {
      if (e.target.files[0]) {
        importNotes(e.target.files[0]);
        importFileInput.value = '';
      }
    });

    // ==================== ИНИЦИАЛИЗАЦИЯ ====================
    if (loadSession()) {
      updateUIForAuth();
    } else {
      updateUIForAuth();
    }
    noteTitleInput.focus();
  })();
</script>
</body>
</html>
