<!DOCTYPE html>
<html lang="uz">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>KundalikMobile — Dashboard</title>

<style>
    *{margin:0;padding:0;box-sizing:border-box;font-family:'Poppins',sans-serif;}
    body{
        background:linear-gradient(135deg,#0f0f1a,#1b2d4d,#0f1628);
        min-height:100vh;
        color:#fff;
    }

    /* NAVBAR (Kundalik uslubida) */
    .navbar{
        width:100%;
        background:rgba(255,255,255,0.07);
        backdrop-filter:blur(12px);
        border-bottom:1px solid rgba(255,255,255,0.15);
        display:flex;
        padding:16px;
        font-size:20px;
        font-weight:600;
    }

    /* BO'LIMLAR MENYUSI */
    .top-menu{
        display:flex;
        overflow-x:auto;
        padding:10px 12px;
        gap:12px;
        background:rgba(255,255,255,0.05);
        backdrop-filter:blur(10px);
        border-bottom:1px solid rgba(255,255,255,0.1);
    }
    .menu-item{
        padding:10px 18px;
        background:rgba(255,255,255,0.07);
        border-radius:10px;
        font-size:14px;
        white-space:nowrap;
        cursor:pointer;
        transition:.3s;
    }
    .menu-item.active{
        background:#4c73ff;
        box-shadow:0 0 12px #4c73ff;
    }

    /* DASHBOARD KARTALARI */
    .section-title{
        margin:20px 15px 8px;
        font-size:20px;
        font-weight:600;
    }

    .cards-row{
        display:flex;
        gap:14px;
        overflow-x:auto;
        padding:0 15px;
    }
    .card{
        background:rgba(255,255,255,0.08);
        backdrop-filter:blur(14px);
        padding:18px;
        border-radius:16px;
        min-width:200px;
        border:1px solid rgba(255,255,255,0.1);
        animation:pop .5s ease;
    }
    @keyframes pop{
        from{opacity:0;transform:translateY(15px);}
        to{opacity:1;transform:translateY(0);}
    }

    .card h3{
        font-size:17px;
        margin-bottom:6px;
        color:#dfe4ff;
    }
    .card p{font-size:13px;color:#c9d1e6;}

    /* POST BLOKLARI */
    .post{
        margin:15px;
        background:rgba(255,255,255,0.07);
        padding:18px;
        border-radius:16px;
        border:1px solid rgba(255,255,255,0.1);
    }
    .post h4{font-size:16px;margin-bottom:5px;}
    .post small{color:#a9b2c9;}

    /* AI INOKOCHA */
    .ai{
        position:fixed;
        bottom:25px;
        right:22px;
        width:62px;height:62px;
        background:#4c73ff;
        border-radius:50%;
        display:flex;
        justify-content:center;
        align-items:center;
        font-size:28px;
        box-shadow:0 0 18px #4c73ff;
        cursor:pointer;
        animation:float 2.4s infinite ease-in-out;
    }
    @keyframes float{
        0%{transform:translateY(0);}
        50%{transform:translateY(-7px);}
        100%{transform:translateY(0);}
    }
</style>
</head>

<body>

<div class="navbar">KundalikMobile</div>

<!-- MENYU (Kundalikga o'xshash) -->
<div class="top-menu">
    <div class="menu-item active">Ta'lim</div>
    <div class="menu-item">Muloqot</div>
    <div class="menu-item">Ilovalar</div>
    <div class="menu-item">Uy vazifa</div>
    <div class="menu-item">O‘qituvchi</div>
</div>

<!-- DARS JADVALLARI -->
<h2 class="section-title">Bugungi darslar</h2>
<div class="cards-row">
    <div class="card">
        <h3>Biologiya</h3>
        <p>08:00 – 08:45</p>
    </div>
    <div class="card">
        <h3>Tarix</h3>
        <p>09:00 – 09:45</p>
    </div>
    <div class="card">
        <h3>Fizika</h3>
        <p>10:00 – 10:45</p>
    </div>
</div>

<!-- POSTLAR (Kundalik kabi) -->
<h2 class="section-title">Yangiliklar</h2>

<div class="post">
    <h4>🔔 Sinfingiz uchun yangi e’lon</h4>
    <small>2 dekabr, 14:22</small>
</div>

<div class="post">
    <h4>📘 Uy vazifalari yangilandi</h4>
    <small>1 dekabr, 19:11</small>
</div>

<!-- AI BUTTON -->
<div class="ai">🤖</div>

</body>
</html>
