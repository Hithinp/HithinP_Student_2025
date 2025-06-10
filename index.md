---
layout: base
title: Hithin Pulamarasetty
description: Home Page
hide: true
image: /images/mario_animation.png
---

<!-- Main Content Area -->
<div class="main-content">
  <div class="page-title">
    <h1>Welcome to My Dashboard</h1>
    <p>Your one-stop place to learn more about my work, experience, and ways to get in touch.</p>
  </div>

  <div class="about-container">
    <!-- Screenshot Profile Card -->
    <div class="profile">
      <h3><i class="fas fa-qrcode"></i> My Profile</h3>
      <div class="qr-code">
        <img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-06-09 at 9.53.53 PM.jpeg" alt="Screenshot 1">
      </div>
      <div class="qr-desc">Scan to view my digital profile</div>
    </div>

    <!-- Links Section -->
    <div class="links">
      <a class="link-card email" href="mailto:hithinp@gmail.com">
        <i class="fas fa-envelope"></i>
        <div class="content">
          <h4>Email</h4>
          <p>hithinp@gmail.com</p>
        </div>
      </a>
      <a class="link-card github" href="https://github.com/Hithinp">
        <i class="fab fa-github"></i>
        <div class="content">
          <h4>GitHub</h4>
          <p>github.com/hithin</p>
        </div>
      </a>
      <a class="link-card linkedin" href="https://www.linkedin.com/in/hithinp">
        <i class="fab fa-linkedin"></i>
        <div class="content">
          <h4>LinkedIn</h4>
          <p>linkedin.com/in/hithinp</p>
        </div>
      </a>
      <a class="link-card resume" href="https://www.canva.com/design/DAGp7N7WX1o/ZzquNIIBr2z0hGxQblvh6g/edit?utm_content=DAGp7N7WX1o&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton">
        <i class="fas fa-file-alt"></i>
        <div class="content">
          <h4>Resume</h4>
          <p>View my resume</p>
        </div>
      </a>
      <a class="link-card onshape" href="https://cad.onshape.com/documents?resourceType=resourceuserowner&nodeId=672eaeee5c1e190ae6501ec7">
        <i class="fas fa-cube"></i>
        <div class="content">
          <h4>Onshape</h4>
          <p>See my CAD work</p>
        </div>
      </a>
    </div>
  </div>
</div>

<!-- External FontAwesome -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

<!-- Inline Styles -->
<style>
/* === Customizable Theme Color === */
:root {
  --primary-color: #007BFF; /* <== CHANGE THIS TO WHATEVER COLOR YOU WANT */
}

/* === General Layout === */
body {
  font-family: 'Segoe UI', sans-serif;
  margin: 0;
  background: #f9f9f9;
  color: #333;
}

.main-content {
  padding: 40px;
}

.page-title h1 {
  color: var(--primary-color);
  font-size: 2.5rem;
  margin-bottom: 0.5rem;
}

.page-title p {
  font-size: 1.2rem;
  color: #555;
}

/* === About Section === */
.about-container {
  display: flex;
  flex-wrap: wrap;
  gap: 30px;
  margin-top: 30px;
}

.profile {
  flex: 1;
  min-width: 250px;
  background: white;
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.1);
  padding: 20px;
  text-align: center;
}

.qr-code img {
  width: 150px;
  height: auto;
  margin: 20px 0;
}

.qr-desc {
  font-size: 0.9rem;
  color: #777;
}

/* === Link Cards === */
.links {
  flex: 2;
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.link-card {
  display: flex;
  align-items: center;
  background: white;
  border-left: 5px solid var(--primary-color);
  border-radius: 8px;
  padding: 15px;
  text-decoration: none;
  color: inherit;
  box-shadow: 0 2px 6px rgba(0,0,0,0.1);
  transition: transform 0.2s ease;
}

.link-card:hover {
  transform: translateY(-3px);
}

.link-card i {
  font-size: 1.5rem;
  margin-right: 15px;
  color: var(--primary-color);
}

.link-card .content h4 {
  margin: 0;
  font-size: 1.1rem;
  color: #222;
}

.link-card .content p {
  margin: 0;
  color: #666;
  font-size: 0.9rem;
}

/* === Footer === */
.footer {
  text-align: center;
  padding: 20px 0;
  background: #fff;
  color: #aaa;
  margin-top: 40px;
}
</style>

<div style="font-family: Arial, sans-serif; max-width: 700px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; box-shadow: 0 2px 8px rgba(0,0,0,0.05);">
  <h2 style="font-size: 1.8rem; margin-bottom: 0.75rem;">🔧 About Me</h2>
  <p style="font-size: 1rem; color: #555; line-height: 1.6;">
    I specialize in AI, robotics, and software development—blending technical precision with creative problem-solving across real-world engineering projects.
  </p>
  <ul style="list-style: none; padding-left: 0; margin-top: 1rem;">
    <li style="margin-bottom: 0.5rem;">🤖 <strong>AI & Automation:</strong> WPILib autonomous code, Limelight vision tracking, task management tools.</li>
    <li style="margin-bottom: 0.5rem;">🛠️ <strong>Hardware Design:</strong> Built a DIY CNC mill from scratch using CAD and custom fabrication.</li>
    <li style="margin-bottom: 0.5rem;">💻 <strong>Full-Stack Skills:</strong> Created web-based tools to support business operations and logistics.</li>
    <li style="margin-bottom: 0.5rem;">📐 <strong>CAD & Systems:</strong> Deep knowledge of modeling, optimization, and mechanical systems.</li>
    <li style="margin-bottom: 0.5rem;">🚀 <strong>Team-Oriented:</strong> FRC design experience with a focus on collaboration and iteration.</li>
  </ul>
</div>


<!-- Footer -->
<div class="footer">
  <p>&copy; 2025 Hithin Pulamarasetty. All rights reserved.</p>
</div>
