<!DOCTYPE html>
<html dir="rtl" lang="fa">
<head>
  <meta charset="utf-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>لوگو شاپ</title>
  <style>
    body {
      font-family: 'Tahoma', sans-serif;
      margin: 0;
      padding: 0;
      background: linear-gradient(to left, #00c6ff, #0072ff);
      color: #ffffff;
      line-height: 1.7;
      transition: background 0.4s, color 0.4s;
    }

    .box {
      background: rgba(0,0,0,0.7);
      padding: 2rem;
      border-radius: 16px;
      max-width: 400px;
      margin: 4rem auto;
      text-align: center;
    }

    input, button {
      width: 90%;
      padding: 10px;
      margin-top: 10px;
      border-radius: 8px;
      border: none;
      font-size: 16px;
      display: block;
      margin-left: auto;
      margin-right: auto;
    }

    button {
      background-color: #00c853;
      color: #fff;
      cursor: pointer;
      font-weight: bold;
    }

    .hidden {
      display: none;
    }

    #mainContent {
      display: none;
    }

    header, .names-section, .settings-menu {
      margin: 20px auto;
      max-width: 800px;
      background-color: rgba(0,0,0,0.6);
      padding: 1rem;
      border-radius: 10px;
    }

    .name-list {
      display: flex;
      justify-content: space-between;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .name-column {
      width: 48%;
    }

    .name {
      cursor: pointer;
      padding: 8px;
      background-color: rgba(255,255,255,0.1);
      margin-bottom: 5px;
      border-radius: 6px;
    }

    .name:hover {
      background-color: rgba(255,255,255,0.2);
    }

    .preview {
      text-align: center;
      margin-top: 20px;
    }

    .preview img {
      width: 200px;
      border-radius: 12px;
    }

    .download-btn {
      background-color: #ff4081;
      color: white;
      padding: 8px 16px;
      border-radius: 6px;
      text-decoration: none;
      margin-top: 10px;
      display: inline-block;
    }

    #themeToggle {
      position: fixed;
      top: 20px;
      left: 20px;
      z-index: 999;
      cursor: pointer;
    }

    #themeToggle img {
      width: 40px;
      height: 40px;
      transition: transform 0.3s ease;
    }

    .dark-mode {
      background: linear-gradient(to right, #1e1e1e, #121212);
      color: #ffffff;
    }

    .dark-mode .box,
    .dark-mode header,
    .dark-mode .names-section,
    .dark-mode .settings-menu {
      background-color: rgba(255, 255, 255, 0.05);
    }

    #settingsToggle {
      background-color: #ff9100;
      color: white;
      padding: 8px 16px;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      cursor: pointer;
      margin-bottom: 10px;
    }

    #settingsPanel {
      background-color: rgba(255,255,255,0.1);
      padding: 10px;
      border-radius: 8px;
    }
  </style>
</head>
<body>

<!-- تغییر تم -->
<div id="themeToggle" onclick="toggleTheme()" title="تغییر روز/شب">
  <img id="themeIcon" src="sun.png" alt="تم">
</div>

<!-- ورود -->
<div class="box">
  <h2>ورود به لوگوشاپ</h2>
  <div id="step1">
    <p>شماره موبایل خود را وارد کنید:</p>
    <input type="tel" id="mobile" placeholder="مثلاً 09123456789">
    <button onclick="sendCode()">ارسال کد</button>
  </div>
  <div id="step2" class="hidden">
    <p>کد ارسال‌شده را وارد کنید:</p>
    <input type="text" id="code" placeholder="کد ۴ رقمی">
    <button onclick="verifyCode()">ورود</button>
  </div>
</div>

<!-- محتوای اصلی -->
<div id="mainContent">
  <header>
    <h1>برنامه لوگوشاپ</h1>
    <input type="text" id="search" placeholder="جستجوی اسم..." oninput="searchName(this.value)">
  </header>

  <div class="names-section">
    <div class="name-list">
      <div class="name-column" id="boyNames">
        <h3>پسرانه</h3>
        <div class="name" onclick="showLogo('مهدی')">مهدی</div>
        <div class="name" onclick="showLogo('سینا')">سینا</div>
        <div class="name" onclick="showLogo('مرتضی')">مرتضی</div>
        <div class="name" onclick="showLogo('هکر')">هکر</div>
        <div class="name" onclick="showLogo('سام')">سام</div>
        <div class="name" onclick="showLogo('امیر')">امیر</div>
        <div class="name" onclick="showLogo('ابوالفضل')">ابوالفضل</div>
        <div class="name" onclick="showLogo('محمد')">محمد</div>
      </div>

      <div class="name-column" id="girlNames">
        <h3>دخترانه</h3>
        <div class="name" onclick="showLogo('ریحانه')">ریحانه</div>
        <div class="name" onclick="showLogo('نرگس')">نرگس</div>
        <div class="name" onclick="showLogo('معصومه')">معصومه</div>
        <div class="name" onclick="showLogo('نازنین')">نازنین</div>
        <div class="name" onclick="showLogo('هلیا')">هلیا</div>
        <div class="name" onclick="showLogo('باران')">باران</div>
        <div class="name" onclick="showLogo('سارا')">سارا</div>
      </div>
    </div>
    <div class="preview" id="preview"></div>
  </div>

  <!-- تنظیمات -->
  <div class="settings-menu">
    <button id="settingsToggle">⚙️ تنظیمات</button>
    <div id="settingsPanel" class="hidden">
      <a href="https://shorts.aparat.com/user/Hossein_game_3689/shorts" target="_blank">آپارات سازنده</a><br>
      <a href="https://rubika.ir/joinc/DIFAGEEB0ABDOOQBBNMDDCIDDSBTCOFG" target="_blank">کانال روبیکا</a><br>
      <p>نسخه: 1.0.0</p>
    </div>
  </div>
</div>

<script>
  let testCode = "1234";
  let isDark = false;

  function sendCode() {
    const mobile = document.getElementById("mobile").value;
    if (mobile.length !== 11 || !mobile.startsWith("09")) {
      alert("شماره موبایل معتبر وارد کنید");
      return;
    }
    alert("کد تستی: " + testCode);
    document.getElementById("step1").classList.add("hidden");
    document.getElementById("step2").classList.remove("hidden");
  }

  function verifyCode() {
    const entered = document.getElementById("code").value;
    if (entered === testCode) {
      alert("ورود موفق! در حال بارگذاری لوگوشاپ...");
      document.querySelector(".box").style.display = "none";
      document.getElementById("mainContent").style.display = "block";
    } else {
      alert("کد اشتباه است");
    }
  }

  function showLogo(name) {
    const preview = document.getElementById("preview");
    const imgPath = `logos/${name}.jpg`;
    preview.innerHTML = `
      <img src="${imgPath}" alt="${name}" />
      <br>
      <a href="${imgPath}" class="download-btn" download>دانلود لوگو</a>
    `;
  }

  function searchName(value) {
    const allNames = document.querySelectorAll('.name');
    allNames.forEach(n => {
      n.style.display = n.innerText.includes(value) ? "block" : "none";
    });
  }

  function toggleTheme() {
    document.body.classList.toggle("dark-mode");
    const icon = document.getElementById("themeIcon");
    isDark = !isDark;
    icon.src = isDark ? "moon.png" : "sun.png";
  }

  document.getElementById("settingsToggle").addEventListener("click", () => {
    document.getElementById("settingsPanel").classList.toggle("hidden");
  });
</script>
</body>
</html>
