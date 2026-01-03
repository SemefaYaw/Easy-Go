<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Easy Go - Multi-Service Marketplace</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Reset & Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            line-height: 1.6;
            color: #333;
            background-color: #f8f9fa;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* Header */
        header {
            background: linear-gradient(135deg, #3a7bd5 0%, #00d2ff 100%);
            color: white;
            padding: 1rem 0;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .logo h1 {
            font-size: 2rem;
            font-weight: 700;
        }
        
        nav ul {
            display: flex;
            list-style: none;
            gap: 1.5rem;
        }
        
        nav a {
            color: white;
            text-decoration: none;
            font-weight: 600;
            padding: 5px 10px;
            border-radius: 4px;
            transition: background-color 0.3s ease;
        }
        
        nav a:hover, nav a.active {
            background-color: rgba(255, 255, 255, 0.2);
        }
        
        /* Hero */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), 
                        url('https://images.unsplash.com/photo-1556742049-0cfed4f6a45d?ixlib=rb-4.0.3&auto=format&fit=crop&w=1950&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            text-align: center;
            padding: 5rem 1rem;
        }
        
        .hero h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
        }
        
        .btn {
            display: inline-block;
            background: #3a7bd5;
            color: white;
            padding: 12px 30px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
        }
        
        .btn:hover {
            background: #2a6bc5;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .btn-small {
            padding: 8px 20px;
            font-size: 0.9rem;
        }
        
        /* Services */
        .section-title {
            text-align: center;
            margin: 3rem 0 2rem;
            font-size: 2rem;
            color: #2c3e50;
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }
        
        .card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s ease;
        }
        
        .card:hover {
            transform: translateY(-5px);
        }
        
        .card-icon {
            background: #3a7bd5;
            color: white;
            font-size: 2rem;
            padding: 1.5rem;
            text-align: center;
        }
        
        .card-content {
            padding: 1.5rem;
            text-align: center;
        }
        
        .card h3 {
            color: #2c3e50;
            margin-bottom: 0.5rem;
        }
        
        .card p {
            color: #666;
            margin-bottom: 1rem;
        }
        
        /* How It Works */
        .steps {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin: 2rem 0 3rem;
        }
        
        .step {
            text-align: center;
            padding: 1rem;
        }
        
        .step-number {
            display: inline-block;
            width: 50px;
            height: 50px;
            line-height: 50px;
            background: #3a7bd5;
            color: white;
            border-radius: 50%;
            font-weight: 700;
            margin-bottom: 1rem;
        }
        
        /* Contact */
        .contact {
            background: white;
            padding: 3rem;
            border-radius: 10px;
            margin-bottom: 3rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        .contact-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            align-items: center;
        }
        
        .phone-link {
            display: inline-block;
            background: #3a7bd5;
            color: white;
            padding: 12px 25px;
            border-radius: 50px;
            font-weight: 600;
            text-decoration: none;
            margin-top: 1rem;
        }
        
        .contact-image img {
            width: 100%;
            border-radius: 10px;
        }
        
        /* Footer */
        footer {
            background: #2c3e50;
            color: white;
            padding: 3rem 0 1.5rem;
        }
        
        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .footer-column h4 {
            color: #3a7bd5;
            margin-bottom: 1rem;
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column li {
            margin-bottom: 0.5rem;
        }
        
        .footer-column a {
            color: #ddd;
            text-decoration: none;
            transition: color 0.3s ease;
        }
        
        .footer-column a:hover {
            color: #3a7bd5;
        }
        
        .copyright {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid #444;
            color: #aaa;
            font-size: 0.9rem;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                gap: 1rem;
            }
            
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .hero h2 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .section-title {
                font-size: 1.8rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <div class="logo">
                <i class="fas fa-bolt fa-2x"></i>
                <h1>Easy Go</h1>
            </div>
            <nav>
                <ul>
                    <li><a href="#" class="active">Home</a></li>
                    <li><a href="#services">Services</a></li>
                    <li><a href="#how-it-works">How It Works</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero -->
    <section class="hero">
        <div class="container">
            <h2>All Services, One Platform</h2>
            <p>Book transportation, home services, appointments, and more with just a few clicks. EasyGo connects you with trusted professionals.</p>
            <a href="#services" class="btn">Explore Services</a>
        </div>
    </section>

    <!-- Services -->
    <div class="container">
        <h2 class="section-title" id="services">Our Services</h2>
        <div class="services-grid">
            <div class="card">
                <div class="card-icon">
                    <i class="fas fa-car"></i>
                </div>
                <div class="card-content">
                    <h3>Transportation</h3>
                    <p>Book rides instantly with our Uber-like service. Choose from economy, premium, or shared rides.</p>
                    <a href="#" class="btn btn-small">Book Now</a>
                </div>
            </div>
            
            <div class="card">
                <div class="card-icon">
                    <i class="fas fa-home"></i>
                </div>
                <div class="card-content">
                    <h3>Home Services</h3>
                    <p>Find reliable professionals for plumbing, electrical work, cleaning, and other home services.</p>
                    <a href="#" class="btn btn-small">Find Help</a>
                </div>
            </div>
            
            <div class="card">
                <div class="card-icon">
                    <i class="fas fa-calendar-check"></i>
                </div>
                <div class="card-content">
                    <h3>Appointments</h3>
                    <p>Schedule appointments with doctors, beauty professionals, tutors, and other service providers.</p>
                    <a href="#" class="btn btn-small">Book Now</a>
                </div>
            </div>
            
            <div class="card">
                <div class="card-icon">
                    <i class="fas fa-plus-circle"></i>
                </div>
                <div class="card-content">
                    <h3>More Services</h3>
                    <p>Discover other on-demand services including delivery, pet care, tutoring, and event planning.</p>
                    <a href="#" class="btn btn-small">Explore</a>
                </div>
            </div>
        </div>
    </div>

    <!-- How It Works -->
    <div class="container">
        <h2 class="section-title" id="how-it-works">How EasyGo Works</h2>
        <div class="steps">
            <div class="step">
                <div class="step-number">1</div>
                <h3>Choose Service</h3>
                <p>Select from our wide range of service categories based on your needs.</p>
            </div>
            <div class="step">
                <div class="step-number">2</div>
                <h3>Book & Schedule</h3>
                <p>Pick a time that works for you and confirm your booking instantly.</p>
            </div>
            <div class="step">
                <div class="step-number">3</div>
                <h3>Service Delivery</h3>
                <p>Our verified professionals arrive on time to deliver quality service.</p>
            </div>
            <div class="step">
                <div class="step-number">4</div>
                <h3>Rate & Review</h3>
                <p>Share your experience to help us maintain service quality standards.</p>
            </div>
        </div>
    </div>

    <!-- Contact -->
    <div class="container">
        <section class="contact" id="contact">
            <h2 class="section-title">Contact Us</h2>
            <div class="contact-container">
                <div class="contact-info">
                    <h3>Need Help? We're Here For You</h3>
                    <p>Have questions about our services or need assistance with a booking? Our customer support team is available 7 days a week.</p>
                    <p>You can reach us directly at:</p>
                    <a href="tel:0547097687" class="phone-link">
                        <i class="fas fa-phone-alt"></i> 054 709 7687
                    </a>
                    <p style="margin-top: 1rem;">Or email: <strong>support@easygo.com</strong></p>
                </div>
                <div class="contact-image">
                    <img src="https://images.unsplash.com/photo-1551836026-d5c2c0b4d3a3?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Customer Support">
                </div>
            </div>
        </section>
    </div>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-grid">
                <div class="footer-column">
                    <h4>EasyGo</h4>
                    <p>Your one-stop platform for all on-demand services. Connecting customers with trusted professionals.</p>
                </div>
                <div class="footer-column">
                    <h4>Quick Links</h4>
                    <ul>
                        <li><a href="#">Home</a></li>
                        <li><a href="#services">Services</a></li>
                        <li><a href="#how-it-works">How It Works</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h4>Services</h4>
                    <ul>
                        <li><a href="#">Transportation</a></li>
                        <li><a href="#">Home Services</a></li>
                        <li><a href="#">Appointments</a></li>
                        <li><a href="#">More Services</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h4>Contact</h4>
                    <ul>
                        <li><i class="fas fa-phone"></i> 054 709 7687</li>
                        <li><i class="fas fa-envelope"></i> support@easygo.com</li>
                        <li><i class="fas fa-map-marker-alt"></i> Accra, Ghana</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 EasyGo Multi-Service Marketplace. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if(targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 100,
                        behavior: 'smooth'
                    });
                }
            });
        });
    </script>
</body>
</html>
