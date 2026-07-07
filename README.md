# vajkebebd.github.io
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>MajorMatch - Professional Academic Guidance</title>
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&family=Montserrat:wght@600;700;800&display=swap" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<style>
/* --- 🎨 LIGHT BLUE THEME + DARK MODE --- */
:root{
  --primary-blue: #2E86C1;      
  --primary-blue-deep: #1B4F72; 
  --accent-blue: #5DADE2;       
  --bg-main: #EAF4FC;           
  --card-bg: #ffffff;
  --text-dark: #1B2631;
  --text-muted: #5D6D7E;
  --success: #27AE60;
  --border-color: #D6EAF8;
  --shadow-pro: 0 10px 30px rgba(46, 134, 193, 0.12);
  --selected-bg: #EAF6FD;
  --top-match-bg: #EDFBF3;
}

body.dark-mode{
  --primary-blue: #5DADE2;
  --primary-blue-deep: #85C1E9;
  --accent-blue: #85C1E9;
  --bg-main: #0F1720;
  --card-bg: #1B2733;
  --text-dark: #EAF4FC;
  --text-muted: #9FB3C8;
  --success: #2ECC71;
  --border-color: #2A3B4C;
  --shadow-pro: 0 10px 30px rgba(0, 0, 0, 0.45);
  --selected-bg: #17324A;
  --top-match-bg: #123626;
}

*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth;}
body{
  font-family: 'Roboto', sans-serif;
  background-color: var(--bg-main);
  color: var(--text-dark);
  line-height: 1.6;
  transition: background-color 0.3s ease, color 0.3s ease;
  overflow-x: hidden;
}

/* Layout Structure */
.container{width:90%;max-width:1400px;margin:40px auto 120px;}

/* Header */
header {
  background: var(--card-bg);
  border-bottom: 1px solid var(--border-color);
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
  min-height: 70px;
  display: flex;
  align-items: center;
  padding: 0 20px;
  position: sticky;
  top: 0;
  z-index: 50;
  transition: background-color 0.3s ease, border-color 0.3s ease;
}

.nav-wrap {
  width: 90%;
  max-width: 1400px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 12px;
  padding: 10px 0;
}

.brand {
  display: flex;
  align-items: center;
  gap: 10px;
}
.brand .logo {
  background: var(--accent-blue);
  color: white;
  width: 45px;
  height: 45px;
  font-size: 1.1rem;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}
.site-name{ font-weight: bold; color: var(--primary-blue); font-family: 'Montserrat', sans-serif; }

.nav-right{
  display:flex;
  align-items:center;
  gap: 20px;
  flex-wrap: wrap;
}

nav {
  display: flex;
  align-items: center;
  padding: 0;
  gap: 25px;
  flex-wrap: wrap;
}
nav a{
  position: relative;
  text-decoration: none;
  font-weight: 600;
  font-size: 1rem;
  color: var(--primary-blue);
  padding: 5px 0;
  transition: color 0.3s ease;
  opacity: 0.8;
  cursor: pointer;
}
nav a:hover{opacity:1; color:var(--accent-blue);}
nav a::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: -3px;
  width: 0;
  height: 3px;
  background: var(--accent-blue);
  border-radius: 2px;
  transition: width 0.3s ease;
}
nav a:hover::after { width: 100%; }
nav a.active { color: var(--accent-blue); opacity: 1; }
nav a.active::after { width: 100%; }

/* Dark mode toggle */
.theme-toggle{
  display:flex;
  align-items:center;
  gap:8px;
  background: var(--bg-main);
  border: 1px solid var(--border-color);
  border-radius: 999px;
  padding: 6px 14px;
  font-weight: 600;
  font-size: 0.9rem;
  color: var(--primary-blue);
  cursor: pointer;
  transition: background-color 0.3s ease;
}
.theme-toggle:hover{ border-color: var(--accent-blue); }

.nav-toggle{
  display:none;
  background:none;
  border: 1px solid var(--border-color);
  border-radius: 8px;
  width: 42px;
  height: 42px;
  font-size: 1.3rem;
  color: var(--primary-blue);
  cursor: pointer;
  align-items:center;
  justify-content:center;
}

/* Views Architecture */
.app-view { display: none; }
.app-view.view-active { display: block; animation: fadeIn 0.4s ease-in-out; }

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(10px); }
  to { opacity: 1; transform: translateY(0); }
}

/* Hero */
.hero {
  padding: 80px 60px;
  border-radius: 24px;
  display: grid;
  grid-template-columns: 2fr 1.2fr;
  color: white;
  background: linear-gradient(135deg, var(--primary-blue) 0%, var(--accent-blue) 100%);
  box-shadow: 0 20px 50px rgba(46, 134, 193, 0.35);
  gap: 24px;
}
.hero h2{font-family: 'Montserrat', sans-serif; font-size:3rem;margin-bottom:25px;font-weight:800; line-height: 1.2;}
.hero p{font-size: 1.25rem; opacity:0.95; margin-bottom:40px}
.cta-row { display: flex; gap: 12px; flex-wrap: wrap; }

.btn-primary{
  background: white;
  color: var(--primary-blue);
  padding:18px 36px;
  border-radius:12px;
  font-size: 1.1rem;
  font-weight: 700;
  border: none;
  cursor: pointer;
  box-shadow:0 8px 30px rgba(0, 0, 0, 0.15);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}
.btn-primary:hover{transform:translateY(-5px);box-shadow:0 15px 40px rgba(0, 0, 0, 0.2);}
.small-cta{
  background: transparent;
  border: 2px solid rgba(255,255,255,0.8);
  color: white;
  padding: 16px 30px;
  border-radius: 12px;
  font-weight: 700;
  font-size: 1.1rem;
  cursor: pointer;
  transition: transform 0.2s ease, background-color 0.2s ease;
}
.small-cta:hover{background:rgba(255,255,255,0.15); transform:translateY(-3px);}

.hero-card{background: var(--card-bg); padding:35px; border-radius:18px; color: var(--text-dark);}
.hero-card h3{color:var(--primary-blue); font-family: 'Montserrat', sans-serif; margin-bottom: 15px;}
.hero-card .features div {padding: 18px; border-radius: 10px; background: var(--bg-main); margin-bottom: 15px;}
.hero-card .features div:last-child{margin-bottom:0;}
.hero-card .features{gap:15px; margin-top:25px; display:flex; flex-direction:column;}
.hero-overlay { display: grid; grid-template-columns: 1fr 420px; gap: 24px; }

/* Quiz Progress */
.progress-wrap-fixed{padding: 30px 0; background: var(--bg-main); border-bottom: 1px solid var(--border-color); margin-bottom: 20px;}
.progress-bar-outer-top{width: 100%; height:8px; background:var(--border-color); border-radius:4px; overflow:hidden;}
.progress-bar-inner-top{background: var(--accent-blue); transition: width 0.4s ease-in-out; height:100%;}
.progress-step-indicator { width: 100%; margin-bottom: 25px; }

/* Quiz card */
.card{
  padding:50px;
  border-radius:24px;
  background: var(--card-bg);
  box-shadow: var(--shadow-pro);
}
.quiz-header {margin-bottom: 30px; border-bottom: 1px solid var(--border-color); padding-bottom: 20px; display:flex; justify-content:space-between; flex-wrap:wrap; gap:10px;}
.question-text{
  font-family: 'Montserrat', sans-serif;
  font-size:1.8rem;
  font-weight:700;
  margin-bottom:40px;
  color:var(--primary-blue);
}
.question-tag {
  display: inline-block;
  padding: 6px 14px;
  background: var(--selected-bg);
  color: var(--primary-blue);
  border-radius: 6px;
  font-size: 0.85rem;
  font-weight: 700;
  text-transform: uppercase;
  margin-bottom: 15px;
  border: 1px solid var(--border-color);
}

.options{
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap:24px;
}
label.option{
  padding:26px;
  border-radius:16px;
  border:3px solid var(--border-color);
  font-size: 1.1rem;
  font-weight: 500;
  transition: all 0.3s ease;
  cursor: pointer;
  display: flex;
  align-items: center;
  position: relative;
  user-select: none;
  background: var(--card-bg);
}
label.option:hover{
  transform:translateY(-6px);
  box-shadow:0 15px 40px rgba(46, 134, 193, 0.2);
  border-color:var(--accent-blue);
}
label.option.selected{
  background: var(--selected-bg);
  border-color:var(--primary-blue);
  box-shadow:0 8px 30px rgba(46, 134, 193, 0.15);
}
label.option input{ position: absolute; opacity: 0; cursor: pointer; }

.quiz-actions{margin-top:40px; display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 15px;}
.btn-ghost{color: var(--text-muted); border: none; background: none; cursor: pointer; padding: 16px 25px; border-radius: 10px; font-size: 1rem; font-weight:600;}
.btn-ghost:hover{color: var(--primary-blue); background: var(--bg-main);}
.btn-next{
  padding:16px 32px;
  border-radius:12px;
  background: var(--primary-blue);
  color: white;
  font-size: 1.1rem;
  font-weight: 600;
  border: none;
  cursor: pointer;
  transition: background-color 0.2s ease, transform 0.2s ease;
}
.btn-next:hover{background: var(--primary-blue-deep); transform:translateY(-3px);}

/* Detailed Results Page */
.results-wrap{margin-top:20px;}
.results-actions{display:flex; gap:15px; flex-wrap:wrap; margin-bottom:35px;}
.btn-outline{
  background: transparent;
  border: 2px solid var(--primary-blue);
  color: var(--primary-blue);
  padding: 14px 26px;
  border-radius: 10px;
  font-weight: 700;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.2s ease;
}
.btn-outline:hover{ background: var(--primary-blue); color: white; }

.results-grid { display: grid; grid-template-columns: 1fr; gap: 35px; }
.result-item{
  padding:40px;
  border-radius:24px;
  border-left:12px solid var(--accent-blue);
  background:var(--card-bg);
  box-shadow: var(--shadow-pro);
}
.result-item.top-match{
  border-left-color:var(--success);
  background: var(--top-match-bg);
  border: 1px solid var(--success);
  border-left-width: 12px;
}
.result-item h3{font-size:2rem; color:var(--primary-blue); margin-bottom:20px; font-family: 'Montserrat', sans-serif; display: flex; justify-content: space-between; align-items: center;}
.match-badge { background: var(--primary-blue); color: white; padding: 6px 16px; border-radius: 999px; font-size: 1rem; font-weight: 800; }
.result-item.top-match .match-badge { background: var(--success); }

.result-section-block { margin-top: 15px; padding-top: 15px; border-top: 1px dashed var(--border-color); }
.result-section-block h5 { font-family: 'Montserrat', sans-serif; font-size: 1.05rem; color: var(--primary-blue); margin-bottom: 6px; }

.major-detail-btn{background:var(--primary-blue); color:white; padding:12px 22px; border-radius:10px; margin-top:25px; font-weight:600; border:none; cursor:pointer;}
.major-detail-btn:hover{background:var(--accent-blue); color: var(--primary-blue-deep);}
.restart-btn{margin-top:40px; padding: 18px 35px; font-size: 1.1rem; border:none; cursor:pointer;}

/* Modals */
.modal-overlay{
  display:none;
  position: fixed;
  inset: 0;
  background: rgba(15, 23, 32, 0.55);
  z-index: 200;
  align-items: center;
  justify-content: center;
  padding: 20px;
}
.modal-overlay.open{ display:flex; }
.modal-content{
  background: var(--card-bg);
  padding:50px;
  border-radius:24px;
  max-width:800px;
  width:100%;
  max-height: 85vh;
  overflow-y: auto;
  box-shadow: 0 10px 50px rgba(0,0,0,0.3);
  position: relative;
}
.modal-content h4{color:var(--primary-blue);font-size:2rem; font-family:'Montserrat', sans-serif; margin-bottom:10px;}
.modal-close{
  position:absolute; top:20px; right:20px;
  background:none; border:none; font-size:1.6rem; cursor:pointer; color: var(--text-muted);
}
.modal-close:hover{ color: var(--primary-blue); }

.compare-table{ width:100%; border-collapse: collapse; margin-top: 20px; }
.compare-table th, .compare-table td{
  border: 1px solid var(--border-color);
  padding: 14px;
  text-align: left;
  vertical-align: top;
  font-size: 0.95rem;
}
.compare-table th{ background: var(--bg-main); color: var(--primary-blue); font-family:'Montserrat', sans-serif; }

/* Isolated Catalog View styling */
.catalog-header { text-align: center; margin-bottom: 40px; }
.catalog-header h3 { color: var(--primary-blue); font-size: 2.6rem; font-family: 'Montserrat', sans-serif; margin-bottom: 10px; }
.catalog-header p { color: var(--text-muted); max-width: 700px; margin: 0 auto; font-size: 1.1rem; }
.feature-badges{ display:flex; flex-wrap:wrap; justify-content:center; gap:12px; margin-bottom:40px; }
.feature-badges span{
  background: var(--card-bg);
  border: 1px solid var(--border-color);
  color: var(--primary-blue);
  padding: 8px 16px;
  border-radius: 999px;
  font-size: 0.9rem;
  font-weight: 600;
  box-shadow: var(--shadow-pro);
}
.major-grid{ display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 30px; }
.major-card{padding:35px;border-radius:18px;border-left:8px solid var(--primary-blue); background:var(--card-bg); box-shadow:var(--shadow-pro); transition: transform 0.2s; }
.major-card:hover { transform: translateY(-4px); }
.major-icon{width:60px;height:60px;background:var(--bg-main); border-radius: 12px; font-size: 1.8rem; flex-shrink:0;}

footer{
  text-align:center;
  padding: 40px 0;
  color:white;
  background:var(--primary-blue);
  font-weight:500;
  font-size: 0.9rem;
}

/* ================= RESPONSIVE / MOBILE ================= */
@media (max-width: 900px){
  .hero{ grid-template-columns: 1fr; padding: 50px 30px; }
  .hero-overlay{ grid-template-columns: 1fr; }
  .hero-card{ margin-top: 20px; }
}

@media (max-width: 768px){
  .nav-toggle{ display:flex; }
  nav{
    display:none;
    width:100%;
    flex-direction: column;
    align-items: flex-start;
    gap: 14px;
    padding: 14px 0 4px;
  }
  nav.nav-open{ display:flex; }
  .nav-right{ width:100%; flex-direction: column; align-items: flex-start; }
  .theme-toggle{ order: -1; }
  .nav-wrap{ align-items: flex-start; }
}

@media (max-width: 520px) {
  .hero h2{ font-size: 1.8rem; }
  .cta-row{ flex-direction: column; gap: 10px; }
  .btn-primary, .small-cta{ width: 100%; text-align:center; }
  .options{ grid-template-columns: 1fr; }
  .quiz-actions{ flex-direction: column-reverse; }
  .btn-next, .btn-ghost{ width: 100%; text-align:center; }
}
</style>
</head>
<body>

<header>
  <div class="nav-wrap">
    <div class="brand">
      <div class="logo">MM</div>
      <div class="site-name"><MajorMatch></div>
    </div>
    <button class="nav-toggle" id="navToggle" aria-label="Toggle navigation">☰</button>
    <div class="nav-right" id="navRight">
      <nav id="mainNav">
        <a data-target="homeView" class="nav-link active">Home</a>
        <a data-target="catalogView" class="nav-link">Catalog &amp; Details</a>
        <a data-target="quizView" class="nav-link">Quiz</a>
        <a data-target="resultsView" class="nav-link">Results</a>
      </nav>
      <button class="theme-toggle" id="themeToggle">🌙 Dark Mode</button>
    </div>
  </div>
</header>

<main class="container">

  <!-- HOME VIEW -->
  <section id="homeView" class="app-view view-active">
    <div class="hero-overlay hero">
      <div style="padding:20px">
        <h2>Discover Your Path <br> With MajorMatch</h2>
        <p>Answer 20 targeted profiling questions evaluating your academic strengths, deep interests, core personality style, and long-term career goals.</p>
        <div class="cta-row">
          <button class="btn-primary" id="startBtn">Start Quiz Now</button>
          <button class="small-cta" id="catalogBtn">Explore Full Catalog</button>
        </div>
      </div>
      <aside class="hero-card">
        <h3>Assessment Snapshot</h3>
        <p style="color:var(--text-muted);">This standardized profiling application accurately balances specific behavioral traits to match university programs.</p>
        <div class="features">
          <div><strong>Evaluation Model:</strong> Advanced Logic (3-point matching)</div>
          <div><strong>Scope:</strong> 11 Academic Disciplines</div>
        </div>
      </aside>
    </div>
  </section>

  <!-- QUIZ VIEW -->
  <section id="quizView" class="app-view">
    <div class="progress-wrap-fixed">
      <div class="progress-step-indicator" id="stepIndicator"></div>
      <div class="progress-bar-outer-top">
        <div class="progress-bar-inner-top" id="topProgressFixed"></div>
      </div>
    </div>
    <div class="card">
      <div class="quiz-header">
        <div class="quiz-title" style="font-size: 1.4rem; font-weight: 700; color: var(--accent-blue);">Major Evaluation Engine</div>
        <div style="font-size:1.2rem;font-weight:600;color:var(--primary-blue)" id="progressText">0 / 20 Questions Completed</div>
      </div>
      <div class="question-area">
        <div class="question-tag" id="questionTag">Dimension</div>
        <div class="question-text" id="questionText"></div>
        <form id="optionsForm" class="options" onsubmit="return false"></form>
      </div>
      <div class="quiz-actions">
        <button class="btn-ghost" id="backBtn">← Previous Question</button>
        <button class="btn-next" id="nextBtn">Next Question →</button>
      </div>
    </div>
  </section>

  <!-- RESULTS VIEW -->
  <section id="resultsView" class="app-view">
    <div class="results-wrap">
      <h3 style="color:var(--primary-blue);margin-bottom:25px; font-size: 2.2rem; font-family:'Montserrat', sans-serif;">Your Tailored Career Matches 🏆</h3>
      <div class="results-actions">
        <button class="btn-outline" id="compareBtn">📊 Compare Top Three Tracks</button>
        <button class="btn-outline" id="pdfBtn">⬇️ Export Analysis Report</button>
      </div>
      <div class="results-grid" id="resultsGrid"></div>
      <button class="restart-btn btn-primary" id="restartBtn" style="background: #E74C3C; color:white; box-shadow: 0 8px 20px rgba(231, 76, 60, 0.3);">Reset Evaluation</button>
    </div>
  </section>

  <!-- SEPARATE CATALOG VIEW -->
  <section id="catalogView" class="app-view">
    <div class="catalog-header">
      <h3>Full Major Catalog &amp; Details</h3>
      <p>Browse through comprehensive details on every specialized program tracking path integrated inside our intelligence matrix platform.</p>
    </div>
    <div class="feature-badges">
      <span>Save Results as PDF</span>
      <span>Compare Top Three Majors</span>
      <span>Dark Mode Toggle</span>
      <span>Mobile Responsive Design</span>
    </div>
    <div class="major-grid" id="majorGrid"></div>
  </section>

</main>

<footer>© 2026 MajorMatch— Major Recommendation System. All Rights Reserved.</footer>

<!-- Major Detail Modal -->
<div class="modal-overlay" id="majorModal">
  <div class="modal-content">
    <button class="modal-close" id="modalClose">&times;</button>
    <h4 id="modalTitle"></h4>
    <p id="modalAbout" style="color:var(--text-muted); margin-bottom:18px; font-size:1.1rem;"></p>
    <p style="margin-bottom:10px;"><strong>Top Careers:</strong> <span id="modalCareers"></span></p>
    <p style="margin-bottom:10px;"><strong>Key Hard Skills:</strong> <span id="modalSkills"></span></p>
    <p style="margin-bottom:10px;"><strong>Required Soft Skills:</strong> <span id="modalSoft"></span></p>
    <p><strong>Suggested Courses:</strong> <span id="modalCourses"></span></p>
    <div style="text-align:right; margin-top:30px;">
      <button class="btn-next" id="closeModalBtn">Close Profile</button>
    </div>
  </div>
</div>

<!-- Compare Modal -->
<div class="modal-overlay" id="compareModal">
  <div class="modal-content" style="max-width:950px;">
    <button class="modal-close" id="compareModalClose">&times;</button>
    <h4>Direct Match Structural Comparison</h4>
    <div style="overflow-x:auto;">
      <table class="compare-table" id="compareTable"></table>
    </div>
    <div style="text-align:right; margin-top:20px;">
      <button class="btn-next" id="closeCompareBtn">Close Sheet</button>
    </div>
  </div>
</div>

<!-- Dynamic Notification Alert Modal -->
<div class="modal-overlay" id="alertModal">
  <div class="modal-content" style="max-width: 450px; text-align: center; padding: 40px 30px;">
    <div style="font-size: 3rem; margin-bottom: 15px;">🔒</div>
    <h4 style="font-size: 1.5rem; margin-bottom: 15px;">Evaluation Required</h4>
    <p style="color: var(--text-muted); margin-bottom: 25px;">You must complete the diagnostic quiz before accessing the premium analytical results dashboard interface.</p>
    <button class="btn-next" id="alertModalActionBtn" style="width: 100%;">Start Quiz Now</button>
  </div>
</div>

<script>
  // --- MULTI-DIMENSIONAL DATA MATRICES ---
  const questions = [
    // 🧠 ACADEMIC STRENGTHS
    { category: "Academic Strengths", q: "1) Which discipline space aligns most cleanly with your textbook performance?", o: ["Complex algorithmic structures", "Logistics or corporate economic modeling", "Psychology and social structure metrics", "Visual composition or creative studio design", "Laboratory synthesis and scientific notation", "Calculus and spatial mechanical matrices"] },
    { category: "Academic Strengths", q: "2) In a formal tracking environment, where does your performance score highest naturally?", o: ["Abstract systematic deductions", "Organizational task assignments", "Interpersonal conflict resolutions", "Graphic art production pipelines", "Empirical data isolation labs", "Physical mechanism optimization blueprints"] },
    { category: "Academic Strengths", q: "3) When analyzing a problem field, what toolset do you process with extreme comfort?", o: ["Integrated compilation environments", "Financial spread spreadsheets", "Qualitative observation surveys", "Vector graphics interfaces", "Controlled lab environments", "Calculators and technical physics equipment"] },
    { category: "Academic Strengths", q: "4) What system architecture type makes the most intuitive sense to your brain?", o: ["Boolean statement systems", "Business accounting flows", "Human developmental lifecycles", "Proportional landscape balances", "Molecular structures", "Kinetic system workflows"] },
    { category: "Academic Strengths", q: "5) Which advanced elective track would you easily pass with the lowest stress?", o: ["Discrete Structural Mathematics", "International Trade Economics", "Cognitive Human Behavior", "Digital Compositing & UI Design", "Organic Molecular Biology", "Structural Engineering Statics"] },

    // 🎯 INTERESTS
    { category: "Interests", q: "6) What project topic naturally consumes your unassigned personal hours?", o: ["Automating scripts or application development", "Evaluating emerging business frameworks", "Organizing volunteer networks", "Studying portfolio asset concepts", "Reviewing scientific laboratory journals", "Drafting physical construction patterns"] },
    { category: "Interests", q: "7) If given an unrestricted grant pass to an exposition, which terminal hall are you viewing?", o: ["Artificial Intelligence Solutions", "Global Venture Capital Keynotes", "Human Rights Summit Panels", "Avant-Garde Architectural Exhibits", "Biomedical Engineering Discoveries", "Automotive Propulsion Lab Displays"] },
    { category: "Interests", q: "8) Which product marketplace sector updates do you read regularly online?", o: ["Open-source developer libraries", "Stock exchange dynamics", "Community outreach initiatives", "Creative typography and asset drops", "Ecological or clinical trials", "Hardware prototype documentation"] },
    { category: "Interests", q: "9) What media topic do you enjoy learning or listening to on podcasts?", o: ["Cybersecurity infrastructure networks", "Corporate turnaround consulting case studies", "Sociological experiment analysis", "Animation design histories", "Genomic research trends", "Aerospace infrastructure designs"] },
    { category: "Interests", q: "10) What functional activity category gives you the most reliable spike in engagement?", o: ["Refining logic processes", "Negotiating structural growth steps", "Counseling team dynamics", "Developing brand aesthetics", "Isolating environmental elements", "Configuring complex mechanical rigs"] },

    // 👥 PERSONALITY
    { category: "Personality", q: "11) Which baseline character term describes your collaborative operational style accurately?", o: ["Systematic and data-driven", "Strategic and leadership-oriented", "Empathetic and relationship-focused", "Imaginative and conceptual", "Methodical and verification-driven", "Analytical and practical"] },
    { category: "Personality", q: "12) How does your mind process unexpected roadblocks inside high-pressure settings?", o: ["Isolating root causes step-by-step", "Delegating task distributions strategically", "Calming group emotional states", "Iterating alternative expressive concepts", "Evaluating controlled metrics", "Testing physical modifications directly"] },
    { category: "Personality", q: "13) Select the workplace dynamic layout that satisfies your personality traits optimal:", o: ["Autonomous technical focus blocks", "Dynamic management environments", "Interactive human-centric spaces", "Fluid non-linear creative studios", "Structured, low-variability clean laboratories", "High-activity field infrastructure sites"] },
    { category: "Personality", q: "14) What social configuration aligns with your natural mental batteries?", o: ["Focused independent problem management", "Directing group performance metrics", "One-on-one deep discovery discussions", "Collaborative vision brainstorming", "Objective data review boards", "Practical task troubleshooting clusters"] },
    { category: "Personality", q: "15) When receiving direct criticism, your default mindset moves immediately to:", o: ["Validating logical mechanics", "Reviewing tactical outcomes", "Assessing emotional weight", "Redesigning aesthetic directions", "Cross-checking evidential foundations", "Modifying active tool implementations"] },

    // 🚀 CAREER GOALS
    { category: "Career Goals", q: "16) What core long-term career milestone dictates your path forward?", o: ["Deploying optimized scalable software engines", "Launching high-equity market enterprises", "Mitigating public health vulnerabilities", "Publishing premier creative portfolio collections", "Discovering innovative medical solutions", "Erecting physical infrastructural monuments"] },
    { category: "Career Goals", q: "17) Which primary professional environment sounds most rewarding?", o: ["Enterprise technical campuses", "Fast-growth venture boardrooms", "Public advocacy operations", "Boutique advertising spaces", "Research clinical installations", "Industrial manufacturing grounds"] },
    { category: "Career Goals", q: "18) What role profile do you target inside a multi-million dollar venture project?", o: ["Chief Software Infrastructure Architect", "Chief Operations Manager", "Director of Human Capital Relations", "Creative Brand Specialist", "Lead Research Methodology Evaluator", "Head Structural Operations Engineer"] },
    { category: "Career Goals", q: "19) You measure your lifetime vocational contribution most accurately via:", o: ["Stability of codebases and software loops", "Gross organizational scale and profit margins", "The volume of human lives directly upgraded", "Cultural and artistic asset production visibility", "Empirical data breakthroughs verified by peers", "Physical structures designed and sustained safely"] },
    { category: "Career Goals", q: "20) Which target skill matrix do you intend to master in your upcoming work horizon?", o: ["Machine Learning & Neural Network Programming", "Capital Asset Allocation & Business Scaling", "Behavioral Diagnosis & Public Program Design", "Advanced Interactive UX & Aesthetic Systems", "Biochemical Isolation & Data Modeling", "Precision Systems Engineering & Thermodynamics"] }
  ];

  const majors = [
    { id: "cs", name: "Computer Science", index: 0, icon: "💻", keySkills: "Java/Python, Algorithm Optimization, Data Structures, Git Logic", reason: "You display high affinity for systematic logical constraints, technological scaling, and direct structural programmatic creation loops.", careers: "Software Developer, Systems Engineer, AI Engineering Specialist", softSkills: "Logical Articulation, Technical Teamwork, Structural Patience", courses: "CS101 Intro to Systems, Advanced Data Structures, Automata Theory" },
    { id: "bus", name: "Business Administration", index: 1, icon: "💼", keySkills: "Financial Strategy, Market Analysis, Operational Leadership, KPI Tracking", reason: "Your profile leans heavily toward group dynamic optimization, market metrics analysis, and high-stakes entrepreneurial leadership.", careers: "Operations Director, Enterprise Consultant, Venture Capitalist", softSkills: "Persuasive Presentation, Operational Agility, Negotiation Tactics", courses: "Strategic Management Principles, Corporate Finance, Microeconomic Strategy" },
    { id: "sw", name: "Social Work & Public Health", index: 2, icon: "🤝", keySkills: "Crisis Counseling, Behavioral Diagnosis, Public Policy Research, Advocacy", reason: "You emphasize deep emotional empathy, humanitarian development, systematic behavioral updates, and community welfare solutions.", careers: "Clinical Care Coordinator, Healthcare Advocate, Social Policy Advisor", softSkills: "Active Empathetic Listening, Interpersonal De-escalation, Cultural Competence", courses: "Human Behavior Dynamics, Foundations of Social Policy, Community Intervention" },
    { id: "gd", name: "Graphic Design & UI/UX", index: 3, icon: "🎨", keySkills: "Vector Compositing, Wireframing, Color Theory, Typography, Interaction Architecture", reason: "You combine spatial aesthetic refinement with intuitive interaction concepts to build visual pathways and digital assets.", careers: "Creative Director, Lead UX Specialist, Visual Brand Designer", softSkills: "Constructive Critique Processing, Ideation Flexibility, Visual Storytelling", courses: "Visual Communication Design, User Interface Frameworks, Portfolio Lab" },
    { id: "bio", name: "Biology & Life Sciences", index: 4, icon: "🔬", keySkills: "Microscopic Isolation, Statistical Inference, Assay Testing, Chromatography", reason: "You excel at empirical verification methods, laboratory deduction frameworks, clinical trials, and environmental tracking data.", careers: "Clinical Research Analyst, Laboratory Chemist, Biotechnologist", softSkills: "Observational Precision, Methodological Integrity, Technical Documentation", courses: "Molecular Genetics, General Biochemistry, Quantitative Chemical Analysis" },
    { id: "eng", name: "Engineering Mechanics", index: 5, icon: "🛠️", keySkills: "CAD Modeling, Structural Analysis, Finite Element Methods, Stress Calculations", reason: "You synthesize advanced calculations with mechanical application blueprints to design and optimize real-world infrastructure systems.", careers: "Mechanical Design Architect, Structural Engineer, Robotics Integrator", softSkills: "Cross-Functional Safety Focus, Analytical Troubleshooting, Collaborative Precision", courses: "Engineering Statics & Dynamics, Thermodynamics Foundations, Fluid Mechanics" }
  ];

  // --- STATE CONTROLLERS ---
  let currentIndex = 0;
  let selectedAnswers = Array(questions.length).fill(null);
  let scores = Array(majors.length).fill(0);
  const maxPossibleScore = questions.length * 3;
  let lastRanking = [];

  // --- DOM CACHE ---
  const views = document.querySelectorAll('.app-view');
  const navLinks = document.querySelectorAll('.nav-link');
  const startBtn = document.getElementById('startBtn');
  const catalogBtn = document.getElementById('catalogBtn');
  const nextBtn = document.getElementById('nextBtn');
  const backBtn = document.getElementById('backBtn');
  const restartBtn = document.getElementById('restartBtn');
  const resultsGrid = document.getElementById('resultsGrid');
  const topProgressFixed = document.getElementById('topProgressFixed');
  const progressText = document.getElementById('progressText');
  const questionText = document.getElementById('questionText');
  const questionTag = document.getElementById('questionTag');
  const optionsForm = document.getElementById('optionsForm');
  const stepIndicator = document.getElementById('stepIndicator');
  const compareBtn = document.getElementById('compareBtn');
  const pdfBtn = document.getElementById('pdfBtn');
  const majorGrid = document.getElementById('majorGrid');
  
  // Modals
  const majorModal = document.getElementById('majorModal');
  const modalClose = document.getElementById('modalClose');
  const closeModalBtn = document.getElementById('closeModalBtn');
  const compareModal = document.getElementById('compareModal');
  const compareModalClose = document.getElementById('compareModalClose');
  const closeCompareBtn = document.getElementById('closeCompareBtn');
  const compareTable = document.getElementById('compareTable');
  const alertModal = document.getElementById('alertModal');
  const alertModalActionBtn = document.getElementById('alertModalActionBtn');

  // --- ROUTING ENGINE ---
  function switchView(targetViewId) {
    if (targetViewId === 'resultsView' && lastRanking.length === 0) {
      openAlertModal();
      return;
    }

    views.forEach(view => {
      view.classList.remove('view-active');
      if(view.id === targetViewId) view.classList.add('view-active');
    });

    navLinks.forEach(link => {
      link.classList.remove('active');
      if(link.getAttribute('data-target') === targetViewId) link.classList.add('active');
    });

    if(targetViewId === 'quizView' && currentIndex === 0) {
      renderQuestion(0);
    }
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }

  navLinks.forEach(link => {
    link.addEventListener('click', (e) => {
      const target = link.getAttribute('data-target');
      if (target === 'quizView' && currentIndex === 0) {
        switchView('homeView');
        setTimeout(() => {
          startBtn.focus();
          startBtn.style.outline = '3px solid var(--accent-blue)';
          setTimeout(() => startBtn.style.outline = 'none', 1200);
        }, 300);
      } else {
        switchView(target);
      }
    });
  });

  // --- ACCESS GUARD ALERTS ---
  function openAlertModal() {
    alertModal.classList.add('open');
  }
  alertModalActionBtn.addEventListener('click', () => {
    alertModal.classList.remove('open');
    switchView('quizView');
  });
  alertModal.addEventListener('click', (e) => { if(e.target === alertModal) alertModal.classList.remove('open'); });

  // --- QUIZ ENGINE CORE ---
  function renderStepIndicator() {
    stepIndicator.innerHTML = '';
    const totalSteps = questions.length;
    const indicatorInner = document.createElement('div');
    indicatorInner.style.cssText = 'display:flex; justify-content:space-between; align-items:center; width:100%;';

    for (let i = 0; i < totalSteps; i++) {
      const dot = document.createElement('div');
      dot.style.cssText = 'width:12px; height:12px; border-radius:50%; transition:all 0.3s ease; flex-shrink:0; z-index:2;';

      if (i < currentIndex) {
        dot.style.background = 'var(--success)';
      } else if (i === currentIndex) {
        dot.style.background = 'var(--primary-blue)';
        dot.style.transform = 'scale(1.4)';
        dot.style.boxShadow = '0 0 0 5px rgba(46, 134, 193, 0.2)';
      } else {
        dot.style.background = 'var(--border-color)';
      }
      indicatorInner.appendChild(dot);

      if (i < totalSteps - 1) {
        const line = document.createElement('div');
        line.style.cssText = 'height:2px; flex-grow:1; margin:0 2px; transition:background 0.3s ease;';
        line.style.background = i < currentIndex ? 'var(--success)' : 'var(--border-color)';
        indicatorInner.appendChild(line);
      }
    }
    stepIndicator.appendChild(indicatorInner);
  }

  function updateProgress(){
    const percent = (currentIndex / questions.length) * 100;
    progressText.innerText = `${currentIndex} / ${questions.length} Questions Completed`;
    topProgressFixed.style.width = percent + '%';
    backBtn.disabled = currentIndex === 0;
    backBtn.style.opacity = currentIndex === 0 ? 0.4 : 1;
    nextBtn.textContent = (currentIndex === questions.length - 1) ? "Compile Profile" : "Next Question →";
    renderStepIndicator();
  }

  function renderQuestion(idx){
    const currentQ = questions[idx];
    questionTag.textContent = currentQ.category;
    questionText.textContent = currentQ.q;
    optionsForm.innerHTML = '';

    currentQ.o.forEach((opt, index)=>{
      const id = `q${idx}_opt_${index}`;
      const label = document.createElement('label');
      label.className = 'option';
      label.setAttribute('for', id);

      const input = document.createElement('input');
      input.type = 'radio';
      input.name = 'q_opt';
      input.value = index; // Map index straight to major profile position
      input.id = id;

      if(selectedAnswers[idx] !== null && selectedAnswers[idx] === index){
        input.checked = true;
        label.classList.add('selected');
      }

      label.addEventListener('click', (e) => {
        if (e.target.tagName !== 'INPUT') {
          document.querySelectorAll('.option').forEach(el => el.classList.remove('selected'));
          label.classList.add('selected');
          input.checked = true;
          selectedAnswers[idx] = index;
        }
      });

      label.appendChild(input);
      const textSpan = document.createElement('span');
      textSpan.textContent = opt;
      label.appendChild(textSpan);
      optionsForm.appendChild(label);
    });

    updateProgress();
  }

  function calculateResults() {
    scores = Array(majors.length).fill(0);
    selectedAnswers.forEach((majorIndex) => {
      if (majorIndex !== null && majorIndex < scores.length) {
        scores[majorIndex] += 3; // Direct matrix mapping logic
      }
    });
  }

  function showResultsView() {
    resultsGrid.innerHTML = '';
    const sorted = majors.map((m) => ({ major: m, score: scores[m.index] })).sort((a, b) => b.score - a.score);
    lastRanking = sorted.slice(0, 3);

    lastRanking.forEach((item, rankingIndex) => {
      const pct = ((item.score / maxPossibleScore) * 100).toFixed(0);
      const div = document.createElement('div');
      div.className = 'result-item';
      if(rankingIndex === 0) div.classList.add('top-match');

      div.innerHTML = `
        <h3>
          <span>${item.major.icon} ${item.major.name}</span>
          <span class="match-badge">${pct}% Match</span>
        </h3>
        
        <div class="result-section-block">
          <h5>Reason</h5>
          <p>${item.major.reason}</p>
        </div>

        <div class="result-section-block">
          <h5>Possible Careers</h5>
          <p>${item.major.careers}</p>
        </div>

        <div class="result-section-block">
          <h5>Required Soft Skills</h5>
          <p>${item.major.softSkills}</p>
        </div>

        <div class="result-section-block">
          <h5>Suggested University Courses</h5>
          <p>${item.major.courses}</p>
        </div>

        <button class="major-detail-btn" data-id="${item.major.id}">Inspect Curriculum Specs</button>
      `;
      resultsGrid.appendChild(div);
    });

    switchView('resultsView');
  }

  // --- CATALOG BUILDER ---
  function initCatalog() {
    majorGrid.innerHTML = '';
    majors.forEach(m => {
      const card = document.createElement('div');
      card.className = 'major-card';
      card.innerHTML = `
        <div style="display:flex;align-items:center;gap:15px;margin-bottom:15px">
          <div class="major-icon" style="display:flex; justify-content:center; align-items:center;">${m.icon}</div>
          <div style="font-weight:700; font-size:1.3rem; color:var(--primary-blue); font-family:'Montserrat', sans-serif;">${m.name}</div>
        </div>
        <p style="color:var(--text-muted); margin-bottom:18px;">${m.reason}</p>
        <div style="font-size:0.95rem; margin-bottom:6px;"><strong>Key Track Skills:</strong> ${m.keySkills}</div>
        <div style="font-size:0.95rem;"><strong>Top Target Fields:</strong> ${m.careers}</div>
      `;
      majorGrid.appendChild(card);
    });
  }

  // --- MODAL HANDLING ---
  function openMajorModal(id) {
    const m = majors.find(item => item.id === id);
    if(!m) return;
    document.getElementById('modalTitle').textContent = `${m.icon} ${m.name}`;
    document.getElementById('modalAbout').textContent = m.reason;
    document.getElementById('modalCareers').textContent = m.careers;
    document.getElementById('modalSkills').textContent = m.keySkills;
    document.getElementById('modalSoft').textContent = m.softSkills;
    document.getElementById('modalCourses').textContent = m.courses;
    majorModal.classList.add('open');
  }

  resultsGrid.addEventListener('click', (e) => {
    const btn = e.target.closest('.major-detail-btn');
    if(btn) openMajorModal(btn.getAttribute('data-id'));
  });

  modalClose.addEventListener('click', () => majorModal.classList.remove('open'));
  closeModalBtn.addEventListener('click', () => majorModal.classList.remove('open'));
  majorModal.addEventListener('click', (e) => { if(e.target === majorModal) majorModal.classList.remove('open'); });

  // --- RECTILINEAR MATRICES MATRIX COMPARISON ---
  compareBtn.addEventListener('click', () => {
    if(lastRanking.length === 0) return;
    
    let head = '<tr><th>Category Metrics</th>' + lastRanking.map(r => `<th>${r.major.icon} ${r.major.name}</th>`).join('') + '</tr>';
    let matchPct = '<tr><td><strong>Match Evaluation</strong></td>' + lastRanking.map(r => `<td><strong>${((r.score / maxPossibleScore)*100).toFixed(0)}% Match</strong></td>`).join('') + '</tr>';
    let coreCareers = '<tr><td><strong>Target Outlets</strong></td>' + lastRanking.map(r => `<td>${r.major.careers}</td>`).join('') + '</tr>';
    let keyHard = '<tr><td><strong>Technical Focus</strong></td>' + lastRanking.map(r => `<td>${r.major.keySkills}</td>`).join('') + '</tr>';
    let keySoft = '<tr><td><strong>Soft Skills</strong></td>' + lastRanking.map(r => `<td>${r.major.softSkills}</td>`).join('') + '</tr>';
    let classes = '<tr><td><strong>Sample Track Curriculum</strong></td>' + lastRanking.map(r => `<td>${r.major.courses}</td>`).join('') + '</tr>';

    compareTable.innerHTML = head + matchPct + coreCareers + keyHard + keySoft + classes;
    compareModal.classList.add('open');
  });

  compareModalClose.addEventListener('click', () => compareModal.classList.remove('open'));
  closeCompareBtn.addEventListener('click', () => compareModal.classList.remove('open'));
  compareModal.addEventListener('click', (e) => { if(e.target === compareModal) compareModal.classList.remove('open'); });

  // --- PDF EXPORT FUNCTION ---
  pdfBtn.addEventListener('click', () => {
    if(lastRanking.length === 0) return;
    const { jsPDF } = window.jspdf;
    const doc = new jsPDF();
    let cursorY = 20;

    doc.setFontSize(20);
    doc.text('MajorMatch Professional Profile Analysis', 14, cursorY);
    cursorY += 12;
    doc.setFontSize(10);
    doc.text(`Evaluation Date: ${new Date().toLocaleDateString()}`, 14, cursorY);
    cursorY += 15;

    lastRanking.forEach((item, index) => {
      const pct = ((item.score / maxPossibleScore) * 100).toFixed(0);
      doc.setFontSize(14);
      doc.text(`${index + 1}. ${item.major.name} (${pct}% Fit Profile)`, 14, cursorY);
      cursorY += 8;
      
      doc.setFontSize(10);
      const reasonSplit = doc.splitTextToSize(`Alignment Assessment: ${item.major.reason}`, 180);
      doc.text(reasonSplit, 14, cursorY);
      cursorY += (reasonSplit.length * 5) + 4;

      const careerSplit = doc.splitTextToSize(`Target Outlets: ${item.major.careers}`, 180);
      doc.text(careerSplit, 14, cursorY);
      cursorY += (careerSplit.length * 5) + 8;
    });

    doc.save('MajorMatch-Comprehensive-Profile.pdf');
  });

  // --- EVENT ATTACHMENTS ---
  startBtn.addEventListener('click', () => switchView('quizView'));
  catalogBtn.addEventListener('click', () => switchView('catalogView'));

  nextBtn.addEventListener('click', () => {
    if (selectedAnswers[currentIndex] === null) {
      alert('Please isolate a profile behavior choice before moving forward.');
      return;
    }
    if (currentIndex < questions.length - 1) {
      currentIndex++;
      renderQuestion(currentIndex);
    } else {
      calculateResults();
      showResultsView();
    }
  });

  backBtn.addEventListener('click', () => {
    if (currentIndex > 0) {
      currentIndex--;
      renderQuestion(currentIndex);
    }
  });

  restartBtn.addEventListener('click', () => {
    currentIndex = 0;
    selectedAnswers = Array(questions.length).fill(null);
    lastRanking = [];
    switchView('quizView');
  });

  // --- GLOBAL THEME MANAGER ---
  const themeToggle = document.getElementById('themeToggle');
  function applyTheme(isDark){
    document.body.classList.toggle('dark-mode', isDark);
    themeToggle.textContent = isDark ? '☀️ Light Mode' : '🌙 Dark Mode';
    localStorage.setItem('majormatch-theme', isDark ? 'dark' : 'light');
  }
  applyTheme(localStorage.getItem('majormatch-theme') === 'dark');
  themeToggle.addEventListener('click', () => applyTheme(!document.body.classList.contains('dark-mode')));

  // --- MOBILE NAV ---
  const navToggle = document.getElementById('navToggle');
  const mainNav = document.getElementById('mainNav');
  navToggle.addEventListener('click', () => mainNav.classList.toggle('nav-open'));
  mainNav.querySelectorAll('a').forEach(a => a.addEventListener('click', () => mainNav.classList.remove('nav-open')));

  // --- INIT APPLICATION ---
  initCatalog();
</script>
</body>
</html>
