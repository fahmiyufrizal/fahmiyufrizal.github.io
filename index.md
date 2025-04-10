---
layout: home
title: ""
---

<div style="display: flex; align-items: center; flex-wrap: wrap; gap: 1.5rem; margin-bottom: 2rem;">
  <img src="https://github.com/fahmiyufrizal.png" width="120" height="120" alt="Fahmi Yufrizal" style="border-radius: 10px;" />

  <div>
    <h1 style="margin: 0 0 0.3em 0;">Hi, I'm <strong>Fahmi Yufrizal</strong> 👋</h1>
    <p style="margin: 0.3em 0;">
      Software engineer focused on backend development, Laravel, and clean architecture.
    </p>
    <p style="margin: 0.3em 0;">
      ✍️ Writing about dev life · 💻 Building useful tools · 🔗
      <a href="https://github.com/fahmiyufrizal" target="_blank">github.com/fahmiyufrizal</a>
    </p>
  </div>
</div>

---

### 📦 Repo

<style>
  .repo-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 1rem;
    margin-top: 1rem;
  }
  .repo-card {
    border: 1px solid #ccc;
    border-radius: 10px;
    padding: 1rem;
    background-color: rgba(255,255,255,0.05);
    transition: all 0.2s;
  }
  body[data-theme='dark'] .repo-card {
    border-color: #333;
    background-color: #1a1a1a;
  }
  .repo-card:hover {
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  }
</style>

<div id="repo-list" class="repo-grid">Loading repositories...</div>

<script>
  fetch("https://api.github.com/users/fahmiyufrizal/repos?sort=updated&per_page=6")
    .then(res => res.json())
    .then(repos => {
      const container = document.getElementById("repo-list");
      container.innerHTML = repos.map(repo => `
        <div class="repo-card">
          <strong><a href="${repo.html_url}" target="_blank">${repo.name}</a></strong>
          <p style="font-size: 0.85em; color: gray; margin: 0.5rem 0;">
            ${repo.description || "No description"}
          </p>
        </div>
      `).join("");
    })
    .catch(() => {
      document.getElementById("repo-list").innerText = "Failed to load repositories.";
    });
</script>

---

