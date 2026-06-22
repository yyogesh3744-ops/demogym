Gym Portfolio Demo Website

Here's a clean, professional gym website you can add to your portfolio. It uses modern design patterns—dark theme, bold typography, smooth animations, and a mobile-first layout.

Full Code

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IRONFORGE GYM | Transform Your Body</title>
    <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #f97316;
            --primary-dark: #ea580c;
            --dark: #0a0a0a;
            --dark-lighter: #141414;
            --dark-card: #1a1a1a;
            --gray: #737373;
            --light: #fafafa;
            --gradient: linear-gradient(135deg, #f97316 0%, #dc2626 100%);
        }

         {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--dark);
            color: var(--light);
            line-height: 1.6;
            overflow-x: hidden;
        }

        / Typography /
        h1, h2, h3, h4 {
            font-family: 'Bebas Neue', sans-serif;
            letter-spacing: 2px;
            line-height: 1.1;
        }

        / Navigation /
        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            padding: 1rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(10, 10, 10, 0.9);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
            transition: all 0.3s ease;
        }

        .navbar.scrolled {
            padding: 0.75rem 5%;
            background: rgba(10, 10, 10, 0.98);
        }

        .logo {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 2rem;
            color: var(--light);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .logo span {
            color: var(--primary);
        }

        .nav-links {
            display: flex;
            gap: 2.5rem;
            list-style: none;
        }

        .nav-links a {
            color: var(--gray);
            text-decoration: none;
            font-weight: 500;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: width 0.3s ease;
        }

        .nav-links a:hover {
            color: var(--light);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-cta {
            background: var(--gradient);
            color: var(--light);
            padding: 0.75rem 1.75rem;
            border: none;
            border-radius: 50px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-size: 0.85rem;
            cursor: pointer;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .nav-cta:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(249, 115, 22, 0.3);
        }

        .mobile-menu-btn {
            display: none;
            flex-direction: column;
            gap: 5px;
            background: none;
            border: none;
            cursor: pointer;
            padding: 5px;
        }

        .mobile-menu-btn span {
            width: 25px;
            height: 2px;
            background: var(--light);
            transition: all 0.3s ease;
        }

        / Hero Section /
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            padding: 0 5%;
            overflow: hidden;
        }

        .hero-bg {
            position: absolute;
            inset: 0;
            background: linear-gradient(135deg, rgba(10, 10, 10, 0.95) 0%, rgba(10, 10, 10, 0.7) 100%),
                        url('https://images.unsplash.com/photo-1534438327276-14e5300c3a48?w=1920&q=80') center/cover;
        }

        .hero-content {
            position: relative;
            z-index: 1;
            text-align: center;
            max-width: 900px;
        }

        .hero-badge {
            display: inline-block;
            background: rgba(249, 115, 22, 0.1);
            border: 1px solid var(--primary);
            color: var(--primary);
            padding: 0.5rem 1.5rem;
            border-radius: 50px;
            font-size: 0.85rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 2rem;
            animation: fadeInUp 0.8s ease;
        }

        .hero h1 {
            font-size: clamp(3rem, 10vw, 7rem);
            margin-bottom: 1.5rem;
            animation: fadeInUp 0.8s ease 0.2s both;
        }

        .hero h1 span {
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero p {
            font-size: 1.25rem;
            color: var(--gray);
            max-width: 600px;
            margin: 0 auto 2.5rem;
            animation: fadeInUp 0.8s ease 0.4s both;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            animation: fadeInUp 0.8s ease 0.6s both;
        }

        .btn {
            padding: 1rem 2.5rem;
            border-radius: 50px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-size: 0.9rem;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
        }

        .btn-primary {
            background: var(--gradient);
            color: var(--light);
            border: none;
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(249, 115, 22, 0.4);
        }

        .btn-outline {
            background: transparent;
            color: var(--light);
            border: 2px solid rgba(255, 255, 255, 0.2);
        }

        .btn-outline:hover {
            border-color: var(--primary);
            color: var(--primary);
        }

        .hero-stats {
            display: flex;
            justify-content: center;
            gap: 4rem;
            margin-top: 4rem;
            animation: fadeInUp 0.8s ease 0.8s both;
        }

        .stat {
            text-align: center;
        }

        .stat-number {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 3rem;
            color: var(--primary);
            display: block;
        }

        .stat-label {
            font-size: 0.85rem;
            color: var(--gray);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .scroll-indicator {
            position: absolute;
            bottom: 2rem;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
        }

        .scroll-indicator svg {
            width: 30px;
            height: 30px;
            stroke: var(--gray);
        }

        / Programs Section /
        .section {
            padding: 6rem 5%;
        }

        .section-header {
            text-align: center;
            margin-bottom: 4rem;
        }

        .section-label {
            color: var(--primary);
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 3px;
            font-size: 0.85rem;
            margin-bottom: 1rem;
            display: block;
        }

        .section-title {
            font-size: clamp(2.5rem, 5vw, 4rem);
        }

        .programs-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .program-card {
            background: var(--dark-card);
            border-radius: 20px;
            overflow: hidden;
            position: relative;
            transition: transform 0.3s ease;
        }

        .program-card:hover {
            transform: translateY(-10px);
        }

        .program-image {
            height: 250px;
            background-size: cover;
            background-position: center;
            position: relative;
        }

        .program-image::after {
            content: '';
            position: absolute;
            inset: 0;
            background: linear-gradient(to top, var(--dark-card) 0%, transparent 50%);
        }

        .program-content {
            padding: 1.5rem;
        }

        .program-tag {
            display: inline-block;
            background: rgba(249, 115, 22, 0.1);
            color: var(--primary);
            padding: 0.35rem 1rem;
            border-radius: 50px;
            font-size: 0.75rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 1rem;
        }

        .program-card h3 {
            font-size: 1.75rem;
            margin-bottom: 0.75rem;
        }

        .program-card p {
            color: var(--gray);
            font-size: 0.95rem;
            margin-bottom: 1.5rem;
        }

        .program-features {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .program-feature {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            font-size: 0.85rem;
            color: var(--gray);
        }

        .program-feature svg {
            width: 16px;
            height: 16px;
            stroke: var(--primary);
        }

        / Features Section /
        .features {
            background: var(--dark-lighter);
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .feature-card {
            text-align: center;
            padding: 2.5rem 2rem;
            background: var(--dark-card);
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: all 0.3s ease;
        }

        .feature-card:hover {
            border-color: var(--primary);
            transform: translateY(-5px);
        }

        .feature-icon {
            width: 70px;
            height: 70px;
            background: var(--gradient);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1.5rem;
        }

        .feature-icon svg {
            width: 32px;
            height: 32px;
            stroke: var(--light);
        }

        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 0.75rem;
        }

        .feature-card p {
            color: var(--gray);
            font-size: 0.95rem;
        }

        / Trainers Section /
        .trainers-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .trainer-card {
            background: var(--dark-card);
            border-radius: 20px;
            overflow: hidden;
            text-align: center;
        }

        .trainer-image {
            height: 300px;
            background-size: cover;
            background-position: center top;
            position: relative;
        }

        .trainer-socials {
            position: absolute;
            bottom: 1rem;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 0.75rem;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .trainer-card:hover .trainer-socials {
            opacity: 1;
        }

        .trainer-social {
            width: 40px;
            height: 40px;
            background: var(--dark);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--light);
            text-decoration: none;
            transition: background 0.3s ease;
        }

        .trainer-social:hover {
            background: var(--primary);
        }

        .trainer-social svg {
            width: 18px;
            height: 18px;
        }

        .trainer-info {
            padding: 1.5rem;
        }

        .trainer-info h3 {
            font-size: 1.5rem;
            margin-bottom: 0.25rem;
        }

        .trainer-role {
            color: var(--primary);
            font-weight: 500;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        / Pricing Section /
        .pricing {
            background: var(--dark-lighter);
        }

        .pricing-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2rem;
            max-width: 1100px;
            margin: 0 auto;
        }

        .pricing-card {
            background: var(--dark-card);
            border-radius: 24px;
            padding: 2.5rem;
            position: relative;
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: all 0.3s ease;
        }

        .pricing-card:hover {
            transform: translateY(-10px);
        }

        .pricing-card.featured {
            background: var(--gradient);
            border: none;
        }

        .pricing-card.featured .pricing-features li {
            color: rgba(255, 255, 255, 0.9);
        }

        .pricing-card.featured .pricing-features svg {
            stroke: var(--light);
        }

        .popular-badge {
            position: absolute;
            top: -12px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--dark);
            color: var(--light);
            padding: 0.5rem 1.5rem;
            border-radius: 50px;
            font-size: 0.75rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .pricing-header {
            text-align: center;
            margin-bottom: 2rem;
            padding-bottom: 2rem;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .pricing-name {
            font-size: 1.25rem;
            margin-bottom: 1rem;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .pricing-price {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 4rem;
            line-height: 1;
        }

        .pricing-price span {
            font-size: 1.25rem;
            font-family: 'Inter', sans-serif;
        }

        .pricing-period {
            color: rgba(255, 255, 255, 0.6);
            font-size: 0.9rem;
        }

        .pricing-features {
            list-style: none;
            margin-bottom: 2rem;
        }

        .pricing-features li {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            color: var(--gray);
            margin-bottom: 1rem;
            font-size: 0.95rem;
        }

        .pricing-features svg {
            width: 20px;
            height: 20px;
            stroke: var(--primary);
            flex-shrink: 0;
        }

        .pricing-card .btn {
            width: 100%;
            justify-content: center;
        }

        .pricing-card.featured .btn {
            background: var(--dark);
        }

        .pricing-card.featured .btn:hover {
            background: var(--dark-lighter);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        / Testimonials Section /
        .testimonials-container {
            max-width: 900px;
            margin: 0 auto;
        }

        .testimonial-card {
            background: var(--dark-card);
            border-radius: 24px;
            padding: 3rem;
            text-align: center;
            position: relative;
        }

        .testimonial-quote {
            font-size: 1.35rem;
            line-height: 1.8;
            color: var(--light);
            margin-bottom: 2rem;
            font-style: italic;
        }

        .testimonial-author {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
        }

        .testimonial-avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            object-fit: cover;
        }

        .testimonial-info h4 {
            font-size: 1.25rem;
            margin-bottom: 0.25rem;
        }

        .testimonial-info span {
            color: var(--primary);
            font-size: 0.9rem;
        }

        .testimonial-stars {
            display: flex;
            justify-content: center;
            gap: 0.25rem;
            margin-bottom: 1.5rem;
        }

        .testimonial-stars svg {
            width: 20px;
            height: 20px;
            fill: var(--primary);
        }

        / CTA Section /
        .cta {
            background: var(--gradient);
            text-align: center;
            padding: 6rem 5%;
            position: relative;
            overflow: hidden;
        }

        .cta::before {
            content: '';
            position: absolute;
            inset: 0;
            background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.05'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
        }

        .cta-content {
            position: relative;
            z-index: 1;
            max-width: 700px;
            margin: 0 auto;
        }

        .cta h2 {
            font-size: clamp(2.5rem, 5vw, 4rem);
            margin-bottom: 1.5rem;
        }

        .cta p {
            font-size: 1.25rem;
            margin-bottom: 2.5rem;
            opacity: 0.9;
        }

        .cta .btn-primary {
            background: var(--dark);
        }

        .cta .btn-primary:hover {
            background: var(--dark-lighter);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
        }

        / Footer /
        .footer {
            background: var(--dark-lighter);
            padding: 5rem 5% 2rem;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: 2fr repeat(3, 1fr);
            gap: 4rem;
            max-width: 1400px;
            margin: 0 auto 4rem;
        }

        .footer-brand .logo {
            margin-bottom: 1.5rem;
        }

        .footer-brand p {
            color: var(--gray);
            margin-bottom: 1.5rem;
            max-width: 300px;
        }

        .footer-socials {
            display: flex;
            gap: 1rem;
        }

        .footer-social {
            width: 45px;
            height: 45px;
            background: var(--dark-card);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--light);
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .footer-social:hover {
            background: var(--primary);
            transform: translateY(-3px);
        }

        .footer-social svg {
            width: 20px;
            height: 20px;
        }

        .footer-column h4 {
            font-size: 1.25rem;
            margin-bottom: 1.5rem;
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 0.75rem;
        }

        .footer-links a {
            color: var(--gray);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-links a:hover {
            color: var(--primary);
        }

        .footer-contact li {
            display: flex;
            align-items: flex-start;
            gap: 0.75rem;
            margin-bottom: 1rem;
            color: var(--gray);
        }

        .footer-contact svg {
            width: 20px;
            height: 20px;
            stroke: var(--primary);
            flex-shrink: 0;
            margin-top: 2px;
        }

        .footer-bottom {
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            padding-top: 2rem;
            text-align: center;
            color: var(--gray);
            font-size: 0.9rem;
        }

        / Animations /
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateX(-50%) translateY(0);
            }
            40% {
                transform: translateX(-50%) translateY(-10px);
            }
            60% {
                transform: translateX(-50%) translateY(-5px);
            }
        }

        / Responsive */
        @media (max-width: 1024px) {
            .footer-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 768px) {
            .nav-links, .nav-cta {
                display: none;
            }

            .mobile-menu-btn {
                display: flex;
            }

            .hero-stats {
                gap: 2rem;
            }

            .stat-number {
                font-size: 2.5rem;
            }

            .footer-grid {
                grid-template-columns: 1fr;
                gap: 2.5rem;
            }
        }

        @media (max-width: 480px) {
            .hero-stats {
                flex-direction: column;
                gap: 1.5rem;
            }

            .hero-buttons {
                flex-direction: column;
                width: 100%;
            }

            .hero-buttons .btn {
                width: 100%;
                justify-content: center;
            }
        }
    </style>
</head>
<body>

    <!-- Navigation -->
    <nav class="navbar">
        <a href="#" class="logo">
            <span>IRON</span>FORGE
        </a>
        <ul class="nav-links">
            <li><a href="#programs">Programs</a></li>
            <li><a href="#features">Features</a></li>
            <li><a href="#trainers">Trainers</a></li>
            <li><a href="#pricing">Pricing</a></li>
            <li><a href="#testimonials">Reviews</a></li>
        </ul>
        <button class="nav-cta">Join Now</button>
        <button class="mobile-menu-btn">
            <span></span>
            <span></span>
            <span></span>
        </button>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-bg"></div>
        <div class="hero-content">
            <span class="hero-badge">🏆 #1 Rated Gym in the City</span>
            <h1>FORGE YOUR <span>STRONGEST</span> SELF</h1>
            <p>Transform your body and mind with world-class equipment, expert trainers, and a community that pushes you to be your best.</p>
            <div class="hero-buttons">
                <a href="#pricing" class="btn btn-primary">
                    Start Free Trial
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
                </a>
                <a href="#programs" class="btn btn-outline">View Programs</a>
            </div>
            <div class="hero-stats">
                <div class="stat">
                    <span class="stat-number">15K+</span>
                    <span class="stat-label">Active Members</span>
                </div>
                <div class="stat">
                    <span class="stat-number">50+</span>
                    <span class="stat-label">Expert Trainers</span>
                </div>
                <div class="stat">
                    <span class="stat-number">98%</span>
                    <span class="stat-label">Success Rate</span>
                </div>
            </div>
        </div>
        <div class="scroll-indicator">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 12 15 18 9"></polyline></svg>
        </div>
    </section>

    <!-- Programs Section -->
    <section class="section" id="programs">
        <div class="section-header">
            <span class="section-label">Our Programs</span>
            <h2 class="section-title">Train Your Way</h2>
        </div>
        <div class="programs-grid">
            <div class="program-card">
                <div class="program-image" style="background-image: url('https://images.unsplash.com/photo-1581009146145-b5ef050c149a?w=600&q=80')"></div>
                <div class="program-content">
                    <span class="program-tag">Strength</span>
                    <h3>Power Lifting</h3>
                    <p>Build raw strength with progressive overload techniques and compound movements.</p>
                    <div class="program-features">
                        <span class="program-feature">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"></circle><polyline points="12 6 12 12 16 14"></polyline></svg>
                            60 min
                        </span>
                        <span class="program-feature">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path><circle cx="9" cy="7" r="4"></circle><path d="M23 21v-2a4 4 0 0 0-3-3.87"></path><path d="M16 3.13a4 4 0 0 1 0 7.75"></path></svg>
                            Small Groups
                        </span>
                    </div>
                </div>
            </div>
            <div class="program-card">
                <div class="program-image" style="background-image: url('https://images.unsplash.com/photo-1518611012118-696072aa579a?w=600&q=80')"></div>
                <div class="program-content">
                    <span class="program-tag">Cardio</span>
                    <h3>HIIT Training</h3>
                    <p>High-intensity intervals to maximize fat burn and improve cardiovascular health.</p>
                    <div class="program-features">
                        <span class="program-feature">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"></circle><polyline points="12 6 12 12 16 14"></polyline></svg>
                            45 min
                        </span>
                        <span class="program-feature">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path><circle cx="9" cy="7" r="4"></circle><path d="M23 21v-2a4 4 0 0 0-3-3.87"></path><path d="M16 3.13a4 4 0 0 1 0 7.75"></path></svg>
                            All Levels
                        </span>
                    </div>
                </div>
            </div>
            <div class="program-card">
                <div class="program-image" style="background-image: url('https://images.unsplash.com/photo-1544367567-0f2fcb009e0b?w=600&q=80')"></div>
                <div class="program-content">
                    <span class="program-tag">Flexibility</span>
                    <h3>Yoga & Mobility</h3>
                    <p>Improve flexibility, reduce stress, and enhance recovery with guided yoga sessions.</p>
                    <div class="program-features">
                        <span class="program-feature">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"></circle><polyline points="12 6 12 12 16 14"></polyline></svg>
                            75 min
                        </span>
                        <span class="program-feature">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path><circle cx="9" cy="7" r="4"></circle><path d="M23 21v-2a4 4 0 0 0-3-3.87"></path><path d="M16 3.13a4 4 0 0 1 0 7.75"></path></svg>
                            Beginner Friendly
                        </span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="section features" id="features">
        <div class="section-header">
            <span class="section-label">Why Choose Us</span>
            <h2 class="section-title">World-Class Facilities</h2>
        </div>
        <div class="features-grid">
            <div class="feature-card">
                <div class="feature-icon">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M6.5 6.5m-2 0a2 2 0 1 0 4 0a2 2 0 1 0 -4 0"></path><path d="M3 22v-4l3 -3l2 3l3 -6l6 6v4"></path><path d="M18 22v-4l-6 -6l-1 1"></path></svg>
                </div>
                <h3>Modern Equipment</h3>
                <p>State-of-the-art machines and free weights from top fitness brands.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M16 21v-2a4 4 0 0 0-4-4H6a4 4 0 0 0-4 4v2"></path><circle cx="9" cy="7" r="4"></circle><path d="M22 21v-2a4 4 0 0 0-3-3.87"></path><path d="M16 3.13a4 4 0 0 1 0 7.75"></path></svg>
                </div>
                <h3>Expert Trainers</h3>
                <p>Certified professionals dedicated to helping you reach your goals.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"></circle><polyline points="12 6 12 12 16 14"></polyline></svg>
                </div>
                <h3>24/7 Access</h3>
                <p>Train on your schedule with round-the-clock gym access.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H20"></path><path d="M6.5 2H20v20H6.5A2.5 2.5 0 0 1 4 19.5v-15A2.5 2.5 0 0 1 6.5 2z"></path></svg>
                </div>
                <h3>Nutrition Plans</h3>
                <p>Personalized meal plans to complement your training regimen.</p>
            </div>
        </div>
    </section>

    <!-- Trainers Section -->
    <section class="section" id="trainers">
        <div class="section-header">
            <span class="section-label">Meet The Team</span>
            <h2 class="section-title">Expert Trainers</h2>
        </div>
        <div class="trainers-grid">
            <div class="trainer-card">
                <div class="trainer-image" style="background-image: url('https://images.unsplash.com/photo-1567013127542-490d757e51fc?w=400&q=80')">
                    <div class="trainer-socials">
                        <a href="#" class="trainer-social">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor"><path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/></svg>
                        </a>
                        <a href="#" class="trainer-social">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>
                        </a>
                    </div>
                </div>
                <div class="trainer-info">
                    <h3>Marcus Chen</h3>
                    <span class="trainer-role">Strength & Conditioning</span>
                </div>
            </div>
            <div class="trainer-card">
                <div class="trainer-image" style="background-image: url('https://images.unsplash.com/photo-1594381898411-846e7d193883?w=400&q=80')">
                    <div class="trainer-socials">
                        <a href="#" class="trainer-social">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor"><path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/></svg>
                        </a>
                        <a href="#" class="trainer-social">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>
                        </a>
                    </div>
                </div>
                <div class="trainer-info">
                    <h3>Sarah Williams</h3>
                    <span class="trainer-role">HIIT & Cardio Specialist</span>
                </div>
            </div>
            <div class="trainer-card">
                <div class="trainer-image" style="background-image: url('https://images.unsplash.com/photo-1571019614242-c5c5dee9f50b?w=400&q=80')">
                    <div class="trainer-socials">
                        <a href="#" class="trainer-social">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor"><path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/></svg>
                        </a>
                        <a href="#" class="trainer-social">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>
                        </a>
                    </div>
                </div>
                <div class="trainer-info">
                    <h3>David Rodriguez</h3>
                    <span class="trainer-role">Yoga & Mobility Coach</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Pricing Section -->
    <section class="section pricing" id="pricing">
        <div class="section-header">
            <span class="section-label">Membership Plans</span>
            <h2 class="section-title">Choose Your Plan</h2>
        </div>
        <div class="pricing-grid">
            <div class="pricing-card">
                <div class="pricing-header">
                    <h3 class="pricing-name">Basic</h3>
                    <div class="pricing-price"><span>$</span>29<span>/mo</span></div>
                    <p class="pricing-period">Billed monthly</p>
                </div>
                <ul class="pricing-features">
                    <li>
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        Full gym access
                    </li>
                    <li>
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        Locker room access
                    </li>
                    <li>
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        Free WiFi
                    </li>
                    <li>
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        Fitness assessment
                    </li>
                </ul>
                <a href="#" class="btn btn-outline">Get Started</a>
            </div>
            <div class="pricing-card featured">
                <span class="popular-badge">Most Popular</span>
                <div class="pricing-header">
                    <h3 class="pricing-name">Pro</h3>
                    <div class="pricing-price"><span>$</span>59<span>/mo</span></div>
                    <p class="pricing-period">Billed monthly</p>
                </div>
                <ul class="pricing-features">
                    <li>
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        Everything in Basic
                    </li>
                    <li>
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        Unlimited group classes
                    </li>
                    <li>
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        2 personal training sessions
                    </li>
                    <li>
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        Nutrition consultation
                    </li>
                    <li>
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        Sauna & spa access
                    </li>
                </ul>
                <a href="#" class="btn btn-primary">Get Started</a>
            </div>
            <div class="pricing-card">
                <div class="pricing-header">
                    <h3 class="pricing-name">Elite</h3>
                    <div class="pricing-price"><span>$</span>99<span>/mo</span></div>
                    <p class="pricing-period">Billed monthly</p>
                </div>
                <ul class="pricing-features">
                    <li>
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        Everything in Pro
                    </li>
                    <li>
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        Unlimited personal training
                    </li>
                    <li>
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        Custom meal plans
                    </li>
                    <li>
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        Priority booking
                    </li>
                    <li>
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"></polyline></svg>
                        Guest passes (2/month)
                    </li>
                </ul>
                <a href="#" class="btn btn-outline">Get Started</a>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="section" id="testimonials">
        <div class="section-header">
            <span class="section-label">Testimonials</span>
            <h2 class="section-title">Success Stories</h2>
        </div>
        <div class="testimonials-container">
            <div class="testimonial-card">
                <div class="testimonial-stars">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/></svg>
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/></svg>
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/></svg>
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/></svg>
                    <svg xmlns="http://www.
