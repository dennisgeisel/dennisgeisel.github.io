<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SignalScore - Innovation Kick-Off</title>
    
    <!-- FONTS -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Source+Sans+3:wght@300;400;500;600;700;900&display=swap" rel="stylesheet">
    
    <!-- ICONS -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

    <style>
        /* --- 0. VARIABLES & THEME --- */
        :root {
            /* Brand Colors */
            --mp-blue: #0076a7;
            --mp-blue-dark: #005a80;
            --mp-blue-light: #e0f2fe;
            --mp-red: #a71815;
            --mp-red-hover: #8a1311;
            
            /* Neutrals */
            --mp-dark: #0f172a;
            --mp-grey: #475569;
            --mp-grey-light: #94a3b8;
            --bg-body: #f8fafc;
            
            /* Surfaces */
            --surface-white: rgba(255, 255, 255, 0.85);
            --surface-glass: rgba(255, 255, 255, 0.6);
            --border-glass: rgba(255, 255, 255, 0.6);
            
            /* Shadows (Soft & Premium) */
            --shadow-xs: 0 1px 2px rgba(0,0,0,0.05);
            --shadow-sm: 0 4px 6px -1px rgba(0, 0, 0, 0.02), 0 2px 4px -2px rgba(0, 0, 0, 0.02);
            --shadow-md: 0 10px 15px -3px rgba(0, 0, 0, 0.03), 0 4px 6px -4px rgba(0, 0, 0, 0.03);
            --shadow-lg: 0 20px 40px -5px rgba(0, 0, 0, 0.05), 0 8px 10px -6px rgba(0, 0, 0, 0.01);
            --shadow-xl: 0 25px 50px -12px rgba(0, 0, 0, 0.15);
            --shadow-blue-glow: 0 0 60px rgba(0, 118, 167, 0.12);
            
            /* Spacing & Radius */
            --radius-md: 16px;
            --radius-lg: 28px;
            --container: 1280px;
        }

        /* --- 1. BASE --- */
        * { box-sizing: border-box; margin: 0; padding: 0; }
        
        html { scroll-behavior: smooth; font-size: 16px; }

        body {
            font-family: 'Source Sans 3', sans-serif;
            background-color: var(--bg-body);
            color: var(--mp-dark);
            line-height: 1.6;
            overflow-x: hidden;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }

        /* Modern Typography */
        h1, h2, h3, h4 {
            line-height: 1.1;
            letter-spacing: -0.03em;
            font-weight: 800;
            color: var(--mp-dark);
        }

        h1 { 
            font-size: clamp(3.2rem, 5.5vw, 5rem); 
            margin-bottom: 1.5rem;
        }
        
        h2 { 
            font-size: clamp(2.2rem, 3.5vw, 3rem); 
            margin-bottom: 1.25rem; 
        }
        
        h3 {
            font-size: 1.5rem;
            margin-bottom: 0.75rem;
            font-weight: 700;
        }

        p { 
            font-size: 1.125rem; 
            color: var(--mp-grey); 
            margin-bottom: 1.5rem; 
            max-width: 60ch; 
            line-height: 1.7;
        }
        
        strong { font-weight: 700; color: var(--mp-dark); }

        /* --- 2. UTILS & LAYOUT --- */
        .container {
            max-width: var(--container);
            margin: 0 auto;
            padding: 0 2rem;
            position: relative;
            z-index: 2;
        }

        .section-padding { padding: 10rem 0; } /* More whitespace for premium feel */

        .text-gradient {
            background: linear-gradient(135deg, var(--mp-blue) 0%, #38bdf8 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            display: inline-block;
        }
        
        .text-center { text-align: center; }
        .mx-auto { margin-left: auto; margin-right: auto; }

        /* Reveal Animation */
        .reveal {
            opacity: 0;
            transform: translateY(40px);
            transition: all 1s cubic-bezier(0.2, 0.8, 0.2, 1);
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        .delay-100 { transition-delay: 0.1s; }
        .delay-200 { transition-delay: 0.2s; }
        .delay-300 { transition-delay: 0.3s; }

        /* --- 3. COMPONENTS --- */
        
        /* Modern Button */
        .btn-primary {
            display: inline-flex;
            align-items: center;
            gap: 12px;
            background: var(--mp-red);
            color: white;
            font-weight: 700;
            padding: 18px 36px;
            border-radius: 100px;
            text-decoration: none;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            box-shadow: 0 8px 20px rgba(167, 24, 21, 0.25);
            font-size: 1.1rem;
            position: relative;
            overflow: hidden;
        }

        .btn-primary::after {
            content: '';
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background: linear-gradient(rgba(255,255,255,0.1), rgba(255,255,255,0));
            opacity: 0;
            transition: opacity 0.3s;
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 35px rgba(167, 24, 21, 0.35);
            background: var(--mp-red-hover);
        }
        
        .btn-primary:hover::after { opacity: 1; }

        .btn-icon {
            background: rgba(255,255,255,0.25);
            width: 32px; 
            height: 32px;
            border-radius: 50%;
            display: flex; 
            align-items: center; 
            justify-content: center;
            font-size: 0.85rem;
            transition: transform 0.3s;
        }
        
        .btn-primary:hover .btn-icon { transform: rotate(-45deg); }

        /* Premium Glass Card */
        .card-glass {
            background: var(--surface-white);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid var(--border-glass);
            border-top: 1px solid rgba(255,255,255,0.9);
            border-radius: var(--radius-lg);
            padding: 3.5rem 2.5rem;
            box-shadow: var(--shadow-lg);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
        }
        
        /* Subtle shine effect */
        .card-glass::before {
            content: '';
            position: absolute;
            top: 0; left: -100%; width: 100%; height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4), transparent);
            transition: 0.5s;
        }

        .card-glass:hover {
            transform: translateY(-8px);
            box-shadow: var(--shadow-xl);
            border-color: rgba(0, 118, 167, 0.3);
        }

        /* Badge */
        .badge {
            display: inline-flex;
            align-items: center;
            padding: 8px 18px;
            background: rgba(0, 118, 167, 0.08);
            color: var(--mp-blue);
            font-weight: 700;
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            border-radius: 100px;
            margin-bottom: 2rem;
            border: 1px solid rgba(0, 118, 167, 0.1);
        }

        /* --- 4. NAVIGATION --- */
        nav {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 2rem 0;
            z-index: 100;
            transition: all 0.4s ease;
        }

        nav.scrolled {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            padding: 1rem 0;
            border-bottom: 1px solid rgba(0,0,0,0.03);
            box-shadow: var(--shadow-sm);
        }

        .nav-inner {
            display: flex;
            justify-content: center; /* CENTERED SINCE LOGO IS GONE */
            align-items: center;
        }

        /* Logo class removed, but keeping CSS if you want to add it back later */
        .logo {
            font-weight: 900;
            font-size: 1.4rem;
            color: var(--mp-dark);
            text-transform: uppercase;
            letter-spacing: -0.02em;
            display: flex; align-items: center; gap: 10px;
        }
        
        .logo i { font-size: 1.2rem; }
        .logo span { color: var(--mp-blue); }

        .nav-menu { display: flex; gap: 3rem; }
        .nav-menu a {
            text-decoration: none;
            color: var(--mp-grey);
            font-weight: 600;
            font-size: 0.95rem;
            transition: color 0.2s;
            position: relative;
        }
        .nav-menu a:hover { color: var(--mp-blue); }
        .nav-menu a::after {
            content: '';
            position: absolute;
            bottom: -5px; left: 0; width: 0; height: 2px;
            background: var(--mp-blue);
            transition: width 0.3s;
        }
        .nav-menu a:hover::after { width: 100%; }

        /* --- 5. HERO SECTION --- */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
            /* Ultra subtle background */
            background: 
                radial-gradient(circle at 85% 10%, rgba(224, 242, 254, 0.4) 0%, transparent 40%),
                radial-gradient(circle at 10% 90%, rgba(241, 245, 249, 1) 0%, transparent 40%),
                #f8fafc;
        }

        .hero-grid {
            display: grid;
            grid-template-columns: 1.1fr 0.9fr;
            gap: 6rem;
            align-items: center;
            padding-top: 4rem;
        }

        .hero-card {
            background: white;
            padding: 3.5rem;
            border-radius: 40px;
            box-shadow: 0 50px 100px -20px rgba(0, 75, 120, 0.15);
            position: relative;
            z-index: 2;
            border: 1px solid white;
            transition: transform 0.5s cubic-bezier(0.2, 0.8, 0.2, 1);
        }
        
        .hero-card:hover { transform: perspective(1000px) rotateY(-2deg) rotateX(2deg); }

        /* Enhanced Circular Chart */
        .circular-chart {
            display: block;
            margin: 0 auto;
            max-width: 80%;
            max-height: 260px;
            filter: drop-shadow(0 10px 20px rgba(0, 118, 167, 0.2));
        }
        .circle-bg {
            fill: none;
            stroke: #e2e8f0;
            stroke-width: 2;
        }
        .circle {
            fill: none;
            stroke-width: 2.5;
            stroke-linecap: round;
            stroke: var(--mp-blue);
            animation: progress 1.5s ease-out forwards;
            stroke-dasharray: 0, 100;
        }
        @keyframes progress { 100% { stroke-dasharray: 87, 100; } }
        
        .percentage {
            fill: var(--mp-dark);
            font-family: 'Source Sans 3', sans-serif;
            font-weight: 800;
            font-size: 0.55em;
            text-anchor: middle;
            transform: translateY(1px);
        }
        .percentage-label {
            fill: var(--mp-grey-light);
            font-family: 'Source Sans 3', sans-serif;
            font-weight: 600;
            font-size: 0.12em;
            text-anchor: middle;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        /* --- 6. FEATURE GRID --- */
        .grid-3 {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2.5rem;
            margin-top: 5rem;
        }

        .feature-icon {
            width: 72px; height: 72px;
            background: linear-gradient(135deg, var(--mp-blue-light) 0%, #f0f9ff 100%);
            color: var(--mp-blue);
            border-radius: 20px;
            display: flex; align-items: center; justify-content: center;
            font-size: 1.75rem;
            margin-bottom: 2rem;
            transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
            box-shadow: inset 0 0 0 1px rgba(255,255,255,0.8), 0 10px 20px -5px rgba(0, 118, 167, 0.1);
        }
        
        .card-glass:hover .feature-icon {
            transform: scale(1.1) rotate(6deg);
            background: var(--mp-blue);
            color: white;
            box-shadow: 0 20px 30px -5px rgba(0, 118, 167, 0.3);
        }

        /* --- 7. SOLUTION (DARK MODE) --- */
        .dark-section {
            background: var(--mp-dark);
            color: white;
            position: relative;
            overflow: hidden;
        }

        /* FIX: Overwrite headings and strong tags for dark background */
        .dark-section h1,
        .dark-section h2,
        .dark-section h3,
        .dark-section h4,
        .dark-section strong {
            color: white;
        }
        
        .dark-section p {
            color: #cbd5e1; /* Light grey for body text */
        }
        
        /* New Layout for Solution Section */
        .solution-grid {
            display: grid;
            grid-template-columns: 1fr 1.2fr; /* Give more space to the visual dashboard */
            gap: 4rem;
            align-items: center;
        }

        /* Stats Grid Enhanced */
        .stats-dashboard {
            background: rgba(255,255,255,0.03);
            border: 1px solid rgba(255,255,255,0.1);
            border-radius: 24px;
            padding: 2.5rem;
            box-shadow: 0 25px 50px -12px rgba(0,0,0,0.5);
            position: relative;
            backdrop-filter: blur(10px);
        }
        
        /* Add a "Live" indicator to the dashboard */
        .dashboard-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
            border-bottom: 1px solid rgba(255,255,255,0.1);
            padding-bottom: 1rem;
        }
        
        .live-indicator {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 0.75rem;
            color: #4ade80; /* Green */
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            background: rgba(74, 222, 128, 0.1);
            padding: 4px 12px;
            border-radius: 20px;
        }
        
        .live-dot {
            width: 8px; height: 8px;
            background: #4ade80;
            border-radius: 50%;
            box-shadow: 0 0 10px #4ade80;
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% { transform: scale(0.95); opacity: 1; }
            50% { transform: scale(1.2); opacity: 0.5; }
            100% { transform: scale(0.95); opacity: 1; }
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 1rem;
        }

        .stat-item {
            background: linear-gradient(145deg, rgba(255,255,255,0.05) 0%, rgba(255,255,255,0.02) 100%);
            border: 1px solid rgba(255,255,255,0.08);
            padding: 1.5rem 0.5rem;
            border-radius: 12px;
            text-align: center;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100%;
            aspect-ratio: 1/1; /* Make them square tiles */
        }
        
        .stat-item::before {
            content: '';
            position: absolute;
            top: 0; left: 0; width: 100%; height: 2px;
            background: linear-gradient(90deg, transparent, #38bdf8, transparent);
            opacity: 0;
            transition: opacity 0.3s;
        }

        .stat-item:hover { 
            background: rgba(255,255,255,0.08); 
            transform: translateY(-3px);
            border-color: rgba(255,255,255,0.2);
            box-shadow: 0 10px 20px -5px rgba(0,0,0,0.3);
        }
        
        .stat-item:hover::before { opacity: 1; }

        .stat-item i { 
            font-size: 1.5rem; 
            color: #38bdf8; 
            margin-bottom: 1rem;
            display: block;
        }
        
        .stat-item span { 
            display: block; 
            font-size: 0.75rem; 
            font-weight: 600; 
            text-transform: uppercase; 
            letter-spacing: 1px; 
            color: rgba(255,255,255,0.7);
        }

        /* Dark Card Variant for Goals Section */
        .card-glass-dark {
            background: rgba(255,255,255,0.03);
            border: 1px solid rgba(255,255,255,0.08);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border-radius: var(--radius-lg);
            padding: 3rem 2rem;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
            text-align: center; /* Zentriert den Text */
        }

        .card-glass-dark:hover {
            background: rgba(255,255,255,0.06);
            transform: translateY(-8px);
            border-color: rgba(56, 189, 248, 0.3); /* Light Blue Border on Hover */
            box-shadow: 0 20px 40px -10px rgba(0,0,0,0.5);
        }

        /* Adjust Icon for Dark Mode */
        .card-glass-dark .feature-icon {
            background: rgba(56, 189, 248, 0.1);
            color: #38bdf8;
            box-shadow: none;
            border: 1px solid rgba(56, 189, 248, 0.2);
            margin-left: auto;  /* Zentriert das Icon */
            margin-right: auto; /* Zentriert das Icon */
        }
        
        .card-glass-dark:hover .feature-icon {
            background: #38bdf8;
            color: white;
            box-shadow: 0 0 20px rgba(56, 189, 248, 0.4);
        }

        /* --- 8. WORKFLOW --- */
        .workflow-steps {
            display: flex;
            justify-content: space-between;
            position: relative;
            margin-top: 6rem;
        }
        
        .workflow-line {
            position: absolute;
            top: 45px;
            left: 60px; right: 60px;
            height: 3px;
            background: #e2e8f0;
            z-index: 0;
            overflow: hidden;
        }
        
        .workflow-line::after {
            content: '';
            position: absolute;
            top: 0; left: -100%; width: 100%; height: 100%;
            background: linear-gradient(90deg, transparent, var(--mp-blue), transparent);
            animation: lineFlow 3s infinite linear;
        }
        
        @keyframes lineFlow { 0% { left: -100%; } 100% { left: 100%; } }

        .wf-step {
            position: relative; z-index: 1;
            text-align: center;
            width: 250px;
        }
        
        .wf-circle {
            width: 90px; height: 90px;
            background: white;
            border: 1px solid #e2e8f0;
            border-radius: 50%;
            display: flex; align-items: center; justify-content: center;
            margin: 0 auto 2rem;
            font-size: 1.75rem;
            font-weight: 900;
            color: #cbd5e1;
            box-shadow: var(--shadow-md);
            transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
            position: relative;
        }
        
        .wf-step:hover .wf-circle {
            border-color: transparent;
            color: white;
            background: var(--mp-blue);
            transform: scale(1.15);
            box-shadow: 0 15px 30px rgba(0, 118, 167, 0.4);
        }

        /* Footer Removed */

        /* --- RESPONSIVE --- */
        @media (max-width: 1024px) {
            /* Fix: Nav needs background on mobile to not clash with hero */
            nav {
                background: rgba(255, 255, 255, 0.95);
                backdrop-filter: blur(10px);
                -webkit-backdrop-filter: blur(10px);
                border-bottom: 1px solid rgba(0,0,0,0.05);
                padding: 1rem 0; /* Compact padding */
            }

            /* Fix: Push Hero content down so it doesn't hide behind nav */
            .hero-grid { 
                grid-template-columns: 1fr; 
                text-align: center; 
                gap: 4rem; 
                padding-top: 140px; /* Increased padding top for mobile */
            }
            
            /* Specific fix for Solution Section Layout */
            .solution-grid { 
                grid-template-columns: 1fr; 
                gap: 4rem; 
            }
            
            /* Center the text content when stacked to avoid "empty right side" feel */
            .solution-text-content {
                text-align: center;
                margin: 0 auto;
                max-width: 800px;
            }
            
            .solution-text-content ul {
                display: inline-block; /* Centers the list block */
                text-align: left;      /* Keeps list items readable */
            }
            
            .hero-text { order: 1; }
            .hero-visual-container { order: 2; margin-top: 1rem; }
            .grid-3 { grid-template-columns: 1fr; gap: 1.5rem; }
            
            /* 2 columns on tablet for stats */
            .stats-grid { grid-template-columns: repeat(4, 1fr); }
            
            p { margin-left: auto; margin-right: auto; }
            
            /* SHOW MENU ON TABLET/MOBILE (CHANGED) */
            .nav-menu { 
                display: flex; 
                justify-content: center;
                flex-wrap: wrap;
                gap: 1.5rem;
                margin-top: 0.5rem;
            } 
            .nav-menu a { font-size: 0.9rem; }
            
            .logo { flex-grow: 1; justify-content: center; }

            .workflow-steps { flex-direction: column; gap: 3rem; align-items: center; }
            .workflow-line { display: none; }
            
            .hero-cta-container { display: flex; justify-content: center; }
        }
        
        /* MOBILE SPECIFIC TWEAKS */
        @media (max-width: 768px) {
            .section-padding { padding: 5rem 0; } /* Reduced padding for mobile */
            
            h1 { font-size: 2.5rem; } /* Smaller H1 */
            h2 { font-size: 2rem; }
            
            .container { padding: 0 1.5rem; }
            
            .hero-card { padding: 2rem; }
            .card-glass, .card-glass-dark { padding: 2.5rem 1.5rem; }
            
            .nav-menu { gap: 1rem; }
            .nav-menu a { font-size: 0.8rem; }
            
            .btn-primary { width: 100%; justify-content: center; }
        }
        
        @media (max-width: 640px) {
            .stats-grid { grid-template-columns: repeat(2, 1fr); }
            .dashboard-header { flex-direction: column; gap: 10px; text-align: center; }
        }
    </style>
</head>
<body>

    <!-- NAV (Logo Removed, Menu Centered) -->
    <nav id="navbar">
        <div class="container nav-inner">
            <!-- LOGO REMOVED -->
            <div class="nav-menu">
                <a href="#challenges">Herausforderung</a>
                <a href="#solution">SignalScore</a>
                <a href="#workflow">Workflow</a>
                <a href="#goals">Erfolge</a>
            </div>
        </div>
    </nav>

    <!-- HERO -->
    <section id="intro" class="hero">
        <div class="container hero-grid">
            <div class="hero-text reveal active">
                <!-- Badge removed here -->
                <h1>Daten statt<br><span class="text-gradient">Bauchgefühl.</span></h1>
                <p>Der neue <strong>SignalScore</strong> identifiziert Ihre wertvollsten Leads automatisch. Sparen Sie kostbare Recherchezeit und fokussieren Sie sich auf das Wesentliche: Den Abschluss.</p>
                
                <div style="margin-top: 3rem;">
                    <a href="#solution" class="btn-primary">
                        Lösung entdecken
                        <div class="btn-icon"><i class="fa-solid fa-arrow-down"></i></div>
                    </a>
                </div>
            </div>

            <div class="hero-visual-container reveal delay-200">
                <div class="hero-card">
                    <h3 style="text-align: center; margin-bottom: 30px;">Lead Potential</h3>
                    <svg viewBox="0 0 36 36" class="circular-chart">
                        <path class="circle-bg" d="M18 2.0845 a 15.9155 15.9155 0 0 1 0 31.831 a 15.9155 15.9155 0 0 1 0 -31.831" />
                        <path class="circle" stroke-dasharray="87, 100" d="M18 2.0845 a 15.9155 15.9155 0 0 1 0 31.831 a 15.9155 15.9155 0 0 1 0 -31.831" />
                        <text x="18" y="20.35" class="percentage">87</text>
                        <text x="18" y="26" class="percentage-label">Score</text>
                    </svg>
                    <div style="text-align: center; margin-top: 30px;">
                        <div style="font-weight: 800; font-size: 1.4rem; letter-spacing: -0.02em;">Musterfirma GmbH</div>
                        <div style="color: var(--mp-blue); font-size: 1rem; margin-top: 8px; font-weight: 600; display: flex; align-items: center; justify-content: center; gap: 8px;">
                            <i class="fa-solid fa-trend-up"></i> Hohe Abschlusschance
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- CHALLENGES -->
    <section id="challenges" class="section-padding">
        <div class="container">
            <div class="reveal text-center">
                <h2>Warum wir handeln.</h2>
                <p class="mx-auto">Der aktuelle Vertriebsprozess hat drei entscheidende Engpässe.</p>
            </div>

            <div class="grid-3">
                <div class="card-glass reveal delay-100">
                    <div class="feature-icon"><i class="fa-regular fa-clock"></i></div>
                    <h3>Zeitverlust</h3>
                    <p style="margin-bottom: 0;">Vertriebler verbringen einen Großteil ihrer Zeit mit manueller Datensuche in verschiedenen Registern.</p>
                </div>
                <div class="card-glass reveal delay-200">
                    <div class="feature-icon"><i class="fa-solid fa-compass"></i></div>
                    <h3>Intuition</h3>
                    <p style="margin-bottom: 0;">Entscheidungen basieren oft auf Bauchgefühl. Wer nicht auf dem Radar ist, wird übersehen.</p>
                </div>
                <div class="card-glass reveal delay-300">
                    <div class="feature-icon"><i class="fa-solid fa-eye-slash"></i></div>
                    <h3>Blinde Flecken</h3>
                    <p style="margin-bottom: 0;">Schläferkunden und neue Marktteilnehmer rutschen durch das Raster statischer Listen.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- SOLUTION (DARK MODE) -->
    <section id="solution" class="section-padding dark-section">
        <!-- Decorational Shape -->
        <div style="position: absolute; top: -10%; right: -5%; width: 600px; height: 600px; background: radial-gradient(circle, rgba(0,118,167,0.15) 0%, transparent 70%); border-radius: 50%; pointer-events: none;"></div>
        
        <div class="container">
            <div class="solution-grid">
                <!-- Left: Text Content -->
                <div class="reveal solution-text-content">
                    <span class="badge" style="background: rgba(255,255,255,0.1); color: white; border-color: rgba(255,255,255,0.2);">Die Lösung</span>
                    <h2 style="margin-bottom: 2rem;">Der SignalScore.<br>0 bis 100.</h2>
                    <p style="color: #cbd5e1;">Wir aggregieren Daten aus neutralen Quellen und verknüpfen sie intelligent mit unserem internen CRM-Wissen.</p>
                    <p style="color: #cbd5e1;">Das Ergebnis ist eine <strong>einzige, dynamische Kennzahl</strong>, die sich in Echtzeit anpasst, wenn sich die Datenlage ändert.</p>
                    
                    <ul style="list-style: none; margin-top: 2.5rem; padding: 0;">
                        <li style="display: flex; align-items: center; gap: 15px; margin-bottom: 1.25rem; font-size: 1.1rem; color: white;">
                            <i class="fa-solid fa-check-circle" style="color: #38bdf8; font-size: 1.3rem;"></i> Priorisierung nach Abschluss-Chance
                        </li>
                        <li style="display: flex; align-items: center; gap: 15px; margin-bottom: 1.25rem; font-size: 1.1rem; color: white;">
                            <i class="fa-solid fa-check-circle" style="color: #38bdf8; font-size: 1.3rem;"></i> Integration direkt im Dashboard
                        </li>
                    </ul>
                </div>

                <!-- Right: Dashboard Visual -->
                <div class="reveal delay-200">
                    <div class="stats-dashboard">
                        <div class="dashboard-header">
                            <h4 style="color: #94a3b8; text-transform: uppercase; letter-spacing: 2px; font-size: 0.85rem; margin: 0;">Signal Monitoring</h4>
                            <div class="live-indicator">
                                <div class="live-dot"></div> Live Analysis
                            </div>
                        </div>
                        
                        <div class="stats-grid">
                            <div class="stat-item">
                                <i class="fa-solid fa-chart-line"></i>
                                <span>Umsatz</span>
                            </div>
                            <div class="stat-item">
                                <i class="fa-solid fa-users"></i>
                                <span>Größe</span>
                            </div>
                            <div class="stat-item">
                                <i class="fa-solid fa-map-location-dot"></i>
                                <span>Region</span>
                            </div>
                            <div class="stat-item">
                                <i class="fa-solid fa-industry"></i>
                                <span>Branche</span>
                            </div>
                            <div class="stat-item">
                                <i class="fa-solid fa-bed"></i>
                                <span>Schläfer</span>
                            </div>
                            <div class="stat-item">
                                <i class="fa-solid fa-graduation-cap"></i>
                                <span>Azubis</span>
                            </div>
                            <div class="stat-item">
                                <i class="fa-solid fa-globe"></i>
                                <span>Web</span>
                            </div>
                            <div class="stat-item">
                                <i class="fa-solid fa-handshake"></i>
                                <span>CRM</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- WORKFLOW -->
    <section id="workflow" class="section-padding">
        <div class="container">
            <div style="text-align: center;" class="reveal">
                <h2>Vom Datenpunkt zum Deal</h2>
                <p style="margin: 0 auto;">Ein automatisierter Prozess, der im Hintergrund für Sie arbeitet.</p>
            </div>

            <div class="workflow-steps reveal delay-200">
                <div class="workflow-line"></div>
                
                <div class="wf-step">
                    <div class="wf-circle">1</div>
                    <h3>Sammeln</h3>
                    <p style="font-size: 1rem; color: var(--mp-grey);">Crawler scannen kontinuierlich neutrale Quellen & Register.</p>
                </div>
                <div class="wf-step">
                    <div class="wf-circle">2</div>
                    <h3>Anreichern</h3>
                    <p style="font-size: 1rem; color: var(--mp-grey);">Verknüpfung mit internen CRM-Historien.</p>
                </div>
                <div class="wf-step">
                    <div class="wf-circle">3</div>
                    <h3>Bewerten</h3>
                    <p style="font-size: 1rem; color: var(--mp-grey);">Die KI-Matrix berechnet den Score (0-100).</p>
                </div>
                <div class="wf-step">
                    <div class="wf-circle">4</div>
                    <h3>Handeln</h3>
                    <p style="font-size: 1rem; color: var(--mp-grey);">Sie erhalten die Hot-Leads serviert.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- NEW SECTION: GOALS & SUCCESS (Dark Mode Variant) -->
    <section id="goals" class="section-padding dark-section" style="padding-bottom: 12rem;">
        <!-- Decorational Shape (Mirrored from Solution Section) -->
        <div style="position: absolute; bottom: -10%; left: -5%; width: 500px; height: 500px; background: radial-gradient(circle, rgba(0,118,167,0.15) 0%, transparent 70%); border-radius: 50%; pointer-events: none;"></div>

        <div class="container">
            <div class="reveal text-center">
                <!-- Badge Removed -->
                <h2>Ziele & Erfolgsmessung</h2>
                <p class="mx-auto" style="color: #94a3b8;">Der Mehrwert auf einen Blick.</p>
            </div>

            <div class="grid-3">
                <!-- Card 1 -->
                <div class="card-glass-dark reveal delay-100">
                    <div class="feature-icon"><i class="fa-regular fa-face-smile"></i></div>
                    <div style="text-transform: uppercase; font-size: 0.75rem; color: #38bdf8; font-weight: 700; margin-bottom: 0.5rem; letter-spacing: 1.5px;">Motivation</div>
                    <h3>Work Happiness</h3>
                    <p style="margin-bottom: 0; color: #cbd5e1;">Spaß an der Nutzung und motivierende Erfolgserlebnisse im Alltag.</p>
                </div>
                
                <!-- Card 2 -->
                <div class="card-glass-dark reveal delay-200">
                    <div class="feature-icon"><i class="fa-regular fa-clock"></i></div>
                    <div style="text-transform: uppercase; font-size: 0.75rem; color: #38bdf8; font-weight: 700; margin-bottom: 0.5rem; letter-spacing: 1.5px;">Prozesse</div>
                    <h3>Bessere Effizienz</h3>
                    <p style="margin-bottom: 0; color: #cbd5e1;">Fokus auf die relevantesten Kunden zum richtigen Zeitpunkt vereinfacht die Akquise.</p>
                </div>

                 <!-- Card 3 -->
                <div class="card-glass-dark reveal delay-300">
                    <div class="feature-icon"><i class="fa-solid fa-chart-column"></i></div>
                    <div style="text-transform: uppercase; font-size: 0.75rem; color: #38bdf8; font-weight: 700; margin-bottom: 0.5rem; letter-spacing: 1.5px;">Verkauf</div>
                    <h3>Mehr Erfolg</h3>
                    <p style="margin-bottom: 0; color: #cbd5e1;">Besserere Passung zwischen Kunde und Medienmarke steigert die Werbewirkung.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- FOOTER REMOVED -->

    <!-- INTERACTION SCRIPT -->
    <script>
        // 1. Reveal on Scroll (Improved Logic)
        function reveal() {
            var reveals = document.querySelectorAll(".reveal");
            for (var i = 0; i < reveals.length; i++) {
                var windowHeight = window.innerHeight;
                var elementTop = reveals[i].getBoundingClientRect().top;
                var elementVisible = 120;
                if (elementTop < windowHeight - elementVisible) {
                    reveals[i].classList.add("active");
                }
            }
        }
        window.addEventListener("scroll", reveal);
        // Trigger once on load
        reveal();

        // 2. Navbar Glass Effect
        window.addEventListener("scroll", function() {
            var nav = document.getElementById("navbar");
            if (window.scrollY > 50) {
                nav.classList.add("scrolled");
            } else {
                nav.classList.remove("scrolled");
            }
        });
    </script>
</body>
</html>
