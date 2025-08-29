# Ex01 Portfolio
## Date:29/08/2025
## Name:Muhammed Aiman S
## Reg No:212224240097

## AIM
To create a Portfolio using HTML and CSS.

## ALGORITHM
### STEP 1
Create an HTML file (index.html)

### STEP 2
Create a CSS file (style.css)

### STEP 3
Include a navigation bar with links to different sections.

### STEP 4
Add structured sections for introduction, about, projects, and contact details.

### STEP 5
Define global styles for fonts, colors, and layout.

### STEP 6
Style the header, navigation bar, and sections.

### STEP 7
Use Flexbox or CSS Grid for layout design.

### STEP 8
Add hover effects and transitions for interactivity.

### STEP 9
Add Images and Media.

### STEP 10
Use optimized images for a professional look.

### STEP 11
Open the HTML file in a browser to check layout and functionality.

### STEP 12
Fix styling issues and refine content placement.

### STEP 13
Deploy the Portfolio.

### STEP 14
Upload to GitHub Pages for free hosting.

## PROGRAM
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Portfolio Experiment</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#f6f7fb;
      --card:#ffffff;
      --text:#1f2937;
      --muted:#6b7280;
      --accent:#3b82f6; /* blue */
      --accent-2:#0ea5e9; /* sky */
      --ring:#e5e7eb;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0; background:var(--bg); color:var(--text);
      font-family:Inter, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji", "Segoe UI Emoji";
      line-height:1.55;
    }
    .page{max-width:1100px; margin:40px auto; padding:24px;}

    .shell{
      background:var(--card);
      border-radius:20px; overflow:hidden;
      box-shadow:0 10px 30px rgba(2,8,20,.06);
      border:1px solid var(--ring);
    }

    /* Header */
    .header{position:relative; padding:36px 36px 28px; background:linear-gradient(135deg, rgba(59,130,246,.08), rgba(14,165,233,.08));}
    .header-grid{
      display:grid; grid-template-columns: 96px 1fr auto; gap:24px; align-items:center;
    }
    .avatar{
      width:96px; height:96px; border-radius:24px; overflow:hidden; background:#dbeafe; display:grid; place-items:center; border:2px solid rgba(59,130,246,.25);
    }
    .avatar img{width:100%; height:100%; object-fit:cover}
    .id h1{font:700 34px/1.1 Poppins, Inter, sans-serif; margin:0 0 6px}
    .id .role{font:600 16px/1.3 Inter, sans-serif; color:var(--accent)}
    .id .tagline{color:var(--muted); margin-top:6px}
    .cta{display:flex; gap:12px; flex-wrap:wrap}
    .btn{appearance:none; border:1px solid var(--accent); background:var(--accent); color:#fff; padding:10px 14px; border-radius:12px; font-weight:600; text-decoration:none; box-shadow:0 6px 14px rgba(59,130,246,.25)}
    .btn.ghost{background:transparent; color:var(--accent); border-color:rgba(59,130,246,.4)}

    /* Body layout */
    .body{display:grid; grid-template-columns: 300px 1fr; gap:28px; padding:28px;}
    @media (max-width: 900px){
      .header-grid{grid-template-columns: 72px 1fr;}
      .cta{grid-column:1 / -1}
      .body{grid-template-columns:1fr}
    }

    /* Sidebar */
    .side .card{background:#fff; border:1px solid var(--ring); border-radius:16px; padding:18px; margin-bottom:18px}
    .section-title{display:flex; align-items:center; gap:10px; margin:0 0 14px; font-weight:700; color:#0f172a; font-family:Poppins, Inter, sans-serif}
    .section-title::before{content:""; width:8px; height:18px; border-radius:6px; background:linear-gradient(180deg, var(--accent), var(--accent-2)); display:inline-block}
    .list{list-style:none; padding:0; margin:0; display:grid; gap:10px}
    .list li{display:grid; gap:4px}
    .muted{color:var(--muted); font-size:14px}

    /* Skills */
    .skill{display:grid; grid-template-columns:1fr auto; gap:8px; align-items:center}
    .meter{height:8px; background:#eef2ff; border-radius:999px; position:relative; overflow:hidden; border:1px solid #e5e7eb}
    .meter > span{position:absolute; left:0; top:0; bottom:0; width:60%; background:linear-gradient(90deg, var(--accent), var(--accent-2)); border-radius:999px}

    /* Content cards */
    .main .card{background:#fff; border:1px solid var(--ring); border-radius:16px; padding:20px; margin-bottom:18px}
    .timeline{position:relative;}
    .timeline::before{content:""; position:absolute; left:10px; top:6px; bottom:6px; width:2px; background:linear-gradient(180deg, var(--ring), #c7d2fe)}
    .item{position:relative; padding-left:36px; margin:18px 0}
    .item::before{content:""; position:absolute; left:4px; top:2px; width:14px; height:14px; border:3px solid #93c5fd; background:#ffffff; border-radius:50%}
    .item h3{margin:0 0 4px; font:600 18px/1.25 Inter, sans-serif}
    .item .where{font-weight:600; color:#0f172a}
    .item .period{color:var(--muted); font-size:14px}
    .item p{margin:8px 0 0}

    .grid{display:grid; grid-template-columns:repeat(2, 1fr); gap:16px}
    @media (max-width: 780px){.grid{grid-template-columns:1fr}}
    .badge{display:inline-block; padding:6px 10px; border-radius:999px; border:1px solid var(--ring); font-size:12px; color:#0f172a; background:#f8fafc}

    /* Footer */
    .footer{padding:14px 24px 22px; display:flex; justify-content:space-between; align-items:center; border-top:1px solid var(--ring); color:var(--muted); font-size:14px}

    /* Print */
    @media print{
      body{background:#fff}
      .page{margin:0; padding:0}
      .shell{box-shadow:none; border:none; border-radius:0}
      .header{background:#fff}
      .btn{display:none}
    }
  </style>
</head>
<body>
  <div class="page">
    <div class="shell">
      <!-- HEADER -->
      <header class="header">
        <div class="header-grid">
          <div class="avatar">
            <!-- Profile photo -->
            <img src="WhatsApp Image 2025-08-29 at 15.52.49_5f8a851f.jpg" alt="Profile" />
          </div>
          <div class="id">
            <h1>Muhammed Aiman</h1>
            <div class="role">UI/UX Designer & Front-End Developer</div>
            <p class="tagline">I craft clean, accessible interfaces and bring ideas to life on the web.</p>
          </div>
          <div class="cta">
            <a class="btn" href="#contact">Contact Me</a>
            <a class="btn ghost" href="#projects">View Projects</a>
          </div>
        </div>
      </header>

      <!-- BODY -->
      <div class="body">
        <!-- SIDEBAR -->
        <aside class="side">
          <section class="card">
            <h2 class="section-title">Profile</h2>
            <p class="muted">Enthusiastic designer with a passion for delightful user experiences, systems thinking, and pixel-perfect implementation.</p>
          </section>

          <section class="card" id="contact">
            <h2 class="section-title">Contact</h2>
            <ul class="list">
              <li>
                <strong>Email</strong>
                <span class="muted">aimanraja52@gmail.com</span>
              </li>
              <li>
                <strong>Phone</strong>
                <span class="muted">8870167403</span>
              </li>
              <li>
                <strong>Birthday</strong>
                <span class="muted">April 6, 2006</span>
              </li>
              <li>
                <strong>Location</strong>
                <span class="muted">Kochi, India</span>
              </li>
              <li>
                <strong>Website</strong>
                <span class="muted">example.dev</span>
              </li>
            </ul>
          </section>

          <section class="card">
            <h2 class="section-title">Skills</h2>
            <div class="list">
              <div class="skill">
                <div>Figma</div>
                <div class="muted">90%</div>
                <div class="meter"><span style="width:90%"></span></div>
              </div>
              <div class="skill">
                <div>HTML/CSS</div>
                <div class="muted">95%</div>
                <div class="meter"><span style="width:95%"></span></div>
              </div>
              <div class="skill">
                <div>JavaScript</div>
                <div class="muted">80%</div>
                <div class="meter"><span style="width:80%"></span></div>
              </div>
              <div class="skill">
                <div>React</div>
                <div class="muted">75%</div>
                <div class="meter"><span style="width:75%"></span></div>
              </div>
            </div>
          </section>
        </aside>

        <!-- MAIN CONTENT -->
        <main class="main">
          <section class="card">
            <h2 class="section-title">Experience</h2>
            <div class="timeline">
              <div class="item">
                <h3>Senior Product Designer <span class="where">• Acme Corp</span></h3>
                <div class="period">2023 — Present</div>
                <p>Leading design for the commerce team; shipped a multi-step checkout that increased conversion by 12%.</p>
              </div>
              <div class="item">
                <h3>UI Engineer <span class="where">• Pixel Labs</span></h3>
                <div class="period">2021 — 2023</div>
                <p>Built a reusable component library in React; reduced design-dev handoff time by 30%.</p>
              </div>
              <div class="item">
                <h3>Design Intern <span class="where">• Studio Nine</span></h3>
                <div class="period">2020 — 2021</div>
                <p>Prototyped mobile interactions and conducted usability tests for early-stage features.</p>
              </div>
            </div>
          </section>

          <section class="card" id="projects">
            <h2 class="section-title">Projects</h2>
            <div class="grid">
              <div class="card" style="margin:0">
                <h3 style="margin-top:0">Portfolio v3</h3>
                <p class="muted">A fast, accessible personal site built with semantic HTML and CSS Grid.</p>
              </div>
              <div class="card" style="margin:0">
                <h3 style="margin-top:0">Shop UI Kit</h3>
                <p class="muted">Design system of 40+ components with responsive tokens and guidelines.</p>
              </div>
            </div>
          </section>

          <section class="card">
            <h2 class="section-title">Education</h2>
            <div class="timeline">
              <div class="item">
                <h3>B.Tech in Computer Science <span class="where">• Your University</span></h3>
                <div class="period">2019 — 2023</div>
                <p>Graduated with First Class; led the Design Club and organized 3 hackathons.</p>
              </div>
            </div>
          </section>
        </main>
      </div>

      <div class="footer">
        <span>© 2025 Muhammed Aiman</span>
        <span>Available for freelance • aimanraja52@gmail.com</span>
      </div>
    </div>
  </div>
</body>
</html>
```

## OUTPUT
<img width="1895" height="1088" alt="Screenshot 2025-08-29 160256" src="https://github.com/user-attachments/assets/066cb531-20c9-460d-b5a9-6d4323a001eb" />

<img width="1899" height="577" alt="Screenshot 2025-08-29 160512" src="https://github.com/user-attachments/assets/bc60a3c2-d268-48ae-959a-fa3827510d16" />

## RESULT
The program for creating Portfolio using HTML and CSS is executed successfully.
