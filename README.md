<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Costico AI - Intelligent Cost Optimization</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Navigation */
        nav {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            transition: all 0.3s ease;
        }

        nav:hover {
            background: rgba(255, 255, 255, 0.15);
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 2rem;
            font-weight: bold;
            color: white;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { text-shadow: 2px 2px 4px rgba(0,0,0,0.3), 0 0 10px rgba(255,255,255,0.3); }
            to { text-shadow: 2px 2px 4px rgba(0,0,0,0.3), 0 0 20px rgba(255,255,255,0.6); }
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            transition: all 0.3s ease;
            padding: 0.5rem 1rem;
            border-radius: 25px;
        }

        .nav-links a:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-2px);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .floating-shapes {
            position: absolute;
            width: 100%;
            height: 100%;
            overflow: hidden;
        }

        .shape {
            position: absolute;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        .shape:nth-child(1) {
            width: 80px;
            height: 80px;
            left: 10%;
            animation-delay: 0s;
        }

        .shape:nth-child(2) {
            width: 120px;
            height: 120px;
            left: 80%;
            animation-delay: 2s;
        }

        .shape:nth-child(3) {
            width: 60px;
            height: 60px;
            left: 50%;
            animation-delay: 4s;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        .hero-content {
            z-index: 2;
            color: white;
            max-width: 800px;
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            animation: slideInUp 1s ease-out;
        }

        .hero p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
            animation: slideInUp 1s ease-out 0.3s both;
        }

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .cta-button {
            background: linear-gradient(45deg, #ff6b6b, #ee5a24);
            color: white;
            padding: 1rem 2rem;
            border: none;
            border-radius: 50px;
            font-size: 1.2rem;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            animation: slideInUp 1s ease-out 0.6s both;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }

        /* Section Styles */
        .section {
            padding: 5rem 0;
            background: white;
            margin: 2rem 0;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .section h2 {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 3rem;
            color: #333;
            background: linear-gradient(45deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        /* Features Grid */
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .feature-card {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            color: white;
            transition: all 0.3s ease;
            animation: fadeInUp 1s ease-out;
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.2);
        }

        .feature-icon {
            width: 80px;
            height: 80px;
            background: rgba(255,255,255,0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1rem;
            font-size: 2rem;
            animation: spin 3s linear infinite;
        }

        @keyframes spin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

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

        /* Pricing Section */
        .pricing-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .pricing-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 2rem;
            border-radius: 20px;
            text-align: center;
            color: white;
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .pricing-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: left 0.5s;
        }

        .pricing-card:hover::before {
            left: 100%;
        }

        .pricing-card:hover {
            transform: scale(1.05);
        }

        .pricing-card h3 {
            font-size: 1.8rem;
            margin-bottom: 1rem;
        }

        .price {
            font-size: 3rem;
            font-weight: bold;
            margin-bottom: 1rem;
        }

        .pricing-features {
            list-style: none;
            margin-bottom: 2rem;
        }

        .pricing-features li {
            margin-bottom: 0.5rem;
            padding: 0.5rem 0;
        }

        .subscribe-btn {
            background: rgba(255,255,255,0.2);
            color: white;
            border: 2px solid white;
            padding: 1rem 2rem;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 1.1rem;
        }

        .subscribe-btn:hover {
            background: white;
            color: #667eea;
            transform: translateY(-2px);
        }

        /* Free Trial Section */
        .trial-section {
            background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 50%, #fecfef 100%);
            padding: 4rem 0;
            text-align: center;
            border-radius: 20px;
            margin: 3rem 0;
        }

        .trial-content h3 {
            font-size: 2.5rem;
            color: #333;
            margin-bottom: 1rem;
        }

        .trial-description {
            font-size: 1.2rem;
            color: #666;
            margin-bottom: 2rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .trial-button {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            padding: 1.5rem 3rem;
            border: none;
            border-radius: 50px;
            font-size: 1.3rem;
            cursor: pointer;
            transition: all 0.3s ease;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        .trial-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.2);
            animation: none;
        }

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }

        .about-text {
            font-size: 1.2rem;
            line-height: 1.8;
            color: #666;
        }

        .about-image {
            text-align: center;
        }

        .about-graphic {
            width: 300px;
            height: 300px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 4rem;
            animation: rotate 10s linear infinite;
            margin: 0 auto;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        /* Signup Page Styles */
        .signup-page {
            display: none;
            min-height: 100vh;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 100px 0 50px;
        }

        .signup-page.active {
            display: block;
        }

        .signup-container {
            max-width: 600px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 3rem;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            animation: slideInUp 0.8s ease-out;
        }

        .signup-header {
            text-align: center;
            margin-bottom: 2rem;
        }

        .signup-header h2 {
            font-size: 2.5rem;
            background: linear-gradient(45deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 0.5rem;
        }

        .signup-header p {
            color: #666;
            font-size: 1.1rem;
        }

        .signup-form {
            display: grid;
            gap: 1.5rem;
        }

        .form-group {
            display: flex;
            flex-direction: column;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
        }

        .form-group label {
            font-weight: bold;
            color: #333;
            margin-bottom: 0.5rem;
            font-size: 1rem;
        }

        .form-group input,
        .form-group select {
            padding: 1rem;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            font-size: 1rem;
            transition: all 0.3s ease;
            background: white;
        }

        .form-group input:focus,
        .form-group select:focus {
            outline: none;
            border-color: #667eea;
            box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
            transform: translateY(-2px);
        }

        .checkbox-group {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin: 1rem 0;
        }

        .checkbox-group input[type="checkbox"] {
            width: 20px;
            height: 20px;
            accent-color: #667eea;
        }

        .checkbox-group label {
            margin: 0;
            font-weight: normal;
            color: #666;
            font-size: 0.9rem;
        }

        .signup-button {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            padding: 1.2rem 2rem;
            border: none;
            border-radius: 50px;
            font-size: 1.2rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 1rem;
        }

        .signup-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(102, 126, 234, 0.4);
        }

        .back-button {
            background: transparent;
            color: #667eea;
            border: 2px solid #667eea;
            padding: 0.8rem 1.5rem;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-bottom: 2rem;
            font-size: 1rem;
        }

        .back-button:hover {
            background: #667eea;
            color: white;
            transform: translateY(-2px);
        }

        .trial-badge {
            background: linear-gradient(45deg, #ff6b6b, #ee5a24);
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: bold;
            display: inline-block;
            margin-bottom: 1rem;
            animation: pulse 2s infinite;
        }

        /* Login Page Styles */
        .login-page {
            display: none;
            min-height: 100vh;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 100px 0 50px;
            position: relative;
            overflow: hidden;
        }

        .login-page.active {
            display: block;
        }

        .login-container {
            max-width: 450px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 3rem;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            animation: slideInUp 0.8s ease-out;
            position: relative;
            z-index: 2;
        }

        .login-header {
            text-align: center;
            margin-bottom: 2rem;
        }

        .login-header h2 {
            font-size: 2.5rem;
            background: linear-gradient(45deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 0.5rem;
        }

        .login-header p {
            color: #666;
            font-size: 1.1rem;
        }

        .login-form {
            display: grid;
            gap: 1.5rem;
        }

        .login-button {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            padding: 1.2rem 2rem;
            border: none;
            border-radius: 50px;
            font-size: 1.2rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 1rem;
        }

        .login-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(102, 126, 234, 0.4);
        }

        .forgot-password {
            text-align: center;
            margin-top: 1rem;
        }

        .forgot-password a {
            color: #667eea;
            text-decoration: none;
            font-size: 0.9rem;
            transition: all 0.3s ease;
        }

        .forgot-password a:hover {
            text-decoration: underline;
            color: #764ba2;
        }

        .signup-link {
            text-align: center;
            margin-top: 2rem;
            padding-top: 2rem;
            border-top: 1px solid #e0e0e0;
        }

        .signup-link p {
            color: #666;
            margin-bottom: 1rem;
        }

        .signup-link button {
            background: transparent;
            color: #667eea;
            border: 2px solid #667eea;
            padding: 0.8rem 1.5rem;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 1rem;
        }

        .signup-link button:hover {
            background: #667eea;
            color: white;
            transform: translateY(-2px);
        }

        /* Login page floating shapes */
        .login-shapes {
            position: absolute;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 1;
        }

        .login-shape {
            position: absolute;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            animation: float 8s ease-in-out infinite;
        }

        .login-shape:nth-child(1) {
            width: 100px;
            height: 100px;
            left: 20%;
            top: 20%;
            animation-delay: 0s;
        }

        .login-shape:nth-child(2) {
            width: 150px;
            height: 150px;
            right: 20%;
            top: 60%;
            animation-delay: 3s;
        }

        .login-shape:nth-child(3) {
            width: 80px;
            height: 80px;
            left: 70%;
            top: 30%;
            animation-delay: 6s;
        }

        /* Success Message */
        .success-message {
            display: none;
            text-align: center;
            padding: 2rem;
            background: linear-gradient(135deg, #4ecdc4 0%, #44a08d 100%);
            color: white;
            border-radius: 15px;
            margin-top: 2rem;
            animation: fadeInUp 0.5s ease-out;
        }

        .success-message.show {
            display: block;
        }

        .success-message h3 {
            font-size: 2rem;
            margin-bottom: 1rem;
        }

        .success-message p {
            font-size: 1.1rem;
            opacity: 0.9;
        }

        .success-icon {
            font-size: 4rem;
            margin-bottom: 1rem;
            animation: bounce 1s ease-out;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateY(0);
            }
            40% {
                transform: translateY(-20px);
            }
            60% {
                transform: translateY(-10px);
            }
        }

        /* Footer */
        footer {
            background: #333;
            color: white;
            text-align: center;
            padding: 2rem 0;
            border-radius: 20px 20px 0 0;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero h1 { font-size: 2.5rem; }
            .hero p { font-size: 1.2rem; }
            .about-content { grid-template-columns: 1fr; }
            .nav-links { display: none; }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <div class="container">
            <div class="nav-container">
                <div class="logo">Costico AI</div>
                <ul class="nav-links">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#pricing">Pricing</a></li>
                    <li><a href="#contact">Contact</a></li>
                    <li><a href="#" onclick="showLoginPage()">Login</a></li>
                </ul>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="floating-shapes">
            <div class="shape"></div>
            <div class="shape"></div>
            <div class="shape"></div>
        </div>
        <div class="hero-content">
            <h1>Transform Your Business with AI-Powered Cost Intelligence</h1>
            <p>Costico AI uses advanced machine learning to optimize your operational costs, reduce waste, and maximize profitability in real-time.</p>
            <a href="#pricing" class="cta-button">Start Optimizing Now</a>
        </div>
    </section>

    <div class="container">
        <!-- Features Section -->
        <section class="section">
            <h2>Why Choose Costico AI?</h2>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">🤖</div>
                    <h3>AI-Powered Analytics</h3>
                    <p>Advanced machine learning algorithms analyze your spending patterns and identify cost-saving opportunities automatically.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">📊</div>
                    <h3>Real-Time Insights</h3>
                    <p>Get instant visibility into your cost structure with dynamic dashboards and predictive analytics.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">💰</div>
                    <h3>Smart Optimization</h3>
                    <p>Automatically implement cost-saving strategies while maintaining operational efficiency and quality.</p>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section id="about" class="section">
            <h2>About Costico AI</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>Costico AI revolutionizes how businesses approach cost management by leveraging cutting-edge artificial intelligence and machine learning technologies. Our platform continuously monitors your operational expenses, identifies inefficiencies, and provides actionable insights to optimize your bottom line.</p>
                    <br>
                    <p>Founded by a team of data scientists and business optimization experts, we understand that every dollar saved is a dollar earned. Our mission is to democratize advanced cost intelligence, making it accessible to businesses of all sizes.</p>
                    <br>
                    <p>With Costico AI, you're not just getting a tool – you're getting a strategic partner that works 24/7 to ensure your business operates at peak financial efficiency.</p>
                </div>
                <div class="about-image">
                    <div class="about-graphic">AI</div>
                </div>
            </div>
        </section>

        <!-- Pricing Section -->
        <section id="pricing" class="section">
            <h2>Choose Your Plan</h2>
            <div class="pricing-grid">
                <div class="pricing-card">
                    <h3>Starter</h3>
                    <div class="price">$29<span style="font-size: 1rem;">/month</span></div>
                    <ul class="pricing-features">
                        <li>✓ Basic cost analytics</li>
                        <li>✓ Monthly reports</li>
                        <li>✓ Email support</li>
                        <li>✓ Up to 3 integrations</li>
                        <li>✓ Standard dashboard</li>
                    </ul>
                    <button class="subscribe-btn">Subscribe Now</button>
                </div>
                
                <div class="pricing-card">
                    <h3>Professional</h3>
                    <div class="price">$149<span style="font-size: 1rem;">/6 months</span></div>
                    <ul class="pricing-features">
                        <li>✓ Advanced AI insights</li>
                        <li>✓ Real-time monitoring</li>
                        <li>✓ Priority support</li>
                        <li>✓ Unlimited integrations</li>
                        <li>✓ Custom dashboards</li>
                        <li>✓ Predictive analytics</li>
                    </ul>
                    <button class="subscribe-btn">Subscribe Now</button>
                </div>
                
                <div class="pricing-card">
                    <h3>Enterprise</h3>
                    <div class="price">$499<span style="font-size: 1rem;">/year</span></div>
                    <ul class="pricing-features">
                        <li>✓ Full AI optimization suite</li>
                        <li>✓ Dedicated account manager</li>
                        <li>✓ 24/7 phone support</li>
                        <li>✓ White-label options</li>
                        <li>✓ API access</li>
                        <li>✓ Custom integrations</li>
                        <li>✓ Advanced reporting</li>
                    </ul>
                    <button class="subscribe-btn">Subscribe Now</button>
                </div>
            </div>
        </section>

        <!-- Free Trial Section -->
        <section class="trial-section">
            <div class="trial-content">
                <h3>Start Your Free Trial Today!</h3>
                <p class="trial-description">
                    Experience the full power of Costico AI with our comprehensive 14-day free trial. 
                    No credit card required, no hidden fees, and full access to all premium features. 
                    See how much you can save in just two weeks!
                </p>
                <button class="trial-button">Start 14-Day Free Trial</button>
            </div>
        </section>
    </div>

    <!-- Login Page -->
    <div id="login-page" class="login-page">
        <div class="login-shapes">
            <div class="login-shape"></div>
            <div class="login-shape"></div>
            <div class="login-shape"></div>
        </div>
        <div class="container">
            <div class="login-container">
                <button class="back-button" onclick="showMainPage()">← Back to Home</button>
                
                <div class="login-header">
                    <h2>Welcome Back!</h2>
                    <p>Sign in to your Costico AI dashboard</p>
                </div>

                <form class="login-form" onsubmit="handleLogin(event)">
                    <div class="form-group">
                        <label for="loginEmail">Email Address *</label>
                        <input type="email" id="loginEmail" name="loginEmail" required 
                               placeholder="Enter your email address">
                    </div>

                    <div class="form-group">
                        <label for="loginPassword">Password *</label>
                        <input type="password" id="loginPassword" name="loginPassword" required 
                               placeholder="Enter your password">
                    </div>

                    <div class="checkbox-group">
                        <input type="checkbox" id="rememberMe" name="rememberMe">
                        <label for="rememberMe">Remember me for 30 days</label>
                    </div>

                    <button type="submit" class="login-button">Sign In</button>
                </form>

                <div class="forgot-password">
                    <a href="#" onclick="alert('Password reset link sent to your email!')">Forgot your password?</a>
                </div>

                <div class="signup-link">
                    <p>Don't have an account yet?</p>
                    <button onclick="showSignupPage()">Start Free Trial</button>
                </div>

                <div id="login-success-message" class="success-message">
                    <div class="success-icon">🚀</div>
                    <h3>Login Successful!</h3>
                    <p>Welcome back to Costico AI!<br>
                    Redirecting to your dashboard...</p>
                </div>
            </div>
        </div>
    </div>

    <!-- Signup Page -->
    <div id="signup-page" class="signup-page">
        <div class="container">
            <div class="signup-container">
                <button class="back-button" onclick="showMainPage()">← Back to Home</button>
                
                <div class="signup-header">
                    <div class="trial-badge">14-Day Free Trial</div>
                    <h2>Join Costico AI Today!</h2>
                    <p>Start optimizing your costs in minutes. No credit card required.</p>
                </div>

                <form class="signup-form" onsubmit="handleSignup(event)">
                    <div class="form-row">
                        <div class="form-group">
                            <label for="firstName">First Name *</label>
                            <input type="text" id="firstName" name="firstName" required>
                        </div>
                        <div class="form-group">
                            <label for="lastName">Last Name *</label>
                            <input type="text" id="lastName" name="lastName" required>
                        </div>
                    </div>

                    <div class="form-group">
                        <label for="email">Email Address *</label>
                        <input type="email" id="email" name="email" required>
                    </div>

                    <div class="form-group">
                        <label for="company">Company Name *</label>
                        <input type="text" id="company" name="company" required>
                    </div>

                    <div class="form-row">
                        <div class="form-group">
                            <label for="phone">Phone Number</label>
                            <input type="tel" id="phone" name="phone">
                        </div>
                        <div class="form-group">
                            <label for="companySize">Company Size</label>
                            <select id="companySize" name="companySize">
                                <option value="">Select size...</option>
                                <option value="1-10">1-10 employees</option>
                                <option value="11-50">11-50 employees</option>
                                <option value="51-200">51-200 employees</option>
                                <option value="201-1000">201-1000 employees</option>
                                <option value="1000+">1000+ employees</option>
                            </select>
                        </div>
                    </div>

                    <div class="form-group">
                        <label for="industry">Industry</label>
                        <select id="industry" name="industry">
                            <option value="">Select industry...</option>
                            <option value="technology">Technology</option>
                            <option value="healthcare">Healthcare</option>
                            <option value="finance">Finance</option>
                            <option value="retail">Retail</option>
                            <option value="manufacturing">Manufacturing</option>
                            <option value="education">Education</option>
                            <option value="other">Other</option>
                        </select>
                    </div>

                    <div class="checkbox-group">
                        <input type="checkbox" id="terms" name="terms" required>
                        <label for="terms">I agree to the Terms of Service and Privacy Policy *</label>
                    </div>

                    <div class="checkbox-group">
                        <input type="checkbox" id="newsletter" name="newsletter">
                        <label for="newsletter">Send me product updates and optimization tips</label>
                    </div>

                    <button type="submit" class="signup-button">Complete Signup</button>
                </form>

                <div id="success-message" class="success-message">
                    <div class="success-icon">🎉</div>
                    <h3>Welcome to Costico AI!</h3>
                    <p>You have successfully signed up for your 14-day free trial.<br>
                    Setup instructions and login details will be sent to your email shortly.</p>
                </div>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p>&copy; 2025 Costico AI. All rights reserved. Transforming businesses through intelligent cost optimization.</p>
        </div>
    </footer>

    <script>
        // ChannelBoost script
        (function(w,d,s,u){let j=d.createElement(s);j.async=true;j.src="https://assets.channelboost.com/scripts/cts.js?uid=" + u;let f=d.getElementsByTagName(s)[0];f.parentNode.insertBefore(j,f);})(window,document,"script","139c1320-164e-42c4-9769-9e21765192c6");

        // Add smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Add button click handlers
        document.querySelectorAll('.subscribe-btn').forEach(button => {
            button.addEventListener('click', function() {
                alert('Redirecting to payment gateway...');
            });
        });

        // Wait for DOM to be fully loaded before adding event listeners
        document.addEventListener('DOMContentLoaded', function() {
            const trialButton = document.querySelector('.trial-button');
            if (trialButton) {
                trialButton.addEventListener('click', function() {
                    // Redirect to Apify console signup
                    window.open('https://console.apify.com/sign-up', '_blank');
                });
            }
        });

        // Show signup page
        function showSignupPage() {
            document.getElementById('signup-page').classList.add('active');
            document.body.style.overflow = 'hidden';
            window.scrollTo(0, 0);
        }

        // Show main page
        function showMainPage() {
            document.getElementById('signup-page').classList.remove('active');
            document.getElementById('login-page').classList.remove('active');
            document.body.style.overflow = 'auto';
        }

        // Show login page
        function showLoginPage() {
            document.getElementById('login-page').classList.add('active');
            document.body.style.overflow = 'hidden';
            window.scrollTo(0, 0);
        }

        // Handle login form submission
        function handleLogin(event) {
            event.preventDefault();
            
            // Get form data
            const formData = new FormData(event.target);
            const email = formData.get('loginEmail');
            const password = formData.get('loginPassword');
            
            // Basic validation
            if (!email || !password) {
                alert('Please fill in all required fields.');
                return;
            }
            
            // Simple email format validation
            const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            if (!emailRegex.test(email)) {
                alert('Please enter a valid email address.');
                return;
            }
            
            // Hide form and show success message
            event.target.style.display = 'none';
            document.getElementById('login-success-message').classList.add('show');
            
            // Auto redirect after 3 seconds
            setTimeout(() => {
                alert('Redirecting to Costico AI Dashboard...\n\nDemo: In a real application, you would be redirected to the main dashboard with your cost optimization data.');
                showMainPage();
                // Reset form
                event.target.reset();
                event.target.style.display = 'grid';
                document.getElementById('login-success-message').classList.remove('show');
            }, 3000);
        }

        // Handle signup form submission
        function handleSignup(event) {
            event.preventDefault();
            
            // Get form data
            const formData = new FormData(event.target);
            const firstName = formData.get('firstName');
            const lastName = formData.get('lastName');
            const email = formData.get('email');
            const company = formData.get('company');
            
            // Validate required fields
            if (!firstName || !lastName || !email || !company) {
                alert('Please fill in all required fields.');
                return;
            }
            
            // Hide form and show success message
            event.target.style.display = 'none';
            document.getElementById('success-message').classList.add('show');
            
            // Auto redirect to main page after 5 seconds
            setTimeout(() => {
                showMainPage();
                // Reset form
                event.target.reset();
                event.target.style.display = 'grid';
                document.getElementById('success-message').classList.remove('show');
            }, 5000);
        }

        // Add floating animation to shapes
        const shapes = document.querySelectorAll('.shape');
        shapes.forEach((shape, index) => {
            shape.style.animationDelay = `${index * 2}s`;
        });
    </script>
</body>
</html>
