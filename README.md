<!DOCTYPE html>
<html lang="ku" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>XOSHNAW AI PREMIUM</title>

<script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>

<style>

*{
  box-sizing:border-box;
  margin:0;
  padding:0;
}

body{
  font-family:Arial,Tahoma,sans-serif;
  background:#f5f7fb;
  color:#151515;
  direction:rtl;
}

header{
  background:#111827;
  color:white;
  padding:15px 20px;
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:10px;
  position:sticky;
  top:0;
  z-index:50;
}

.logo{
  font-size:21px;
  font-weight:bold;
}

.header-actions{
  display:flex;
  gap:8px;
}

button{
  border:0;
  cursor:pointer;
  font-family:inherit;
}

.header-btn{
  padding:10px 15px;
  border-radius:10px;
  background:#fff;
  color:#111827;
  font-weight:bold;
}

.dark-btn{
  background:#2563eb;
  color:white;
}

.hero{
  padding:70px 20px;
  text-align:center;
  background:linear-gradient(135deg,#111827,#2563eb);
  color:white;
}

.hero .big-emoji{
  font-size:65px;
  margin-bottom:15px;
}

.hero h1{
  font-size:38px;
  margin-bottom:15px;
}

.hero p{
  max-width:700px;
  margin:auto;
  line-height:1.9;
  font-size:17px;
}

.hero-btn{
  margin-top:25px;
  padding:14px 25px;
  border-radius:12px;
  background:#fff;
  color:#111827;
  font-size:16px;
  font-weight:bold;
}

.container{
  width:min(1100px,92%);
  margin:auto;
}

section{
  padding:55px 0;
}

.section-title{
  text-align:center;
  font-size:28px;
  margin-bottom:30px;
}

.cards{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:20px;
}

.card{
  background:white;
  border-radius:18px;
  padding:28px;
  box-shadow:0 8px 30px rgba(0,0,0,.07);
  text-align:center;
}

.emoji{
  font-size:45px;
  margin-bottom:15px;
}

.card h3{
  margin-bottom:12px;
}

.card p{
  color:#666;
  line-height:1.8;
}

.videos{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:20px;
}

.video-card{
  background:white;
  border-radius:18px;
  overflow:hidden;
  box-shadow:0 8px 30px rgba(0,0,0,.07);
}

.video-placeholder{
  height:170px;
  display:flex;
  align-items:center;
  justify-content:center;
  background:#111827;
  color:white;
  font-size:50px;
}

.video-info{
  padding:20px;
}

.video-info h3{
  margin-bottom:10px;
}

.video-info p{
  color:#666;
  line-height:1.7;
}

.plans{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:20px;
}

.plan{
  position:relative;
  background:white;
  border-radius:20px;
  padding:30px 25px;
  box-shadow:0 8px 30px rgba(0,0,0,.08);
  text-align:center;
}

.plan.featured{
  border:3px solid #2563eb;
}

.badge{
  position:absolute;
  top:0;
  left:50%;
  transform:translate(-50%,-50%);
  background:#2563eb;
  color:white;
  padding:7px 15px;
  border-radius:20px;
  font-size:13px;
  white-space:nowrap;
}

.price{
  font-size:34px;
  font-weight:bold;
  margin:18px 0;
  color:#2563eb;
}

.price small{
  font-size:14px;
}

.plan ul{
  list-style:none;
  text-align:right;
  line-height:2.2;
  margin:15px 0 25px;
}

.plan button,
.submit-btn{
  width:100%;
  padding:13px;
  border-radius:11px;
  background:#2563eb;
  color:white;
  font-weight:bold;
  font-size:15px;
}

.dashboard,
.admin-panel{
  display:none;
  margin:30px auto;
  width:min(1100px,92%);
  background:white;
  padding:30px;
  border-radius:20px;
  box-shadow:0 8px 30px rgba(0,0,0,.08);
}

.status{
  padding:15px;
  border-radius:12px;
  margin:15px 0;
  font-weight:bold;
}

.status.pending{
  background:#fff3cd;
  color:#856404;
}

.status.active{
  background:#d1fae5;
  color:#065f46;
}

.logout{
  margin-top:20px;
  padding:12px 20px;
  border-radius:10px;
  background:#dc2626;
  color:white;
  font-weight:bold;
}

.admin-email{
  background:#eef2ff;
  color:#3730a3;
  padding:12px;
  border-radius:10px;
  margin:15px 0;
  text-align:center;
  font-weight:bold;
}

.admin-stats{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:15px;
  margin:20px 0;
}

.stat{
  background:#f8fafc;
  border-radius:15px;
  padding:20px;
  text-align:center;
  line-height:1.8;
}

.stat strong{
  font-size:25px;
}

.admin-premium-box{
  margin-top:25px;
  padding:25px;
  border-radius:18px;
  background:linear-gradient(135deg,#111827,#1d4ed8);
  color:white;
}

.admin-premium-box p{
  line-height:1.8;
  margin:10px 0 20px;
}

.admin-premium-status{
  background:rgba(255,255,255,.15);
  padding:15px;
  border-radius:12px;
  margin-bottom:18px;
}

.admin-premium-buttons{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:10px;
}

.admin-premium-btn{
  background:white;
  color:#111827;
  padding:14px 8px;
  border-radius:12px;
  font-weight:bold;
}

.payment-list{
  margin-top:20px;
}

.payment-item{
  background:#f8fafc;
  padding:18px;
  border-radius:14px;
  margin-bottom:12px;
  line-height:1.9;
}

.payment-item img{
  max-width:180px;
  border-radius:10px;
  display:block;
  margin:10px 0;
}

.admin-user{
  border:1px solid #e5e7eb;
  padding:18px;
  border-radius:14px;
  margin:12px 0;
  line-height:2;
}

.accept{
  background:#16a34a;
  color:white;
  padding:9px 15px;
  border-radius:8px;
  margin-left:5px;
}

.reject{
  background:#dc2626;
  color:white;
  padding:9px 15px;
  border-radius:8px;
}

.modal{
  display:none;
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.65);
  z-index:100;
  align-items:center;
  justify-content:center;
  padding:15px;
  overflow:auto;
}

.modal-box{
  width:min(520px,100%);
  max-height:92vh;
  overflow:auto;
  background:white;
  border-radius:20px;
  padding:25px;
  position:relative;
}

.close{
  position:absolute;
  top:10px;
  left:12px;
  width:35px;
  height:35px;
  border-radius:50%;
  background:#f1f5f9;
  font-size:25px;
}

.modal-title{
  text-align:center;
  margin-bottom:25px;
}

.form-group{
  margin-bottom:16px;
}

.form-group label{
  display:block;
  margin-bottom:7px;
  font-weight:bold;
}

input,
textarea{
  width:100%;
  padding:12px;
  border:1px solid #d1d5db;
  border-radius:10px;
  font-family:inherit;
  font-size:15px;
}

textarea{
  min-height:90px;
  resize:vertical;
}

.selected-plan{
  background:#eff6ff;
  padding:15px;
  border-radius:12px;
  text-align:center;
  line-height:2;
  margin-bottom:20px;
}

.fib-box{
  background:#eff6ff;
  border:1px solid #bfdbfe;
  padding:20px;
  border-radius:15px;
  margin-bottom:20px;
}

.fib-number{
  background:white;
  padding:15px;
  text-align:center;
  font-size:24px;
  font-weight:bold;
  letter-spacing:2px;
  border-radius:10px;
  margin:15px 0;
}

.notice{
  background:#dcfce7;
  color:#166534;
  padding:10px;
  border-radius:8px;
  text-align:center;
}

.warning{
  margin-top:12px;
  background:#fee2e2;
  color:#991b1b;
  padding:12px;
  border-radius:10px;
  line-height:1.8;
  text-align:center;
}

.success{
  display:none;
  background:#dcfce7;
  color:#166534;
  padding:18px;
  border-radius:12px;
  text-align:center;
  line-height:1.8;
}

footer{
  background:#111827;
  color:white;
  text-align:center;
  padding:30px 15px;
  margin-top:30px;
}

@media(max-width:800px){

  .cards,
  .videos,
  .plans{
    grid-template-columns:1fr;
  }

  .admin-stats{
    grid-template-columns:1fr;
  }

  .admin-premium-buttons{
    grid-template-columns:1fr;
  }

  header{
    flex-direction:column;
  }

  .hero h1{
    font-size:30px;
  }

}

</style>
</head>

<body>

<header>

  <div class="logo">
    XOSHNAW AI PREMIUM
  </div>

  <div class="header-actions">

    <button class="header-btn" onclick="openLogin()">
      👤 چوونەژوورەوە
    </button>

    <button class="header-btn dark-btn" onclick="openRegister()">
      📝 تۆمارکردن
    </button>

  </div>

</header>


<section class="hero">

  <div class="big-emoji">🤖</div>

  <h1>
    بەخێربێیت بۆ XOSHNAW AI
  </h1>

  <p>
    شوێنێکی تایبەت بۆ فێربوونی AI Tools،
    ڤیدیۆی فێرکاری، ئامرازە زیرەکەکان
    و ناوەڕۆکی Premium.
  </p>

  <button class="hero-btn" onclick="scrollToPlans()">
    👑 بەژداربوونی Premium
  </button>

</section>


<section>

<div class="container">

<h2 class="section-title">
🚀 چی بەدەست دەهێنیت؟
</h2>

<div class="cards">

<div class="card">
<div class="emoji">🤖</div>
<h3>AI Tools</h3>
<p>
فێربوونی ئامرازەکانی AI و چۆنیەتی بەکارهێنانیان.
</p>
</div>

<div class="card">
<div class="emoji">🎬</div>
<h3>ڤیدیۆی فێرکاری</h3>
<p>
ڤیدیۆی نوێی فێرکاری بە شێوەی ڕوون و ئاسان.
</p>
</div>

<div class="card">
<div class="emoji">👑</div>
<h3>Premium</h3>
<p>
دەستگەیشتن بە ناوەڕۆکی تایبەت بۆ ئەندامانی Premium.
</p>
</div>

</div>

</div>

</section>


<section>

<div class="container">

<h2 class="section-title">
🎬 ڤیدیۆکانی فێرکاری
</h2>

<div class="videos">

<div class="video-card">
<div class="video-placeholder">▶️</div>
<div class="video-info">
<h3>AI Tool ـی یەکەم</h3>
<p>
ڤیدیۆی فێرکاری بۆ ئەندامانی Premium.
</p>
</div>
</div>

<div class="video-card">
<div class="video-placeholder">▶️</div>
<div class="video-info">
<h3>چۆن AI بەکاربهێنین؟</h3>
<p>
فێربوونی بنەڕەتی AI بە زمانی کوردی.
</p>
</div>
</div>

<div class="video-card">
<div class="video-placeholder">🔒</div>
<div class="video-info">
<h3>Premium Video</h3>
<p>
ئەم ڤیدیۆیە تەنها بۆ ئەندامانی Premium ـە.
</p>
</div>
</div>

</div>

</div>

</section>


<section id="plans">

<div class="container">

<h2 class="section-title">
👑 پلانەکانی Premium
</h2>

<div class="plans">

<div class="plan">

<h3>هەفتانە</h3>

<div class="price">
1,500 <small>د.ع</small>
</div>

<ul>
<li>✓ دەستگەیشتن بە Premium</li>
<li>✓ ڤیدیۆی فێرکاری</li>
<li>✓ AI Tools</li>
</ul>

<button onclick="choosePlan('هەفتانە',1500)">
هەڵبژاردن
</button>

</div>


<div class="plan featured">

<div class="badge">
باشترین هەڵبژاردە
</div>

<h3>مانگانە</h3>

<div class="price">
4,000 <small>د.ع</small>
</div>

<ul>
<li>✓ دەستگەیشتن بە Premium</li>
<li>✓ هەموو ڤیدیۆکان</li>
<li>✓ AI Tools</li>
<li>✓ ناوەڕۆکی نوێ</li>
</ul>

<button onclick="choosePlan('مانگانە',4000)">
هەڵبژاردن
</button>

</div>


<div class="plan">

<h3>ساڵانە</h3>

<div class="price">
15,000 <small>د.ع</small>
</div>

<ul>
<li>✓ Premium بۆ ساڵێک</li>
<li>✓ هەموو ڤیدیۆکان</li>
<li>✓ AI Tools</li>
<li>✓ هەموو ناوەڕۆکی داهاتوو</li>
</ul>

<button onclick="choosePlan('ساڵانە',15000)">
هەڵبژاردن
</button>

</div>

</div>

</div>

</section>


<div id="dashboard" class="dashboard">

<h2>👤 بەخێربێیت</h2>

<p id="dashboardName"></p>

<div id="premiumStatus" class="status pending">
Premium هێشتا چالاک نەکراوە.
</div>

<div id="dashboardPlan"></div>

<div id="myPayments" class="payment-list"></div>

<button class="logout" onclick="logout()">
چوونەدەرەوە
</button>

</div>


<div id="adminPanel" class="admin-panel">

<h2>👨‍💼 XOSHNAW ADMIN PANEL</h2>

<div class="admin-email">
lawaking24@gmail.com
</div>

<div class="admin-stats">

<div class="stat">
👥
<br>
<strong id="userCount">0</strong>
<br>
Users
</div>

<div class="stat">
💰
<br>
<strong id="pendingCount">0</strong>
<br>
Pending
</div>

<div class="stat">
👑
<br>
<strong id="activeCount">0</strong>
<br>
Premium
</div>

</div>


<div class="admin-premium-box">

<h3>
👑 Premium ـی ئەدمین
</h3>

<p>
لێرەوە دەتوانیت بۆ ئەکاونتی ئەدمین
Premium چالاک بکەیت، بەبێ ناردنی پارە و وەسڵ.
</p>

<div id="adminPremiumStatus" class="admin-premium-status">
⏳ دۆخی Premium ـی ئەدمین...
</div>

<div class="admin-premium-buttons">

<button
class="admin-premium-btn"
onclick="activateAdminPremium('هەفتانە',7)">
👑 هەفتانە
<br>
7 ڕۆژ
</button>

<button
class="admin-premium-btn"
onclick="activateAdminPremium('مانگانە',30)">
👑 مانگانە
<br>
30 ڕۆژ
</button>

<button
class="admin-premium-btn"
onclick="activateAdminPremium('ساڵانە',365)">
👑 ساڵانە
<br>
365 ڕۆژ
</button>

</div>

</div>


<h3 style="margin-top:30px">
📋 داواکارییەکانی پارەدان
</h3>

<div id="adminPayments" class="payment-list"></div>


<h3 style="margin-top:30px">
👥 بەکارهێنەران
</h3>

<div id="adminUsers"></div>


<button class="logout" onclick="adminLogout()">
دەرچوون لە Admin
</button>

</div>


<footer>

<strong>XOSHNAW AI PREMIUM</strong>

<br><br>

فێربوون • AI • Technology • Premium

</footer>


<!-- REGISTER MODAL -->

<div id="registerModal" class="modal">

<div class="modal-box">

<button class="close" onclick="closeAll()">×</button>

<h2 class="modal-title">
📝 تۆمارکردنی ئەکاونت
</h2>

<div class="form-group">
<label>ناوی تەواو</label>
<input id="regName" type="text" placeholder="ناوی تەواوت">
</div>

<div class="form-group">
<label>ژمارەی مۆبایل</label>
<input id="regPhone" type="tel" placeholder="07xxxxxxxxx">
</div>

<div class="form-group">
<label>ئیمەیڵ</label>
<input id="regEmail" type="email" placeholder="example@gmail.com">
</div>

<div class="form-group">
<label>وشەی نهێنی</label>
<input id="regPassword" type="password" placeholder="وشەی نهێنی">
</div>

<button
class="submit-btn"
onclick="registerUser()">
📝 تۆمارکردن
</button>

<p style="text-align:center;margin-top:15px">

ئەکاونتت هەیە؟

<button
style="border:0;background:none;color:#0066cc;cursor:pointer;font-weight:bold"
onclick="openLogin()">
Login
</button>

</p>

</div>

</div>


<!-- LOGIN MODAL -->

<div id="loginModal" class="modal">

<div class="modal-box">

<button class="close" onclick="closeAll()">×</button>

<h2 class="modal-title">
🔐 چوونەژوورەوە
</h2>

<div class="form-group">
<label>ئیمەیڵ</label>
<input id="loginEmail" type="email" placeholder="example@gmail.com">
</div>

<div class="form-group">
<label>وشەی نهێنی</label>
<input id="loginPassword" type="password" placeholder="وشەی نهێنی">
</div>

<button
class="submit-btn"
onclick="loginUser()">
🔐 Login
</button>

</div>

</div>


<!-- PAYMENT MODAL -->

<div id="paymentModal" class="modal">

<div class="modal-box">

<button class="close" onclick="closePayment()">×</button>

<h2 class="modal-title">
💳 تەواوکردنی بەژداری
</h2>

<div class="selected-plan">

پلان:
<strong id="selectedPlan">---</strong>

<br>

بڕ:
<strong id="selectedPrice">---</strong>
د.ع

</div>


<div class="fib-box">

<h3>
🔵 پارەدان بە FIB
</h3>

<p style="margin-top:10px">

تکایە بچۆرە ناو ئەپی FIB ـەکەتەوە
و بڕی پارەکە بۆ ئەم ژمارەیە بنێرە:

</p>

<div class="fib-number">
7515176569
</div>

<div class="notice">
تکایە بڕی پارەکە بە وردی بنێرە.
</div>

<div class="warning">

بەژداربووی بەڕێز ❤️

<br>

تکایە لە بڕی پارەکە و ژمارەکە
دڵنیا ببەرەوە.

<br>

لە کاتی بە هەڵە ڕۆشتنی پارە بۆ هەر هەژمارێک،
بەرپرسیار نین!

</div>

</div>


<div id="paymentForm">

<div class="form-group">
<label>ناوی تەواو</label>
<input id="userName" type="text">
</div>

<div class="form-group">
<label>ژمارەی مۆبایل</label>
<input id="userPhone" type="tel">
</div>

<div class="form-group">
<label>ژمارەی مامەڵە</label>
<input id="transactionId" type="text" placeholder="ئەگەر هەیە">
</div>

<div class="form-group">
<label>وێنەی رسید / مامەڵە</label>
<input id="receiptImage" type="file" accept="image/*">
</div>

<div class="form-group">
<label>تێبینی</label>
<textarea
id="message"
placeholder="هەر تێبینییەکت هەیە"></textarea>
</div>

<button
class="submit-btn"
style="background:#00a85a"
onclick="sendPayment()">

📤 ناردنی وەسڵ بۆ ئەدمین

</button>

</div>


<div class="success" id="paymentSuccess">

✅ داواکارییەکەت تۆمارکرا!

<br>

ئەدمین پشکنینی وەسڵەکەت دەکات.

</div>

</div>

</div>


<script>

/* =========================
   SUPABASE
========================= */

const SUPABASE_URL =
"https://wpjqvpcqaufrpstnziad.supabase.co";

const SUPABASE_KEY =
"sb_publishable_9ALxJWahJqUFvtMXR7-5TA_XHBIF6ZK";

const ADMIN_EMAIL =
"lawaking24@gmail.com";

const supabaseClient =
window.supabase.createClient(
  SUPABASE_URL,
  SUPABASE_KEY
);


/* =========================
   VARIABLES
========================= */

let currentUser = null;
let currentProfile = null;
let selectedPlan = "";
let selectedPrice = 0;


/* =========================
   ESCAPE HTML
========================= */

function escapeHTML(value){

  if(value === null || value === undefined){
    return "";
  }

  return String(value)
    .replace(/&/g,"&amp;")
    .replace(/</g,"&lt;")
    .replace(/>/g,"&gt;")
    .replace(/"/g,"&quot;")
    .replace(/'/g,"&#039;");
}


/* =========================
   MODALS
========================= */

function openLogin(){

  closeAll();

  document.getElementById("loginModal").style.display="flex";
}


function openRegister(){

  closeAll();

  document.getElementById("registerModal").style.display="flex";
}


function closePayment(){

  document.getElementById("paymentModal").style.display="none";

}


function closeAll(){

  document.getElementById("loginModal").style.display="none";

  document.getElementById("registerModal").style.display="none";

  document.getElementById("paymentModal").style.display="none";

}


/* =========================
   REGISTER
========================= */

async function registerUser(){

  const name =
    document.getElementById("regName").value.trim();

  const phone =
    document.getElementById("regPhone").value.trim();

  const email =
    document.getElementById("regEmail").value.trim();

  const password =
    document.getElementById("regPassword").value;

  if(!name || !phone || !email || !password){

    alert("❌ تکایە هەموو خانەکان پڕ بکەرەوە.");

    return;
  }

  if(password.length < 6){

    alert("❌ وشەی نهێنی دەبێت لانیکەم 6 پیت بێت.");

    return;
  }

  try{

    const {data,error} =
      await supabaseClient.auth.signUp({

        email:email,

        password:password,

        options:{
          data:{
            full_name:name,
            phone:phone
          }
        }

      });


    if(error){

      alert(
        "❌ تۆمارکردن سەرکەوتوو نەبوو:\n" +
        error.message
      );

      return;
    }


    if(data.user){

      const {error:profileError} =
        await supabaseClient
          .from("profiles")
          .upsert({

            id:data.user.id,

            full_name:name,

            phone:phone,

            is_admin:
              email.toLowerCase() ===
              ADMIN_EMAIL.toLowerCase(),

            premium_active:false

          });


      if(profileError){

        console.error(profileError);

      }

    }


    alert(
      "✅ ئەکاونتەکەت دروست کرا.\n\n" +
      "ئێستا دەتوانیت Login بکەیت."
    );

    closeAll();

    document.getElementById("regName").value="";
    document.getElementById("regPhone").value="";
    document.getElementById("regEmail").value="";
    document.getElementById("regPassword").value="";


  }catch(error){

    console.error(error);

    alert("❌ هەڵەیەک ڕوویدا.");

  }

}


/* =========================
   LOGIN
========================= */

async function loginUser(){

  const email =
    document.getElementById("loginEmail").value.trim();

  const password =
    document.getElementById("loginPassword").value;

  if(!email || !password){

    alert("❌ تکایە ئیمەیڵ و وشەی نهێنی بنووسە.");

    return;
  }

  try{

    const {data,error} =
      await supabaseClient.auth.signInWithPassword({

        email:email,

        password:password

      });


    if(error){

      alert(
        "❌ Login سەرکەوتوو نەبوو:\n" +
        error.message
      );

      return;
    }


    currentUser = data.user;

    await loadProfile();

    closeAll();

    await showDashboard();

    if(isAdmin()){

      await showAdmin();

    }


  }catch(error){

    console.error(error);

    alert("❌ هەڵەیەک ڕوویدا.");

  }

}


/* =========================
   LOAD PROFILE
========================= */

async function loadProfile(){

  if(!currentUser){

    return null;

  }


  const {data,error} =
    await supabaseClient
      .from("profiles")
      .select("*")
      .eq("id",currentUser.id)
      .maybeSingle();


  if(error){

    console.error(error);

    return null;

  }


  currentProfile = data;

  return data;

}


/* =========================
   ADMIN CHECK
========================= */

function isAdmin(){

  return !!(
    currentUser &&
    currentUser.email &&
    currentUser.email.toLowerCase() ===
    ADMIN_EMAIL.toLowerCase()
  );

}


/* =========================
   DASHBOARD
========================= */

async function showDashboard(){

  if(!currentUser){

    return;

  }

  await loadProfile();

  const dashboard =
    document.getElementById("dashboard");

  dashboard.style.display="block";


  const name =
    currentProfile?.full_name ||
    currentUser.user_metadata?.full_name ||
    currentUser.email;


  document.getElementById("dashboardName").textContent =
    "سڵاو " + name;


  const status =
    document.getElementById("premiumStatus");


  const plan =
    document.getElementById("dashboardPlan");


  const active =
    currentProfile?.premium_active === true;


  let expiresText="";

  if(currentProfile?.premium_expires_at){

    const d =
      new Date(currentProfile.premium_expires_at);

    if(!isNaN(d.getTime())){

      expiresText =
        d.toLocaleDateString("ku-IQ");

    }

  }


  if(active){

    status.className="status active";

    status.innerHTML =
      "👑 Premium ـەکەت چالاکە.";

    plan.innerHTML =
      "<p><strong>پلان:</strong> " +
      escapeHTML(currentProfile.premium_plan || "") +
      "</p>" +

      (expiresText
        ? "<p><strong>کۆتایی:</strong> " +
          escapeHTML(expiresText) +
          "</p>"
        : "");

  }else{

    status.className="status pending";

    status.innerHTML =
      "Premium هێشتا چالاک نەکراوە.";

    plan.innerHTML="";

  }


  await loadMyPayments();

}


/* =========================
   MY PAYMENTS
========================= */

async function loadMyPayments(){

  const box =
    document.getElementById("myPayments");

  if(!currentUser){

    box.innerHTML="";

    return;

  }


  const {data,error} =
    await supabaseClient
      .from("payment_requests")
      .select("*")
      .eq("user_id",currentUser.id)
      .order("created_at",{ascending:false});


  if(error){

    console.error(error);

    box.innerHTML="";

    return;

  }


  if(!data || data.length===0){

    box.innerHTML =
      "<p style='color:#777'>هیچ داواکارییەکت نییە.</p>";

    return;

  }


  let html =
    "<h3 style='margin-bottom:12px'>📋 داواکارییەکانت</h3>";


  data.forEach(item=>{

    const status =
      item.status === "accepted"
      ? "✅ پەسەندکراو"
      : item.status === "rejected"
      ? "❌ ڕەتکرایەوە"
      : "⏳ چاوەڕوانی";


    html +=
      "<div class='payment-item'>" +

      "<strong>پلان:</strong> " +
      escapeHTML(item.plan || "") +

      "<br>" +

      "<strong>بڕ:</strong> " +
      escapeHTML(item.amount || "") +
      " د.ع" +

      "<br>" +

      "<strong>دۆخ:</strong> " +
      status +

      "</div>";

  });


  box.innerHTML=html;

}


/* =========================
   CHOOSE PLAN
========================= */

function choosePlan(plan,price){

  if(!currentUser){

    alert(
      "تکایە سەرەتا Register یان Login بکە."
    );

    openLogin();

    return;

  }


  selectedPlan = plan;
  selectedPrice = Number(price);


  /*
    👑 گرنگ:
    تەنها ئەدمین هیچ پارەدانێک ناکات.
    Premium ڕاستەوخۆ چالاک دەکرێت.
  */

  if(isAdmin()){

    const days =
      plan === "هەفتانە"
      ? 7
      : plan === "مانگانە"
      ? 30
      : 365;


    activateAdminPremium(plan,days);

    return;

  }


  /*
    👤 USER عادی:
    دەچێتە FIB
  */

  document.getElementById("selectedPlan").textContent =
    plan;

  document.getElementById("selectedPrice").textContent =
    selectedPrice.toLocaleString("en-US");


  const metadata =
    currentUser.user_metadata || {};


  document.getElementById("userName").value =
    currentProfile?.full_name ||
    metadata.full_name ||
    "";


  document.getElementById("userPhone").value =
    currentProfile?.phone ||
    metadata.phone ||
    "";


  document.getElementById("transactionId").value="";
  document.getElementById("receiptImage").value="";
  document.getElementById("message").value="";


  document.getElementById("paymentForm").style.display="block";

  document.getElementById("paymentSuccess").style.display="none";

  document.getElementById("paymentModal").style.display="flex";

}


/* =========================
   ADMIN SELF PREMIUM
========================= */

async function activateAdminPremium(plan,days){

  /*
    🔒 تەنها ADMIN
  */

  if(!currentUser){

    alert("❌ تکایە Login بکە.");

    return;

  }


  if(!isAdmin()){

    alert(
      "❌ ئەم تایبەتمەندییە تەنها بۆ ئەدمینە."
    );

    return;

  }


  const endDate =
    new Date();


  endDate.setDate(
    endDate.getDate() + Number(days)
  );


  try{

    const {error} =
      await supabaseClient
        .from("profiles")
        .update({

          premium_active:true,

          premium_plan:plan,

          premium_expires_at:
            endDate.toISOString()

        })
        .eq("id",currentUser.id);


    if(error){

      console.error(error);

      alert(
        "❌ Premium ـی ئەدمین چالاک نەکرا.\n\n" +
        error.message
      );

      return;

    }


    currentProfile = {

      ...(currentProfile || {}),

      premium_active:true,

      premium_plan:plan,

      premium_expires_at:
        endDate.toISOString()

    };


    /*
      🔔 ئەم ئاگادارکردنەوەیە تەنها
      لەسەر ئامێری ئەدمین دەردەکەوێت.
    */

    alert(

      "👑 Premium چالاک کرا!\n\n" +

      "پلان: " + plan + "\n" +

      "ماوە: " + days + " ڕۆژ\n\n" +

      "💳 هیچ پارەدانێک پێویست نییە."

    );


    await showDashboard();

    await showAdmin();

  }catch(error){

    console.error(error);

    alert(
      "❌ هەڵەیەک ڕوویدا."
    );

  }

}


/* =========================
   SEND PAYMENT
========================= */

async function sendPayment(){

  if(!currentUser){

    alert("❌ تکایە Login بکە.");

    return;

  }


  /*
    👑 ئەدمین نابێت لێرە بێت.
  */

  if(isAdmin()){

    alert(
      "👑 ئەدمین پێویستی بە ناردنی وەسڵ نییە."
    );

    closePayment();

    return;

  }


  const name =
    document.getElementById("userName").value.trim();

  const phone =
    document.getElementById("userPhone").value.trim();

  const transactionId =
    document.getElementById("transactionId").value.trim();

  const file =
    document.getElementById("receiptImage").files[0];

  const message =
    document.getElementById("message").value.trim();


  if(!name || !phone){

    alert(
      "❌ تکایە ناو و ژمارەی مۆبایل پڕ بکەرەوە."
    );

    return;

  }


  if(!file){

    alert(
      "❌ تکایە وێنەی وەسڵ دابنێ."
    );

    return;

  }


  try{

    /*
      Upload receipt
    */

    const extension =
      file.name.split(".").pop();

    const fileName =
      currentUser.id +
      "_" +
      Date.now() +
      "." +
      extension;


    const filePath =
      fileName;


    const {error:uploadError} =
      await supabaseClient
        .storage
        .from("receipts")
        .upload(
          filePath,
          file,
          {
            cacheControl:"3600",
            upsert:false
          }
        );


    if(uploadError){

      console.error(uploadError);

      alert(
        "❌ ناردنی وێنەی وەسڵ سەرکەوتوو نەبوو:\n" +
        uploadError.message
      );

      return;

    }


    const {data:urlData} =
      supabaseClient
        .storage
        .from("receipts")
        .getPublicUrl(filePath);


    const receiptUrl =
      urlData?.publicUrl || "";


    /*
      Insert payment request
    */

    const {error} =
      await supabaseClient
        .from("payment_requests")
        .insert({

          user_id:currentUser.id,

          plan:selectedPlan,

          amount:selectedPrice,

          receipt_url:receiptUrl,

          status:"pending",

          transaction_id:
            transactionId || null,

          message:
            message || null

        });


    if(error){

      console.error(error);

      alert(
        "❌ داواکارییەکە نەنێردرا:\n" +
        error.message
      );

      return;

    }


    document.getElementById("paymentForm").style.display="none";

    document.getElementById("paymentSuccess").style.display="block";


    await loadMyPayments();


  }catch(error){

    console.error(error);

    alert("❌ هەڵەیەک ڕوویدا.");

  }

}


/* =========================
   ADMIN PANEL
========================= */

async function showAdmin(){

  if(!isAdmin()){

    document.getElementById("adminPanel").style.display="none";

    return;

  }


  document.getElementById("adminPanel").style.display="block";

  await renderAdmin();

}


/* =========================
   RENDER ADMIN
========================= */

async function renderAdmin(){

  if(!isAdmin()){

    return;

  }


  await loadProfile();


  const adminStatus =
    document.getElementById("adminPremiumStatus");


  if(currentProfile?.premium_active){

    let dateText="";

    if(currentProfile.premium_expires_at){

      const d =
        new Date(
          currentProfile.premium_expires_at
        );

      dateText =
        d.toLocaleDateString("ku-IQ");

    }


    adminStatus.innerHTML =
      "👑 Premium چالاکە" +

      "<br>" +

      "پلان: " +
      escapeHTML(
        currentProfile.premium_plan || ""
      ) +

      (dateText
        ? "<br>کۆتایی: " +
          escapeHTML(dateText)
        : "");

  }else{

    adminStatus.innerHTML =
      "⏳ Premium ـی ئەدمین چالاک نییە.";

  }


  /*
    USERS
  */

  const usersResult =
    await supabaseClient
      .from("profiles")
      .select("*")
      .order("created_at",{ascending:false});


  if(!usersResult.error){

    const users =
      usersResult.data || [];


    document.getElementById("userCount").textContent =
      users.length;


    const active =
      users.filter(
        u => u.premium_active === true
      ).length;


    document.getElementById("activeCount").textContent =
      active;


    let html="";


    users.forEach(user=>{

      const isUserAdmin =
        user.id === currentUser.id ||
        user.is_admin === true;


      html +=
        "<div class='admin-user'>" +

        "👤 <strong>" +
        escapeHTML(user.full_name || "بێ ناو") +
        "</strong>" +

        "<br>" +

        "📱 " +
        escapeHTML(user.phone || "-") +

        "<br>" +

        "👑 Premium: " +
        (user.premium_active
          ? "✅ چالاک"
          : "❌ ناچالاک") +

        (user.premium_plan
          ? "<br>📦 پلان: " +
            escapeHTML(user.premium_plan)
          : "") +

        (isUserAdmin
          ? "<br>👨‍💼 ADMIN"
          : "") +

        "</div>";

    });


    document.getElementById("adminUsers").innerHTML =
      html || "<p>هیچ بەکارهێنەرێک نییە.</p>";

  }


  /*
    PAYMENTS
  */

  const paymentsResult =
    await supabaseClient
      .from("payment_requests")
      .select("*")
      .order("created_at",{ascending:false});


  if(paymentsResult.error){

    console.error(
      paymentsResult.error
    );

    return;

  }


  const payments =
    paymentsResult.data || [];


  const pending =
    payments.filter(
      p => p.status === "pending"
    ).length;


  document.getElementById("pendingCount").textContent =
    pending;


  let paymentsHtml="";


  if(payments.length===0){

    paymentsHtml =
      "<p>هیچ داواکارییەک نییە.</p>";

  }else{

    for(const payment of payments){

      let user=null;


      const userResult =
        await supabaseClient
          .from("profiles")
          .select("*")
          .eq("id",payment.user_id)
          .maybeSingle();


      if(!userResult.error){

        user=userResult.data;

      }


      const status =
        payment.status === "accepted"
        ? "✅ پەسەندکراو"
        : payment.status === "rejected"
        ? "❌ ڕەتکرایەوە"
        : "⏳ چاوەڕوان";


      paymentsHtml +=

        "<div class='payment-item'>" +

        "<strong>👤 ناو:</strong> " +
        escapeHTML(
          user?.full_name || "نادیار"
        ) +

        "<br>" +

        "<strong>📱 مۆبایل:</strong> " +
        escapeHTML(
          user?.phone || "نادیار"
        ) +

        "<br>" +

        "<strong>📦 پلان:</strong> " +
        escapeHTML(
          payment.plan || ""
        ) +

        "<br>" +

        "<strong>💰 بڕ:</strong> " +
        escapeHTML(
          payment.amount || ""
        ) +
        " د.ع" +

        "<br>" +

        "<strong>🔢 مامەڵە:</strong> " +
        escapeHTML(
          payment.transaction_id || "-"
        ) +

        "<br>" +

        "<strong>📌 دۆخ:</strong> " +
        status;


      if(payment.message){

        paymentsHtml +=

          "<br><strong>📝 تێبینی:</strong> " +

          escapeHTML(
            payment.message
          );

      }


      if(payment.receipt_url){

        paymentsHtml +=

          "<br>" +

          "<a href='" +
          escapeHTML(payment.receipt_url) +
          "' target='_blank'>" +

          "<img src='" +
          escapeHTML(payment.receipt_url) +
          "' alt='Receipt'>" +

          "</a>";

      }


      if(payment.status === "pending"){

        paymentsHtml +=

          "<br><br>" +

          "<button class='accept' " +
          "onclick=\"acceptRequest('" +
          payment.id +
          "','" +
          payment.user_id +
          "','" +
          escapeHTML(payment.plan || "") +
          "')\">" +

          "✅ پەسەندکردن" +

          "</button>" +

          "<button class='reject' " +
          "onclick=\"rejectRequest('" +
          payment.id +
          "')\">" +

          "❌ ڕەتکردنەوە" +

          "</button>";

      }


      paymentsHtml +=
        "</div>";

    }

  }


  document.getElementById("adminPayments").innerHTML =
    paymentsHtml;

}


/* =========================
   ACCEPT REQUEST
========================= */

async function acceptRequest(
  paymentId,
  userId,
  plan
){

  if(!isAdmin()){

    alert("❌ دەسەڵاتت نییە.");

    return;

  }


  const days =
    plan === "هەفتانە"
    ? 7
    : plan === "مانگانە"
    ? 30
    : 365;


  const endDate =
    new Date();


  endDate.setDate(
    endDate.getDate() + days
  );


  try{

    const {error:profileError} =
      await supabaseClient
        .from("profiles")
        .update({

          premium_active:true,

          premium_plan:plan,

          premium_expires_at:
            endDate.toISOString()

        })
        .eq("id",userId);


    if(profileError){

      alert(
        "❌ Premium ـی بەکارهێنەر چالاک نەکرا:\n" +
        profileError.message
      );

      return;

    }


    const {error:paymentError} =
      await supabaseClient
        .from("payment_requests")
        .update({

          status:"accepted",

          reviewed_at:
            new Date().toISOString()

        })
        .eq("id",paymentId);


    if(paymentError){

      alert(
        "⚠️ Premium چالاک کرا، بەڵام دۆخی داواکاری نوێ نەکرایەوە."
      );

      console.error(paymentError);

      return;

    }


    alert("✅ داواکاری پەسەندکرا و Premium چالاک کرا.");

    await renderAdmin();

  }catch(error){

    console.error(error);

    alert("❌ هەڵەیەک ڕوویدا.");

  }

}


/* =========================
   REJECT REQUEST
========================= */

async function rejectRequest(paymentId){

  if(!isAdmin()){

    alert("❌ دەسەڵاتت نییە.");

    return;

  }


  const ok =
    confirm(
      "دڵنیایت دەتەوێت ئەم داواکارییە ڕەت بکەیتەوە؟"
    );


  if(!ok){

    return;

  }


  const {error} =
    await supabaseClient
      .from("payment_requests")
      .update({

        status:"rejected",

        reviewed_at:
          new Date().toISOString()

      })
      .eq("id",paymentId);


  if(error){

    alert(
      "❌ ڕەتکردنەوە سەرکەوتوو نەبوو:\n" +
      error.message
    );

    return;

  }


  alert("❌ داواکارییەکە ڕەتکرایەوە.");

  await renderAdmin();

}


/* =========================
   LOGOUT
========================= */

async function logout(){

  await supabaseClient.auth.signOut();

  currentUser=null;
  currentProfile=null;

  document.getElementById("dashboard").style.display="none";
  document.getElementById("adminPanel").style.display="none";

  alert("✅ چوویتە دەرەوە.");

}


/* =========================
   ADMIN LOGOUT
========================= */

async function adminLogout(){

  await logout();

}


/* =========================
   SCROLL
========================= */

function scrollToPlans(){

  document.getElementById("plans")
    .scrollIntoView({
      behavior:"smooth"
    });

}


function goPlans(){

  scrollToPlans();

}


/* =========================
   BACKGROUND CLOSE
========================= */

document.addEventListener(
  "click",
  function(e){

    if(e.target.classList.contains("modal")){

      e.target.style.display="none";

    }

  }
);


/* =========================
   AUTH STATE
========================= */

supabaseClient.auth.onAuthStateChange(
  async (event,session)=>{

    if(session?.user){

      currentUser =
        session.user;

      /*
        هەندێک جار Supabase
        پێویستی بە کەمێک کات هەیە
      */

      setTimeout(
        async ()=>{

          await loadProfile();

          await showDashboard();

          if(isAdmin()){

            await showAdmin();

          }

        },
        100
      );

    }else{

      currentUser=null;
      currentProfile=null;

      document.getElementById("dashboard").style.display="none";
      document.getElementById("adminPanel").style.display="none";

    }

  }
);


/* =========================
   START APP
========================= */

async function startApp(){

  const {data} =
    await supabaseClient.auth.getSession();


  if(data?.session?.user){

    currentUser =
      data.session.user;

    await loadProfile();

    await showDashboard();

    if(isAdmin()){

      await showAdmin();

    }

  }

}


startApp();

</script>

</body>
</html>
