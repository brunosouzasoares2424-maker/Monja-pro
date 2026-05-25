<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1">
<title>MounjaPRO — Volte a sentir controle sobre sua fome</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
/* ─── RESET & ROOT ─────────────────────────────── */
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --purple:#4c1d95;
  --purple-mid:#6d28d9;
  --purple-soft:#ede9fe;
  --orange:#f97316;
  --orange-soft:#fff7ed;
  --cream:#faf9f7;
  --dark:#1a1523;
  --mid:#4b4558;
  --light:#8b7fa8;
  --border:#e8e4f0;
  --white:#ffffff;
  --radius:18px;
  --shadow:0 4px 32px rgba(76,29,149,.10);
}
html{scroll-behavior:smooth}
body{font-family:'DM Sans',sans-serif;background:var(--cream);color:var(--dark);line-height:1.65;overflow-x:hidden}
a{text-decoration:none;color:inherit}
img{max-width:100%;display:block}

/* ─── TRUST BAR ────────────────────────────────── */
.trust-bar{
  background:var(--dark);
  color:rgba(255,255,255,.75);
  display:flex;justify-content:center;align-items:center;
  gap:28px;flex-wrap:wrap;
  padding:10px 20px;
  font-size:.78rem;font-weight:500;letter-spacing:.03em;
}
.trust-bar span{display:flex;align-items:center;gap:5px;color:#fff}
.trust-bar span em{opacity:.5;font-style:normal}

/* ─── NAV ──────────────────────────────────────── */
nav{
  background:var(--white);
  border-bottom:1px solid var(--border);
  display:flex;align-items:center;justify-content:space-between;
  padding:14px 32px;
  position:sticky;top:0;z-index:900;
}
.nav-logo img{height:36px}
.nav-cta{
  background:var(--orange);color:var(--white);
  font-weight:700;font-size:.85rem;
  padding:10px 22px;border-radius:100px;
  transition:transform .2s,box-shadow .2s;
  box-shadow:0 4px 18px rgba(249,115,22,.35);
  white-space:nowrap;
}
.nav-cta:hover{transform:translateY(-2px);box-shadow:0 8px 28px rgba(249,115,22,.45)}

/* ─── HERO ─────────────────────────────────────── */
.hero{
  display:grid;grid-template-columns:1fr 1fr;
  max-width:1100px;margin:0 auto;
  padding:64px 32px 56px;
  gap:48px;align-items:center;
}
@media(max-width:760px){
  .hero{grid-template-columns:1fr;padding:40px 20px 32px;gap:32px}
  .hero-media{order:-1}
}

.hero-eyebrow{
  display:inline-flex;align-items:center;gap:8px;
  background:var(--purple-soft);color:var(--purple-mid);
  border-radius:100px;padding:6px 16px;
  font-size:.78rem;font-weight:600;letter-spacing:.05em;text-transform:uppercase;
  margin-bottom:20px;
}
.hero h1{
  font-family:'DM Serif Display',serif;
  font-size:clamp(2rem,4.5vw,3rem);
  line-height:1.18;
  color:var(--dark);
  margin-bottom:16px;
}
.hero h1 em{color:var(--purple-mid);font-style:normal}
.hero-sub{
  font-size:1.05rem;color:var(--mid);
  font-weight:400;margin-bottom:32px;max-width:460px;
}

.hero-trust{
  display:flex;align-items:center;gap:16px;
  flex-wrap:wrap;margin-bottom:28px;
}
.stars-row{display:flex;gap:2px}
.star{color:#f59e0b;font-size:1rem}
.hero-trust-text{font-size:.85rem;color:var(--mid)}
.hero-trust-text strong{color:var(--dark)}

.btn-main{
  display:inline-flex;align-items:center;justify-content:center;gap:10px;
  background:linear-gradient(135deg,var(--purple) 0%,var(--purple-mid) 100%);
  color:var(--white);font-weight:700;font-size:1rem;
  padding:18px 36px;border-radius:100px;
  box-shadow:0 8px 32px rgba(109,40,217,.35);
  transition:transform .2s,box-shadow .2s;
  width:100%;max-width:420px;
  letter-spacing:.02em;
}
.btn-main:hover{transform:translateY(-3px);box-shadow:0 14px 40px rgba(109,40,217,.45)}
.btn-main svg{flex-shrink:0}

.hero-reassurance{
  display:flex;gap:20px;flex-wrap:wrap;margin-top:16px;
}
.reassure-item{
  display:flex;align-items:center;gap:6px;
  font-size:.8rem;color:var(--mid);font-weight:500;
}
.reassure-item span.dot{
  width:7px;height:7px;border-radius:50%;
  background:var(--purple-mid);flex-shrink:0;
}

/* UGC Video frame */
.hero-media{position:relative}
.video-phone{
  width:100%;max-width:320px;
  margin:0 auto;
  background:#000;
  border-radius:32px;
  overflow:hidden;
  box-shadow:0 24px 80px rgba(76,29,149,.22);
  position:relative;
  aspect-ratio:9/16;
}
.video-phone video{width:100%;height:100%;object-fit:cover}
.phone-overlay{
  position:absolute;inset:0;
  background:linear-gradient(to top,rgba(0,0,0,.55) 0%,transparent 40%);
  pointer-events:none;
  border-radius:32px;
}
.phone-caption{
  position:absolute;bottom:20px;left:16px;right:16px;
  color:#fff;font-size:.83rem;font-weight:600;
  line-height:1.4;
}
.tiktok-ui{
  position:absolute;top:16px;left:16px;right:16px;
  display:flex;align-items:center;gap:8px;
}
.tiktok-avatar{
  width:36px;height:36px;border-radius:50%;
  background:var(--purple-soft);overflow:hidden;
  border:2px solid #fff;
  flex-shrink:0;
}
.tiktok-avatar img{width:100%;height:100%;object-fit:cover}
.tiktok-name{color:#fff;font-size:.78rem;font-weight:700}
.tiktok-tag{color:rgba(255,255,255,.7);font-size:.7rem}

/* ─── PAIN SECTION ─────────────────────────────── */
.pain-section{
  background:var(--white);
  padding:72px 20px;
}
.pain-inner{max-width:700px;margin:0 auto;text-align:center}
.section-eyebrow{
  display:inline-block;
  color:var(--purple-mid);font-size:.78rem;font-weight:600;
  text-transform:uppercase;letter-spacing:.08em;
  margin-bottom:14px;
}
.section-title{
  font-family:'DM Serif Display',serif;
  font-size:clamp(1.6rem,4vw,2.4rem);
  line-height:1.2;margin-bottom:16px;
}
.section-sub{font-size:1rem;color:var(--mid);max-width:560px;margin:0 auto 44px}

.pain-cards{
  display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
  gap:16px;text-align:left;
}
.pain-card{
  background:var(--cream);border:1px solid var(--border);
  border-radius:var(--radius);padding:24px 20px;
  transition:border-color .2s,transform .2s;
}
.pain-card:hover{border-color:var(--purple-mid);transform:translateY(-3px)}
.pain-emoji{font-size:1.6rem;margin-bottom:10px}
.pain-card h3{font-size:.95rem;font-weight:700;margin-bottom:6px}
.pain-card p{font-size:.85rem;color:var(--mid)}

/* ─── DISCOVERY ────────────────────────────────── */
.discovery{
  padding:72px 20px;
  background:linear-gradient(160deg,var(--purple) 0%,#2e1065 100%);
  position:relative;overflow:hidden;
}
.discovery::before{
  content:'';position:absolute;inset:0;
  background:url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.03'%3E%3Ccircle cx='30' cy='30' r='2'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
  pointer-events:none;
}
.discovery-inner{
  max-width:1000px;margin:0 auto;
  display:grid;grid-template-columns:1fr 1fr;
  gap:60px;align-items:center;
}
@media(max-width:720px){.discovery-inner{grid-template-columns:1fr;gap:36px}}
.disc-text .section-eyebrow{color:rgba(255,255,255,.6)}
.disc-text .section-title{color:#fff;text-align:left;margin-bottom:20px}
.disc-sub{color:rgba(255,255,255,.75);font-size:1rem;margin-bottom:32px;max-width:420px}

.benefit-stack{display:flex;flex-direction:column;gap:14px;margin-bottom:36px}
.benefit-row{
  display:flex;align-items:flex-start;gap:14px;
  background:rgba(255,255,255,.07);
  border:1px solid rgba(255,255,255,.1);
  border-radius:14px;padding:16px 18px;
}
.benefit-icon{font-size:1.3rem;flex-shrink:0;margin-top:1px}
.benefit-body h4{color:#fff;font-size:.9rem;font-weight:700;margin-bottom:3px}
.benefit-body p{color:rgba(255,255,255,.65);font-size:.82rem}

.disc-product{
  display:flex;flex-direction:column;align-items:center;gap:20px;
}
.product-img-wrap{
  position:relative;
  background:rgba(255,255,255,.08);
  border-radius:28px;
  padding:32px;
  backdrop-filter:blur(10px);
  border:1px solid rgba(255,255,255,.12);
}
.product-img-wrap img{
  max-width:240px;
  filter:drop-shadow(0 20px 60px rgba(0,0,0,.4));
  animation:float 4s ease-in-out infinite;
}
@keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-10px)}}

.product-badges{
  display:flex;gap:10px;flex-wrap:wrap;justify-content:center;
}
.prod-badge{
  background:rgba(255,255,255,.12);
  border:1px solid rgba(255,255,255,.18);
  color:#fff;border-radius:100px;
  padding:7px 16px;font-size:.78rem;font-weight:600;
}

.btn-main-white{
  display:inline-flex;align-items:center;justify-content:center;gap:10px;
  background:var(--orange);color:#fff;
  font-weight:700;font-size:1rem;
  padding:18px 36px;border-radius:100px;
  box-shadow:0 8px 28px rgba(249,115,22,.4);
  transition:transform .2s,box-shadow .2s;
  width:100%;max-width:380px;
}
.btn-main-white:hover{transform:translateY(-3px);box-shadow:0 12px 36px rgba(249,115,22,.55)}

/* ─── BEFORE/AFTER ─────────────────────────────── */
.transformation{background:var(--white);padding:72px 20px}
.trans-inner{max-width:900px;margin:0 auto;text-align:center}
.ba-wrap{
  margin:40px auto 0;
  max-width:560px;
  border-radius:24px;overflow:hidden;
  box-shadow:0 8px 48px rgba(76,29,149,.14);
}
.ba-wrap img{width:100%}

/* ─── TESTIMONIALS ─────────────────────────────── */
.testimonials{background:var(--cream);padding:72px 20px}
.test-inner{max-width:1000px;margin:0 auto;text-align:center}
.test-grid{
  display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
  gap:20px;margin-top:44px;text-align:left;
}
.test-card{
  background:var(--white);border:1px solid var(--border);
  border-radius:var(--radius);padding:28px 24px;
  transition:box-shadow .2s,transform .2s;
}
.test-card:hover{box-shadow:var(--shadow);transform:translateY(-4px)}
.test-header{display:flex;align-items:center;gap:12px;margin-bottom:16px}
.test-avatar{
  width:46px;height:46px;border-radius:50%;
  background:var(--purple-soft);overflow:hidden;flex-shrink:0;
}
.test-avatar img{width:100%;height:100%;object-fit:cover}
.test-name{font-weight:700;font-size:.9rem}
.test-location{font-size:.75rem;color:var(--light)}
.test-stars{display:flex;gap:2px;margin-bottom:12px}
.test-stars span{color:#f59e0b;font-size:.85rem}
.test-text{font-size:.88rem;color:var(--mid);line-height:1.6;font-style:italic}
.test-tag{
  display:inline-block;
  background:var(--purple-soft);color:var(--purple-mid);
  border-radius:100px;padding:4px 12px;font-size:.72rem;font-weight:600;
  margin-top:14px;
}

/* ─── UGC VIDEO 2 ──────────────────────────────── */
.ugc-section{
  background:var(--dark);
  padding:72px 20px;
}
.ugc-inner{
  max-width:860px;margin:0 auto;
  display:grid;grid-template-columns:1fr 1fr;
  gap:52px;align-items:center;
}
@media(max-width:680px){.ugc-inner{grid-template-columns:1fr;gap:32px}}
.ugc-text .section-eyebrow{color:rgba(255,255,255,.5)}
.ugc-text .section-title{color:#fff;text-align:left;margin-bottom:16px}
.ugc-text p{color:rgba(255,255,255,.65);font-size:.95rem;margin-bottom:28px}
.mini-phones{display:flex;gap:12px;justify-content:center}
.mini-phone{
  flex:1;max-width:160px;
  background:#111;border-radius:20px;overflow:hidden;
  aspect-ratio:9/16;box-shadow:0 12px 48px rgba(0,0,0,.5);
}
.mini-phone video{width:100%;height:100%;object-fit:cover}

/* ─── HOW IT WORKS ─────────────────────────────── */
.how{background:var(--white);padding:72px 20px}
.how-inner{max-width:820px;margin:0 auto;text-align:center}
.steps{
  display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
  gap:28px;margin-top:44px;
}
.step{text-align:center;padding:0 8px}
.step-num{
  width:52px;height:52px;border-radius:50%;
  background:var(--purple-soft);color:var(--purple-mid);
  font-family:'DM Serif Display',serif;font-size:1.4rem;font-weight:700;
  display:flex;align-items:center;justify-content:center;
  margin:0 auto 16px;
}
.step h3{font-size:.95rem;font-weight:700;margin-bottom:6px}
.step p{font-size:.84rem;color:var(--mid)}

/* ─── TRUST / CHECKOUT ─────────────────────────── */
.checkout-section{
  background:linear-gradient(160deg,var(--purple) 0%,#2e1065 100%);
  padding:80px 20px;
}
.checkout-inner{
  max-width:700px;margin:0 auto;text-align:center;
}
.checkout-inner .section-title{color:#fff;margin-bottom:12px}
.checkout-sub{color:rgba(255,255,255,.7);font-size:1rem;margin-bottom:44px;max-width:480px;margin-left:auto;margin-right:auto}

.checkout-card{
  background:var(--white);border-radius:28px;
  padding:44px 36px;
  box-shadow:0 24px 80px rgba(0,0,0,.25);
}
@media(max-width:480px){.checkout-card{padding:32px 20px}}

.plan-select{display:flex;flex-direction:column;gap:12px;margin-bottom:28px}
.plan-opt{
  display:flex;align-items:center;gap:16px;
  border:2px solid var(--border);border-radius:14px;
  padding:16px 20px;cursor:pointer;
  transition:border-color .2s,background .2s;
  text-align:left;position:relative;
}
.plan-opt.selected{border-color:var(--purple-mid);background:var(--purple-soft)}
.plan-opt input[type=radio]{accent-color:var(--purple-mid)}
.plan-info{flex:1}
.plan-name{font-weight:700;font-size:.95rem}
.plan-desc{font-size:.78rem;color:var(--mid)}
.plan-price{
  font-family:'DM Serif Display',serif;
  font-size:1.3rem;color:var(--dark);font-weight:700;
}
.plan-badge-best{
  position:absolute;top:-10px;right:16px;
  background:var(--orange);color:#fff;
  font-size:.68rem;font-weight:700;padding:3px 12px;border-radius:100px;
  text-transform:uppercase;letter-spacing:.06em;
}

.checkout-btn{
  display:flex;align-items:center;justify-content:center;gap:10px;
  background:linear-gradient(135deg,var(--purple) 0%,var(--purple-mid) 100%);
  color:#fff;font-weight:700;font-size:1.05rem;
  padding:20px 28px;border-radius:100px;width:100%;
  box-shadow:0 8px 32px rgba(109,40,217,.35);
  transition:transform .2s,box-shadow .2s;
  border:none;cursor:pointer;
  letter-spacing:.02em;
  margin-bottom:16px;
}
.checkout-btn:hover{transform:translateY(-2px);box-shadow:0 12px 40px rgba(109,40,217,.5)}

.checkout-microtrust{
  display:flex;justify-content:center;gap:20px;flex-wrap:wrap;
  font-size:.78rem;color:var(--mid);font-weight:500;
  margin-top:6px;
}
.checkout-microtrust span{display:flex;align-items:center;gap:5px}

.security-row{
  display:flex;justify-content:center;gap:24px;flex-wrap:wrap;
  margin-top:28px;padding-top:24px;border-top:1px solid var(--border);
}
.sec-badge{
  display:flex;flex-direction:column;align-items:center;gap:4px;
  font-size:.72rem;color:var(--mid);font-weight:600;
}
.sec-badge .si{font-size:1.4rem}

/* ─── GUARANTEE ────────────────────────────────── */
.guarantee{background:var(--cream);padding:72px 20px}
.guarantee-inner{
  max-width:620px;margin:0 auto;
  background:var(--white);border:1px solid var(--border);
  border-radius:28px;padding:52px 40px;text-align:center;
  box-shadow:var(--shadow);
}
@media(max-width:480px){.guarantee-inner{padding:36px 20px}}
.guarantee-icon{font-size:3.5rem;margin-bottom:16px;display:block}
.guarantee-inner h2{
  font-family:'DM Serif Display',serif;
  font-size:1.8rem;margin-bottom:12px;
}
.guarantee-inner p{color:var(--mid);font-size:.95rem;margin-bottom:28px}
.g-list{
  display:flex;flex-direction:column;gap:10px;text-align:left;
  margin-bottom:28px;
}
.g-item{
  display:flex;align-items:center;gap:10px;
  font-size:.88rem;font-weight:600;
}
.g-check{color:#16a34a;font-size:1rem}

/* ─── FAQ ──────────────────────────────────────── */
.faq{background:var(--white);padding:72px 20px}
.faq-inner{max-width:680px;margin:0 auto;text-align:center}
.faq-list{margin-top:44px;text-align:left}
.faq-item{
  border-bottom:1px solid var(--border);
  padding:20px 0;
}
.faq-q{
  display:flex;align-items:center;justify-content:space-between;
  cursor:pointer;font-weight:600;font-size:.95rem;
  gap:16px;user-select:none;
}
.faq-q .arr{
  flex-shrink:0;color:var(--purple-mid);
  transition:transform .3s;font-size:1.1rem;
}
.faq-item.open .arr{transform:rotate(180deg)}
.faq-a{
  font-size:.88rem;color:var(--mid);
  max-height:0;overflow:hidden;
  transition:max-height .35s ease,padding .35s ease;
}
.faq-item.open .faq-a{max-height:200px;padding-top:12px}

/* ─── FOOTER ───────────────────────────────────── */
footer{
  background:var(--dark);
  padding:52px 24px 32px;
}
.footer-inner{
  max-width:900px;margin:0 auto;
  display:grid;grid-template-columns:1.6fr 1fr 1fr;
  gap:40px;margin-bottom:40px;
}
@media(max-width:600px){.footer-inner{grid-template-columns:1fr}}
.footer-logo img{height:32px;margin-bottom:14px;filter:brightness(0) invert(1)}
.footer-brand p{color:rgba(255,255,255,.5);font-size:.82rem;line-height:1.7}
.footer-col h4{
  color:rgba(255,255,255,.4);font-size:.72rem;font-weight:700;
  text-transform:uppercase;letter-spacing:.08em;margin-bottom:14px;
}
.footer-col a{
  display:block;color:rgba(255,255,255,.6);font-size:.83rem;
  margin-bottom:9px;font-weight:500;transition:color .2s;
}
.footer-col a:hover{color:#fff}
.footer-bottom{
  border-top:1px solid rgba(255,255,255,.08);
  padding-top:24px;display:flex;flex-wrap:wrap;
  align-items:center;justify-content:space-between;gap:12px;
  font-size:.75rem;color:rgba(255,255,255,.3);
}

/* ─── STICKY CTA ───────────────────────────────── */
.sticky-cta{
  position:fixed;bottom:0;left:0;right:0;z-index:999;
  background:var(--white);
  border-top:1px solid var(--border);
  padding:14px 20px;
  display:flex;align-items:center;justify-content:space-between;gap:12px;
  box-shadow:0 -4px 24px rgba(76,29,149,.12);
}
.sticky-left{display:flex;flex-direction:column}
.sticky-label{font-size:.72rem;color:var(--light);font-weight:500}
.sticky-msg{font-size:.88rem;font-weight:700;color:var(--dark)}
.sticky-btn{
  background:linear-gradient(135deg,var(--purple) 0%,var(--purple-mid) 100%);
  color:#fff;font-weight:700;font-size:.88rem;
  padding:12px 24px;border-radius:100px;white-space:nowrap;
  box-shadow:0 4px 18px rgba(109,40,217,.35);
  transition:transform .2s;flex-shrink:0;
}
.sticky-btn:hover{transform:scale(1.03)}

/* ─── ANIMATIONS ───────────────────────────────── */
.fade-in{opacity:0;transform:translateY(20px);transition:opacity .6s ease,transform .6s ease}
.fade-in.visible{opacity:1;transform:none}

/* ─── DISCLAIMER ───────────────────────────────── */
.legal{
  background:var(--cream);border-top:1px solid var(--border);
  padding:20px;text-align:center;
  font-size:.72rem;color:var(--light);line-height:1.6;
}

</style>
</head>
<body>

<!-- LOGO BANNER TOPO -->
<div style="width:100%;background:#ffffff;padding:18px 0;text-align:center;border-bottom:1px solid #e8e4f0;">
  <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAACEEAAALoCAIAAAAS2u5YAABnL2NhQlgAAGcvanVtYgAAAB5qdW1kYzJwYQARABCAAACqADibcQNjMnBhAAAAZwlqdW1iAAAAR2p1bWRjMm1hABEAEIAAAKoAOJtxA3VybjpjMnBhOjc3OWJmZmViLTI1MTEtNDNkZi04ZmY0LWI3Y2ZhYjg1NDM4ZQAAABblanVtYgAAAClqdW1kYzJhcwARABCAAACqADibcQNjMnBhLmFzc2VydGlvbnMAAAAJ0Wp1bWIAAAA7anVtZEDLDDK7ikidpwsq1vR/Q2kTYzJwYS5pY29uAAAAABhjMnNofYUTWhT850p9tWyCp0yyAQAAABdiZmRiAGltYWdlL3N2Zyt4bWwAAAAJd2JpZGI8c3ZnIHdpZHRoPSI3MTYiIGhlaWdodD0iNzE2IiB2aWV3Qm94PSIwIDAgNzE2IDcxNiIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTUwOC43NDkgMzE3LjM5OUM1MTYuNzc3IDI4Ny4zMTQgNTA4Ljk5MSAyNTMuODg0IDQ4NS4zODkgMjMwLjI4MkM0NjEuNzg4IDIwNi42ODEgNDI4LjM2IDE5OC44OTUgMzk4LjI3MyAyMDYuOTIzQzM3Ni4yMzEgMTg0LjkyOCAzNDMuMzkgMTc0Ljk1NiAzMTEuMTQ4IDE4My41OTZDMjc4LjkwNiAxOTIuMjM0IDI1NS40NSAyMTcuMjkyIDI0Ny4zNiAyNDcuMzYxQzIxNy4yOTEgMjU1LjQ1MSAxOTIuMjMzIDI3OC45MSAxODMuNTk1IDMxMS4xNDlDMTc0Ljk1NyAzNDMuMzkxIDE4NC45MjcgMzc2LjIzMiAyMDYuOTI0IDM5OC4yNzRDMTk4Ljg5NiA0MjguMzU5IDIwNi42ODMgNDYxLjc4OSAyMzAuMjg0IDQ4NS4zOTFDMjUzLjg4NSA1MDguOTkyIDI4Ny4zMTMgNTE2Ljc3OSAzMTcuNDAxIDUwOC43NUMzMzkuNDQyIDUzMC43NDUgMzcyLjI4NiA1NDAuNzE3IDQwNC41MjUgNTMyLjA3OUM0MzYuNzY3IDUyMy40NDEgNDYwLjIyMyA0OTguMzg0IDQ2OC4zMTMgNDY4LjMxNUM0OTguMzgzIDQ2MC4yMjQgNTIzLjQ0IDQzNi43NjYgNTMyLjA3OCA0MDQuNTI2QzU0MC43MTYgMzcyLjI4NSA1MzAuNzQ3IDMzOS40NDMgNTA4Ljc0OSAzMTcuNDAyVjMxNy4zOTlaTTQ3MC44OTkgMjQ0Ljc3NkM0ODYuODkyIDI2MC43NyA0OTMuNDg4IDI4Mi42MDEgNDkwLjY4NyAzMDMuNDEyTDQxNS41NzcgMjYwLjA0
