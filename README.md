<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>LPJ Kampung Lestari Sehat — Juli 2026</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,400;9..144,500;9..144,600;9..144,700&family=Manrope:wght@400;500;600;700;800&family=IBM+Plex+Mono:wght@500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --bg: #eef4f0;
    --panel: #ffffff;
    --ink: #142621;
    --ink-soft: #52655c;
    --ink-faint: #8a9a92;

    --teal-900: #0a3830;
    --teal-700: #0e5b4c;
    --teal-600: #146e5a;
    --teal-500: #2f8570;
    --sage-200: #d8e8de;
    --sage-100: #eaf3ee;

    --alert-700: #a5352a;
    --alert-500: #d9584a;
    --alert-100: #f8e4e1;

    --gold-700: #8c6712;
    --gold-500: #b9871f;
    --gold-100: #f4e9d1;

    --blue-600: #2f5f8a;
    --blue-100: #e2ecf4;

    --line: #dbe6df;

    --font-display: 'Fraunces', Georgia, serif;
    --font-body: 'Manrope', -apple-system, sans-serif;
    --font-mono: 'IBM Plex Mono', 'Courier New', monospace;
  }

  *{box-sizing:border-box;}
  html{-webkit-text-size-adjust:100%;}
  body{
    margin:0;
    background:var(--bg);
    color:var(--ink);
    font-family:var(--font-body);
    line-height:1.55;
    -webkit-font-smoothing:antialiased;
  }

  .page{
    max-width:560px;
    margin:0 auto;
    background:var(--panel);
    min-height:100vh;
    box-shadow:0 0 60px rgba(10,56,48,0.08);
    overflow:hidden;
  }

  a{color:inherit;}
  img,svg{display:block;max-width:100%;}

  /* ---------- HERO ---------- */
  .hero{
    background:linear-gradient(165deg,var(--teal-900) 0%,var(--teal-700) 55%,var(--teal-600) 100%);
    color:#f2f8f5;
    padding:34px 24px 30px;
    position:relative;
  }
  .hero::after{
    content:"";
    position:absolute;
    inset:auto 0 0 0;
    height:1px;
    background:rgba(255,255,255,0.12);
  }
  .eyebrow{
    font-family:var(--font-mono);
    font-size:0.68rem;
    letter-spacing:0.14em;
    text-transform:uppercase;
    color:#b7d8cb;
    display:flex;
    align-items:center;
    gap:8px;
    margin-bottom:14px;
  }
  .eyebrow .dot{width:6px;height:6px;border-radius:50%;background:#7fd9b6;flex:none;}
  .hero h1{
    font-family:var(--font-display);
    font-weight:600;
    font-size:1.85rem;
    line-height:1.2;
    margin:0 0 10px;
    letter-spacing:-0.01em;
  }
  .hero p.loc{
    margin:0;
    font-size:0.85rem;
    color:#cfe4da;
  }
  .pulse-wrap{margin:22px -4px -6px;opacity:0.9;}
  .pulse-wrap svg{width:100%;height:auto;}

  .hero-stats{
    display:grid;
    grid-template-columns:1fr 1fr 1fr;
    gap:1px;
    background:rgba(255,255,255,0.14);
    border-radius:14px;
    overflow:hidden;
    margin-top:18px;
  }
  .hero-stat{
    background:rgba(255,255,255,0.06);
    padding:14px 10px;
    text-align:center;
  }
  .hero-stat .v{
    font-family:var(--font-mono);
    font-size:1.15rem;
    font-weight:600;
    color:#fff;
    display:block;
  }
  .hero-stat .l{
    font-size:0.65rem;
    color:#bcd9cb;
    margin-top:4px;
    line-height:1.3;
  }

  /* ---------- SECTIONS ---------- */
  section{
    padding:30px 24px;
    border-bottom:1px solid var(--line);
  }
  section.tight{padding-top:22px;}
  .sec-eyebrow{
    font-family:var(--font-mono);
    font-size:0.68rem;
    letter-spacing:0.12em;
    text-transform:uppercase;
    color:var(--teal-600);
    margin-bottom:8px;
    font-weight:600;
  }
  h2.sec-title{
    font-family:var(--font-display);
    font-size:1.35rem;
    font-weight:600;
    margin:0 0 14px;
    color:var(--teal-900);
    letter-spacing:-0.01em;
  }
  p{margin:0 0 12px;color:var(--ink-soft);font-size:0.92rem;}
  p:last-child{margin-bottom:0;}

  .reveal{opacity:0;transform:translateY(14px);transition:opacity 0.6s ease, transform 0.6s ease;}
  .reveal.is-visible{opacity:1;transform:translateY(0);}

  /* ---------- PENDAHULUAN ---------- */
  .info-card{
    background:var(--sage-100);
    border-radius:14px;
    padding:16px;
    margin-bottom:10px;
  }
  .info-card .lbl{
    font-size:0.72rem;
    font-weight:700;
    color:var(--teal-700);
    text-transform:uppercase;
    letter-spacing:0.06em;
    margin-bottom:6px;
  }
  .info-card p{color:var(--ink);font-size:0.88rem;margin:0;}

  /* ---------- AGENDA ---------- */
  .meta-row{
    display:flex;
    gap:10px;
    font-size:0.82rem;
    color:var(--ink-soft);
    margin-bottom:18px;
    flex-wrap:wrap;
  }
  .meta-row span{
    background:var(--sage-100);
    padding:6px 10px;
    border-radius:20px;
    font-weight:600;
    color:var(--teal-700);
  }
  .agenda-list{list-style:none;margin:0;padding:0;counter-reset:agenda;}
  .agenda-list li{
    counter-increment:agenda;
    display:flex;
    gap:12px;
    padding:11px 0;
    border-top:1px solid var(--line);
    font-size:0.9rem;
    color:var(--ink);
  }
  .agenda-list li:first-child{border-top:none;}
  .agenda-list li::before{
    content:counter(agenda);
    font-family:var(--font-mono);
    font-weight:600;
    font-size:0.78rem;
    color:var(--teal-600);
    background:var(--sage-100);
    width:24px;height:24px;
    border-radius:50%;
    display:flex;align-items:center;justify-content:center;
    flex:none;
  }

  /* ---------- ABSENSI ---------- */
  .attend-item{margin-bottom:18px;}
  .attend-item:last-child{margin-bottom:0;}
  .attend-top{
    display:flex;
    justify-content:space-between;
    align-items:baseline;
    margin-bottom:6px;
  }
  .attend-name{font-weight:700;font-size:0.88rem;color:var(--ink);}
  .attend-num{font-family:var(--font-mono);font-size:0.82rem;color:var(--ink-soft);}
  .bar-track{
    height:10px;
    background:var(--sage-100);
    border-radius:6px;
    overflow:hidden;
    position:relative;
  }
  .bar-fill{
    height:100%;
    border-radius:6px;
    background:linear-gradient(90deg,var(--teal-500),var(--teal-600));
  }
  .attend-bottom{
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-top:6px;
  }
  .pct{font-family:var(--font-mono);font-weight:700;color:var(--teal-700);font-size:0.85rem;}
  .chip{
    font-size:0.68rem;
    font-weight:700;
    padding:3px 8px;
    border-radius:20px;
    display:inline-flex;
    align-items:center;
    gap:4px;
  }
  .chip.up{background:#e0f0e6;color:#1f7a4d;}
  .chip.down{background:var(--alert-100);color:var(--alert-700);}
  .chip.flat{background:var(--blue-100);color:var(--blue-600);}

  .total-box{
    margin-top:22px;
    background:var(--teal-900);
    color:#fff;
    border-radius:14px;
    padding:18px 16px;
    display:flex;
    justify-content:space-between;
    align-items:center;
  }
  .total-box .tl{font-size:0.78rem;color:#bcd9cb;}
  .total-box .tv{font-family:var(--font-mono);font-size:1.5rem;font-weight:700;}
  .total-box .td{font-size:0.72rem;color:#8fd6ae;margin-top:2px;font-family:var(--font-mono);}

  /* ---------- PEMETAAN KESEHATAN ---------- */
  .group-summary{display:flex;flex-direction:column;gap:10px;margin-bottom:20px;}
  .group-row{
    display:flex;
    gap:12px;
    padding:12px;
    background:var(--sage-100);
    border-radius:12px;
  }
  .group-row .tag{
    font-family:var(--font-mono);
    font-size:0.68rem;
    font-weight:700;
    color:var(--teal-700);
    background:#fff;
    border-radius:6px;
    padding:3px 7px;
    height:fit-content;
    flex:none;
  }
  .group-row p{font-size:0.85rem;margin:0;color:var(--ink);}

  .sheet-cta{
    display:flex;
    align-items:center;
    justify-content:space-between;
    gap:12px;
    background:var(--teal-700);
    color:#fff;
    border-radius:14px;
    padding:16px;
    text-decoration:none;
    margin:18px 0 22px;
    transition:background 0.2s ease;
  }
  .sheet-cta:hover{background:var(--teal-600);}
  .sheet-cta .stext{font-size:0.85rem;}
  .sheet-cta .stext b{display:block;font-size:0.95rem;margin-bottom:2px;}
  .sheet-cta .sarrow{
    font-size:1.2rem;
    flex:none;
  }

  .priority-head{
    display:flex;
    justify-content:space-between;
    align-items:baseline;
    margin-bottom:12px;
  }
  .priority-head h3{
    font-family:var(--font-display);
    font-size:1.05rem;
    margin:0;
    color:var(--teal-900);
  }
  .priority-head span{
    font-family:var(--font-mono);
    font-size:0.7rem;
    color:var(--alert-700);
    background:var(--alert-100);
    padding:3px 8px;
    border-radius:20px;
    font-weight:700;
  }

  .bp-list{list-style:none;margin:0;padding:0;}
  .bp-card{
    display:flex;
    gap:12px;
    align-items:flex-start;
    padding:13px 0;
    border-top:1px solid var(--line);
  }
  .bp-card:first-child{border-top:none;}
  .bp-rank{
    font-family:var(--font-mono);
    font-size:0.72rem;
    color:var(--ink-faint);
    width:16px;
    flex:none;
    padding-top:3px;
  }
  .bp-main{flex:1;min-width:0;}
  .bp-name{font-weight:700;font-size:0.88rem;color:var(--ink);margin-bottom:2px;}
  .bp-note{font-size:0.78rem;color:var(--ink-soft);}
  .bp-read{
    flex:none;
    text-align:right;
  }
  .bp-num{
    font-family:var(--font-mono);
    font-weight:700;
    font-size:1.05rem;
    color:var(--alert-700);
    line-height:1.1;
  }
  .bp-unit{
    font-family:var(--font-mono);
    font-size:0.62rem;
    color:var(--ink-faint);
    letter-spacing:0.04em;
  }

  .zone-note{
    margin-top:16px;
    background:var(--blue-100);
    border-radius:12px;
    padding:13px 14px;
  }
  .zone-note p{font-size:0.83rem;color:var(--blue-600);margin:0;}
  .zone-note b{color:var(--blue-600);}

  /* ---------- EVALUASI ---------- */
  .rtl-list{list-style:none;margin:0;padding:0;counter-reset:rtl;}
  .rtl-list li{
    counter-increment:rtl;
    padding:14px 0;
    border-top:1px solid var(--line);
  }
  .rtl-list li:first-child{border-top:none;}
  .rtl-list .rtl-lbl{
    display:flex;
    align-items:center;
    gap:8px;
    font-family:var(--font-mono);
    font-size:0.7rem;
    font-weight:700;
    color:var(--teal-600);
    text-transform:uppercase;
    letter-spacing:0.06em;
    margin-bottom:5px;
  }
  .rtl-list .rtl-lbl::before{
    content:counter(rtl,decimal-leading-zero);
  }
  .rtl-list p{font-size:0.88rem;color:var(--ink);}

  /* ---------- KEUANGAN ---------- */
  .fin-block{margin-bottom:18px;}
  .fin-head{
    display:flex;
    justify-content:space-between;
    align-items:baseline;
    margin-bottom:8px;
  }
  .fin-head h3{
    font-family:var(--font-display);
    font-size:1rem;
    margin:0;
  }
  .fin-head h3.in{color:var(--teal-700);}
  .fin-head h3.out{color:var(--alert-700);}
  .fin-head .fin-total{
    font-family:var(--font-mono);
    font-weight:700;
    font-size:0.92rem;
  }
  .fin-row{
    display:flex;
    justify-content:space-between;
    padding:8px 0;
    border-top:1px dashed var(--line);
    font-size:0.85rem;
  }
  .fin-row:first-child{border-top:none;}
  .fin-row .fname{color:var(--ink-soft);}
  .fin-row .famt{font-family:var(--font-mono);color:var(--ink);font-weight:600;}

  .balance-card{
    margin-top:22px;
    background:linear-gradient(155deg,var(--gold-500),var(--gold-700));
    border-radius:16px;
    padding:20px;
    color:#fff;
    text-align:center;
  }
  .balance-card .bl{
    font-size:0.72rem;
    letter-spacing:0.1em;
    text-transform:uppercase;
    font-family:var(--font-mono);
    color:#f7ecd3;
    margin-bottom:6px;
  }
  .balance-card .bv{
    font-family:var(--font-mono);
    font-size:2rem;
    font-weight:700;
    letter-spacing:-0.02em;
  }
  .balance-card .bs{
    display:inline-block;
    margin-top:8px;
    background:rgba(255,255,255,0.2);
    padding:4px 12px;
    border-radius:20px;
    font-size:0.72rem;
    font-weight:700;
  }

  /* ---------- FOOTER ---------- */
  footer{
    padding:32px 24px 40px;
    background:var(--teal-900);
    color:#cfe4da;
  }
  footer p{color:#cfe4da;font-size:0.85rem;}
  .sig-block{
    margin-top:20px;
    padding-top:20px;
    border-top:1px solid rgba(255,255,255,0.15);
  }
  .sig-block .sig-loc{font-size:0.78rem;color:#8fb5a5;margin-bottom:18px;}
  .sig-line{
    font-size:0.78rem;
    color:#a9c9ba;
    line-height:1.6;
  }
  .sig-line b{color:#fff;display:block;font-family:var(--font-display);font-size:0.98rem;font-weight:600;margin-top:2px;}
  .sig-space{height:44px;border-bottom:1px solid rgba(255,255,255,0.2);margin:14px 0 10px;max-width:200px;}

  @media (prefers-reduced-motion: reduce){
    .reveal{opacity:1;transform:none;transition:none;}
  }
</style>
</head>
<body>
<div class="page">

  <!-- HERO -->
  <div class="hero">
    <div class="eyebrow"><span class="dot"></span>LPJ Kampung Lestari Sehat · Edisi Juli 2026</div>
    <h1>Report Kampung Lestari Sehat</h1>
    <p class="loc">RT 13 / RW 06 · Kelurahan Manyaran, Semarang Barat, Kota Semarang</p>

    <div class="pulse-wrap">
      <svg viewBox="0 0 500 60" preserveAspectRatio="none">
        <polyline points="0,32 60,32 80,32 95,10 110,50 125,32 160,32 200,32 215,14 228,48 240,32 500,32"
          fill="none" stroke="#7fd9b6" stroke-width="2.5" stroke-linejoin="round" stroke-linecap="round"/>
      </svg>
    </div>

    <div class="hero-stats">
      <div class="hero-stat">
        <span class="v">66,67%</span>
        <span class="l">Partisipasi total<br>▲ 10,72%</span>
      </div>
      <div class="hero-stat">
        <span class="v">9 org</span>
        <span class="l">Warga prioritas<br>hipertensi</span>
      </div>
      <div class="hero-stat">
        <span class="v">263,5rb</span>
        <span class="l">Saldo kas<br>bulan ini</span>
      </div>
    </div>
  </div>

  <!-- PENDAHULUAN -->
  <section class="reveal">
    <div class="sec-eyebrow">01 · Pendahuluan</div>
    <h2 class="sec-title">Kenapa Kegiatan Ini Ada</h2>
    <div class="info-card">
      <div class="lbl">Latar Belakang</div>
      <p>Program rutin bulanan untuk menjaga kualitas kesehatan warga, mempererat silaturahmi, dan mendeteksi dini faktor risiko Penyakit Tidak Menular seperti hipertensi lewat aktivitas fisik dan cek kesehatan dasar.</p>
    </div>
    <div class="info-card">
      <div class="lbl">Tujuan Laporan</div>
      <p>Melaporkan tingkat kehadiran warga, memetakan kondisi kesehatan (tensi &amp; SpO2), serta menjaga transparansi kegiatan dan akuntabilitas keuangan RT.</p>
    </div>
  </section>

  <!-- PELAKSANAAN -->
  <section class="reveal">
    <div class="sec-eyebrow">02 · Pelaksanaan</div>
    <h2 class="sec-title">Waktu, Tempat &amp; Agenda</h2>
    <div class="meta-row">
      <span>Minggu, 19 Juli 2026</span>
      <span>06.00 WIB – selesai</span>
      <span>Jalan Utama RT 13/RW 06</span>
    </div>
    <ul class="agenda-list">
      <li>Jalan sehat &amp; senam bersama warga</li>
      <li>Pengecekan kesehatan (tensi, SpO2, nadi) di Posko KLS</li>
      <li>Edukasi &amp; sharing kesehatan warga</li>
      <li>Ramah tamah &amp; pembagian konsumsi</li>
    </ul>
  </section>

  <!-- ABSENSI -->
  <section class="reveal">
    <div class="sec-eyebrow">03 · Kehadiran</div>
    <h2 class="sec-title">Siapa yang Datang Bulan Ini</h2>

    <div class="attend-item">
      <div class="attend-top"><span class="attend-name">Ibu-Ibu</span><span class="attend-num">19 / 26 warga</span></div>
      <div class="bar-track"><div class="bar-fill" style="width:73.08%"></div></div>
      <div class="attend-bottom"><span class="pct">73,08%</span><span class="chip up">▲ 15,39%</span></div>
    </div>

    <div class="attend-item">
      <div class="attend-top"><span class="attend-name">Bapak-Bapak</span><span class="attend-num">16 / 26 warga</span></div>
      <div class="bar-track"><div class="bar-fill" style="width:61.54%"></div></div>
      <div class="attend-bottom"><span class="pct">61,54%</span><span class="chip down">▼ 7,69%</span></div>
    </div>

    <div class="attend-item">
      <div class="attend-top"><span class="attend-name">Anak-Anak</span><span class="attend-num">5 / 11 warga</span></div>
      <div class="bar-track"><div class="bar-fill" style="width:45.45%"></div></div>
      <div class="attend-bottom"><span class="pct">45,45%</span><span class="chip down">▼ 9,10%</span></div>
    </div>

    <div class="attend-item">
      <div class="attend-top"><span class="attend-name">Remaja</span><span class="attend-num">6 / 6 warga</span></div>
      <div class="bar-track"><div class="bar-fill" style="width:100%"></div></div>
      <div class="attend-bottom"><span class="pct">100,00%</span><span class="chip flat">Optimal</span></div>
    </div>

    <div class="total-box">
      <div>
        <div class="tl">Total partisipasi</div>
        <div class="td">vs 55,95% (Juni 2026)</div>
      </div>
      <div>
        <div class="tv">66,67%</div>
      </div>
    </div>
  </section>

  <!-- PEMETAAN KESEHATAN -->
  <section class="reveal">
    <div class="sec-eyebrow">04 · Analisa Tensi</div>
    <h2 class="sec-title">Peta Kondisi Kesehatan Warga</h2>

    <div class="group-summary">
      <div class="group-row">
        <span class="tag">BPK</span>
        <p>Mayoritas normal/ideal. Ada tren tensi tinggi sebelum olahraga, tapi turun setelah jalan sehat.</p>
      </div>
      <div class="group-row">
        <span class="tag">IBU</span>
        <p>Partisipasi cek kesehatan paling tinggi, tapi sektor dengan fluktuasi tensi sistolik tinggi paling banyak ditemukan.</p>
      </div>
      <div class="group-row">
        <span class="tag">RMJ</span>
        <p>100% zona hijau, pembuluh darah optimal. Contoh: Raihan 106/58 mmHg, Rifqy 97/60 mmHg.</p>
      </div>
    </div>

    <a class="sheet-cta" href="https://docs.google.com/spreadsheets/d/1qoG3G8Y68jSv49JHZ1NCyKKD5NgGkdj7y8WzwCpYVXA/edit?usp=sharing" target="_blank" rel="noopener">
      <span class="stext"><b>Lihat data tensi lengkap</b>Seluruh warga, per sesi pengukuran — Google Sheets</span>
      <span class="sarrow">→</span>
    </a>

    <div class="priority-head">
      <h3>Warga Prioritas</h3>
      <span>≥ 140/90 mmHg</span>
    </div>
    <ul class="bp-list">
      <li class="bp-card">
        <span class="bp-rank">1</span>
        <div class="bp-main"><div class="bp-name">Bu Rantiyem</div><div class="bp-note">Sistolik tertinggi bulan ini</div></div>
        <div class="bp-read"><div class="bp-num">179/84</div><div class="bp-unit">MMHG</div></div>
      </li>
      <li class="bp-card">
        <span class="bp-rank">2</span>
        <div class="bp-main"><div class="bp-name">Pak M. Yusuf</div><div class="bp-note">Fluktuatif tinggi pada cek ke-3</div></div>
        <div class="bp-read"><div class="bp-num">173/80</div><div class="bp-unit">MMHG</div></div>
      </li>
      <li class="bp-card">
        <span class="bp-rank">3</span>
        <div class="bp-main"><div class="bp-name">Pak Pramono (Pak RT)</div><div class="bp-note">Diastolik / beban jantung tertinggi</div></div>
        <div class="bp-read"><div class="bp-num">165/103</div><div class="bp-unit">MMHG</div></div>
      </li>
      <li class="bp-card">
        <span class="bp-rank">4</span>
        <div class="bp-main"><div class="bp-name">Bu Wiwin Linawat</div><div class="bp-note">Hipertensi tingkat 2</div></div>
        <div class="bp-read"><div class="bp-num">158/88</div><div class="bp-unit">MMHG</div></div>
      </li>
      <li class="bp-card">
        <span class="bp-rank">5</span>
        <div class="bp-main"><div class="bp-name">Pak David Hari Prastyo</div><div class="bp-note">Turun ke 143/99 pasca senam</div></div>
        <div class="bp-read"><div class="bp-num">157/105</div><div class="bp-unit">MMHG</div></div>
      </li>
      <li class="bp-card">
        <span class="bp-rank">6</span>
        <div class="bp-main"><div class="bp-name">Bu Rini Hastiuti</div><div class="bp-note">Cenderung stabil</div></div>
        <div class="bp-read"><div class="bp-num">157/88</div><div class="bp-unit">MMHG</div></div>
      </li>
      <li class="bp-card">
        <span class="bp-rank">7</span>
        <div class="bp-main"><div class="bp-name">Bu Debora Riyani</div><div class="bp-note">Hipertensi tingkat 2</div></div>
        <div class="bp-read"><div class="bp-num">154/89</div><div class="bp-unit">MMHG</div></div>
      </li>
      <li class="bp-card">
        <span class="bp-rank">8</span>
        <div class="bp-main"><div class="bp-name">Bu Pudji Lestari</div><div class="bp-note">SpO2 sempat drop 92%, nadi 121 — membaik usai istirahat</div></div>
        <div class="bp-read"><div class="bp-num">152/84</div><div class="bp-unit">MMHG</div></div>
      </li>
      <li class="bp-card">
        <span class="bp-rank">9</span>
        <div class="bp-main"><div class="bp-name">Pak Agus Pitoyo</div><div class="bp-note">Membaik ke 135/77 pasca jalan sehat</div></div>
        <div class="bp-read"><div class="bp-num">151/82</div><div class="bp-unit">MMHG</div></div>
      </li>
    </ul>

    <div class="zone-note">
      <p><b>Catatan klinis:</b> aktivitas fisik terbukti efektif menurunkan tensi sistolik 10–16 poin secara instan bagi warga dengan riwayat tensi tinggi.</p>
    </div>
  </section>

  <!-- EVALUASI -->
  <section class="reveal">
    <div class="sec-eyebrow">05 · Evaluasi</div>
    <h2 class="sec-title">Evaluasi &amp; Rencana Tindak Lanjut</h2>
    <ul class="rtl-list">
      <li>
        <div class="rtl-lbl">Partisipasi</div>
        <p>Perlu dorongan kembali untuk Bapak-Bapak dan Anak-Anak. Remaja dan Ibu-Ibu sudah sangat baik.</p>
      </li>
      <li>
        <div class="rtl-lbl">Manfaat olahraga</div>
        <p>Layak dirutinkan — efeknya langsung terasa pada penurunan tensi warga dengan riwayat tensi tinggi.</p>
      </li>
      <li>
        <div class="rtl-lbl">Rencana bulan depan</div>
        <p>Sisipkan edukasi nutrisi/makanan rendah garam, mengingat 9 warga masuk kategori Hipertensi Tingkat 2.</p>
      </li>
    </ul>
  </section>

  <!-- KEUANGAN -->
  <section class="reveal">
    <div class="sec-eyebrow">06 · Kas KLS</div>
    <h2 class="sec-title">Ringkasan Keuangan Juli 2026</h2>

    <div class="fin-block">
      <div class="fin-head">
        <h3 class="in">Pemasukan</h3>
        <span class="fin-total" style="color:var(--teal-700)">Rp1.048.500</span>
      </div>
      <div class="fin-row"><span class="fname">Kas RT (Operasional)</span><span class="famt">Rp825.000</span></div>
      <div class="fin-row"><span class="fname">Sisa KLS Juni 2026</span><span class="famt">Rp223.500</span></div>
    </div>

    <div class="fin-block">
      <div class="fin-head">
        <h3 class="out">Pengeluaran</h3>
        <span class="fin-total" style="color:var(--alert-700)">Rp785.000</span>
      </div>
      <div class="fin-row"><span class="fname">Konsumsi jalan sehat</span><span class="famt">Rp585.000</span></div>
      <div class="fin-row"><span class="fname">Bendera</span><span class="famt">Rp50.000</span></div>
      <div class="fin-row"><span class="fname">Transport coach (instruktur)</span><span class="famt">Rp150.000</span></div>
    </div>

    <div class="balance-card">
      <div class="bl">Saldo Bulan Ini</div>
      <div class="bv">Rp263.500</div>
      <span class="bs">✓ Surplus</span>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <p>Demikian laporan pertanggungjawaban kegiatan dan rincian keuangan Kampung Lestari Sehat edisi Juli 2026. Terima kasih kepada seluruh kader kesehatan, pengurus RT, dan warga yang telah berpartisipasi.</p>
    <div class="sig-block">
      <div class="sig-loc">Semarang, 20 Juli 2026</div>
      <div class="sig-line">
        Seksi Kepemudaan dan Olahraga<br>Kampung Lestari Sehat (KLS)
        <div class="sig-space"></div>
        (Tanda tangan)
        <b>Koordinator Seksi Kepemudaan &amp; Olahraga</b>
        RT 13 / RW 06, Kelurahan Manyaran
      </div>
    </div>
  </footer>

</div>

<script>
  const els = document.querySelectorAll('.reveal');
  if('IntersectionObserver' in window){
    const io = new IntersectionObserver((entries)=>{
      entries.forEach(e=>{
        if(e.isIntersecting){
          e.target.classList.add('is-visible');
          io.unobserve(e.target);
        }
      });
    },{threshold:0.12});
    els.forEach(el=>io.observe(el));
  } else {
    els.forEach(el=>el.classList.add('is-visible'));
  }
</script>
</body>
</html>
