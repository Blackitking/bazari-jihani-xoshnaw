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
padding:0
}

body{
font-family:Arial,Tahoma,sans-serif;
background:#f5f7fb;
color:#151515;
direction:rtl
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
z-index:50
}

.logo{
font-size:21px;
font-weight:bold
}

.header-actions{
display:flex;
gap:8px
}

button{
border:0;
cursor:pointer
}

.header-btn{
padding:10px 15px;
border-radius:10px;
background:#fff;
color:#111827;
font-weight:bold
}

.dark-btn{
background:#2563eb;
color:white
}

.logout-header{
background:#dc2626;
color:white
}

.hero{
padding:70px 20px;
text-align:center;
background:linear-gradient(135deg,#111827,#2563eb);
color:white
}

.hero .big-emoji{
font-size:65px;
margin-bottom:15px
}

.hero h1{
font-size:38px;
margin-bottom:15px
}

.hero p{
max-width:700px;
margin:auto;
line-height:1.9;
font-size:17px
}

.hero-btn{
margin-top:25px;
padding:14px 25px;
border-radius:12px;
background:#fff;
color:#111827;
font-size:16px;
font-weight:bold
}

.container{
width:min(1100px,92%);
margin:auto
}

section{
padding:55px 0
}

.section-title{
text-align:center;
font-size:28px;
margin-bottom:30px
}

.cards{
display:grid;
grid-template-columns:repeat(3,1fr);
gap:20px
}

.card{
background:white;
border-radius:18px;
padding:28px;
box-shadow:0 8px 30px rgba(0,0,0,.07);
text-align:center
}

.emoji{
font-size:45px;
margin-bottom:15px
}

.card h3{
margin-bottom:12px
}

.card p{
color:#666;
line-height:1.8
}

.plans{
display:grid;
grid-template-columns:repeat(3,1fr);
gap:20px
}

.plan{
position:relative;
background:white;
border-radius:20px;
padding:30px 25px;
box-shadow:0 8px 30px rgba(0,0,0,.08);
text-align:center
}

.plan.featured{
border:3px solid #2563eb
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
white-space:nowrap
}

.price{
font-size:34px;
font-weight:bold;
margin:18px 0;
color:#2563eb
}

.price small{
font-size:14px
}

.plan ul{
list-style:none;
text-align:right;
line-height:2.2;
margin:15px 0 25px
}

.plan button,
.submit-btn{
width:100%;
padding:13px;
border-radius:11px;
background:#2563eb;
color:white;
font-weight:bold;
font-size:15px
}

.dashboard{
display:none;
margin:30px auto;
width:min(1100px,92%);
background:white;
padding:30px;
border-radius:20px;
box-shadow:0 8px 30px rgba(0,0,0,.08)
}

.status{
padding:15px;
border-radius:12px;
margin:15px 0;
font-weight:bold
}

.status.pending{
background:#fff3cd;
color:#856404
}

.status.active{
background:#d1fae5;
color:#065f46
}

.admin-box{
display:none;
background:#ede9fe;
color:#5b21b6;
padding:14px;
border-radius:12px;
margin:15px 0;
font-weight:bold;
text-align:center
}

.logout{
margin-top:20px;
padding:12px 20px;
border-radius:10px;
background:#dc2626;
color:white;
font-weight:bold
}

.payment-list{
margin-top:20px
}

.payment-item{
background:#f8fafc;
padding:18px;
border-radius:14px;
margin-bottom:12px;
line-height:1.9
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
overflow:auto
}

.modal-box{
width:min(520px,100%);
max-height:92vh;
overflow:auto;
background:white;
border-radius:20px;
padding:25px;
position:relative
}

.close{
position:absolute;
top:10px;
left:12px;
width:35px;
height:35px;
border-radius:50%;
background:#f1f5f9;
font-size:25px
}

.modal-title{
text-align:center;
margin-bottom:25px
}

.form-group{
margin-bottom:16px
}

.form-group label{
display:block;
margin-bottom:7px;
font-weight:bold
}

input,
textarea{
width:100%;
padding:12px;
border:1px solid #d1d5db;
border-radius:10px;
font-family:inherit;
font-size:15px
}

textarea{
min-height:90px;
resize:vertical
}

.selected-plan{
background:#eff6ff;
padding:15px;
border-radius:12px;
text-align:center;
line-height:2;
margin-bottom:20px
}

.fib-box{
background:#eff6ff;
border:1px solid #bfdbfe;
padding:20px;
border-radius:15px;
margin-bottom:20px
}

.fib-number{
background:white;
padding:15px;
text-align:center;
font-size:24px;
font-weight:bold;
letter-spacing:2px;
border-radius:10px;
margin:15px 0
}

.notice{
background:#dcfce7;
color:#166534;
padding:10px;
border-radius:8px;
text-align:center
}

.warning{
margin-top:12px;
background:#fee2e2;
color:#991b1b;
padding:12px;
border-radius:10px;
line-height:1.8;
text-align:center
}

.success{
display:none;
background:#dcfce7;
color:#166534;
padding:18px;
border-radius:12px;
text-align:center;
line-height:1.8
}

footer{
background:#111827;
color:white;
text-align:center;
padding:30px 15px;
margin-top:30px
}

@media(max-width:800px){

.cards,
.plans{
grid-template-columns:1fr
}

header{
flex-direction:column
}

.hero h1{
font-size:30px
}

}

</style>

</head>

<body>


<header>

<div class="logo">
XOSHNAW AI PREMIUM
</div>


<!-- ئەمانە بۆ کەسی نەچووەتە ژوورەوە -->

<div
class="header-actions"
id="authButtons">

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


<!-- تەنها دوای Login دەردەکەوێت -->

<div
class="header-actions"
id="logoutArea"
style="display:none">

<button
class="header-btn logout-header"
onclick="logout()">

🚪 چوونەدەرەوە

</button>

</div>

</header>


<section class="hero">

<div class="big-emoji">
🤖
</div>

<h1>
بەخێربێیت بۆ XOSHNAW AI
</h1>

<p>
شوێنێکی تایبەت بۆ فێربوونی AI Tools،
ڤیدیۆی فێرکاری، ئامرازە زیرەکەکان
و ناوەڕۆکی Premium.
</p>

<button
class="hero-btn"
onclick="scrollToPlans()">

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

<h3>
AI Tools
</h3>

<p>
فێربوونی ئامرازەکانی AI
و چۆنیەتی بەکارهێنانیان.
</p>

</div>


<div class="card">

<div class="emoji">🎬</div>

<h3>
ڤیدیۆی فێرکاری
</h3>

<p>
ڤیدیۆی نوێی فێرکاری
بە شێوەی ڕوون و ئاسان.
</p>

</div>


<div class="card">

<div class="emoji">👑</div>

<h3>
Premium
</h3>

<p>
دەستگەیشتن بە ناوەڕۆکی تایبەت
بۆ ئەندامانی Premium.
</p>

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

<h3>
هەفتانە
</h3>

<div class="price">
1,500 <small>د.ع</small>
</div>

<ul>
<li>✓ دەستگەیشتن بە Premium</li>
<li>✓ ڤیدیۆی فێرکاری</li>
<li>✓ AI Tools</li>
</ul>

<button
onclick="choosePlan('هەفتانە',1500)">

هەڵبژاردن

</button>

</div>


<div class="plan featured">

<div class="badge">
باشترین هەڵبژاردە
</div>

<h3>
مانگانە
</h3>

<div class="price">
4,000 <small>د.ع</small>
</div>

<ul>
<li>✓ دەستگەیشتن بە Premium</li>
<li>✓ هەموو ڤیدیۆکان</li>
<li>✓ AI Tools</li>
<li>✓ ناوەڕۆکی نوێ</li>
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
15,000 <small>د.ع</small>
</div>

<ul>
<li>✓ Premium بۆ ساڵێک</li>
<li>✓ هەموو ڤیدیۆکان</li>
<li>✓ AI Tools</li>
<li>✓ هەموو ناوەڕۆکی داهاتوو</li>
</ul>

<button
onclick="choosePlan('ساڵانە',15000)">

هەڵبژاردن

</button>

</div>


</div>

</div>

</section>


<div
id="dashboard"
class="dashboard">

<h2>
👤 بەخێربێیت
</h2>

<p id="dashboardName"></p>


<div
id="adminBox"
class="admin-box">

👑 تۆ بەڕێوەبەری XOSHNAW AI PREMIUM ـیت

</div>


<div
id="premiumStatus"
class="status pending">

Premium هێشتا چالاک نەکراوە.

</div>


<div id="dashboardPlan"></div>


<div
id="myPayments"
class="payment-list">
</div>


<button
class="logout"
onclick="logout()">

🚪 چوونەدەرەوە

</button>

</div>


<!-- REGISTER -->

<div
id="registerModal"
class="modal">

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
type="text">

</div>


<div class="form-group">

<label>
ژمارەی مۆبایل
</label>

<input
id="regPhone"
type="tel">

</div>


<div class="form-group">

<label>
ئیمەیڵ
</label>

<input
id="regEmail"
type="email">

</div>


<div class="form-group">

<label>
وشەی نهێنی
</label>

<input
id="regPassword"
type="password">

</div>


<button
class="submit-btn"
onclick="registerUser()">

📝 تۆمارکردن

</button>

</div>

</div>


<!-- LOGIN -->

<div
id="loginModal"
class="modal">

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
type="email">

</div>


<div class="form-group">

<label>
وشەی نهێنی
</label>

<input
id="loginPassword"
type="password">

</div>


<button
class="submit-btn"
onclick="loginUser()">

🔐 Login

</button>

</div>

</div>


<!-- PAYMENT -->

<div
id="paymentModal"
class="modal">

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

لە کاتی بە هەڵە ڕۆشتنی پارە
بۆ هەر هەژمارێک،
بەرپرسیار نین!

</div>

</div>


<div id="paymentForm">


<div class="form-group">

<label>
ناوی تەواو
</label>

<input id="userName">

</div>


<div class="form-group">

<label>
ژمارەی مۆبایل
</label>

<input id="userPhone">

</div>


<div class="form-group">

<label>
ژمارەی مامەڵە
</label>

<input id="transactionId">

</div>


<div class="form-group">

<label>
وێنەی رسید / مامەڵە
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

<textarea id="message"></textarea>

</div>


<button
class="submit-btn"
style="background:#00a85a"
onclick="sendPayment()">

📤 ناردنی وەسڵ بۆ ئەدمین

</button>

</div>


<div
class="success"
id="paymentSuccess">

✅ داواکارییەکەت تۆمارکرا!

<br>

وەسڵەکەت نێردراوە بۆ پشکنین.

</div>

</div>

</div>


<footer>

<strong>
XOSHNAW AI PREMIUM
</strong>

<br><br>

فێربوون • AI • Technology • Premium

</footer>


<script>


/* =========================
   SUPABASE
========================= */

const SUPABASE_URL =
"https://wpjqvpcqaufrpstnziad.supabase.co";

const SUPABASE_KEY =
"sb_publishable_9ALxJWahJqUFvtMXR7-5TA_XHBIF6ZK";


/* ئەمە Admin ـە */

const ADMIN_EMAIL =
"lawaking24@gmail.com";


const supabaseClient =
window.supabase.createClient(
SUPABASE_URL,
SUPABASE_KEY
);


let currentUser = null;

let currentProfile = null;

let selectedPlan = "";

let selectedPrice = 0;


/* =========================
   ESCAPE HTML
========================= */

function escapeHTML(value){

if(value === null || value === undefined)
return "";

return String(value)
.replace(/&/g,"&amp;")
.replace(/</g,"&lt;")
.replace(/>/g,"&gt;")
.replace(/"/g,"&quot;")
.replace(/'/g,"&#039;");

}


/* =========================
   ADMIN CHECK
========================= */

function isAdmin(){

if(!currentUser)
return false;


/*
ئیمەیڵەکە بە تەنها
Admin ـە.
*/

if(
currentUser.email &&
currentUser.email.toLowerCase()
===
ADMIN_EMAIL.toLowerCase()
){

return true;

}


/*
ئەگەر لە profiles ـیش
is_admin=true بێت.
*/

if(
currentProfile &&
currentProfile.is_admin === true
){

return true;

}


return false;

}


/* =========================
   HEADER
========================= */

function updateAuthButtons(){

const authButtons =
document.getElementById("authButtons");

const logoutArea =
document.getElementById("logoutArea");


if(currentUser){

authButtons.style.display="none";

logoutArea.style.display="flex";

}else{

authButtons.style.display="flex";

logoutArea.style.display="none";

}

}


/* =========================
   OPEN LOGIN
========================= */

function openLogin(){

closeAll();

document.getElementById("loginModal")
.style.display="flex";

}


/* =========================
   OPEN REGISTER
========================= */

function openRegister(){

closeAll();

document.getElementById("registerModal")
.style.display="flex";

}


/* =========================
   CLOSE PAYMENT
========================= */

function closePayment(){

document.getElementById("paymentModal")
.style.display="none";

}


/* =========================
   CLOSE ALL
========================= */

function closeAll(){

document.getElementById("loginModal")
.style.display="none";

document.getElementById("registerModal")
.style.display="none";

document.getElementById("paymentModal")
.style.display="none";

}


/* =========================
   REGISTER
========================= */

async function registerUser(){

const name =
document.getElementById("regName")
.value.trim();

const phone =
document.getElementById("regPhone")
.value.trim();

const email =
document.getElementById("regEmail")
.value.trim();

const password =
document.getElementById("regPassword")
.value;


if(
!name ||
!phone ||
!email ||
!password
){

alert(
"❌ تکایە هەموو خانەکان پڕ بکەرەوە."
);

return;

}


if(password.length < 6){

alert(
"❌ وشەی نهێنی دەبێت لانیکەم 6 پیت بێت."
);

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
"❌ تۆمارکردن سەرکەوتوو نەبوو:\n\n"
+
error.message
);

return;

}


/*
دروستکردنی Profile
*/

if(data.user){

const {error:profileError} =
await supabaseClient
.from("profiles")
.upsert({

id:data.user.id,

full_name:name,

phone:phone,

is_admin:false,

premium_active:false

});


if(profileError){

console.error(
"profileError:",
profileError
);

}

}


alert(
"✅ ئەکاونتەکەت دروست کرا.\n\nئێستا Login بکە."
);


/*
تەنها ئەگەر session هەبێت
header دەگۆڕێت.
*/

if(data.session){

currentUser=data.user;

await loadProfile();

updateAuthButtons();

await showDashboard();

}


closeAll();


}catch(error){

console.error(error);

alert(
"❌ هەڵەیەک ڕوویدا:\n\n"
+
(error.message || error)
);

}

}


/* =========================
   LOGIN
========================= */

async function loginUser(){

const email =
document.getElementById("loginEmail")
.value.trim();

const password =
document.getElementById("loginPassword")
.value;


if(!email || !password){

alert(
"❌ تکایە ئیمەیڵ و وشەی نهێنی بنووسە."
);

return;

}


try{


const {data,error} =
await supabaseClient.auth
.signInWithPassword({

email:email,

password:password

});


if(error){

alert(
"❌ Login سەرکەوتوو نەبوو:\n\n"
+
error.message
);

return;

}


currentUser=data.user;


await loadProfile();


/*
دوای Login:
Login و Register دەشاردرێن.
تەنها Logout دەردەکەوێت.
*/

updateAuthButtons();


closeAll();


await showDashboard();


}catch(error){

console.error(error);

alert(
"❌ هەڵەیەک ڕوویدا:\n\n"
+
(error.message || error)
);

}

}


/* =========================
   LOAD PROFILE
========================= */

async function loadProfile(){

if(!currentUser)
return null;


const {data,error} =
await supabaseClient
.from("profiles")
.select("*")
.eq("id",currentUser.id)
.maybeSingle();


if(error){

console.error(
"PROFILE ERROR:",
error
);

currentProfile=null;

return null;

}


currentProfile=data;

return data;

}


/* =========================
   DASHBOARD
========================= */

async function showDashboard(){

if(!currentUser)
return;


await loadProfile();


document.getElementById("dashboard")
.style.display="block";


const name =
currentProfile?.full_name ||
currentUser.user_metadata?.full_name ||
currentUser.email;


document.getElementById("dashboardName")
.textContent =
"سڵاو " + name;


/*
Admin Box
*/

const adminBox =
document.getElementById("adminBox");


if(isAdmin()){

adminBox.style.display="block";

}else{

adminBox.style.display="none";

}


/*
Premium Status
*/

const status =
document.getElementById("premiumStatus");

const plan =
document.getElementById("dashboardPlan");


if(
currentProfile?.premium_active === true
){

status.className="status active";

status.innerHTML =
"👑 Premium ـەکەت چالاکە.";


let expiryText="";


if(currentProfile.premium_expires_at){

const expiry =
new Date(
currentProfile.premium_expires_at
);

expiryText =
"<br><strong>کۆتایی:</strong> "
+
expiry.toLocaleDateString("ku-IQ");

}


plan.innerHTML =

"<p>" +

"<strong>پلان:</strong> "

+

escapeHTML(
currentProfile.premium_plan || ""
)

+

expiryText

+

"</p>";

}else{

status.className="status pending";

status.innerHTML =
"Premium هێشتا چالاک نەکراوە.";

plan.innerHTML="";

}


/*
Payment history
*/

await loadMyPayments();

}


/* =========================
   USER PAYMENTS
========================= */

async function loadMyPayments(){

const box =
document.getElementById("myPayments");


if(!currentUser)
return;


const {data,error} =
await supabaseClient
.from("payment_requests")
.select("*")
.eq("user_id",currentUser.id)
.order(
"created_at",
{ascending:false}
);


if(error){

console.error(
"PAYMENTS ERROR:",
error
);

box.innerHTML="";

return;

}


if(!data || data.length === 0){

box.innerHTML =
"<p style='color:#777'>هیچ داواکارییەکت نییە.</p>";

return;

}


let html =
"<h3 style='margin-bottom:12px'>📋 داواکارییەکانت</h3>";


data.forEach(item=>{

let status="⏳ چاوەڕوان";


if(item.status === "accepted")
status="✅ پەسەندکراو";


if(item.status === "rejected")
status="❌ ڕەتکرایەوە";


html +=

"<div class='payment-item'>"

+

"<strong>پلان:</strong> "

+

escapeHTML(
item.plan || ""
)

+

"<br>"

+

"<strong>بڕ:</strong> "

+

escapeHTML(
item.amount || ""
)

+

" د.ع"

+

"<br>"

+

"<strong>دۆخ:</strong> "

+

status

+

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
"❌ تکایە سەرەتا Login بکە."
);

openLogin();

return;

}


selectedPlan=plan;

selectedPrice=Number(price);


/*
ADMIN
ڕاستەوخۆ Premium
*/

if(isAdmin()){

activateAdminPremium(
plan,
price
);

return;

}


/*
NORMAL USER
دەچێتە FIB
*/

document.getElementById("selectedPlan")
.textContent=plan;


document.getElementById("selectedPrice")
.textContent =
selectedPrice.toLocaleString("en-US");


document.getElementById("userName")
.value =
currentProfile?.full_name ||
currentUser.user_metadata?.full_name ||
"";


document.getElementById("userPhone")
.value =
currentProfile?.phone ||
currentUser.user_metadata?.phone ||
"";


document.getElementById("transactionId")
.value="";


document.getElementById("receiptImage")
.value="";


document.getElementById("message")
.value="";


document.getElementById("paymentForm")
.style.display="block";


document.getElementById("paymentSuccess")
.style.display="none";


document.getElementById("paymentModal")
.style.display="flex";

}


/* =========================
   ADMIN PREMIUM
========================= */

async function activateAdminPremium(
plan,
price
){

if(!currentUser || !isAdmin())
return;


/*
ماوەی پلان
*/

let days=7;


if(plan === "مانگانە"){
days=30;
}


if(plan === "ساڵانە"){
days=365;
}


const expires =
new Date();


expires.setDate(
expires.getDate()+days
);


/*
Update profile
*/

const {error} =
await supabaseClient
.from("profiles")
.update({

is_admin:true,

premium_active:true,

premium_plan:plan,

premium_expires_at:
expires.toISOString()

})
.eq(
"id",
currentUser.id
);


if(error){

console.error(
"ADMIN PREMIUM ERROR:",
error
);

alert(
"❌ Premium ـی Admin چالاک نەکرا:\n\n"
+
error.message
);

return;

}


await loadProfile();

await showDashboard();


alert(

"👑 Premium چالاک کرا!"

+

"\n\nپلان: "
+
plan

+

"\nبڕ: "
+
Number(price)
.toLocaleString("en-US")
+
" د.ع"

+

"\n\nبۆ Admin پارەدان پێویست نییە."

);

}


/* =========================
   SEND PAYMENT
   NORMAL USERS ONLY
========================= */

async function sendPayment(){

if(!currentUser){

alert(
"❌ تکایە Login بکە."
);

return;

}


/*
Admin نابێت ئەم function ـە بەکاربهێنێت.
*/

if(isAdmin()){

alert(
"👑 تۆ Admin ـیت.\nPremium ـەکەت بەبێ پارەدان چالاک دەکرێت."
);

return;

}


const name =
document.getElementById("userName")
.value.trim();


const phone =
document.getElementById("userPhone")
.value.trim();


const file =
document.getElementById("receiptImage")
.files[0];


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


/*
Maximum 5MB
*/

if(
file.size >
5 * 1024 * 1024
){

alert(
"❌ قەبارەی وێنەکە زۆرە.\nتکایە وێنەیەکی کەمتر لە 5MB هەڵبژێرە."
);

return;

}


try{


/*
UPLOAD RECEIPT
*/

const extension =
file.name
.split(".")
.pop()
.toLowerCase();


const fileName =

currentUser.id
+
"_"
+
Date.now()
+
"."
+
extension;


const {error:uploadError} =
await supabaseClient
.storage
.from("receipts")
.upload(

fileName,

file,

{
cacheControl:"3600",
upsert:false,
contentType:file.type
}

);


if(uploadError){

console.error(
"UPLOAD ERROR:",
uploadError
);

alert(
"❌ ناردنی وێنەی وەسڵ سەرکەوتوو نەبوو:\n\n"
+
uploadError.message
);

return;

}


/*
PUBLIC URL
*/

const {data:urlData} =
supabaseClient
.storage
.from("receipts")
.getPublicUrl(
fileName
);


const receiptUrl =
urlData?.publicUrl || "";


if(!receiptUrl){

alert(
"❌ لینکی وەسڵ دروست نەکرا."
);

return;

}


/*
PAYMENT DATA

تەنها column ـە دڵنیابووەکان.
message و transaction_id نەنێردراون.
*/

const paymentData={

user_id:currentUser.id,

plan:selectedPlan,

amount:selectedPrice,

receipt_url:receiptUrl,

status:"pending"

};


/*
INSERT
*/

const {error} =
await supabaseClient
.from("payment_requests")
.insert(
paymentData
);


if(error){

console.error(
"PAYMENT INSERT ERROR:",
error
);

alert(
"❌ داواکارییەکە نەنێردرا:\n\n"
+
(error.message || "Unknown error")
);

return;

}


/*
SUCCESS
*/

document.getElementById("paymentForm")
.style.display="none";


document.getElementById("paymentSuccess")
.style.display="block";


await loadMyPayments();


}catch(error){

console.error(
"SEND PAYMENT ERROR:",
error
);

alert(
"❌ هەڵەیەک ڕوویدا:\n\n"
+
(error.message || error)
);

}

}


/* =========================
   LOGOUT
========================= */

async function logout(){

/*
پرسیاری دڵنیایی
*/

const answer =
confirm(
"🚪 ئایا دڵنیایت لە چوونەدەرەوە؟"
);


/*
نەخێر
*/

if(!answer){

return;

}


/*
بەڵێ
*/

const {error} =
await supabaseClient
.auth
.signOut();


if(error){

alert(
"❌ چوونەدەرەوە سەرکەوتوو نەبوو:\n\n"
+
error.message
);

return;

}


currentUser=null;

currentProfile=null;


document.getElementById("dashboard")
.style.display="none";


updateAuthButtons();


alert(
"✅ بە سەرکەوتوویی چوویتە دەرەوە."
);

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


/* =========================
   CLOSE MODALS
========================= */

document.addEventListener(
"click",
function(e){

if(
e.target.classList.contains("modal")
){

e.target.style.display="none";

}

}
);


/* =========================
   AUTH STATE
========================= */

supabaseClient.auth.onAuthStateChange(

(event,session)=>{


if(session?.user){

currentUser=session.user;


/*
header update
*/

updateAuthButtons();


setTimeout(
async()=>{

await loadProfile();

updateAuthButtons();

await showDashboard();

},
100
);


}else{


currentUser=null;

currentProfile=null;


/*
Login/Register دووبارە دەردەکەون
*/

updateAuthButtons();


document.getElementById("dashboard")
.style.display="none";

}

}
);


/* =========================
   START APP
========================= */

async function startApp(){

const {data} =
await supabaseClient
.auth
.getSession();


if(data?.session?.user){

currentUser=
data.session.user;


await loadProfile();


updateAuthButtons();


await showDashboard();

}else{

currentUser=null;

currentProfile=null;

updateAuthButtons();

}

}


/* START */

startApp();

</script>

</body>
</html>
