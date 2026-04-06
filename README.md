<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tahoe Auto Repair Inc.</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  :root {
    --navy: #0d1b2a; --navy2: #162032; --red: #c0392b; --red2: #a93226;
    --silver: #bfc9d1; --light: #f4f6f8; --white: #ffffff;
    --text: #1a2330; --muted: #5a6a7a;
  }
  body { font-family: 'DM Sans', sans-serif; color: var(--text); background: var(--white); }
  a { text-decoration: none; color: inherit; }

  nav { background: var(--navy); display: flex; align-items: center; justify-content: space-between; padding: 0 5%; height: 64px; position: sticky; top: 0; z-index: 100; }
  .logo { font-family: 'Bebas Neue', sans-serif; font-size: 26px; letter-spacing: 2px; color: var(--white); }
  .logo span { color: var(--red); }
  .nav-links { display: flex; gap: 28px; }
  .nav-links a { font-size: 13px; font-weight: 500; letter-spacing: 1px; text-transform: uppercase; color: var(--silver); transition: color .2s; }
  .nav-links a:hover { color: var(--white); }
  .nav-cta { background: var(--red); color: var(--white); font-size: 13px; font-weight: 500; letter-spacing: 1px; text-transform: uppercase; padding: 10px 20px; border-radius: 4px; transition: background .2s; }
  .nav-cta:hover { background: var(--red2); }

  .hero { background: var(--navy); padding: 80px 5% 90px; position: relative; overflow: hidden; }
  .hero::before { content: ''; position: absolute; top: 0; right: 0; width: 50%; height: 100%; background: linear-gradient(135deg, transparent 40%, #c0392b18 100%); pointer-events: none; }
  .hero-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 60px; align-items: center; max-width: 1100px; margin: 0 auto; }
  .hero-eyebrow { font-size: 12px; letter-spacing: 3px; text-transform: uppercase; color: var(--red); font-weight: 500; margin-bottom: 18px; }
  .hero h1 { font-family: 'Bebas Neue', sans-serif; font-size: clamp(48px, 6vw, 80px); line-height: 1; color: var(--white); letter-spacing: 2px; margin-bottom: 22px; }
  .hero h1 em { color: var(--red); font-style: normal; }
  .hero p { font-size: 16px; line-height: 1.7; color: var(--silver); max-width: 420px; margin-bottom: 36px; }
  .hero-btns { display: flex; gap: 14px; flex-wrap: wrap; }
  .btn-primary { background: var(--red); color: var(--white); padding: 14px 28px; border-radius: 4px; font-weight: 500; font-size: 14px; transition: background .2s; display: inline-block; }
  .btn-primary:hover { background: var(--red2); }
  .btn-secondary { border: 1.5px solid var(--silver); color: var(--silver); padding: 13px 28px; border-radius: 4px; font-weight: 500; font-size: 14px; transition: all .2s; display: inline-block; }
  .btn-secondary:hover { border-color: var(--white); color: var(--white); }
  .hero-stats { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  .stat-card { background: #ffffff0d; border: 1px solid #ffffff18; border-radius: 8px; padding: 22px 20px; }
  .stat-card .num { font-family: 'Bebas Neue', sans-serif; font-size: 48px; color: var(--red); letter-spacing: 1px; line-height: 1; }
  .stat-card .label { font-size: 12px; color: var(--silver); letter-spacing: 1px; text-transform: uppercase; margin-top: 4px; }

  .trust-bar { background: var(--red); padding: 14px 5%; display: flex; justify-content: center; gap: 40px; flex-wrap: wrap; }
  .trust-item { color: var(--white); font-size: 13px; font-weight: 500; letter-spacing: .5px; display: flex; align-items: center; gap: 7px; }

  .services-section { padding: 80px 5%; max-width: 1200px; margin: 0 auto; }
  .section-label { font-size: 11px; letter-spacing: 3px; text-transform: uppercase; color: var(--red); font-weight: 500; margin-bottom: 10px; }
  .section-title { font-family: 'Bebas Neue', sans-serif; font-size: clamp(36px, 4vw, 52px); letter-spacing: 1px; color: var(--navy); margin-bottom: 8px; }
  .section-sub { font-size: 15px; color: var(--muted); line-height: 1.6; max-width: 520px; margin-bottom: 48px; }

  .services-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 24px; }
  .service-card { border-radius: 12px; overflow: hidden; border: 1px solid #e2e8ee; transition: transform .25s, box-shadow .25s; cursor: default; background: var(--white); }
  .service-card:hover { transform: translateY(-5px); box-shadow: 0 12px 32px rgba(0,0,0,0.10); }
  .service-img { width: 100%; height: 200px; object-fit: cover; display: block; background: #e2e8ee; }
  .service-body { padding: 22px 20px; }
  .service-tag { display: inline-block; background: #fdecea; color: var(--red); font-size: 11px; font-weight: 500; letter-spacing: 1px; text-transform: uppercase; padding: 4px 10px; border-radius: 4px; margin-bottom: 10px; }
  .service-body h3 { font-size: 17px; font-weight: 500; color: var(--navy); margin-bottom: 8px; }
  .service-body p { font-size: 13px; color: var(--muted); line-height: 1.65; }

  .why-section { background: var(--navy); padding: 80px 5%; }
  .why-inner { max-width: 1100px; margin: 0 auto; display: grid; grid-template-columns: 1fr 1fr; gap: 60px; align-items: start; }
  .why-section .section-label { color: var(--red); }
  .why-section .section-title { color: var(--white); }
  .why-section .section-sub { color: var(--silver); }
  .why-list { display: flex; flex-direction: column; gap: 20px; }
  .why-item { display: flex; gap: 16px; align-items: flex-start; }
  .why-num { font-family: 'Bebas Neue', sans-serif; font-size: 32px; color: var(--red); line-height: 1; min-width: 32px; }
  .why-text h4 { font-size: 15px; font-weight: 500; color: var(--white); margin-bottom: 4px; }
  .why-text p { font-size: 13px; color: var(--silver); line-height: 1.6; }

  .cta-strip { background: var(--red); padding: 56px 5%; text-align: center; }
  .cta-strip h2 { font-family: 'Bebas Neue', sans-serif; font-size: clamp(32px, 4vw, 48px); color: var(--white); letter-spacing: 1px; margin-bottom: 10px; }
  .cta-strip p { color: #ffffff99; font-size: 15px; margin-bottom: 28px; }
  .cta-actions { display: flex; gap: 16px; justify-content: center; flex-wrap: wrap; }
  .btn-white { background: var(--white); color: var(--red); padding: 14px 28px; border-radius: 4px; font-weight: 500; font-size: 14px; transition: background .2s; }
  .btn-white:hover { background: #f0f0f0; }
  .btn-outline-white { border: 1.5px solid var(--white); color: var(--white); padding: 13px 28px; border-radius: 4px; font-weight: 500; font-size: 14px; transition: background .2s; }
  .btn-outline-white:hover { background: #ffffff18; }

  .contact-section { padding: 80px 5%; background: var(--light); }
  .contact-inner { max-width: 1100px; margin: 0 auto; display: grid; grid-template-columns: 1fr 1fr; gap: 60px; align-items: start; }
  .contact-card { background: var(--white); border-radius: 12px; padding: 32px; border: 1px solid #dde3ea; }
  .contact-card h3 { font-family: 'Bebas Neue', sans-serif; font-size: 24px; letter-spacing: 1px; color: var(--navy); margin-bottom: 22px; }
  .info-row { display: flex; gap: 12px; margin-bottom: 16px; align-items: flex-start; }
  .info-icon { font-size: 16px; min-width: 20px; margin-top: 1px; }
  .info-row div { font-size: 14px; line-height: 1.5; }
  .info-label { font-size: 11px; letter-spacing: 1px; text-transform: uppercase; color: var(--muted); font-weight: 500; margin-bottom: 2px; }
  .hours-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 6px; margin-top: 6px; font-size: 13px; }
  .hours-grid .day { color: var(--muted); }
  .hours-grid .time { font-weight: 500; color: var(--navy); }
  .map-placeholder { border-radius: 10px; overflow: hidden; height: 240px; background: #e8ecf0; display: flex; align-items: center; justify-content: center; font-size: 13px; color: var(--muted); border: 1px solid #dde3ea; margin-top: 20px; }

  footer { background: var(--navy); padding: 32px 5%; display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 16px; }
  footer .logo { font-size: 20px; }
  footer p { font-size: 12px; color: var(--silver); }

  @media (max-width: 900px) { .services-grid { grid-template-columns: 1fr 1fr; } }
  @media (max-width: 720px) {
    .hero-grid, .why-inner, .contact-inner { grid-template-columns: 1fr; }
    .nav-links { display: none; }
    .services-grid { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<nav>
  <div class="logo">TAHOE <span>AUTO</span></div>
  <div class="nav-links">
    <a href="#services">Services</a>
    <a href="#why">Why Us</a>
    <a href="#contact">Contact</a>
  </div>
  <a href="tel:2269264129" class="nav-cta">📞 226-926-4129</a>
</nav>

<section class="hero">
  <div class="hero-grid">
    <div>
      <div class="hero-eyebrow">London, ON — Collision & Auto Body</div>
      <h1>Back on the Road.<br><em>Stress-Free.</em></h1>
      <p>From collision repair to precision paint matching, Tahoe Auto Repair handles your claim and your car — so you don't have to worry about a thing.</p>
      <div class="hero-btns">
        <a href="#contact" class="btn-primary">Get a Free Estimate</a>
        <a href="tel:2269264129" class="btn-secondary">📞 Call Now</a>
      </div>
    </div>
    <div class="hero-stats">
      <div class="stat-card"><div class="num">100%</div><div class="label">Insurance Handled</div></div>
      <div class="stat-card"><div class="num">5</div><div class="label">Services Offered</div></div>
      <div class="stat-card"><div class="num">FREE</div><div class="label">Estimates</div></div>
      <div class="stat-card"><div class="num">5★</div><div class="label">Quality Results</div></div>
    </div>
  </div>
</section>

<div class="trust-bar">
  <div class="trust-item">🛡️ Insurance Claims Assistance</div>
  <div class="trust-item">🎨 Precision Colour Matching</div>
  <div class="trust-item">✅ Certified Technicians</div>
  <div class="trust-item">🚗 All Makes & Models</div>
</div>

<div class="services-section" id="services">
  <div class="section-label">What We Do</div>
  <div class="section-title">Our Services</div>
  <p class="section-sub">Complete auto body and mechanical care under one roof, from minor dings to full collision restoration.</p>

  <div class="services-grid">

    <div class="service-card">
      <img class="service-img" src="https://images.unsplash.com/photo-1625047509168-a7026f36de04?w=600&q=80&fit=crop" alt="Auto body collision repair" onerror="this.style.background='#dde3ea';this.removeAttribute('src')">
      <div class="service-body">
        <div class="service-tag">Body Work</div>
        <h3>Auto Body Repair</h3>
        <p>Complete collision restoration — we work directly with all major insurance providers to get you back on the road fast.</p>
      </div>
    </div>

    <div class="service-card">
      <img class="service-img" src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=600&q=80&fit=crop" alt="Auto paint and dent repair" onerror="this.style.background='#dde3ea';this.removeAttribute('src')">
      <div class="service-body">
        <div class="service-tag">Paint & Dent</div>
        <h3>Paint & Dent Repair</h3>
        <p>Precision colour matching and paintless dent removal for a finish that looks and feels factory-new.</p>
      </div>
    </div>

    <div class="service-card">
      <img class="service-img" src="https://images.unsplash.com/photo-1504222490345-c075b626c84b?w=600&q=80&fit=crop" alt="Mechanic automotive repair" onerror="this.style.background='#dde3ea';this.removeAttribute('src')">
      <div class="service-body">
        <div class="service-tag">Mechanical</div>
        <h3>Mechanic Services</h3>
        <p>General automotive repairs and routine maintenance by certified technicians to keep your vehicle running right.</p>
      </div>
    </div>

    <div class="service-card">
      <img class="service-img" src="https://images.unsplash.com/photo-1507136566006-cfc505b114fc?w=600&q=80&fit=crop" alt="Professional car detailing" onerror="this.style.background='#dde3ea';this.removeAttribute('src')">
      <div class="service-body">
        <div class="service-tag">Detailing</div>
        <h3>Detailing</h3>
        <p>Professional interior and exterior cleaning that restores your car's showroom shine — inside and out.</p>
      </div>
    </div>

    <div class="service-card">
      <img class="service-img" src="https://images.unsplash.com/photo-1593786081892-8b40a2c548fa?w=600&q=80&fit=crop" alt="Windshield repair and replacement" onerror="this.style.background='#dde3ea';this.removeAttribute('src')">
      <div class="service-body">
        <div class="service-tag">Glass</div>
        <h3>Windshield Repair</h3>
        <p>Fast glass chip and crack restoration by experienced technicians — often completed same-day.</p>
      </div>
    </div>

  </div>
</div>

<div class="why-section" id="why">
  <div class="why-inner">
    <div>
      <div class="section-label">Why Tahoe</div>
      <div class="section-title">We Make It Easy</div>
      <p class="section-sub">Dealing with a damaged car is stressful enough. We handle the hard parts so you can focus on what matters.</p>
    </div>
    <div class="why-list">
      <div class="why-item"><div class="why-num">01</div><div class="why-text"><h4>Insurance handled for you</h4><p>We communicate directly with your insurer and handle the paperwork on your behalf.</p></div></div>
      <div class="why-item"><div class="why-num">02</div><div class="why-text"><h4>Free, no-obligation estimates</h4><p>Bring your car in or call — we'll give you an honest assessment at no cost.</p></div></div>
      <div class="why-item"><div class="why-num">03</div><div class="why-text"><h4>All services under one roof</h4><p>Body work, paint, glass, mechanics, and detailing — no need to visit multiple shops.</p></div></div>
      <div class="why-item"><div class="why-num">04</div><div class="why-text"><h4>Quality that lasts</h4><p>Certified technicians and top-grade materials mean results you can trust for years.</p></div></div>
    </div>
  </div>
</div>

<div class="cta-strip">
  <h2>Ready to Get Your Car Fixed?</h2>
  <p>Free estimates — no commitment required. We'll take it from there.</p>
  <div class="cta-actions">
    <a href="mailto:tahoe.inc8@gmail.com" class="btn-white">Email for a Free Estimate</a>
    <a href="tel:2269264129" class="btn-outline-white">📞 226-926-4129</a>
  </div>
</div>

<div class="contact-section" id="contact">
  <div class="contact-inner">
    <div>
      <div class="section-label">Find Us</div>
      <div class="section-title">Contact & Hours</div>
      <p class="section-sub">Drop by, give us a call, or send an email — we're here Monday to Friday to help.</p>
      <div class="map-placeholder">📍 126 Clarke Rd Units 7&8, London, ON N5W 5E1</div>
    </div>
    <div class="contact-card">
      <h3>Get In Touch</h3>
      <div class="info-row">
        <div class="info-icon">📍</div>
        <div><div class="info-label">Address</div>126 Clarke Rd, Units 7 &amp; 8<br>London, ON N5W 5E1</div>
      </div>
      <div class="info-row">
        <div class="info-icon">📞</div>
        <div><div class="info-label">Phone</div><a href="tel:2269264129" style="color:var(--red);font-weight:500;">226-926-4129</a></div>
      </div>
      <div class="info-row">
        <div class="info-icon">✉️</div>
        <div><div class="info-label">Email</div><a href="mailto:tahoe.inc8@gmail.com" style="color:var(--red);font-weight:500;">tahoe.inc8@gmail.com</a></div>
      </div>
      <div class="info-row">
        <div class="info-icon">🕘</div>
        <div>
          <div class="info-label">Hours</div>
          <div class="hours-grid">
            <span class="day">Monday – Friday</span><span class="time">9:00 AM – 5:00 PM</span>
            <span class="day">Saturday – Sunday</span><span class="time">Closed</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<footer>
  <div class="logo">TAHOE <span>AUTO</span></div>
  <p>© 2025 Tahoe Auto Repair Inc. · 126 Clarke Rd, London, ON</p>
  <p>226-926-4129</p>
</footer>

</body>
</html>
