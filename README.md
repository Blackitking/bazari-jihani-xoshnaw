<!DOCTYPE html>
<html lang="ku" dir="rtl">

<head>

<meta charset="UTF-8">

<meta name="viewport"
content="width=device-width, initial-scale=1.0">

<title>XOSHNAW AI PREMIUM</title>

<!-- SUPABASE -->
<script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>

<style>

*{
box-sizing:border-box;
margin:0;
padding:0;
font-family:Arial,Tahoma,sans-serif;
}

body{
min-height:100vh;
background:
linear-gradient(
135deg,
#07111f,
#102d52,
#0066cc
);
color:#fff;
}

header{
padding:18px 5%;
display:flex;
justify-content:space-between;
align-items:center;
border-bottom:1px solid rgba(255,255,255,.15);
backdrop-filter:blur(10px);
position:sticky;
top:0;
z-index:20;
}

.logo{
font-size:23px;
font-weight:900;
}

.logo span{
color:#00d9ff;
}

.header-buttons{
display:flex;
gap:8px;
}

.header-btn{
border:0;
padding:10px 15px;
border-radius:12px;
background:#00d9ff;
color:#00131d;
font-weight:bold;
cursor:pointer;
}

.dark-btn{
background:#fff;
}

.container{
width:92%;
max-width:1100px;
margin:auto;
}

.hero{
text-align:center;
padding:60px 20px;
}

.hero .icon{
font-size:65px;
}

.hero h1{
font-size:42px;
margin:15px 0;
}

.hero h1 span{
color:#00d9ff;
}

.hero p{
max-width:700px;
margin:auto;
color:#d9e8f5;
line-height:1.9;
}

.main-btn{
margin-top:25px;
padding:15px 30px;
border:0;
border-radius:15px;
background:#00d9ff;
color:#00131d;
font-size:17px;
font-weight:bold;
cursor:pointer;
}

.section-title{
text-align:center;
margin:30px 0 20px;
}

.features,
.pricing,
.videos{
display:grid;
grid-template-columns:repeat(3,1fr);
gap:18px;
}

.feature,
.video-card{
background:rgba(255,255,255,.09);
border:1px solid rgba(255,255,255,.12);
border-radius:20px;
padding:22px;
text-align:center;
}

.feature .emoji{
font-size:42px;
margin-bottom:10px;
}

.feature p,
.video-card p{
color:#d4e2ef;
line-height:1.7;
margin-top:8px;
}

.video-card{
padding:0;
overflow:hidden;
text-align:right;
}

.video-placeholder{
height:160px;
display:flex;
align-items:center;
justify-content:center;
background:rgba(0,0,0,.2);
font-size:50px;
}

.video-info{
padding:18px;
}

.plan{
background:#fff;
color:#102033;
border-radius:22px;
padding:28px 22px;
text-align:center;
position:relative;
box-shadow:0 15px 40px rgba(0,0,0,.2);
}

.plan.popular{
border:4px solid #00d9ff;
}

.badge{
position:absolute;
top:-14px;
right:50%;
transform:translateX(50%);
background:#00d9ff;
color:#00131d;
padding:6px 15px;
border-radius:20px;
font-size:13px;
font-weight:bold;
}

.price{
font-size:34px;
font-weight:900;
color:#0066cc;
margin:12px 0;
}

.price small{
font-size:14px;
color:#555;
}

.plan ul{
list-style:none;
margin:18px 0;
line-height:2;
}

.plan li::before{
content:"✓ ";
color:#00a85a;
font-weight:bold;
}

.plan button,
.submit-btn{
width:100%;
padding:13px;
border:0;
border-radius:13px;
background:#0066cc;
color:white;
font-weight:bold;
cursor:pointer;
}

footer{
margin-top:50px;
padding:30px;
text-align:center;
background:rgba(0,0,0,.2);
color:#cbd9e5;
line-height:2;
}

/* MODAL */

.modal{
display:none;
position:fixed;
inset:0;
background:rgba(0,0,0,.78);
z-index:100;
padding:15px;
overflow:auto;
}

.modal-box{
width:100%;
max-width:560px;
margin:25px auto;
background:#fff;
color:#172334;
border-radius:24px;
padding:25px;
}

.close{
float:left;
background:#eee;
border:0;
width:35px;
height:35px;
border-radius:50%;
cursor:pointer;
font-size:20px;
}

.modal-title{
text-align:center;
margin-bottom:20px;
}

.form-group{
margin-top:14px;
}

.form-group label{
display:block;
margin-bottom:6px;
font-weight:bold;
}

.form-group input,
.form-group textarea{
width:100%;
padding:13px;
border:1px solid #ccd5df;
border-radius:11px;
outline:none;
}

.form-group textarea{
min-height:90px;
}

.selected-plan{
background:#eef8ff;
border:1px solid #bdeaff;
padding:15px;
border-radius:15px;
text-align:center;
margin-bottom:18px;
}

.fib-box{
background:#eef8ff;
padding:18px;
border-radius:15px;
text-align:center;
margin-bottom:18px;
}

.fib-number{
font-size:24px;
font-weight:900;
direction:ltr;
margin:12px 0;
color:#0066cc;
}

.notice{
background:#fff7df;
border:1px solid #ffe29a;
color:#604900;
padding:13px;
border-radius:12px;
line-height:1.8;
margin-top:12px;
}

.warning{
background:#ffe8e8;
border:2px solid #e00000;
color:#c00000;
padding:14px;
border-radius:12px;
line-height:1.8;
margin-top:12px;
font-weight:bold;
text-align:center;
}

.success{
display:none;
background:#eafff3;
color:#075d31;
padding:18px;
border-radius:14px;
text-align:center;
line-height:1.8;
margin-top:15px;
}

/* DASHBOARD */

.dashboard{
display:none;
padding:25px 0 50px;
}

.dashboard-box{
background:#fff;
color:#172334;
border-radius:20px;
padding:22px;
margin-top:20px;
}

.dashboard-box h2{
margin-bottom:15px;
}

.status{
padding:15px;
border-radius:12px;
background:#eee;
margin:10px 0;
font-weight:bold;
}

.status.active{
background:#eafff3;
color:#08733d;
}

.status.pending{
background:#fff7df;
color:#755500;
}

.status.rejected{
background:#ffe8e8;
color:#b00000;
}

.logout{
background:#e00000;
color:#fff;
border:0;
padding:10px 15px;
border-radius:10px;
cursor:pointer;
}

/* ADMIN */

.admin{
display:none;
padding:30px 0 60px;
}

.admin-header{
background:#fff;
color:#172334;
padding:20px;
border-radius:20px;
margin-bottom:20px;
}

.admin-stats{
display:grid;
grid-template-columns:repeat(3,1fr);
gap:12px;
margin-top:15px;
}

.stat{
padding:18px;
border-radius:15px;
background:#eef8ff;
text-align:center;
}

.requests{
display:grid;
gap:15px;
}

.request{
background:#fff;
color:#172334;
border-radius:18px;
padding:18px;
}

.request h3{
margin-bottom:10px;
}

.request p{
line-height:1.9;
}

.receipt-preview{
width:100%;
max-height:400px;
object-fit:contain;
background:#eee;
border-radius:12px;
margin:12px 0;
}

.request-buttons{
display:flex;
gap:10px;
margin-top:12px;
}

.accept,
.reject{
flex:1;
padding:12px;
border:0;
border-radius:10px;
color:#fff;
font-weight:bold;
cursor:pointer;
}

.accept{
background:#00a85a;
}

.reject{
background:#e00000;
}

.empty{
background:#fff;
color:#555;
padding:25px;
border-radius:15px;
text-align:center;
}

.hidden{
display:none!important;
}

.loading{
text-align:center;
padding:20px;
}

.user-request{
background:#eef8ff;
padding:15px;
border-radius:14px;
margin-top:15px;
color:#172334;
}

.small-btn{
border:0;
padding:9px 13px;
border-radius:9px;
cursor:pointer;
background:#0066cc;
color:#fff;
font-weight:bold;
}

@media(max-width:800px){

.features,
.pricing,
.videos{
grid-template-columns:1fr;
}

.hero h1{
font-size:31px;
}

.admin-stats{
grid-template-columns:1fr;
}

.header-buttons{
flex-direction:column;
}

}

</style>

</head>

<body>

<header>

<div class="logo">
XOSHNAW <span>AI</span> PREMIUM
</div>

<div class="header-buttons">

<button
class="header-btn"
onclick="openLogin()">
👤 چوونەژوورەوە
</button>

<button
class="header-btn dark-btn"
onclick="openRegister()">
📝 تۆمارکردن
</button>

</div>

</header>


<!-- HOME -->

<main id="home" class="container">

<section class="hero">

<div class="icon">🤖</div>

<h1>
بەخێربێیت بۆ
<span>XOSHNAW AI</span>
</h1>

<p>
شوێنێکی تایبەت بۆ فێربوونی AI Tools،
ڤیدیۆی فێرکاری، ئامرازە زیرەکەکان
و ناوەڕۆکی Premium.
</p>

<button
class="main-btn"
onclick="scrollToPlans()">

👑 بەژداربوونی Premium

</button>

</section>


<h2 class="section-title">
🚀 چی بەدەست دەهێنیت؟
</h2>

<section class="features">

<div class="feature">

<div class="emoji">🤖</div>

<h3>AI Tools</h3>

<p>
فێربوونی ئامرازەکانی AI
و چۆنیەتی بەکارهێنانیان.
</p>

</div>


<div class="feature">

<div class="emoji">🎬</div>

<h3>ڤیدیۆی فێرکاری</h3>

<p>
ڤیدیۆی نوێی فێرکاری
بە شێوەی ڕوون و ئاسان.
</p>

</div>


<div class="feature">

<div class="emoji">👑</div>

<h3>Premium</h3>

<p>
دەستگەیشتن بە ناوەڕۆکی تایبەت
بۆ ئەندامانی Premium.
</p>

</div>

</section>


<h2 class="section-title">
🎬 ڤیدیۆکانی فێرکاری
</h2>

<section class="videos">

<div class="video-card">

<div class="video-placeholder">
▶️
</div>

<div class="video-info">

<h3>
AI Tool ـی یەکەم
</h3>

<p>
ڤیدیۆی فێرکاری بۆ ئەندامانی Premium.
</p>

</div>

</div>


<div class="video-card">

<div class="video-placeholder">
▶️
</div>

<div class="video-info">

<h3>
چۆن AI بەکاربهێنین؟
</h3>

<p>
فێربوونی بنەڕەتی AI بە زمانی کوردی.
</p>

</div>

</div>


<div class="video-card">

<div class="video-placeholder">
🔒
</div>

<div class="video-info">

<h3>
Premium Video
</h3>

<p>
ئەم ڤیدیۆیە تەنها بۆ ئەندامانی Premium ـە.
</p>

</div>

</div>

</section>


<h2
id="plans"
class="section-title">

👑 پلانەکانی Premium

</h2>


<section class="pricing">


<div class="plan">

<h3>
هەفتانە
</h3>

<div class="price">
1,500
<small>د.ع</small>
</div>

<ul>

<li>دەستگەیشتن بە Premium</li>
<li>ڤیدیۆی فێرکاری</li>
<li>AI Tools</li>

</ul>

<button
onclick="choosePlan('هەفتانە',1500)">

هەڵبژاردن

</button>

</div>


<div class="plan popular">

<div class="badge">
باشترین هەڵبژاردە
</div>

<h3>
مانگانە
</h3>

<div class="price">
4,000
<small>د.ع</small>
</div>

<ul>

<li>دەستگەیشتن بە Premium</li>
<li>هەموو ڤیدیۆکان</li>
<li>AI Tools</li>
<li>ناوەڕۆکی نوێ</li>

</ul>

<button
onclick="choosePlan('مانگانە',4000)">

هەڵبژاردن

</button>

</div>


<div class="plan">

<h3>
ساڵانە
</h3>

<div class="price">
15,000
<small>د.ع</small>
</div>

<ul>

<li>Premium بۆ ساڵێک</li>
<li>هەموو ڤیدیۆکان</li>
<li>AI Tools</li>
<li>هەموو ناوەڕۆکی داهاتوو</li>

</ul>

<button
onclick="choosePlan('ساڵانە',15000)">

هەڵبژاردن

</button>

</div>

</section>

</main>


<!-- USER DASHBOARD -->

<section
id="dashboard"
class="dashboard container">

<div class="dashboard-box">

<h2>
👤 بەخێربێیت
</h2>

<p id="dashboardName"></p>

<div
id="premiumStatus"
class="status">

حاڵەت:
Premium نییە

</div>

<div id="dashboardPlan"></div>

<div id="myPayments"></div>

<br>

<button
class="logout"
onclick="logout()">

چوونەدەرەوە

</button>

</div>

</section>


<!-- ADMIN -->

<section
id="adminPanel"
class="admin container">

<div class="admin-header">

<h2>
👨‍💼 XOSHNAW ADMIN PANEL
</h2>

<p style="margin-top:10px">
📧 lawaking24@gmail.com
</p>

<div class="admin-stats">

<div class="stat">

👥
<br>

<strong id="userCount">
0
</strong>

<br>
Users

</div>


<div class="stat">

💰
<br>

<strong id="pendingCount">
0
</strong>

<br>
Pending

</div>


<div class="stat">

👑
<br>

<strong id="activeCount">
0
</strong>

<br>
Premium

</div>

</div>

<br>

<button
class="logout"
onclick="adminLogout()">

دەرچوون لە Admin

</button>

</div>

<div
id="requests"
class="requests">

</div>

</section>


<footer>

<strong>
XOSHNAW AI PREMIUM
</strong>

<br>

فێربوون • AI • Technology • Premium

</footer>


<!-- REGISTER -->

<div
class="modal"
id="registerModal">

<div class="modal-box">

<button
class="close"
onclick="closeAll()">
×
</button>

<h2 class="modal-title">
📝 تۆمارکردنی ئەکاونت
</h2>


<div class="form-group">

<label>
ناوی تەواو
</label>

<input
id="regName"
type="text"
placeholder="ناوی تەواوت">

</div>


<div class="form-group">

<label>
ژمارەی مۆبایل
</label>

<input
id="regPhone"
type="tel"
placeholder="07xxxxxxxxx">

</div>


<div class="form-group">

<label>
ئیمەیڵ
</label>

<input
id="regEmail"
type="email"
placeholder="example@gmail.com">

</div>


<div class="form-group">

<label>
وشەی نهێنی
</label>

<input
id="regPassword"
type="password"
placeholder="وشەی نهێنی">

</div>


<button
class="submit-btn"
style="margin-top:20px"
onclick="registerUser()">

📝 تۆمارکردن

</button>


<p
style="text-align:center;margin-top:15px">

ئەکاونتت هەیە؟

<button
style="border:0;background:none;color:#0066cc;cursor:pointer;font-weight:bold"
onclick="openLogin()">

Login

</button>

</p>

</div>

</div>


<!-- LOGIN -->

<div
class="modal"
id="loginModal">

<div class="modal-box">

<button
class="close"
onclick="closeAll()">
×
</button>

<h2 class="modal-title">
🔐 چوونەژوورەوە
</h2>


<div class="form-group">

<label>
ئیمەیڵ
</label>

<input
id="loginEmail"
type="email"
placeholder="example@gmail.com">

</div>


<div class="form-group">

<label>
وشەی نهێنی
</label>

<input
id="loginPassword"
type="password"
placeholder="وشەی نهێنی">

</div>


<button
class="submit-btn"
style="margin-top:20px"
onclick="loginUser()">

🔐 Login

</button>

</div>

</div>


<!-- PAYMENT -->

<div
class="modal"
id="paymentModal">

<div class="modal-box">

<button
class="close"
onclick="closePayment()">

×

</button>

<h2 class="modal-title">

💳 تەواوکردنی بەژداری

</h2>


<div class="selected-plan">

پلان:

<strong id="selectedPlan">
---
</strong>

<br>

بڕ:

<strong id="selectedPrice">
---
</strong>

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

<label>
ناوی تەواو
</label>

<input
id="userName"
type="text">

</div>


<div class="form-group">

<label>
ژمارەی مۆبایل
</label>

<input
id="userPhone"
type="tel">

</div>


<div class="form-group">

<label>
ژمارەی مامەڵە
</label>

<input
id="transactionId"
type="text"
placeholder="ئەگەر هەیە">

</div>


<div class="form-group">

<label>
وێنەی وەسڵ
</label>

<input
id="receiptImage"
type="file"
accept="image/*">

</div>


<div class="form-group">

<label>
تێبینی
</label>

<textarea
id="message"
placeholder="هەر تێبینییەکت هەیە">

</textarea>

</div>


<button
class="submit-btn"
style="margin-top:20px;background:#00a85a"
onclick="sendPayment()">

📤 ناردنی وەسڵ بۆ Admin

</button>

</div>


<div
class="success"
id="paymentSuccess">

✅ وەسڵەکەت بە سەرکەوتوویی نێردرا!

<br>

ئەدمین پشکنینی وەسڵەکەت دەکات.

</div>

</div>

</div>


<script>

/* =========================================
   SUPABASE CONFIG
========================================= */

const SUPABASE_URL =
"https://wpjqvpcqaufrpstnziad.supabase.co";

const SUPABASE_KEY =
"sb_publishable_9ALxJWahJqUFvtMXR7-5TA_XHBIF6ZK";


const supabaseClient =
window.supabase.createClient(
SUPABASE_URL,
SUPABASE_KEY
);


/* =========================================
   VARIABLES
========================================= */

let currentUser = null;

let currentProfile = null;

let selectedPlan = "";

let selectedPrice = 0;


/* =========================================
   HELPERS
========================================= */

function escapeHTML(value){

return String(value || "")
.replace(/&/g,"&amp;")
.replace(/</g,"&lt;")
.replace(/>/g,"&gt;")
.replace(/"/g,"&quot;")
.replace(/'/g,"&#039;");

}


/* =========================================
   MODALS
========================================= */

function openRegister(){

closeAll();

document.getElementById(
"registerModal"
).style.display="block";

}


function openLogin(){

closeAll();

document.getElementById(
"loginModal"
).style.display="block";

}


function closeAll(){

document.getElementById(
"registerModal"
).style.display="none";

document.getElementById(
"loginModal"
).style.display="none";

}


function closePayment(){

document.getElementById(
"paymentModal"
).style.display="none";

}


/* =========================================
   REGISTER
========================================= */

async function registerUser(){

const name =
document.getElementById(
"regName"
).value.trim();

const phone =
document.getElementById(
"regPhone"
).value.trim();

const email =
document.getElementById(
"regEmail"
).value.trim();

const password =
document.getElementById(
"regPassword"
).value;


if(!name || !phone || !email || !password){

alert(
"تکایە هەموو خانەکان پڕ بکەرەوە."
);

return;

}


if(password.length < 6){

alert(
"وشەی نهێنی دەبێت لانیکەم 6 پیت بێت."
);

return;

}


const { data,error } =
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
"❌ هەڵە: " +
error.message
);

return;

}


/*
Supabase email confirmation
ئەگەر چالاک بێت، پێویستە ئیمەیڵەکە پشتڕاست بکرێتەوە.
*/

if(data.user){

alert(
"✅ ئەکاونتەکەت دروست کرا. ئەگەر داوای پشتڕاستکردنەوەی ئیمەیڵ کرا، ئیمەیڵەکەت پشتڕاست بکەرەوە."
);

closeAll();

}

}


/* =========================================
   LOGIN
========================================= */

async function loginUser(){

const email =
document.getElementById(
"loginEmail"
).value.trim();

const password =
document.getElementById(
"loginPassword"
).value;


if(!email || !password){

alert(
"تکایە ئیمەیڵ و وشەی نهێنی بنووسە."
);

return;

}


const { data,error } =
await supabaseClient.auth.signInWithPassword({

email:email,

password:password

});


if(error){

alert(
"❌ ئیمەیڵ یان وشەی نهێنی هەڵەیە."
);

return;

}


currentUser = data.user;


await loadProfile();


closeAll();


if(
currentUser.email.toLowerCase()
===
"lawaking24@gmail.com".toLowerCase()
){

showAdmin();

}else{

showDashboard();

}

}


/* =========================================
   LOAD PROFILE
========================================= */

async function loadProfile(){

if(!currentUser){

return;

}


const { data,error } =
await supabaseClient
.from("profiles")
.select("*")
.eq("id",currentUser.id)
.single();


if(error){

console.log(error);

return;

}


currentProfile = data;

}


/* =========================================
   LOGOUT
========================================= */

async function logout(){

await supabaseClient.auth.signOut();

currentUser=null;

currentProfile=null;

document.getElementById(
"dashboard"
).style.display="none";

document.getElementById(
"adminPanel"
).style.display="none";

document.getElementById(
"home"
).style.display="block";

}


async function adminLogout(){

await logout();

}


/* =========================================
   DASHBOARD
========================================= */

async function showDashboard(){

document.getElementById(
"home"
).style.display="none";

document.getElementById(
"adminPanel"
).style.display="none";

document.getElementById(
"dashboard"
).style.display="block";


document.getElementById(
"dashboardName"
).innerHTML=

"ناو: <strong>" +
escapeHTML(
currentProfile?.full_name ||
currentUser?.user_metadata?.full_name ||
""
) +
"</strong><br>" +

"ئیمەیڵ: " +
escapeHTML(currentUser.email) +
"<br>" +

"ژمارە: " +
escapeHTML(currentProfile?.phone || "");


const status =
document.getElementById(
"premiumStatus"
);


if(
currentProfile &&
currentProfile.premium_active
){

status.className =
"status active";

status.innerHTML =
"👑 Premium چالاکە ✅";


document.getElementById(
"dashboardPlan"
).innerHTML=

"<p>پلان: <strong>" +
escapeHTML(
currentProfile.premium_plan
) +
"</strong></p>" +

"<p>کۆتایی Premium: <strong>" +
escapeHTML(
currentProfile.premium_expires_at
? new Date(
currentProfile.premium_expires_at
).toLocaleDateString("ku-IQ")
: ""
) +
"</strong></p>";

}else{

status.className =
"status pending";

status.innerHTML =
"Premium هێشتا چالاک نەکراوە.";

document.getElementById(
"dashboardPlan"
).innerHTML=

"<br>" +

"<button class='submit-btn'
onclick='goPlans()'>" +

"👑 کڕینی Premium" +

"</button>";

}


await loadMyPayments();

}


/* =========================================
   MY PAYMENTS
========================================= */

async function loadMyPayments(){

const box =
document.getElementById(
"myPayments"
);


const { data,error } =
await supabaseClient
.from("payment_requests")
.select("*")
.eq("user_id",currentUser.id)
.order("created_at",{ascending:false});


if(error){

console.log(error);

box.innerHTML="";

return;

}


if(!data || data.length===0){

box.innerHTML="";

return;

}


box.innerHTML =

"<h3 style='margin-top:20px'>💳 داواکارییەکانت</h3>" +

data.map(r => {

let text="";

let cls="pending";


if(r.status==="accepted"){

text="✅ وەرگیراوە";

cls="active";

}

else if(r.status==="rejected"){

text="❌ ڕەتکراوەتەوە";

cls="rejected";

}

else{

text="⏳ چاوەڕوانی پشکنین";

}


return `

<div class="user-request">

<strong>
${escapeHTML(r.plan)}
</strong>

<br>

💰 ${escapeHTML(r.amount)} د.ع

<br>

<div class="status ${cls}">

${text}

</div>

</div>

`;

}).join("");

}


/* =========================================
   CHOOSE PLAN
========================================= */

function choosePlan(plan,price){

if(!currentUser){

alert(
"تکایە سەرەتا Register یان Login بکە."
);

openLogin();

return;

}


selectedPlan=plan;

selectedPrice=price;


document.getElementById(
"selectedPlan"
).textContent=plan;


document.getElementById(
"selectedPrice"
).textContent=
price.toLocaleString("en-US");


document.getElementById(
"userName"
).value=
currentProfile?.full_name || "";


document.getElementById(
"userPhone"
).value=
currentProfile?.phone || "";


document.getElementById(
"paymentForm"
).style.display="block";


document.getElementById(
"paymentSuccess"
).style.display="none";


document.getElementById(
"receiptImage"
).value="";


document.getElementById(
"paymentModal"
).style.display="block";

}


/* =========================================
   SEND PAYMENT
========================================= */

async function sendPayment(){

if(!currentUser){

alert(
"تکایە Login بکە."
);

return;

}


const name =
document.getElementById(
"userName"
).value.trim();

const phone =
document.getElementById(
"userPhone"
).value.trim();

const transaction =
document.getElementById(
"transactionId"
).value.trim();

const message =
document.getElementById(
"message"
).value.trim();

const file =
document.getElementById(
"receiptImage"
).files[0];


if(!name || !phone){

alert(
"تکایە ناو و ژمارەی مۆبایل بنووسە."
);

return;

}


if(!file){

alert(
"تکایە وێنەی وەسڵەکە هەڵبژێرە."
);

return;

}


/* image size limit */

if(file.size > 8 * 1024 * 1024){

alert(
"❌ قەبارەی وێنەکە زۆرە. تکایە وێنەیەکی کەمتر لە 8MB هەڵبژێرە."
);

return;

}


/* filename */

const extension =
file.name.split(".").pop();

const fileName =
currentUser.id +
"/" +
Date.now() +
"." +
extension;


/* upload */

const { data:uploadData,error:uploadError } =

await supabaseClient
.storage
.from("receipts")
.upload(
fileName,
file,
{
contentType:file.type,
upsert:false
}
);


if(uploadError){

console.log(uploadError);

alert(
"❌ نەتوانرا وەسڵ Upload بکرێت:\n" +
uploadError.message
);

return;

}


/* public URL */

const { data:urlData } =
supabaseClient
.storage
.from("receipts")
.getPublicUrl(fileName);


const receiptURL =
urlData.publicUrl;


/* database request */

const { error:insertError } =

await supabaseClient
.from("payment_requests")
.insert({

user_id:currentUser.id,

plan:selectedPlan,

amount:selectedPrice,

receipt_url:receiptURL,

status:"pending"

});


if(insertError){

console.log(insertError);

alert(
"❌ وەسڵ Upload کرا بەڵام داواکارییەکە تۆمار نەکرا:\n" +
insertError.message
);

return;

}


/* success */

document.getElementById(
"paymentForm"
).style.display="none";


document.getElementById(
"paymentSuccess"
).style.display="block";


setTimeout(async function(){

closePayment();

document.getElementById(
"paymentForm"
).style.display="block";

document.getElementById(
"paymentSuccess"
).style.display="none";

await loadMyPayments();

},2000);

}


/* =========================================
   ADMIN
========================================= */

async function showAdmin(){

document.getElementById(
"home"
).style.display="none";

document.getElementById(
"dashboard"
).style.display="none";

document.getElementById(
"adminPanel"
).style.display="block";


await renderAdmin();

}


/* =========================================
   ADMIN DATA
========================================= */

async function renderAdmin(){

const container =
document.getElementById(
"requests"
);


container.innerHTML =
"<div class='empty'>⏳ داواکارییەکان بار دەکرێن...</div>";


/* users */

const { data:users,error:userError } =

await supabaseClient
.from("profiles")
.select("*");


if(userError){

console.log(userError);

container.innerHTML =
"<div class='empty'>❌ نەتوانرا Users بخوێندرێتەوە.</div>";

return;

}


/* requests */

const { data:requests,error:requestError } =

await supabaseClient
.from("payment_requests")
.select("*")
.order(
"created_at",
{ascending:false}
);


if(requestError){

console.log(requestError);

container.innerHTML =
"<div class='empty'>❌ نەتوانرا داواکارییەکان بخوێندرێنەوە.</div>";

return;

}


const pending =
requests.filter(
r => r.status==="pending"
);


const active =
users.filter(
u => u.premium_active
);


document.getElementById(
"userCount"
).textContent=
users.length;


document.getElementById(
"pendingCount"
).textContent=
pending.length;


document.getElementById(
"activeCount"
).textContent=
active.length;


if(!requests.length){

container.innerHTML =
"<div class='empty'>هیچ داواکارییەک نییە.</div>";

return;

}


/* render */

container.innerHTML =
requests.map(r => {

const user =
users.find(
u => u.id===r.user_id
);


let statusText="";

let statusClass="pending";


if(r.status==="accepted"){

statusText="✅ وەرگیراوە";

statusClass="active";

}
else if(r.status==="rejected"){

statusText="❌ ڕەتکراوەتەوە";

statusClass="rejected";

}
else{

statusText="⏳ چاوەڕوانی پشکنین";

}


return `

<div class="request">

<h3>
💳 داواکاری
</h3>

<p>

👤

<strong>
${escapeHTML(
user?.full_name || "بێ ناو"
)}
</strong>

<br>

📱
${escapeHTML(
user?.phone || "نییە"
)}

<br>

📧
${escapeHTML(
user?.id || ""
)}

<br>

👑 پلان:
${escapeHTML(r.plan)}

<br>

💰 بڕ:
<strong>
${escapeHTML(
Number(r.amount).toLocaleString("en-US")
)}
</strong>
د.ع

<br>

🕐
${escapeHTML(
new Date(r.created_at)
.toLocaleString("ku-IQ")
)}

</p>


<div class="status ${statusClass}">

${statusText}

</div>


<img
class="receipt-preview"
src="${escapeHTML(r.receipt_url)}"
alt="Receipt">


<a
href="${escapeHTML(r.receipt_url)}"
target="_blank"
style="
display:block;
text-align:center;
background:#0066cc;
color:white;
padding:12px;
border-radius:10px;
text-decoration:none;
margin-top:10px;
">

🔍 کردنەوەی وەسڵ

</a>


${
r.status==="pending"

?

`

<div class="request-buttons">

<button
class="accept"
onclick="acceptRequest('${r.id}','${r.user_id}','${escapeHTML(r.plan)}')">

✅ وەرگرتن

</button>


<button
class="reject"
onclick="rejectRequest('${r.id}')">

❌ ڕەتکردنەوە

</button>

</div>

`

:

""

}

</div>

`;

}).join("");

}


/* =========================================
   ACCEPT
========================================= */

async function acceptRequest(
requestId,
userId,
plan
){

const days =
plan==="هەفتانە"
? 7
: plan==="مانگانە"
? 30
: 365;


const end =
new Date();


end.setDate(
end.getDate()+days
);


/* update user */

const { error:userError } =

await supabaseClient
.from("profiles")
.update({

premium_active:true,

premium_plan:plan,

premium_expires_at:
end.toISOString()

})
.eq("id",userId);


if(userError){

alert(
"❌ نەتوانرا Premium چالاک بکرێت:\n" +
userError.message
);

console.log(userError);

return;

}


/* update payment */

const { error:paymentError } =

await supabaseClient
.from("payment_requests")
.update({

status:"accepted",

reviewed_at:
new Date().toISOString()

})
.eq("id",requestId);


if(paymentError){

alert(
"⚠️ Premium چالاک کرا، بەڵام دۆخی داواکاری نەگۆڕدرا."
);

console.log(paymentError);

return;

}


alert(
"✅ وەسڵەکە وەرگیرا و Premium چالاک کرا."
);


await renderAdmin();

}


/* =========================================
   REJECT
========================================= */

async function rejectRequest(id){

const ok =
confirm(
"دڵنیایت دەتەوێت ئەم وەسڵە ڕەت بکەیتەوە؟"
);


if(!ok){

return;

}


const { error } =

await supabaseClient
.from("payment_requests")
.update({

status:"rejected",

reviewed_at:
new Date().toISOString()

})
.eq("id",id);


if(error){

alert(
"❌ هەڵە ڕوویدا:\n" +
error.message
);

console.log(error);

return;

}


alert(
"❌ داواکارییەکە ڕەتکرایەوە."
);


await renderAdmin();

}


/* =========================================
   NAVIGATION
========================================= */

function scrollToPlans(){

document.getElementById(
"plans"
).scrollIntoView({

behavior:"smooth"

});

}


function goPlans(){

document.getElementById(
"dashboard"
).style.display="none";

document.getElementById(
"home"
).style.display="block";

setTimeout(
scrollToPlans,
100
);

}


/* =========================================
   MODAL CLICK
========================================= */

window.onclick =
function(event){

if(
event.target ===
document.getElementById(
"registerModal"
)
){

closeAll();

}


if(
event.target ===
document.getElementById(
"loginModal"
)
){

closeAll();

}


if(
event.target ===
document.getElementById(
"paymentModal"
)
){

closePayment();

}

};


/* =========================================
   START
========================================= */

async function startApp(){

const {
data
} =
await supabaseClient
.auth
.getSession();


if(!data.session){

return;

}


currentUser =
data.session.user;


await loadProfile();


if(
currentUser.email.toLowerCase()
===
"lawaking24@gmail.com".toLowerCase()
){

showAdmin();

}else{

showDashboard();

}

}


startApp();


/* =========================================
   AUTH STATE
========================================= */

supabaseClient
.auth
.onAuthStateChange(
async(event,session)=>{

if(
event==="SIGNED_OUT"
){

currentUser=null;

currentProfile=null;

document.getElementById(
"adminPanel"
).style.display="none";

document.getElementById(
"dashboard"
).style.display="none";

document.getElementById(
"home"
).style.display="block";

}

}
);

</script>

</body>

</html>
