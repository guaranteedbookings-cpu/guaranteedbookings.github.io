# guaranteedbookings.github.io
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Contractor Demand Blueprint | Stop Using Airbnb Data</title>
    <link href="https://fonts.googleapis.com/css2?family=Oswald:wght@500;700&family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --gold: #FFD700;
            --gold-metallic: linear-gradient(135deg, #FFE55C 0%, #FFD700 50%, #DAA520 100%);
            --dark: #0a0a0a;
            --dark-card: #111111;
            --grey: #1a1a1a;
        }

        body {
            background-color: var(--dark);
            color: #ffffff;
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Typography */
        h1, h2, h3 {
            font-family: 'Oswald', sans-serif;
            text-transform: uppercase;
            letter-spacing: -1px;
            line-height: 1;
        }

        .text-gold {
            background: var(--gold-metallic);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .text-strike {
            position: relative;
            color: #444;
            display: inline-block;
        }

        .text-strike::after {
            content: '';
            position: absolute;
            left: -5%;
            top: 50%;
            width: 110%;
            height: 4px;
            background: linear-gradient(90deg, transparent, #ff4444, #ff0000, #ff4444, transparent);
            box-shadow: 0 0 10px rgba(255,0,0,0.6);
            transform: rotate(-2deg);
        }

        /* Buttons */
        .btn-primary {
            background: var(--gold-metallic);
            color: #000;
            padding: 18px 40px;
            font-weight: 800;
            text-transform: uppercase;
            letter-spacing: 2px;
            border: none;
            cursor: pointer;
            font-size: 16px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(255,215,0,0.3);
            transition: all 0.3s;
            text-decoration: none;
            display: inline-block;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(255,215,0,0.5);
        }

        .btn-secondary {
            background: transparent;
            color: var(--gold);
            border: 2px solid var(--gold);
            padding: 16px 38px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 2px;
            cursor: pointer;
            transition: all 0.3s;
            text-decoration: none;
            display: inline-block;
        }

        .btn-secondary:hover {
            background: var(--gold);
            color: #000;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            padding: 60px 20px;
            background: radial-gradient(circle at 50% 50%, #1a1a1a 0%, #050505 100%);
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-image: 
                radial-gradient(circle at 20% 80%, rgba(255,215,0,0.03) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(255,215,0,0.03) 0%, transparent 50%);
            pointer-events: none;
        }

        .hero-content {
            max-width: 1200px;
            width: 100%;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 80px;
            align-items: center;
            position: relative;
            z-index: 2;
        }

        .hero-headline {
            font-size: clamp(48px, 8vw, 80px);
            margin-bottom: 30px;
            font-weight: 800;
            line-height: 0.95;
        }

        .hero-subhead {
            font-size: 20px;
            opacity: 0.8;
            margin-bottom: 40px;
            max-width: 540px;
            line-height: 1.6;
            font-weight: 300;
        }

        .hero-visual {
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .pdf-mockup {
            width: 400px;
            height: 565px;
            background: var(--grey);
            border: 2px solid rgba(255,215,0,0.3);
            box-shadow: 
                0 20px 60px rgba(0,0,0,0.8),
                0 0 40px rgba(255,215,0,0.1);
            transform: rotateY(-15deg) rotateX(5deg);
            position: relative;
            display: flex;
            flex-direction: column;
            padding: 40px;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: rotateY(-15deg) rotateX(5deg) translateY(0); }
            50% { transform: rotateY(-15deg) rotateX(5deg) translateY(-20px); }
        }

        .pdf-header {
            font-family: 'Oswald', sans-serif;
            font-size: 28px;
            text-transform: uppercase;
            margin-bottom: 20px;
            line-height: 1.2;
        }

        .pdf-line {
            height: 4px;
            background: var(--gold);
            width: 60px;
            margin: 20px 0;
            box-shadow: 0 0 10px rgba(255,215,0,0.5);
        }

        /* Problem Section */
        .problem {
            padding: 120px 20px;
            background: #080808;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            font-size: clamp(36px, 5vw, 56px);
            margin-bottom: 20px;
            text-align: center;
        }

        .section-subtitle {
            text-align: center;
            opacity: 0.7;
            margin-bottom: 60px;
            font-size: 18px;
        }

        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 60px;
        }

        .problem-card {
            background: var(--dark-card);
            border: 1px solid rgba(255,255,255,0.1);
            padding: 40px;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .problem-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: var(--gold-metallic);
            transform: scaleX(0);
            transition: transform 0.3s;
        }

        .problem-card:hover::before {
            transform: scaleX(1);
        }

        .problem-card:hover {
            border-color: rgba(255,215,0,0.3);
            box-shadow: 0 10px 40px rgba(255,215,0,0.1);
            transform: translateY(-5px);
        }

        .card-icon {
            font-size: 48px;
            margin-bottom: 20px;
            opacity: 0.8;
        }

        .card-title {
            font-family: 'Oswald', sans-serif;
            font-size: 24px;
            margin-bottom: 15px;
            color: var(--gold);
        }

        /* Tools Section */
        .tools {
            padding: 120px 20px;
            background: var(--dark);
        }

        .tools-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 20px;
            margin-top: 60px;
        }

        .tool-card {
            background: rgba(255,215,0,0.05);
            border: 1px solid rgba(255,215,0,0.2);
            padding: 30px;
            text-align: center;
            transition: all 0.3s;
            cursor: pointer;
        }

        .tool-card:hover {
            background: rgba(255,215,0,0.1);
            border-color: var(--gold);
            transform: translateY(-5px);
        }

        .tool-number {
            font-family: 'Oswald', sans-serif;
            font-size: 48px;
            color: var(--gold);
            opacity: 0.3;
            margin-bottom: 10px;
        }

        .tool-title {
            font-weight: 700;
            margin-bottom: 10px;
            font-size: 18px;
        }

        /* ROI Section */
        .roi {
            padding: 120px 20px;
            background: linear-gradient(180deg, #080808 0%, #111 100%);
            position: relative;
            overflow: hidden;
        }

        .roi::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,215,0,0.03) 0%, transparent 70%);
            pointer-events: none;
        }

        .calculator {
            max-width: 800px;
            margin: 60px auto;
            background: var(--dark-card);
            border: 1px solid rgba(255,215,0,0.2);
            padding: 60px;
            text-align: center;
            position: relative;
        }

        .calculator-result {
            font-family: 'Oswald', sans-serif;
            font-size: 72px;
            background: var(--gold-metallic);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin: 30px 0;
        }

        /* Content Preview */
        .contents {
            padding: 120px 20px;
            background: #080808;
        }

        .timeline {
            max-width: 800px;
            margin: 60px auto;
            position: relative;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(180deg, transparent, var(--gold), transparent);
            transform: translateX(-50%);
        }

        .timeline-item {
            display: flex;
            margin-bottom: 40px;
            position: relative;
            align-items: center;
        }

        .timeline-item:nth-child(odd) {
            flex-direction: row-reverse;
            text-align: right;
        }

        .timeline-item:nth-child(odd) .timeline-content {
            padding-right: 60px;
            padding-left: 0;
        }

        .timeline-content {
            flex: 1;
            padding-left: 60px;
        }

        .timeline-number {
            width: 50px;
            height: 50px;
            background: var(--gold-metallic);
            color: #000;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 900;
            font-size: 20px;
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            box-shadow: 0 0 20px rgba(255,215,0,0.4);
            z-index: 2;
        }

        /* CTA Section */
        .cta {
            padding: 120px 20px;
            background: var(--gold-metallic);
            position: relative;
            text-align: center;
        }

        .cta h2 {
            color: #000;
            font-size: clamp(36px, 5vw, 56px);
            margin-bottom: 20px;
        }

        .cta p {
            color: #000;
            opacity: 0.8;
            margin-bottom: 40px;
            font-size: 20px;
        }

        .btn-dark {
            background: #000;
            color: var(--gold);
            padding: 20px 50px;
            font-weight: 800;
            text-transform: uppercase;
            letter-spacing: 2px;
            border: none;
            cursor: pointer;
            font-size: 18px;
            transition: all 0.3s;
            text-decoration: none;
            display: inline-block;
        }

        .btn-dark:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }

        /* Responsive */
        @media (max-width: 968px) {
            .hero-content {
                grid-template-columns: 1fr;
                text-align: center;
            }
            
            .hero-subhead {
                margin-left: auto;
                margin-right: auto;
            }
            
            .tools-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .timeline::before {
                left: 30px;
            }
            
            .timeline-item,
            .timeline-item:nth-child(odd) {
                flex-direction: row;
                text-align: left;
                padding-left: 80px;
            }
            
            .timeline-item:nth-child(odd) .timeline-content,
            .timeline-content {
                padding-left: 0;
                padding-right: 0;
            }
            
            .timeline-number {
                left: 30px;
                transform: translateX(-50%);
            }
        }

        @media (max-width: 640px) {
            .tools-grid {
                grid-template-columns: 1fr;
            }
            
            .cards-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Animations */
        @keyframes pulse-gold {
            0%, 100% { box-shadow: 0 0 20px rgba(255,215,0,0.4); }
            50% { box-shadow: 0 0 40px rgba(255,215,0,0.6); }
        }

        .animate-pulse {
            animation: pulse-gold 2s infinite;
        }
    </style>
<base target="_blank">
</head>
<body>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <div class="hero-text">
                <h1 class="hero-headline">
                    <span class="text-strike">Your Airbnb</span><br>
                    <span class="text-gold">Dashboard Is<br>Lying To You</span>
                </h1>
                <p class="hero-subhead">
                    The tourism data destroying your occupancy rates—and the construction intelligence system fixing it.
                </p>
                <a href="#download" class="btn-primary animate-pulse">
                    Download The Free Blueprint
                </a>
                <p style="margin-top: 20px; font-size: 14px; opacity: 0.6;">
                    13 pages. Zero fluff. Used by 2,400+ UK operators.
                </p>
            </div>
            <div class="hero-visual">
                <div class="pdf-mockup">
                    <div class="pdf-header">
                        STOP USING<br>
                        <span style="opacity: 0.4;">AIRBNB</span> DATA
                    </div>
                    <div class="pdf-line"></div>
                    <p style="font-size: 14px; opacity: 0.8; line-height: 1.6; margin-top: 20px;">
                        The Contractor Demand Blueprint
                    </p>
                    <div style="margin-top: auto; padding: 20px; background: rgba(255,215,0,0.1); border: 1px solid rgba(255,215,0,0.3); text-align: center;">
                        <span style="color: #FFD700; font-weight: 700;">FREE PDF</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Problem Section -->
    <section class="problem">
        <div class="container">
            <h2 class="section-title">
                The <span class="text-gold">Mid-Week Ghost Town</span><br>
                Nobody Talks About
            </h2>
            <p class="section-subtitle">
                While you're dropping prices to compete with holiday lets, contractors are sleeping in budget hotels 2 miles away.
            </p>
            
            <div class="cards-grid">
                <div class="problem-card">
                    <div class="card-icon">📅</div>
                    <div class="card-title">The Monday-Wednesday Gap</div>
                    <p>Airbnb shows you competing with other hosts. It doesn't show you that contractors need Mon-Thu stays, not Fri-Sun.</p>
                </div>
                
                <div class="problem-card">
                    <div class="card-icon">📉</div>
                    <div class="card-title">The Price Crash Loop</div>
                    <p>You lower rates to match tourism demand. Contractors would pay £35/room. You're charging £25 because "that's the market rate."</p>
                </div>
                
                <div class="problem-card">
                    <div class="card-icon">🤖</div>
                    <div class="card-title">The Algorithm Trap</div>
                    <p>Airbnb's "Smart Pricing" compares you to holiday apartments. It ignores the £50/night Travelodge down the road.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Solution/Tools Section -->
    <section class="tools">
        <div class="container">
            <h2 class="section-title">
                The <span class="text-gold">4-Data Validation</span> System
            </h2>
            <p class="section-subtitle">
                Stop guessing. Start knowing where the contractors are before you buy.
            </p>
            
            <div class="tools-grid">
                <div class="tool-card">
                    <div class="tool-number">01</div>
                    <div class="tool-title">Construction Map</div>
                    <p style="font-size: 14px; opacity: 0.7;">Multi-year projects = Gold mines</p>
                </div>
                
                <div class="tool-card">
                    <div class="tool-number">02</div>
                    <div class="tool-title">News Index</div>
                    <p style="font-size: 14px; opacity: 0.7;">Spot demand 6 months early</p>
                </div>
                
                <div class="tool-card">
                    <div class="tool-number">03</div>
                    <div class="tool-title">Glenigan Data</div>
                    <p style="font-size: 14px; opacity: 0.7;">Direct contractor contacts</p>
                </div>
                
                <div class="tool-card">
                    <div class="tool-number">04</div>
                    <div class="tool-title">BidStats Filter</div>
                    <p style="font-size: 14px; opacity: 0.7;">Government contract tracking</p>
                </div>
            </div>
            
            <div style="text-align: center; margin-top: 60px;">
                <p style="opacity: 0.8; max-width: 600px; margin: 0 auto;">
                    Page 8 reveals the Pricing Logic that turns £50 hotel rates into £35 guaranteed contractor bookings.
                </p>
            </div>
        </div>
    </section>

    <!-- ROI Calculator Section -->
    <section class="roi">
        <div class="container">
            <h2 class="section-title" style="text-align: center;">
                The <span class="text-gold">Multi-Room Math</span>
            </h2>
            <p class="section-subtitle" style="text-align: center;">
                Why 5 bedrooms beats 2 bedrooms every time.
            </p>
            
            <div class="calculator">
                <div style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 40px; margin-bottom: 40px;">
                    <div style="text-align: center;">
                        <div style="font-size: 14px; text-transform: uppercase; letter-spacing: 2px; opacity: 0.6; margin-bottom: 10px;">Property</div>
                        <div style="font-family: 'Oswald'; font-size: 32px;">5 Bedrooms</div>
                    </div>
                    <div style="text-align: center;">
                        <div style="font-size: 14px; text-transform: uppercase; letter-spacing: 2px; opacity: 0.6; margin-bottom: 10px;">Rate</div>
                        <div style="font-family: 'Oswald'; font-size: 32px; color: #FFD700;">£35/room</div>
                    </div>
                    <div style="text-align: center;">
                        <div style="font-size: 14px; text-transform: uppercase; letter-spacing: 2px; opacity: 0.6; margin-bottom: 10px;">Nights</div>
                        <div style="font-family: 'Oswald'; font-size: 32px;">Mon-Thu</div>
                    </div>
                </div>
                
                <div style="border-top: 1px solid rgba(255,215,0,0.2); border-bottom: 1px solid rgba(255,215,0,0.2); padding: 30px 0; margin: 30px 0;">
                    <div style="font-size: 14px; text-transform: uppercase; letter-spacing: 2px; opacity: 0.6;">Monthly Revenue Potential</div>
                    <div class="calculator-result">£2,100</div>
                    <div style="font-size: 18px; opacity: 0.8;">vs £850 typical Airbnb monthly average</div>
                </div>
                
                <p style="opacity: 0.6; font-size: 14px; font-style: italic;">
                    Based on 4-night mid-week occupancy. Page 9 of the Blueprint breaks down the full model.
                </p>
            </div>
        </div>
    </section>

    <!-- What's Inside -->
    <section class="contents">
        <div class="container">
            <h2 class="section-title" style="text-align: center;">
                What's Inside The <span class="text-gold">Blueprint</span>
            </h2>
            <p class="section-subtitle" style="text-align: center;">
                13 pages. Zero fluff. Just the validation framework.
            </p>
            
            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-number">1</div>
                    <div class="timeline-content">
                        <h3 style="font-family: 'Oswald'; font-size: 24px; margin-bottom: 5px;">The Cover</h3>
                        <p style="opacity: 0.7;">Why your current data source is broken</p>
                    </div>
                </div>
                
                <div class="timeline-item">
                    <div class="timeline-number">2</div>
                    <div class="timeline-content">
                        <h3 style="font-family: 'Oswald'; font-size: 24px; margin-bottom: 5px;">The Core Mistake</h3>
                        <p style="opacity: 0.7;">Tourism vs. Contractor behavior patterns</p>
                    </div>
                </div>
                
                <div class="timeline-item">
                    <div class="timeline-number">3</div>
                    <div class="timeline-content">
                        <h3 style="font-family: 'Oswald'; font-size: 24px; margin-bottom: 5px;">The 4 Tools</h3>
                        <p style="opacity: 0.7;">Construction Map, Index, Glenigan & BidStats</p>
                    </div>
                </div>
                
                <div class="timeline-item">
                    <div class="timeline-number" style="background: #000; color: #FFD700; border: 2px solid #FFD700;">8</div>
                    <div class="timeline-content">
                        <h3 style="font-family: 'Oswald'; font-size: 24px; margin-bottom: 5px; color: #FFD700;">Pricing Logic ★</h3>
                        <p style="opacity: 0.7;">How to price against hotels, not Airbnbs</p>
                    </div>
                </div>
                
                <div class="timeline-item">
                    <div class="timeline-number">13</div>
                    <div class="timeline-content">
                        <h3 style="font-family: 'Oswald'; font-size: 24px; margin-bottom: 5px;">The Checklist</h3>
                        <p style="opacity: 0.7;">5-box validation before you buy</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Final CTA -->
    <section class="cta" id="download">
        <h2>Stop Using Airbnb Data.<br>Start Securing Bookings.</h2>
        <p>Join 2,400+ operators using real-world construction data.</p>
        
        <form style="max-width: 500px; margin: 40px auto; display: flex; gap: 10px;">
            <input type="email" placeholder="Enter your email" style="flex: 1; padding: 20px; border: none; background: rgba(0,0,0,0.2); color: #000; font-size: 16px; border-bottom: 2px solid #000;">
            <button type="submit" class="btn-dark">Get The Blueprint →</button>
        </form>
        
        <p style="font-size: 12px; opacity: 0.6; margin-top: 20px;">
            No spam. Unsubscribe anytime. PDF delivered instantly.
        </p>
    </section>

</body>
</html>
