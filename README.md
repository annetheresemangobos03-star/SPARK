<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SPARK | Sustained Pages for Active Reading Knowledge</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700;800&family=Playfair+Display:wght@600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root{--primary:#FF6B35;--secondary:#F7C548;--accent:#2EC4B6;--dark:#1A1A2E;--light:#FFF9F0;--white:#FFF}
        *{margin:0;padding:0;box-sizing:border-box}
        body{font-family:'Poppins',sans-serif;background:var(--light);color:var(--dark);line-height:1.7}
        nav{position:fixed;top:0;width:100%;background:rgba(255,255,255,0.98);padding:1rem 5%;display:flex;justify-content:space-between;align-items:center;z-index:1000;box-shadow:0 2px 20px rgba(0,0,0,0.08)}
        .logo{display:flex;align-items:center;gap:10px;font-size:1.4rem;font-weight:800;color:var(--primary);text-decoration:none}
        .logo-icon{width:42px;height:42px;background:linear-gradient(135deg,#FF6B35,#F7C548);border-radius:10px;display:flex;align-items:center;justify-content:center;color:white;font-size:1.2rem}
        .nav-links{display:flex;gap:2rem;list-style:none}
        .nav-links a{text-decoration:none;color:var(--dark);font-weight:500;transition:.3s}
        .nav-links a:hover{color:var(--primary)}
        .cta-btn{background:linear-gradient(135deg,#FF6B35,#F7C548);color:white;padding:0.7rem 1.5rem;border-radius:50px;text-decoration:none;font-weight:600}
        .hero{min-height:100vh;display:flex;align-items:center;padding:7rem 5% 4rem;background:linear-gradient(135deg,#FFF9F0,#FFE8D6);position:relative;overflow:hidden}
        .hero::before{content:'';position:absolute;top:-25%;right:-10%;width:500px;height:500px;background:radial-gradient(circle,rgba(255,107,53,0.15),transparent 70%);border-radius:50%}
        .hero-content{flex:1;max-width:600px;z-index:1}
        .hero-badge{display:inline-block;background:white;padding:0.5rem 1.2rem;border-radius:50px;font-size:0.85rem;font-weight:600;color:var(--primary);margin-bottom:1.2rem;box-shadow:0 5px 20px rgba(0,0,0,0.08)}
        .hero h1{font-family:'Playfair Display',serif;font-size:clamp(2.2rem,4.5vw,3.5rem);line-height:1.2;margin-bottom:1.2rem}
        .hero h1 span{color:var(--primary)}
        .hero p{font-size:1.1rem;color:#555;margin-bottom:1.8rem}
        .hero-buttons{display:flex;gap:1rem;flex-wrap:wrap}
        .btn-secondary{background:white;color:var(--dark);padding:0.7rem 1.5rem;border-radius:50px;text-decoration:none;font-weight:600;transition:.3s;border:2px solid transparent}
        .btn-secondary:hover{border-color:var(--primary);color:var(--primary)}
        .hero-visual{flex:1;display:flex;justify-content:center;position:relative}
        .floating-cards{position:relative;width:320px;height:320px}
        .float-card{position:absolute;background:white;border-radius:18px;padding:1.2rem;box-shadow:0 15px 40px rgba(0,0,0,0.1);animation:float 6s ease-in-out infinite;display:flex;align-items:center;gap:0.8rem}
        .float-card:nth-child(1){top:5%;left:5%}
        .float-card:nth-child(2){top:35%;right:0}
        .float-card:nth-child(3){bottom:10%;left:15%}
        .float-card-icon{width:42px;height:42px;border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:1.1rem}
        .float-card:nth-child(1) .float-card-icon{background:rgba(255,107,53,0.15);color:var(--primary)}
        .float-card:nth-child(2) .float-card-icon{background:rgba(46,196,182,0.15);color:var(--accent)}
        .float-card:nth-child(3) .float-card-icon{background:rgba(247,197,72,0.15);color:var(--secondary)}
        .float-card h4{font-size:0.85rem}
        .float-card p{font-size:0.7rem;color:#888;margin:0}
        @keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-15px)}}
        .section{padding:5rem 5%}
        .section-header{text-align:center;max-width:650px;margin:0 auto 3rem}
        .section-header h2{font-family:'Playfair Display',serif;font-size:2.3rem;margin-bottom:0.5rem}
        .section-header .subtitle{color:var(--primary);font-weight:600;font-size:0.85rem;text-transform:uppercase;letter-spacing:2px}
        .about{background:var(--white)}
        .about-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:1.8rem;max-width:1000px;margin:0 auto}
        .about-card{background:var(--light);padding:1.8rem;border-radius:18px;transition:.3s}
        .about-card:hover{transform:translateY(-8px);box-shadow:0 18px 45px rgba(0,0,0,0.1)}
        .about-card .icon{width:60px;height:60px;border-radius:14px;display:flex;align-items:center;justify-content:center;font-size:1.5rem;margin-bottom:1rem}
        .about-card:nth-child(1) .icon{background:rgba(255,107,53,0.15);color:var(--primary)}
        .about-card:nth-child(2) .icon{background:rgba(46,196,182,0.15);color:var(--accent)}
        .about-card:nth-child(3) .icon{background:rgba(247,197,72,0.15);color:var(--secondary)}
        .about-card h3{margin-bottom:0.7rem;font-size:1.15rem}
        .about-card p{color:#666;font-size:0.9rem}
        .research{background:var(--dark);color:white}
        .research h2{color:white}
        .research-box{background:rgba(255,255,255,0.03);border-left:4px solid var(--primary);padding:1.8rem;border-radius:0 18px 18px 0;margin-bottom:1.5rem}
        .research-box h4{color:var(--secondary);margin-bottom:0.8rem;display:flex;align-items:center;gap:8px}
        .research-box p{opacity:0.9;margin-bottom:0.8rem}
        .research-box ul{list-style:none}
        .research-box li{padding:0.4rem 0;padding-left:1.4rem;position:relative}
        .research-box li::before{content:'→';position:absolute;left:0;color:var(--accent)}
        .objectives-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:1.3rem;max-width:1000px;margin:0 auto}
        .objective-card{background:white;padding:1.5rem;border-radius:14px;box-shadow:0 8px 30px rgba(0,0,0,0.05);display:flex;gap:1rem}
        .objective-number{width:42px;height:42px;background:linear-gradient(135deg,#FF6B35,#F7C548);border-radius:10px;display:flex;align-items:center;justify-content:center;color:white;font-weight:700;flex-shrink:0}
        .objective-content h4{margin-bottom:0.2rem;font-size:1rem}
        .objective-content p{color:#666;font-size:0.8rem}
        .workshops{background:white}
        .workshop-tabs{display:flex;justify-content:center;gap:0.8rem;margin-bottom:2.5rem;flex-wrap:wrap}
        .tab-btn{padding:0.8rem 1.5rem;border:none;background:var(--light);border-radius:50px;font-size:0.9rem;font-weight:600;cursor:pointer;transition:.3s;font-family:'Poppins',sans-serif}
        .tab-btn.active,.tab-btn:hover{background:var(--primary);color:white}
        .workshop-content{display:none;animation:fadeIn .5s}
        .workshop-content.active{display:block}
        @keyframes fadeIn{from{opacity:0}to{opacity:1}}
        .session-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(320px,1fr));gap:1.8rem;max-width:1000px;margin:0 auto}
        .session-card{background:var(--light);border-radius:18px;overflow:hidden}
        .session-header{background:linear-gradient(135deg,#FF6B35,#F7C548);color:white;padding:1.2rem 1.4rem;display:flex;justify-content:space-between;align-items:center}
        .session-header h4{font-size:1rem}
        .session-time{background:rgba(255,255,255,0.25);padding:0.25rem 0.8rem;border-radius:20px;font-size:0.75rem}
        .session-body{padding:1.3rem}
        .activity-item{display:flex;gap:0.9rem;padding:0.7rem 0;border-bottom:1px solid #eee}
        .activity-item:last-child{border:none}
        .activity-icon{width:36px;height:36px;background:rgba(46,196,182,0.15);border-radius:8px;display:flex;align-items:center;justify-content:center;color:var(--accent);flex-shrink:0}
        .activity-content h5{font-size:0.9rem;margin-bottom:0.15rem}
        .activity-content p{font-size:0.75rem;color:#666}
        .activities{background:var(--dark);color:white}
        .activities .section-header h2,.activities .section-header p{color:white}
        .activities-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(230px,1fr));gap:1.3rem;max-width:1000px;margin:0 auto}
        .activity-card{background:rgba(255,255,255,0.05);border-radius:14px;padding:1.3rem;transition:.3s;border:1px solid rgba(255,255,255,0.1)}
        .activity-card:hover{background:rgba(255,255,255,0.1);transform:translateY(-4px)}
        .activity-card .icon{width:45px;height:45px;background:rgba(255,107,53,0.2);border-radius:10px;display:flex;align-items:center;justify-content:center;color:var(--primary);margin-bottom:0.9rem;font-size:1.2rem}
        .activity-card h4{margin-bottom:0.4rem;font-size:1rem}
        .activity-card p{font-size:0.8rem;opacity:0.8}
        footer{background:#111;color:white;padding:2.5rem 5%;text-align:center}
        footer p{opacity:0.7;font-size:0.9rem}
        @media(max-width:768px){.hero{flex-direction:column;text-align:center;padding-top:6rem}.hero-content{max-width:100%}.hero-buttons{justify-content:center}.hero-visual{display:none}.nav-links{display:none}}
    </style>
</head>
<body>
    <nav>
        <a href="#" class="logo"><div class="logo-icon"><i class="fas fa-bolt"></i></div>SPARK</a>
        <ul class="nav-links">
            <li><a href="#about">About</a></li>
            <li><a href="#research">Research</a></li>
            <li><a href="#objectives">Objectives</a></li>
            <li><a href="#workshops">Workshops</a></li>
            <li><a href="#activities">Activities</a></li>
        </ul>
        <a href="#workshops" class="cta-btn">Get Started</a>
    </nav>

    <section class="hero">
        <div class="hero-content">
            <div class="hero-badge"><i class="fas fa-star"></i> Vocabulary Intervention Program</div>
            <h1>Sustained Pages for <span>Active Reading Knowledge</span></h1>
            <p>Transform passive readers into active vocabulary learners through structured engagement, collaborative learning, and meaningful language application.</p>
            <div class="hero-buttons">
                <a href="#workshops" class="cta-btn">Explore Workshops</a>
                <a href="#about" class="btn-secondary">Learn More</a>
            </div>
        </div>
        <div class="hero-visual">
            <div class="floating-cards">
                <div class="float-card"><div class="float-card-icon"><i class="fas fa-book-open"></i></div><div><h4>Active Reading</h4><p>Engage with texts</p></div></div>
                <div class="float-card"><div class="float-card-icon"><i class="fas fa-pen-fancy"></i></div><div><h4>Creative Writing</h4><p>Apply vocabulary</p></div></div>
                <div class="float-card"><div class="float-card-icon"><i class="fas fa-users"></i></div><div><h4>Collaboration</h4><p>Learn together</p></div></div>
            </div>
        </div>
    </section>

    <section id="about" class="section about">
        <div class="section-header">
            <span class="subtitle">About the Program</span>
            <h2>Building Stronger Readers</h2>
        </div>
        <div class="about-grid">
            <div class="about-card">
                <div class="icon"><i class="fas fa-search"></i></div>
                <h3>Active Learning</h3>
                <p>Students move beyond passive reading by actively analyzing texts, identifying unfamiliar words, and applying vocabulary in meaningful contexts.</p>
            </div>
            <div class="about-card">
                <div class="icon"><i class="fas fa-lightbulb"></i></div>
                <h3>Context Understanding</h3>
                <p>Learn to use context clues, prior knowledge, and morphological analysis to determine word meanings independently.</p>
            </div>
            <div class="about-card">
                <div class="icon"><i class="fas fa-rocket"></i></div>
                <h3>Creative Application</h3>
                <p>Apply newly learned words through writing, speaking, and collaborative activities that reinforce vocabulary retention.</p>
            </div>
        </div>
    </section>

    <section id="research" class="section research">
        <div class="section-header">
            <span class="subtitle" style="color:var(--accent)">Research Background</span>
            <h2>The Evidence Behind SPARK</h2>
        </div>
        <div style="max-width:900px;margin:0 auto">
            <div class="research-box">
                <h4><i class="fas fa-chart-line"></i> Key Findings</h4>
                <p>Research revealed that Junior High School students demonstrate moderate reading duration and satisfactory vocabulary proficiency. However, statistical analysis showed <strong>no significant relationship</strong> between reading time and vocabulary improvement.</p>
                <ul>
                    <li>Simply increasing reading time does NOT automatically improve vocabulary</li>
                    <li>Students may read without actively understanding unfamiliar words</li>
                    <li>Active engagement is essential for vocabulary development</li>
                </ul>
            </div>
            <div class="research-box">
                <h4><i class="fas fa-clipboard-check"></i> The SPARK Solution</h4>
                <p>Vocabulary development becomes effective when learners interact with
