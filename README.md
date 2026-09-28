<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Personal portfolio website">
  <title>Itodo Caleb | Portfolio</title>

  <style>
    /* =========================
       RESET & GLOBAL STYLES
    ========================== */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      scroll-behavior: smooth;
    }

    :root {
      --primary: #6366f1;
      --primary-dark: #4f46e5;
      --secondary: #8b5cf6;
      --dark: #0f172a;
      --dark-2: #1e293b;
      --light: #f8fafc;
      --gray: #64748b;
      --white: #ffffff;
      --success: #16a34a;
      --danger: #dc2626;
      --border: #e2e8f0;
    }

    body {
      font-family: Arial, Helvetica, sans-serif;
      line-height: 1.6;
      color: var(--dark);
      background: var(--white);
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    ul {
      list-style: none;
    }

    img {
      max-width: 100%;
      display: block;
    }

    .container {
      width: 90%;
      max-width: 1150px;
      margin: auto;
    }

    section {
      padding: 100px 0;
    }

    .section-title {
      text-align: center;
      margin-bottom: 50px;
    }

    .section-title h2 {
      font-size: 2.5rem;
      margin-bottom: 10px;
    }

    .section-title p {
      color: var(--gray);
    }

    .btn {
      display: inline-block;
      padding: 13px 25px;
      border-radius: 8px;
      font-weight: bold;
      transition: 0.3s ease;
      cursor: pointer;
      border: none;
    }

    .btn-primary {
      background: var(--primary);
      color: var(--white);
    }

    .btn-primary:hover {
      background: var(--primary-dark);
      transform: translateY(-2px);
    }

    .btn-outline {
      border: 2px solid var(--primary);
      color: var(--primary);
      margin-left: 10px;
    }

    .btn-outline:hover {
      background: var(--primary);
      color: var(--white);
    }

    /* =========================
       NAVBAR
    ========================== */
    header {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      z-index: 1000;
      background: rgba(255, 255, 255, 0.95);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid #eee;
    }

    nav {
      height: 70px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .logo {
      font-size: 1.5rem;
      font-weight: 800;
      color: var(--primary);
    }

    .nav-links {
      display: flex;
      gap: 30px;
      align-items: center;
    }

    .nav-links a {
      font-weight: 600;
      transition: 0.3s;
    }

    .nav-links a:hover {
      color: var(--primary);
    }

    .menu-btn {
      display: none;
      font-size: 1.7rem;
      border: none;
      background: none;
      cursor: pointer;
    }

    /* =========================
       HOME
    ========================== */
    #home {
      min-height: 100vh;
      display: flex;
      align-items: center;
      background:
        radial-gradient(circle at 10% 20%, rgba(99, 102, 241, 0.15), transparent 30%),
        radial-gradient(circle at 90% 80%, rgba(139, 92, 246, 0.15), transparent 30%),
        var(--light);
    }

    .hero {
      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      align-items: center;
      gap: 60px;
      padding-top: 70px;
    }

    .hero-content h4 {
      color: var(--primary);
      font-size: 1.1rem;
      margin-bottom: 10px;
    }

    .hero-content h1 {
      font-size: clamp(2.5rem, 6vw, 4.5rem);
      line-height: 1.1;
      margin-bottom: 20px;
    }

    .hero-content h1 span {
      color: var(--primary);
    }

    .hero-content p {
      max-width: 600px;
      color: var(--gray);
      font-size: 1.1rem;
      margin-bottom: 30px;
    }

    .hero-image {
      display: flex;
      justify-content: center;
    }

    .profile-circle {
      width: 330px;
      height: 330px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      font-size: 5rem;
      font-weight: bold;
      box-shadow: 0 25px 60px rgba(79, 70, 229, 0.3);
    }

    /* =========================
       ABOUT
    ========================== */
    #about {
      background: var(--white);
    }

    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 60px;
      align-items: center;
    }

    .about-image {
      height: 400px;
      border-radius: 20px;
      background: linear-gradient(135deg, #6366f1, #8b5cf6);
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      font-size: 6rem;
      font-weight: bold;
    }

    .about-content h3 {
      font-size: 2rem;
      margin-bottom: 20px;
    }

    .about-content p {
      color: var(--gray);
      margin-bottom: 15px;
    }

    .about-info {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 15px;
      margin-top: 25px;
    }

    .info-item strong {
      display: block;
      color: var(--dark);
    }

    .info-item span {
      color: var(--gray);
    }

    /* =========================
       SKILLS
    ========================== */
    #skills {
      background: var(--light);
    }

    .skills-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 25px 50px;
    }

    .skill {
      margin-bottom: 15px;
    }

    .skill-header {
      display: flex;
      justify-content: space-between;
      margin-bottom: 8px;
      font-weight: bold;
    }

    .skill-bar {
      height: 10px;
      background: #e2e8f0;
      border-radius: 20px;
      overflow: hidden;
    }

    .skill-progress {
      height: 100%;
      background: linear-gradient(90deg, var(--primary), var(--secondary));
      border-radius: 20px;
    }

    /* =========================
       PROJECTS
    ========================== */
    #projects {
      background: var(--white);
    }

    .projects-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 25px;
    }

    .project-card {
      background: white;
      border: 1px solid var(--border);
      border-radius: 15px;
      overflow: hidden;
      transition: 0.3s ease;
    }

    .project-card:hover {
      transform: translateY(-8px);
      box-shadow: 0 15px 35px rgba(15, 23, 42, 0.1);
    }

    .project-image {
      height: 200px;
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      font-size: 3rem;
      font-weight: bold;
    }

    .project-content {
      padding: 25px;
    }

    .project-content h3 {
      margin-bottom: 10px;
    }

    .project-content p {
      color: var(--gray);
      margin-bottom: 20px;
    }

    .tags {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-bottom: 20px;
    }

    .tag {
      background: #eef2ff;
      color: var(--primary);
      padding: 5px 10px;
      border-radius: 20px;
      font-size: 0.8rem;
      font-weight: bold;
    }

    .project-link {
      color: var(--primary);
      font-weight: bold;
    }

    /* =========================
       CONTACT
    ========================== */
    #contact {
      background: var(--light);
    }

    .contact-grid {
      display: grid;
      grid-template-columns: 0.8fr 1.2fr;
      gap: 50px;
    }

    .contact-info h3 {
      font-size: 2rem;
      margin-bottom: 15px;
    }

    .contact-info > p {
      color: var(--gray);
      margin-bottom: 30px;
    }

    .contact-item {
      display: flex;
      gap: 15px;
      margin-bottom: 20px;
      align-items: center;
    }

    .contact-icon {
      width: 45px;
      height: 45px;
      background: #eef2ff;
      color: var(--primary);
      border-radius: 10px;
      display: flex;
      justify-content: center;
      align-items: center;
      font-weight: bold;
    }

    .contact-item span {
      color: var(--gray);
    }

    .contact-form {
      background: white;
      padding: 35px;
      border-radius: 15px;
      box-shadow: 0 10px 30px rgba(15, 23, 42, 0.06);
    }

    .form-group {
      margin-bottom: 20px;
    }

    .form-group label {
      display: block;
      margin-bottom: 7px;
      font-weight: 600;
    }

    .form-group input,
    .form-group textarea {
      width: 100%;
      padding: 13px 15px;
      border: 1px solid var(--border);
      border-radius: 8px;
      font-family: inherit;
      font-size: 1rem;
      outline: none;
      transition: 0.3s;
    }

    .form-group input:focus,
    .form-group textarea:focus {
      border-color: var(--primary);
      box-shadow: 0 0 0 3px rgba(99, 102, 241, 0.1);
    }

    .form-group textarea {
      min-height: 150px;
      resize: vertical;
    }

    .error {
      color: var(--danger);
      font-size: 0.85rem;
      margin-top: 5px;
      display: block;
    }

    .success-message {
      display: none;
      background: #dcfce7;
      color: var(--success);
      padding: 15px;
      border-radius: 8px;
      margin-bottom: 20px;
    }

    /* =========================
       FOOTER
    ========================== */
    footer {
      background: var(--dark);
      color: white;
      padding: 30px 0;
      text-align: center;
    }

    footer p {
      color: #94a3b8;
    }

    .social-links {
      margin-top: 15px;
      display: flex;
      justify-content: center;
      gap: 15px;
    }

    .social-links a {
      color: #cbd5e1;
      transition: 0.3s;
    }

    .social-links a:hover {
      color: white;
    }

    /* =========================
       ANIMATIONS
    ========================== */
    .fade-up {
      opacity: 0;
      transform: translateY(30px);
      animation: fadeUp 0.8s forwards;
    }

    @keyframes fadeUp {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    /* =========================
       TABLET
    ========================== */
    @media (max-width: 900px) {
      .hero {
        grid-template-columns: 1fr;
        text-align: center;
      }

      .hero-content p {
        margin-left: auto;
        margin-right: auto;
      }

      .hero-image {
        order: -1;
      }

      .profile-circle {
        width: 250px;
        height: 250px;
        font-size: 4rem;
      }

      .about-grid {
        grid-template-columns: 1fr;
      }

      .about-image {
        height: 300px;
      }

      .projects-grid {
        grid-template-columns: repeat(2, 1fr);
      }

      .contact-grid {
        grid-template-columns: 1fr;
      }
    }

    /* =========================
       MOBILE
    ========================== */
    @media (max-width: 650px) {
      section {
        padding: 70px 0;
      }

      .section-title h2 {
        font-size: 2rem;
      }

      .nav-links {
        position: absolute;
        top: 70px;
        left: 0;
        width: 100%;
        background: white;
        flex-direction: column;
        gap: 0;
        max-height: 0;
        overflow: hidden;
        transition: 0.3s ease;
        border-bottom: 1px solid #eee;
      }

      .nav-links.active {
        max-height: 400px;
      }

      .nav-links li {
        width: 100%;
        text-align: center;
      }

      .nav-links a {
        display: block;
        padding: 15px;
      }

      .menu-btn {
        display: block;
      }

      .hero-content h1 {
        font-size: 2.7rem;
      }

      .btn {
        padding: 11px 18px;
      }

      .btn-outline {
        margin-left: 5px;
      }

      .skills-grid,
      .projects-grid {
        grid-template-columns: 1fr;
      }

      .about-info {
        grid-template-columns: 1fr;
      }

      .contact-form {
        padding: 25px 20px;
      }
    }
  </style>
</head>

<body>

  <!-- =========================
       NAVIGATION
  ========================== -->
  <header>
    <div class="container">
      <nav>
        <a href="#home" class="logo">IC.</a>

        <button class="menu-btn" id="menuBtn" aria-label="Open navigation">
          ☰
        </button>

        <ul class="nav-links" id="navLinks">
          <li><a href="#home">Home</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#skills">Skills</a></li>
          <li><a href="#projects">Projects</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
    </div>
  </header>


  <!-- =========================
       HOME
  ========================== -->
  <section id="home">
    <div class="container">
      <div class="hero">

        <div class="hero-content fade-up">
          <h4>Hello, I'm</h4>

          <h1>
            Itodo <span>Caleb</span>
          </h1>

          <p>
            I'm a passionate Web Developer who creates modern,
            responsive and user-friendly websites and applications.
          </p>

          <a href="#projects" class="btn btn-primary">
            View My Work
          </a>

          <a href="#contact" class="btn btn-outline">
            Contact Me
          </a>
        </div>

        <div class="hero-image fade-up">
          <div class="profile-circle">
            IC
          </div>
        </div>

      </div>
    </div>
  </section>


  <!-- =========================
       ABOUT
  ========================== -->
  <section id="about">
    <div class="container">

      <div class="section-title">
        <h2>About Me</h2>
        <p>Get to know me and what I do</p>
      </div>

      <div class="about-grid">

        <div class="about-image">
          IC
        </div>

        <div class="about-content">
          <h3>I'm a Creative Web Developer</h3>

          <p>
            I enjoy turning ideas into beautiful, functional and
            interactive digital experiences. I focus on writing
            clean code and building websites that work perfectly
            across different screen sizes.
          </p>

          <p>
            When I'm not coding, I enjoy learning new technologies,
            working on personal projects and exploring new ideas.
          </p>

          <div class="about-info">

            <div class="info-item">
              <strong>Name:</strong>
              <span>Itodo Caleb</span>
            </div>

            <div class="info-item">
              <strong>Email:</strong>
              <span>caleb@example.com</span>
            </div>

            <div class="info-item">
              <strong>Location:</strong>
              <span>Lagos, Nigeria</span>
            </div>

            <div class="info-item">
              <strong>Freelance:</strong>
              <span>Available</span>
            </div>

          </div>
        </div>

      </div>
    </div>
  </section>


  <!-- =========================
       SKILLS
  ========================== -->
  <section id="skills">
    <div class="container">

      <div class="section-title">
        <h2>My Skills</h2>
        <p>Technologies and tools I work with</p>
      </div>

      <div class="skills-grid">

        <div class="skill">
          <div class="skill-header">
            <span>HTML</span>
            <span>95%</span>
          </div>
          <div class="skill-bar">
            <div class="skill-progress" style="width:95%"></div>
          </div>
        </div>

        <div class="skill">
          <div class="skill-header">
            <span>CSS</span>
            <span>90%</span>
          </div>
          <div class="skill-bar">
            <div class="skill-progress" style="width:90%"></div>
          </div>
        </div>

        <div class="skill">
          <div class="skill-header">
            <span>JavaScript</span>
            <span>85%</span>
          </div>
          <div class="skill-bar">
            <div class="skill-progress" style="width:85%"></div>
          </div>
        </div>

        <div class="skill">
          <div class="skill-header">
            <span>React</span>
            <span>80%</span>
          </div>
          <div class="skill-bar">
            <div class="skill-progress" style="width:80%"></div>
          </div>
        </div>

        <div class="skill">
          <div class="skill-header">
            <span>Node.js</span>
            <span>75%</span>
          </div>
          <div class="skill-bar">
            <div class="skill-progress" style="width:75%"></div>
          </div>
        </div>

        <div class="skill">
          <div class="skill-header">
            <span>Git & GitHub</span>
            <span>85%</span>
          </div>
          <div class="skill-bar">
            <div class="skill-progress" style="width:85%"></div>
          </div>
        </div>

      </div>
    </div>
  </section>


  <!-- =========================
       PROJECTS
  ========================== -->
  <section id="projects">
    <div class="container">

      <div class="section-title">
        <h2>My Projects</h2>
        <p>Some of my recent work</p>
      </div>

      <div class="projects-grid">

        <!-- Project 1 -->
        <article class="project-card">

          <div class="project-image">
            01
          </div>

          <div class="project-content">
            <h3>E-Commerce Website</h3>

            <p>
              A modern online store with product browsing,
              shopping cart and responsive design.
            </p>

            <div class="tags">
              <span class="tag">HTML</span>
              <span class="tag">CSS</span>
              <span class="tag">JavaScript</span>
            </div>

            <a href="#" class="project-link">
              View Project →
            </a>
          </div>

        </article>


        <!-- Project 2 -->
        <article class="project-card">

          <div class="project-image">
            02
          </div>

          <div class="project-content">
            <h3>Task Manager</h3>

            <p>
              A simple productivity application for creating,
              managing and completing tasks.
            </p>

            <div class="tags">
              <span class="tag">JavaScript</span>
              <span class="tag">CSS</span>
              <span class="tag">API</span>
            </div>

            <a href="#" class="project-link">
              View Project →
            </a>
          </div>

        </article>


        <!-- Project 3 -->
        <article class="project-card">

          <div class="project-image">
            03
          </div>

          <div class="project-content">
            <h3>Portfolio Website</h3>

            <p>
              A clean and responsive personal portfolio
              designed to showcase skills and projects.
            </p>

            <div class="tags">
              <span class="tag">HTML</span>
              <span class="tag">CSS</span>
              <span class="tag">JavaScript</span>
            </div>

            <a href="#" class="project-link">
              View Project →
            </a>
          </div>

        </article>

      </div>
    </div>
  </section>


  <!-- =========================
       CONTACT
  ========================== -->
  <section id="contact">
    <div class="container">

      <div class="section-title">
        <h2>Contact Me</h2>
        <p>Have a project in mind? Let's talk.</p>
      </div>

      <div class="contact-grid">

        <div class="contact-info">

          <h3>Let's work together</h3>

          <p>
            Feel free to contact me if you have a project,
            question or collaboration idea.
          </p>

          <div class="contact-item">
            <div class="contact-icon">@</div>
            <div>
              <strong>Email</strong>
              <span>caleb@example.com</span>
            </div>
          </div>

          <div class="contact-item">
            <div class="contact-icon">☎</div>
            <div>
              <strong>Phone</strong>
              <span>+234 800 000 0000</span>
            </div>
          </div>

          <div class="contact-item">
            <div class="contact-icon">📍</div>
            <div>
              <strong>Location</strong>
              <span>Lagos, Nigeria</span>
            </div>
          </div>

        </div>


        <!-- Contact Form -->
        <form class="contact-form" id="contactForm" novalidate>

          <div class="success-message" id="successMessage">
            Your message has been submitted successfully!
          </div>

          <div class="form-group">
            <label for="name">Full Name</label>

            <input
              type="text"
              id="name"
              name="name"
              placeholder="Enter your name"
            >

            <span class="error" id="nameError"></span>
          </div>


          <div class="form-group">
            <label for="email">Email Address</label>

            <input
              type="email"
              id="email"
              name="email"
              placeholder="Enter your email"
            >

            <span class="error" id="emailError"></span>
          </div>


          <div class="form-group">
            <label for="subject">Subject</label>

            <input
              type="text"
              id="subject"
              name="subject"
              placeholder="Enter subject"
            >

            <span class="error" id="subjectError"></span>
          </div>


          <div class="form-group">
            <label for="message">Message</label>

            <textarea
              id="message"
              name="message"
              placeholder="Write your message..."
            ></textarea>

            <span class="error" id="messageError"></span>
          </div>


          <button type="submit" class="btn btn-primary">
            Send Message
          </button>

        </form>

      </div>
    </div>
  </section>


  <!-- =========================
       FOOTER
  ========================== -->
  <footer>
    <div class="container">

      <p>
        © <span id="year"></span> Alex Carter. All rights reserved.
      </p>

      <div class="social-links">
        <a href="#" aria-label="GitHub">GitHub</a>
        <a href="#" aria-label="LinkedIn">LinkedIn</a>
        <a href="#" aria-label="Twitter">Twitter</a>
      </div>

    </div>
  </footer>


  <!-- =========================
       JAVASCRIPT
  ========================== -->
  <script>

    // =========================
    // MOBILE MENU
    // =========================

    const menuBtn = document.getElementById("menuBtn");
    const navLinks = document.getElementById("navLinks");

    menuBtn.addEventListener("click", () => {
      navLinks.classList.toggle("active");

      if (navLinks.classList.contains("active")) {
        menuBtn.textContent = "✕";
      } else {
        menuBtn.textContent = "☰";
      }
    });


    // Close mobile menu when link is clicked

    document.querySelectorAll(".nav-links a").forEach(link => {
      link.addEventListener("click", () => {
        navLinks.classList.remove("active");
        menuBtn.textContent = "☰";
      });
    });


    // =========================
    // CONTACT FORM VALIDATION
    // =========================

    const contactForm = document.getElementById("contactForm");

    const nameInput = document.getElementById("name");
    const emailInput = document.getElementById("email");
    const subjectInput = document.getElementById("subject");
    const messageInput = document.getElementById("message");

    const nameError = document.getElementById("nameError");
    const emailError = document.getElementById("emailError");
    const subjectError = document.getElementById("subjectError");
    const messageError = document.getElementById("messageError");

    const successMessage =
      document.getElementById("successMessage");


    function validateEmail(email) {
      return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
    }


    function clearErrors() {
      nameError.textContent = "";
      emailError.textContent = "";
      subjectError.textContent = "";
      messageError.textContent = "";
    }


    contactForm.addEventListener("submit", function(event) {

      event.preventDefault();

      clearErrors();

      successMessage.style.display = "none";

      let isValid = true;


      // Name validation

      if (nameInput.value.trim() === "") {

        nameError.textContent = "Please enter your name.";

        isValid = false;

      } else if (nameInput.value.trim().length < 2) {

        nameError.textContent =
          "Name must be at least 2 characters.";

        isValid = false;
      }


      // Email validation

      if (emailInput.value.trim() === "") {

        emailError.textContent =
          "Please enter your email address.";

        isValid = false;

      } else if (!validateEmail(emailInput.value.trim())) {

        emailError.textContent =
          "Please enter a valid email address.";

        isValid = false;
      }


      // Subject validation

      if (subjectInput.value.trim() === "") {

        subjectError.textContent =
          "Please enter a subject.";

        isValid = false;

      } else if (subjectInput.value.trim().length < 3) {

        subjectError.textContent =
          "Subject must be at least 3 characters.";

        isValid = false;
      }


      // Message validation

      if (messageInput.value.trim() === "") {

        messageError.textContent =
          "Please enter your message.";

        isValid = false;

      } else if (messageInput.value.trim().length < 10) {

        messageError.textContent =
          "Message must be at least 10 characters.";

        isValid = false;
      }


      // Form is valid

      if (isValid) {

        successMessage.style.display = "block";

        contactForm.reset();

        setTimeout(() => {
          successMessage.style.display = "none";
        }, 5000);
      }

    });


    // =========================
    // CURRENT YEAR
    // =========================

    document.getElementById("year").textContent =
      new Date().getFullYear();


    // =========================
    // SMOOTH NAVIGATION
    // =========================

    document.querySelectorAll('a[href^="#"]').forEach(anchor => {

      anchor.addEventListener("click", function(event) {

        const target = document.querySelector(
          this.getAttribute("href")
        );

        if (target) {

          event.preventDefault();

          target.scrollIntoView({
            behavior: "smooth"
          });

        }

      });

    });

  </script>

</body>
</html>
