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
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
    max-width: 1100px;
    margin: auto;
    padding: 2rem;
  }

  .project-card {
    background: #fff;
    border-radius: 12px;
    box-shadow: 0 8px 20px rgba(0,0,0,0.06);
    overflow: hidden;
    display: flex;
    flex-direction: column;
    transition: transform 0.2s ease;
  }

  .project-card:hover {
    transform: translateY(-5px);
  }

  .project-card img {
    width: 100%;
    height: 180px;
    object-fit: cover;
  }

  .project-card-content {
    padding: 1rem 1.2rem;
    flex-grow: 1;
  }

  .project-card h3 {
    margin-top: 0;
    font-size: 1.2rem;
    color: #2d70c9;
  }

  .project-card p {
    font-size: 0.95rem;
    color: #333;
    margin-bottom: 1rem;
  }

  .project-card a {
    display: inline-block;
    text-decoration: none;
    font-weight: bold;
    color: #fff;
    background-color: #2d70c9;
    padding: 0.5rem 1rem;
    border-radius: 6px;
    font-size: 0.9rem;
  }

  .project-label {
    position: absolute;
    top: 12px;
    right: 12px;
    background: #f9a825;
    color: #fff;
    font-size: 0.7rem;
    font-weight: bold;
    padding: 4px 8px;
    border-radius: 4px;
  }

  .project-card-wrapper {
    position: relative;
  }
</style>


<div class="card-grid">

  <!-- 🟦 Your osTicket card -->
  <!-- 🟪 Your Phishing card -->

  <!-- 🐍 Python automation card -->
  <div class="project-card-wrapper">
    <div class="project-label">Python</div>
    <div class="project-card">
      <img src="/assets/img/ip-automation.jpg" alt="Python Script Project">
      <div class="project-card-content">
        <h3>Allow-List IP Automation Script</h3>
        <p>Python script designed to automate updates to an allow-list file by removing unauthorized IPs from access logs. Includes logic for comparison, validation, and reporting.</p>
        <a href="https://github.com/Slewis916/IP-Allowlist-Automation" target="_blank">View Project</a>
      </div>
    </div>
  </div>

</div>