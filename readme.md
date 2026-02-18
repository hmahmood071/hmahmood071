# Mahmood Hassan - Colorful Portfolio

This is the HTML, CSS, and JS code for my colorful portfolio website. It includes a hero section, about, services, portfolio, contact, responsive navbar, gradient buttons, scroll reveal animation, and more.

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mahmood Hassan - Colorful Portfolio</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;800&display=swap" rel="stylesheet">

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
    scroll-behavior: smooth;
}

body {
    background: #fefefe;
    color: #222;
}

/* ===== Navbar ===== */
header {
    width: 100%;
    padding: 20px 8%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: linear-gradient(90deg, #6a11cb, #2575fc);
    position: fixed;
    top: 0;
    z-index: 1000;
    box-shadow: 0 5px 20px rgba(0,0,0,0.2);
}

.logo {
    font-weight: 800;
    font-size: 24px;
    color: #fff;
}

nav {
    display: flex;
}

nav a {
    margin-left: 25px;
    text-decoration: none;
    color: #fff;
    font-weight: 500;
    transition: 0.3s;
}

nav a:hover {
    color: #42e5f5;
}

/* Hamburger */
.menu-toggle {
    display: none;
    font-size: 28px;
    cursor: pointer;
    color: #fff;
}

/* ===== Sections ===== */
section {
    padding: 120px 8%;
    min-height: 100vh;
    opacity: 0;
    transform: translateY(50px);
    transition: all 0.6s ease-out;
    border-radius: 20px;
    margin-top: 20px;
}

/* Hero */
.hero {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 40px;
    background: linear-gradient(135deg, #6a11cb, #2575fc);
    color: #fff;
    padding: 150px 8%;
}

.hero-text h1 {
    font-size: 52px;
    margin-bottom: 20px;
}

.hero-text p {
    font-size: 18px;
    margin-bottom: 30px;
}

/* Hero image */
.hero-image img {
    width: 600px;
    max-width: 100%;
    border-radius: 20px;
    box-shadow: 0 20px 50px rgba(106,17,203,0.4), 0 10px 30px rgba(37,117,252,0.3);
    transition: transform 0.5s ease;
}

.hero-image img:hover {
    transform: scale(1.05);
}

/* Buttons */
.btn {
    padding: 14px 32px;
    border-radius: 40px;
    border: none;
    cursor: pointer;
    font-weight: 600;
    font-size: 16px;
    margin-right: 15px;
    transition: 0.4s;
}

.btn-gradient {
    background: linear-gradient(45deg, #6a11cb, #2575fc, #42e5f5);
    background-size: 300% 300%;
    color: #fff;
}

.btn-gradient:hover {
    animation: gradientMove 3s ease infinite;
    transform: translateY(-4px);
    box-shadow: 0 12px 30px rgba(66, 229, 245, 0.5);
}

@keyframes gradientMove {
    0%{ background-position:0% 50%; }
    50%{ background-position:100% 50%; }
    100%{ background-position:0% 50%; }
}

/* Other sections colors */
.about { background: #f0f4f8; color: #222; }
.services { background: #fffae3; color: #222; }
.portfolio { background: #e0f7fa; color: #222; }
.contact { background: #ffe3e3; color: #222; }

/* Headings */
h2 {
    text-align: center;
    margin-bottom: 30px;
    font-size: 38px;
}

/* Paragraphs */
p {
    max-width: 700px;
    margin: auto;
    text-align: center;
    line-height: 1.7;
}

/* Contact Form */
form {
    max-width: 500px;
    margin: 20px auto;
    display: flex;
    flex-direction: column;
    gap: 15px;
}

input, textarea {
    padding: 12px;
    border-radius: 10px;
    border: none;
    outline: none;
}

textarea { resize: none; }

/* ===== Responsive ===== */
@media (max-width: 992px) {
    .hero {
        flex-direction: column;
        text-align: center;
    }

    .hero-text h1 { font-size: 40px; }
}

@media (max-width: 768px) {
    nav {
        position: absolute;
        top: 70px;
        right: 0;
        background: #fff;
        flex-direction: column;
        width: 200px;
        padding: 20px;
        display: none;
        border-radius: 10px;
    }

    nav.active { display: flex; }

    nav a { margin: 15px 0; color: #222; }

    .menu-toggle { display: block; }
}
</style>
</head>
<body>

<header>
    <div class="logo">MAHMOOD</div>
    <div class="menu-toggle" onclick="toggleMenu()">☰</div>
    <nav id="nav">
        <a href="#home">Home</a>
        <a href="#about">About</a>
        <a href="#services">Services</a>
        <a href="#portfolio">Portfolio</a>
        <a href="#contact">Contact</a>
    </nav>
</header>

<section class="hero" id="home">
    <div class="hero-text">
        <h1>Welcome to My Colorful World</h1>
        <p>I create digital experiences that are vibrant, fast, and built to last.</p>
        <button class="btn btn-gradient">Get Started</button>
    </div>
    <div class="hero-image">
        <img src="profile.png" alt="Mahmood Hassan">
    </div>
</section>

<section class="about" id="about">
    <h2>About Me</h2>
    <p>I focus on clarity, structure, and performance. Strong code ages well.</p>
</section>

<section class="services" id="services">
    <h2>Services</h2>
    <p>Website Design, Frontend Development, Responsive Layout, UI Optimization.</p>
</section>

<section class="portfolio" id="portfolio">
    <h2>Portfolio</h2>
    <p>Showcase your best projects here.</p>
</section>

<section class="contact" id="contact">
    <h2>Contact Me</h2>
    <form onsubmit="return validateForm()">
        <input type="text" id="name" placeholder="Your Name">
        <input type="email" id="email" placeholder="Your Email">
        <textarea rows="4" id="message" placeholder="Your Message"></textarea>
        <button class="btn btn-gradient" type="submit">Send Message</button>
    </form>
</section>

<script>
function toggleMenu() {
    document.getElementById("nav").classList.toggle("active");
}

function validateForm() {
    let name = document.getElementById("name").value;
    let email = document.getElementById("email").value;
    let message = document.getElementById("message").value;

    if(name === "" || email === "" || message === "") {
        alert("Please fill in all fields.");
        return false;
    }

    alert("Message sent successfully!");
    return true;
}

// Scroll Reveal
const sections = document.querySelectorAll('section');
window.addEventListener('scroll', () => {
    sections.forEach(sec => {
        const rect = sec.getBoundingClientRect();
        if(rect.top < window.innerHeight - 100){
            sec.style.opacity = 1;
            sec.style.transform = 'translateY(0)';
        }
    });
});
</script>

</body>
</html>
