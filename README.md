<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>My Travel Blog</title>
    <style>
        /* General Reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* Body and Fonts */
        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            background-color: #f9f9f9;
            color: #333;
        }

        h1,
        h2,
        h3 {
            font-family: 'Georgia', serif;
            color: #2c3e50;
        }

        /* Navigation Bar */
        header {
            background-color: #2c3e50;
            padding: 10px 0;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
            opacity: 0;
            animation: headerAnimation 1s ease-out forwards; /* Animation on header */
        }

        @keyframes headerAnimation {
            0% {
                opacity: 0;
                transform: translateY(-20px);
            }

            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 20px;
        }

        nav .logo h1 {
            color: #fff;
            font-size: 1.8rem;
            animation: slideInLogo 1s ease-out forwards; /* Animation on logo */
        }

        @keyframes slideInLogo {
            0% {
                transform: translateX(-100%);
            }

            100% {
                transform: translateX(0);
            }
        }

        nav .nav-links {
            list-style: none;
            display: flex;
            animation: fadeInLinks 1.5s ease-out forwards; /* Animation on links */
        }

        @keyframes fadeInLinks {
            0% {
                opacity: 0;
                transform: translateY(20px);
            }

            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        nav .nav-links li {
            margin: 0 15px;
        }

        nav .nav-links a {
            color: #fff;
            text-decoration: none;
            font-size: 1.1rem;
            transition: color 0.3s ease;
        }

        nav .nav-links a:hover {
            color: #e74c3c;
        }

        /* Hero Section */
        .hero {
            background: url('https://via.placeholder.com/1600x600') no-repeat center center/cover;
            height: 60vh;
            color: #fff;
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
            position: relative;
            background-attachment: fixed;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.4);
        }

        .hero h2 {
            font-size: 3rem;
            margin-bottom: 10px;
            z-index: 1;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 20px;
            z-index: 1;
        }

        .hero button {
            padding: 12px 25px;
            background-color: #e74c3c;
            color: #fff;
            border: none;
            font-size: 1.1rem;
            cursor: pointer;
            border-radius: 5px;
            transition: background-color 0.3s ease, transform 0.3s ease;
            z-index: 1;
        }

        .hero button:hover {
            background-color: #c0392b;
            transform: scale(1.05);
        }

        /* About Section */
        .about {
            padding: 60px 20px;
            text-align: center;
            background-color: #ecf0f1;
        }

        .about h2 {
            font-size: 2rem;
            margin-bottom: 20px;
            color: #2c3e50;
        }

        .about p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto;
            line-height: 1.6;
        }

        .about ul {
            list-style-type: none;
            margin-top: 30px;
            padding: 0;
            font-size: 1.1rem;
            text-align: left;
            display: inline-block;
        }

        .about ul li {
            margin: 10px 0;
        }

        /* Destinations Section */
        .destinations {
            padding: 60px 20px;
            text-align: center;
        }

        .destinations h2 {
            font-size: 2.5rem;
            margin-bottom: 30px;
            color: #2c3e50;
        }

        .destinations-container {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 20px;
        }

        .destination-card {
            background: #fff;
            width: 30%;
            margin-bottom: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            text-align: center;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .destination-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 8px 15px rgba(0, 0, 0, 0.2);
        }

        .destination-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .destination-card img:hover {
            transform: scale(1.1);
        }

        .destination-card h3 {
            margin: 10px 0;
            font-size: 1.5rem;
            color: #e74c3c;
        }

        .destination-card p {
            padding: 0 10px;
            color: #7f8c8d;
        }

        /* Contact Section */
        .contact {
            background-color: #34495e;
            color: #fff;
            padding: 60px 20px;
            text-align: center;
        }

        .contact h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
        }

        .contact p {
            font-size: 1.2rem;
            margin-bottom: 30px;
        }

        .contact form {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
        }

        .contact input,
        .contact textarea {
            padding: 15px;
            width: 320px;
            border: 1px solid #fff;
            border-radius: 5px;
            background-color: #2c3e50;
            color: #fff;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .contact input:focus,
        .contact textarea:focus {
            border-color: #e74c3c;
            outline: none;
        }

        .contact button {
            padding: 12px 25px;
            background-color: #e74c3c;
            color: #fff;
            border: none;
            font-size: 1.1rem;
            cursor: pointer;
            border-radius: 5px;
            transition: background-color 0.3s ease, transform 0.3s ease;
        }

        .contact button:hover {
            background-color: #c0392b;
            transform: scale(1.05);
        }

        /* Footer */
        footer {
            background-color: #2c3e50;
            color: #fff;
            text-align: center;
            padding: 15px 0;
            font-size: 1rem;
        }

        footer p {
            margin: 0;
        }
    </style>
</head>

<body>

    <!-- Navigation Bar -->
    <header>
        <nav>
            <div class="logo">
                <h1>Travel Explorer</h1>
            </div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about" id="aboutLink">About</a></li>
                <li><a href="#destinations">Destinations</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h2>Explore The World With Us</h2>
            <p>Join us on an unforgettable adventure around the world! From the bustling streets of New York City to the serene beaches of Bali, we've got you covered.</p>
            <button onclick="window.location.href='#destinations'">Start Exploring</button>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <h2>About Us</h2>
        <p>At Travel Explorer, we believe that travel is not just about visiting new places but about experiencing the culture, people, and cuisine. We are a group of passionate explorers who want to share the best of our adventures with you. Our mission is to inspire you to embark on your own journey and see the world through our eyes.</p>
        <ul>
            <li><strong>Expert Travel Tips:</strong> We provide detailed guides and tips on how to make the most out of your travels.</li>
            <li><strong>Local Experiences:</strong> Our content focuses on authentic experiences, not just tourist attractions.</li>
            <li><strong>Exclusive Offers:</strong> We work with hotels and tour operators to bring you exclusive deals.</li>
        </ul>
    </section>

    <!-- Destinations Section -->
    <section id="destinations" class="destinations">
        <h2>Top Destinations</h2>
        <div class="destinations-container">
            <div class="destination-card">
                <img src="https://via.placeholder.com/300" alt="Bali">
                <h3>Bali, Indonesia</h3>
                <p>Known for its stunning beaches, lush landscapes, and rich culture, Bali offers something for everyone, whether you’re a thrill-seeker or someone looking to unwind in paradise.</p>
            </div>
            <div class="destination-card">
                <img src="https://via.placeholder.com/300" alt="Paris">
                <h3>Paris, France</h3>
                <p>The City of Love. From the Eiffel Tower to the Louvre, Paris is full of iconic landmarks, incredible food, and an atmosphere unlike any other city in the world.</p>
            </div>
            <div class="destination-card">
                <img src="https://via.placeholder.com/300" alt="New York">
                <h3>New York City, USA</h3>
                <p>New York is the epitome of excitement. Whether you’re visiting Times Square, Central Park, or the Statue of Liberty, the energy of the city will captivate you.</p>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <h2>Contact Us</h2>
        <p>If you have any questions or need travel advice, feel free to reach out to us. We’re here to help you plan your next adventure!</p>
        <form onsubmit="hideAboutSection(event)">
            <input type="text" placeholder="Your Name" required>
            <input type="email" id="userEmail" placeholder="Your Email" required>
            <textarea placeholder="Your Message" required></textarea>
            <button type="submit">Send Message</button>
        </form>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2025 Travel Explorer. All rights reserved.</p>
    </footer>

    <script>
        function hideAboutSection(event) {
            event.preventDefault();  // Prevent form submission
            var email = document.getElementById("userEmail").value;

            if (email) {
                document.getElementById("about").style.display = "none"; // Hide the About section if email is entered
            }
        }
    </script>

</body>

</html>
