# 11224213林巧芝 11224216林品妤


# 使用 ChatGPT 輕鬆創建用戶註冊頁面

隨著 AI 技術的快速發展，ChatGPT 已逐漸成為開發者的重要輔助工具。
在建立「使用者註冊頁面」這類常見功能時，透過 ChatGPT 可大幅提升開發效率，減少重複性工作。

# 需求分析

註冊頁面至少應包含以下功能與要素：

1.使用者名稱、電子郵件、密碼（基本必填項）

2.手機號碼或驗證碼欄位（選填）

3.表單驗證：格式正確、必填、密碼強度等

4.統一的頁面樣式與主題色




# 步驟與內容細項




## 第一步：生成 HTML 結構





<img width="736" height="692" alt="1" src="https://github.com/user-attachments/assets/46dc0d9b-3950-4068-94d7-ed62f8a8173d" />




程式碼



```python
<!DOCTYPE html>
<html lang="zh-Hant">
<head>
<meta charset="UTF-8">
<title>註冊帳號</title>
<style>
    body {
        font-family: Arial, sans-serif;
        background: #f2f2f2;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
    }
    .container {
        background: #fff;
        padding: 30px;
        border-radius: 12px;
        width: 320px;
        box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    input {
        width: 100%;
        padding: 10px;
        margin: 8px 0;
        border: 1px solid #ccc;
        border-radius: 6px;
    }
    button {
        width: 100%;
        padding: 10px;
        background: #007BFF;
        border: none;
        color: #fff;
        cursor: pointer;
        border-radius: 6px;
        font-size: 16px;
    }
    button:hover {
        background: #005FCC;
    }
    .error {
        color: red;
        font-size: 14px;
    }
</style>
</head>
<body>
<div class="container">
    <h2>註冊帳號</h2>
    <form id="registerForm">
        <input type="text" id="username" placeholder="使用者名稱">
        <input type="email" id="email" placeholder="Email">
        <input type="password" id="password" placeholder="密碼 (至少 8 字)">
        <button type="submit">註冊</button>
        <p class="error" id="errorMsg"></p>
    </form>
</div>

<script>
document.getElementById("registerForm").addEventListener("submit", function(e){
    e.preventDefault();
    let username = document.getElementById("username").value.trim();
    let email = document.getElementById("email").value.trim();
    let password = document.getElementById("password").value.trim();
    let error = document.getElementById("errorMsg");

    if (!username || !email || !password) {
        error.textContent = "請填寫所有欄位";
        return;
    }
    if (password.length < 8) {
        error.textContent = "密碼至少需要 8 個字";
        return;
    }

    error.textContent = "";
    alert("註冊成功 ✅");
});
</script>
</body>
</html>
```



### 依照它生成的結果測試如下




<img width="1920" height="1027" alt="2" src="https://github.com/user-attachments/assets/9c96aba3-4a32-4698-a0e1-e6afb2bd2f77" />





## 第二步：增加確認密碼欄位


二次確保用戶密碼



<img width="762" height="758" alt="3" src="https://github.com/user-attachments/assets/5997dbe2-d94b-4750-8b67-a1d30b34237d" />



程式碼生成如下


```python
<!DOCTYPE html>
<html lang="zh-Hant">
<head>
<meta charset="UTF-8">
<title>註冊帳號</title>
<style>
    body {
        font-family: Arial, sans-serif;
        background: #f2f2f2;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
    }
    .container {
        background: #fff;
        padding: 30px;
        border-radius: 12px;
        width: 320px;
        box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    input {
        width: 100%;
        padding: 10px;
        margin: 8px 0;
        border: 1px solid #ccc;
        border-radius: 6px;
    }
    button {
        width: 100%;
        padding: 10px;
        background: #007BFF;
        border: none;
        color: #fff;
        cursor: pointer;
        border-radius: 6px;
        font-size: 16px;
    }
    button:hover {
        background: #005FCC;
    }
    .error {
        color: red;
        font-size: 14px;
        height: 18px;
    }
</style>
</head>
<body>
<div class="container">
    <h2>註冊帳號</h2>

    <input type="text" id="username" placeholder="使用者名稱">
    <input type="email" id="email" placeholder="Email">
    <input type="password" id="password" placeholder="密碼 (至少 8 字)">
    <input type="password" id="confirmPassword" placeholder="再次輸入密碼">

    <button onclick="register()">註冊</button>
    <p class="error" id="msg"></p>
</div>

<script>
function register() {
    const username = document.getElementById("username").value.trim();
    const email = document.getElementById("email").value.trim();
    const password = document.getElementById("password").value.trim();
    const confirmPassword = document.getElementById("confirmPassword").value.trim();
    const msg = document.getElementById("msg");

    if (!username || !email || !password || !confirmPassword) {
        msg.textContent = "請填寫所有欄位";
        return;
    }

    if (password.length < 8) {
        msg.textContent = "密碼至少 8 個字";
        return;
    }

    if (password !== confirmPassword) {
        msg.textContent = "密碼與確認密碼不一致";
        return;
    }

    msg.textContent = "";
    alert("註冊成功 ✅");
}
</script>
</body>
</html>

```



測試結果



<img width="1920" height="1025" alt="4" src="https://github.com/user-attachments/assets/f7c2b5cd-73f5-44a3-bd4f-917f57fb02c1" />


## 第三步：最後測試功能是否正常



### 輸入正確帳號密碼


<img width="1920" height="1026" alt="5" src="https://github.com/user-attachments/assets/e91e404f-5a5c-48c2-915f-1ad39703082c" />



### 輸入少於8位數字密碼


<img width="1920" height="1027" alt="6" src="https://github.com/user-attachments/assets/1ff97f83-50ef-4a3d-8226-d9d67e430d15" />



### 輸入兩次不同的密碼


<img width="1920" height="1025" alt="7" src="https://github.com/user-attachments/assets/d004a1f9-ba5a-4a6a-ae42-46b0bd4df96d" />






