<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css">
    <title>V. Vishnu's Portfolio</title>
    <style>
        /* General styling */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
        body {
            background-color: #000;
            color: #fff;
            overflow-x: hidden;
        }
        header {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 1rem 5%;
            background-color: transparent;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 100;
        }
        .logo {
            font-size: 2.5rem;
            color: #b74b4b;
            font-weight: bold;
        }
        nav a {
            font-size: 1.6rem;
            color: #fff;
            margin-left: 2rem;
            text-decoration: none;
        }
        nav a.active, nav a:hover {
            color: #b74b4b;
            border-bottom: 2px solid #b74b4b;
        }
        .home {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            text-align: center;
            padding-top: 80px;
        }
        .home h1 {
            font-size: 4rem;
            font-weight: 700;
        }
        .home h1 span {
            color: #b74b4b;
        }
        .typing-text {
            font-size: 2rem;
            font-weight: 600;
            margin-top: 1rem;
        }
        .home img {
            border-radius: 50%;
            width: 180px;
            margin-top: 20px;
            border: 4px solid #b74b4b;
        }
        .social-icons a {
            font-size: 1.8rem;
            color: #b74b4b;
            margin: 0 1rem;
            transition: color 0.3s;
        }
        .social-icons a:hover {
            color: #fff;
        }
        .contact {
            text-align: center;
            margin: 2rem 0;
        }
        .contact input, .contact textarea {
            width: 80%;
            margin: 0.5rem 0;
            padding: 0.8rem;
            border-radius: 8px;
            border: 1px solid #ddd;
        }
        .contact button {
            background-color: #b74b4b;
            color: #fff;
            padding: 0.8rem 2rem;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .contact button:hover {
            background-color: #ff69b4;
        }
        footer {
            text-align: center;
            padding: 1rem 0;
            background-color: #222;
            color: #fff;
        }
        /* Responsive Navigation */
        @media (max-width: 600px) {
            nav a {
                display: block;
                margin: 1rem 0;
                text-align: center;
            }
        }
        
    </style>
</head>
<body>

    <!-- Header -->
    <header>
        <a href="#" class="logo">V. Vishnu</a>
        <nav>
            <a href="#" class="active">Home</a>
            <a href="#">About</a>
            <a href="#">Services</a>
            <a href="#">Projects</a>
            <a href="#">Contact</a>
        </nav>
    </header>

    <!-- Home Section -->
    <section class="home">
        <img src="vishnu7.png" alt="V. Vishnu Profile Picture">
        <h1>Hi, I'm <span>V. Vishnu</span></h1>
        <div class="typing-text">
            <span id="typing"></span>
        </div>
        <div class="social-icons">
            <a href="https://github.com/Vishnu-tppr" target="_blank"><i class="fab fa-github"></i></a>
            <a href="https://www.linkedin.com/in/vishnu-v-31583b327?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app" target="_blank"><i class="fab fa-linkedin"></i></a>
            <a href="mailto:Vishnu.tppr@gmail.com"><i class="fas fa-envelope"></i></a>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact">
        <h2>Contact Me</h2>
        <form id="contactForm">
            <input type="text" placeholder="Your Name" required>
            <input type="email" placeholder="Your Email" required>
            <textarea placeholder="Your Message" rows="4" required></textarea>
            <button type="submit">Send Message</button>
        </form>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2025 V.Vishnu</p>
    </footer>

    <!-- JavaScript for Typing Effect -->
    <script>
        const words = ["1st Year CSE", "Upcoming Software Developer", "Problem Solver", "Web Developer"];
        let wordIndex = 0;
        let charIndex = 0;
        let currentText = "";
        let typing = true;

        function type() {
            if (typing) {
                if (charIndex < words[wordIndex].length) {
                    currentText += words[wordIndex].charAt(charIndex);
                    document.getElementById("typing").textContent = currentText;
                    charIndex++;
                    setTimeout(type, 150);
                } else {
                    typing = false;
                    setTimeout(type, 1000);
                }
            } else {
                if (charIndex > 0) {
                    currentText = currentText.slice(0, -1);
                    document.getElementById("typing").textContent = currentText;
                    charIndex--;
                    setTimeout(type, 100);
                } else {
                    typing = true;
                    wordIndex = (wordIndex + 1) % words.length;
                    setTimeout(type, 500);
                }
            }
        }
        document.addEventListener("DOMContentLoaded", type);
    </script>
</body>
</html>

