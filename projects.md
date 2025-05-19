---
layout: default
title: "Projects"
permalink: /projects/
---


<ul>
  {% for project in site.projects %}
    <li>
      <a href="{{ project.url }}">{{ project.title }}</a> - {{ project.description }}
    </li>
  {% endfor %}
</ul>


<style>
  .card-grid {
    display: flex;
    flex-wrap: wrap;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
    max-width: 1100px;
    margin: auto;
    padding: 2rem;
    justify-content: center;
  }

  .project-card {
  max-width: 360px; /* 🔹 Limit the card width */
  margin: auto; /* 🔹 Center card if in solo display */
  background: #fff;
  border-radius: 12px;
  box-shadow: 0 8px 20px rgba(0,0,0,0.06);
  overflow: hidden;
  display: flex;
  flex-direction: column;
  transition: transform 0.2s ease;
  justify-content: space-between;  /* Distributes content evenly */
  height: 100%
  flex: 1 1 300px;
}

.project-card-content {
  padding: 1.0rem 1.2rem;
  flex-grow: 1;
  text-align: center; /* 🔹 Center text */
}

.project-card a {
  margin-top: 1rem;
  display: inline-block;
  padding: 0.6rem 1.2rem;
  background-color: #2d70c9;
  color: white;
  border-radius: 6px;
  font-weight: bold;
  text-decoration: none;
}

.project-card a:hover {
  background-color: #1f4f95;
}

.project-card img {
  margin-bottom: 0;
  display: block;
}

.project-card h3 {
  margin-top: 0.75rem;  /* ↓ Lower this number for tighter spacing */
  font-size: 1.3rem;
}

.project-card:hover {
  box-shadow: 0 10px 24px rgba(0,0,0,0.1);
  transform: translateY(-4px);
}

.project-card p {
  text-align: left;
}

.project-card:hover {
  transform: scale(1.02);
  box-shadow: 0 12px 28px rgba(0,0,0,0.08);
}
 .project-link {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  font-weight: bold;
  text-decoration: none;
  background: #2d70c9;
  color: white;
  padding: 0.6rem 1.2rem;
  border-radius: 8px;
  font-size: 1rem;
}

</style>


<div class="card-grid">

  <!-- 🟦 Your osTicket card -->

  <div class="project-card-wrapper">
  
    <div class="project-card">
      <img src="/assets/img/logo copy.png" alt="osTicket Helpdesk deployment">
      <div class="project-card-content">
        <h3>osTicket Helpdesk Deployment (Microsoft Azure)</h3>
      <p>This project simulates the deployment and configuration of a helpdesk ticketing system using the LAMP stack (Linux, Apache, MySQL, PHP) and osTicket. It includes request handling, escalation workflows, and ticket lifecycle documentation.</p>

        <div style="margin-top: 1rem; text-align: center;">
        <a href="https://github.com/Slewis916/osTicket-Installation.git" target="_blank" class="project-link">
         <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" alt="GitHub logo"
          width="18" 
          style="vertical-align: middle; 
          margin-right: 8px;">
         Github Repo
        </a>
        </div>
      </div>
    </div>
  </div>
  

  <!-- 🐍 Python automation card -->

  <div class="project-card-wrapper">
  
    <div class="project-card">
      <img src="/assets/img/python.png" alt="Python Script Project">
      <div class="project-card-content">
        <h3>Allow-List IP Automation Script</h3>
        <p>Python script designed to automate updates to an allow-list file by removing unauthorized IPs from access logs. Includes logic for comparison, validation, and reporting.</p>
        <div style="margin-top: 1rem; text-align: center;">
        <a href="https://github.com/Slewis916/IP-Allow-List-Automation.git" target="_blank" class="project-link">
         <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" alt="GitHub logo" width="18" style="vertical-align: middle; margin-right: 6px;">
        Github Repo
        </a>
        </div>
      </div>
    </div>
  </div>
<!-- 🟪 Your Phishing card -->
</div>