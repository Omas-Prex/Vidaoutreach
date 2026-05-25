<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vida Outreach Management</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
–ink: #0f0e0c;
–cream: #f5f0e8;
–warm: #e8dfc8;
–gold: #b8922a;
–gold-light: #d4aa4a;
–muted: #6b6355;
–rule: #c9bea8;
}

html { scroll-behavior: smooth; }

body {
background: var(–cream);
color: var(–ink);
font-family: ‘DM Sans’, sans-serif;
font-weight: 300;
overflow-x: hidden;
}

/* NAV */
nav {
position: fixed; top: 0; left: 0; right: 0; z-index: 100;
display: flex; align-items: center; justify-content: space-between;
padding: 1.4rem 5vw;
background: rgba(245,240,232,0.92);
backdrop-filter: blur(12px);
border-bottom: 1px solid var(–rule);
}
.nav-logo {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.1rem;
font-weight: 600;
letter-spacing: 0.12em;
text-transform: uppercase;
color: var(–ink);
text-decoration: none;
}
.nav-logo span { color: var(–gold); }
nav a.nav-link {
font-size: 0.78rem;
letter-spacing: 0.1em;
text-transform: uppercase;
color: var(–muted);
text-decoration: none;
transition: color 0.2s;
}
nav a.nav-link:hover { color: var(–gold); }
.nav-links { display: flex; gap: 2.5rem; align-items: center; }
.nav-cta {
font-size: 0.75rem;
letter-spacing: 0.1em;
text-transform: uppercase;
background: var(–ink);
color: var(–cream) !important;
padding: 0.6rem 1.4rem;
text-decoration: none;
transition: background 0.2s;
}
.nav-cta:hover { background: var(–gold) !important; color: var(–cream) !important; }

/* HERO */
.hero {
min-height: 100vh;
display: grid;
grid-template-columns: 1fr 1fr;
position: relative;
overflow: hidden;
}
.hero-left {
padding: 12rem 5vw 6rem 8vw;
display: flex;
flex-direction: column;
justify-content: center;
position: relative;
z-index: 2;
}
.hero-eyebrow {
font-size: 0.72rem;
letter-spacing: 0.22em;
text-transform: uppercase;
color: var(–gold);
margin-bottom: 1.8rem;
display: flex;
align-items: center;
gap: 0.8rem;
}
.hero-eyebrow::before {
content: ‘’;
display: block;
width: 2rem;
height: 1px;
background: var(–gold);
}
h1 {
font-family: ‘Cormorant Garamond’, serif;
font-size: clamp(3rem, 5vw, 5.2rem);
font-weight: 300;
line-height: 1.08;
letter-spacing: -0.01em;
margin-bottom: 2rem;
color: var(–ink);
}
h1 em {
font-style: italic;
color: var(–gold);
}
.hero-sub {
font-size: 1.05rem;
line-height: 1.75;
color: var(–muted);
max-width: 42ch;
margin-bottom: 3rem;
}
.hero-actions {
display: flex;
gap: 1rem;
flex-wrap: wrap;
}
.btn-primary {
display: inline-block;
background: var(–ink);
color: var(–cream);
font-size: 0.78rem;
letter-spacing: 0.12em;
text-transform: uppercase;
padding: 1rem 2.2rem;
text-decoration: none;
transition: background 0.25s;
font-family: ‘DM Sans’, sans-serif;
border: none; cursor: pointer;
}
.btn-primary:hover { background: var(–gold); }
.btn-ghost {
display: inline-block;
border: 1px solid var(–rule);
color: var(–muted);
font-size: 0.78rem;
letter-spacing: 0.12em;
text-transform: uppercase;
padding: 1rem 2.2rem;
text-decoration: none;
transition: border-color 0.25s, color 0.25s;
font-family: ‘DM Sans’, sans-serif;
}
.btn-ghost:hover { border-color: var(–gold); color: var(–gold); }

.hero-right {
position: relative;
overflow: hidden;
}
.hero-right::before {
content: ‘’;
position: absolute; inset: 0;
background: linear-gradient(135deg, #2a2018 0%, #1a150d 60%, #0f0e0c 100%);
}
.hero-pattern {
position: absolute; inset: 0;
background-image:
repeating-linear-gradient(0deg, transparent, transparent 60px, rgba(184,146,42,0.06) 60px, rgba(184,146,42,0.06) 61px),
repeating-linear-gradient(90deg, transparent, transparent 60px, rgba(184,146,42,0.06) 60px, rgba(184,146,42,0.06) 61px);
}
.hero-quote {
position: absolute;
bottom: 3rem; left: 3rem; right: 3rem;
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.5rem;
font-style: italic;
font-weight: 300;
color: rgba(245,240,232,0.85);
line-height: 1.5;
border-left: 2px solid var(–gold);
padding-left: 1.5rem;
}
.hero-quote cite {
display: block;
margin-top: 1rem;
font-size: 0.72rem;
letter-spacing: 0.15em;
text-transform: uppercase;
font-style: normal;
color: var(–gold-light);
font-family: ‘DM Sans’, sans-serif;
}
.hero-stat-strip {
position: absolute;
top: 50%;
transform: translateY(-50%);
right: 3rem;
display: flex;
flex-direction: column;
gap: 2.5rem;
}
.hero-stat { text-align: right; }
.hero-stat .num {
font-family: ‘Cormorant Garamond’, serif;
font-size: 2.8rem;
font-weight: 300;
color: var(–gold-light);
line-height: 1;
}
.hero-stat .label {
font-size: 0.65rem;
letter-spacing: 0.15em;
text-transform: uppercase;
color: rgba(245,240,232,0.4);
margin-top: 0.25rem;
}

/* DIVIDER */
.section-divider {
display: flex;
align-items: center;
gap: 1.5rem;
padding: 0 8vw;
margin: 5rem 0 0;
}
.section-divider::before, .section-divider::after {
content: ‘’; flex: 1; height: 1px; background: var(–rule);
}
.divider-label {
font-size: 0.68rem;
letter-spacing: 0.2em;
text-transform: uppercase;
color: var(–muted);
white-space: nowrap;
}

/* WHO WE SERVE */
.who-section {
padding: 6rem 8vw;
}
.section-header {
margin-bottom: 4rem;
}
.section-tag {
font-size: 0.7rem;
letter-spacing: 0.2em;
text-transform: uppercase;
color: var(–gold);
margin-bottom: 1rem;
}
h2 {
font-family: ‘Cormorant Garamond’, serif;
font-size: clamp(2rem, 3.5vw, 3.2rem);
font-weight: 300;
line-height: 1.12;
color: var(–ink);
max-width: 20ch;
}
h2 em { font-style: italic; color: var(–gold); }

.who-grid {
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 0;
border: 1px solid var(–rule);
}
.who-card {
padding: 2.5rem 2rem;
border-right: 1px solid var(–rule);
transition: background 0.3s;
position: relative;
}
.who-card:last-child { border-right: none; }
.who-card:hover { background: var(–warm); }
.who-icon {
font-size: 1.8rem;
margin-bottom: 1.2rem;
display: block;
}
.who-title {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.35rem;
font-weight: 600;
margin-bottom: 0.8rem;
color: var(–ink);
}
.who-desc {
font-size: 0.88rem;
line-height: 1.7;
color: var(–muted);
}

/* HOW IT WORKS */
.how-section {
background: var(–ink);
color: var(–cream);
padding: 7rem 8vw;
}
.how-section .section-tag { color: var(–gold-light); }
.how-section h2 { color: var(–cream); }

.how-steps {
display: grid;
grid-template-columns: repeat(4, 1fr);
gap: 0;
margin-top: 4rem;
border-top: 1px solid rgba(255,255,255,0.1);
}
.how-step {
padding: 3rem 2rem 2rem;
border-right: 1px solid rgba(255,255,255,0.1);
position: relative;
}
.how-step:last-child { border-right: none; }
.step-num {
font-family: ‘Cormorant Garamond’, serif;
font-size: 4rem;
font-weight: 300;
color: rgba(184,146,42,0.2);
line-height: 1;
margin-bottom: 1.5rem;
}
.step-title {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.25rem;
font-weight: 600;
color: var(–cream);
margin-bottom: 0.8rem;
}
.step-desc {
font-size: 0.85rem;
line-height: 1.7;
color: rgba(245,240,232,0.55);
}

/* SERVICES */
.services-section {
padding: 7rem 8vw;
display: grid;
grid-template-columns: 1fr 1.6fr;
gap: 6rem;
align-items: start;
}
.services-intro { position: sticky; top: 7rem; }
.services-intro p {
font-size: 0.95rem;
line-height: 1.8;
color: var(–muted);
margin-top: 1.5rem;
}

.service-list { display: flex; flex-direction: column; }
.service-item {
padding: 2.2rem 0;
border-bottom: 1px solid var(–rule);
display: grid;
grid-template-columns: auto 1fr;
gap: 2rem;
align-items: start;
cursor: default;
transition: background 0.2s;
}
.service-item:first-child { border-top: 1px solid var(–rule); }
.service-num {
font-family: ‘Cormorant Garamond’, serif;
font-size: 0.85rem;
font-weight: 600;
color: var(–gold);
padding-top: 0.3rem;
letter-spacing: 0.05em;
}
.service-name {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.4rem;
font-weight: 600;
margin-bottom: 0.5rem;
color: var(–ink);
}
.service-desc {
font-size: 0.87rem;
line-height: 1.7;
color: var(–muted);
}
.service-tags {
display: flex;
flex-wrap: wrap;
gap: 0.4rem;
margin-top: 0.8rem;
}
.tag {
font-size: 0.68rem;
letter-spacing: 0.1em;
text-transform: uppercase;
background: var(–warm);
color: var(–muted);
padding: 0.3rem 0.7rem;
}

/* DISCRETION */
.discretion-section {
background: var(–warm);
padding: 6rem 8vw;
display: grid;
grid-template-columns: 1fr 1fr;
gap: 6rem;
align-items: center;
}
.discretion-text h2 { max-width: none; }
.discretion-text p {
font-size: 0.95rem;
line-height: 1.85;
color: var(–muted);
margin-top: 1.5rem;
}
.discretion-pillars {
display: grid;
grid-template-columns: 1fr 1fr;
gap: 1.5rem;
margin-top: 2.5rem;
}
.pillar {
padding: 1.5rem;
background: var(–cream);
border-left: 2px solid var(–gold);
}
.pillar-name {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.1rem;
font-weight: 600;
margin-bottom: 0.4rem;
}
.pillar-desc {
font-size: 0.8rem;
line-height: 1.6;
color: var(–muted);
}

.discretion-visual {
position: relative;
height: 420px;
background: var(–ink);
overflow: hidden;
}
.discretion-visual::before {
content: ‘’;
position: absolute; inset: 0;
background:
radial-gradient(ellipse at 70% 30%, rgba(184,146,42,0.15) 0%, transparent 60%),
radial-gradient(ellipse at 20% 80%, rgba(184,146,42,0.08) 0%, transparent 50%);
}
.disc-inner {
position: absolute; inset: 0;
display: flex;
align-items: center;
justify-content: center;
flex-direction: column;
gap: 0.5rem;
}
.disc-ring {
width: 180px; height: 180px;
border-radius: 50%;
border: 1px solid rgba(184,146,42,0.3);
display: flex;
align-items: center;
justify-content: center;
position: relative;
}
.disc-ring::before {
content: ‘’;
position: absolute;
inset: 12px;
border-radius: 50%;
border: 1px solid rgba(184,146,42,0.15);
}
.disc-text {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1rem;
font-style: italic;
color: var(–gold-light);
text-align: center;
padding: 0 1.5rem;
}
.disc-caption {
font-size: 0.65rem;
letter-spacing: 0.2em;
text-transform: uppercase;
color: rgba(245,240,232,0.3);
margin-top: 1rem;
}

/* CONTACT */
.contact-section {
padding: 7rem 8vw;
display: grid;
grid-template-columns: 1fr 1.2fr;
gap: 6rem;
align-items: start;
}
.contact-intro p {
font-size: 0.95rem;
line-height: 1.85;
color: var(–muted);
margin-top: 1.5rem;
margin-bottom: 2rem;
}
.contact-detail {
display: flex;
align-items: flex-start;
gap: 1rem;
margin-bottom: 1.2rem;
}
.cd-label {
font-size: 0.7rem;
letter-spacing: 0.15em;
text-transform: uppercase;
color: var(–gold);
width: 5rem;
flex-shrink: 0;
padding-top: 0.1rem;
}
.cd-val {
font-size: 0.9rem;
color: var(–ink);
}

.contact-form { display: flex; flex-direction: column; gap: 1.2rem; }
.form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1.2rem; }
.form-field { display: flex; flex-direction: column; gap: 0.4rem; }
.form-field label {
font-size: 0.68rem;
letter-spacing: 0.15em;
text-transform: uppercase;
color: var(–muted);
}
.form-field input, .form-field select, .form-field textarea {
font-family: ‘DM Sans’, sans-serif;
font-size: 0.9rem;
font-weight: 300;
background: transparent;
border: none;
border-bottom: 1px solid var(–rule);
padding: 0.7rem 0;
color: var(–ink);
outline: none;
transition: border-color 0.2s;
-webkit-appearance: none;
appearance: none;
}
.form-field input:focus, .form-field select:focus, .form-field textarea:focus {
border-bottom-color: var(–gold);
}
.form-field textarea { resize: vertical; min-height: 90px; }
.form-field select { cursor: pointer; background-color: var(–cream); }
.form-note {
font-size: 0.78rem;
color: var(–muted);
line-height: 1.6;
}

/* FOOTER */
footer {
background: var(–ink);
color: rgba(245,240,232,0.5);
padding: 3rem 8vw;
display: flex;
align-items: center;
justify-content: space-between;
flex-wrap: wrap;
gap: 1rem;
}
.footer-logo {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1rem;
font-weight: 600;
letter-spacing: 0.1em;
text-transform: uppercase;
color: var(–cream);
text-decoration: none;
}
.footer-logo span { color: var(–gold); }
.footer-copy { font-size: 0.75rem; }
.footer-tagline {
font-family: ‘Cormorant Garamond’, serif;
font-style: italic;
font-size: 0.9rem;
color: rgba(245,240,232,0.35);
}

/* VALUES SECTION */
.values-section {
background: var(–ink);
padding: 7rem 8vw;
}
.values-section .section-tag { color: var(–gold-light); }
.values-section h2 { color: var(–cream); margin-bottom: 1.2rem; }
.values-lead {
font-size: 1rem;
line-height: 1.85;
color: rgba(245,240,232,0.5);
max-width: 58ch;
margin-bottom: 5rem;
}
.values-grid {
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 0;
border-top: 1px solid rgba(255,255,255,0.08);
}
.value-card {
padding: 3.5rem 2.5rem 3rem;
border-right: 1px solid rgba(255,255,255,0.08);
position: relative;
}
.value-card:last-child { border-right: none; }
.value-glyph {
font-family: ‘Cormorant Garamond’, serif;
font-size: 5rem;
font-weight: 300;
color: rgba(184,146,42,0.12);
line-height: 1;
position: absolute;
top: 2rem;
right: 2rem;
pointer-events: none;
user-select: none;
}
.value-icon {
width: 2.8rem;
height: 2.8rem;
border: 1px solid rgba(184,146,42,0.35);
display: flex;
align-items: center;
justify-content: center;
margin-bottom: 2rem;
font-size: 1.1rem;
}
.value-name {
font-family: ‘Cormorant Garamond’, serif;
font-size: 2rem;
font-weight: 600;
color: var(–cream);
margin-bottom: 1rem;
letter-spacing: -0.01em;
}
.value-name em {
display: block;
font-style: italic;
color: var(–gold-light);
font-size: 1rem;
font-weight: 300;
letter-spacing: 0.05em;
margin-top: 0.2rem;
}
.value-desc {
font-size: 0.88rem;
line-height: 1.85;
color: rgba(245,240,232,0.5);
margin-bottom: 1.5rem;
}
.value-principles {
list-style: none;
display: flex;
flex-direction: column;
gap: 0.5rem;
}
.value-principles li {
font-size: 0.75rem;
letter-spacing: 0.08em;
text-transform: uppercase;
color: var(–gold-light);
display: flex;
align-items: center;
gap: 0.6rem;
opacity: 0.7;
}
.value-principles li::before {
content: ‘’;
display: block;
width: 1.2rem;
height: 1px;
background: var(–gold);
flex-shrink: 0;
}
@media (max-width: 900px) {
.values-grid { grid-template-columns: 1fr; }
.value-card { border-right: none; border-bottom: 1px solid rgba(255,255,255,0.08); }
.value-card:last-child { border-bottom: none; }
}

/* CASE REFERENCES */
.cases-section {
padding: 6rem 8vw;
background: var(–cream);
}
.cases-grid {
display: grid;
grid-template-columns: 1fr 1fr;
gap: 0;
border: 1px solid var(–rule);
}
.case-card {
padding: 2.5rem 2.2rem;
border-right: 1px solid var(–rule);
border-bottom: 1px solid var(–rule);
display: grid;
grid-template-columns: auto 1fr;
gap: 1.5rem;
transition: background 0.25s;
}
.case-card:nth-child(2n) { border-right: none; }
.case-card:nth-child(3), .case-card:nth-child(4) { border-bottom: none; }
.case-card:hover { background: var(–warm); }
.case-num {
font-family: ‘Cormorant Garamond’, serif;
font-size: 2.2rem;
font-weight: 300;
color: rgba(184,146,42,0.25);
line-height: 1;
padding-top: 0.2rem;
}
.case-type {
font-size: 0.68rem;
letter-spacing: 0.15em;
text-transform: uppercase;
color: var(–gold);
margin-bottom: 0.7rem;
}
.case-summary {
font-size: 0.9rem;
line-height: 1.75;
color: var(–muted);
margin-bottom: 1rem;
}
@media (max-width: 900px) {
.cases-grid { grid-template-columns: 1fr; }
.case-card { border-right: none; border-bottom: 1px solid var(–rule); }
.case-card:last-child { border-bottom: none; }
}

/* ANIMATIONS */
@keyframes fadeUp {
from { opacity: 0; transform: translateY(24px); }
to { opacity: 1; transform: translateY(0); }
}
.hero-eyebrow { animation: fadeUp 0.6s ease 0.1s both; }
h1 { animation: fadeUp 0.7s ease 0.25s both; }
.hero-sub { animation: fadeUp 0.7s ease 0.4s both; }
.hero-actions { animation: fadeUp 0.7s ease 0.55s both; }

/* RESPONSIVE */
@media (max-width: 900px) {
.hero { grid-template-columns: 1fr; }
.hero-right { display: none; }
.hero-left { padding: 9rem 6vw 5rem; }
.who-grid { grid-template-columns: 1fr; }
.who-card { border-right: none; border-bottom: 1px solid var(–rule); }
.how-steps { grid-template-columns: 1fr 1fr; }
.how-step { border-bottom: 1px solid rgba(255,255,255,0.1); }
.services-section { grid-template-columns: 1fr; gap: 3rem; }
.services-intro { position: static; }
.discretion-section { grid-template-columns: 1fr; }
.discretion-visual { display: none; }
.contact-section { grid-template-columns: 1fr; gap: 3rem; }
.form-row { grid-template-columns: 1fr; }
nav .nav-links { display: none; }
}
</style>

</head>
<body>

<!-- NAV -->

<nav>
  <a href="#" class="nav-logo">Vida Outreach<span>.</span></a>
  <div class="nav-links">
    <a href="#services" class="nav-link">Services</a>
    <a href="#how" class="nav-link">How It Works</a>
    <a href="#contact" class="nav-link">Contact</a>
    <a href="#contact" class="nav-link nav-cta">Start an Engagement</a>
  </div>
</nav>

<!-- HERO -->

<section class="hero">
  <div class="hero-left">
    <div class="hero-eyebrow">Vida Outreach Management</div>
    <h1>Giving that <em>reaches</em> who it must.</h1>
    <p class="hero-sub">We plan, manage, and execute social and humanitarian outreach on behalf of individuals, organisations, and diaspora donors — with precision, dignity, and full discretion.</p>
    <div class="hero-actions">
      <a href="#contact" class="btn-primary">Start a Conversation</a>
      <a href="#services" class="btn-ghost">Our Services</a>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-pattern"></div>
    <div class="hero-stat-strip">
      <div class="hero-stat">
        <div class="num">10+</div>
        <div class="label">Outreaches executed</div>
      </div>
      <div class="hero-stat">
        <div class="num">100%</div>
        <div class="label">Delivery record</div>
      </div>
      <div class="hero-stat">
        <div class="num">0</div>
        <div class="label">Bureaucratic delays</div>
      </div>
    </div>
    <div class="hero-quote">
      "Every act of genuine giving deserves to arrive with its full dignity intact."
      <cite>— Vida Outreach Management</cite>
    </div>
  </div>
</section>

<!-- WHO WE SERVE -->

<div class="section-divider"><span class="divider-label">Who We Serve</span></div>
<section class="who-section">
  <div class="section-header">
    <div class="section-tag">Our Clients</div>
    <h2>Built for those who want to <em>do good</em> — right.</h2>
  </div>
  <div class="who-grid">
    <div class="who-card">
      <span class="who-icon">🏛️</span>
      <div class="who-title">Public Officials & Politicians</div>
      <p class="who-desc">Reach your constituency on merit, without bureaucratic gatekeeping. We execute on your mandate — transparently or anonymously, your choice.</p>
    </div>
    <div class="who-card">
      <span class="who-icon">🌍</span>
      <div class="who-title">Diaspora Donors</div>
      <p class="who-desc">Send impact home. Whether you're in London, Houston, or Dubai — we are your trusted feet on the ground, handling everything end-to-end.</p>
    </div>
    <div class="who-card">
      <span class="who-icon">🤲</span>
      <div class="who-title">Individuals & Organisations</div>
      <p class="who-desc">Private givers, faith communities, NGOs, and corporations who need a specialist team to execute outreach with accountability and care.</p>
    </div>
  </div>
</section>

<!-- HOW IT WORKS -->

<section class="how-section" id="how">
  <div class="section-header">
    <div class="section-tag">Our Process</div>
    <h2>From brief to <em>impact</em> — with nothing lost.</h2>
  </div>
  <div class="how-steps">
    <div class="how-step">
      <div class="step-num">01</div>
      <div class="step-title">Brief & Scope</div>
      <p class="step-desc">You share your goals, budget, timeline, and the community to be served. We listen deeply and ask the right questions.</p>
    </div>
    <div class="how-step">
      <div class="step-num">02</div>
      <div class="step-title">Plan & Verify</div>
      <p class="step-desc">We research the beneficiary group, establish need verification, and design an execution plan with zero waste and full accountability.</p>
    </div>
    <div class="how-step">
      <div class="step-num">03</div>
      <div class="step-title">Execute</div>
      <p class="step-desc">Our team coordinates all logistics, procurement, personnel, and on-ground presence. You stay informed at every stage.</p>
    </div>
    <div class="how-step">
      <div class="step-num">04</div>
      <div class="step-title">Report & Verify</div>
      <p class="step-desc">Full documentation: photos, beneficiary counts, distribution records, and a post-engagement impact report delivered to you.</p>
    </div>
  </div>
</section>

<!-- SERVICES -->

<section class="services-section" id="services">
  <div class="services-intro">
    <div class="section-tag">Services</div>
    <h2>Every<em> form</em> of giving, handled.</h2>
    <p>We specialise in dignified, accountable outreach — regardless of scale, geography, or how visible you want to be.</p>
  </div>
  <div class="service-list">
    <div class="service-item">
      <div class="service-num">01</div>
      <div>
        <div class="service-name">Community Outreach Execution</div>
        <p class="service-desc">Full-scale outreach events for orphanages, widows, IDPs, and underserved communities — planned and executed to your brief.</p>
        <div class="service-tags"><span class="tag">Food relief</span><span class="tag">Welfare packs</span><span class="tag">Medical outreach</span></div>
      </div>
    </div>
    <div class="service-item">
      <div class="service-num">02</div>
      <div>
        <div class="service-name">Anonymous Giving Management</div>
        <p class="service-desc">Your identity is fully protected. We execute under our operational cover — beneficiaries receive with dignity, donors remain private.</p>
        <div class="service-tags"><span class="tag">Identity shielded</span><span class="tag">No media coverage</span><span class="tag">Full documentation</span></div>
      </div>
    </div>
    <div class="service-item">
      <div class="service-num">03</div>
      <div>
        <div class="service-name">Diaspora Remote Giving</div>
        <p class="service-desc">Send resources home from anywhere in the world. We are your verified, trusted on-ground partner — handling procurement, delivery, and proof.</p>
        <div class="service-tags"><span class="tag">International donors</span><span class="tag">Currency handling</span><span class="tag">Impact reports</span></div>
      </div>
    </div>
    <div class="service-item">
      <div class="service-num">04</div>
      <div>
        <div class="service-name">Organisational Outreach Programs</div>
        <p class="service-desc">CSR programs, faith-community outreaches, NGO delivery support — we integrate with your mandate and execute at scale.</p>
        <div class="service-tags"><span class="tag">CSR</span><span class="tag">Faith orgs</span><span class="tag">NGO support</span></div>
      </div>
    </div>
    <div class="service-item">
      <div class="service-num">05</div>
      <div>
        <div class="service-name">Political & Public-Sector Outreach</div>
        <p class="service-desc">Merit-based, transparent constituency outreach with no middlemen. Delivered cleanly, documented properly, and tied to outcomes — not optics.</p>
        <div class="service-tags"><span class="tag">Constituency delivery</span><span class="tag">Accountability reports</span><span class="tag">Public or private</span></div>
      </div>
    </div>
  </div>
</section>

<!-- DISCRETION -->

<section class="discretion-section">
  <div class="discretion-text">
    <div class="section-tag">Trust & Discretion</div>
    <h2>Some giving should <em>never</em> become noise.</h2>
    <p>We understand that not every act of generosity needs an audience. Our confidentiality framework means your identity, your intent, and your resources are handled with the same care as the outreach itself.</p>
    <div class="discretion-pillars">
      <div class="pillar">
        <div class="pillar-name">Identity Shield</div>
        <p class="pillar-desc">Client identity is never disclosed to beneficiaries, media, or third parties without explicit consent.</p>
      </div>
      <div class="pillar">
        <div class="pillar-name">Clean Chain</div>
        <p class="pillar-desc">Resources flow through verified channels with full documentation — no leakage, no diversion.</p>
      </div>
      <div class="pillar">
        <div class="pillar-name">No Political Noise</div>
        <p class="pillar-desc">Outreach is need-led, not optics-led. We don't allow merit engagements to become campaign material unless you say so.</p>
      </div>
      <div class="pillar">
        <div class="pillar-name">Verified Impact</div>
        <p class="pillar-desc">Every engagement is documented with beneficiary records, distribution logs, and photographic evidence.</p>
      </div>
    </div>
  </div>
  <div class="discretion-visual">
    <div class="hero-pattern"></div>
    <div class="disc-inner">
      <div class="disc-ring">
        <div class="disc-text">Trusted with what matters most</div>
      </div>
      <div class="disc-caption">Vida Outreach Confidentiality Standard</div>
    </div>
  </div>
</section>

<!-- VALUES -->

<section class="values-section">
  <div class="section-header">
    <div class="section-tag">What We Stand On</div>
    <h2>Three values. <em>No exceptions.</em></h2>
    <p class="values-lead">Every outreach we touch is governed by the same three principles — from the first brief to the final report. They are not aspirational. They are operational.</p>
  </div>
  <div class="values-grid">
    <div class="value-card">
      <div class="value-glyph">I</div>
      <div class="value-icon">⚖️</div>
      <div class="value-name">Integrity<em>Doing what is right, always</em></div>
      <p class="value-desc">Every resource entrusted to us is handled with absolute transparency. We do not cut corners, inflate costs, or misrepresent impact. What we say happened — happened.</p>
      <ul class="value-principles">
        <li>Full financial accountability</li>
        <li>No diversion of resources</li>
        <li>Honest reporting, every time</li>
      </ul>
    </div>
    <div class="value-card">
      <div class="value-glyph">E</div>
      <div class="value-icon">🏆</div>
      <div class="value-name">Excellence<em>Delivering beyond the brief</em></div>
      <p class="value-desc">We treat every engagement — regardless of budget — as if it is our most important one. Our planning is meticulous, our execution clean, and our standard the same whether the client is a local church or an international NGO.</p>
      <ul class="value-principles">
        <li>Rigorous pre-engagement planning</li>
        <li>On-time, on-brief delivery</li>
        <li>Quality over convenience</li>
      </ul>
    </div>
    <div class="value-card">
      <div class="value-glyph">C</div>
      <div class="value-icon">🤝</div>
      <div class="value-name">Community<em>The people are the mission</em></div>
      <p class="value-desc">We do not see beneficiaries as recipients — we see them as people with dignity. Every outreach is designed to serve with respect, not spectacle. The community is not a backdrop. They are the reason.</p>
      <ul class="value-principles">
        <li>Dignity-centred delivery</li>
        <li>Need-led, not optics-led</li>
        <li>Long-term community thinking</li>
      </ul>
    </div>
  </div>
</section>

<!-- CASE REFERENCES -->

<section class="cases-section">
  <div class="section-divider" style="padding:0;margin:0 0 4rem;"><span class="divider-label">Selected Past Engagements</span></div>
  <div class="cases-grid">
    <div class="case-card">
      <div class="case-num">01</div>
      <div class="case-body">
        <div class="case-type">Faith-Based Organisation · Nigeria</div>
        <p class="case-summary">Food and welfare packages delivered to over 40 needy families in a rural community in Sapele, Delta State — coordinated end-to-end on behalf of a local faith-based organisation.</p>
        <div class="case-tags"><span class="tag">Food relief</span><span class="tag">Welfare packages</span><span class="tag">Rural community</span></div>
      </div>
    </div>
    <div class="case-card">
      <div class="case-num">02</div>
      <div class="case-body">
        <div class="case-type">Anonymous Client · Accra, Ghana</div>
        <p class="case-summary">Orphanage welfare and food packages outreach executed across multiple client-selected locations in Delta State — fully anonymous, fully documented.</p>
        <div class="case-tags"><span class="tag">Orphanage outreach</span><span class="tag">Anonymous giving</span><span class="tag">Multi-location</span></div>
      </div>
    </div>
    <div class="case-card">
      <div class="case-num">03</div>
      <div class="case-body">
        <div class="case-type">Anonymous Client · Ireland</div>
        <p class="case-summary">Christmas welfare and food packages outreach delivered on behalf of a diaspora donor in Ireland — remote brief, full ground execution, zero client exposure.</p>
        <div class="case-tags"><span class="tag">Diaspora giving</span><span class="tag">Seasonal outreach</span><span class="tag">Anonymous</span></div>
      </div>
    </div>
    <div class="case-card">
      <div class="case-num">04</div>
      <div class="case-body">
        <div class="case-type">International NGO · Nigeria</div>
        <p class="case-summary">Farming equipment and seedlings delivered to over 20 indigenous farmers in Obiaruku, Delta State — procurement, logistics, and verified beneficiary distribution handled in full.</p>
        <div class="case-tags"><span class="tag">Agricultural support</span><span class="tag">NGO delivery</span><span class="tag">Verified impact</span></div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->

<section class="contact-section" id="contact">
  <div class="contact-intro">
    <div class="section-tag">Get In Touch</div>
    <h2>Begin your <em>engagement.</em></h2>
    <p>Every engagement starts with a private conversation. Share your intention and we will respond within 24 hours with a tailored proposal approach.</p>
    <div class="contact-detail">
      <span class="cd-label">Email</span>
      <span class="cd-val">hello@vidaoutreach.org</span>
    </div>
    <div class="contact-detail">
      <span class="cd-label">Reach</span>
      <span class="cd-val">Nigeria · UK · USA · Diaspora-wide</span>
    </div>
    <div class="contact-detail">
      <span class="cd-label">Response</span>
      <span class="cd-val">Within 24 hours, confidentially</span>
    </div>
  </div>
  <div class="contact-form">
    <div class="form-row">
      <div class="form-field">
        <label>Your Name</label>
        <input type="text" placeholder="Full name">
      </div>
      <div class="form-field">
        <label>Email</label>
        <input type="email" placeholder="your@email.com">
      </div>
    </div>
    <div class="form-field">
      <label>Client Type</label>
      <select>
        <option value="">Select one…</option>
        <option>Individual / Private Donor</option>
        <option>Politician / Public Official</option>
        <option>Diaspora Donor</option>
        <option>Organisation / NGO</option>
        <option>Faith Community</option>
        <option>Corporate / CSR</option>
      </select>
    </div>
    <div class="form-row">
      <div class="form-field">
        <label>Approximate Budget</label>
        <input type="text" placeholder="e.g. ₦500,000 or $2,000">
      </div>
      <div class="form-field">
        <label>Preferred Timeline</label>
        <input type="text" placeholder="e.g. Within 3 weeks">
      </div>
    </div>
    <div class="form-field">
      <label>Tell us about the community you want to reach</label>
      <textarea placeholder="Who should benefit? What do you want them to receive? Any special conditions?"></textarea>
    </div>
    <div class="form-field">
      <label style="display:flex;align-items:center;gap:0.5rem;cursor:pointer;text-transform:none;letter-spacing:0;font-size:0.82rem;color:var(--muted);">
        <input type="checkbox" style="width:auto;border-bottom:none;padding:0;"> I prefer to remain anonymous in this engagement
      </label>
    </div>
    <p class="form-note">Your inquiry is treated with complete confidentiality. We do not share client information with any third party.</p>
    <button class="btn-primary" type="button">Send Inquiry →</button>
  </div>
</section>

<!-- FOOTER -->

<footer>
  <a href="#" class="footer-logo">Vida Outreach<span>.</span></a>
  <span class="footer-tagline">Giving that reaches who it must.</span>
  <span class="footer-copy">© 2026 Vida Outreach Management. All rights reserved.</span>
</footer>

</body>
</html>
