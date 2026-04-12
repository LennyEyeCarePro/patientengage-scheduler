# PatientEngage Feature Page Design System

> Canonical reference: `scheduler/index.html`
> Every feature page must visually match the scheduler page exactly.
> Copy CSS from this document — do not invent new patterns.

---

## 1. Fonts

```html
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:ital,opsz,wght@0,9..40,400;0,9..40,500;0,9..40,600;0,9..40,700;0,9..40,800;1,9..40,400&display=swap" rel="stylesheet">
```

| Usage | Font | Weight | Notes |
|---|---|---|---|
| Body text, UI, buttons, labels | DM Sans | 400–800 | `font-family: 'DM Sans', sans-serif` |
| h1, h2, h3 (inside `.ptext`), `.stat-n`, `.cs-n`, `.qtext`, `.pullquote p` | DM Serif Display | 400 (normal) | `font-family: 'DM Serif Display', serif` |

**Never use Inter, Poppins, or any other font.**

---

## 2. CSS Variables

Paste this block exactly into every feature page `:root`:

```css
:root {
  --navy:    #0F2A4A;
  --blue:    #1B5FA8;
  --teal:    #00A3A3;
  --green:   #0F6E56;
  --green-bg:#F0FDF9;
  --green-bd:#A7F3D0;
  --slate:   #4B6278;
  --muted:   #7A96A8;
  --border:  #E2E8F0;
  --bg:      #F8FAFC;
  --blue-lt: #EEF4FF;
}
```

**Do not add extra variables.** These are all you need.

---

## 3. Base Styles

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }
body {
  font-family: 'DM Sans', sans-serif;
  color: var(--navy);
  background: #fff;
  -webkit-font-smoothing: antialiased;
  font-size: 17px;
  line-height: 1.65;
}
```

---

## 4. Navigation

Sticky top bar. Three zones: logo (left), links (center-ish), actions (right).

```html
<nav>
  <a href="/" class="nav-logo">PatientEngage</a>
  <ul class="nav-links">
    <li><a href="/scheduler">Real-Time Scheduler</a></li>
    <li><a href="/campaigns">One-Click Campaigns</a></li>
    <li><a href="/ai-voice-agent">AI Voice Agent</a></li>
    <li><a href="/google-reserve">Google Reserve</a></li>
    <li><a href="/reminders">Reminders</a></li>
  </ul>
  <div class="nav-actions">
    <a href="#" class="btn-outline">Sign in</a>
    <a href="#" class="btn-dark">Get started</a>
  </div>
</nav>
```

Mark the current page's link with `class="active"`.

```css
nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 18px 48px;
  background: #fff;
  border-bottom: 1px solid var(--border);
  position: sticky;
  top: 0;
  z-index: 100;
}
.nav-logo { font-size: 17px; font-weight: 800; color: var(--navy); text-decoration: none; letter-spacing: -.3px; }
.nav-links { display: flex; gap: 28px; list-style: none; }
.nav-links a { font-size: 14px; color: var(--muted); text-decoration: none; transition: color .2s; }
.nav-links a:hover { color: var(--navy); }
.nav-links .active { color: var(--navy); font-weight: 600; border-bottom: 2px solid var(--teal); padding-bottom: 2px; }
.nav-actions { display: flex; gap: 8px; }
```

---

## 5. Buttons

All buttons use **30px border-radius** (pill shape). Never use 8px.

| Class | Usage | CSS |
|---|---|---|
| `.btn-outline` | Nav "Sign in" | `padding: 9px 22px; border-radius: 30px; border: 1.5px solid var(--border); background: #fff; color: var(--navy); font-size: 14px; font-weight: 600;` |
| `.btn-dark` | Nav "Get started" | `padding: 9px 22px; border-radius: 30px; border: none; background: var(--navy); color: #fff; font-size: 14px; font-weight: 600;` |
| `.btn-navy-pill` | Hero primary CTA | `padding: 14px 32px; border-radius: 30px; border: none; background: var(--navy); color: #fff; font-size: 15px; font-weight: 700;` |
| `.btn-ghost-pill` | Hero secondary CTA | `padding: 14px 32px; border-radius: 30px; border: 1.5px solid var(--border); background: #fff; color: var(--navy); font-size: 15px; font-weight: 600;` |
| `.btn-teal-pill` | CTA section | `padding: 14px 32px; border-radius: 30px; border: none; background: var(--teal); color: #fff; font-size: 15px; font-weight: 700;` |

All buttons must have `font-family: 'DM Sans', sans-serif; cursor: pointer;`.

---

## 6. Hero Section

**Always centered.** Never left-aligned. Never a two-column grid.

```html
<section class="hero">
  <div class="badge"><span class="badge-dot"></span> Badge text here</div>
  <h1>Headline with <em>teal italic accent.</em></h1>
  <p class="hero-sub">Subheadline text here.</p>
  <div class="hero-cta">
    <button class="btn-navy-pill">Primary CTA</button>
    <button class="btn-ghost-pill">Secondary CTA</button>
  </div>
  <p class="hero-fine">Fine print · separated by middots</p>
  <!-- Optional: hero-frame with browser chrome mockup -->
</section>
```

```css
.hero { padding: 88px 48px 72px; text-align: center; }

.badge {
  display: inline-flex; align-items: center; gap: 7px;
  padding: 6px 18px; background: var(--green-bg); border: 1px solid var(--green-bd);
  border-radius: 30px; font-size: 13px; font-weight: 600; color: var(--green); margin-bottom: 24px;
}
.badge-dot { width: 7px; height: 7px; border-radius: 50%; background: var(--green); }

h1 {
  font-family: 'DM Serif Display', serif;
  font-size: 56px; font-weight: 400; color: var(--navy);
  line-height: 1.08; letter-spacing: -.5px; margin-bottom: 20px;
  max-width: 640px; margin-left: auto; margin-right: auto;
}
h1 em { font-style: italic; color: var(--teal); }

.hero-sub {
  font-size: 19px; color: var(--slate); line-height: 1.7;
  max-width: 560px; margin: 0 auto 30px;
}

.hero-cta { display: flex; gap: 12px; justify-content: center; flex-wrap: wrap; margin-bottom: 14px; }
.hero-fine { font-size: 14px; color: var(--muted); margin-bottom: 56px; }
```

### Hero Frame (browser chrome mockup)

Optional. Used when there is a screenshot or visual to show.

```html
<div class="hero-frame">
  <div class="frame-bar">
    <span class="fdot" style="background:#FF5F57"></span>
    <span class="fdot" style="background:#FEBC2E"></span>
    <span class="fdot" style="background:#28C840"></span>
    <span class="furl">URL bar text</span>
  </div>
  <img src="..." alt="...">
</div>
```

```css
.hero-frame {
  max-width: 700px; margin: 0 auto; border-radius: 16px;
  overflow: hidden; border: 1px solid var(--border);
  box-shadow: 0 8px 48px rgba(15,42,74,.12);
}
.frame-bar {
  background: var(--bg); padding: 11px 18px;
  border-bottom: 1px solid var(--border);
  display: flex; align-items: center; gap: 7px;
}
.fdot { width: 10px; height: 10px; border-radius: 50%; }
.furl {
  background: #EDF2F7; border-radius: 5px; padding: 4px 16px;
  font-size: 12px; color: var(--muted); margin-left: 12px;
  flex: 1; max-width: 340px; text-align: center;
}
.hero-frame img { width: 100%; display: block; }
```

---

## 7. Stats Bar

Full-width flex row directly below the hero. 3 or 4 stat items.

```html
<div class="stats">
  <div class="stat">
    <div class="stat-n">7,500+</div>
    <div class="stat-l">description line<br>second line</div>
  </div>
  <!-- repeat for each stat -->
</div>
```

```css
.stats {
  display: flex;
  border-top: 1px solid var(--border);
  border-bottom: 1px solid var(--border);
  background: var(--bg);
}
.stat { flex: 1; padding: 32px 24px; text-align: center; border-right: 1px solid var(--border); }
.stat:last-child { border-right: none; }
.stat-n {
  font-family: 'DM Serif Display', serif;
  font-size: 42px; color: var(--navy); line-height: 1; margin-bottom: 7px;
}
.stat-l { font-size: 14px; color: var(--muted); line-height: 1.5; }
```

---

## 8. Content Sections

All content sections follow this pattern:

```html
<section class="section">          <!-- or class="section section-alt" for gray bg -->
  <div class="si">                 <!-- max-width: 900px centered container -->
    <div class="eyebrow">LABEL</div>
    <h2>Section headline</h2>
    <p class="ssub">Section description text.</p>
    <!-- section-specific content here -->
  </div>
</section>
```

```css
.section { padding: 80px 48px; }
.section-alt { background: var(--bg); }
.si { max-width: 900px; margin: 0 auto; }
.eyebrow {
  font-size: 12px; font-weight: 700; color: var(--teal);
  letter-spacing: 1.2px; text-transform: uppercase; margin-bottom: 12px;
}
h2 {
  font-family: 'DM Serif Display', serif;
  font-size: 40px; font-weight: 400; color: var(--navy);
  line-height: 1.15; margin-bottom: 12px; letter-spacing: -.3px;
}
.ssub {
  font-size: 17px; color: var(--slate); line-height: 1.75;
  max-width: 520px; margin-bottom: 44px;
}
```

**Alternate `.section` and `.section-alt`** for visual rhythm (white, gray, white, gray...).

---

## 9. Component Library

### 9a. Problem Cards (`.before-grid`)

3-column grid of pain-point cards. Use `.hl` + `.btag.bad` for highlighted/negative cards.

```html
<div class="before-grid">
  <div class="bc">                <!-- or class="bc hl" for red-tinted highlight -->
    <span class="btag">Label</span>   <!-- or class="btag bad" for red tag -->
    <div class="btitle">Card title</div>
    <div class="bbody">Card body text.</div>
  </div>
  <!-- repeat 3x -->
</div>
```

```css
.before-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 16px; margin-bottom: 40px; }
.bc { padding: 26px; border-radius: 14px; border: 1px solid var(--border); background: #fff; }
.bc.hl { border-color: #FECACA; background: #FEF9F9; }
.btag {
  display: inline-block; padding: 3px 12px; border-radius: 20px;
  font-size: 11px; font-weight: 700; letter-spacing: .5px; text-transform: uppercase;
  margin-bottom: 12px; background: var(--bg); color: var(--muted);
}
.btag.bad { background: #FEE2E2; color: #DC2626; }
.btitle { font-size: 16px; font-weight: 700; color: var(--navy); margin-bottom: 10px; }
.bbody { font-size: 14px; color: var(--slate); line-height: 1.7; }
```

### 9b. Pullquote

Dark navy block that follows problem cards.

```html
<div class="pullquote">
  <p>"Quote text in DM Serif italic."</p>
  <span>Attribution or context line</span>
</div>
```

```css
.pullquote { background: var(--navy); border-radius: 14px; padding: 32px 40px; text-align: right; }
.pullquote p {
  font-family: 'DM Serif Display', serif;
  font-size: 22px; color: #fff; line-height: 1.5; font-style: italic; margin-bottom: 10px;
}
.pullquote span { font-size: 14px; color: var(--muted); }
```

### 9c. Steps Grid

3-column grid of process steps. Hover turns border teal.

```html
<div class="steps">
  <div class="step">
    <div class="step-n">Step 1</div>
    <div class="step-t">Step title</div>
    <div class="step-b">Step description text.</div>
  </div>
  <!-- repeat 3x -->
</div>
```

If your feature genuinely has 4 steps, use `grid-template-columns: 1fr 1fr 1fr 1fr`. But prefer 3 columns when possible.

```css
.steps { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 16px; }
.step { padding: 26px; border: 1px solid var(--border); border-radius: 14px; background: #fff; transition: border-color .2s; }
.step:hover { border-color: var(--teal); }
.step-n { font-size: 12px; font-weight: 700; color: var(--teal); margin-bottom: 10px; letter-spacing: .3px; }
.step-t { font-size: 16px; font-weight: 700; color: var(--navy); margin-bottom: 8px; }
.step-b { font-size: 14px; color: var(--slate); line-height: 1.7; }
```

### 9d. Image + Text Pairs

Two-column layout alternating image/text sides. Use `.flip` to swap sides.

```html
<div class="pair">
  <div class="ptext">
    <h3>Pair heading</h3>
    <p>Description paragraph.</p>
    <span class="proof-pill">Data point or proof</span>
  </div>
  <div class="pframe">
    <img src="..." alt="...">
  </div>
</div>

<div class="pair flip">
  <!-- same structure, image appears on left -->
</div>
```

```css
.pair { display: grid; grid-template-columns: 1fr 1fr; gap: 56px; align-items: center; margin-top: 56px; }
.pair.flip { direction: rtl; }
.pair.flip > * { direction: ltr; }
.pframe { border-radius: 14px; overflow: hidden; border: 1px solid var(--border); box-shadow: 0 4px 28px rgba(15,42,74,.09); }
.pframe img { width: 100%; display: block; }
.ptext h3 {
  font-family: 'DM Serif Display', serif;
  font-size: 30px; font-weight: 400; color: var(--navy); line-height: 1.2; margin-bottom: 14px;
}
.ptext p { font-size: 15px; color: var(--slate); line-height: 1.75; margin-bottom: 14px; }
.proof-pill {
  display: inline-block; padding: 5px 16px;
  background: var(--blue-lt); color: var(--blue); border-radius: 20px;
  font-size: 13px; font-weight: 600;
}
```

### 9e. Case Study

Gradient card with stats grid and testimonial.

```html
<div class="case">
  <!-- Optional intro text -->
  <div class="case-stats">
    <div class="cs"><div class="cs-n">108</div><div class="cs-l">label</div></div>
    <div class="cs"><div class="cs-n">33%</div><div class="cs-l">label</div></div>
    <div class="cs"><div class="cs-n">10%</div><div class="cs-l">label</div></div>
    <div class="cs"><div class="cs-n">3.3%</div><div class="cs-l">label</div></div>
  </div>
  <p class="qtext">"Testimonial quote in DM Serif italic."</p>
  <div class="qattr">
    <div class="avatar">XX</div>
    <div>
      <div class="qname">Name or role</div>
      <div class="qloc">Location or context</div>
    </div>
  </div>
</div>
```

```css
.case {
  background: linear-gradient(135deg, #F0F7FF, #F0FDFB);
  border: 1px solid #DBEAFE; border-radius: 16px; padding: 40px;
}
.case-stats {
  display: grid; grid-template-columns: repeat(4, 1fr);
  border: 1px solid var(--border); border-radius: 12px;
  overflow: hidden; background: #fff; margin: 22px 0 32px;
}
.cs { padding: 20px 14px; text-align: center; border-right: 1px solid var(--border); }
.cs:last-child { border-right: none; }
.cs-n { font-family: 'DM Serif Display', serif; font-size: 34px; color: var(--navy); line-height: 1; margin-bottom: 5px; }
.cs-l { font-size: 13px; color: var(--muted); line-height: 1.4; }
.qtext {
  font-family: 'DM Serif Display', serif; font-size: 20px; color: var(--navy);
  line-height: 1.65; font-style: italic; margin-bottom: 20px;
}
.qattr { display: flex; align-items: center; gap: 14px; }
.avatar {
  width: 42px; height: 42px; border-radius: 50%; background: var(--teal);
  display: flex; align-items: center; justify-content: center;
  font-size: 13px; font-weight: 700; color: #fff; flex-shrink: 0;
}
.qname { font-size: 14px; font-weight: 700; color: var(--navy); }
.qloc { font-size: 13px; color: var(--muted); margin-top: 2px; }
```

### 9f. Objections / FAQ Accordion

Collapsible question/answer blocks.

```html
<div class="obj" onclick="toggle(this)">
  <div class="obj-q">"Question text" <span class="arr">&#8595;</span></div>
  <div class="obj-a">Answer text.</div>
</div>
```

Requires this script at the bottom:
```html
<script>function toggle(el) { el.classList.toggle('open'); }</script>
```

```css
.obj { border: 1px solid var(--border); border-radius: 12px; margin-bottom: 10px; overflow: hidden; background: #fff; }
.obj-q {
  padding: 18px 24px; font-size: 15px; font-weight: 600; color: var(--navy);
  cursor: pointer; display: flex; justify-content: space-between; align-items: center;
  transition: background .15s; user-select: none; line-height: 1.4;
}
.obj-q:hover { background: var(--bg); }
.arr { color: var(--muted); font-size: 20px; transition: transform .2s; flex-shrink: 0; margin-left: 16px; }
.obj-a { padding: 0 24px 20px; font-size: 15px; color: var(--slate); line-height: 1.75; display: none; }
.obj.open .obj-a { display: block; }
.obj.open .arr { transform: rotate(180deg); }
```

### 9g. Comparison Table

Wrapped in `.tw` for rounded border-radius.

```html
<div class="tw">
  <table>
    <thead>
      <tr>
        <th>Feature</th>
        <th class="pe">PatientEngage</th>
        <th>Competitor 1</th>
        <th>Competitor 2</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Row label</td>
        <td class="pe win">✓ Yes</td>
        <td>No</td>
        <td>Partial</td>
      </tr>
    </tbody>
  </table>
</div>
<p class="tnote">Table footnote text.</p>
```

```css
.tw { border: 1px solid var(--border); border-radius: 14px; overflow: hidden; overflow-x: auto; }
table { width: 100%; border-collapse: collapse; font-size: 14px; }
thead th {
  padding: 15px 18px; text-align: left; font-weight: 700;
  color: var(--navy); background: var(--bg); border-bottom: 1px solid var(--border); font-size: 14px;
}
thead th:not(:first-child) { text-align: center; }
thead th.pe { background: var(--blue-lt); color: var(--blue); }
tbody td { padding: 13px 18px; border-bottom: 1px solid #F1F5F9; color: var(--slate); font-size: 14px; }
tbody td:not(:first-child) { text-align: center; }
tbody td.pe { background: #F8FBFF; }
tbody td.win { color: var(--green); font-weight: 700; }
tbody tr:last-child td { border-bottom: none; }
tbody tr:hover td { background: var(--bg); }
tbody tr:hover td.pe { background: var(--blue-lt); }
.tnote { font-size: 13px; color: var(--muted); margin-top: 12px; }
```

### 9h. Cross-feature Teaser

Green-tinted banner linking to another feature page.

```html
<div class="gr-teaser">
  <div>
    <div class="gr-teaser-label">Also included</div>
    <div class="gr-teaser-title">Feature name</div>
    <div class="gr-teaser-body">Short description of the related feature.</div>
  </div>
  <a href="/feature-slug" class="gr-link">Learn more &#8594;</a>
</div>
```

```css
.gr-teaser {
  margin-top: 56px; padding: 28px 32px;
  border: 1px solid var(--green-bd); border-radius: 14px; background: var(--green-bg);
  display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap; gap: 20px;
}
.gr-teaser-label { font-size: 12px; font-weight: 700; color: var(--green); letter-spacing: .8px; text-transform: uppercase; margin-bottom: 7px; }
.gr-teaser-title { font-size: 17px; font-weight: 700; color: var(--navy); margin-bottom: 6px; }
.gr-teaser-body { font-size: 14px; color: var(--slate); max-width: 500px; line-height: 1.65; }
.gr-link {
  display: inline-block; padding: 11px 24px; border-radius: 30px;
  border: 1.5px solid var(--green); color: var(--green); font-size: 14px;
  font-weight: 600; text-decoration: none; white-space: nowrap; transition: background .2s;
}
.gr-link:hover { background: rgba(15,110,86,.08); }
```

### 9i. Logos / Trust Bar

Optional row of practice name pills.

```html
<div class="logos">
  <p>Trust statement text</p>
  <div class="logo-row">
    <span class="logo-pill">Practice Name</span>
    <!-- repeat -->
    <span class="logo-pill">+ hundreds more</span>
  </div>
</div>
```

```css
.logos { padding: 28px 48px; text-align: center; border-bottom: 1px solid var(--border); }
.logos p { font-size: 14px; color: var(--muted); margin-bottom: 16px; }
.logo-row { display: flex; justify-content: center; gap: 10px; flex-wrap: wrap; }
.logo-pill {
  padding: 7px 18px; border: 1px solid var(--border); border-radius: 30px;
  font-size: 13px; font-weight: 600; color: var(--muted);
}
```

---

## 10. CTA Section

```html
<section class="cta">
  <h2>CTA headline</h2>
  <p class="cta-sub">Supporting text.</p>
  <div class="cta-btns">
    <button class="btn-teal-pill">Primary CTA</button>
    <button class="btn-ghost-pill">Secondary CTA</button>
  </div>
  <p class="cta-fine">Fine print · Or <a>link text</a></p>
</section>
```

```css
.cta {
  padding: 88px 48px; text-align: center;
  background: var(--bg); border-top: 1px solid var(--border);
}
.cta h2 { margin-bottom: 14px; }
.cta-sub { font-size: 17px; color: var(--slate); margin-bottom: 32px; line-height: 1.7; }
.cta-btns { display: flex; gap: 12px; justify-content: center; flex-wrap: wrap; }
.cta-fine { font-size: 14px; color: var(--muted); margin-top: 18px; }
.cta-fine a { color: var(--blue); text-decoration: underline; cursor: pointer; }
```

---

## 11. Footer

Simple one-line footer. No columns, no link lists, no dark background.

```html
<footer>
  <span class="flogo">PatientEngage</span>
  <span class="fcopy">&copy; 2026 &middot; patientengage.ai</span>
</footer>
```

```css
footer {
  padding: 24px 48px; display: flex; justify-content: space-between;
  align-items: center; border-top: 1px solid var(--border);
}
.flogo { font-size: 16px; font-weight: 800; color: var(--navy); }
.fcopy { font-size: 13px; color: var(--muted); }
```

---

## 12. Responsive Breakpoint

Single breakpoint at 768px. Copy this block exactly.

```css
@media (max-width: 768px) {
  nav { padding: 16px 20px; }
  .nav-links { display: none; }
  h1 { font-size: 38px; }
  .hero { padding: 60px 20px 52px; }
  .hero-sub { font-size: 17px; }
  .stats { flex-direction: column; }
  .stat { border-right: none; border-bottom: 1px solid var(--border); }
  .stat:last-child { border-bottom: none; }
  .logos { padding: 24px 20px; }
  .section { padding: 60px 20px; }
  .before-grid, .steps { grid-template-columns: 1fr; }
  .pair, .pair.flip { grid-template-columns: 1fr; gap: 28px; direction: ltr; }
  .case-stats { grid-template-columns: 1fr 1fr; }
  .cs:nth-child(2) { border-right: none; }
  .cs:nth-child(3) { border-top: 1px solid var(--border); }
  h2 { font-size: 30px; }
  .pullquote { text-align: left; padding: 24px; }
  .gr-teaser { flex-direction: column; }
  .cta { padding: 60px 20px; }
  footer { flex-direction: column; gap: 8px; padding: 20px; text-align: center; }
}
```

---

## 13. Page Structure Template

Every feature page follows this section order:

1. **Nav** — sticky, with current page `.active`
2. **Hero** — centered, badge + h1 + hero-sub + CTAs + fine print + optional hero-frame
3. **Stats** — 3 or 4 stat items in flex row
4. **Logos** — optional trust bar
5. **Problem** — `.section` with eyebrow + h2 + ssub + before-grid + pullquote
6. **How It Works** — `.section.section-alt` with eyebrow + h2 + steps grid
7. **Deep Dive** — `.section` with pairs (image + text) or channel cards
8. **Case Study** — `.section` with `.case` card containing stats + testimonial
9. **Objections / FAQ** — `.section.section-alt` with `.obj` accordion items
10. **Comparison Table** — `.section` with `.tw` table
11. **Cross-feature Teaser** — optional `.gr-teaser` linking to related feature
12. **CTA** — `.cta` section with teal pill button
13. **Footer** — simple one-line

Not every section is required. But sections that are used must follow these patterns exactly.

---

## 14. Things That Are WRONG (Do Not Do These)

- **Inter font** — never use it
- **Left-aligned hero** with two-column grid layout
- **`opacity: 0` animations** — never use `.animate-section` or scroll-triggered opacity. Content must be visible immediately.
- **Dark navy CTA section** — CTA section uses `var(--bg)` light gray, not `var(--navy)`
- **4-column dark footer** with link lists — footer is one line
- **Square buttons** with `border-radius: 8px` — all buttons are pills (30px)
- **Separate CSS files** — all CSS is inline in `<style>` in the `<head>`
- **External JS frameworks** — no React, no Tailwind, no build tools. Plain HTML + CSS + minimal vanilla JS.

---

## 15. Content Rules (from Lenny)

- SeaShore House (#1718) must NEVER appear in pictures or data
- Pricing is confidential — all references must be `[pricing redacted]`
- Case study practice anonymized as **"Coastal Eye Associates"**
- Provenance rules: tag data as [OBSERVED], [CALCULATED], or [ESTIMATE]
- Don't frame "0 to X" as growth
- Key value prop: "It's not just the emails, but the landing pages as well. It keeps the visitor inside the ecosystem and tries to trigger appointments."
- Keep a small focus on ease of use and saving staff time
