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
  gap: 2rem;
  flex-wrap: wrap;
  justify-content: center;
}

.project-card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%;
  max-width: 360px;
  flex: 1 1 320px;
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
  max-height: 160px;
  object-fit: contain;
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
   max-width: 90%;
  line-height: 1.6;
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

.github-button {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 0.6rem 1.2rem;
  background-color: #2d70c9;
  color: white;
  font-weight: bold;
  font-size: 1rem;
  border-radius: 8px;
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.github-button:hover {
  background-color: #1e56a0;
}

</style>


<div class="card-grid">

  <!-- 🟦 Your osTicket card -->

  <div class="project-card-wrapper">
  
    <div class="project-card">
      <img src="/assets/img/logo copy.png" alt="osTicket Helpdesk deployment">
      <div class="project-card-content">
        <h3>osTicket Helpdesk Deployment (Microsoft Azure)</h3>
      <p>This project simulates the deployment and configuration of a helpdesk ticketing system using the LAMP stack (Linux, Apache, MySQL, PHP) and osTicket.</p>

        <div style="margin-top: 1rem; text-align: center;">
        <a href="https://github.com/Slewis916/osTicket-Installation.git" target="_blank" rel="noopener noreferrer" class="project-link">
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
        <a href="https://github.com/Slewis916/IP-Allow-List-Automation.git" target="_blank" rel="noopener noreferrer" class="project-link">
         <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" alt="GitHub logo" width="18" style="vertical-align: middle; margin-right: 6px;">
        Github Repo
        </a>
        </div>
      </div>
    </div>
  </div>
<!-- 🟪 Your Phishing card -->
</div>