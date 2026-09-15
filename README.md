
<!DOCTYPE html>
<html lang="ku" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>XOSHNAW AI PREMIUM</title>

<style>
*{
  box-sizing:border-box;
  margin:0;
  padding:0;
  font-family:Arial,Tahoma,sans-serif;
}

body{
  min-height:100vh;
  background:linear-gradient(135deg,#07111f,#102d52,#0066cc);
  color:#fff;
}

header{
  padding:22px 5%;
  display:flex;
  justify-content:space-between;
  align-items:center;
  border-bottom:1px solid rgba(255,255,255,.15);
  backdrop-filter:blur(10px);
}

.logo{
  font-size:25px;
  font-weight:900;
  color:#fff;
}

.logo span{
  color:#00d9ff;
}

.header-btn{
  border:0;
  padding:11px 18px;
  border-radius:12px;
  background:#00d9ff;
  color:#00131d;
  font-weight:bold;
  cursor:pointer;
}

.container{
  width:92%;
  max-width:1100px;
  margin:35px auto;
}

.hero{
  text-align:center;
  padding:55px 20px;
}

.hero .icon{
  font-size:65px;
  margin-bottom:15px;
}

.hero h1{
  font-size:42px;
  margin-bottom:15px;
}

.hero h1 span{
  color:#00d9ff;
}

.hero p{
  max-width:700px;
  margin:auto;
  color:#d9e8f5;
  line-height:1.9;
  font-size:17px;
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
  box-shadow:0 8px 25px rgba(0,217,255,.25);
}

.section-title{
  text-align:center;
  margin:30px 0 20px;
  font-size:28px;
}

.features{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:18px;
}

.feature{
  background:rgba(255,255,255,.09);
  border:1px solid rgba(255,255,255,.12);
  border-radius:20px;
  padding:25px;
  text-align:center;
}

.feature .emoji{
  font-size:42px;
  margin-bottom:12px;
}

.feature h3{
  margin-bottom:8px;
}

.feature p{
  color:#d4e2ef;
  line-height:1.7;
}

.pricing{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:20px;
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
  transform:translateY(-8px);
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

.plan h3{
  font-size:24px;
  margin-bottom:12px;
}

.price{
  font-size:34px;
  font-weight:900;
  color:#0066cc;
}

.price small{
  font-size:15px;
  color:#555;
}

.plan ul{
  list-style:none;
  margin:20px 0;
  line-height:2;
}

.plan li::before{
  content:"✓ ";
  color:#00a85a;
  font-weight:bold;
}

.plan button{
  width:100%;
  padding:13px;
  border:0;
  border-radius:13px;
  background:#0066cc;
  color:#fff;
  font-weight:bold;
  cursor:pointer;
}

.modal{
  display:none;
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.75);
  z-index:100;
  padding:20px;
  overflow:auto;
}

.modal-box{
  max-width:550px;
  margin:40px auto;
  background:#fff;
  color:#172334;
  border-radius:24px;
  padding:28px;
}

.modal-box h2{
  text-align:center;
  margin-bottom:20px;
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

.selected-plan{
  background:#eef8ff;
  border:1px solid #bdeaff;
  padding:15px;
  border-radius:15px;
  text-align:center;
  margin-bottom:20px;
}

.payment-methods{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:15px;
}

.payment-method{
  border:2px solid #ddd;
  padding:18px;
  border-radius:16px;
  text-align:center;
  cursor:pointer;
  background:#fff;
  font-weight:bold;
}

.payment-method:hover{
  border-color:#00aeea;
}

.payment-method.active{
  border-color:#0066cc;
  background:#eef8ff;
}

.payment-box{
  display:none;
  text-align:center;
  margin-top:20px;
}

.qr{
  width:220px;
  height:220px;
  object-fit:contain;
  border:8px solid #fff;
  box-shadow:0 5px 20px rgba(0,0,0,.15);
  margin:15px auto;
  display:block;
}

.account{
  background:#f1f4f7;
  padding:12px;
  border-radius:10px;
  margin:10px 0;
  direction:ltr;
  font-weight:bold;
}

.form-group{
  margin-top:15px;
  text-align:right;
}

.form-group label{
  display:block;
  margin-bottom:7px;
  font-weight:bold;
}

.form-group input,
.form-group select,
.form-group textarea{
  width:100%;
  padding:13px;
  border:1px solid #ccd5df;
  border-radius:11px;
  outline:none;
}

.form-group textarea{
  min-height:90px;
  resize:vertical;
}

.submit{
  width:100%;
  margin-top:20px;
  padding:14px;
  border:0;
  border-radius:13px;
  background:#00a85a;
  color:white;
  font-weight:bold;
  cursor:pointer;
}

.notice{
  background:#fff7df;
  border:1px solid #ffe29a;
  color:#604900;
  padding:13px;
  border-radius:12px;
  line-height:1.7;
  margin-top:15px;
}

.videos{
  margin-top:40px;
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:18px;
}

.video-card{
  background:rgba(255,255,255,.09);
  border-radius:18px;
  overflow:hidden;
  border:1px solid rgba(255,255,255,.12);
}

.video-card .video-placeholder{
  height:170px;
  display:flex;
  align-items:center;
  justify-content:center;
  background:rgba(0,0,0,.2);
  font-size:50px;
}

.video-card div:last-child{
  padding:18px;
}

footer{
  margin-top:50px;
  padding:30px;
  text-align:center;
  background:rgba(0,0,0,.2);
  color:#cbd9e5;
  line-height:2;
}

.success{
  display:none;
  text-align:center;
  padding:20px;
  background:#eafff3;
  color:#075d31;
  border-radius:15px;
  margin-top:20px;
}

@media(max-width:800px){
  .features,
  .pricing,
  .videos{
    grid-template-columns:1fr;
  }

  .plan.popular{
    transform:none;
  }

  .hero h1{
    font-size:31px;
  }

  .payment-methods{
    grid-template-columns:1fr;
  }
}
</style>
</head>

<body>

<header>
  <div class="logo">XOSHNAW <span>AI</span> PREMIUM</div>
  <button class="header-btn" onclick="openPricing()">بەژداربوون</button>
</header>

<main class="container">

<section class="hero">
  <div class="icon">🤖</div>

  <h1>
    بەخێربێیت بۆ
    <span>XOSHNAW AI</span>
  </h1>

  <p>
    شوێنێکی تایبەت بۆ فێربوونی AI Tools،
    ڤیدیۆی فێرکاری، ئامرازە زیرەکەکان و ناوەڕۆکی Premium.
  </p>

  <button class="main-btn" onclick="openPricing()">
    👑 بەژداربوونی Premium
  </button>
</section>


<h2 class="section-title">🚀 چی بەدەست دەهێنیت؟</h2>

<section class="features">

  <div class="feature">
    <div class="emoji">🤖</div>
    <h3>AI Tools</h3>
    <p>
      فێربوونی ئامرازەکانی AI و چۆنیەتی بەکارهێنانیان.
    </p>
  </div>

  <div class="feature">
    <div class="emoji">🎬</div>
    <h3>ڤیدیۆی فێرکاری</h3>
    <p>
      ڤیدیۆی نوێی فێرکاری بە شێوەی ڕوون و ئاسان.
    </p>
  </div>

  <div class="feature">
    <div class="emoji">👑</div>
    <h3>Premium</h3>
    <p>
      دەستگەیشتن بە ناوەڕۆکی تایبەت تەنها بۆ ئەندامانی Premium.
    </p>
  </div>

</section>


<h2 class="section-title">🎬 ڤیدیۆکانی فێرکاری</h2>

<section class="videos">

  <div class="video-card">
    <div class="video-placeholder">▶️</div>
    <div>
      <h3>AI Tool ـی یەکەم</h3>
      <p>ڤیدیۆی فێرکاری بۆ ئەندامانی Premium.</p>
    </div>
  </div>

  <div class="video-card">
    <div class="video-placeholder">▶️</div>
    <div>
      <h3>چۆن AI بەکاربهێنین؟</h3>
      <p>فێربوونی بنەڕەتی AI بە زمانی کوردی.</p>
    </div>
  </div>

  <div class="video-card">
    <div class="video-placeholder">🔒</div>
    <div>
      <h3>Premium Video</h3>
      <p>ئەم ڤیدیۆیە تەنها بۆ ئەندامانی Premium ـە.</p>
    </div>
  </div>

</section>


<h2 class="section-title">👑 پلانەکانی Premium</h2>

<section class="pricing">

  <div class="plan">
    <h3>هەفتانە</h3>

    <div class="price">
      1,500
      <small>د.ع</small>
    </div>

    <ul>
      <li>دەستگەیشتن بە Premium</li>
      <li>ڤیدیۆی فێرکاری</li>
      <li>AI Tools</li>
    </ul>

    <button onclick="choosePlan('هەفتانە','1,500')">
      هەڵبژاردن
    </button>
  </div>


  <div class="plan popular">

    <div class="badge">باشترین هەڵبژاردە</div>

    <h3>مانگانە</h3>

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

    <button onclick="choosePlan('مانگانە','4,000')">
      هەڵبژاردن
    </button>
  </div>


  <div class="plan">

    <h3>ساڵانە</h3>

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

    <button onclick="choosePlan('ساڵانە','15,000')">
      هەڵبژاردن
    </button>
  </div>

</section>

</main>


<footer>
  <strong>XOSHNAW AI PREMIUM</strong><br>
  فێربوون • AI • Technology • Premium
</footer>



<!-- PAYMENT MODAL -->

<div class="modal" id="paymentModal">

  <div class="modal-box">

    <button class="close" onclick="closeModal()">×</button>

    <h2>💳 تەواوکردنی بەژداری</h2>

    <div class="selected-plan">
      پلان:
      <strong id="selectedPlan">---</strong>
      <br>
      بڕ:
      <strong id="selectedPrice">---</strong> د.ع
    </div>

    <h3 style="text-align:center;margin-bottom:15px;">
      چۆن دەتەوێت پارە بدەیت؟
    </h3>

    <div class="payment-methods">

      <div
        class="payment-method"
        id="fastpayMethod"
        onclick="selectPayment('fastpay')">
        🟢 FastPay
      </div>

      <div
        class="payment-method"
        id="fibMethod"
        onclick="selectPayment('fib')">
        🔵 FIB
      </div>

    </div>


    <!-- FASTPAY -->

    <div class="payment-box" id="fastpayBox">

      <h3>🟢 پارەدان بە FastPay</h3>

      <!-- QR ـی خۆت لێرە دابنێ -->
      <img
        class="qr"
        src="fastpay-qr.png"
        alt="FastPay QR">

      <div class="account">
        FastPay Account: 07XXXXXXXXX
      </div>

      <div class="notice">
        تکایە QR ـەکە scan بکە و بڕی پارەکە بنێرە.
        دوای ناردنی پارە، وێنەی رسیدەکە لە خوارەوە بنێرە.
      </div>

    </div>


    <!-- FIB -->

    <div class="payment-box" id="fibBox">

      <h3>🔵 پارەدان بە FIB</h3>

      <!-- QR ـی خۆت لێرە دابنێ -->
      <img
        class="qr"
        src="fib-qr.png"
        alt="FIB QR">

      <div class="account">
        FIB Account: 07XXXXXXXXX
      </div>

      <div class="notice">
        تکایە QR ـەکە scan بکە و بڕی پارەکە بنێرە.
        دوای ناردنی پارە، وێنەی رسیدەکە لە خوارەوە بنێرە.
      </div>

    </div>


    <!-- RECEIPT FORM -->

    <div id="receiptForm">

      <div class="form-group">
        <label>ناوی تەواو</label>
        <input
          type="text"
          id="userName"
          placeholder="ناوی تەواوت بنووسە">
      </div>

      <div class="form-group">
        <label>ژمارەی مۆبایل</label>
        <input
          type="tel"
          id="userPhone"
          placeholder="07xxxxxxxxx">
      </div>

      <div class="form-group">
        <label>ژمارەی مامەڵە</label>
        <input
          type="text"
          id="transactionId"
          placeholder="ئەگەر هەیە">
      </div>

      <div class="form-group">
        <label>وێنەی رسید / مامەڵە</label>
        <input
          type="file"
          id="receiptImage"
          accept="image/*">
      </div>

      <div class="form-group">
        <label>تێبینی</label>
        <textarea
          id="message"
          placeholder="هەر تێبینییەکت هەیە لێرە بنووسە"></textarea>
      </div>

      <button class="submit" onclick="sendRequest()">
        📤 ناردنی داواکاری بۆ ئەدمین
      </button>

    </div>


    <div class="success" id="successMessage">
      ✅ داواکارییەکەت نێردرا!
      <br><br>
      تکایە چاوەڕێی پشتڕاستکردنەوەی ئەدمین بکە.
      دوای دڵنیابوونەوە، Premium ـەکەت چالاک دەکرێت.
    </div>

  </div>

</div>



<script>

let selectedPlan = "";
let selectedPrice = "";
let selectedPayment = "";


/* کردنەوەی پلانەکان */

function openPricing(){

  window.scrollTo({
    top:document.body.scrollHeight,
    behavior:"smooth"
  });

}


/* هەڵبژاردنی پلان */

function choosePlan(plan,price){

  selectedPlan = plan;
  selectedPrice = price;

  document.getElementById("selectedPlan").textContent = plan;

  document.getElementById("selectedPrice").textContent = price;

  document.getElementById("paymentModal").style.display = "block";

}


/* داخستنی Modal */

function closeModal(){

  document.getElementById("paymentModal").style.display = "none";

}


/* هەڵبژاردنی شێوازی پارەدان */

function selectPayment(method){

  selectedPayment = method;

  document.getElementById("fastpayMethod").classList.remove("active");
  document.getElementById("fibMethod").classList.remove("active");

  document.getElementById("fastpayBox").style.display = "none";
  document.getElementById("fibBox").style.display = "none";

  if(method === "fastpay"){

    document
      .getElementById("fastpayMethod")
      .classList.add("active");

    document
      .getElementById("fastpayBox")
      .style.display = "block";

  }

  if(method === "fib"){

    document
      .getElementById("fibMethod")
      .classList.add("active");

    document
      .getElementById("fibBox")
      .style.display = "block";

  }

}


/* ناردنی داواکاری */

function sendRequest(){

  const name =
    document.getElementById("userName").value.trim();

  const phone =
    document.getElementById("userPhone").value.trim();

  const transaction =
    document.getElementById("transactionId").value.trim();

  const receipt =
    document.getElementById("receiptImage").files[0];

  const message =
    document.getElementById("message").value.trim();


  if(!selectedPlan){

    alert("تکایە سەرەتا پلانێک هەڵبژێرە.");

    return;

  }


  if(!selectedPayment){

    alert("تکایە FastPay یان FIB هەڵبژێرە.");

    return;

  }


  if(!name){

    alert("تکایە ناوی تەواوت بنووسە.");

    return;

  }


  if(!phone){

    alert("تکایە ژمارەی مۆبایل بنووسە.");

    return;

  }


  if(!receipt){

    alert("تکایە وێنەی رسیدەکە بنێرە.");

    return;

  }


  /*
    لەم شوێنەدا دواتر Backend / Firebase / Supabase
    زیاد دەکەین بۆ ئەوەی داواکارییەکە بە ڕاستی بگاتە
    Admin Panel.

    ئێستا تەنها نموونەی UI ـە.
  */


  console.log({
    name:name,
    phone:phone,
    plan:selectedPlan,
    price:selectedPrice,
    payment:selectedPayment,
    transaction:transaction,
    receipt:receipt.name,
    message:message
  });


  document.getElementById("receiptForm").style.display = "none";

  document.getElementById("successMessage").style.display = "block";


  alert(
    "داواکارییەکەت ئامادەی ناردنە بۆ ئەدمین. " +
    "لە وەشانی داهاتوودا بە Firebase/Supabase بە تەواوی پەیوەندی دەدرێت."
  );

}


/* کلیک لە دەرەوەی Modal */

window.onclick = function(event){

  const modal =
    document.getElementById("paymentModal");

  if(event.target === modal){

    closeModal();

  }

}

</script>

</body>
</html>
