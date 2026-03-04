# Facemask

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vynco App</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap');
  * { margin:0; padding:0; box-sizing:border-box; font-family: 'Poppins', sans-serif; }

  body, html { height:100%; width:100%; overflow:hidden; background:#121212; display:flex; justify-content:center; align-items:center; flex-direction:column; }
 /* Jump Animation to login page */
  #splash.jump {
    animation: jumpToLogin 0.8s forwards;
  }

  @keyframes jumpToLogin {
    0% { transform: translateY(0) scale(1); opacity:1; }
    50% { transform: translateY(-50px) scale(1.2); opacity:1; }
    100% { transform: translateY(-100vh) scale(0.5); opacity:0; }
  }

  /* Login Page Placeholder */
  #loginPage {
    position:absolute;
    top:0; left:0;
    width:100%; height:100%;
    display:flex;
    justify-content:center;
    align-items:center;
    background:#1e1e1e;
    color:white;
    flex-direction:column;
    opacity:0;
    transition: opacity 0.5s ease;
  }


  /* Splash Screen */
 
  #splash {
<div id="splash">
  <div class="logo">V</div>
  <div class="tagline">Be real you</div>
  <div class="from-text">
    from
    <span>Social Platform</span>
  </div>
</div>

    position:absolute;
    top:0; left:0;
    width:100%; height:100%;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    background:#121212;
    color:white;
    z-index:10;
    transition: opacity 0.8s ease;
  }

  .logo {
    width:80px;
    height:80px;
    background:white;
    color:#121212;
    font-weight:bold;
    font-size:36px;
    display:flex;
    justify-content:center;
    align-items:center;
    border-radius:20px;
    margin-bottom:20px;
    transform: scale(0);
    animation: logoPop 1s forwards;
  }

  @keyframes logoPop {
    0% { transform: scale(0); opacity:0; }
    70% { transform: scale(1.2); opacity:1; }
    100% { transform: scale(1); }
  }

  .tagline {
    font-size:20px;
    font-weight:300;
    opacity:0;
    animation: fadeIn 1.5s forwards;
    animation-delay:0.8s;
  }

  @keyframes fadeIn { to { opacity:1; } }

  .from-text {
    position:absolute;
    bottom:50px;
    text-align:center;
    font-size:14px;
    opacity:0;
    animation: fadeIn 1s forwards;
    animation-delay:1.5s;
  }

  .from-text span {
    display:block;
    font-weight:bold;
    font-size:16px;
    margin-top:2px;
  }

  #splash.jump {
    animation: jumpToLogin 0.8s forwards;
  }

  @keyframes jumpToLogin {
    0% { transform: translateY(0) scale(1); opacity:1; }
    50% { transform: translateY(-50px) scale(1.2); opacity:1; }
    100% { transform: translateY(-100vh) scale(0.5); opacity:0; }
  }

  /* Login Page */
  #loginPage {
    position:absolute;
    top:0; left:0;
    width:100%; height:100%;
    display:flex;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    background: linear-gradient(180deg, #f3f4f6, #ffffff);
    opacity:0;
    transition: opacity 0.5s ease;
    z-index:1;
  }

  #loginPage.active { opacity:1; }

  /* Login Page Styles */
  .login-container {
    width:90%;
    max-width:400px;
    display:flex;
    flex-direction:column;
    align-items:center;
    text-align:center;
    padding:20px;
    border-radius:15px;
    box-shadow:0 8px 20px rgba(0,0,0,0.08);
    background:#fff;
  }

  .login-container .logo {
    font-size:2.5rem;
    font-weight:700;
    color:#222;
    margin-bottom:20px;
    animation: float 3s ease-in-out infinite;
  }

  @keyframes float {
    0%,100% { transform: translateY(0); }
    50% { transform: translateY(-8px); }
  }

  input {
    width:100%;
    padding:12px;
    margin:10px 0;
    border:1px solid #ddd;
    border-radius:10px;
    font-size:1rem;
    box-sizing:border-box;
  }

  .password-container {
    width:100%;
    position:relative;
    display:flex;
    align-items:center;
  }

  .password-container input {
    flex:1;
    margin:10px 0;
  }

  .toggle-password {
    position:absolute;
    right:12px;
    top:50%;
    transform: translateY(-50%);
    background:none;
    border:none;
    cursor:pointer;
    font-weight:600;
    color:#111;
    font-size:0.9rem;
  }

  button {
    width:100%;
    padding:12px;
    background-color:#111;
    color:white;
    border:none;
    border-radius:10px;
    margin-top:15px;
    font-weight:600;
    cursor:pointer;
    transition:0.3s;
  }

  button:hover { background-color:#333; }

  .forgot { margin-top:10px; color:#666; font-size:0.9rem; cursor:pointer; }
  .create-account { margin-top:30px; font-size:1rem; color:#111; }
  .tagline-login { margin-bottom:40px; font-style:italic; font-weight:600; color:#666; animation: pulse 2s infinite; }
  @keyframes pulse { 0%,100% { opacity:1; } 50% { opacity:0.6; } }

  .language-selector { position:absolute; top:10px; right:10px; }
  select { padding:6px; border-radius:8px; border:1px solid #ccc; }

  @media (max-width:400px){
    .login-container .logo { font-size:2rem; margin-bottom:15px; }
    .tagline-login, .create-account { font-size:0.95rem; }
  }

</style>
</head>
<body>

<!-- Splash Screen -->
<div id="splash">
  <div class="logo">V</div>
  <div class="tagline">Be real you</div>
  <div class="from-text">from <span>Social Platform</span></div>
</div>

<!-- Login Page -->
<div id="loginPage">
  <div class="language-selector">
    <select id="languageSelect">
      <option value="en">English</option>
      <option value="es">Spanish</option>
      <option value="fr">French</option>
      <option value="hi">Hindi</option>
      <option value="ne">Nepali</option>
      <option value="zh">Chinese</option>
      <option value="ja">Japanese</option>
      <option value="ko">Korean</option>
      <option value="ru">Russian</option>
      <option value="pt">Portuguese</option>
      <option value="ar">Arabic</option>
      <option value="de">German</option>
      <option value="it">Italian</option>
    </select>
  </div>

  <div class="login-container">
    <div class="logo">Vynco</div>
    <input id="inputEmail" type="text" placeholder="">
    <div class="password-container">
      <input id="inputPassword" type="password" placeholder="">
      <button type="button" class="toggle-password" id="togglePassword">Show</button>
    </div>
    <button id="loginBtn"></button>
    <div class="forgot" id="forgotText"></div>
    <div class="create-account" id="createText"></div>
    <div class="tagline-login" id="taglineText"></div>
  </div>
</div>

<script>
  // Splash to Login Transition
  setTimeout(()=>{
    const splash = document.getElementById('splash');
    const login = document.getElementById('loginPage');
    splash.classList.add('jump');
    setTimeout(()=>{
      splash.style.display='none';
      login.classList.add('active');
    },800);
  },3000);

  // Translations
  const translations = {
    en: { email:"Enter your number or email", password:"Password", login:"Login", forgot:"Forgot password?", create:"Create a new Vynco account", tagline:"Be real you" },
    es: { email:"Introduce tu número o correo electrónico", password:"Contraseña", login:"Iniciar sesión", forgot:"¿Olvidaste tu contraseña?", create:"Crea una nueva cuenta Vynco", tagline:"Sé tu verdadero yo" },
    fr: { email:"Entrez votre numéro ou e-mail", password:"Mot de passe", login:"Connexion", forgot:"Mot de passe oublié ?", create:"Créer un nouveau compte Vynco", tagline:"Soyez vraiment vous" },
    hi: { email:"अपना नंबर या ईमेल दर्ज करें", password:"पासवर्ड", login:"लॉगिन करें", forgot:"पासवर्ड भूल गए?", create:"नया Vynco खाता बनाएं", tagline:"सच्चे बनो तुम" },
    ne: { email:"तपाईंको नम्बर वा इमेल प्रविष्ट गर्नुहोस्", password:"पासवर्ड", login:"लगइन गर्नुहोस्", forgot:"पासवर्ड बिर्सिनुभयो?", create:"नयाँ Vynco खाता सिर्जना गर्नुहोस्", tagline:"साँचो तपाईं बन्छ" },
    zh: { email:"输入您的号码或电子邮件", password:"密码", login:"登录", forgot:"忘记密码？", create:"创建新的 Vynco 帐户", tagline:"做真正的你" },
    ja: { email:"番号またはメールを入力してください", password:"パスワード", login:"ログイン", forgot:"パスワードをお忘れですか？", create:"新しいVyncoアカウントを作成", tagline:"本当の自分になろう" },
    ko: { email:"번호 또는 이메일을 입력하세요", password:"비밀번호", login:"로그인", forgot:"비밀번호를 잊으셨나요?", create:"새로운 Vynco 계정 만들기", tagline:"진짜 당신이 되세요" },
    ru: { email:"Введите свой номер или email", password:"Пароль", login:"Войти", forgot:"Забыли пароль?", create:"Создать новый аккаунт Vynco", tagline:"Будь настоящим собой" },
    pt: { email:"Digite seu número ou e-mail", password:"Senha", login:"Entrar", forgot:"Esqueceu a senha?", create:"Crie uma nova conta Vynco", tagline:"Seja você mesmo" },
    ar: { email:"أدخل رقمك أو بريدك الإلكتروني", password:"كلمة المرور", login:"تسجيل الدخول", forgot:"هل نسيت كلمة المرور؟", create:"إنشاء حساب Vynco جديد", tagline:"كن نفسك الحقيقي" },
    de: { email:"Geben Sie Ihre Nummer oder E-Mail ein", password:"Passwort", login:"Anmelden", forgot:"Passwort vergessen?", create:"Erstellen Sie ein neues Vynco-Konto", tagline:"Sei wirklich du" },
    it: { email:"Inserisci il tuo numero o email", password:"Password", login:"Accedi", forgot:"Hai dimenticato la password?", create:"Crea un nuovo account Vynco", tagline:"Sii veramente te stesso" }
  };

  const langSelect = document.getElementById("languageSelect");
  const inputEmail = document.getElementById("inputEmail");
  const inputPassword = document.getElementById("inputPassword");
  const loginBtn = document.getElementById("loginBtn");
  const forgotText = document.getElementById("forgotText");
  const createText = document.getElementById("createText");
  const taglineText = document.getElementById("taglineText");
  const togglePassword = document.getElementById("togglePassword");

  function applyLanguage(lang){
    const t = translations[lang] || translations['en'];
    inputEmail.placeholder = t.email;
    inputPassword.placeholder = t.password;
    loginBtn.innerText = t.login;
    forgotText.innerText = t.forgot;
    createText.innerText = t.create;
    taglineText.innerText = t.tagline;
  }

  langSelect.addEventListener("change", ()=>applyLanguage(langSelect.value));
  applyLanguage(langSelect.value);

  togglePassword.addEventListener("click", ()=>{
    if(inputPassword.type==="password"){
      inputPassword.type="text";
      togglePassword.textContent="Hide";
    } else {
      inputPassword.type="password";
      togglePassword.textContent="Show";
    }
  });

  loginBtn.addEventListener("click", ()=>{
    if(!inputEmail.value || !inputPassword.value){
      alert("Please fill in all fields");
    } else {
      console.log("Login submitted:", inputEmail.value, inputPassword.value);
    }
  });
</script>

</body>
</html>
