<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ToolForge - Premium Digital Tools Suite</title>
    <meta name="description" content="Free online tools for conversion, compression, calculation, and more.">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            /* Light Theme */
            --primary: #3b82f6;
            --primary-dark: #2563eb;
            --primary-light: #93c5fd;
            --text: #000000;
            --text-light: #363b46;
            --bg: #f9fafb;
            --bg-secondary: #ffffff;
            --card-bg: rgba(255, 255, 255, 0.8);
            --header-bg: rgba(255, 255, 255, 0.9);
            --border: rgba(0, 0, 0, 0.1);
            --shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            --glass-blur: blur(12px);
            --transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .dark-mode {
            /* Dark Theme */
            --primary: #60a5fa;
            --primary-dark: #3b82f6;
            --primary-light: #1e40af;
            --text: #f9fafb;
            --text-light: #d1d5db;
            --bg: #111827;
            --bg-secondary: #1f2937;
            --card-bg: rgba(31, 41, 55, 0.7);
            --header-bg: rgba(17, 24, 39, 0.9);
            --border: rgba(255, 255, 255, 0.1);
            --shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            line-height: 1.6;
            color: var(--text);
            background-color: var(--bg);
            transition: background-color 0.5s ease, color 0.5s ease;
            overflow-x: hidden;
        }

        /* Smooth scroll behavior */
        html {
            scroll-behavior: smooth;
        }

        /* Header Styles */
        header {
            background-color: var(--header-bg);
            backdrop-filter: var(--glass-blur);
            -webkit-backdrop-filter: var(--glass-blur);
            position: sticky;
            top: 0;
            z-index: 1000;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: var(--shadow);
            border-bottom: 1px solid var(--border);
            transition: var(--transition);
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .logo span {
            color: var(--text);
            transition: var(--transition);
        }

        .logo-icon {
            width: 32px;
            height: 32px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            color: white;
            border-radius: 8px;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        nav a {
            text-decoration: none;
            color: var(--text);
            font-weight: 500;
            position: relative;
            transition: var(--transition);
            padding: 0.5rem 0;
        }

        nav a:hover {
            color: var(--primary);
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--primary);
            transition: var(--transition);
        }

        nav a:hover::after {
            width: 100%;
        }

        .header-actions {
            display: flex;
            align-items: center;
            gap: 1.5rem;
        }

        .contact-email {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            color: var(--text);
            text-decoration: none;
            transition: var(--transition);
            font-size: 0.9rem;
        }

        .contact-email:hover {
            color: var(--primary);
        }

        /* Theme Toggle */
        .theme-toggle {
            position: relative;
            width: 44px;
            height: 24px;
            border-radius: 12px;
            background: var(--bg-secondary);
            border: 1px solid var(--border);
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            padding: 0 3px;
        }

        .theme-toggle:hover {
            box-shadow: 0 0 0 3px var(--primary-light);
        }

        .toggle-thumb {
            width: 18px;
            height: 18px;
            border-radius: 50%;
            background: var(--primary);
            position: absolute;
            left: 3px;
            transition: transform 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 10px;
        }

        .dark-mode .toggle-thumb {
            transform: translateX(20px);
        }

        /* Mobile Menu */
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--text);
            cursor: pointer;
            transition: var(--transition);
        }

        .mobile-menu-btn:hover {
            color: var(--primary);
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--primary-dark), var(--primary));
            color: white;
            padding: 6rem 2rem;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiPjxkZWZzPjxwYXR0ZXJuIGlkPSJwYXR0ZXJuIiB3aWR0aD0iNDAiIGhlaWdodD0iNDAiIHBhdHRlcm5Vbml0cz0idXNlclNwYWNlT25Vc2UiIHBhdHRlcm5UcmFuc2Zvcm09InJvdGF0ZSg0NSkiPjxyZWN0IHdpZHRoPSIyMCIgaGVpZ2h0PSIyMCIgZmlsbD0icmdiYSgyNTUsMjU1LDI1NSwwLjA1KSIvPjwvcGF0dGVybj48L2RlZnM+PHJlY3QgZmlsbD0idXJsKCNwYXR0ZXJuKSIgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIvPjwvc3ZnPg==');
            opacity: 0.3;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
            z-index: 2;
        }

        .hero h1 {
            font-size: 2.8rem;
            margin-bottom: 1.5rem;
            font-weight: 800;
            line-height: 1.2;
            animation: fadeInUp 0.8s ease-out both;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2.5rem;
            opacity: 0.9;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            animation: fadeInUp 0.8s ease-out 0.2s both;
        }

        .cta-button {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background-color: white;
            color: var(--primary-dark);
            padding: 1rem 2.5rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            animation: fadeInUp 0.8s ease-out 0.4s both;
            border: none;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            position: relative;
            overflow: hidden;
        }

        .cta-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to right, transparent, rgba(255, 255, 255, 0.3), transparent);
            transform: translateX(-100%);
            transition: transform 0.6s ease;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
        }

        .cta-button:hover::before {
            transform: translateX(100%);
        }

        .tool-icons {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 4rem;
            flex-wrap: wrap;
        }

        .tool-icon {
            background-color: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(5px);
            -webkit-backdrop-filter: blur(5px);
            width: 80px;
            height: 80px;
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
            animation: float 6s ease-in-out infinite;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .tool-icon:nth-child(2) {
            animation-delay: 1s;
        }
        .tool-icon:nth-child(3) {
            animation-delay: 2s;
        }
        .tool-icon:nth-child(4) {
            animation-delay: 3s;
        }

        .tool-icon:hover {
            transform: translateY(-10px) scale(1.1);
            background-color: rgba(255, 255, 255, 0.25);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }

        .tool-icon i {
            font-size: 2rem;
            color: white;
        }

        /* Search Section */
        .search-section {
            padding: 4rem 2rem;
            max-width: 1200px;
            margin: -3rem auto 0;
            position: relative;
            z-index: 10;
        }

        .search-container {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }

        .search-input {
            width: 100%;
            padding: 1.2rem 1.5rem;
            padding-left: 3.5rem;
            border: none;
            border-radius: 50px;
            font-size: 1rem;
            transition: var(--transition);
            box-shadow: var(--shadow);
            background-color: var(--card-bg);
            backdrop-filter: var(--glass-blur);
            -webkit-backdrop-filter: var(--glass-blur);
            border: 1px solid var(--border);
            color: var(--text);
        }

        .search-input:focus {
            outline: none;
            box-shadow: 0 0 0 3px var(--primary-light);
        }

        .search-icon {
            position: absolute;
            left: 1.5rem;
            top: 50%;
            transform: translateY(-50%);
            color: var(--text-light);
            transition: var(--transition);
        }

        .search-input:focus + .search-icon {
            color: var(--primary);
        }

        /* Tools Section */
        .tools-section {
            padding: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
            color: var(--text);
            font-weight: 700;
        }

        .section-description {
            margin-bottom: 2rem;
            color: var(--text-light);
            max-width: 700px;
        }

        .tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1.5rem;
            margin-bottom: 4rem;
        }

        .tool-card {
            background-color: var(--card-bg);
            backdrop-filter: var(--glass-blur);
            -webkit-backdrop-filter: var(--glass-blur);
            border-radius: 16px;
            padding: 1.75rem;
            box-shadow: var(--shadow);
            transition: var(--transition);
            opacity: 0;
            transform: translateY(20px);
            border: 1px solid var(--border);
        }

        .tool-card.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .tool-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
            border-color: var(--primary-light);
        }

        .tool-icon-container {
            width: 64px;
            height: 64px;
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            border-radius: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 1.5rem;
            color: white;
            font-size: 1.75rem;
            box-shadow: 0 4px 12px rgba(59, 130, 246, 0.3);
        }

        .tool-name {
            font-weight: 700;
            margin-bottom: 0.75rem;
            font-size: 1.1rem;
            color: var(--text);
        }

        .tool-description {
            color: var(--text-light);
            margin-bottom: 1.75rem;
            font-size: 0.95rem;
            line-height: 1.5;
        }

        .use-tool-btn {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background-color: var(--primary);
            color: white;
            padding: 0.7rem 1.5rem;
            border-radius: 12px;
            text-decoration: none;
            font-weight: 500;
            font-size: 0.95rem;
            transition: var(--transition);
            border: none;
            cursor: pointer;
        }

        .use-tool-btn:hover {
            background-color: var(--primary-dark);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(59, 130, 246, 0.4);
        }

        .use-tool-btn i {
            font-size: 0.8rem;
            transition: transform 0.3s ease;
        }

        .use-tool-btn:hover i {
            transform: translateX(3px);
        }

        /* No Results Message */
        .no-results {
            grid-column: 1 / -1;
            text-align: center;
            padding: 3rem;
            color: var(--text-light);
            display: none;
        }

        /* Footer */
        footer {
            background-color: var(--bg-secondary);
            color: var(--text);
            padding: 5rem 2rem 2rem;
            margin-top: 3rem;
            border-top: 1px solid var(--border);
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
        }

        .footer-about {
            display: flex;
            flex-direction: column;
        }

        .footer-logo {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 1.5rem;
            text-decoration: none;
        }

        .footer-tagline {
            opacity: 0.8;
            margin-bottom: 1.5rem;
            line-height: 1.6;
        }

        .footer-contact {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            color: var(--text);
            text-decoration: none;
            margin-bottom: 1rem;
            transition: var(--transition);
        }

        .footer-contact:hover {
            color: var(--primary);
        }

        .footer-links h3 {
            font-size: 1.2rem;
            margin-bottom: 1.5rem;
            color: var(--text);
            font-weight: 600;
        }

        .footer-links ul {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 1rem;
        }

        .footer-links a {
            color: var(--text-light);
            text-decoration: none;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .footer-links a:hover {
            color: var(--primary);
            transform: translateX(5px);
        }

        .footer-links a i {
            font-size: 0.8rem;
            opacity: 0.7;
        }

        .copyright {
            text-align: center;
            padding-top: 3rem;
            margin-top: 3rem;
            border-top: 1px solid var(--border);
            color: var(--text-light);
            font-size: 0.9rem;
        }

        /* Back to Top Button */
        .back-to-top {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            width: 50px;
            height: 50px;
            background-color: var(--primary);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            box-shadow: 0 4px 20px rgba(59, 130, 246, 0.3);
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
            z-index: 100;
            border: none;
            cursor: pointer;
        }

        .back-to-top.visible {
            opacity: 1;
            visibility: visible;
        }

        .back-to-top:hover {
            background-color: var(--primary-dark);
            transform: translateY(-5px);
        }

        /* Animations */
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-15px); }
            100% { transform: translateY(0px); }
        }

        @keyframes cardAppear {
            from { opacity: 0; transform: translateY(20px) scale(0.95); }
            to { opacity: 1; transform: translateY(0) scale(1); }
        }

        /* Responsive Design */
        @media (max-width: 1024px) {
            .hero h1 {
                font-size: 2.4rem;
            }
            
            .hero p {
                font-size: 1.1rem;
            }
        }

        @media (max-width: 768px) {
            header {
                padding: 1rem;
            }

            nav ul {
                display: none;
                position: absolute;
                top: 70px;
                left: 0;
                width: 100%;
                background-color: var(--header-bg);
                backdrop-filter: var(--glass-blur);
                -webkit-backdrop-filter: var(--glass-blur);
                flex-direction: column;
                align-items: center;
                padding: 1rem 0;
                box-shadow: 0 10px 15px rgba(0, 0, 0, 0.1);
                border-bottom: 1px solid var(--border);
                z-index: 999;
            }

            nav ul.show {
                display: flex;
            }

            .mobile-menu-btn {
                display: block;
            }

            .contact-email {
                display: none;
            }

            .hero {
                padding: 5rem 1rem;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .hero p {
                font-size: 1rem;
            }

            .tool-icons {
                gap: 1rem;
                margin-top: 3rem;
            }

            .tool-icon {
                width: 60px;
                height: 60px;
            }

            .search-section, .tools-section {
                padding: 2rem 1rem;
            }

            .tools-grid {
                grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
            }
        }

        @media (max-width: 480px) {
            .hero h1 {
                font-size: 1.8rem;
            }

            .cta-button {
                padding: 0.9rem 1.8rem;
                font-size: 1rem;
            }

            .tool-icon {
                width: 50px;
                height: 50px;
            }

            .tool-icon i {
                font-size: 1.5rem;
            }

            .footer-content {
                grid-template-columns: 1fr;
                gap: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <a href="#" class="logo" id="homeLink">
            <div class="logo-icon">
                <i class="fas fa-tools"></i>
            </div>
            Tool<span>Forge</span>
        </a>
        
        <nav>
            <ul id="navMenu">
                <li><a href="#" id="homeNavLink">Home</a></li>
                <li><a href="#tools">All Tools</a></li>
                <li><a href="Contect Us.html">Contect</a></li>
                <li><a href="About Us.html">About</a></li>
            </ul>
        </nav>
        
        <div class="header-actions">
            <a href="mailto:toolforg@gmail.com" class="contact-email">
                <i class="fas fa-envelope"></i> Email
            </a>
            
            <div class="theme-toggle" id="themeToggle">
                <div class="toggle-thumb">
                    <i class="fas fa-sun"></i>
                </div>
            </div>
        </div>
        
        <button class="mobile-menu-btn" id="mobileMenuBtn">
            <i class="fas fa-bars"></i>
        </button>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>All in One Place, Your Daily Tools</h1>
            <p>Convert, calculate, compress, and simplify your everyday tasks — fast and free.</p>
            <a href="#tools" class="cta-button">
                Explore Tools <i class="fas fa"></i>
            </a>
            
            <div class="tool-icons">
                <div class="tool-icon">
                    <i class="fas fa-image"></i>
                </div>
                <div class="tool-icon">
                    <i class="fas fa-file-alt"></i>
                </div>
                <div class="tool-icon">
                    <i class="fas fa-calculator"></i>
                </div>
                <div class="tool-icon">
                    <i class="fas fa-code"></i>
                </div>
            </div>
        </div>
    </section>

    <!-- Search Section -->
    <section class="search-section">
        <div class="search-container">
            <i class="fas fa-search search-icon"></i>
            <input type="text" class="search-input" placeholder="Find a tool..." id="toolSearch" autocomplete="off">
        </div>
    </section>

    <!-- Tools Sections -->
    <main class="tools-section" id="tools">
        <!-- Image Tools -->
        <section>
            <h2 class="section-title">🖼 Image Tools</h2>
            <p class="section-description">Enhance and manipulate your images with our powerful image tools</p>
            
            <div class="tools-grid" id="image-tools">
                <div class="tool-card" data-category="image" data-name="Image Converter" data-description="Convert between JPG, PNG, GIF, and more formats">
                    <div class="tool-icon-container">
                        <i class="fas fa-exchange-alt"></i>
                    </div>
                    <h3 class="tool-name">Image Converter</h3>
                    <p class="tool-description">Convert between JPG, PNG, GIF, and more formats</p>
                    <a href="/Image Convertor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="image" data-name="Image Compressor" data-description="Reduce image file size without losing quality">
                    <div class="tool-icon-container">
                        <i class="fas fa-compress-alt"></i>
                    </div>
                    <h3 class="tool-name">Image Compressor</h3>
                    <p class="tool-description">Reduce image file size without losing quality</p>
                    <a href="Image Compressor 3.html" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>                
                
                <div class="tool-card" data-category="image" data-name="Resizer" data-description="Resize images to any dimension">
                    <div class="tool-icon-container">
                        <i class="fas fa-expand-alt"></i>
                    </div>
                    <h3 class="tool-name">Image Resizer</h3>
                    <p class="tool-description">Resize images to any dimension</p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="image" data-name="Cropper" data-description="Crop images to focus on what matters">
                    <div class="tool-icon-container">
                        <i class="fas fa-crop-alt"></i>
                    </div>
                    <h3 class="tool-name">Image Cropper</h3>
                    <p class="tool-description">Crop images to focus on what matters</p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="image" data-name="OCR" data-description="Extract text from images">
                    <div class="tool-icon-container">
                        <i class="fas fa-font"></i>
                    </div>
                    <h3 class="tool-name">Image to Text (OCR)</h3>
                    <p class="tool-description">Extract text from images</p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="image" data-name="Rotator" data-description="Rotate and flip images">
                    <div class="tool-icon-container">
                        <i class="fas fa-sync-alt"></i>
                    </div>
                    <h3 class="tool-name">Image Rotator</h3>
                    <p class="tool-description">Rotate and flip images</p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
            </div>
        </section>
        
        <!-- Document Tools -->
        <section>
            <h2 class="section-title">📄 Document Tools</h2>
            <p class="section-description">Manage and convert your documents with ease</p>
            
            <div class="tools-grid" id="document-tools">
                <div class="tool-card" data-category="document" data-name="PDF to Word" data-description="Convert PDF files to editable Word documents">
                    <div class="tool-icon-container">
                        <i class="fas fa-file-word"></i>
                    </div>
                    <h3 class="tool-name">PDF to Word</h3>
                    <p class="tool-description">Convert PDF files to editable Word documents</p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="document" data-name="PDF Compressor" data-description="Reduce PDF file size while preserving quality">
                    <div class="tool-icon-container">
                        <i class="fas fa-file-pdf"></i>
                    </div>
                    <h3 class="tool-name">PDF Compressor</h3>
                    <p class="tool-description">Reduce PDF file size while preserving quality</p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="document" data-name="PDF Merger" data-description="Combine multiple PDFs into one document">
                    <div class="tool-icon-container">
                        <i class="fas fa-object-group"></i>
                    </div>
                    <h3 class="tool-name">PDF Merger</h3>
                    <p class="tool-description">Combine multiple PDFs into one document</p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="document" data-name="Document Converter" data-description="Convert between various document formats">
                    <div class="tool-icon-container">
                        <i class="fas fa-file-export"></i>
                    </div>
                    <h3 class="tool-name">Document Converter</h3>
                    <p class="tool-description">Convert between various document formats</p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="document" data-name="PDF Lock/Unlock" data-description="Secure or unlock PDF files with passwords">
                    <div class="tool-icon-container">
                        <i class="fas fa-lock"></i>
                    </div>
                    <h3 class="tool-name">PDF Lock/Unlock</h3>
                    <p class="tool-description">Secure or unlock PDF files with passwords</p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="document" data-name="eSign" data-description="Add digital signatures to documents">
                    <div class="tool-icon-container">
                        <i class="fas fa-signature"></i>
                    </div>
                    <h3 class="tool-name">eSign</h3>
                    <p class="tool-description">Add digital signatures to documents</p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
            </div>
        </section>
        
        <!-- Calculator Tools -->
        <section>
            <h2 class="section-title">📱 Calculator Tools</h2>
            <p class="section-description">Perform various calculations for your needs</p>
            
            <div class="tools-grid" id="calculator-tools">
                <div class="tool-card" data-category="calculator" data-name="Scientific Calculator" data-description="Advanced calculator for complex calculations">
                    <div class="tool-icon-container">
                        <i class="fas fa-square-root-alt"></i>
                    </div>
                    <h3 class="tool-name">Scientific Calculator</h3>
                    <p class="tool-description">Advanced calculator for complex calculations</p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="calculator" data-name="Age Calculator" data-description="Calculate age from birth date">
                    <div class="tool-icon-container">
                        <i class="fas fa-birthday-cake"></i>
                    </div>
                    <h3 class="tool-name">Age Calculator</h3>
                    <p class="tool-description">Calculate age from birth date</p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="calculator" data-name="BMI Calculator" data-description="Calculate your Body Mass Index">
                    <div class="tool-icon-container">
                        <i class="fas fa-weight"></i>
                    </div>
                    <h3 class="tool-name">BMI Calculator</h3>
                    <p class="tool-description">Calculate your Body Mass Index</p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="calculator" data-name="Loan EMI Calculator" data-description="Calculate monthly loan payments">
                    <div class="tool-icon-container">
                        <i class="fas fa-home"></i>
                    </div>
                    <h3 class="tool-name">Loan EMI Calculator</h3>
                    <p class="tool-description">Calculate monthly loan payments</p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="calculator" data-name="GST Calculator" data-description="Calculate Goods and Services Tax">
                    <div class="tool-icon-container">
                        <i class="fas fa-percentage"></i>
                    </div>
                    <h3 class="tool-name">GST Calculator</h3>
                    <p class="tool-description">Calculate Goods and Services Tax</p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="calculator" data-name="Currency Converter" data-description="Convert between world currencies">
                    <div class="tool-icon-container">
                        <i class="fas fa-money-bill-wave"></i>
                    </div>
                    <h3 class="tool-name">Currency Converter</h3>
                    <p class="tool-description">Convert between world currencies</p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
            </div>
        </section>

        <!-- Code Formator Tool-->
        <section>
            <h2 class="section-title">👨‍💻 Code Formatter Tool</h2>
            <p class="section-description">Format and beautify your HTML, CSS, JavaScript, and other code.</p>
            
            <div class="tools-grid" id="calculator-tools">
                <div class="tool-card" data-category="calculator" data-name="Scientific Calculator" data-description="Advanced calculator for complex calculations">
                    <div class="tool-icon-container">
                        <i class="fas fa-code"></i>
                    </div>
                    <h3 class="tool-name">Code</h3>
                    <p class="tool-description"></p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="calculator" data-name="Age Calculator" data-description="Calculate age from birth date">
                    <div class="tool-icon-container">
                        <i class="fas fa-code"></i>
                    </div>
                    <h3 class="tool-name">Code</h3>
                    <p class="tool-description"></p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="calculator" data-name="BMI Calculator" data-description="Calculate your Body Mass Index">
                    <div class="tool-icon-container">
                        <i class="fas fa-code"></i>
                    </div>
                    <h3 class="tool-name">Code</h3>
                    <p class="tool-description"></p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="calculator" data-name="Loan EMI Calculator" data-description="Calculate monthly loan payments">
                    <div class="tool-icon-container">
                        <i class="fas fa-code"></i>
                    </div>
                    <h3 class="tool-name">Code </h3>
                    <p class="tool-description"></p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="calculator" data-name="GST Calculator" data-description="Calculate Goods and Services Tax">
                    <div class="tool-icon-container">
                        <i class="fas fa-code"></i>
                    </div>
                    <h3 class="tool-name">Code</h3>
                    <p class="tool-description"></p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
                
                <div class="tool-card" data-category="calculator" data-name="Currency Converter" data-description="Convert between world currencies">
                    <div class="tool-icon-container">
                        <i class="fas fa-code"></i>
                    </div>
                    <h3 class="tool-name">Code </h3>
                    <p class="tool-description"></p>
                    <a href="/image-compressor" class="use-tool-btn">Use Tool <i class="fas fa-arrow-right"></i></a>
                </div>
            </div>
        </section>
        
        <!-- No Results Message -->
        <div class="no-results" id="noResults">
            <i class="fas fa-search" style="font-size: 2rem; margin-bottom: 1rem;"></i>
            <h3>No tools found</h3>
            <p>Try a different search term or browse our categories</p>
        </div>
    </main>

    <!-- Footer -->
    <footer id="contact">
        <div class="footer-content">
            <div class="footer-about">
                <a href="#" id="homeNavLink" class="footer-logo">
                <i class="fas fa-tools"></i> ToolForge</a>

                <p class="footer-tagline">Smart Tools for a Smoother Digital Journey</p>
                <a href="mailto:toolforg@gmail.com" class="footer-contact">
                    <i class="fas fa-envelope"></i> toolforg@gmail.com
                </a>
            </div>
            
            <div class="footer-links">
                <h3>Quick Links</h3>
                <ul>
                    
                    <li><a href="#tools"><i class="fas fa-chevron-right"></i> Tools</a></li>
                    <li><a href="Contect Us.html"><i class="fas fa-chevron-right"></i> Contact</a></li>
                </ul>
            </div>
            
            <div class="footer-links">
                <h3>Legal</h3>
                <ul>
                    <li><a href="About Us.html"><i class="fas fa-chevron-right"></i> About</a></li>
                    <li><a href="Privacy Policy.html"><i class="fas fa-chevron-right"></i> Privacy Policy</a></li>
                    <li><a href="Terms of Use.html"><i class="fas fa-chevron-right"></i> Terms of Use</a></li>
                    <li><a href="Sitemap.html"><i class="fas fa-chevron-right"></i> Site Map</a></li>
                </ul>
            </div>
        </div>
        
        <div class="copyright">
            &copy; 2025 ToolForge. All rights reserved.
        </div>
    </footer>

    <!-- Back to Top Button -->
    <button class="back-to-top" id="backToTop">
        <i class="fas fa-arrow-up"></i>
    </button>

    <script>
        // Mobile menu toggle
        document.getElementById('mobileMenuBtn').addEventListener('click', function() {
            document.getElementById('navMenu').classList.toggle('show');
            this.innerHTML = this.innerHTML.includes('times') ? 
                '<i class="fas fa-bars"></i>' : 
                '<i class="fas fa-times"></i>';
        });

        // Theme toggle
        const themeToggle = document.getElementById('themeToggle');
        const prefersDarkScheme = window.matchMedia('(prefers-color-scheme: dark)');
        
        // Check for saved theme preference or use system preference
        const currentTheme = localStorage.getItem('theme') || 
                            (prefersDarkScheme.matches ? 'dark' : 'light');
        
        if (currentTheme === 'dark') {
            document.body.classList.add('dark-mode');
            themeToggle.querySelector('.toggle-thumb').innerHTML = '<i class="fas fa-moon"></i>';
        }
        
        themeToggle.addEventListener('click', function() {
            document.body.classList.toggle('dark-mode');
            const theme = document.body.classList.contains('dark-mode') ? 'dark' : 'light';
            localStorage.setItem('theme', theme);
            
            // Update icon
            const thumb = this.querySelector('.toggle-thumb');
            thumb.innerHTML = theme === 'dark' ? 
                '<i class="fas fa-moon"></i>' : 
                '<i class="fas fa-sun"></i>';
        });

        // Enhanced search functionality with debounce
        const toolSearch = document.getElementById('toolSearch');
        const toolCards = document.querySelectorAll('.tool-card');
        const noResults = document.getElementById('noResults');
        let searchTimeout;
        
        toolSearch.addEventListener('input', function(e) {
            clearTimeout(searchTimeout);
            searchTimeout = setTimeout(() => {
                const searchTerm = e.target.value.toLowerCase().trim();
                let hasResults = false;
                
                toolCards.forEach(card => {
                    const name = card.getAttribute('data-name').toLowerCase();
                    const desc = card.getAttribute('data-description').toLowerCase();
                    const category = card.getAttribute('data-category').toLowerCase();
                    
                    if (name.includes(searchTerm) || desc.includes(searchTerm) || category.includes(searchTerm)) {
                        card.style.display = 'block';
                        hasResults = true;
                    } else {
                        card.style.display = 'none';
                    }
                });
                
                // Show/hide no results message
                noResults.style.display = hasResults || searchTerm === '' ? 'none' : 'block';
            }, 300);
        });

        // Scroll animation for tool cards with Intersection Observer
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);

        document.querySelectorAll('.tool-card').forEach((card, index) => {
            // Add slight delay to each card for staggered animation
            card.style.transitionDelay = `${index * 0.05}s`;
            observer.observe(card);
        });

        // Back to top button
        const backToTop = document.getElementById('backToTop');
        
        window.addEventListener('scroll', function() {
            if (window.pageYOffset > 300) {
                backToTop.classList.add('visible');
            } else {
                backToTop.classList.remove('visible');
            }
        });

        // Back to top functionality
        backToTop.addEventListener('click', function(e) {
            e.preventDefault();
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });

        // Home link functionality
        const homeLink = document.getElementById('homeLink');
        const homeNavLink = document.getElementById('homeNavLink');
        
        function scrollToTop(e) {
            if (e) e.preventDefault();
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
            
            // Close mobile menu if open
            if (window.innerWidth <= 768) {
                document.getElementById('navMenu').classList.remove('show');
                document.getElementById('mobileMenuBtn').innerHTML = '<i class="fas fa-bars"></i>';
            }
        }
        
        homeLink.addEventListener('click', scrollToTop);
        homeNavLink.addEventListener('click', scrollToTop);

        // Initialize scroll position
        window.addEventListener('load', function() {
            if (window.location.hash === '#') {
                scrollToTop();
            }
        });

        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            if (anchor.id !== 'homeLink' && anchor.id !== 'homeNavLink') {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    
                    const targetId = this.getAttribute('href');
                    if (targetId === '#') return;
                    
                    const targetElement = document.querySelector(targetId);
                    if (targetElement) {
                        targetElement.scrollIntoView({
                            behavior: 'smooth'
                        });
                        
                        // Close mobile menu if open
                        if (window.innerWidth <= 768) {
                            document.getElementById('navMenu').classList.remove('show');
                            document.getElementById('mobileMenuBtn').innerHTML = '<i class="fas fa-bars"></i>';
                        }
                    }
                });
            }
        });

        // Preload hover animations
        document.addEventListener('DOMContentLoaded', function() {
            // This forces browsers to preload hover states
            const links = document.querySelectorAll('a, button');
            links.forEach(link => {
                link.addEventListener('mouseenter', function() {}, false);
                link.addEventListener('mouseleave', function() {}, false);
            });
        });

        // Performance optimization - lazy load non-critical elements
        if ('loading' in HTMLImageElement.prototype) {
            // Native lazy loading supported
            const images = document.querySelectorAll('img[loading="lazy"]');
            images.forEach(img => {
                img.src = img.dataset.src;
            });
        } else {
            // Fallback for browsers without native lazy loading
            const lazyLoadObserver = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        const img = entry.target;
                        img.src = img.dataset.src;
                        lazyLoadObserver.unobserve(img);
                    }
                });
            });

            document.querySelectorAll('img[loading="lazy"]').forEach(img => {
                lazyLoadObserver.observe(img);
            });
        }
    </script>
</body>
</html>
