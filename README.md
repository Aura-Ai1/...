
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Sarı Lokanta — Nişantaşı</title>
<meta name="description" content="Nişantaşı'nın semt lokantası. Günlük değişen mutfağımız, rezervasyon ve QR ile kolay sipariş.">

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Playfair+Display:wght@400;500;600;700&display=swap" rel="stylesheet">

<style>
:root{
    --bg:#f4f0e7;
    --paper:#faf8f2;
    --ink:#151513;
    --muted:#777269;
    --yellow:#d9a91f;
    --yellow2:#efc84e;
    --dark:#141412;
    --line:rgba(21,21,19,.12);
    --serif:"Playfair Display",Georgia,serif;
    --sans:"DM Sans",Arial,sans-serif;
    --max:1280px;
}

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
}

body{
    background:var(--bg);
    color:var(--ink);
    font-family:var(--sans);
    overflow-x:hidden;
}

body.lock{
    overflow:hidden;
}

a{
    color:inherit;
    text-decoration:none;
}

button{
    font:inherit;
}

.container{
    width:min(var(--max),calc(100% - 56px));
    margin:auto;
}

/* =========================
   LOADER
========================= */

.loader{
    position:fixed;
    inset:0;
    z-index:9999;
    background:var(--dark);
    color:white;
    display:grid;
    place-items:center;
    transition:.8s ease;
}

.loader.done{
    opacity:0;
    visibility:hidden;
    pointer-events:none;
}

.loader-brand{
    text-align:center;
}

.loader-brand span{
    display:block;
    font-family:var(--serif);
    font-size:54px;
    letter-spacing:-2px;
}

.loader-brand small{
    display:block;
    margin-top:12px;
    color:#aaa69d;
    letter-spacing:3px;
    font-size:9px;
    text-transform:uppercase;
}

.loader-bar{
    width:120px;
    height:2px;
    background:var(--yellow);
    margin:24px auto 0;
    transform:scaleX(0);
    transform-origin:left;
    animation:load 1.2s ease forwards;
}

@keyframes load{
    to{transform:scaleX(1)}
}

/* =========================
   HEADER
========================= */

.header{
    position:fixed;
    z-index:1000;
    top:0;
    left:0;
    width:100%;
    padding:24px 0;
    transition:.35s ease;
}

.header.scrolled{
    padding:13px 0;
    background:rgba(244,240,231,.88);
    backdrop-filter:blur(20px);
    border-bottom:1px solid var(--line);
}

.nav{
    display:flex;
    align-items:center;
    justify-content:space-between;
}

.logo{
    display:flex;
    align-items:center;
    gap:11px;
    font-weight:700;
    font-size:18px;
    letter-spacing:-.5px;
}

.logo-mark{
    width:39px;
    height:39px;
    border-radius:50%;
    background:var(--yellow);
    display:grid;
    place-items:center;
    font-family:var(--serif);
    font-size:21px;
}

.nav-links{
    display:flex;
    align-items:center;
    gap:34px;
    font-size:13px;
}

.nav-links a{
    position:relative;
    color:#45423c;
}

.nav-links a:after{
    content:"";
    position:absolute;
    left:0;
    bottom:-7px;
    width:0;
    height:1px;
    background:var(--ink);
    transition:.25s;
}

.nav-links a:hover:after{
    width:100%;
}

.nav-cta{
    display:flex;
    align-items:center;
    gap:10px;
}

.small-button{
    min-height:44px;
    padding:0 18px;
    border-radius:100px;
    background:var(--ink);
    color:white;
    display:inline-flex;
    align-items:center;
    justify-content:center;
    font-size:12px;
    font-weight:700;
    transition:.25s;
}

.small-button:hover{
    background:var(--yellow);
    color:var(--ink);
    transform:translateY(-2px);
}

.menu-btn{
    display:none;
    width:44px;
    height:44px;
    border-radius:50%;
    border:1px solid var(--line);
    background:transparent;
    cursor:pointer;
}

/* =========================
   MOBILE MENU
========================= */

.mobile-menu{
    position:fixed;
    z-index:900;
    top:76px;
    left:16px;
    right:16px;
    padding:12px;
    border-radius:20px;
    background:var(--paper);
    border:1px solid var(--line);
    box-shadow:0 25px 80px rgba(0,0,0,.15);
    opacity:0;
    transform:translateY(-15px);
    pointer-events:none;
    transition:.3s;
}

.mobile-menu.open{
    opacity:1;
    transform:translateY(0);
    pointer-events:auto;
}

.mobile-menu a{
    display:block;
    padding:16px;
    border-radius:12px;
}

.mobile-menu a:hover{
    background:var(--bg);
}

/* =========================
   HERO
========================= */

.hero{
    min-height:100vh;
    padding:150px 0 70px;
    display:flex;
    align-items:center;
    position:relative;
}

.hero:before{
    content:"";
    position:absolute;
    width:650px;
    height:650px;
    border-radius:50%;
    background:var(--yellow);
    opacity:.10;
    right:-300px;
    top:50px;
    filter:blur(5px);
}

.hero-grid{
    display:grid;
    grid-template-columns:1fr .92fr;
    align-items:center;
    gap:90px;
}

.kicker{
    display:flex;
    align-items:center;
    gap:10px;
    text-transform:uppercase;
    letter-spacing:2px;
    font-size:10px;
    font-weight:700;
    color:var(--yellow-dark);
    margin-bottom:25px;
}

.kicker i{
    display:block;
    width:32px;
    height:1px;
    background:var(--yellow);
}

.hero h1{
    font-family:var(--serif);
    font-size:clamp(62px,8vw,112px);
    line-height:.88;
    letter-spacing:-5px;
    font-weight:500;
    max-width:800px;
}

.hero h1 em{
    font-style:normal;
    color:var(--yellow);
}

.hero-copy{
    max-width:560px;
    color:var(--muted);
    font-size:16px;
    line-height:1.85;
    margin-top:31px;
}

.hero-actions{
    display:flex;
    flex-wrap:wrap;
    gap:11px;
    margin-top:34px;
}

.button{
    min-height:56px;
    padding:0 24px;
    border-radius:100px;
    display:inline-flex;
    align-items:center;
    justify-content:center;
    gap:12px;
    font-size:13px;
    font-weight:700;
    transition:.3s;
}

.button-black{
    background:var(--ink);
    color:white;
}

.button-black:hover{
    transform:translateY(-3px);
    box-shadow:0 18px 35px rgba(0,0,0,.14);
}

.button-light{
    border:1px solid var(--line);
    background:rgba(255,255,255,.4);
}

.button-light:hover{
    background:var(--yellow);
    border-color:var(--yellow);
}

.hero-media{
    position:relative;
}

.photo{
    min-height:610px;
    border-radius:30px;
    position:relative;
    overflow:hidden;
    background:
        linear-gradient(145deg,rgba(0,0,0,.02),rgba(0,0,0,.25)),
        url("assets/sari-lokanta.jpg") center/cover,
        #c49a29;
    box-shadow:0 40px 90px rgba(0,0,0,.13);
}

/*
  Fotoğraf yoksa sarı arka plan görünür.
  Gerçek fotoğraf için:
  assets/sari-lokanta.jpg
*/

.photo:after{
    content:"";
    position:absolute;
    inset:0;
    background:linear-gradient(
        to top,
        rgba(0,0,0,.42),
        transparent 50%
    );
}

.photo-caption{
    position:absolute;
    z-index:2;
    left:24px;
    right:24px;
    bottom:24px;
    padding:23px;
    border-radius:20px;
    background:rgba(250,248,242,.90);
    backdrop-filter:blur(16px);
}

.photo-caption small{
    color:var(--muted);
    font-size:9px;
    letter-spacing:1.7px;
    text-transform:uppercase;
}

.photo-caption h3{
    font-family:var(--serif);
    font-size:28px;
    font-weight:500;
    line-height:1.1;
    margin-top:8px;
}

.photo-caption p{
    color:var(--muted);
    font-size:11px;
    margin-top:8px;
}

/* =========================
   TICKER
========================= */

.ticker{
    background:var(--ink);
    color:white;
    overflow:hidden;
}

.ticker-track{
    width:max-content;
    display:flex;
    animation:move 25s linear infinite;
}

.ticker-item{
    padding:19px 35px;
    font-family:var(--serif);
    font-size:18px;
    display:flex;
    gap:35px;
    align-items:center;
}

.ticker-item b{
    color:var(--yellow);
}

@keyframes move{
    to{transform:translateX(-50%)}
}

/* =========================
   COMMON
========================= */

section{
    padding:135px 0;
}

.section-top{
    display:flex;
    justify-content:space-between;
    align-items:end;
    gap:50px;
    margin-bottom:65px;
}

.label{
    font-size:10px;
    text-transform:uppercase;
    letter-spacing:2px;
    color:var(--yellow-dark);
    font-weight:700;
    margin-bottom:17px;
}

.title{
    font-family:var(--serif);
    font-weight:500;
    font-size:clamp(45px,5vw,72px);
    line-height:.98;
    letter-spacing:-3px;
}

.description{
    max-width:460px;
    color:var(--muted);
    font-size:14px;
    line-height:1.85;
}

/* =========================
   STORY
========================= */

.story{
    background:var(--paper);
}

.story-grid{
    display:grid;
    grid-template-columns:.65fr 1.35fr;
    gap:110px;
    align-items:center;
}

.story-number{
    font-family:var(--serif);
    color:var(--yellow);
    font-size:180px;
    line-height:.8;
}

.story-content h2{
    font-family:var(--serif);
    font-size:clamp(42px,5vw,67px);
    line-height:1;
    letter-spacing:-2px;
    max-width:750px;
}

.story-content p{
    color:var(--muted);
    max-width:700px;
    font-size:15px;
    line-height:1.9;
    margin-top:24px;
}

.signature{
    font-family:var(--serif);
    font-size:25px;
    margin-top:31px;
}

/* =========================
   PHILOSOPHY
========================= */

.values{
    background:var(--bg);
}

.values-grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    border-top:1px solid var(--line);
}

.value{
    min-height:320px;
    padding:35px;
    border-right:1px solid var(--line);
    position:relative;
}

.value:last-child{
    border-right:0;
}

.value-number{
    color:var(--yellow-dark);
    font-size:10px;
    letter-spacing:1px;
}

.value h3{
    font-family:var(--serif);
    font-size:32px;
    font-weight:500;
    margin-top:95px;
}

.value p{
    color:var(--muted);
    font-size:13px;
    line-height:1.75;
    max-width:300px;
    margin-top:12px;
}

/* =========================
   KITCHEN
========================= */

.kitchen{
    background:var(--dark);
    color:white;
    position:relative;
    overflow:hidden;
}

.kitchen:before{
    content:"S";
    position:absolute;
    right:-100px;
    top:-170px;
    font-family:var(--serif);
    font-size:700px;
    line-height:1;
    color:rgba(255,255,255,.025);
}

.kitchen-grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:100px;
    align-items:center;
    position:relative;
    z-index:1;
}

.kitchen .label{
    color:var(--yellow);
}

.kitchen h2{
    font-family:var(--serif);
    font-size:clamp(48px,6vw,82px);
    line-height:.94;
    letter-spacing:-3px;
    max-width:680px;
}

.kitchen-copy{
    color:#aaa69e;
    font-size:15px;
    line-height:1.9;
    max-width:580px;
    margin-top:28px;
}

.kitchen-list{
    border-top:1px solid rgba(255,255,255,.12);
}

.kitchen-row{
    min-height:80px;
    display:flex;
    justify-content:space-between;
    align-items:center;
    border-bottom:1px solid rgba(255,255,255,.12);
}

.kitchen-row strong{
    font-family:var(--serif);
    font-size:23px;
    font-weight:400;
}

.kitchen-row span{
    color:var(--yellow);
    text-transform:uppercase;
    letter-spacing:1.4px;
    font-size:9px;
}

/* =========================
   QR
========================= */

.order{
    background:var(--yellow);
}

.order-grid{
    display:grid;
    grid-template-columns:1.3fr .7fr;
    gap:80px;
    align-items:center;
}

.order h2{
    font-family:var(--serif);
    font-size:clamp(50px,7vw,90px);
    line-height:.9;
    letter-spacing:-4px;
    max-width:850px;
}

.order p{
    max-width:590px;
    color:rgba(0,0,0,.62);
    line-height:1.8;
    font-size:15px;
    margin-top:25px;
}

.qr-card{
    background:white;
    padding:24px;
    border-radius:28px;
    box-shadow:0 30px 70px rgba(0,0,0,.13);
    text-align:center;
}

.qr{
    aspect-ratio:1;
    position:relative;
    background:white;
    border:1px solid #ddd;
    overflow:hidden;
    display:grid;
    place-items:center;
}

/* Dekoratif QR görünümü */
.qr-pattern{
    width:78%;
    height:78%;
    background:
        linear-gradient(90deg,#111 10px,transparent 10px) 0 0/23px 23px,
        linear-gradient(#111 10px,transparent 10px) 0 0/23px 23px;
    opacity:.9;
}

.qr-corner{
    position:absolute;
    width:55px;
    height:55px;
    border:9px solid #111;
}

.qr-corner.one{
    left:14px;
    top:14px;
}

.qr-corner.two{
    right:14px;
    top:14px;
}

.qr-corner.three{
    left:14px;
    bottom:14px;
}

.qr-card strong{
    display:block;
    margin-top:18px;
    font-size:13px;
}

.qr-card small{
    color:var(--muted);
    display:block;
    margin-top:5px;
    font-size:11px;
}

/* =========================
   DELIVERY
========================= */

.delivery{
    background:var(--paper);
}

.delivery-grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:100px;
    align-items:center;
}

.delivery h2{
    font-family:var(--serif);
    font-size:clamp(45px,5vw,72px);
    line-height:.96;
    letter-spacing:-3px;
}

.delivery p{
    max-width:550px;
    color:var(--muted);
    font-size:15px;
    line-height:1.85;
    margin-top:25px;
}

.delivery-info{
    background:var(--bg);
    border-radius:28px;
    padding:35px;
}

.info-row{
    display:flex;
    justify-content:space-between;
    gap:20px;
    padding:20px 0;
    border-bottom:1px solid var(--line);
}

.info-row:last-child{
    border:0;
}

.info-row span{
    color:var(--muted);
    font-size:12px;
}

.info-row strong{
    font-size:13px;
}

/* =========================
   RESERVATION
========================= */

.reservation{
    padding-top:0;
    background:var(--paper);
}

.reservation-box{
    background:var(--dark);
    color:white;
    border-radius:32px;
    text-align:center;
    padding:90px 30px;
    position:relative;
    overflow:hidden;
}

.reservation-box:before,
.reservation-box:after{
    content:"";
    position:absolute;
    border:1px solid rgba(224,179,41,.23);
    border-radius:50%;
}

.reservation-box:before{
    width:390px;
    height:390px;
    left:-190px;
    top:-190px;
}

.reservation-box:after{
    width:330px;
    height:330px;
    right:-160px;
    bottom:-180px;
}

.reservation-box .label{
    color:var(--yellow);
}

.reservation-box h2{
    font-family:var(--serif);
    font-size:clamp(48px,6vw,82px);
    line-height:.95;
    letter-spacing:-3px;
    max-width:850px;
    margin:auto;
    position:relative;
    z-index:2;
}

.reservation-box p{
    color:#aaa69e;
    max-width:550px;
    line-height:1.8;
    font-size:14px;
    margin:25px auto 30px;
    position:relative;
    z-index:2;
}

.reservation-actions{
    display:flex;
    justify-content:center;
    flex-wrap:wrap;
    gap:10px;
    position:relative;
    z-index:2;
}

.button-yellow{
    background:var(--yellow);
    color:var(--ink);
}

.button-yellow:hover{
    background:white;
}

.button-outline{
    color:white;
    border:1px solid rgba(255,255,255,.2);
}

.button-outline:hover{
    border-color:white;
}

/* =========================
   CONTACT
========================= */

.contact{
    background:var(--paper);
}

.contact-grid{
    display:grid;
    grid-template-columns:.85fr 1.15fr;
    gap:100px;
    align-items:stretch;
}

.contact h2{
    font-family:var(--serif);
    font-size:clamp(45px,5vw,72px);
    line-height:.95;
    letter-spacing:-3px;
}

.details{
    margin-top:40px;
}

.detail{
    padding:19px 0;
    border-bottom:1px solid var(--line);
}

.detail small{
    display:block;
    color:var(--yellow-dark);
    text-transform:uppercase;
    font-weight:700;
    font-size:9px;
    letter-spacing:1.5px;
    margin-bottom:7px;
}

.detail span,
.detail a{
    font-size:14px;
}

.map{
    min-height:480px;
    border-radius:30px;
    overflow:hidden;
    background:#ddd7c9;
    position:relative;
    display:grid;
    place-items:center;
}

.map-grid{
    position:absolute;
    inset:-100px;
    opacity:.35;
    background:
        linear-gradient(25deg,transparent 47%,#aaa 48%,#aaa 49%,transparent 50%),
        linear-gradient(155deg,transparent 47%,#aaa 48%,#aaa 49%,transparent 50%);
    background-size:90px 90px;
    transform:rotate(8deg);
}

.pin{
    position:relative;
    z-index:2;
    width:82px;
    height:82px;
    border-radius:50%;
    background:var(--yellow);
    display:grid;
    place-items:center;
    font-size:25px;
    box-shadow:0 20px 45px rgba(0,0,0,.18);
}

/* =========================
   FOOTER
========================= */

footer{
    background:var(--dark);
    color:white;
    padding:70px 0 28px;
}

.footer-top{
    display:flex;
    justify-content:space-between;
    gap:60px;
    padding-bottom:55px;
    border-bottom:1px solid rgba(255,255,255,.1);
}

.footer-description{
    color:#858179;
    max-width:330px;
    line-height:1.7;
    font-size:12px;
    margin-top:16px;
}

.footer-links{
    display:flex;
    gap:80px;
}

.footer-column strong{
    display:block;
    color:var(--yellow);
    text-transform:uppercase;
    letter-spacing:1.5px;
    font-size:9px;
    margin-bottom:18px;
}

.footer-column a{
    display:block;
    color:#aaa69e;
    font-size:12px;
    margin-bottom:12px;
    transition:.2s;
}

.footer-column a:hover{
    color:white;
}

.footer-bottom{
    padding-top:24px;
    display:flex;
    justify-content:space-between;
    color:#66635c;
    font-size:10px;
}

/* =========================
   FLOATING BAR
========================= */

.floating{
    position:fixed;
    z-index:800;
    bottom:20px;
    left:50%;
    transform:translateX(-50%);
    display:flex;
    align-items:center;
    padding:5px;
    border-radius:100px;
    background:rgba(20,20,18,.94);
    backdrop-filter:blur(15px);
    box-shadow:0 20px 50px rgba(0,0,0,.2);
}

.floating a{
    padding:12px 18px;
    color:white;
    font-size:11px;
    font-weight:700;
    border-radius:100px;
}

.floating a:first-child{
    background:var(--yellow);
    color:var(--ink);
}

/* =========================
   REVEAL
========================= */

.reveal{
    opacity:0;
    transform:translateY(35px);
    transition:
        opacity .8s ease,
        transform .8s cubic-bezier(.2,.7,.2,1);
}

.reveal.show{
    opacity:1;
    transform:none;
}

/* =========================
   RESPONSIVE
========================= */

@media(max-width:950px){

    .container{
        width:min(var(--max),calc(100% - 34px));
    }

    .nav-links,
    .nav-cta{
        display:none;
    }

    .menu-btn{
        display:grid;
        place-items:center;
    }

    .hero{
        padding-top:125px;
    }

    .hero-grid,
    .story-grid,
    .kitchen-grid,
    .order-grid,
    .delivery-grid,
    .contact-grid{
        grid-template-columns:1fr;
        gap:55px;
    }

    .hero h1{
        font-size:clamp(57px,14vw,95px);
    }

    .photo{
        min-height:480px;
    }

    .section-top{
        display:block;
    }

    .section-top .description{
        margin-top:25px;
    }

    .values-grid{
        grid-template-columns:1fr;
    }

    .value{
        min-height:250px;
        border-right:0;
        border-bottom:1px solid var(--line);
    }

    .value:last-child{
        border-bottom:0;
    }

    .value h3{
        margin-top:65px;
    }

    .order-grid{
        text-align:left;
    }

    .qr-card{
        max-width:310px;
        margin:auto;
    }

    .floating{
        width:calc(100% - 24px);
        justify-content:center;
    }

    .floating a{
        flex:1;
        text-align:center;
    }
}

@media(max-width:550px){

    section{
        padding:90px 0;
    }

    .hero{
        min-height:auto;
        padding-bottom:80px;
    }

    .hero-actions{
        flex-direction:column;
    }

    .button{
        width:100%;
    }

    .photo{
        min-height:410px;
        border-radius:22px;
    }

